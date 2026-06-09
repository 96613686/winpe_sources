# DpspLaunchRunDLLUserHost

- ea: `0x180017040`
- end: `0x18001721f`
- name: `DpspLaunchRunDLLUserHost`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b484`

## callees

- `0x180008dd8`
- `0x180009090`
- `0x180009fb0`
- `0x18000a856`
- `0x180017040`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800171f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800171f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800171ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800171ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800171ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800171ca`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18001718a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18001718a`

## string_xrefs

- `0x1800170ee`: `clientcore\base\diagnosis\pdi\wdi\framework\dps\dpstask.cpp`
- `0x1800170b1`: `%systemroot%\system32\rundll32.exe`
- `0x1800170e7`: `DpspLaunchRunDLLUserHost`
- `0x1800170ff`: `"%systemroot%\system32\rundll32.exe" "%systemroot%\system32\wdi.dll",WdipLaunchRunDLLUserHost`

## pseudocode

```c
__int64 __fastcall DpspLaunchRunDLLUserHost(__int64 a1, __int64 a2)
{
  int v4; // eax
  signed int v5; // ebx
  int v6; // eax
  void *v7; // rcx
  signed int LastError; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+60h] [rbp-A0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ApplicationName[264]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR CommandLine[512]; // [rsp+300h] [rbp+200h] BYREF

  memset_0(CommandLine, 0, sizeof(CommandLine));
  memset_0(ApplicationName, 0, 0x208u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  v4 = WdipExpandVariables(ApplicationName, 0x104u, L"%systemroot%\\system32\\rundll32.exe");
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = WdipExpandVariables(
           CommandLine,
           0x200u,
           L"\"%systemroot%\\system32\\rundll32.exe\" \"%systemroot%\\system32\\wdi.dll\",WdipLaunchRunDLLUserHost");
    v5 = v6;
    if ( v6 < 0 )
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpstask.cpp",
        (int)L"DpspLaunchRunDLLUserHost",
        351,
        (int)L"Error = %d",
        v6);
      goto LABEL_9;
    }
    v7 = *(void **)(a1 + 800);
    StartupInfo.lpDesktop = *(LPWSTR *)(a1 + 784);
    if ( CreateProcessAsUserW(v7, ApplicationName, CommandLine, 0, 0, 0, 0x20u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      v5 = 0;
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 < 0 )
      {
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpstask.cpp",
          (int)L"DpspLaunchRunDLLUserHost",
          366,
          (int)L"Error = %d",
          v5);
        goto LABEL_9;
      }
    }
    *(_DWORD *)(a2 + 4) = ProcessInformation.dwProcessId;
    goto LABEL_9;
  }
  WdipTraceError(
    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpstask.cpp",
    (int)L"DpspLaunchRunDLLUserHost",
    343,
    (int)L"Error = %d",
    v4);
LABEL_9:
  if ( (unsigned __int64)ProcessInformation.hProcess - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(ProcessInformation.hProcess);
    ProcessInformation.hProcess = 0;
  }
  if ( (unsigned __int64)ProcessInformation.hThread - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(ProcessInformation.hThread);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180017040  mov     [rsp-8+arg_10], rbx
0x180017045  push    rbp
0x180017046  push    rsi
0x180017047  push    rdi
0x180017048  lea     rbp, [rsp-610h]
0x180017050  sub     rsp, 710h
0x180017057  mov     rax, cs:__security_cookie
0x18001705e  xor     rax, rsp
0x180017061  mov     [rbp+620h+var_20], rax
0x180017068  mov     rsi, rdx
0x18001706b  mov     rdi, rcx
0x18001706e  xor     edx, edx; Val
0x180017070  lea     rcx, [rbp+620h+CommandLine]; void *
0x180017077  mov     r8d, 400h; Size
0x18001707d  call    memset_0
0x180017082  xor     edx, edx; Val
0x180017084  lea     rcx, [rbp+620h+ApplicationName]; void *
0x180017088  mov     r8d, 208h; Size
0x18001708e  call    memset_0
0x180017093  xor     eax, eax
0x180017095  lea     rcx, [rbp+620h+StartupInfo+4]; void *
0x180017099  xorps   xmm0, xmm0
0x18001709c  mov     qword ptr [rsp+720h+ProcessInformation.dwProcessId], rax
0x1800170a1  xor     edx, edx; Val
0x1800170a3  movups  xmmword ptr [rsp+720h+ProcessInformation.hProcess], xmm0
0x1800170a8  lea     r8d, [rax+64h]; Size
0x1800170ac  call    memset_0
0x1800170b1  lea     r8, aSystemrootSyst_2; "%systemroot%\\system32\\rundll32.exe"
0x1800170b8  mov     [rbp+620h+StartupInfo.cb], 68h ; 'h'
0x1800170bf  mov     edx, 104h; unsigned __int64
0x1800170c4  lea     rcx, [rbp+620h+ApplicationName]; unsigned __int16 *
0x1800170c8  call    WdipExpandVariables
0x1800170cd  mov     ebx, eax
0x1800170cf  test    eax, eax
0x1800170d1  jns     short loc_1800170FF
0x1800170d3  movzx   ecx, ax
0x1800170d6  mov     r8d, 157h; int
0x1800170dc  mov     dword ptr [rsp+720h+lpThreadAttributes], ecx; Args
0x1800170e0  lea     r9, aErrorD; "Error = %d"
0x1800170e7  lea     rdx, aDpsplaunchrund; "DpspLaunchRunDLLUserHost"
0x1800170ee  lea     rcx, aClientcoreBase_4; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800170f5  call    WdipTraceError
0x1800170fa  jmp     loc_18001719D
0x1800170ff  lea     r8, aSystemrootSyst_0; "\"%systemroot%\\system32\\rundll32.exe"...
0x180017106  mov     edx, 200h; unsigned __int64
0x18001710b  lea     rcx, [rbp+620h+CommandLine]; unsigned __int16 *
0x180017112  call    WdipExpandVariables
0x180017117  mov     ebx, eax
0x180017119  test    eax, eax
0x18001711b  jns     short loc_18001712C
0x18001711d  movzx   eax, ax
0x180017120  mov     r8d, 15Fh
0x180017126  mov     dword ptr [rsp+720h+lpThreadAttributes], eax
0x18001712a  jmp     short loc_1800170E0
0x18001712c  mov     rax, [rdi+310h]
0x180017133  lea     r8, [rbp+620h+CommandLine]; lpCommandLine
0x18001713a  mov     rcx, [rdi+320h]; hToken
0x180017141  lea     rdx, [rbp+620h+ApplicationName]; lpApplicationName
0x180017145  mov     [rbp+620h+StartupInfo.lpDesktop], rax
0x180017149  xor     r9d, r9d; lpProcessAttributes
0x18001714c  lea     rax, [rsp+720h+ProcessInformation]
0x180017151  mov     [rsp+720h+lpProcessInformation], rax; lpProcessInformation
0x180017156  lea     rax, [rbp+620h+StartupInfo]
0x18001715a  mov     [rsp+720h+lpStartupInfo], rax; lpStartupInfo
0x18001715f  mov     [rsp+720h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180017168  mov     [rsp+720h+lpEnvironment], 0; lpEnvironment
0x180017171  mov     [rsp+720h+dwCreationFlags], 20h ; ' '; dwCreationFlags
0x180017179  mov     [rsp+720h+bInheritHandles], 0; bInheritHandles
0x180017181  mov     [rsp+720h+lpThreadAttributes], 0; lpThreadAttributes
0x18001718a  call    cs:__imp_CreateProcessAsUserW
0x180017190  test    eax, eax
0x180017192  jz      short loc_1800171F4
0x180017194  xor     ebx, ebx
0x180017196  mov     eax, [rsp+720h+ProcessInformation.dwProcessId]
0x18001719a  mov     [rsi+4], eax
0x18001719d  mov     rcx, [rsp+720h+ProcessInformation.hProcess]; hObject
0x1800171a2  lea     rax, [rcx-1]
0x1800171a6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800171aa  ja      short loc_1800171BB
0x1800171ac  call    cs:__imp_CloseHandle
0x1800171b2  mov     [rsp+720h+ProcessInformation.hProcess], 0
0x1800171bb  mov     rcx, [rsp+720h+ProcessInformation.hThread]; hObject
0x1800171c0  lea     rax, [rcx-1]
0x1800171c4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800171c8  ja      short loc_1800171D0
0x1800171ca  call    cs:__imp_CloseHandle
0x1800171d0  mov     eax, ebx
0x1800171d2  mov     rcx, [rbp+620h+var_20]
0x1800171d9  xor     rcx, rsp; StackCookie
0x1800171dc  call    __security_check_cookie
0x1800171e1  mov     rbx, [rsp+720h+arg_10]
0x1800171e9  add     rsp, 710h
0x1800171f0  pop     rdi
0x1800171f1  pop     rsi
0x1800171f2  pop     rbp
0x1800171f3  retn
0x1800171f4  call    cs:__imp_GetLastError
0x1800171fa  mov     ebx, eax
0x1800171fc  test    eax, eax
0x1800171fe  jle     short loc_180017209
0x180017200  movzx   ebx, ax
0x180017203  or      ebx, 80070000h
0x180017209  test    ebx, ebx
0x18001720b  jns     short loc_180017196
0x18001720d  movzx   eax, bx
0x180017210  mov     r8d, 16Eh
0x180017216  mov     dword ptr [rsp+720h+lpThreadAttributes], eax
0x18001721a  jmp     loc_1800170E0
```
