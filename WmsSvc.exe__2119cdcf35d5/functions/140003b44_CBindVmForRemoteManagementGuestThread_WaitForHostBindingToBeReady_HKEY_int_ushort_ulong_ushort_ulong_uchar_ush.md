# CBindVmForRemoteManagementGuestThread::WaitForHostBindingToBeReady(HKEY__ *,int *,ushort * *,ulong *,ushort * *,ulong *,uchar * *,ushort * *)

- ea: `0x140003b44`
- end: `0x140003f3f`
- name: `?WaitForHostBindingToBeReady@CBindVmForRemoteManagementGuestThread@@IEAAJPEAUHKEY__@@PEAHPEAPEAGPEAK23PEAPEAE2@Z`
- size: `1019`
- prototype: `__int64 __usercall@<rax>(CBindVmForRemoteManagementGuestThread *__hidden this@<rcx>, HKEY hKey@<rdx>, int *@<r8>, unsigned __int16 **@<r9>, unsigned int *, unsigned __int16 **, unsigned int *, unsigned __int8 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140003f48`

## callees

- `0x140002a0c`
- `0x140003b44`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140003c61`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140003dc7`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140003c61`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140003dc7`
- `KERNEL32!CloseHandle` at `0x140003f26`
- `KERNEL32!CloseHandle` at `0x140003f26`
- `KERNEL32!ResetEvent` at `0x140003d86`
- `KERNEL32!ResetEvent` at `0x140003d86`
- `KERNEL32!WaitForMultipleObjects` at `0x140003d29`
- `KERNEL32!WaitForMultipleObjects` at `0x140003d29`
- `KERNEL32!CreateEventW` at `0x140003b7f`
- `KERNEL32!CreateEventW` at `0x140003b7f`
- `KERNEL32!GetLastError` at `0x140003b93`
- `KERNEL32!GetLastError` at `0x140003e5b`
- `KERNEL32!GetLastError` at `0x140003e8d`
- `KERNEL32!GetLastError` at `0x140003b93`
- `KERNEL32!GetLastError` at `0x140003e5b`
- `KERNEL32!GetLastError` at `0x140003e8d`
- `KERNEL32!IsDebuggerPresent` at `0x140003bee`
- `KERNEL32!IsDebuggerPresent` at `0x140003cb4`
- `KERNEL32!IsDebuggerPresent` at `0x140003e1e`
- `KERNEL32!IsDebuggerPresent` at `0x140003ee8`
- `KERNEL32!IsDebuggerPresent` at `0x140003bee`
- `KERNEL32!IsDebuggerPresent` at `0x140003cb4`
- `KERNEL32!IsDebuggerPresent` at `0x140003e1e`
- `KERNEL32!IsDebuggerPresent` at `0x140003ee8`

## string_xrefs

- `0x140003bc3`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x140003c90`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x140003dfa`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x140003ec4`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x140003bcd`: `rghEvents[ET_REGISTRY_CHANGE] != 0`
- `0x140003bb6`: `CBindVmForRemoteManagementGuestThread::WaitForHostBindingToBeReady`
- `0x140003c83`: `CBindVmForRemoteManagementGuestThread::WaitForHostBindingToBeReady`
- `0x140003ded`: `CBindVmForRemoteManagementGuestThread::WaitForHostBindingToBeReady`
- `0x140003ebd`: `CBindVmForRemoteManagementGuestThread::WaitForHostBindingToBeReady`
- `0x140003ceb`: `CBindVmForRemoteManagementGuestThread::WaitForHostBindingToBeReady - Starting wait for %s to be set\n`
- `0x140003f06`: `CBindVmForRemoteManagementGuestThread::WaitForHostBindingToBeReady - Termination event occured\n`
- `0x140003da4`: `CBindVmForRemoteManagementGuestThread::WaitForHostBindingToBeReady - Continue to wait for %s to be set\n`
- `0x140003e4a`: `CBindVmForRemoteManagementGuestThread::WaitForHostBindingToBeReady - %s is set\n`

## pseudocode

```c
__int64 __fastcall CBindVmForRemoteManagementGuestThread::WaitForHostBindingToBeReady(
        HANDLE *this,
        HKEY hKey,
        int *a3,
        unsigned __int16 **a4,
        unsigned int *a5,
        unsigned __int16 **a6,
        unsigned int *a7,
        unsigned __int8 **a8,
        unsigned __int16 **a9)
{
  HANDLE EventW; // rax
  signed int v13; // eax
  signed int HostBindingInfo; // ebx
  unsigned int v15; // r14d
  __int64 v16; // r9
  LSTATUS v17; // eax
  DWORD v18; // eax
  LSTATUS v19; // eax
  signed int LastError; // eax
  const unsigned __int16 *v21; // r12
  signed int v22; // eax
  unsigned int *v24; // [rsp+28h] [rbp-70h]
  unsigned __int8 **v25; // [rsp+30h] [rbp-68h]
  const unsigned __int16 *v26; // [rsp+30h] [rbp-68h]
  unsigned __int16 **v27; // [rsp+38h] [rbp-60h]
  HANDLE Handles[11]; // [rsp+40h] [rbp-58h] BYREF

  *a3 = 0;
  Handles[0] = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  Handles[1] = EventW;
  if ( EventW )
  {
    v17 = RegNotifyChangeKeyValue(hKey, 1, 4u, EventW, 1);
    HostBindingInfo = v17;
    if ( !v17 )
    {
      Handles[0] = this[3];
      DEBUGMSG(
        L"CBindVmForRemoteManagementGuestThread::WaitForHostBindingToBeReady - Starting wait for %s to be set\n",
        L"MultiPointHostSslCertificate-2");
      while ( 1 )
      {
        v18 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
        if ( !v18 )
        {
          DEBUGMSG(L"CBindVmForRemoteManagementGuestThread::WaitForHostBindingToBeReady - Termination event occured\n");
          HostBindingInfo = -2147467260;
          goto LABEL_42;
        }
        if ( v18 != 1 )
          break;
        HostBindingInfo = CBindVmForRemoteManagementGuestThread::GetHostBindingInfo(
                            (CBindVmForRemoteManagementGuestThread *)this,
                            a3,
                            a4,
                            a5,
                            a6,
                            a7,
                            a8,
                            a9);
        if ( HostBindingInfo < 0 )
          goto LABEL_42;
        if ( !ResetEvent(Handles[1]) )
        {
          LastError = GetLastError();
          HostBindingInfo = LastError;
          if ( LastError > 0 )
            HostBindingInfo = (unsigned __int16)LastError | 0x80070000;
          v21 = L"fSuccess";
          v15 = 616;
          goto LABEL_37;
        }
        if ( *a3 )
        {
          DEBUGMSG(
            L"CBindVmForRemoteManagementGuestThread::WaitForHostBindingToBeReady - %s is set\n",
            L"MultiPointHostSslCertificate-2");
          goto LABEL_42;
        }
        DEBUGMSG(
          L"CBindVmForRemoteManagementGuestThread::WaitForHostBindingToBeReady - Continue to wait for %s to be set\n",
          L"MultiPointHostSslCertificate-2");
        v19 = RegNotifyChangeKeyValue(hKey, 1, 4u, Handles[1], 1);
        HostBindingInfo = v19;
        if ( v19 )
        {
          if ( v19 > 0 )
            HostBindingInfo = (unsigned __int16)v19 | 0x80070000;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
            0x26Eu,
            L"CBindVmForRemoteManagementGuestThread::WaitForHostBindingToBeReady",
            L"CBRAEx",
            L"lr == 0L",
            HostBindingInfo);
          if ( IsDebuggerPresent() )
          {
            LODWORD(v27) = HostBindingInfo;
            v16 = 622;
            v26 = L"lr == 0L";
            goto LABEL_8;
          }
          LODWORD(v25) = HostBindingInfo;
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
            622,
            L"CBindVmForRemoteManagementGuestThread::WaitForHostBindingToBeReady",
            L"CBRAEx",
            L"lr == 0L",
            v25);
          goto LABEL_42;
        }
      }
      v22 = GetLastError();
      HostBindingInfo = v22;
      if ( v22 > 0 )
        HostBindingInfo = (unsigned __int16)v22 | 0x80070000;
      v21 = L"0";
      v15 = 639;
LABEL_37:
      if ( HostBindingInfo >= 0 )
        HostBindingInfo = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
        v15,
        L"CBindVmForRemoteManagementGuestThread::WaitForHostBindingToBeReady",
        L"CBRAEx",
        v21,
        HostBindingInfo);
      if ( !IsDebuggerPresent() )
      {
        LODWORD(v25) = HostBindingInfo;
        v24 = (unsigned int *)v21;
        goto LABEL_10;
      }
      LODWORD(v27) = HostBindingInfo;
      v16 = v15;
      v26 = v21;
      goto LABEL_8;
    }
    if ( v17 > 0 )
      HostBindingInfo = (unsigned __int16)v17 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
      0x251u,
      L"CBindVmForRemoteManagementGuestThread::WaitForHostBindingToBeReady",
      L"CBRAEx",
      L"lr == 0L",
      HostBindingInfo);
    if ( IsDebuggerPresent() )
    {
      LODWORD(v27) = HostBindingInfo;
      v16 = 593;
      v26 = L"lr == 0L";
      goto LABEL_8;
    }
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
      593,
      L"CBindVmForRemoteManagementGuestThread::WaitForHostBindingToBeReady",
      L"CBRAEx",
      L"lr == 0L",
      HostBindingInfo);
  }
  else
  {
    v13 = GetLastError();
    HostBindingInfo = v13;
    if ( v13 > 0 )
      HostBindingInfo = (unsigned __int16)v13 | 0x80070000;
    v15 = 590;
    if ( HostBindingInfo >= 0 )
      HostBindingInfo = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
      0x24Eu,
      L"CBindVmForRemoteManagementGuestThread::WaitForHostBindingToBeReady",
      L"CBRAEx",
      L"rghEvents[ET_REGISTRY_CHANGE] != 0",
      HostBindingInfo);
    if ( IsDebuggerPresent() )
    {
      LODWORD(v27) = HostBindingInfo;
      v16 = 590;
      v26 = L"rghEvents[ET_REGISTRY_CHANGE] != 0";
LABEL_8:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
        v16,
        L"CBindVmForRemoteManagementGuestThread::WaitForHostBindingToBeReady",
        L"CBRAEx",
        v26,
        v27,
        Handles[0]);
      goto LABEL_42;
    }
    LODWORD(v25) = HostBindingInfo;
    v24 = (unsigned int *)L"rghEvents[ET_REGISTRY_CHANGE] != 0";
LABEL_10:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
      v15,
      L"CBindVmForRemoteManagementGuestThread::WaitForHostBindingToBeReady",
      L"CBRAEx",
      v24,
      v25);
  }
LABEL_42:
  if ( (unsigned __int64)Handles[1] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(Handles[1]);
  return (unsigned int)HostBindingInfo;
}

```

## disassembly

```asm
0x140003b44  mov     [rsp+arg_18], r9
0x140003b49  push    rbx
0x140003b4a  push    rbp
0x140003b4b  push    rsi
0x140003b4c  push    rdi
0x140003b4d  push    r12
0x140003b4f  push    r13
0x140003b51  push    r14
0x140003b53  push    r15
0x140003b55  sub     rsp, 58h
0x140003b59  xor     r9d, r9d; lpName
0x140003b5c  mov     dword ptr [r8], 0
0x140003b63  mov     rdi, r8
0x140003b66  mov     rsi, rdx
0x140003b69  mov     rbp, rcx
0x140003b6c  xorps   xmm0, xmm0
0x140003b6f  xor     r8d, r8d; bInitialState
0x140003b72  xor     ecx, ecx; lpEventAttributes
0x140003b74  lea     ebx, [r9+1]
0x140003b78  mov     edx, ebx; bManualReset
0x140003b7a  movups  xmmword ptr [rsp+98h+Handles], xmm0
0x140003b7f  call    cs:__imp_CreateEventW
0x140003b85  mov     [rsp+98h+Handles+8], rax
0x140003b8a  test    rax, rax
0x140003b8d  jnz     loc_140003C4F
0x140003b93  call    cs:__imp_GetLastError
0x140003b99  mov     ebx, eax
0x140003b9b  test    eax, eax
0x140003b9d  jle     short loc_140003BA8
0x140003b9f  movzx   ebx, ax
0x140003ba2  or      ebx, 80070000h
0x140003ba8  mov     eax, 80004005h
0x140003bad  lea     rbp, aCbraex; "CBRAEx"
0x140003bb4  test    ebx, ebx
0x140003bb6  lea     rsi, aCbindvmforremo_16; "CBindVmForRemoteManagementGuestThread::"...
0x140003bbd  mov     r14d, 24Eh
0x140003bc3  lea     rdi, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x140003bca  cmovns  ebx, eax
0x140003bcd  lea     r15, aRgheventsEtReg; "rghEvents[ET_REGISTRY_CHANGE] != 0"
0x140003bd4  mov     dword ptr [rsp+98h+var_70], ebx; int
0x140003bd8  mov     r9, rbp; unsigned __int16 *
0x140003bdb  mov     r8, rsi; unsigned __int16 *
0x140003bde  mov     qword ptr [rsp+98h+fAsynchronous], r15; unsigned __int16 *
0x140003be3  mov     edx, r14d; unsigned int
0x140003be6  mov     rcx, rdi; unsigned __int16 *
0x140003be9  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140003bee  call    cs:__imp_IsDebuggerPresent
0x140003bf4  test    eax, eax
0x140003bf6  jz      short loc_140003C27
0x140003bf8  mov     dword ptr [rsp+98h+var_60], ebx
0x140003bfc  mov     r9d, r14d
0x140003bff  mov     [rsp+98h+var_68], r15
0x140003c04  mov     ecx, 2; unsigned __int8
0x140003c09  mov     [rsp+98h+var_70], rbp
0x140003c0e  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140003c15  mov     r8, rdi
0x140003c18  mov     qword ptr [rsp+98h+fAsynchronous], rsi
0x140003c1d  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140003c22  jmp     loc_140003F17
0x140003c27  mov     dword ptr [rsp+98h+var_68], ebx
0x140003c2b  mov     [rsp+98h+var_70], r15
0x140003c30  mov     r8d, r14d
0x140003c33  mov     r9, rsi
0x140003c36  mov     qword ptr [rsp+98h+fAsynchronous], rbp
0x140003c3b  mov     rdx, rdi
0x140003c3e  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140003c45  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140003c4a  jmp     loc_140003F17
0x140003c4f  mov     r9, rax; hEvent
0x140003c52  mov     [rsp+98h+fAsynchronous], ebx; fAsynchronous
0x140003c56  mov     r8d, 4; dwNotifyFilter
0x140003c5c  mov     edx, ebx; bWatchSubtree
0x140003c5e  mov     rcx, rsi; hKey
0x140003c61  call    cs:__imp_RegNotifyChangeKeyValue
0x140003c67  mov     ebx, eax
0x140003c69  test    eax, eax
0x140003c6b  jz      short loc_140003CE0
0x140003c6d  jle     short loc_140003C78
0x140003c6f  movzx   ebx, ax
0x140003c72  or      ebx, 80070000h
0x140003c78  lea     rbp, aCbraex; "CBRAEx"
0x140003c7f  mov     dword ptr [rsp+98h+var_70], ebx; int
0x140003c83  lea     rsi, aCbindvmforremo_16; "CBindVmForRemoteManagementGuestThread::"...
0x140003c8a  mov     r15d, 251h
0x140003c90  lea     rdi, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x140003c97  mov     r9, rbp; unsigned __int16 *
0x140003c9a  lea     r14, aLr0l; "lr == 0L"
0x140003ca1  mov     r8, rsi; unsigned __int16 *
0x140003ca4  mov     edx, r15d; unsigned int
0x140003ca7  mov     qword ptr [rsp+98h+fAsynchronous], r14; unsigned __int16 *
0x140003cac  mov     rcx, rdi; unsigned __int16 *
0x140003caf  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140003cb4  call    cs:__imp_IsDebuggerPresent
0x140003cba  test    eax, eax
0x140003cbc  jz      short loc_140003CCF
0x140003cbe  mov     dword ptr [rsp+98h+var_60], ebx
0x140003cc2  mov     r9d, r15d
0x140003cc5  mov     [rsp+98h+var_68], r14
0x140003cca  jmp     loc_140003C04
0x140003ccf  mov     dword ptr [rsp+98h+var_68], ebx
0x140003cd3  mov     r8d, r15d
0x140003cd6  mov     [rsp+98h+var_70], r14
0x140003cdb  jmp     loc_140003C33
0x140003ce0  mov     rax, [rbp+18h]
0x140003ce4  lea     rdx, aMultipointhost_4; "MultiPointHostSslCertificate-2"
0x140003ceb  lea     rcx, aCbindvmforremo_2; "CBindVmForRemoteManagementGuestThread::"...
0x140003cf2  mov     [rsp+98h+Handles], rax
0x140003cf7  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140003cfc  mov     r14, [rsp+98h+arg_40]
0x140003d04  mov     r15d, 2
0x140003d0a  mov     r12, [rsp+98h+arg_38]
0x140003d12  mov     r13, [rsp+98h+arg_30]
0x140003d1a  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x140003d1e  lea     rdx, [rsp+98h+Handles]; lpHandles
0x140003d23  xor     r8d, r8d; bWaitAll
0x140003d26  mov     ecx, r15d; nCount
0x140003d29  call    cs:__imp_WaitForMultipleObjects
0x140003d2f  test    eax, eax
0x140003d31  jz      loc_140003F06
0x140003d37  cmp     eax, 1
0x140003d3a  jnz     loc_140003E8D
0x140003d40  mov     rax, [rsp+98h+arg_28]
0x140003d48  mov     rdx, rdi; int *
0x140003d4b  mov     r9, [rsp+98h+arg_20]; unsigned int *
0x140003d53  mov     rcx, rbp; this
0x140003d56  mov     r8, [rsp+98h+arg_18]; unsigned __int16 **
0x140003d5e  mov     [rsp+98h+var_60], r14; unsigned __int16 **
0x140003d63  mov     [rsp+98h+var_68], r12; unsigned __int8 **
0x140003d68  mov     [rsp+98h+var_70], r13; unsigned int *
0x140003d6d  mov     qword ptr [rsp+98h+fAsynchronous], rax; unsigned __int16 **
0x140003d72  call    ?GetHostBindingInfo@CBindVmForRemoteManagementGuestThread@@IEAAJPEAHPEAPEAGPEAK12PEAPEAE1@Z; CBindVmForRemoteManagementGuestThread::GetHostBindingInfo(int *,ushort * *,ulong *,ushort * *,ulong *,uchar * *,ushort * *)
0x140003d77  mov     ebx, eax
0x140003d79  test    eax, eax
0x140003d7b  js      loc_140003F17
0x140003d81  mov     rcx, [rsp+98h+Handles+8]; hEvent
0x140003d86  call    cs:__imp_ResetEvent
0x140003d8c  test    eax, eax
0x140003d8e  jz      loc_140003E5B
0x140003d94  cmp     dword ptr [rdi], 0
0x140003d97  lea     rdx, aMultipointhost_4; "MultiPointHostSslCertificate-2"
0x140003d9e  jnz     loc_140003E4A
0x140003da4  lea     rcx, aCbindvmforremo_17; "CBindVmForRemoteManagementGuestThread::"...
0x140003dab  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140003db0  mov     r9, [rsp+98h+Handles+8]; hEvent
0x140003db5  mov     eax, 1
0x140003dba  mov     edx, eax; bWatchSubtree
0x140003dbc  mov     [rsp+98h+fAsynchronous], eax; fAsynchronous
0x140003dc0  mov     rcx, rsi; hKey
0x140003dc3  lea     r8d, [rax+3]; dwNotifyFilter
0x140003dc7  call    cs:__imp_RegNotifyChangeKeyValue
0x140003dcd  mov     ebx, eax
0x140003dcf  test    eax, eax
0x140003dd1  jz      loc_140003D1A
0x140003dd7  jle     short loc_140003DE2
0x140003dd9  movzx   ebx, ax
0x140003ddc  or      ebx, 80070000h
0x140003de2  lea     rbp, aCbraex; "CBRAEx"
0x140003de9  mov     dword ptr [rsp+98h+var_70], ebx; int
0x140003ded  lea     rsi, aCbindvmforremo_16; "CBindVmForRemoteManagementGuestThread::"...
0x140003df4  mov     r12d, 26Eh
0x140003dfa  lea     rdi, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x140003e01  mov     r9, rbp; unsigned __int16 *
0x140003e04  lea     r14, aLr0l; "lr == 0L"
0x140003e0b  mov     r8, rsi; unsigned __int16 *
0x140003e0e  mov     edx, r12d; unsigned int
0x140003e11  mov     qword ptr [rsp+98h+fAsynchronous], r14; unsigned __int16 *
0x140003e16  mov     rcx, rdi; unsigned __int16 *
0x140003e19  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140003e1e  call    cs:__imp_IsDebuggerPresent
0x140003e24  test    eax, eax
0x140003e26  jz      short loc_140003E39
0x140003e28  mov     dword ptr [rsp+98h+var_60], ebx
0x140003e2c  mov     r9d, r12d
0x140003e2f  mov     [rsp+98h+var_68], r14
0x140003e34  jmp     loc_140003EFE
0x140003e39  mov     dword ptr [rsp+98h+var_68], ebx
0x140003e3d  mov     r8d, r12d
0x140003e40  mov     [rsp+98h+var_70], r14
0x140003e45  jmp     loc_140003C33
0x140003e4a  lea     rcx, aCbindvmforremo_18; "CBindVmForRemoteManagementGuestThread::"...
0x140003e51  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140003e56  jmp     loc_140003F17
0x140003e5b  call    cs:__imp_GetLastError
0x140003e61  mov     ebx, eax
0x140003e63  test    eax, eax
0x140003e65  jle     short loc_140003E70
0x140003e67  movzx   ebx, ax
0x140003e6a  or      ebx, 80070000h
0x140003e70  lea     r12, aFsuccess; "fSuccess"
0x140003e77  mov     r14d, 268h
0x140003e7d  jmp     short loc_140003EAF
0x140003e7f  mov     dword ptr [rsp+98h+var_68], ebx
0x140003e83  mov     [rsp+98h+var_70], r12
0x140003e88  jmp     loc_140003C30
0x140003e8d  call    cs:__imp_GetLastError
0x140003e93  mov     ebx, eax
0x140003e95  test    eax, eax
0x140003e97  jle     short loc_140003EA2
0x140003e99  movzx   ebx, ax
0x140003e9c  or      ebx, 80070000h
0x140003ea2  lea     r12, a0; "0"
0x140003ea9  mov     r14d, 27Fh
0x140003eaf  mov     eax, 80004005h
0x140003eb4  lea     rbp, aCbraex; "CBRAEx"
0x140003ebb  test    ebx, ebx
0x140003ebd  lea     rsi, aCbindvmforremo_16; "CBindVmForRemoteManagementGuestThread::"...
0x140003ec4  lea     rdi, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x140003ecb  mov     r9, rbp; unsigned __int16 *
0x140003ece  cmovns  ebx, eax
0x140003ed1  mov     r8, rsi; unsigned __int16 *
0x140003ed4  mov     dword ptr [rsp+98h+var_70], ebx; int
0x140003ed8  mov     edx, r14d; unsigned int
0x140003edb  mov     rcx, rdi; unsigned __int16 *
0x140003ede  mov     qword ptr [rsp+98h+fAsynchronous], r12; unsigned __int16 *
0x140003ee3  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140003ee8  call    cs:__imp_IsDebuggerPresent
0x140003eee  test    eax, eax
0x140003ef0  jz      short loc_140003E7F
0x140003ef2  mov     dword ptr [rsp+98h+var_60], ebx
0x140003ef6  mov     r9d, r14d
0x140003ef9  mov     [rsp+98h+var_68], r12
0x140003efe  mov     ecx, r15d
0x140003f01  jmp     loc_140003C09
0x140003f06  lea     rcx, aCbindvmforremo_20; "CBindVmForRemoteManagementGuestThread::"...
0x140003f0d  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140003f12  mov     ebx, 80004004h
0x140003f17  mov     rcx, [rsp+98h+Handles+8]; hObject
0x140003f1c  lea     rax, [rcx-1]
0x140003f20  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140003f24  ja      short loc_140003F2C
0x140003f26  call    cs:__imp_CloseHandle
0x140003f2c  mov     eax, ebx
0x140003f2e  add     rsp, 58h
0x140003f32  pop     r15
0x140003f34  pop     r14
0x140003f36  pop     r13
0x140003f38  pop     r12
0x140003f3a  pop     rdi
0x140003f3b  pop     rsi
0x140003f3c  pop     rbp
0x140003f3d  pop     rbx
0x140003f3e  retn
```
