# GetAppName

- ea: `0x180009c38`
- end: `0x180009edc`
- name: `GetAppName`
- size: `676`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180009ee4`

## callees

- `0x180001ee0`
- `0x1800028d8`
- `0x180005568`
- `0x180009c38`
- `0x180033bc8`
- `0x18005d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009d32`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009d32`
- `api-ms-win-crt-private-l1-1-0!_o__wmakepath_s` at `0x180009d13`
- `api-ms-win-crt-private-l1-1-0!_o__wmakepath_s` at `0x180009e5c`
- `api-ms-win-crt-private-l1-1-0!_o__wmakepath_s` at `0x180009d13`
- `api-ms-win-crt-private-l1-1-0!_o__wmakepath_s` at `0x180009e5c`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180009ce3`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180009e30`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180009ce3`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180009e30`
- `KERNEL32!CloseHandle` at `0x180009e81`
- `KERNEL32!CloseHandle` at `0x180009e81`
- `KERNEL32!OpenProcess` at `0x180009da4`
- `KERNEL32!OpenProcess` at `0x180009da4`
- `KERNEL32!FreeLibrary` at `0x180009e72`
- `KERNEL32!FreeLibrary` at `0x180009eb0`
- `KERNEL32!FreeLibrary` at `0x180009e72`
- `KERNEL32!FreeLibrary` at `0x180009eb0`
- `KERNEL32!GetProcAddress` at `0x180009d67`
- `KERNEL32!GetProcAddress` at `0x180009de3`
- `KERNEL32!GetProcAddress` at `0x180009d67`
- `KERNEL32!GetProcAddress` at `0x180009de3`
- `KERNEL32!GetModuleFileNameW` at `0x180009ca1`
- `KERNEL32!GetModuleFileNameW` at `0x180009ca1`

## string_xrefs

- `0x180009dc0`: `psapi.dll`

## pseudocode

```c
_BOOL8 __fastcall GetAppName(STRSAFE_LPWSTR pszDest)
{
  BOOL v2; // ebx
  FARPROC ProcAddress; // rax
  HANDLE v4; // r15
  HMODULE v5; // r14
  FARPROC v6; // rax
  DWORD dwProcessId[2]; // [rsp+58h] [rbp-A8h] BYREF
  HMODULE hLibModule; // [rsp+60h] [rbp-A0h]
  wchar_t Ext[264]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t Filename[264]; // [rsp+280h] [rbp+180h] BYREF

  memset_0(Filename, 0, 0x208u);
  memset_0(Ext, 0, 0x208u);
  if ( !GetModuleFileNameW(0, pszDest, 0x104u)
    || _wsplitpath_s(pszDest, 0, 0, 0, 0, Filename, 0x104u, Ext, 0x104u)
    || (unsigned int)_o__wmakepath_s(pszDest, 260, 0, 0, Filename, Ext) )
  {
    return 0;
  }
  v2 = 1;
  if ( !(unsigned int)_o__wcsicmp(pszDest, L"SplWow64.exe") )
  {
    v2 = 0;
    if ( (int)LoadLibraryFromSystemDirectory(L"winspool.drv") < 0 )
      goto LABEL_18;
    ProcAddress = GetProcAddress(0, "GetPrintExecutionData");
    if ( !ProcAddress )
      goto LABEL_18;
    *(_QWORD *)dwProcessId = 0;
    if ( !((unsigned int (__fastcall *)(DWORD *))ProcAddress)(dwProcessId) )
      goto LABEL_18;
    if ( dwProcessId[0] != 4 )
      goto LABEL_18;
    v4 = OpenProcess(0x1000u, 0, dwProcessId[1]);
    if ( !v4 )
      goto LABEL_18;
    hLibModule = 0;
    if ( (int)LoadLibraryFromSystemDirectory(L"psapi.dll") >= 0 )
    {
      v5 = hLibModule;
      v6 = GetProcAddress(hLibModule, "GetProcessImageFileNameW");
      if ( v6
        && ((unsigned int (__fastcall *)(HANDLE, STRSAFE_LPWSTR, __int64))v6)(v4, pszDest, 260)
        && !_wsplitpath_s(pszDest, 0, 0, 0, 0, Filename, 0x104u, Ext, 0x104u) )
      {
        v2 = _o__wmakepath_s(pszDest, 260, 0, 0, Filename, Ext) == 0;
      }
      if ( v5 )
        FreeLibrary(v5);
    }
    CloseHandle(v4);
    if ( !v2 )
    {
LABEL_18:
      if ( StringCchCopyW(pszDest, 0x104u, L"SplWow64.exe") >= 0 )
        return 1;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180009c38  push    rbp
0x180009c3a  push    rbx
0x180009c3b  push    rdi
0x180009c3c  push    r13
0x180009c3e  push    r14
0x180009c40  push    r15
0x180009c42  lea     rbp, [rsp-3A8h]
0x180009c4a  sub     rsp, 4A8h
0x180009c51  mov     rax, cs:__security_cookie
0x180009c58  xor     rax, rsp
0x180009c5b  mov     [rbp+3D0h+var_40], rax
0x180009c62  mov     rdi, rcx
0x180009c65  mov     [rsp+4D0h+hModule], 0
0x180009c6e  mov     ebx, 208h
0x180009c73  lea     rcx, [rbp+3D0h+var_250]; void *
0x180009c7a  mov     r8d, ebx; Size
0x180009c7d  xor     edx, edx; Val
0x180009c7f  call    memset_0
0x180009c84  mov     r8d, ebx; Size
0x180009c87  lea     rcx, [rsp+4D0h+var_460]; void *
0x180009c8c  xor     edx, edx; Val
0x180009c8e  call    memset_0
0x180009c93  mov     r13d, 104h
0x180009c99  mov     rdx, rdi; lpFilename
0x180009c9c  mov     r8d, r13d; nSize
0x180009c9f  xor     ecx, ecx; hModule
0x180009ca1  call    cs:__imp_GetModuleFileNameW
0x180009ca7  test    eax, eax
0x180009ca9  jz      loc_180009EBA
0x180009caf  mov     [rsp+4D0h+ExtCount], r13; ExtCount
0x180009cb4  lea     rax, [rsp+4D0h+var_460]
0x180009cb9  mov     [rsp+4D0h+Ext], rax; Ext
0x180009cbe  xor     r9d, r9d; Dir
0x180009cc1  lea     rax, [rbp+3D0h+var_250]
0x180009cc8  mov     [rsp+4D0h+FilenameCount], r13; FilenameCount
0x180009ccd  mov     [rsp+4D0h+Filename], rax; Filename
0x180009cd2  xor     r8d, r8d; DriveCount
0x180009cd5  xor     edx, edx; Drive
0x180009cd7  mov     [rsp+4D0h+DirCount], 0; DirCount
0x180009ce0  mov     rcx, rdi; FullPath
0x180009ce3  call    cs:__imp__wsplitpath_s
0x180009ce9  test    eax, eax
0x180009ceb  jnz     loc_180009EBA
0x180009cf1  lea     rax, [rsp+4D0h+var_460]
0x180009cf6  xor     r9d, r9d
0x180009cf9  mov     [rsp+4D0h+Filename], rax
0x180009cfe  xor     r8d, r8d
0x180009d01  lea     rax, [rbp+3D0h+var_250]
0x180009d08  mov     edx, r13d
0x180009d0b  mov     rcx, rdi
0x180009d0e  mov     [rsp+4D0h+DirCount], rax
0x180009d13  call    cs:__imp__o__wmakepath_s
0x180009d19  test    eax, eax
0x180009d1b  jnz     loc_180009EBA
0x180009d21  lea     r14d, [rax+1]
0x180009d25  mov     rcx, rdi
0x180009d28  lea     rdx, aSplwow64Exe; "SplWow64.exe"
0x180009d2f  mov     ebx, r14d
0x180009d32  call    cs:__imp__o__wcsicmp
0x180009d38  test    eax, eax
0x180009d3a  jnz     loc_180009EB6
0x180009d40  lea     rdx, [rsp+4D0h+hModule]
0x180009d45  xor     ebx, ebx
0x180009d47  lea     rcx, aWinspoolDrv_0; "winspool.drv"
0x180009d4e  call    LoadLibraryFromSystemDirectory
0x180009d53  test    eax, eax
0x180009d55  js      loc_180009E8B
0x180009d5b  mov     rcx, [rsp+4D0h+hModule]; hModule
0x180009d60  lea     rdx, aGetprintexecut; "GetPrintExecutionData"
0x180009d67  call    cs:__imp_GetProcAddress
0x180009d6d  test    rax, rax
0x180009d70  jz      loc_180009E8B
0x180009d76  lea     rcx, [rsp+4D0h+dwProcessId]
0x180009d7b  mov     qword ptr [rsp+4D0h+dwProcessId], rbx
0x180009d80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d85  test    eax, eax
0x180009d87  jz      loc_180009E8B
0x180009d8d  cmp     [rsp+4D0h+dwProcessId], 4
0x180009d92  jnz     loc_180009E8B
0x180009d98  mov     r8d, [rsp+4D0h+dwProcessId+4]; dwProcessId
0x180009d9d  xor     edx, edx; bInheritHandle
0x180009d9f  mov     ecx, 1000h; dwDesiredAccess
0x180009da4  call    cs:__imp_OpenProcess
0x180009daa  mov     r15, rax
0x180009dad  test    rax, rax
0x180009db0  jz      loc_180009E8B
0x180009db6  lea     rdx, [rsp+4D0h+hLibModule]
0x180009dbb  mov     [rsp+4D0h+hLibModule], rbx
0x180009dc0  lea     rcx, aPsapiDll; "psapi.dll"
0x180009dc7  call    LoadLibraryFromSystemDirectory
0x180009dcc  test    eax, eax
0x180009dce  js      loc_180009E7E
0x180009dd4  mov     r14, [rsp+4D0h+hLibModule]
0x180009dd9  lea     rdx, aGetprocessimag; "GetProcessImageFileNameW"
0x180009de0  mov     rcx, r14; hModule
0x180009de3  call    cs:__imp_GetProcAddress
0x180009de9  test    rax, rax
0x180009dec  jz      short loc_180009E6A
0x180009dee  mov     r8d, r13d
0x180009df1  mov     rdx, rdi
0x180009df4  mov     rcx, r15
0x180009df7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dfc  test    eax, eax
0x180009dfe  jz      short loc_180009E6A
0x180009e00  mov     [rsp+4D0h+ExtCount], r13; ExtCount
0x180009e05  lea     rax, [rsp+4D0h+var_460]
0x180009e0a  mov     [rsp+4D0h+Ext], rax; Ext
0x180009e0f  xor     r9d, r9d; Dir
0x180009e12  lea     rax, [rbp+3D0h+var_250]
0x180009e19  mov     [rsp+4D0h+FilenameCount], r13; FilenameCount
0x180009e1e  mov     [rsp+4D0h+Filename], rax; Filename
0x180009e23  xor     r8d, r8d; DriveCount
0x180009e26  xor     edx, edx; Drive
0x180009e28  mov     [rsp+4D0h+DirCount], rbx; DirCount
0x180009e2d  mov     rcx, rdi; FullPath
0x180009e30  call    cs:__imp__wsplitpath_s
0x180009e36  test    eax, eax
0x180009e38  jnz     short loc_180009E6A
0x180009e3a  lea     rax, [rsp+4D0h+var_460]
0x180009e3f  xor     r9d, r9d
0x180009e42  mov     [rsp+4D0h+Filename], rax
0x180009e47  xor     r8d, r8d
0x180009e4a  lea     rax, [rbp+3D0h+var_250]
0x180009e51  mov     edx, r13d
0x180009e54  mov     rcx, rdi
0x180009e57  mov     [rsp+4D0h+DirCount], rax
0x180009e5c  call    cs:__imp__o__wmakepath_s
0x180009e62  test    eax, eax
0x180009e64  lea     eax, [rbx+1]
0x180009e67  cmovz   ebx, eax
0x180009e6a  test    r14, r14
0x180009e6d  jz      short loc_180009E78
0x180009e6f  mov     rcx, r14; hLibModule
0x180009e72  call    cs:__imp_FreeLibrary
0x180009e78  mov     r14d, 1
0x180009e7e  mov     rcx, r15; hObject
0x180009e81  call    cs:__imp_CloseHandle
0x180009e87  test    ebx, ebx
0x180009e89  jnz     short loc_180009EA3
0x180009e8b  lea     r8, aSplwow64Exe; "SplWow64.exe"
0x180009e92  mov     rdx, r13; cchDest
0x180009e95  mov     rcx, rdi; pszDest
0x180009e98  call    StringCchCopyW
0x180009e9d  test    eax, eax
0x180009e9f  cmovns  ebx, r14d
0x180009ea3  cmp     [rsp+4D0h+hModule], 0
0x180009ea9  jz      short loc_180009EB6
0x180009eab  mov     rcx, [rsp+4D0h+hModule]; hLibModule
0x180009eb0  call    cs:__imp_FreeLibrary
0x180009eb6  mov     eax, ebx
0x180009eb8  jmp     short loc_180009EBC
0x180009eba  xor     eax, eax
0x180009ebc  mov     rcx, [rbp+3D0h+var_40]
0x180009ec3  xor     rcx, rsp; StackCookie
0x180009ec6  call    __security_check_cookie
0x180009ecb  add     rsp, 4A8h
0x180009ed2  pop     r15
0x180009ed4  pop     r14
0x180009ed6  pop     r13
0x180009ed8  pop     rdi
0x180009ed9  pop     rbx
0x180009eda  pop     rbp
0x180009edb  retn
```
