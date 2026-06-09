# AuxUlibInitialize

- ea: `0x18013d108`
- end: `0x18013d2b4`
- name: `AuxUlibInitialize`
- size: `428`
- prototype: `BOOL __stdcall()`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18013c4c8`

## callees

- `0x18013d108`
- `0x18013d700`
- `0x18013e72c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18013d1ed`
- `KERNEL32!GetLastError` at `0x18013d239`
- `KERNEL32!GetLastError` at `0x18013d1ed`
- `KERNEL32!GetLastError` at `0x18013d239`
- `KERNEL32!SetLastError` at `0x18013d287`
- `KERNEL32!SetLastError` at `0x18013d287`
- `KERNEL32!GetModuleHandleW` at `0x18013d182`
- `KERNEL32!GetModuleHandleW` at `0x18013d19b`
- `KERNEL32!GetModuleHandleW` at `0x18013d1bb`
- `KERNEL32!GetModuleHandleW` at `0x18013d182`
- `KERNEL32!GetModuleHandleW` at `0x18013d19b`
- `KERNEL32!GetModuleHandleW` at `0x18013d1bb`
- `KERNEL32!GetVersionExW` at `0x18013d15e`
- `KERNEL32!GetVersionExW` at `0x18013d15e`
- `KERNEL32!GetProcAddress` at `0x18013d1db`
- `KERNEL32!GetProcAddress` at `0x18013d20b`
- `KERNEL32!GetProcAddress` at `0x18013d227`
- `KERNEL32!GetProcAddress` at `0x18013d1db`
- `KERNEL32!GetProcAddress` at `0x18013d20b`
- `KERNEL32!GetProcAddress` at `0x18013d227`

## string_xrefs

- `0x18013d17b`: `api-ms-win-core-memory-l1-1-0.dll`
- `0x18013d194`: `api-ms-win-core-libraryloader-l1-1-0.dll`
- `0x18013d1b4`: `ntdll.dll`
- `0x18013d1d1`: `SetSystemFileCacheSize`
- `0x18013d21d`: `PrivIsDllSynchronizationHeld`

## pseudocode

```c
BOOL __stdcall AuxUlibInitialize()
{
  HMODULE ModuleHandleW; // rdi
  HMODULE v2; // rsi
  HMODULE v3; // rbx
  _OSVERSIONINFOW VersionInformation; // [rsp+20h] [rbp-138h] BYREF

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
  if ( dword_180194654 )
    return 1;
  VersionInformation.dwOSVersionInfoSize = 276;
  if ( GetVersionExW(&VersionInformation) )
  {
    if ( VersionInformation.dwPlatformId - 1 > 1 )
    {
LABEL_20:
      SetLastError(0x32u);
      return 0;
    }
    ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-memory-l1-1-0.dll");
    if ( !ModuleHandleW )
      return 0;
    v2 = GetModuleHandleW(L"api-ms-win-core-libraryloader-l1-1-0.dll");
    if ( !v2 )
      return 0;
    if ( VersionInformation.dwPlatformId != 2 )
    {
      v3 = 0;
      goto LABEL_11;
    }
    v3 = GetModuleHandleW(L"ntdll.dll");
    if ( v3 )
    {
LABEL_11:
      qword_180194668 = (__int64)GetProcAddress(ModuleHandleW, "SetSystemFileCacheSize");
      if ( !qword_180194668 && GetLastError() != 127 )
        return 0;
      if ( !v3 )
      {
        qword_180194678 = (__int64)Win9xCheckDllSynchronization;
        goto LABEL_19;
      }
      qword_180194670 = (__int64)GetProcAddress(v3, "NtSetSystemInformation");
      if ( qword_180194670 )
      {
        qword_180194678 = (__int64)GetProcAddress(v2, "PrivIsDllSynchronizationHeld");
        if ( !qword_180194678 && GetLastError() != 127 )
          return 0;
LABEL_19:
        dword_180194658 = VersionInformation.dwPlatformId;
        dword_18019465C = VersionInformation.dwMajorVersion;
        dword_180194660 = VersionInformation.dwMinorVersion;
        _InterlockedExchange(&dword_180194654, 1);
        return 1;
      }
      goto LABEL_20;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18013d108  mov     [rsp+arg_0], rbx
0x18013d10d  mov     [rsp+arg_8], rsi
0x18013d112  push    rdi
0x18013d113  sub     rsp, 150h
0x18013d11a  mov     rax, cs:__security_cookie
0x18013d121  xor     rax, rsp
0x18013d124  mov     [rsp+158h+var_18], rax
0x18013d12c  xor     edx, edx; Val
0x18013d12e  lea     rcx, [rsp+158h+VersionInformation.dwMajorVersion]; void *
0x18013d133  mov     r8d, 110h; Size
0x18013d139  call    memset_0
0x18013d13e  cmp     cs:dword_180194654, 0
0x18013d145  jz      short loc_18013D151
0x18013d147  mov     eax, 1
0x18013d14c  jmp     loc_18013D28F
0x18013d151  lea     rcx, [rsp+158h+VersionInformation]; lpVersionInformation
0x18013d156  mov     [rsp+158h+VersionInformation.dwOSVersionInfoSize], 114h
0x18013d15e  call    cs:__imp_GetVersionExW
0x18013d164  test    eax, eax
0x18013d166  jz      loc_18013D28D
0x18013d16c  mov     eax, [rsp+158h+VersionInformation.dwPlatformId]
0x18013d170  dec     eax
0x18013d172  cmp     eax, 1
0x18013d175  ja      loc_18013D282
0x18013d17b  lea     rcx, aApiMsWinCoreMe; "api-ms-win-core-memory-l1-1-0.dll"
0x18013d182  call    cs:__imp_GetModuleHandleW
0x18013d188  mov     rdi, rax
0x18013d18b  test    rax, rax
0x18013d18e  jz      loc_18013D28D
0x18013d194  lea     rcx, aApiMsWinCoreLi; "api-ms-win-core-libraryloader-l1-1-0.dl"...
0x18013d19b  call    cs:__imp_GetModuleHandleW
0x18013d1a1  mov     rsi, rax
0x18013d1a4  test    rax, rax
0x18013d1a7  jz      loc_18013D28D
0x18013d1ad  cmp     [rsp+158h+VersionInformation.dwPlatformId], 2
0x18013d1b2  jnz     short loc_18013D1CF
0x18013d1b4  lea     rcx, aNtdllDll; "ntdll.dll"
0x18013d1bb  call    cs:__imp_GetModuleHandleW
0x18013d1c1  mov     rbx, rax
0x18013d1c4  test    rax, rax
0x18013d1c7  jz      loc_18013D28D
0x18013d1cd  jmp     short loc_18013D1D1
0x18013d1cf  xor     ebx, ebx
0x18013d1d1  lea     rdx, ProcName; "SetSystemFileCacheSize"
0x18013d1d8  mov     rcx, rdi; hModule
0x18013d1db  call    cs:__imp_GetProcAddress
0x18013d1e1  mov     cs:qword_180194668, rax
0x18013d1e8  test    rax, rax
0x18013d1eb  jnz     short loc_18013D1FC
0x18013d1ed  call    cs:__imp_GetLastError
0x18013d1f3  cmp     eax, 7Fh
0x18013d1f6  jnz     loc_18013D28D
0x18013d1fc  test    rbx, rbx
0x18013d1ff  jz      short loc_18013D246
0x18013d201  lea     rdx, aNtsetsysteminf; "NtSetSystemInformation"
0x18013d208  mov     rcx, rbx; hModule
0x18013d20b  call    cs:__imp_GetProcAddress
0x18013d211  mov     cs:qword_180194670, rax
0x18013d218  test    rax, rax
0x18013d21b  jz      short loc_18013D282
0x18013d21d  lea     rdx, aPrivisdllsynch; "PrivIsDllSynchronizationHeld"
0x18013d224  mov     rcx, rsi; hModule
0x18013d227  call    cs:__imp_GetProcAddress
0x18013d22d  mov     cs:qword_180194678, rax
0x18013d234  test    rax, rax
0x18013d237  jnz     short loc_18013D254
0x18013d239  call    cs:__imp_GetLastError
0x18013d23f  cmp     eax, 7Fh
0x18013d242  jz      short loc_18013D254
0x18013d244  jmp     short loc_18013D28D
0x18013d246  lea     rax, Win9xCheckDllSynchronization
0x18013d24d  mov     cs:qword_180194678, rax
0x18013d254  mov     eax, [rsp+158h+VersionInformation.dwPlatformId]
0x18013d258  mov     cs:dword_180194658, eax
0x18013d25e  mov     eax, [rsp+158h+VersionInformation.dwMajorVersion]
0x18013d262  mov     cs:dword_18019465C, eax
0x18013d268  mov     eax, [rsp+158h+VersionInformation.dwMinorVersion]
0x18013d26c  mov     cs:dword_180194660, eax
0x18013d272  mov     eax, 1
0x18013d277  xchg    eax, cs:dword_180194654
0x18013d27d  jmp     loc_18013D147
0x18013d282  mov     ecx, 32h ; '2'; dwErrCode
0x18013d287  call    cs:__imp_SetLastError
0x18013d28d  xor     eax, eax
0x18013d28f  mov     rcx, [rsp+158h+var_18]
0x18013d297  xor     rcx, rsp; StackCookie
0x18013d29a  call    __security_check_cookie
0x18013d29f  lea     r11, [rsp+158h+var_8]
0x18013d2a7  mov     rbx, [r11+10h]
0x18013d2ab  mov     rsi, [r11+18h]
0x18013d2af  mov     rsp, r11
0x18013d2b2  pop     rdi
0x18013d2b3  retn
```
