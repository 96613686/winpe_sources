# CEventNotificationService::TerminateAllRunningSessionAgents(void)

- ea: `0x140026bbc`
- end: `0x140026ede`
- name: `?TerminateAllRunningSessionAgents@CEventNotificationService@@IEAAJXZ`
- size: `802`
- prototype: `__int64 __fastcall(CEventNotificationService *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task`

## callers

- `0x14001e6c8`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x140026bbc`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c290`
- `0x14005c408`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140026c85`
- `KERNEL32!CloseHandle` at `0x140026eb3`
- `KERNEL32!CloseHandle` at `0x140026c85`
- `KERNEL32!CloseHandle` at `0x140026eb3`
- `KERNEL32!K32GetProcessImageFileNameW` at `0x140026cb6`
- `KERNEL32!K32GetProcessImageFileNameW` at `0x140026cb6`
- `KERNEL32!K32EnumProcesses` at `0x140026c44`
- `KERNEL32!K32EnumProcesses` at `0x140026c44`
- `KERNEL32!OpenProcess` at `0x140026c96`
- `KERNEL32!OpenProcess` at `0x140026c96`
- `KERNEL32!TerminateProcess` at `0x140026d0f`
- `KERNEL32!TerminateProcess` at `0x140026d0f`
- `KERNEL32!GetLastError` at `0x140026d1d`
- `KERNEL32!GetLastError` at `0x140026dcd`
- `KERNEL32!GetLastError` at `0x140026d1d`
- `KERNEL32!GetLastError` at `0x140026dcd`
- `KERNEL32!IsDebuggerPresent` at `0x140026d5a`
- `KERNEL32!IsDebuggerPresent` at `0x140026e3d`
- `KERNEL32!IsDebuggerPresent` at `0x140026d5a`
- `KERNEL32!IsDebuggerPresent` at `0x140026e3d`
- `msvcrt!wcsrchr` at `0x140026cce`
- `msvcrt!wcsrchr` at `0x140026cce`
- `msvcrt!_wcsicmp` at `0x140026ce7`
- `msvcrt!_wcsicmp` at `0x140026ce7`

## string_xrefs

- `0x140026c6a`: `CEventNotificationService::TerminateAllRunningSessionAgents`
- `0x140026e19`: `CEventNotificationService::TerminateAllRunningSessionAgents`
- `0x140026ce0`: `WmsSessionAgent.exe`
- `0x140026cfe`: `CEventNotificationService::TerminateAllRunningSessionAgents - Terminating WmsSessionAgent process ID %li (%s) .\n`
- `0x140026d31`: `CEventNotificationService::TerminateAllRunningSessionAgents - TerminateProcess() failed, hr = 0x%08X\n`

## pseudocode

```c
__int64 __fastcall CEventNotificationService::TerminateAllRunningSessionAgents(CEventNotificationService *this)
{
  DWORD v1; // ebx
  DWORD *v2; // r15
  char *v3; // r14
  DWORD *v4; // rax
  signed int v5; // ebx
  DWORD v6; // ebp
  __int64 v7; // r12
  char *v8; // rax
  wchar_t *v9; // rax
  signed int v10; // eax
  const unsigned __int16 *v11; // r9
  signed int LastError; // eax
  const unsigned __int16 *v13; // r12
  const unsigned __int16 *v14; // r13
  unsigned int v15; // ebp
  DWORD cbNeeded[4]; // [rsp+40h] [rbp-268h] BYREF
  WCHAR ImageFileName[264]; // [rsp+50h] [rbp-258h] BYREF

  v1 = 0;
  cbNeeded[0] = 0;
  v2 = 0;
  memset_0(ImageFileName, 0, 0x208u);
  v3 = 0;
  do
  {
    v1 += 4096;
    operator delete(v2);
    v4 = (DWORD *)operator new(saturated_mul((unsigned __int64)v1 >> 2, 4u));
    v2 = v4;
    if ( !v4 )
    {
      v5 = -2147024882;
      v13 = L"pdwProcesses";
      v14 = L"CPR";
      v15 = 6455;
LABEL_26:
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        v15,
        L"CEventNotificationService::TerminateAllRunningSessionAgents",
        v14,
        v13,
        v5);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          v15,
          L"CEventNotificationService::TerminateAllRunningSessionAgents",
          v14,
          v13,
          v5);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          v15,
          L"CEventNotificationService::TerminateAllRunningSessionAgents",
          v14,
          v13,
          v5);
      goto LABEL_29;
    }
    if ( !K32EnumProcesses(v4, v1, cbNeeded) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      v13 = L"fSuccess";
      v14 = L"CBRAEx";
      if ( v5 >= 0 )
        v5 = -2147467259;
      v15 = 6458;
      goto LABEL_26;
    }
  }
  while ( cbNeeded[0] >= v1 );
  v5 = 0;
  v6 = cbNeeded[0] >> 2;
  v7 = 0;
  if ( cbNeeded[0] >> 2 )
  {
    do
    {
      if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v3);
      v8 = (char *)OpenProcess(0x1001u, 0, v2[v7]);
      v3 = v8;
      if ( v8 )
      {
        if ( K32GetProcessImageFileNameW(v8, ImageFileName, 0x104u) )
        {
          v9 = wcsrchr(ImageFileName, 0x5Cu);
          if ( v9 )
          {
            if ( !_wcsicmp(L"WmsSessionAgent.exe", v9) )
            {
              DEBUGMSG(
                L"CEventNotificationService::TerminateAllRunningSessionAgents - Terminating WmsSessionAgent process ID %li (%s) .\n",
                v2[v7],
                ImageFileName);
              if ( !TerminateProcess(v3, 0) )
              {
                v10 = GetLastError();
                if ( v10 > 0 )
                  v10 = (unsigned __int16)v10 | 0x80070000;
                DEBUGMSG(
                  L"CEventNotificationService::TerminateAllRunningSessionAgents - TerminateProcess() failed, hr = 0x%08X\n",
                  (unsigned int)v10);
                LOGASSERT(
                  L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
                  0x1962u,
                  L"CEventNotificationService::TerminateAllRunningSessionAgents",
                  v11,
                  L"FALSE");
                if ( IsDebuggerPresent() )
                  DEBUGMSGLEVEL(
                    2u,
                    L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
                    L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
                    6498,
                    L"CEventNotificationService::TerminateAllRunningSessionAgents",
                    L"ASSERT",
                    L"FALSE");
                else
                  DEBUGMSGBOX(
                    L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
                    L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
                    6498,
                    L"CEventNotificationService::TerminateAllRunningSessionAgents",
                    L"ASSERT",
                    L"FALSE");
              }
            }
          }
        }
      }
      v7 = (unsigned int)(v7 + 1);
    }
    while ( (unsigned int)v7 < v6 );
    v5 = 0;
  }
LABEL_29:
  operator delete(v2);
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140026bbc  push    rbx
0x140026bbe  push    rbp
0x140026bbf  push    rsi
0x140026bc0  push    r12
0x140026bc2  push    r13
0x140026bc4  push    r14
0x140026bc6  push    r15
0x140026bc8  sub     rsp, 270h
0x140026bcf  mov     rax, cs:__security_cookie
0x140026bd6  xor     rax, rsp
0x140026bd9  mov     [rsp+2A8h+var_48], rax
0x140026be1  xor     ebx, ebx
0x140026be3  lea     rcx, [rsp+2A8h+ImageFileName]; void *
0x140026be8  xor     edx, edx; Val
0x140026bea  mov     [rsp+2A8h+cbNeeded], ebx
0x140026bee  mov     r8d, 208h; Size
0x140026bf4  xor     r15d, r15d
0x140026bf7  call    memset_0
0x140026bfc  xor     r14d, r14d
0x140026bff  mov     rcx, r15; Block
0x140026c02  add     ebx, 1000h
0x140026c08  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140026c0d  mov     ecx, ebx
0x140026c0f  mov     eax, 4
0x140026c14  shr     rcx, 2
0x140026c18  mul     rcx
0x140026c1b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140026c22  cmovb   rax, rcx
0x140026c26  mov     rcx, rax; Size
0x140026c29  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140026c2e  mov     r15, rax
0x140026c31  test    rax, rax
0x140026c34  jz      loc_140026E01
0x140026c3a  lea     r8, [rsp+2A8h+cbNeeded]; lpcbNeeded
0x140026c3f  mov     edx, ebx; cb
0x140026c41  mov     rcx, rax; lpidProcess
0x140026c44  call    cs:__imp_K32EnumProcesses
0x140026c4a  test    eax, eax
0x140026c4c  jz      loc_140026DCD
0x140026c52  mov     ebp, [rsp+2A8h+cbNeeded]
0x140026c56  cmp     ebp, ebx
0x140026c58  jnb     short loc_140026BFF
0x140026c5a  xor     ebx, ebx
0x140026c5c  shr     ebp, 2
0x140026c5f  xor     r12d, r12d
0x140026c62  test    ebp, ebp
0x140026c64  jz      loc_140026E9E
0x140026c6a  lea     rsi, aCeventnotifica_168; "CEventNotificationService::TerminateAll"...
0x140026c71  lea     rbx, aFalse; "FALSE"
0x140026c78  lea     rax, [r14-1]
0x140026c7c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140026c80  ja      short loc_140026C8B
0x140026c82  mov     rcx, r14; hObject
0x140026c85  call    cs:__imp_CloseHandle
0x140026c8b  mov     r8d, [r15+r12*4]; dwProcessId
0x140026c8f  xor     edx, edx; bInheritHandle
0x140026c91  mov     ecx, 1001h; dwDesiredAccess
0x140026c96  call    cs:__imp_OpenProcess
0x140026c9c  mov     r14, rax
0x140026c9f  test    rax, rax
0x140026ca2  jz      loc_140026DBA
0x140026ca8  mov     r8d, 104h; nSize
0x140026cae  lea     rdx, [rsp+2A8h+ImageFileName]; lpImageFileName
0x140026cb3  mov     rcx, rax; hProcess
0x140026cb6  call    cs:__imp_K32GetProcessImageFileNameW
0x140026cbc  test    eax, eax
0x140026cbe  jz      loc_140026DBA
0x140026cc4  mov     edx, 5Ch ; '\'; Ch
0x140026cc9  lea     rcx, [rsp+2A8h+ImageFileName]; Str
0x140026cce  call    cs:__imp_wcsrchr
0x140026cd4  test    rax, rax
0x140026cd7  jz      loc_140026DBA
0x140026cdd  mov     rdx, rax; String2
0x140026ce0  lea     rcx, aWmssessionagen; "WmsSessionAgent.exe"
0x140026ce7  call    cs:__imp__wcsicmp
0x140026ced  test    eax, eax
0x140026cef  jnz     loc_140026DBA
0x140026cf5  mov     edx, [r15+r12*4]
0x140026cf9  lea     r8, [rsp+2A8h+ImageFileName]
0x140026cfe  lea     rcx, aCeventnotifica_207; "CEventNotificationService::TerminateAll"...
0x140026d05  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140026d0a  xor     edx, edx; uExitCode
0x140026d0c  mov     rcx, r14; hProcess
0x140026d0f  call    cs:__imp_TerminateProcess
0x140026d15  test    eax, eax
0x140026d17  jnz     loc_140026DBA
0x140026d1d  call    cs:__imp_GetLastError
0x140026d23  test    eax, eax
0x140026d25  jle     short loc_140026D2F
0x140026d27  movzx   eax, ax
0x140026d2a  or      eax, 80070000h
0x140026d2f  mov     edx, eax
0x140026d31  lea     rcx, aCeventnotifica_98; "CEventNotificationService::TerminateAll"...
0x140026d38  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140026d3d  mov     r13d, 1962h
0x140026d43  mov     [rsp+2A8h+var_288], rbx; unsigned __int16 *
0x140026d48  mov     edx, r13d; unsigned int
0x140026d4b  lea     rcx, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140026d52  mov     r8, rsi; unsigned __int16 *
0x140026d55  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140026d5a  call    cs:__imp_IsDebuggerPresent
0x140026d60  test    eax, eax
0x140026d62  lea     rax, aAssert; "ASSERT"
0x140026d69  jz      short loc_140026D97
0x140026d6b  mov     [rsp+2A8h+var_278], rbx
0x140026d70  lea     r8, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140026d77  mov     qword ptr [rsp+2A8h+var_280], rax
0x140026d7c  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140026d83  mov     r9d, r13d
0x140026d86  mov     [rsp+2A8h+var_288], rsi
0x140026d8b  mov     ecx, 2; unsigned __int8
0x140026d90  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140026d95  jmp     short loc_140026DBA
0x140026d97  mov     qword ptr [rsp+2A8h+var_280], rbx
0x140026d9c  lea     rdx, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140026da3  mov     r9, rsi
0x140026da6  mov     [rsp+2A8h+var_288], rax
0x140026dab  mov     r8d, r13d
0x140026dae  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140026db5  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140026dba  inc     r12d
0x140026dbd  cmp     r12d, ebp
0x140026dc0  jb      loc_140026C78
0x140026dc6  xor     ebx, ebx
0x140026dc8  jmp     loc_140026E9E
0x140026dcd  call    cs:__imp_GetLastError
0x140026dd3  mov     ebx, eax
0x140026dd5  test    eax, eax
0x140026dd7  jle     short loc_140026DE2
0x140026dd9  movzx   ebx, ax
0x140026ddc  or      ebx, 80070000h
0x140026de2  test    ebx, ebx
0x140026de4  lea     r12, aFsuccess; "fSuccess"
0x140026deb  mov     eax, 80004005h
0x140026df0  lea     r13, aCbraex; "CBRAEx"
0x140026df7  cmovns  ebx, eax
0x140026dfa  mov     ebp, 193Ah
0x140026dff  jmp     short loc_140026E19
0x140026e01  mov     ebx, 8007000Eh
0x140026e06  lea     r12, aPdwprocesses; "pdwProcesses"
0x140026e0d  lea     r13, aCpr; "CPR"
0x140026e14  mov     ebp, 1937h
0x140026e19  lea     rsi, aCeventnotifica_168; "CEventNotificationService::TerminateAll"...
0x140026e20  mov     [rsp+2A8h+var_280], ebx; int
0x140026e24  mov     r8, rsi; unsigned __int16 *
0x140026e27  mov     [rsp+2A8h+var_288], r12; unsigned __int16 *
0x140026e2c  mov     r9, r13; unsigned __int16 *
0x140026e2f  lea     rcx, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140026e36  mov     edx, ebp; unsigned int
0x140026e38  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140026e3d  call    cs:__imp_IsDebuggerPresent
0x140026e43  test    eax, eax
0x140026e45  jz      short loc_140026E77
0x140026e47  mov     [rsp+2A8h+var_270], ebx
0x140026e4b  lea     r8, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140026e52  mov     [rsp+2A8h+var_278], r12
0x140026e57  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140026e5e  mov     qword ptr [rsp+2A8h+var_280], r13
0x140026e63  mov     r9d, ebp
0x140026e66  mov     ecx, 2; unsigned __int8
0x140026e6b  mov     [rsp+2A8h+var_288], rsi
0x140026e70  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140026e75  jmp     short loc_140026E9E
0x140026e77  mov     dword ptr [rsp+2A8h+var_278], ebx
0x140026e7b  lea     rdx, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140026e82  mov     qword ptr [rsp+2A8h+var_280], r12
0x140026e87  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140026e8e  mov     r9, rsi
0x140026e91  mov     [rsp+2A8h+var_288], r13
0x140026e96  mov     r8d, ebp
0x140026e99  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140026e9e  mov     rcx, r15; Block
0x140026ea1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140026ea6  lea     rcx, [r14-1]
0x140026eaa  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140026eae  ja      short loc_140026EB9
0x140026eb0  mov     rcx, r14; hObject
0x140026eb3  call    cs:__imp_CloseHandle
0x140026eb9  mov     eax, ebx
0x140026ebb  mov     rcx, [rsp+2A8h+var_48]
0x140026ec3  xor     rcx, rsp; StackCookie
0x140026ec6  call    __security_check_cookie
0x140026ecb  add     rsp, 270h
0x140026ed2  pop     r15
0x140026ed4  pop     r14
0x140026ed6  pop     r13
0x140026ed8  pop     r12
0x140026eda  pop     rsi
0x140026edb  pop     rbp
0x140026edc  pop     rbx
0x140026edd  retn
```
