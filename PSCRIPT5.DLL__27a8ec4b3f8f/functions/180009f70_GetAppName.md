# GetAppName

- ea: `0x180009f70`
- end: `0x18000a261`
- name: `GetAppName`
- size: `753`
- prototype: `_BOOL8 __fastcall(STRSAFE_LPWSTR pszDest)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000a268`

## callees

- `0x180001f20`
- `0x180002938`
- `0x1800055fc`
- `0x180009f70`
- `0x1800352ac`
- `0x18005f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a07c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a07c`
- `api-ms-win-crt-private-l1-1-0!_o__wmakepath_s` at `0x18000a057`
- `api-ms-win-crt-private-l1-1-0!_o__wmakepath_s` at `0x18000a1c8`
- `api-ms-win-crt-private-l1-1-0!_o__wmakepath_s` at `0x18000a057`
- `api-ms-win-crt-private-l1-1-0!_o__wmakepath_s` at `0x18000a1c8`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18000a021`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18000a196`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18000a021`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18000a196`
- `KERNEL32!CloseHandle` at `0x18000a1f9`
- `KERNEL32!CloseHandle` at `0x18000a1f9`
- `KERNEL32!OpenProcess` at `0x18000a0fa`
- `KERNEL32!OpenProcess` at `0x18000a0fa`
- `KERNEL32!FreeLibrary` at `0x18000a1e4`
- `KERNEL32!FreeLibrary` at `0x18000a22e`
- `KERNEL32!FreeLibrary` at `0x18000a1e4`
- `KERNEL32!FreeLibrary` at `0x18000a22e`
- `KERNEL32!GetProcAddress` at `0x18000a0b7`
- `KERNEL32!GetProcAddress` at `0x18000a13f`
- `KERNEL32!GetProcAddress` at `0x18000a0b7`
- `KERNEL32!GetProcAddress` at `0x18000a13f`
- `KERNEL32!GetModuleFileNameW` at `0x180009fd9`
- `KERNEL32!GetModuleFileNameW` at `0x180009fd9`

## string_xrefs

- `0x18000a11c`: `psapi.dll`

## pseudocode

```c
_BOOL8 __fastcall GetAppName(STRSAFE_LPWSTR pszDest)
{
  BOOL v2; // ebx
  FARPROC ProcAddress; // rax
  HANDLE v4; // r15
  HMODULE v5; // r14
  FARPROC v6; // rax
  HMODULE hModule; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwProcessId[2]; // [rsp+58h] [rbp-A8h] BYREF
  HMODULE hLibModule; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Ext[264]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t Filename[264]; // [rsp+280h] [rbp+180h] BYREF

  hModule = 0;
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
    if ( (int)LoadLibraryFromSystemDirectory(L"winspool.drv", &hModule) < 0 )
      goto LABEL_18;
    ProcAddress = GetProcAddress(hModule, "GetPrintExecutionData");
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
    if ( (int)LoadLibraryFromSystemDirectory(L"psapi.dll", &hLibModule) >= 0 )
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
        v2 = 1;
    }
    if ( hModule )
      FreeLibrary(hModule);
  }
  return v2;
}

```

## disassembly

```asm
0x180009f70  push    rbp
0x180009f72  push    rbx
0x180009f73  push    rdi
0x180009f74  push    r13
0x180009f76  push    r14
0x180009f78  push    r15
0x180009f7a  lea     rbp, [rsp-3A8h]
0x180009f82  sub     rsp, 4A8h
0x180009f89  mov     rax, cs:__security_cookie
0x180009f90  xor     rax, rsp
0x180009f93  mov     [rbp+3D0h+var_40], rax
0x180009f9a  mov     rdi, rcx
0x180009f9d  mov     [rsp+4D0h+hModule], 0
0x180009fa6  mov     ebx, 208h
0x180009fab  lea     rcx, [rbp+3D0h+var_250]; void *
0x180009fb2  mov     r8d, ebx; Size
0x180009fb5  xor     edx, edx; Val
0x180009fb7  call    memset_0
0x180009fbc  mov     r8d, ebx; Size
0x180009fbf  lea     rcx, [rsp+4D0h+var_460]; void *
0x180009fc4  xor     edx, edx; Val
0x180009fc6  call    memset_0
0x180009fcb  mov     r13d, 104h
0x180009fd1  mov     rdx, rdi; lpFilename
0x180009fd4  mov     r8d, r13d; nSize
0x180009fd7  xor     ecx, ecx; hModule
0x180009fd9  call    cs:__imp_GetModuleFileNameW
0x180009fe0  nop     dword ptr [rax+rax+00h]
0x180009fe5  test    eax, eax
0x180009fe7  jz      loc_18000A23E
0x180009fed  mov     [rsp+4D0h+ExtCount], r13; ExtCount
0x180009ff2  lea     rax, [rsp+4D0h+var_460]
0x180009ff7  mov     [rsp+4D0h+Ext], rax; Ext
0x180009ffc  xor     r9d, r9d; Dir
0x180009fff  lea     rax, [rbp+3D0h+var_250]
0x18000a006  mov     [rsp+4D0h+FilenameCount], r13; FilenameCount
0x18000a00b  mov     [rsp+4D0h+Filename], rax; Filename
0x18000a010  xor     r8d, r8d; DriveCount
0x18000a013  xor     edx, edx; Drive
0x18000a015  mov     [rsp+4D0h+DirCount], 0; DirCount
0x18000a01e  mov     rcx, rdi; FullPath
0x18000a021  call    cs:__imp__wsplitpath_s
0x18000a028  nop     dword ptr [rax+rax+00h]
0x18000a02d  test    eax, eax
0x18000a02f  jnz     loc_18000A23E
0x18000a035  lea     rax, [rsp+4D0h+var_460]
0x18000a03a  xor     r9d, r9d
0x18000a03d  mov     [rsp+4D0h+Filename], rax
0x18000a042  xor     r8d, r8d
0x18000a045  lea     rax, [rbp+3D0h+var_250]
0x18000a04c  mov     edx, r13d
0x18000a04f  mov     rcx, rdi
0x18000a052  mov     [rsp+4D0h+DirCount], rax
0x18000a057  call    cs:__imp__o__wmakepath_s
0x18000a05e  nop     dword ptr [rax+rax+00h]
0x18000a063  test    eax, eax
0x18000a065  jnz     loc_18000A23E
0x18000a06b  lea     r14d, [rax+1]
0x18000a06f  mov     rcx, rdi
0x18000a072  lea     rdx, aSplwow64Exe; "SplWow64.exe"
0x18000a079  mov     ebx, r14d
0x18000a07c  call    cs:__imp__o__wcsicmp
0x18000a083  nop     dword ptr [rax+rax+00h]
0x18000a088  test    eax, eax
0x18000a08a  jnz     loc_18000A23A
0x18000a090  lea     rdx, [rsp+4D0h+hModule]
0x18000a095  xor     ebx, ebx
0x18000a097  lea     rcx, aWinspoolDrv_0; "winspool.drv"
0x18000a09e  call    LoadLibraryFromSystemDirectory
0x18000a0a3  test    eax, eax
0x18000a0a5  js      loc_18000A209
0x18000a0ab  mov     rcx, [rsp+4D0h+hModule]; hModule
0x18000a0b0  lea     rdx, aGetprintexecut; "GetPrintExecutionData"
0x18000a0b7  call    cs:__imp_GetProcAddress
0x18000a0be  nop     dword ptr [rax+rax+00h]
0x18000a0c3  test    rax, rax
0x18000a0c6  jz      loc_18000A209
0x18000a0cc  lea     rcx, [rsp+4D0h+dwProcessId]
0x18000a0d1  mov     qword ptr [rsp+4D0h+dwProcessId], rbx
0x18000a0d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0db  test    eax, eax
0x18000a0dd  jz      loc_18000A209
0x18000a0e3  cmp     [rsp+4D0h+dwProcessId], 4
0x18000a0e8  jnz     loc_18000A209
0x18000a0ee  mov     r8d, [rsp+4D0h+dwProcessId+4]; dwProcessId
0x18000a0f3  xor     edx, edx; bInheritHandle
0x18000a0f5  mov     ecx, 1000h; dwDesiredAccess
0x18000a0fa  call    cs:__imp_OpenProcess
0x18000a101  nop     dword ptr [rax+rax+00h]
0x18000a106  mov     r15, rax
0x18000a109  test    rax, rax
0x18000a10c  jz      loc_18000A209
0x18000a112  lea     rdx, [rsp+4D0h+hLibModule]
0x18000a117  mov     [rsp+4D0h+hLibModule], rbx
0x18000a11c  lea     rcx, aPsapiDll; "psapi.dll"
0x18000a123  call    LoadLibraryFromSystemDirectory
0x18000a128  test    eax, eax
0x18000a12a  js      loc_18000A1F6
0x18000a130  mov     r14, [rsp+4D0h+hLibModule]
0x18000a135  lea     rdx, aGetprocessimag; "GetProcessImageFileNameW"
0x18000a13c  mov     rcx, r14; hModule
0x18000a13f  call    cs:__imp_GetProcAddress
0x18000a146  nop     dword ptr [rax+rax+00h]
0x18000a14b  test    rax, rax
0x18000a14e  jz      loc_18000A1DC
0x18000a154  mov     r8d, r13d
0x18000a157  mov     rdx, rdi
0x18000a15a  mov     rcx, r15
0x18000a15d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a162  test    eax, eax
0x18000a164  jz      short loc_18000A1DC
0x18000a166  mov     [rsp+4D0h+ExtCount], r13; ExtCount
0x18000a16b  lea     rax, [rsp+4D0h+var_460]
0x18000a170  mov     [rsp+4D0h+Ext], rax; Ext
0x18000a175  xor     r9d, r9d; Dir
0x18000a178  lea     rax, [rbp+3D0h+var_250]
0x18000a17f  mov     [rsp+4D0h+FilenameCount], r13; FilenameCount
0x18000a184  mov     [rsp+4D0h+Filename], rax; Filename
0x18000a189  xor     r8d, r8d; DriveCount
0x18000a18c  xor     edx, edx; Drive
0x18000a18e  mov     [rsp+4D0h+DirCount], rbx; DirCount
0x18000a193  mov     rcx, rdi; FullPath
0x18000a196  call    cs:__imp__wsplitpath_s
0x18000a19d  nop     dword ptr [rax+rax+00h]
0x18000a1a2  test    eax, eax
0x18000a1a4  jnz     short loc_18000A1DC
0x18000a1a6  lea     rax, [rsp+4D0h+var_460]
0x18000a1ab  xor     r9d, r9d
0x18000a1ae  mov     [rsp+4D0h+Filename], rax
0x18000a1b3  xor     r8d, r8d
0x18000a1b6  lea     rax, [rbp+3D0h+var_250]
0x18000a1bd  mov     edx, r13d
0x18000a1c0  mov     rcx, rdi
0x18000a1c3  mov     [rsp+4D0h+DirCount], rax
0x18000a1c8  call    cs:__imp__o__wmakepath_s
0x18000a1cf  nop     dword ptr [rax+rax+00h]
0x18000a1d4  test    eax, eax
0x18000a1d6  lea     eax, [rbx+1]
0x18000a1d9  cmovz   ebx, eax
0x18000a1dc  test    r14, r14
0x18000a1df  jz      short loc_18000A1F0
0x18000a1e1  mov     rcx, r14; hLibModule
0x18000a1e4  call    cs:__imp_FreeLibrary
0x18000a1eb  nop     dword ptr [rax+rax+00h]
0x18000a1f0  mov     r14d, 1
0x18000a1f6  mov     rcx, r15; hObject
0x18000a1f9  call    cs:__imp_CloseHandle
0x18000a200  nop     dword ptr [rax+rax+00h]
0x18000a205  test    ebx, ebx
0x18000a207  jnz     short loc_18000A221
0x18000a209  lea     r8, aSplwow64Exe; "SplWow64.exe"
0x18000a210  mov     rdx, r13; cchDest
0x18000a213  mov     rcx, rdi; pszDest
0x18000a216  call    StringCchCopyW
0x18000a21b  test    eax, eax
0x18000a21d  cmovns  ebx, r14d
0x18000a221  cmp     [rsp+4D0h+hModule], 0
0x18000a227  jz      short loc_18000A23A
0x18000a229  mov     rcx, [rsp+4D0h+hModule]; hLibModule
0x18000a22e  call    cs:__imp_FreeLibrary
0x18000a235  nop     dword ptr [rax+rax+00h]
0x18000a23a  mov     eax, ebx
0x18000a23c  jmp     short loc_18000A240
0x18000a23e  xor     eax, eax
0x18000a240  mov     rcx, [rbp+3D0h+var_40]
0x18000a247  xor     rcx, rsp; StackCookie
0x18000a24a  call    __security_check_cookie
0x18000a24f  add     rsp, 4A8h
0x18000a256  pop     r15
0x18000a258  pop     r14
0x18000a25a  pop     r13
0x18000a25c  pop     rdi
0x18000a25d  pop     rbx
0x18000a25e  pop     rbp
0x18000a25f  retn
```
