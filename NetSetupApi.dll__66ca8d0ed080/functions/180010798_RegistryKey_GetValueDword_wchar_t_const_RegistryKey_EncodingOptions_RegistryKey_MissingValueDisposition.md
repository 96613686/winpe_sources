# RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)

- ea: `0x180010798`
- end: `0x1800108dd`
- name: `?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z`
- size: `325`
- prototype: `__int64 __fastcall(HKEY *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180003f40`

## callees

- `0x1800065d4`
- `0x180006608`
- `0x18000895c`
- `0x18000fbfc`
- `0x180010798`
- `0x180010df0`
- `0x1800119f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800107f0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800107f0`

## pseudocode

```c
__int64 __fastcall RegistryKey::GetValueDword(HKEY *a1)
{
  HKEY v1; // rcx
  LSTATUS v2; // eax
  signed int v3; // ebx
  _BYTE pExceptionObject[208]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+100h] [rbp+0h] BYREF
  DWORD Type; // [rsp+104h] [rbp+4h] BYREF
  BYTE Data[4]; // [rsp+108h] [rbp+8h] BYREF

  v1 = *a1;
  *(_DWORD *)Data = 0;
  cbData = 4;
  Type = 0;
  v2 = RegQueryValueExW(v1, L"ForceAllowApi", 0, &Type, Data, &cbData);
  v3 = v2;
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (unsigned int)WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids,
        (unsigned int)L"ForceAllowApi",
        v2);
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v3);
    throw (Win32Exception *)pExceptionObject;
  }
  if ( Type != 4 || cbData != 4 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_SDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, Type, (unsigned int)L"ForceAllowApi", Type, cbData);
    HResultException::HResultException((HResultException *)pExceptionObject, -2147023267);
    throw (HResultException *)pExceptionObject;
  }
  return *(unsigned int *)Data;
}

```

## disassembly

```asm
0x180010798  mov     [rsp-8+arg_8], rbx
0x18001079d  push    rbp
0x18001079e  lea     rbp, [rsp-20h]
0x1800107a3  sub     rsp, 120h
0x1800107aa  mov     rax, cs:__security_cookie
0x1800107b1  xor     rax, rsp
0x1800107b4  mov     [rbp+20h+var_10], rax
0x1800107b8  mov     rcx, [rcx]; hKey
0x1800107bb  lea     rax, [rbp+20h+cbData]
0x1800107bf  mov     [rsp+120h+lpcbData], rax; lpcbData
0x1800107c4  lea     r9, [rbp+20h+Type]; lpType
0x1800107c8  lea     rax, [rbp+20h+Data]
0x1800107cc  mov     dword ptr [rbp+20h+Data], 0
0x1800107d3  xor     r8d, r8d; lpReserved
0x1800107d6  mov     [rsp+120h+lpData], rax; lpData
0x1800107db  lea     rdx, aForceallowapi; "ForceAllowApi"
0x1800107e2  mov     [rbp+20h+cbData], 4
0x1800107e9  mov     [rbp+20h+Type], 0
0x1800107f0  call    cs:__imp_RegQueryValueExW
0x1800107f6  mov     ebx, eax
0x1800107f8  test    eax, eax
0x1800107fa  jz      short loc_180010853
0x1800107fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180010803  lea     rdx, WPP_GLOBAL_Control
0x18001080a  cmp     rcx, rdx
0x18001080d  jz      short loc_180010835
0x18001080f  cmp     byte ptr [rcx+19h], 2
0x180010813  jb      short loc_180010835
0x180010815  mov     rcx, [rcx+10h]
0x180010819  lea     r9, aForceallowapi; "ForceAllowApi"
0x180010820  mov     edx, 17h
0x180010825  mov     dword ptr [rsp+120h+lpData], eax
0x180010829  lea     r8, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids
0x180010830  call    WPP_SF_SD
0x180010835  mov     edx, ebx; int
0x180010837  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18001083c  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180010841  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180010848  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18001084d  call    _CxxThrowException_0
0x180010853  mov     r8d, [rbp+20h+Type]
0x180010857  mov     eax, [rbp+20h+cbData]
0x18001085a  cmp     r8d, 4
0x18001085e  jnz     short loc_180010885
0x180010860  cmp     eax, r8d
0x180010863  jnz     short loc_180010885
0x180010865  mov     eax, dword ptr [rbp+20h+Data]
0x180010868  mov     rcx, [rbp+20h+var_10]
0x18001086c  xor     rcx, rsp; StackCookie
0x18001086f  call    __security_check_cookie
0x180010874  mov     rbx, [rsp+120h+arg_8]
0x18001087c  add     rsp, 120h
0x180010883  pop     rbp
0x180010884  retn
0x180010885  mov     rcx, cs:WPP_GLOBAL_Control
0x18001088c  lea     rdx, WPP_GLOBAL_Control
0x180010893  cmp     rcx, rdx
0x180010896  jz      short loc_1800108BC
0x180010898  cmp     byte ptr [rcx+19h], 2
0x18001089c  jb      short loc_1800108BC
0x18001089e  mov     rcx, [rcx+10h]
0x1800108a2  lea     r9, aForceallowapi; "ForceAllowApi"
0x1800108a9  mov     dword ptr [rsp+120h+lpcbData], eax
0x1800108ad  mov     edx, 18h
0x1800108b2  mov     dword ptr [rsp+120h+lpData], r8d
0x1800108b7  call    WPP_SF_SDD
0x1800108bc  mov     edx, 8007065Dh; int
0x1800108c1  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800108c6  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800108cb  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800108d2  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800108d7  call    _CxxThrowException_0
```
