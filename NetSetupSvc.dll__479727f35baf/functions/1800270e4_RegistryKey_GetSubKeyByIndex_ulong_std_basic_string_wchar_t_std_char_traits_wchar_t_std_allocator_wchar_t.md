# RegistryKey::GetSubKeyByIndex(ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1800270e4`
- end: `0x1800271e9`
- name: `?GetSubKeyByIndex@RegistryKey@@QEBA_NKAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `261`
- prototype: `char __fastcall(HKEY *, DWORD, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180026980`
- `0x1800271f0`
- `0x180028104`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x1800078f8`
- `0x180008c78`
- `0x18002650c`
- `0x1800270e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180027148`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180027148`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall RegistryKey::GetSubKeyByIndex(HKEY *a1, DWORD a2, __int64 a3)
{
  HKEY v3; // rcx
  unsigned int v5; // ebx
  _BYTE pExceptionObject[208]; // [rsp+40h] [rbp-2F8h] BYREF
  DWORD cchName[4]; // [rsp+110h] [rbp-228h] BYREF
  WCHAR Name[256]; // [rsp+120h] [rbp-218h] BYREF

  v3 = *a1;
  cchName[0] = 256;
  v5 = RegEnumKeyExW(v3, a2, Name, cchName, 0, 0, 0, 0);
  if ( v5 == 259 )
    return 0;
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids, v5);
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v5);
    throw (Win32Exception *)pExceptionObject;
  }
  std::wstring::_Assign<wchar_t>(a3, Name, cchName[0]);
  return 1;
}

```

## disassembly

```asm
0x1800270e4  mov     [rsp+arg_18], rbx
0x1800270e9  push    rdi
0x1800270ea  sub     rsp, 330h
0x1800270f1  mov     rax, cs:__security_cookie
0x1800270f8  xor     rax, rsp
0x1800270fb  mov     [rsp+338h+var_18], rax
0x180027103  mov     rcx, [rcx]; hKey
0x180027106  lea     r9, [rsp+338h+cchName]; lpcchName
0x18002710e  mov     [rsp+338h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180027117  mov     rdi, r8
0x18002711a  mov     [rsp+338h+lpcchClass], 0; lpcchClass
0x180027123  lea     r8, [rsp+338h+Name]; lpName
0x18002712b  mov     [rsp+338h+lpClass], 0; lpClass
0x180027134  mov     [rsp+338h+lpReserved], 0; lpReserved
0x18002713d  mov     [rsp+338h+cchName], 100h
0x180027148  call    cs:__imp_RegEnumKeyExW
0x18002714e  mov     ebx, eax
0x180027150  cmp     eax, 103h
0x180027155  jnz     short loc_18002715B
0x180027157  xor     al, al
0x180027159  jmp     short loc_1800271C8
0x18002715b  test    ebx, ebx
0x18002715d  jz      short loc_1800271AE
0x18002715f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027166  lea     rax, WPP_GLOBAL_Control
0x18002716d  cmp     rcx, rax
0x180027170  jz      short loc_180027190
0x180027172  cmp     byte ptr [rcx+19h], 2
0x180027176  jb      short loc_180027190
0x180027178  mov     rcx, [rcx+10h]
0x18002717c  lea     r8, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids
0x180027183  mov     edx, 0Bh
0x180027188  mov     r9d, ebx
0x18002718b  call    WPP_SF_d
0x180027190  mov     edx, ebx; int
0x180027192  lea     rcx, [rsp+338h+pExceptionObject]; this
0x180027197  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x18002719c  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x1800271a3  lea     rcx, [rsp+338h+pExceptionObject]; pExceptionObject
0x1800271a8  call    _CxxThrowException_0
0x1800271ae  mov     r8d, [rsp+338h+cchName]
0x1800271b6  lea     rdx, [rsp+338h+Name]
0x1800271be  mov     rcx, rdi
0x1800271c1  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800271c6  mov     al, 1
0x1800271c8  mov     rcx, [rsp+338h+var_18]
0x1800271d0  xor     rcx, rsp; StackCookie
0x1800271d3  call    __security_check_cookie
0x1800271d8  mov     rbx, [rsp+338h+arg_18]
0x1800271e0  add     rsp, 330h
0x1800271e7  pop     rdi
0x1800271e8  retn
```
