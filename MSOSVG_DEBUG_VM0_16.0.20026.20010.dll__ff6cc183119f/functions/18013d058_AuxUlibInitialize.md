# AuxUlibInitialize

- ea: `0x18013d058`
- end: `0x18013d204`
- name: `AuxUlibInitialize`
- size: `428`
- prototype: `BOOL __stdcall()`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18013c418`

## callees

- `0x18013d058`
- `0x18013d650`
- `0x18013e67c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18013d13d`
- `KERNEL32!GetLastError` at `0x18013d189`
- `KERNEL32!GetLastError` at `0x18013d13d`
- `KERNEL32!GetLastError` at `0x18013d189`
- `KERNEL32!SetLastError` at `0x18013d1d7`
- `KERNEL32!SetLastError` at `0x18013d1d7`
- `KERNEL32!GetModuleHandleW` at `0x18013d0d2`
- `KERNEL32!GetModuleHandleW` at `0x18013d0eb`
- `KERNEL32!GetModuleHandleW` at `0x18013d10b`
- `KERNEL32!GetModuleHandleW` at `0x18013d0d2`
- `KERNEL32!GetModuleHandleW` at `0x18013d0eb`
- `KERNEL32!GetModuleHandleW` at `0x18013d10b`
- `KERNEL32!GetVersionExW` at `0x18013d0ae`
- `KERNEL32!GetVersionExW` at `0x18013d0ae`
- `KERNEL32!GetProcAddress` at `0x18013d12b`
- `KERNEL32!GetProcAddress` at `0x18013d15b`
- `KERNEL32!GetProcAddress` at `0x18013d177`
- `KERNEL32!GetProcAddress` at `0x18013d12b`
- `KERNEL32!GetProcAddress` at `0x18013d15b`
- `KERNEL32!GetProcAddress` at `0x18013d177`

## string_xrefs

- `0x18013d0cb`: `api-ms-win-core-memory-l1-1-0.dll`
- `0x18013d0e4`: `api-ms-win-core-libraryloader-l1-1-0.dll`
- `0x18013d104`: `ntdll.dll`
- `0x18013d121`: `SetSystemFileCacheSize`
- `0x18013d16d`: `PrivIsDllSynchronizationHeld`

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
0x18013d058  mov     [rsp+arg_0], rbx
0x18013d05d  mov     [rsp+arg_8], rsi
0x18013d062  push    rdi
0x18013d063  sub     rsp, 150h
0x18013d06a  mov     rax, cs:__security_cookie
0x18013d071  xor     rax, rsp
0x18013d074  mov     [rsp+158h+var_18], rax
0x18013d07c  xor     edx, edx; Val
0x18013d07e  lea     rcx, [rsp+158h+VersionInformation.dwMajorVersion]; void *
0x18013d083  mov     r8d, 110h; Size
0x18013d089  call    memset_0
0x18013d08e  cmp     cs:dword_180194654, 0
0x18013d095  jz      short loc_18013D0A1
0x18013d097  mov     eax, 1
0x18013d09c  jmp     loc_18013D1DF
0x18013d0a1  lea     rcx, [rsp+158h+VersionInformation]; lpVersionInformation
0x18013d0a6  mov     [rsp+158h+VersionInformation.dwOSVersionInfoSize], 114h
0x18013d0ae  call    cs:__imp_GetVersionExW
0x18013d0b4  test    eax, eax
0x18013d0b6  jz      loc_18013D1DD
0x18013d0bc  mov     eax, [rsp+158h+VersionInformation.dwPlatformId]
0x18013d0c0  dec     eax
0x18013d0c2  cmp     eax, 1
0x18013d0c5  ja      loc_18013D1D2
0x18013d0cb  lea     rcx, aApiMsWinCoreMe; "api-ms-win-core-memory-l1-1-0.dll"
0x18013d0d2  call    cs:__imp_GetModuleHandleW
0x18013d0d8  mov     rdi, rax
0x18013d0db  test    rax, rax
0x18013d0de  jz      loc_18013D1DD
0x18013d0e4  lea     rcx, aApiMsWinCoreLi; "api-ms-win-core-libraryloader-l1-1-0.dl"...
0x18013d0eb  call    cs:__imp_GetModuleHandleW
0x18013d0f1  mov     rsi, rax
0x18013d0f4  test    rax, rax
0x18013d0f7  jz      loc_18013D1DD
0x18013d0fd  cmp     [rsp+158h+VersionInformation.dwPlatformId], 2
0x18013d102  jnz     short loc_18013D11F
0x18013d104  lea     rcx, aNtdllDll; "ntdll.dll"
0x18013d10b  call    cs:__imp_GetModuleHandleW
0x18013d111  mov     rbx, rax
0x18013d114  test    rax, rax
0x18013d117  jz      loc_18013D1DD
0x18013d11d  jmp     short loc_18013D121
0x18013d11f  xor     ebx, ebx
0x18013d121  lea     rdx, ProcName; "SetSystemFileCacheSize"
0x18013d128  mov     rcx, rdi; hModule
0x18013d12b  call    cs:__imp_GetProcAddress
0x18013d131  mov     cs:qword_180194668, rax
0x18013d138  test    rax, rax
0x18013d13b  jnz     short loc_18013D14C
0x18013d13d  call    cs:__imp_GetLastError
0x18013d143  cmp     eax, 7Fh
0x18013d146  jnz     loc_18013D1DD
0x18013d14c  test    rbx, rbx
0x18013d14f  jz      short loc_18013D196
0x18013d151  lea     rdx, aNtsetsysteminf; "NtSetSystemInformation"
0x18013d158  mov     rcx, rbx; hModule
0x18013d15b  call    cs:__imp_GetProcAddress
0x18013d161  mov     cs:qword_180194670, rax
0x18013d168  test    rax, rax
0x18013d16b  jz      short loc_18013D1D2
0x18013d16d  lea     rdx, aPrivisdllsynch; "PrivIsDllSynchronizationHeld"
0x18013d174  mov     rcx, rsi; hModule
0x18013d177  call    cs:__imp_GetProcAddress
0x18013d17d  mov     cs:qword_180194678, rax
0x18013d184  test    rax, rax
0x18013d187  jnz     short loc_18013D1A4
0x18013d189  call    cs:__imp_GetLastError
0x18013d18f  cmp     eax, 7Fh
0x18013d192  jz      short loc_18013D1A4
0x18013d194  jmp     short loc_18013D1DD
0x18013d196  lea     rax, Win9xCheckDllSynchronization
0x18013d19d  mov     cs:qword_180194678, rax
0x18013d1a4  mov     eax, [rsp+158h+VersionInformation.dwPlatformId]
0x18013d1a8  mov     cs:dword_180194658, eax
0x18013d1ae  mov     eax, [rsp+158h+VersionInformation.dwMajorVersion]
0x18013d1b2  mov     cs:dword_18019465C, eax
0x18013d1b8  mov     eax, [rsp+158h+VersionInformation.dwMinorVersion]
0x18013d1bc  mov     cs:dword_180194660, eax
0x18013d1c2  mov     eax, 1
0x18013d1c7  xchg    eax, cs:dword_180194654
0x18013d1cd  jmp     loc_18013D097
0x18013d1d2  mov     ecx, 32h ; '2'; dwErrCode
0x18013d1d7  call    cs:__imp_SetLastError
0x18013d1dd  xor     eax, eax
0x18013d1df  mov     rcx, [rsp+158h+var_18]
0x18013d1e7  xor     rcx, rsp; StackCookie
0x18013d1ea  call    __security_check_cookie
0x18013d1ef  lea     r11, [rsp+158h+var_8]
0x18013d1f7  mov     rbx, [r11+10h]
0x18013d1fb  mov     rsi, [r11+18h]
0x18013d1ff  mov     rsp, r11
0x18013d202  pop     rdi
0x18013d203  retn
```
