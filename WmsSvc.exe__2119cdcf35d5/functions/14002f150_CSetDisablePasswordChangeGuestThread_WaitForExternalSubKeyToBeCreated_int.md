# CSetDisablePasswordChangeGuestThread::WaitForExternalSubKeyToBeCreated(int *)

- ea: `0x14002f150`
- end: `0x14002f62f`
- name: `?WaitForExternalSubKeyToBeCreated@CSetDisablePasswordChangeGuestThread@@IEAAJPEAH@Z`
- size: `1247`
- prototype: `__int64 __fastcall(CSetDisablePasswordChangeGuestThread *__hidden this, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002eaa0`

## callees

- `0x14002f150`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14002f1a6`
- `ADVAPI32!RegOpenKeyExW` at `0x14002f399`
- `ADVAPI32!RegOpenKeyExW` at `0x14002f1a6`
- `ADVAPI32!RegOpenKeyExW` at `0x14002f399`
- `ADVAPI32!RegCloseKey` at `0x14002f5f7`
- `ADVAPI32!RegCloseKey` at `0x14002f60e`
- `ADVAPI32!RegCloseKey` at `0x14002f5f7`
- `ADVAPI32!RegCloseKey` at `0x14002f60e`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x14002f318`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x14002f3e5`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x14002f318`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x14002f3e5`
- `KERNEL32!CloseHandle` at `0x14002f5e0`
- `KERNEL32!CloseHandle` at `0x14002f5e0`
- `KERNEL32!ResetEvent` at `0x14002f3b0`
- `KERNEL32!ResetEvent` at `0x14002f3b0`
- `KERNEL32!WaitForMultipleObjects` at `0x14002f362`
- `KERNEL32!WaitForMultipleObjects` at `0x14002f362`
- `KERNEL32!CreateEventW` at `0x14002f26d`
- `KERNEL32!CreateEventW` at `0x14002f26d`
- `KERNEL32!GetLastError` at `0x14002f280`
- `KERNEL32!GetLastError` at `0x14002f46a`
- `KERNEL32!GetLastError` at `0x14002f541`
- `KERNEL32!GetLastError` at `0x14002f280`
- `KERNEL32!GetLastError` at `0x14002f46a`
- `KERNEL32!GetLastError` at `0x14002f541`
- `KERNEL32!IsDebuggerPresent` at `0x14002f1fd`
- `KERNEL32!IsDebuggerPresent` at `0x14002f2db`
- `KERNEL32!IsDebuggerPresent` at `0x14002f441`
- `KERNEL32!IsDebuggerPresent` at `0x14002f4c5`
- `KERNEL32!IsDebuggerPresent` at `0x14002f522`
- `KERNEL32!IsDebuggerPresent` at `0x14002f59c`
- `KERNEL32!IsDebuggerPresent` at `0x14002f1fd`
- `KERNEL32!IsDebuggerPresent` at `0x14002f2db`
- `KERNEL32!IsDebuggerPresent` at `0x14002f441`
- `KERNEL32!IsDebuggerPresent` at `0x14002f4c5`
- `KERNEL32!IsDebuggerPresent` at `0x14002f522`
- `KERNEL32!IsDebuggerPresent` at `0x14002f59c`

## string_xrefs

- `0x14002f2ba`: `rghEvents[ET_REGISTRY_CHANGE] != 0`
- `0x14002f1dc`: `termsrv\wms\src\devices\wmssvc\setdisablepasswordchangeguestthread.cpp`
- `0x14002f2b0`: `termsrv\wms\src\devices\wmssvc\setdisablepasswordchangeguestthread.cpp`
- `0x14002f41e`: `termsrv\wms\src\devices\wmssvc\setdisablepasswordchangeguestthread.cpp`
- `0x14002f49a`: `termsrv\wms\src\devices\wmssvc\setdisablepasswordchangeguestthread.cpp`
- `0x14002f50a`: `termsrv\wms\src\devices\wmssvc\setdisablepasswordchangeguestthread.cpp`
- `0x14002f571`: `termsrv\wms\src\devices\wmssvc\setdisablepasswordchangeguestthread.cpp`
- `0x14002f1c7`: `CSetDisablePasswordChangeGuestThread::WaitForExternalSubKeyToBeCreated`
- `0x14002f2a3`: `CSetDisablePasswordChangeGuestThread::WaitForExternalSubKeyToBeCreated`
- `0x14002f414`: `CSetDisablePasswordChangeGuestThread::WaitForExternalSubKeyToBeCreated`
- `0x14002f48d`: `CSetDisablePasswordChangeGuestThread::WaitForExternalSubKeyToBeCreated`
- `0x14002f4fd`: `CSetDisablePasswordChangeGuestThread::WaitForExternalSubKeyToBeCreated`
- `0x14002f564`: `CSetDisablePasswordChangeGuestThread::WaitForExternalSubKeyToBeCreated`
- `0x14002f33e`: `CSetDisablePasswordChangeGuestThread::WaitForExternalSubKeyToBeCreated - Starting wait for HKLM\SOFTWARE\Microsoft\Virtual Machine\External to be created\n`
- `0x14002f5c1`: `CSetDisablePasswordChangeGuestThread::WaitForExternalSubKeyToBeCreated - Termination event occured\n`
- `0x14002f3c2`: `CSetDisablePasswordChangeGuestThread::WaitForExternalSubKeyToBeCreated - Externals key got created\n`

## pseudocode

```c
__int64 __fastcall CSetDisablePasswordChangeGuestThread::WaitForExternalSubKeyToBeCreated(HANDLE *this, int *a2)
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
    v6 = 111;
LABEL_5:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
      v6,
      L"CSetDisablePasswordChangeGuestThread::WaitForExternalSubKeyToBeCreated",
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
    v11 = 114;
    if ( v5 >= 0 )
      v5 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
      0x72u,
      L"CSetDisablePasswordChangeGuestThread::WaitForExternalSubKeyToBeCreated",
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
    v7 = 114;
    v22 = L"rghEvents[ET_REGISTRY_CHANGE] != 0";
    goto LABEL_7;
  }
  v12 = RegNotifyChangeKeyValue(hKey, 0, 1u, EventW, 1);
  v5 = v12;
  if ( v12 )
  {
    if ( v12 > 0 )
      v5 = (unsigned __int16)v12 | 0x80070000;
    v6 = 117;
    goto LABEL_5;
  }
  v13 = 0;
  Handles[0] = this[3];
  DEBUGMSG(
    L"CSetDisablePasswordChangeGuestThread::WaitForExternalSubKeyToBeCreated - Starting wait for HKLM\\SOFTWARE\\Microsoft"
     "\\Virtual Machine\\External to be created\n");
  while ( 1 )
  {
    v14 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
    if ( !v14 )
    {
      DEBUGMSG(L"CSetDisablePasswordChangeGuestThread::WaitForExternalSubKeyToBeCreated - Termination event occured\n");
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
      v11 = 158;
      if ( v5 >= 0 )
        v5 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
        0x9Eu,
        L"CSetDisablePasswordChangeGuestThread::WaitForExternalSubKeyToBeCreated",
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
          L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
          v7,
          L"CSetDisablePasswordChangeGuestThread::WaitForExternalSubKeyToBeCreated",
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
      v11 = 136;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
        0x88u,
        L"CSetDisablePasswordChangeGuestThread::WaitForExternalSubKeyToBeCreated",
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
      v11 = 139;
      if ( v5 >= 0 )
        v5 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
        0x8Bu,
        L"CSetDisablePasswordChangeGuestThread::WaitForExternalSubKeyToBeCreated",
        L"CBRAEx",
        L"fSuccess",
        v5);
      v17 = !IsDebuggerPresent();
      v18 = L"fSuccess";
      goto LABEL_53;
    }
    if ( v5 )
      break;
    DEBUGMSG(L"CSetDisablePasswordChangeGuestThread::WaitForExternalSubKeyToBeCreated - Externals key got created\n");
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
    L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
    0x96u,
    L"CSetDisablePasswordChangeGuestThread::WaitForExternalSubKeyToBeCreated",
    L"CBRAEx",
    L"lr == 0L",
    v5);
  if ( IsDebuggerPresent() )
  {
    v24 = v5;
    v7 = 150;
    v22 = L"lr == 0L";
    goto LABEL_7;
  }
  v8 = 150;
LABEL_9:
  v23 = v5;
  v21 = L"lr == 0L";
LABEL_10:
  DEBUGMSGBOX(
    L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
    L"termsrv\\wms\\src\\devices\\wmssvc\\setdisablepasswordchangeguestthread.cpp",
    v8,
    L"CSetDisablePasswordChangeGuestThread::WaitForExternalSubKeyToBeCreated",
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
0x14002f150  mov     [rsp-28h+arg_0], rbx
0x14002f155  mov     [rsp-28h+arg_8], rsi
0x14002f15a  push    rbp
0x14002f15b  push    rdi
0x14002f15c  push    r12
0x14002f15e  push    r14
0x14002f160  push    r15
0x14002f162  mov     rbp, rsp
0x14002f165  sub     rsp, 50h
0x14002f169  mov     r14, rdx
0x14002f16c  mov     [rbp+hKey], 0
0x14002f174  mov     rsi, rcx
0x14002f177  mov     [rbp+arg_18], 0
0x14002f17f  xorps   xmm0, xmm0
0x14002f182  lea     rax, [rbp+hKey]
0x14002f186  lea     rdx, aSoftwareMicros_14; "SOFTWARE\\Microsoft\\Virtual Machine"
0x14002f18d  mov     [rsp+50h+phkResult], rax; phkResult
0x14002f192  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002f199  mov     r9d, 10h; samDesired
0x14002f19f  xor     r8d, r8d; ulOptions
0x14002f1a2  movups  xmmword ptr [rbp+Handles], xmm0
0x14002f1a6  call    cs:__imp_RegOpenKeyExW
0x14002f1ac  mov     ebx, eax
0x14002f1ae  test    eax, eax
0x14002f1b0  jz      loc_14002F25E
0x14002f1b6  jle     short loc_14002F1C1
0x14002f1b8  movzx   ebx, ax
0x14002f1bb  or      ebx, 80070000h
0x14002f1c1  mov     r12d, 6Fh ; 'o'
0x14002f1c7  lea     rsi, aCsetdisablepas_4; "CSetDisablePasswordChangeGuestThread::W"...
0x14002f1ce  mov     [rsp+50h+var_28], ebx; int
0x14002f1d2  lea     r14, aCbraex; "CBRAEx"
0x14002f1d9  mov     r8, rsi; unsigned __int16 *
0x14002f1dc  lea     rdi, aTermsrvWmsSrcD_26; "termsrv\\wms\\src\\devices\\wmssvc\\set"...
0x14002f1e3  mov     r9, r14; unsigned __int16 *
0x14002f1e6  lea     r15, aLr0l; "lr == 0L"
0x14002f1ed  mov     rcx, rdi; unsigned __int16 *
0x14002f1f0  mov     edx, r12d; unsigned int
0x14002f1f3  mov     [rsp+50h+phkResult], r15; unsigned __int16 *
0x14002f1f8  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002f1fd  call    cs:__imp_IsDebuggerPresent
0x14002f203  test    eax, eax
0x14002f205  jz      short loc_14002F236
0x14002f207  mov     [rsp+50h+var_18], ebx
0x14002f20b  mov     r9d, r12d
0x14002f20e  mov     [rsp+50h+var_20], r15
0x14002f213  mov     ecx, 2; unsigned __int8
0x14002f218  mov     qword ptr [rsp+50h+var_28], r14
0x14002f21d  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14002f224  mov     r8, rdi
0x14002f227  mov     [rsp+50h+phkResult], rsi
0x14002f22c  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002f231  jmp     loc_14002F5D2
0x14002f236  mov     r8d, r12d
0x14002f239  mov     dword ptr [rsp+50h+var_20], ebx
0x14002f23d  mov     qword ptr [rsp+50h+var_28], r15
0x14002f242  mov     r9, rsi
0x14002f245  mov     [rsp+50h+phkResult], r14
0x14002f24a  mov     rdx, rdi
0x14002f24d  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002f254  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002f259  jmp     loc_14002F5D2
0x14002f25e  xor     r9d, r9d; lpName
0x14002f261  xor     r8d, r8d; bInitialState
0x14002f264  xor     ecx, ecx; lpEventAttributes
0x14002f266  lea     r15d, [r9+1]
0x14002f26a  mov     edx, r15d; bManualReset
0x14002f26d  call    cs:__imp_CreateEventW
0x14002f273  mov     [rbp+Handles+8], rax
0x14002f277  test    rax, rax
0x14002f27a  jnz     loc_14002F307
0x14002f280  call    cs:__imp_GetLastError
0x14002f286  mov     ebx, eax
0x14002f288  test    eax, eax
0x14002f28a  jle     short loc_14002F295
0x14002f28c  movzx   ebx, ax
0x14002f28f  or      ebx, 80070000h
0x14002f295  mov     eax, 80004005h
0x14002f29a  lea     r14, aCbraex; "CBRAEx"
0x14002f2a1  test    ebx, ebx
0x14002f2a3  lea     rsi, aCsetdisablepas_4; "CSetDisablePasswordChangeGuestThread::W"...
0x14002f2aa  mov     r15d, 72h ; 'r'
0x14002f2b0  lea     rdi, aTermsrvWmsSrcD_26; "termsrv\\wms\\src\\devices\\wmssvc\\set"...
0x14002f2b7  cmovns  ebx, eax
0x14002f2ba  lea     r12, aRgheventsEtReg; "rghEvents[ET_REGISTRY_CHANGE] != 0"
0x14002f2c1  mov     [rsp+50h+var_28], ebx; int
0x14002f2c5  mov     r9, r14; unsigned __int16 *
0x14002f2c8  mov     r8, rsi; unsigned __int16 *
0x14002f2cb  mov     [rsp+50h+phkResult], r12; unsigned __int16 *
0x14002f2d0  mov     edx, r15d; unsigned int
0x14002f2d3  mov     rcx, rdi; unsigned __int16 *
0x14002f2d6  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002f2db  call    cs:__imp_IsDebuggerPresent
0x14002f2e1  test    eax, eax
0x14002f2e3  jz      short loc_14002F2F6
0x14002f2e5  mov     [rsp+50h+var_18], ebx
0x14002f2e9  mov     r9d, r15d
0x14002f2ec  mov     [rsp+50h+var_20], r12
0x14002f2f1  jmp     loc_14002F213
0x14002f2f6  mov     dword ptr [rsp+50h+var_20], ebx
0x14002f2fa  mov     qword ptr [rsp+50h+var_28], r12
0x14002f2ff  mov     r8d, r15d
0x14002f302  jmp     loc_14002F242
0x14002f307  mov     rcx, [rbp+hKey]; hKey
0x14002f30b  mov     r9, rax; hEvent
0x14002f30e  mov     r8d, r15d; dwNotifyFilter
0x14002f311  mov     dword ptr [rsp+50h+phkResult], r15d; fAsynchronous
0x14002f316  xor     edx, edx; bWatchSubtree
0x14002f318  call    cs:__imp_RegNotifyChangeKeyValue
0x14002f31e  mov     ebx, eax
0x14002f320  test    eax, eax
0x14002f322  jz      short loc_14002F33A
0x14002f324  jle     short loc_14002F32F
0x14002f326  movzx   ebx, ax
0x14002f329  or      ebx, 80070000h
0x14002f32f  mov     r12d, 75h ; 'u'
0x14002f335  jmp     loc_14002F1C7
0x14002f33a  mov     rax, [rsi+18h]
0x14002f33e  lea     rcx, aCsetdisablepas_18; "CSetDisablePasswordChangeGuestThread::W"...
0x14002f345  xor     edi, edi
0x14002f347  mov     [rbp+Handles], rax
0x14002f34b  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002f350  lea     r12d, [rdi+2]
0x14002f354  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x14002f358  lea     rdx, [rbp+Handles]; lpHandles
0x14002f35c  xor     r8d, r8d; bWaitAll
0x14002f35f  mov     ecx, r12d; nCount
0x14002f362  call    cs:__imp_WaitForMultipleObjects
0x14002f368  test    eax, eax
0x14002f36a  jz      loc_14002F5C1
0x14002f370  cmp     eax, r15d
0x14002f373  jnz     loc_14002F541
0x14002f379  lea     rax, [rbp+arg_18]
0x14002f37d  mov     r9d, 20019h; samDesired
0x14002f383  xor     r8d, r8d; ulOptions
0x14002f386  mov     [rsp+50h+phkResult], rax; phkResult
0x14002f38b  lea     rdx, aSoftwareMicros_13; "SOFTWARE\\Microsoft\\Virtual Machine\\E"...
0x14002f392  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002f399  call    cs:__imp_RegOpenKeyExW
0x14002f39f  mov     ebx, eax
0x14002f3a1  test    eax, 0FFFFFFFDh
0x14002f3a6  jnz     loc_14002F4D9
0x14002f3ac  mov     rcx, [rbp+Handles+8]; hEvent
0x14002f3b0  call    cs:__imp_ResetEvent
0x14002f3b6  test    eax, eax
0x14002f3b8  jz      loc_14002F46A
0x14002f3be  test    ebx, ebx
0x14002f3c0  jnz     short loc_14002F3D3
0x14002f3c2  lea     rcx, aCsetdisablepas_1; "CSetDisablePasswordChangeGuestThread::W"...
0x14002f3c9  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002f3ce  mov     edi, r15d
0x14002f3d1  jmp     short loc_14002F3F1
0x14002f3d3  mov     r9, [rbp+Handles+8]; hEvent
0x14002f3d7  mov     r8d, r15d; dwNotifyFilter
0x14002f3da  mov     rcx, [rbp+hKey]; hKey
0x14002f3de  xor     edx, edx; bWatchSubtree
0x14002f3e0  mov     dword ptr [rsp+50h+phkResult], r15d; fAsynchronous
0x14002f3e5  call    cs:__imp_RegNotifyChangeKeyValue
0x14002f3eb  mov     ebx, eax
0x14002f3ed  test    eax, eax
0x14002f3ef  jnz     short loc_14002F3FE
0x14002f3f1  test    edi, edi
0x14002f3f3  jnz     loc_14002F5CD
0x14002f3f9  jmp     loc_14002F354
0x14002f3fe  jle     short loc_14002F409
0x14002f400  movzx   ebx, ax
0x14002f403  or      ebx, 80070000h
0x14002f409  lea     r14, aCbraex; "CBRAEx"
0x14002f410  mov     [rsp+50h+var_28], ebx; int
0x14002f414  lea     rsi, aCsetdisablepas_4; "CSetDisablePasswordChangeGuestThread::W"...
0x14002f41b  mov     r9, r14; unsigned __int16 *
0x14002f41e  lea     rdi, aTermsrvWmsSrcD_26; "termsrv\\wms\\src\\devices\\wmssvc\\set"...
0x14002f425  mov     r8, rsi; unsigned __int16 *
0x14002f428  lea     r15, aLr0l; "lr == 0L"
0x14002f42f  mov     rcx, rdi; unsigned __int16 *
0x14002f432  mov     edx, 96h; unsigned int
0x14002f437  mov     [rsp+50h+phkResult], r15; unsigned __int16 *
0x14002f43c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002f441  call    cs:__imp_IsDebuggerPresent
0x14002f447  test    eax, eax
0x14002f449  jz      short loc_14002F45F
0x14002f44b  mov     [rsp+50h+var_18], ebx
0x14002f44f  mov     r9d, 96h
0x14002f455  mov     [rsp+50h+var_20], r15
0x14002f45a  jmp     loc_14002F5B9
0x14002f45f  mov     r8d, 96h
0x14002f465  jmp     loc_14002F239
0x14002f46a  call    cs:__imp_GetLastError
0x14002f470  mov     ebx, eax
0x14002f472  test    eax, eax
0x14002f474  jle     short loc_14002F47F
0x14002f476  movzx   ebx, ax
0x14002f479  or      ebx, 80070000h
0x14002f47f  mov     eax, 80004005h
0x14002f484  lea     r14, aCbraex; "CBRAEx"
0x14002f48b  test    ebx, ebx
0x14002f48d  lea     rsi, aCsetdisablepas_4; "CSetDisablePasswordChangeGuestThread::W"...
0x14002f494  mov     r15d, 8Bh
0x14002f49a  lea     rdi, aTermsrvWmsSrcD_26; "termsrv\\wms\\src\\devices\\wmssvc\\set"...
0x14002f4a1  cmovns  ebx, eax
0x14002f4a4  mov     r9, r14; unsigned __int16 *
0x14002f4a7  lea     rax, aFsuccess; "fSuccess"
0x14002f4ae  mov     [rsp+50h+var_28], ebx; int
0x14002f4b2  mov     r8, rsi; unsigned __int16 *
0x14002f4b5  mov     [rsp+50h+phkResult], rax; unsigned __int16 *
0x14002f4ba  mov     edx, r15d; unsigned int
0x14002f4bd  mov     rcx, rdi; unsigned __int16 *
0x14002f4c0  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002f4c5  call    cs:__imp_IsDebuggerPresent
0x14002f4cb  test    eax, eax
0x14002f4cd  lea     rax, aFsuccess; "fSuccess"
0x14002f4d4  jmp     loc_14002F5AB
0x14002f4d9  test    ebx, ebx
0x14002f4db  jle     short loc_14002F4E6
0x14002f4dd  movzx   ebx, bx
0x14002f4e0  or      ebx, 80070000h
0x14002f4e6  lea     rax, aLr0lLr2l_0; "lr == 0L || lr == 2L"
0x14002f4ed  mov     [rsp+50h+var_28], ebx; int
0x14002f4f1  lea     r14, aCbraex; "CBRAEx"
0x14002f4f8  mov     [rsp+50h+phkResult], rax; unsigned __int16 *
0x14002f4fd  lea     rsi, aCsetdisablepas_4; "CSetDisablePasswordChangeGuestThread::W"...
0x14002f504  mov     r15d, 88h
0x14002f50a  lea     rdi, aTermsrvWmsSrcD_26; "termsrv\\wms\\src\\devices\\wmssvc\\set"...
0x14002f511  mov     r9, r14; unsigned __int16 *
0x14002f514  mov     r8, rsi; unsigned __int16 *
0x14002f517  mov     edx, r15d; unsigned int
0x14002f51a  mov     rcx, rdi; unsigned __int16 *
0x14002f51d  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002f522  call    cs:__imp_IsDebuggerPresent
0x14002f528  test    eax, eax
0x14002f52a  lea     rax, aLr0lLr2l_0; "lr == 0L || lr == 2L"
0x14002f531  jnz     short loc_14002F5AD
0x14002f533  mov     dword ptr [rsp+50h+var_20], ebx
0x14002f537  mov     qword ptr [rsp+50h+var_28], rax
0x14002f53c  jmp     loc_14002F2FF
0x14002f541  call    cs:__imp_GetLastError
0x14002f547  mov     ebx, eax
0x14002f549  test    eax, eax
0x14002f54b  jle     short loc_14002F556
0x14002f54d  movzx   ebx, ax
0x14002f550  or      ebx, 80070000h
0x14002f556  mov     eax, 80004005h
0x14002f55b  lea     r14, aCbraex; "CBRAEx"
0x14002f562  test    ebx, ebx
0x14002f564  lea     rsi, aCsetdisablepas_4; "CSetDisablePasswordChangeGuestThread::W"...
0x14002f56b  mov     r15d, 9Eh
0x14002f571  lea     rdi, aTermsrvWmsSrcD_26; "termsrv\\wms\\src\\devices\\wmssvc\\set"...
0x14002f578  cmovns  ebx, eax
0x14002f57b  mov     r9, r14; unsigned __int16 *
0x14002f57e  lea     rax, a0; "0"
0x14002f585  mov     [rsp+50h+var_28], ebx; int
0x14002f589  mov     r8, rsi; unsigned __int16 *
0x14002f58c  mov     [rsp+50h+phkResult], rax; unsigned __int16 *
0x14002f591  mov     edx, r15d; unsigned int
0x14002f594  mov     rcx, rdi; unsigned __int16 *
0x14002f597  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002f59c  call    cs:__imp_IsDebuggerPresent
0x14002f5a2  test    eax, eax
0x14002f5a4  lea     rax, a0; "0"
0x14002f5ab  jz      short loc_14002F533
0x14002f5ad  mov     [rsp+50h+var_18], ebx
0x14002f5b1  mov     r9d, r15d
0x14002f5b4  mov     [rsp+50h+var_20], rax
0x14002f5b9  mov     ecx, r12d
0x14002f5bc  jmp     loc_14002F218
0x14002f5c1  lea     rcx, aCsetdisablepas_8; "CSetDisablePasswordChangeGuestThread::W"...
0x14002f5c8  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002f5cd  xor     ebx, ebx
0x14002f5cf  mov     [r14], edi
0x14002f5d2  mov     rcx, [rbp+Handles+8]; hObject
0x14002f5d6  lea     rax, [rcx-1]
0x14002f5da  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002f5de  ja      short loc_14002F5EE
0x14002f5e0  call    cs:__imp_CloseHandle
0x14002f5e6  mov     [rbp+Handles+8], 0
0x14002f5ee  mov     rcx, [rbp+arg_18]; hKey
0x14002f5f2  test    rcx, rcx
0x14002f5f5  jz      short loc_14002F605
0x14002f5f7  call    cs:__imp_RegCloseKey
0x14002f5fd  mov     [rbp+arg_18], 0
0x14002f605  mov     rcx, [rbp+hKey]; hKey
0x14002f609  test    rcx, rcx
0x14002f60c  jz      short loc_14002F614
0x14002f60e  call    cs:__imp_RegCloseKey
0x14002f614  lea     r11, [rsp+50h+var_s0]
0x14002f619  mov     eax, ebx
0x14002f61b  mov     rbx, [r11+30h]
0x14002f61f  mov     rsi, [r11+38h]
0x14002f623  mov     rsp, r11
0x14002f626  pop     r15
0x14002f628  pop     r14
0x14002f62a  pop     r12
0x14002f62c  pop     rdi
0x14002f62d  pop     rbp
0x14002f62e  retn
```
