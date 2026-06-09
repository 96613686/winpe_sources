# CEventNotificationService::CoreProcessWatcherThreadProc(void)

- ea: `0x140018304`
- end: `0x140018539`
- name: `?CoreProcessWatcherThreadProc@CEventNotificationService@@IEAAJXZ`
- size: `565`
- prototype: `__int64 __fastcall(CEventNotificationService *this, __int64, __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task`

## callers

- `0x140027f30`

## callees

- `0x140018304`
- `0x1400267d0`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c290`
- `0x14005c408`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400184cd`
- `KERNEL32!CloseHandle` at `0x1400184e9`
- `KERNEL32!CloseHandle` at `0x14001851b`
- `KERNEL32!CloseHandle` at `0x1400184cd`
- `KERNEL32!CloseHandle` at `0x1400184e9`
- `KERNEL32!CloseHandle` at `0x14001851b`
- `KERNEL32!GetProcessId` at `0x1400184ab`
- `KERNEL32!GetProcessId` at `0x1400184ab`
- `KERNEL32!WaitForMultipleObjects` at `0x1400183d1`
- `KERNEL32!WaitForMultipleObjects` at `0x1400183d1`
- `KERNEL32!GetLastError` at `0x1400183e8`
- `KERNEL32!GetLastError` at `0x1400183e8`
- `KERNEL32!IsDebuggerPresent` at `0x14001835d`
- `KERNEL32!IsDebuggerPresent` at `0x140018432`
- `KERNEL32!IsDebuggerPresent` at `0x14001835d`
- `KERNEL32!IsDebuggerPresent` at `0x140018432`

## string_xrefs

- `0x140018344`: `(m_hCoreProcess != NULL) && (m_hCoreProcessWatcherThreadTerminationEvent != NULL)`
- `0x140018316`: `CEventNotificationService::CoreProcessWatcherThreadProc`
- `0x1400183b5`: `CEventNotificationService::CoreProcessWatcherThreadProc - Waiting for shell process to terminate...\n`
- `0x140018499`: `CEventNotificationService::CoreProcessWatcherThreadProc - Kill event signaled\n`
- `0x1400184b3`: `CEventNotificationService::CoreProcessWatcherThreadProc - Detected termination of core process 0x%X\n`
- `0x140018501`: `CEventNotificationService::CoreProcessWatcherThreadProc - Exiting\n`

## pseudocode

```c
__int64 __fastcall CEventNotificationService::CoreProcessWatcherThreadProc(
        CEventNotificationService *this,
        __int64 a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  __int64 v5; // rcx
  DWORD v6; // eax
  signed int LastError; // eax
  signed int v8; // ebx
  DWORD ProcessId; // eax
  char *v10; // rcx
  char *v11; // rcx
  char *v12; // rcx
  __int64 v14; // [rsp+30h] [rbp-58h]
  signed int v15; // [rsp+38h] [rbp-50h]
  HANDLE Handles; // [rsp+40h] [rbp-48h] BYREF
  __int64 v17; // [rsp+48h] [rbp-40h]

  Handles = (HANDLE)*((_QWORD *)this + 10);
  v5 = *((_QWORD *)this + 12);
  v17 = v5;
  if ( !Handles || !v5 )
  {
    LOGASSERT(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0x179Cu,
      L"CEventNotificationService::CoreProcessWatcherThreadProc",
      a4,
      L"(m_hCoreProcess != NULL) && (m_hCoreProcessWatcherThreadTerminationEvent != NULL)");
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        6044,
        L"CEventNotificationService::CoreProcessWatcherThreadProc",
        L"ASSERT",
        L"(m_hCoreProcess != NULL) && (m_hCoreProcessWatcherThreadTerminationEvent != NULL)");
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        6044,
        L"CEventNotificationService::CoreProcessWatcherThreadProc",
        L"ASSERT",
        L"(m_hCoreProcess != NULL) && (m_hCoreProcessWatcherThreadTerminationEvent != NULL)");
  }
  DEBUGMSG(L"CEventNotificationService::CoreProcessWatcherThreadProc - Waiting for shell process to terminate...\n");
  v6 = WaitForMultipleObjects(2u, &Handles, 0, 0xFFFFFFFF);
  if ( v6 )
  {
    if ( v6 == 1 )
    {
      v8 = 0;
      DEBUGMSG(L"CEventNotificationService::CoreProcessWatcherThreadProc - Kill event signaled\n");
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( v8 >= 0 )
        v8 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        0x17BCu,
        L"CEventNotificationService::CoreProcessWatcherThreadProc",
        L"CBRAEx",
        L"0",
        v8);
      if ( IsDebuggerPresent() )
      {
        v15 = v8;
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          6076,
          L"CEventNotificationService::CoreProcessWatcherThreadProc",
          L"CBRAEx",
          L"0",
          v15,
          Handles,
          v17);
      }
      else
      {
        LODWORD(v14) = v8;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          6076,
          L"CEventNotificationService::CoreProcessWatcherThreadProc",
          L"CBRAEx",
          L"0",
          v14);
      }
    }
  }
  else
  {
    ProcessId = GetProcessId(*((HANDLE *)this + 10));
    DEBUGMSG(
      L"CEventNotificationService::CoreProcessWatcherThreadProc - Detected termination of core process 0x%X\n",
      ProcessId);
    v10 = (char *)*((_QWORD *)this + 10);
    if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v10);
      *((_QWORD *)this + 10) = 0;
    }
    v11 = (char *)*((_QWORD *)this + 11);
    if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v11);
      *((_QWORD *)this + 11) = 0;
    }
    v8 = CEventNotificationService::SwitchToMaintenanceMode(this);
  }
  DEBUGMSG(L"CEventNotificationService::CoreProcessWatcherThreadProc - Exiting\n");
  v12 = (char *)*((_QWORD *)this + 10);
  if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v12);
    *((_QWORD *)this + 10) = 0;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140018304  push    rbx
0x140018306  push    rbp
0x140018307  push    rdi
0x140018308  push    r13
0x14001830a  push    r14
0x14001830c  push    r15
0x14001830e  sub     rsp, 58h
0x140018312  mov     rax, [rcx+50h]
0x140018316  lea     r14, aCeventnotifica_164; "CEventNotificationService::CoreProcessW"...
0x14001831d  mov     [rsp+88h+Handles], rax
0x140018322  mov     rdi, rcx
0x140018325  mov     rcx, [rcx+60h]
0x140018329  lea     rbp, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140018330  mov     [rsp+88h+var_40], rcx
0x140018335  test    rax, rax
0x140018338  jz      short loc_14001833F
0x14001833a  test    rcx, rcx
0x14001833d  jnz     short loc_1400183B5
0x14001833f  mov     ebx, 179Ch
0x140018344  lea     r15, aMHcoreprocessN_0; "(m_hCoreProcess != NULL) && (m_hCorePro"...
0x14001834b  mov     edx, ebx; unsigned int
0x14001834d  mov     [rsp+88h+var_68], r15; unsigned __int16 *
0x140018352  mov     r8, r14; unsigned __int16 *
0x140018355  mov     rcx, rbp; unsigned __int16 *
0x140018358  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x14001835d  call    cs:__imp_IsDebuggerPresent
0x140018363  test    eax, eax
0x140018365  lea     rax, aAssert; "ASSERT"
0x14001836c  jz      short loc_140018396
0x14001836e  mov     [rsp+88h+var_58], r15
0x140018373  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14001837a  mov     qword ptr [rsp+88h+var_60], rax
0x14001837f  mov     r9d, ebx
0x140018382  mov     r8, rbp
0x140018385  mov     [rsp+88h+var_68], r14
0x14001838a  mov     ecx, 2; unsigned __int8
0x14001838f  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140018394  jmp     short loc_1400183B5
0x140018396  mov     qword ptr [rsp+88h+var_60], r15
0x14001839b  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400183a2  mov     r9, r14
0x1400183a5  mov     [rsp+88h+var_68], rax
0x1400183aa  mov     r8d, ebx
0x1400183ad  mov     rdx, rbp
0x1400183b0  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400183b5  lea     rcx, aCeventnotifica_149; "CEventNotificationService::CoreProcessW"...
0x1400183bc  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400183c1  xor     r8d, r8d; bWaitAll
0x1400183c4  lea     rdx, [rsp+88h+Handles]; lpHandles
0x1400183c9  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1400183cd  lea     ecx, [r8+2]; nCount
0x1400183d1  call    cs:__imp_WaitForMultipleObjects
0x1400183d7  test    eax, eax
0x1400183d9  jz      loc_1400184A7
0x1400183df  cmp     eax, 1
0x1400183e2  jz      loc_140018497
0x1400183e8  call    cs:__imp_GetLastError
0x1400183ee  mov     ebx, eax
0x1400183f0  test    eax, eax
0x1400183f2  jle     short loc_1400183FD
0x1400183f4  movzx   ebx, ax
0x1400183f7  or      ebx, 80070000h
0x1400183fd  mov     eax, 80004005h
0x140018402  lea     r13, a0; "0"
0x140018409  test    ebx, ebx
0x14001840b  lea     r9, aCbraex; "CBRAEx"
0x140018412  mov     r15d, 17BCh
0x140018418  mov     r8, r14; unsigned __int16 *
0x14001841b  cmovns  ebx, eax
0x14001841e  mov     edx, r15d; unsigned int
0x140018421  mov     [rsp+88h+var_60], ebx; int
0x140018425  mov     rcx, rbp; unsigned __int16 *
0x140018428  mov     [rsp+88h+var_68], r13; unsigned __int16 *
0x14001842d  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140018432  call    cs:__imp_IsDebuggerPresent
0x140018438  test    eax, eax
0x14001843a  lea     rax, aCbraex; "CBRAEx"
0x140018441  jz      short loc_140018472
0x140018443  mov     [rsp+88h+var_50], ebx
0x140018447  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14001844e  mov     [rsp+88h+var_58], r13
0x140018453  mov     r9d, r15d
0x140018456  mov     qword ptr [rsp+88h+var_60], rax
0x14001845b  mov     r8, rbp
0x14001845e  mov     ecx, 2; unsigned __int8
0x140018463  mov     [rsp+88h+var_68], r14
0x140018468  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14001846d  jmp     loc_140018501
0x140018472  mov     dword ptr [rsp+88h+var_58], ebx
0x140018476  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14001847d  mov     qword ptr [rsp+88h+var_60], r13
0x140018482  mov     r9, r14
0x140018485  mov     r8d, r15d
0x140018488  mov     [rsp+88h+var_68], rax
0x14001848d  mov     rdx, rbp
0x140018490  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140018495  jmp     short loc_140018501
0x140018497  xor     ebx, ebx
0x140018499  lea     rcx, aCeventnotifica_123; "CEventNotificationService::CoreProcessW"...
0x1400184a0  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400184a5  jmp     short loc_140018501
0x1400184a7  mov     rcx, [rdi+50h]; Process
0x1400184ab  call    cs:__imp_GetProcessId
0x1400184b1  mov     edx, eax
0x1400184b3  lea     rcx, aCeventnotifica_85; "CEventNotificationService::CoreProcessW"...
0x1400184ba  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400184bf  mov     rcx, [rdi+50h]; hObject
0x1400184c3  lea     rax, [rcx-1]
0x1400184c7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400184cb  ja      short loc_1400184DB
0x1400184cd  call    cs:__imp_CloseHandle
0x1400184d3  mov     qword ptr [rdi+50h], 0
0x1400184db  mov     rcx, [rdi+58h]; hObject
0x1400184df  lea     rax, [rcx-1]
0x1400184e3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400184e7  ja      short loc_1400184F7
0x1400184e9  call    cs:__imp_CloseHandle
0x1400184ef  mov     qword ptr [rdi+58h], 0
0x1400184f7  mov     rcx, rdi; this
0x1400184fa  call    ?SwitchToMaintenanceMode@CEventNotificationService@@IEAAJXZ; CEventNotificationService::SwitchToMaintenanceMode(void)
0x1400184ff  mov     ebx, eax
0x140018501  lea     rcx, aCeventnotifica_91; "CEventNotificationService::CoreProcessW"...
0x140018508  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14001850d  mov     rcx, [rdi+50h]; hObject
0x140018511  lea     rdx, [rcx-1]
0x140018515  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x140018519  ja      short loc_140018529
0x14001851b  call    cs:__imp_CloseHandle
0x140018521  mov     qword ptr [rdi+50h], 0
0x140018529  mov     eax, ebx
0x14001852b  add     rsp, 58h
0x14001852f  pop     r15
0x140018531  pop     r14
0x140018533  pop     r13
0x140018535  pop     rdi
0x140018536  pop     rbp
0x140018537  pop     rbx
0x140018538  retn
```
