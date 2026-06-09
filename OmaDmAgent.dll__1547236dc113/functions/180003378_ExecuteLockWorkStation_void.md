# ExecuteLockWorkStation(void)

- ea: `0x180003378`
- end: `0x1800035e6`
- name: `?ExecuteLockWorkStation@@YAJXZ`
- size: `622`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004950`

## callees

- `0x180001284`
- `0x1800012b8`
- `0x180003378`
- `0x1800059a8`
- `0x1800059ec`
- `0x18001f3da`
- `0x18001f420`

## import_xrefs

- `ADVAPI32!CreateProcessAsUserW` at `0x180003561`
- `ADVAPI32!CreateProcessAsUserW` at `0x180003561`
- `KERNEL32!CloseHandle` at `0x180003591`
- `KERNEL32!CloseHandle` at `0x1800035a2`
- `KERNEL32!CloseHandle` at `0x1800035b3`
- `KERNEL32!CloseHandle` at `0x180003591`
- `KERNEL32!CloseHandle` at `0x1800035a2`
- `KERNEL32!CloseHandle` at `0x1800035b3`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x18000346f`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x18000346f`
- `KERNEL32!GetLastError` at `0x1800033ed`
- `KERNEL32!GetLastError` at `0x1800034ee`
- `KERNEL32!GetLastError` at `0x180003571`
- `KERNEL32!GetLastError` at `0x1800033ed`
- `KERNEL32!GetLastError` at `0x1800034ee`
- `KERNEL32!GetLastError` at `0x180003571`
- `KERNEL32!GetSystemDirectoryW` at `0x1800033dd`
- `KERNEL32!GetSystemDirectoryW` at `0x1800033dd`
- `WTSAPI32!WTSQueryUserToken` at `0x1800034d9`
- `WTSAPI32!WTSQueryUserToken` at `0x1800034d9`

## string_xrefs

- `0x18000341f`: `rundll32.exe`
- `0x18000344f`: `rundll32.exe user32.dll,LockWorkStation`

## pseudocode

```c
__int64 ExecuteLockWorkStation(void)
{
  UINT SystemDirectoryW; // eax
  signed int v1; // eax
  signed int v2; // ebx
  DWORD active; // eax
  __int64 v4; // rcx
  __int64 v5; // r8
  signed int LastError; // eax
  signed int v7; // eax
  HANDLE phToken; // [rsp+60h] [rbp-A0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-98h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v12[32]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR Buffer[264]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR CommandLine[264]; // [rsp+320h] [rbp+220h] BYREF
  WCHAR ApplicationName[264]; // [rsp+530h] [rbp+430h] BYREF

  phToken = 0;
  *(_QWORD *)&StartupInfo.cb = 104;
  memset_0(&StartupInfo.lpReserved, 0, 0x60u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  if ( SystemDirectoryW )
  {
    if ( SystemDirectoryW <= 0x104 )
    {
      v2 = StringCchPrintfW(ApplicationName, 0x104u, L"%s\\%s", Buffer, L"rundll32.exe");
      if ( v2 >= 0 )
      {
        v2 = StringCchCopyW(CommandLine, 0x104u, L"rundll32.exe user32.dll,LockWorkStation");
        if ( v2 >= 0 )
        {
          active = WTSGetActiveConsoleSessionId();
          if ( active == -1 )
          {
            if ( (unsigned int)dword_18002B000 > 5 && (unsigned __int8)tlgKeywordOn(v4, 0x200000000000LL, v5) )
              tlgWriteTransfer_EventWriteTransfer(&dword_18002B000, byte_1800249B9, 0, 0, 2, v12);
            return (unsigned int)-2147467259;
          }
          else
          {
            if ( WTSQueryUserToken(active, &phToken) )
              goto LABEL_20;
            LastError = GetLastError();
            v2 = LastError;
            if ( LastError > 0 )
              v2 = (unsigned __int16)LastError | 0x80070000;
            if ( v2 >= 0 )
            {
LABEL_20:
              if ( CreateProcessAsUserW(
                     phToken,
                     ApplicationName,
                     CommandLine,
                     0,
                     0,
                     0,
                     0,
                     0,
                     0,
                     &StartupInfo,
                     &ProcessInformation) )
              {
                goto LABEL_21;
              }
              v7 = GetLastError();
              v2 = v7;
              if ( v7 > 0 )
                v2 = (unsigned __int16)v7 | 0x80070000;
              if ( v2 >= 0 )
              {
LABEL_21:
                CloseHandle(ProcessInformation.hThread);
                CloseHandle(ProcessInformation.hProcess);
              }
              CloseHandle(phToken);
            }
          }
        }
      }
    }
    else
    {
      return (unsigned int)-2147024883;
    }
  }
  else
  {
    v1 = GetLastError();
    v2 = v1;
    if ( v1 > 0 )
      return (unsigned __int16)v1 | 0x80070000;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180003378  mov     [rsp-8+arg_0], rbx
0x18000337d  mov     [rsp-8+arg_8], rdi
0x180003382  push    rbp
0x180003383  lea     rbp, [rsp-650h]
0x18000338b  sub     rsp, 750h
0x180003392  mov     rax, cs:__security_cookie
0x180003399  xor     rax, rsp
0x18000339c  mov     [rbp+650h+var_10], rax
0x1800033a3  xor     edx, edx; Val
0x1800033a5  mov     [rsp+750h+phToken], 0
0x1800033ae  lea     rcx, [rbp+650h+StartupInfo.lpReserved]; void *
0x1800033b2  mov     qword ptr [rbp+650h+StartupInfo.cb], 68h ; 'h'
0x1800033ba  lea     r8d, [rdx+60h]; Size
0x1800033be  call    memset_0
0x1800033c3  xorps   xmm0, xmm0
0x1800033c6  lea     rcx, [rbp+650h+Buffer]; lpBuffer
0x1800033ca  xor     eax, eax
0x1800033cc  mov     edi, 104h
0x1800033d1  mov     edx, edi; uSize
0x1800033d3  mov     qword ptr [rsp+750h+ProcessInformation.dwProcessId], rax
0x1800033d8  movups  xmmword ptr [rsp+750h+ProcessInformation.hProcess], xmm0
0x1800033dd  call    cs:__imp_GetSystemDirectoryW
0x1800033e4  nop     dword ptr [rax+rax+00h]
0x1800033e9  test    eax, eax
0x1800033eb  jnz     short loc_180003411
0x1800033ed  call    cs:__imp_GetLastError
0x1800033f4  nop     dword ptr [rax+rax+00h]
0x1800033f9  mov     ebx, eax
0x1800033fb  test    eax, eax
0x1800033fd  jle     loc_1800035BF
0x180003403  movzx   ebx, ax
0x180003406  or      ebx, 80070000h
0x18000340c  jmp     loc_1800035BF
0x180003411  cmp     eax, edi
0x180003413  jbe     short loc_18000341F
0x180003415  mov     ebx, 8007000Dh
0x18000341a  jmp     loc_1800035BF
0x18000341f  lea     rax, aRundll32Exe; "rundll32.exe"
0x180003426  mov     rdx, rdi; unsigned __int64
0x180003429  lea     r9, [rbp+650h+Buffer]
0x18000342d  mov     [rsp+750h+lpThreadAttributes], rax
0x180003432  lea     r8, aSS; "%s\\%s"
0x180003439  lea     rcx, [rbp+650h+ApplicationName]; unsigned __int16 *
0x180003440  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003445  mov     ebx, eax
0x180003447  test    eax, eax
0x180003449  js      loc_1800035BF
0x18000344f  lea     r8, aRundll32ExeUse; "rundll32.exe user32.dll,LockWorkStation"
0x180003456  mov     rdx, rdi; unsigned __int64
0x180003459  lea     rcx, [rbp+650h+CommandLine]; unsigned __int16 *
0x180003460  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003465  mov     ebx, eax
0x180003467  test    eax, eax
0x180003469  js      loc_1800035BF
0x18000346f  call    cs:__imp_WTSGetActiveConsoleSessionId
0x180003476  nop     dword ptr [rax+rax+00h]
0x18000347b  cmp     eax, 0FFFFFFFFh
0x18000347e  jnz     short loc_1800034D2
0x180003480  mov     eax, cs:dword_18002B000
0x180003486  cmp     eax, 5
0x180003489  jbe     short loc_1800034C8
0x18000348b  mov     rdx, 200000000000h
0x180003495  call    _tlgKeywordOn
0x18000349a  test    al, al
0x18000349c  jz      short loc_1800034C8
0x18000349e  lea     rax, [rbp+650h+var_660]
0x1800034a2  xor     r9d, r9d
0x1800034a5  mov     qword ptr [rsp+750h+bInheritHandles], rax
0x1800034aa  lea     rdx, byte_1800249B9
0x1800034b1  xor     r8d, r8d
0x1800034b4  mov     dword ptr [rsp+750h+lpThreadAttributes], 2
0x1800034bc  lea     rcx, dword_18002B000
0x1800034c3  call    _tlgWriteTransfer_EventWriteTransfer
0x1800034c8  mov     ebx, 80004005h
0x1800034cd  jmp     loc_1800035BF
0x1800034d2  lea     rdx, [rsp+750h+phToken]; phToken
0x1800034d7  mov     ecx, eax; SessionId
0x1800034d9  call    cs:__imp_WTSQueryUserToken
0x1800034e0  nop     dword ptr [rax+rax+00h]
0x1800034e5  mov     edi, 80070000h
0x1800034ea  test    eax, eax
0x1800034ec  jnz     short loc_18000350D
0x1800034ee  call    cs:__imp_GetLastError
0x1800034f5  nop     dword ptr [rax+rax+00h]
0x1800034fa  mov     ebx, eax
0x1800034fc  test    eax, eax
0x1800034fe  jle     short loc_180003505
0x180003500  movzx   ebx, ax
0x180003503  or      ebx, edi
0x180003505  test    ebx, ebx
0x180003507  js      loc_1800035BF
0x18000350d  mov     rcx, [rsp+750h+phToken]; hToken
0x180003512  lea     rax, [rsp+750h+ProcessInformation]
0x180003517  mov     [rsp+750h+lpProcessInformation], rax; lpProcessInformation
0x18000351c  lea     r8, [rbp+650h+CommandLine]; lpCommandLine
0x180003523  lea     rax, [rbp+650h+StartupInfo]
0x180003527  xor     r9d, r9d; lpProcessAttributes
0x18000352a  mov     [rsp+750h+lpStartupInfo], rax; lpStartupInfo
0x18000352f  lea     rdx, [rbp+650h+ApplicationName]; lpApplicationName
0x180003536  mov     [rsp+750h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18000353f  mov     [rsp+750h+lpEnvironment], 0; lpEnvironment
0x180003548  mov     [rsp+750h+dwCreationFlags], 0; dwCreationFlags
0x180003550  mov     [rsp+750h+bInheritHandles], 0; bInheritHandles
0x180003558  mov     [rsp+750h+lpThreadAttributes], 0; lpThreadAttributes
0x180003561  call    cs:__imp_CreateProcessAsUserW
0x180003568  nop     dword ptr [rax+rax+00h]
0x18000356d  test    eax, eax
0x18000356f  jnz     short loc_18000358C
0x180003571  call    cs:__imp_GetLastError
0x180003578  nop     dword ptr [rax+rax+00h]
0x18000357d  mov     ebx, eax
0x18000357f  test    eax, eax
0x180003581  jle     short loc_180003588
0x180003583  movzx   ebx, ax
0x180003586  or      ebx, edi
0x180003588  test    ebx, ebx
0x18000358a  js      short loc_1800035AE
0x18000358c  mov     rcx, [rsp+750h+ProcessInformation.hThread]; hObject
0x180003591  call    cs:__imp_CloseHandle
0x180003598  nop     dword ptr [rax+rax+00h]
0x18000359d  mov     rcx, [rsp+750h+ProcessInformation.hProcess]; hObject
0x1800035a2  call    cs:__imp_CloseHandle
0x1800035a9  nop     dword ptr [rax+rax+00h]
0x1800035ae  mov     rcx, [rsp+750h+phToken]; hObject
0x1800035b3  call    cs:__imp_CloseHandle
0x1800035ba  nop     dword ptr [rax+rax+00h]
0x1800035bf  mov     eax, ebx
0x1800035c1  mov     rcx, [rbp+650h+var_10]
0x1800035c8  xor     rcx, rsp; StackCookie
0x1800035cb  call    __security_check_cookie
0x1800035d0  lea     r11, [rsp+750h+var_s0]
0x1800035d8  mov     rbx, [r11+10h]
0x1800035dc  mov     rdi, [r11+18h]
0x1800035e0  mov     rsp, r11
0x1800035e3  pop     rbp
0x1800035e4  retn
```
