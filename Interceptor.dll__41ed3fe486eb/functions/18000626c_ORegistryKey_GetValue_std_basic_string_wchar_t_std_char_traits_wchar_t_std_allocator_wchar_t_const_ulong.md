# ORegistryKey::GetValue(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong &)

- ea: `0x18000626c`
- end: `0x18000635b`
- name: `?GetValue@ORegistryKey@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAK@Z`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800052dc`

## callees

- `0x180005e18`
- `0x1800060f4`
- `0x18000626c`
- `0x1800266e0`
- `0x1800282a0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800062cf`
- `ADVAPI32!RegQueryValueExW` at `0x1800062cf`

## pseudocode

```c
bool __fastcall ORegistryKey::GetValue(__int64 a1, __int64 a2, BYTE *lpData)
{
  __int64 v4; // rbx
  HKEY v5; // rcx
  bool v6; // cc
  LSTATUS v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r9
  DWORD Type; // [rsp+30h] [rbp-3B8h] BYREF
  DWORD cbData[3]; // [rsp+34h] [rbp-3B4h] BYREF
  _BYTE pExceptionObject[912]; // [rsp+40h] [rbp-3A8h] BYREF

  v4 = a2;
  v5 = *(HKEY *)(a1 + 48);
  if ( !v5 )
  {
    OException::OException((__int64)pExceptionObject);
    throw (OException *)pExceptionObject;
  }
  v6 = *(_QWORD *)(a2 + 24) <= 7u;
  Type = 4;
  cbData[0] = 4;
  if ( !v6 )
    a2 = *(_QWORD *)a2;
  v7 = RegQueryValueExW(v5, (LPCWSTR)a2, 0, &Type, lpData, cbData);
  if ( !v7 )
    return Type == 4;
  if ( v7 != 2 && v7 != 234 )
  {
    OException::OException((__int64)pExceptionObject, v8, v7, v9, (_QWORD *)(a1 + 16), v4);
    throw (OException *)pExceptionObject;
  }
  return 0;
}

```

## disassembly

```asm
0x18000626c  mov     [rsp+arg_18], rbx
0x180006271  push    rdi
0x180006272  sub     rsp, 3E0h
0x180006279  mov     rax, cs:__security_cookie
0x180006280  xor     rax, rsp
0x180006283  mov     [rsp+3E8h+var_18], rax
0x18000628b  mov     rdi, rcx
0x18000628e  mov     rbx, rdx
0x180006291  mov     rcx, [rcx+30h]; hKey
0x180006295  test    rcx, rcx
0x180006298  jz      loc_18000633F
0x18000629e  cmp     qword ptr [rdx+18h], 7
0x1800062a3  mov     [rsp+3E8h+Type], 4
0x1800062ab  mov     [rsp+3E8h+cbData], 4
0x1800062b3  jbe     short loc_1800062B8
0x1800062b5  mov     rdx, [rdx]; lpValueName
0x1800062b8  lea     rax, [rsp+3E8h+cbData]
0x1800062bd  mov     [rsp+3E8h+lpcbData], rax; lpcbData
0x1800062c2  lea     r9, [rsp+3E8h+Type]; lpType
0x1800062c7  mov     [rsp+3E8h+lpData], r8; lpData
0x1800062cc  xor     r8d, r8d; lpReserved
0x1800062cf  call    cs:__imp_RegQueryValueExW
0x1800062d5  test    eax, eax
0x1800062d7  jz      short loc_1800062E9
0x1800062d9  cmp     eax, 2
0x1800062dc  jz      short loc_1800062E5
0x1800062de  cmp     eax, 0EAh
0x1800062e3  jnz     short loc_180006312
0x1800062e5  xor     al, al
0x1800062e7  jmp     short loc_1800062F1
0x1800062e9  cmp     [rsp+3E8h+Type], 4
0x1800062ee  setz    al
0x1800062f1  mov     rcx, [rsp+3E8h+var_18]
0x1800062f9  xor     rcx, rsp; StackCookie
0x1800062fc  call    __security_check_cookie
0x180006301  mov     rbx, [rsp+3E8h+arg_18]
0x180006309  add     rsp, 3E0h
0x180006310  pop     rdi
0x180006311  retn
0x180006312  lea     rcx, [rdi+10h]
0x180006316  mov     [rsp+3E8h+lpcbData], rbx
0x18000631b  mov     [rsp+3E8h+lpData], rcx
0x180006320  mov     r8d, eax
0x180006323  lea     rcx, [rsp+3E8h+pExceptionObject]
0x180006328  call    ??$?0$0DP@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V01@@OException@@QEAA@W4exceptionType@et@@IAEAY0DP@$$CB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; OException::OException(et::exceptionType,uint,wchar_t const (&)[63],std::wstring const &,std::wstring const &)
0x18000632d  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x180006334  lea     rcx, [rsp+3E8h+pExceptionObject]; pExceptionObject
0x180006339  call    _CxxThrowException
0x18000633f  lea     rcx, [rsp+3E8h+pExceptionObject]
0x180006344  call    ??$?0$0FN@@OException@@QEAA@W4exceptionType@et@@AEAY0FN@$$CB_W@Z; OException::OException(et::exceptionType,wchar_t const (&)[93])
0x180006349  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x180006350  lea     rcx, [rsp+3E8h+pExceptionObject]; pExceptionObject
0x180006355  call    _CxxThrowException
```
