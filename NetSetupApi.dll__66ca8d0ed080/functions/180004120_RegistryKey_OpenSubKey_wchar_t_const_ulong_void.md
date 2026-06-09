# RegistryKey::OpenSubKey(wchar_t const *,ulong,void *)

- ea: `0x180004120`
- end: `0x180004251`
- name: `?OpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z`
- size: `305`
- prototype: `HKEY __fastcall(HKEY *, HKEY, const WCHAR *, REGSAM)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180003f40`
- `0x180006af8`
- `0x18000e0d8`

## callees

- `0x180004120`
- `0x1800065d4`
- `0x18000895c`
- `0x18000fbfc`
- `0x1800119f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000422d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000422d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000416e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800041d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000416e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800041d0`

## pseudocode

```c
HKEY __fastcall RegistryKey::OpenSubKey(HKEY *a1, HKEY a2, const WCHAR *a3, REGSAM a4)
{
  HKEY v4; // rbp
  LSTATUS v8; // edi
  DWORD LastError; // eax
  _BYTE pExceptionObject[208]; // [rsp+38h] [rbp-110h] BYREF
  HKEY phkResult; // [rsp+108h] [rbp-40h] BYREF

  phkResult = a2;
  v4 = *a1;
  phkResult = 0;
  v8 = RegOpenKeyExW(v4, a3, 0, a4, &phkResult);
  if ( v8 == 5 )
    v8 = RegOpenKeyExW(v4, a3, 4u, a4, &phkResult);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids,
        (_DWORD)a3,
        v8);
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v8);
    throw (Win32Exception *)pExceptionObject;
  }
  if ( !phkResult )
  {
    LastError = GetLastError();
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, LastError);
    throw (Win32Exception *)pExceptionObject;
  }
  *(_QWORD *)a2 = phkResult;
  return a2;
}

```

## disassembly

```asm
0x180004120  mov     r11, rsp
0x180004123  push    rbx
0x180004124  push    rbp
0x180004125  push    rsi
0x180004126  push    rdi
0x180004127  push    r14
0x180004129  sub     rsp, 120h
0x180004130  mov     rax, cs:__security_cookie
0x180004137  xor     rax, rsp
0x18000413a  mov     [rsp+148h+var_38], rax
0x180004142  mov     [rsp+148h+var_40], rdx
0x18000414a  xor     eax, eax
0x18000414c  mov     rbp, [rcx]
0x18000414f  mov     r14, r8
0x180004152  mov     [r11-40h], rax
0x180004156  mov     rbx, rdx
0x180004159  lea     rax, [r11-40h]
0x18000415d  xor     r8d, r8d; ulOptions
0x180004160  mov     rdx, r14; lpSubKey
0x180004163  mov     [rsp+148h+phkResult], rax; phkResult
0x180004168  mov     rcx, rbp; hKey
0x18000416b  mov     esi, r9d
0x18000416e  call    cs:__imp_RegOpenKeyExW
0x180004174  mov     edi, eax
0x180004176  cmp     eax, 5
0x180004179  jz      short loc_1800041B4
0x18000417b  test    edi, edi
0x18000417d  jnz     short loc_1800041DA
0x18000417f  mov     rax, [rsp+148h+var_40]
0x180004187  test    rax, rax
0x18000418a  jz      loc_18000422D
0x180004190  mov     [rbx], rax
0x180004193  mov     rax, rbx
0x180004196  mov     rcx, [rsp+148h+var_38]
0x18000419e  xor     rcx, rsp; StackCookie
0x1800041a1  call    __security_check_cookie
0x1800041a6  add     rsp, 120h
0x1800041ad  pop     r14
0x1800041af  pop     rdi
0x1800041b0  pop     rsi
0x1800041b1  pop     rbp
0x1800041b2  pop     rbx
0x1800041b3  retn
0x1800041b4  lea     rax, [rsp+148h+var_40]
0x1800041bc  mov     r9d, esi; samDesired
0x1800041bf  mov     r8d, 4; ulOptions
0x1800041c5  mov     [rsp+148h+phkResult], rax; phkResult
0x1800041ca  mov     rdx, r14; lpSubKey
0x1800041cd  mov     rcx, rbp; hKey
0x1800041d0  call    cs:__imp_RegOpenKeyExW
0x1800041d6  mov     edi, eax
0x1800041d8  jmp     short loc_18000417B
0x1800041da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800041e1  lea     rax, WPP_GLOBAL_Control
0x1800041e8  cmp     rcx, rax
0x1800041eb  jz      short loc_18000420F
0x1800041ed  cmp     byte ptr [rcx+19h], 2
0x1800041f1  jb      short loc_18000420F
0x1800041f3  mov     rcx, [rcx+10h]
0x1800041f7  lea     r8, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids
0x1800041fe  mov     edx, 0Eh
0x180004203  mov     dword ptr [rsp+148h+phkResult], edi
0x180004207  mov     r9, r14
0x18000420a  call    WPP_SF_SD
0x18000420f  mov     edx, edi; int
0x180004211  lea     rcx, [rsp+148h+pExceptionObject]; this
0x180004216  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x18000421b  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180004222  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x180004227  call    _CxxThrowException_0
0x18000422d  call    cs:__imp_GetLastError
0x180004233  mov     edx, eax; int
0x180004235  lea     rcx, [rsp+148h+pExceptionObject]; this
0x18000423a  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x18000423f  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180004246  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x18000424b  call    _CxxThrowException_0
```
