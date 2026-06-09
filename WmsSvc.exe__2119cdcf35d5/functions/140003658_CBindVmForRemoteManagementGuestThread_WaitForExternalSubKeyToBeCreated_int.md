# CBindVmForRemoteManagementGuestThread::WaitForExternalSubKeyToBeCreated(int *)

- ea: `0x140003658`
- end: `0x140003b3e`
- name: `?WaitForExternalSubKeyToBeCreated@CBindVmForRemoteManagementGuestThread@@IEAAJPEAH@Z`
- size: `1254`
- prototype: `__int64 __fastcall(CBindVmForRemoteManagementGuestThread *__hidden this, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003f48`

## callees

- `0x140003658`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1400036ae`
- `ADVAPI32!RegOpenKeyExW` at `0x1400038a8`
- `ADVAPI32!RegOpenKeyExW` at `0x1400036ae`
- `ADVAPI32!RegOpenKeyExW` at `0x1400038a8`
- `ADVAPI32!RegCloseKey` at `0x140003b06`
- `ADVAPI32!RegCloseKey` at `0x140003b1d`
- `ADVAPI32!RegCloseKey` at `0x140003b06`
- `ADVAPI32!RegCloseKey` at `0x140003b1d`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140003820`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x1400038f4`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140003820`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x1400038f4`
- `KERNEL32!CloseHandle` at `0x140003aef`
- `KERNEL32!CloseHandle` at `0x140003aef`
- `KERNEL32!ResetEvent` at `0x1400038bf`
- `KERNEL32!ResetEvent` at `0x1400038bf`
- `KERNEL32!WaitForMultipleObjects` at `0x140003871`
- `KERNEL32!WaitForMultipleObjects` at `0x140003871`
- `KERNEL32!CreateEventW` at `0x140003775`
- `KERNEL32!CreateEventW` at `0x140003775`
- `KERNEL32!GetLastError` at `0x140003788`
- `KERNEL32!GetLastError` at `0x140003979`
- `KERNEL32!GetLastError` at `0x140003a50`
- `KERNEL32!GetLastError` at `0x140003788`
- `KERNEL32!GetLastError` at `0x140003979`
- `KERNEL32!GetLastError` at `0x140003a50`
- `KERNEL32!IsDebuggerPresent` at `0x140003705`
- `KERNEL32!IsDebuggerPresent` at `0x1400037e3`
- `KERNEL32!IsDebuggerPresent` at `0x140003950`
- `KERNEL32!IsDebuggerPresent` at `0x1400039d4`
- `KERNEL32!IsDebuggerPresent` at `0x140003a31`
- `KERNEL32!IsDebuggerPresent` at `0x140003aab`
- `KERNEL32!IsDebuggerPresent` at `0x140003705`
- `KERNEL32!IsDebuggerPresent` at `0x1400037e3`
- `KERNEL32!IsDebuggerPresent` at `0x140003950`
- `KERNEL32!IsDebuggerPresent` at `0x1400039d4`
- `KERNEL32!IsDebuggerPresent` at `0x140003a31`
- `KERNEL32!IsDebuggerPresent` at `0x140003aab`

## string_xrefs

- `0x1400036e4`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x1400037b8`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x14000392d`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x1400039a9`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x140003a19`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x140003a80`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x1400036cf`: `CBindVmForRemoteManagementGuestThread::WaitForExternalSubKeyToBeCreated`
- `0x1400037ab`: `CBindVmForRemoteManagementGuestThread::WaitForExternalSubKeyToBeCreated`
- `0x140003923`: `CBindVmForRemoteManagementGuestThread::WaitForExternalSubKeyToBeCreated`
- `0x14000399c`: `CBindVmForRemoteManagementGuestThread::WaitForExternalSubKeyToBeCreated`
- `0x140003a0c`: `CBindVmForRemoteManagementGuestThread::WaitForExternalSubKeyToBeCreated`
- `0x140003a73`: `CBindVmForRemoteManagementGuestThread::WaitForExternalSubKeyToBeCreated`
- `0x1400037c2`: `rghEvents[ET_REGISTRY_CHANGE] != 0`
- `0x140003853`: `CBindVmForRemoteManagementGuestThread::WaitForExternalSubKeyToBeCreated - Starting wait for %s to be created\n`
- `0x140003ad0`: `CBindVmForRemoteManagementGuestThread::WaitForExternalSubKeyToBeCreated - Termination event occured\n`
- `0x1400038d1`: `CBindVmForRemoteManagementGuestThread::WaitForExternalSubKeyToBeCreated - Externals key got created\n`

## pseudocode

```c
__int64 __fastcall CBindVmForRemoteManagementGuestThread::WaitForExternalSubKeyToBeCreated(HANDLE *this, int *a2)
{
  LSTATUS v4; // eax
  int v5; // ebx
  unsigned int v6; // r12d
  __int64 v7; // r9
  __int64 v8; // r8
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v11; // r15d
  LSTATUS v12; // eax
  int v13; // edi
  DWORD v14; // eax
  LSTATUS v15; // eax
  signed int v16; // eax
  bool v17; // zf
  const unsigned __int16 *v18; // rax
  signed int v19; // eax
  const unsigned __int16 *v21; // [rsp+28h] [rbp-28h]
  const unsigned __int16 *v22; // [rsp+30h] [rbp-20h]
  int v23; // [rsp+30h] [rbp-20h]
  int v24; // [rsp+38h] [rbp-18h]
  HANDLE Handles[2]; // [rsp+40h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+40h] BYREF
  HKEY phkResult; // [rsp+98h] [rbp+48h] BYREF

  hKey = 0;
  phkResult = 0;
  *(_OWORD *)Handles = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Virtual Machine", 0, 0x10u, &hKey);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    v6 = 496;
LABEL_5:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
      v6,
      L"CBindVmForRemoteManagementGuestThread::WaitForExternalSubKeyToBeCreated",
      L"CBRAEx",
      L"lr == 0L",
      v5);
    if ( !IsDebuggerPresent() )
    {
      v8 = v6;
      goto LABEL_9;
    }
    v24 = v5;
    v7 = v6;
    v22 = L"lr == 0L";
    goto LABEL_7;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  Handles[1] = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v11 = 499;
    if ( v5 >= 0 )
      v5 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
      0x1F3u,
      L"CBindVmForRemoteManagementGuestThread::WaitForExternalSubKeyToBeCreated",
      L"CBRAEx",
      L"rghEvents[ET_REGISTRY_CHANGE] != 0",
      v5);
    if ( !IsDebuggerPresent() )
    {
      v23 = v5;
      v21 = L"rghEvents[ET_REGISTRY_CHANGE] != 0";
LABEL_19:
      v8 = v11;
      goto LABEL_10;
    }
    v24 = v5;
    v7 = 499;
    v22 = L"rghEvents[ET_REGISTRY_CHANGE] != 0";
    goto LABEL_7;
  }
  v12 = RegNotifyChangeKeyValue(hKey, 0, 1u, EventW, 1);
  v5 = v12;
  if ( v12 )
  {
    if ( v12 > 0 )
      v5 = (unsigned __int16)v12 | 0x80070000;
    v6 = 502;
    goto LABEL_5;
  }
  v13 = 0;
  Handles[0] = this[3];
  DEBUGMSG(
    L"CBindVmForRemoteManagementGuestThread::WaitForExternalSubKeyToBeCreated - Starting wait for %s to be created\n",
    L"SOFTWARE\\Microsoft\\Virtual Machine\\External");
  while ( 1 )
  {
    v14 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
    if ( !v14 )
    {
      DEBUGMSG(L"CBindVmForRemoteManagementGuestThread::WaitForExternalSubKeyToBeCreated - Termination event occured\n");
LABEL_56:
      v5 = 0;
      *a2 = v13;
      goto LABEL_57;
    }
    if ( v14 != 1 )
    {
      v19 = GetLastError();
      v5 = v19;
      if ( v19 > 0 )
        v5 = (unsigned __int16)v19 | 0x80070000;
      v11 = 543;
      if ( v5 >= 0 )
        v5 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
        0x21Fu,
        L"CBindVmForRemoteManagementGuestThread::WaitForExternalSubKeyToBeCreated",
        L"CBRAEx",
        L"0",
        v5);
      v17 = !IsDebuggerPresent();
      v18 = L"0";
LABEL_53:
      if ( !v17 )
      {
LABEL_54:
        v24 = v5;
        v7 = v11;
        v22 = v18;
LABEL_7:
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
          v7,
          L"CBindVmForRemoteManagementGuestThread::WaitForExternalSubKeyToBeCreated",
          L"CBRAEx",
          v22,
          v24,
          Handles[0]);
        goto LABEL_57;
      }
LABEL_47:
      v23 = v5;
      v21 = v18;
      goto LABEL_19;
    }
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Virtual Machine\\External", 0, 0x20019u, &phkResult);
    if ( (v5 & 0xFFFFFFFD) != 0 )
    {
      if ( v5 > 0 )
        v5 = (unsigned __int16)v5 | 0x80070000;
      v11 = 521;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
        0x209u,
        L"CBindVmForRemoteManagementGuestThread::WaitForExternalSubKeyToBeCreated",
        L"CBRAEx",
        L"lr == 0L || lr == 2L",
        v5);
      v17 = !IsDebuggerPresent();
      v18 = L"lr == 0L || lr == 2L";
      if ( !v17 )
        goto LABEL_54;
      goto LABEL_47;
    }
    if ( !ResetEvent(Handles[1]) )
    {
      v16 = GetLastError();
      v5 = v16;
      if ( v16 > 0 )
        v5 = (unsigned __int16)v16 | 0x80070000;
      v11 = 524;
      if ( v5 >= 0 )
        v5 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
        0x20Cu,
        L"CBindVmForRemoteManagementGuestThread::WaitForExternalSubKeyToBeCreated",
        L"CBRAEx",
        L"fSuccess",
        v5);
      v17 = !IsDebuggerPresent();
      v18 = L"fSuccess";
      goto LABEL_53;
    }
    if ( v5 )
      break;
    DEBUGMSG(L"CBindVmForRemoteManagementGuestThread::WaitForExternalSubKeyToBeCreated - Externals key got created\n");
    v13 = 1;
LABEL_32:
    if ( v13 )
      goto LABEL_56;
  }
  v15 = RegNotifyChangeKeyValue(hKey, 0, 1u, Handles[1], 1);
  v5 = v15;
  if ( !v15 )
    goto LABEL_32;
  if ( v15 > 0 )
    v5 = (unsigned __int16)v15 | 0x80070000;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
    0x217u,
    L"CBindVmForRemoteManagementGuestThread::WaitForExternalSubKeyToBeCreated",
    L"CBRAEx",
    L"lr == 0L",
    v5);
  if ( IsDebuggerPresent() )
  {
    v24 = v5;
    v7 = 535;
    v22 = L"lr == 0L";
    goto LABEL_7;
  }
  v8 = 535;
LABEL_9:
  v23 = v5;
  v21 = L"lr == 0L";
LABEL_10:
  DEBUGMSGBOX(
    L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
    L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
    v8,
    L"CBindVmForRemoteManagementGuestThread::WaitForExternalSubKeyToBeCreated",
    L"CBRAEx",
    v21,
    v23);
LABEL_57:
  if ( (unsigned __int64)Handles[1] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(Handles[1]);
    Handles[1] = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140003658  mov     [rsp-28h+arg_0], rbx
0x14000365d  mov     [rsp-28h+arg_8], rsi
0x140003662  push    rbp
0x140003663  push    rdi
0x140003664  push    r12
0x140003666  push    r14
0x140003668  push    r15
0x14000366a  mov     rbp, rsp
0x14000366d  sub     rsp, 50h
0x140003671  mov     r14, rdx
0x140003674  mov     [rbp+hKey], 0
0x14000367c  mov     rsi, rcx
0x14000367f  mov     [rbp+arg_18], 0
0x140003687  xorps   xmm0, xmm0
0x14000368a  lea     rax, [rbp+hKey]
0x14000368e  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Virtual Machine"
0x140003695  mov     [rsp+50h+phkResult], rax; phkResult
0x14000369a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400036a1  mov     r9d, 10h; samDesired
0x1400036a7  xor     r8d, r8d; ulOptions
0x1400036aa  movups  xmmword ptr [rbp+Handles], xmm0
0x1400036ae  call    cs:__imp_RegOpenKeyExW
0x1400036b4  mov     ebx, eax
0x1400036b6  test    eax, eax
0x1400036b8  jz      loc_140003766
0x1400036be  jle     short loc_1400036C9
0x1400036c0  movzx   ebx, ax
0x1400036c3  or      ebx, 80070000h
0x1400036c9  mov     r12d, 1F0h
0x1400036cf  lea     rsi, aCbindvmforremo_7; "CBindVmForRemoteManagementGuestThread::"...
0x1400036d6  mov     [rsp+50h+var_28], ebx; int
0x1400036da  lea     r14, aCbraex; "CBRAEx"
0x1400036e1  mov     r8, rsi; unsigned __int16 *
0x1400036e4  lea     rdi, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x1400036eb  mov     r9, r14; unsigned __int16 *
0x1400036ee  lea     r15, aLr0l; "lr == 0L"
0x1400036f5  mov     rcx, rdi; unsigned __int16 *
0x1400036f8  mov     edx, r12d; unsigned int
0x1400036fb  mov     [rsp+50h+phkResult], r15; unsigned __int16 *
0x140003700  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140003705  call    cs:__imp_IsDebuggerPresent
0x14000370b  test    eax, eax
0x14000370d  jz      short loc_14000373E
0x14000370f  mov     [rsp+50h+var_18], ebx
0x140003713  mov     r9d, r12d
0x140003716  mov     [rsp+50h+var_20], r15
0x14000371b  mov     ecx, 2; unsigned __int8
0x140003720  mov     qword ptr [rsp+50h+var_28], r14
0x140003725  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000372c  mov     r8, rdi
0x14000372f  mov     [rsp+50h+phkResult], rsi
0x140003734  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140003739  jmp     loc_140003AE1
0x14000373e  mov     r8d, r12d
0x140003741  mov     dword ptr [rsp+50h+var_20], ebx
0x140003745  mov     qword ptr [rsp+50h+var_28], r15
0x14000374a  mov     r9, rsi
0x14000374d  mov     [rsp+50h+phkResult], r14
0x140003752  mov     rdx, rdi
0x140003755  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000375c  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140003761  jmp     loc_140003AE1
0x140003766  xor     r9d, r9d; lpName
0x140003769  xor     r8d, r8d; bInitialState
0x14000376c  xor     ecx, ecx; lpEventAttributes
0x14000376e  lea     r15d, [r9+1]
0x140003772  mov     edx, r15d; bManualReset
0x140003775  call    cs:__imp_CreateEventW
0x14000377b  mov     [rbp+Handles+8], rax
0x14000377f  test    rax, rax
0x140003782  jnz     loc_14000380F
0x140003788  call    cs:__imp_GetLastError
0x14000378e  mov     ebx, eax
0x140003790  test    eax, eax
0x140003792  jle     short loc_14000379D
0x140003794  movzx   ebx, ax
0x140003797  or      ebx, 80070000h
0x14000379d  mov     eax, 80004005h
0x1400037a2  lea     r14, aCbraex; "CBRAEx"
0x1400037a9  test    ebx, ebx
0x1400037ab  lea     rsi, aCbindvmforremo_7; "CBindVmForRemoteManagementGuestThread::"...
0x1400037b2  mov     r15d, 1F3h
0x1400037b8  lea     rdi, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x1400037bf  cmovns  ebx, eax
0x1400037c2  lea     r12, aRgheventsEtReg; "rghEvents[ET_REGISTRY_CHANGE] != 0"
0x1400037c9  mov     [rsp+50h+var_28], ebx; int
0x1400037cd  mov     r9, r14; unsigned __int16 *
0x1400037d0  mov     r8, rsi; unsigned __int16 *
0x1400037d3  mov     [rsp+50h+phkResult], r12; unsigned __int16 *
0x1400037d8  mov     edx, r15d; unsigned int
0x1400037db  mov     rcx, rdi; unsigned __int16 *
0x1400037de  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400037e3  call    cs:__imp_IsDebuggerPresent
0x1400037e9  test    eax, eax
0x1400037eb  jz      short loc_1400037FE
0x1400037ed  mov     [rsp+50h+var_18], ebx
0x1400037f1  mov     r9d, r15d
0x1400037f4  mov     [rsp+50h+var_20], r12
0x1400037f9  jmp     loc_14000371B
0x1400037fe  mov     dword ptr [rsp+50h+var_20], ebx
0x140003802  mov     qword ptr [rsp+50h+var_28], r12
0x140003807  mov     r8d, r15d
0x14000380a  jmp     loc_14000374A
0x14000380f  mov     rcx, [rbp+hKey]; hKey
0x140003813  mov     r9, rax; hEvent
0x140003816  mov     r8d, r15d; dwNotifyFilter
0x140003819  mov     dword ptr [rsp+50h+phkResult], r15d; fAsynchronous
0x14000381e  xor     edx, edx; bWatchSubtree
0x140003820  call    cs:__imp_RegNotifyChangeKeyValue
0x140003826  mov     ebx, eax
0x140003828  test    eax, eax
0x14000382a  jz      short loc_140003842
0x14000382c  jle     short loc_140003837
0x14000382e  movzx   ebx, ax
0x140003831  or      ebx, 80070000h
0x140003837  mov     r12d, 1F6h
0x14000383d  jmp     loc_1400036CF
0x140003842  mov     rax, [rsi+18h]
0x140003846  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Virtual Machine\\E"...
0x14000384d  xor     edi, edi
0x14000384f  mov     [rbp+Handles], rax
0x140003853  lea     rcx, aCbindvmforremo_4; "CBindVmForRemoteManagementGuestThread::"...
0x14000385a  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000385f  lea     r12d, [rdi+2]
0x140003863  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x140003867  lea     rdx, [rbp+Handles]; lpHandles
0x14000386b  xor     r8d, r8d; bWaitAll
0x14000386e  mov     ecx, r12d; nCount
0x140003871  call    cs:__imp_WaitForMultipleObjects
0x140003877  test    eax, eax
0x140003879  jz      loc_140003AD0
0x14000387f  cmp     eax, r15d
0x140003882  jnz     loc_140003A50
0x140003888  lea     rax, [rbp+arg_18]
0x14000388c  mov     r9d, 20019h; samDesired
0x140003892  xor     r8d, r8d; ulOptions
0x140003895  mov     [rsp+50h+phkResult], rax; phkResult
0x14000389a  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Virtual Machine\\E"...
0x1400038a1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400038a8  call    cs:__imp_RegOpenKeyExW
0x1400038ae  mov     ebx, eax
0x1400038b0  test    eax, 0FFFFFFFDh
0x1400038b5  jnz     loc_1400039E8
0x1400038bb  mov     rcx, [rbp+Handles+8]; hEvent
0x1400038bf  call    cs:__imp_ResetEvent
0x1400038c5  test    eax, eax
0x1400038c7  jz      loc_140003979
0x1400038cd  test    ebx, ebx
0x1400038cf  jnz     short loc_1400038E2
0x1400038d1  lea     rcx, aCbindvmforremo_5; "CBindVmForRemoteManagementGuestThread::"...
0x1400038d8  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400038dd  mov     edi, r15d
0x1400038e0  jmp     short loc_140003900
0x1400038e2  mov     r9, [rbp+Handles+8]; hEvent
0x1400038e6  mov     r8d, r15d; dwNotifyFilter
0x1400038e9  mov     rcx, [rbp+hKey]; hKey
0x1400038ed  xor     edx, edx; bWatchSubtree
0x1400038ef  mov     dword ptr [rsp+50h+phkResult], r15d; fAsynchronous
0x1400038f4  call    cs:__imp_RegNotifyChangeKeyValue
0x1400038fa  mov     ebx, eax
0x1400038fc  test    eax, eax
0x1400038fe  jnz     short loc_14000390D
0x140003900  test    edi, edi
0x140003902  jnz     loc_140003ADC
0x140003908  jmp     loc_140003863
0x14000390d  jle     short loc_140003918
0x14000390f  movzx   ebx, ax
0x140003912  or      ebx, 80070000h
0x140003918  lea     r14, aCbraex; "CBRAEx"
0x14000391f  mov     [rsp+50h+var_28], ebx; int
0x140003923  lea     rsi, aCbindvmforremo_7; "CBindVmForRemoteManagementGuestThread::"...
0x14000392a  mov     r9, r14; unsigned __int16 *
0x14000392d  lea     rdi, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x140003934  mov     r8, rsi; unsigned __int16 *
0x140003937  lea     r15, aLr0l; "lr == 0L"
0x14000393e  mov     rcx, rdi; unsigned __int16 *
0x140003941  mov     edx, 217h; unsigned int
0x140003946  mov     [rsp+50h+phkResult], r15; unsigned __int16 *
0x14000394b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140003950  call    cs:__imp_IsDebuggerPresent
0x140003956  test    eax, eax
0x140003958  jz      short loc_14000396E
0x14000395a  mov     [rsp+50h+var_18], ebx
0x14000395e  mov     r9d, 217h
0x140003964  mov     [rsp+50h+var_20], r15
0x140003969  jmp     loc_140003AC8
0x14000396e  mov     r8d, 217h
0x140003974  jmp     loc_140003741
0x140003979  call    cs:__imp_GetLastError
0x14000397f  mov     ebx, eax
0x140003981  test    eax, eax
0x140003983  jle     short loc_14000398E
0x140003985  movzx   ebx, ax
0x140003988  or      ebx, 80070000h
0x14000398e  mov     eax, 80004005h
0x140003993  lea     r14, aCbraex; "CBRAEx"
0x14000399a  test    ebx, ebx
0x14000399c  lea     rsi, aCbindvmforremo_7; "CBindVmForRemoteManagementGuestThread::"...
0x1400039a3  mov     r15d, 20Ch
0x1400039a9  lea     rdi, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x1400039b0  cmovns  ebx, eax
0x1400039b3  mov     r9, r14; unsigned __int16 *
0x1400039b6  lea     rax, aFsuccess; "fSuccess"
0x1400039bd  mov     [rsp+50h+var_28], ebx; int
0x1400039c1  mov     r8, rsi; unsigned __int16 *
0x1400039c4  mov     [rsp+50h+phkResult], rax; unsigned __int16 *
0x1400039c9  mov     edx, r15d; unsigned int
0x1400039cc  mov     rcx, rdi; unsigned __int16 *
0x1400039cf  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400039d4  call    cs:__imp_IsDebuggerPresent
0x1400039da  test    eax, eax
0x1400039dc  lea     rax, aFsuccess; "fSuccess"
0x1400039e3  jmp     loc_140003ABA
0x1400039e8  test    ebx, ebx
0x1400039ea  jle     short loc_1400039F5
0x1400039ec  movzx   ebx, bx
0x1400039ef  or      ebx, 80070000h
0x1400039f5  lea     rax, aLr0lLr2l_0; "lr == 0L || lr == 2L"
0x1400039fc  mov     [rsp+50h+var_28], ebx; int
0x140003a00  lea     r14, aCbraex; "CBRAEx"
0x140003a07  mov     [rsp+50h+phkResult], rax; unsigned __int16 *
0x140003a0c  lea     rsi, aCbindvmforremo_7; "CBindVmForRemoteManagementGuestThread::"...
0x140003a13  mov     r15d, 209h
0x140003a19  lea     rdi, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x140003a20  mov     r9, r14; unsigned __int16 *
0x140003a23  mov     r8, rsi; unsigned __int16 *
0x140003a26  mov     edx, r15d; unsigned int
0x140003a29  mov     rcx, rdi; unsigned __int16 *
0x140003a2c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140003a31  call    cs:__imp_IsDebuggerPresent
0x140003a37  test    eax, eax
0x140003a39  lea     rax, aLr0lLr2l_0; "lr == 0L || lr == 2L"
0x140003a40  jnz     short loc_140003ABC
0x140003a42  mov     dword ptr [rsp+50h+var_20], ebx
0x140003a46  mov     qword ptr [rsp+50h+var_28], rax
0x140003a4b  jmp     loc_140003807
0x140003a50  call    cs:__imp_GetLastError
0x140003a56  mov     ebx, eax
0x140003a58  test    eax, eax
0x140003a5a  jle     short loc_140003A65
0x140003a5c  movzx   ebx, ax
0x140003a5f  or      ebx, 80070000h
0x140003a65  mov     eax, 80004005h
0x140003a6a  lea     r14, aCbraex; "CBRAEx"
0x140003a71  test    ebx, ebx
0x140003a73  lea     rsi, aCbindvmforremo_7; "CBindVmForRemoteManagementGuestThread::"...
0x140003a7a  mov     r15d, 21Fh
0x140003a80  lea     rdi, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x140003a87  cmovns  ebx, eax
0x140003a8a  mov     r9, r14; unsigned __int16 *
0x140003a8d  lea     rax, a0; "0"
0x140003a94  mov     [rsp+50h+var_28], ebx; int
0x140003a98  mov     r8, rsi; unsigned __int16 *
0x140003a9b  mov     [rsp+50h+phkResult], rax; unsigned __int16 *
0x140003aa0  mov     edx, r15d; unsigned int
0x140003aa3  mov     rcx, rdi; unsigned __int16 *
0x140003aa6  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140003aab  call    cs:__imp_IsDebuggerPresent
0x140003ab1  test    eax, eax
0x140003ab3  lea     rax, a0; "0"
0x140003aba  jz      short loc_140003A42
0x140003abc  mov     [rsp+50h+var_18], ebx
0x140003ac0  mov     r9d, r15d
0x140003ac3  mov     [rsp+50h+var_20], rax
0x140003ac8  mov     ecx, r12d
0x140003acb  jmp     loc_140003720
0x140003ad0  lea     rcx, aCbindvmforremo_10; "CBindVmForRemoteManagementGuestThread::"...
0x140003ad7  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140003adc  xor     ebx, ebx
0x140003ade  mov     [r14], edi
0x140003ae1  mov     rcx, [rbp+Handles+8]; hObject
0x140003ae5  lea     rax, [rcx-1]
0x140003ae9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140003aed  ja      short loc_140003AFD
0x140003aef  call    cs:__imp_CloseHandle
0x140003af5  mov     [rbp+Handles+8], 0
0x140003afd  mov     rcx, [rbp+arg_18]; hKey
0x140003b01  test    rcx, rcx
0x140003b04  jz      short loc_140003B14
0x140003b06  call    cs:__imp_RegCloseKey
0x140003b0c  mov     [rbp+arg_18], 0
0x140003b14  mov     rcx, [rbp+hKey]; hKey
0x140003b18  test    rcx, rcx
0x140003b1b  jz      short loc_140003B23
0x140003b1d  call    cs:__imp_RegCloseKey
0x140003b23  lea     r11, [rsp+50h+var_s0]
0x140003b28  mov     eax, ebx
0x140003b2a  mov     rbx, [r11+30h]
0x140003b2e  mov     rsi, [r11+38h]
0x140003b32  mov     rsp, r11
0x140003b35  pop     r15
0x140003b37  pop     r14
0x140003b39  pop     r12
0x140003b3b  pop     rdi
0x140003b3c  pop     rbp
0x140003b3d  retn
```
