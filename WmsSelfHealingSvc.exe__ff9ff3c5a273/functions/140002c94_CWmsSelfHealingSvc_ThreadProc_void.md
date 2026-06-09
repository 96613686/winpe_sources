# CWmsSelfHealingSvc::ThreadProc(void)

- ea: `0x140002c94`
- end: `0x140003006`
- name: `?ThreadProc@CWmsSelfHealingSvc@@AEAAJXZ`
- size: `882`
- prototype: `__int64 __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140003150`

## callees

- `0x140001cb8`
- `0x1400029e8`
- `0x140002c94`
- `0x1400036a0`
- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x1400058e8`
- `0x140009344`
- `0x14000c010`

## import_xrefs

- `KERNEL32!WaitForMultipleObjects` at `0x140002f28`
- `KERNEL32!WaitForMultipleObjects` at `0x140002f28`
- `KERNEL32!ResetEvent` at `0x140002f71`
- `KERNEL32!ResetEvent` at `0x140002f71`
- `KERNEL32!WaitForSingleObject` at `0x140002eb8`
- `KERNEL32!WaitForSingleObject` at `0x140002eb8`
- `KERNEL32!SetEvent` at `0x140002fe7`
- `KERNEL32!SetEvent` at `0x140002fe7`
- `KERNEL32!IsDebuggerPresent` at `0x140002cf6`
- `KERNEL32!IsDebuggerPresent` at `0x140002e18`
- `KERNEL32!IsDebuggerPresent` at `0x140002cf6`
- `KERNEL32!IsDebuggerPresent` at `0x140002e18`
- `ole32!CoInitializeEx` at `0x140002cb1`
- `ole32!CoInitializeEx` at `0x140002cb1`
- `ole32!CoUninitialize` at `0x140002ff2`
- `ole32!CoUninitialize` at `0x140002ff2`
- `ntdll!NtQueryWnfStateData` at `0x140002dcc`
- `ntdll!NtQueryWnfStateData` at `0x140002dcc`

## string_xrefs

- `0x140002f77`: `CWmsSelfHealingSvc::ShutDown - reset service ready event\n`
- `0x140002cc5`: `CWmsSelfHealingSvc::ThreadProc`
- `0x140002d79`: `CWmsSelfHealingSvc::ThreadProc - Waiting for WNF_DEP_OOBE_COMPLETE to be set\n`
- `0x140002f4c`: `CWmsSelfHealingSvc::ThreadProc - Service was shutdown while waiting for WNF_DEP_OOBE_COMPLETE to be set\n`
- `0x140002ee0`: `CWmsSelfHealingSvc::ThreadProc - WNF_DEP_OOBE_COMPLETE was set\n`
- `0x140002ddc`: `CWmsSelfHealingSvc::IsMachineOobeCompleted - NtQueryWnfStateData failed, status = %x\n`
- `0x140002e00`: `CWmsSelfHealingSvc::IsMachineOobeCompleted`
- `0x140002e55`: `CWmsSelfHealingSvc::IsMachineOobeCompleted`
- `0x140002e6d`: `CWmsSelfHealingSvc::IsMachineOobeCompleted`

## pseudocode

```c
__int64 __fastcall CWmsSelfHealingSvc::ThreadProc(HANDLE *this)
{
  HRESULT v2; // eax
  HRESULT v3; // edi
  int v4; // r14d
  int v5; // eax
  DWORD v6; // eax
  CWmsSelfHealingSvc *v7; // rcx
  unsigned int v8; // edx
  const unsigned __int16 *v9; // rcx
  unsigned int v10; // r8d
  HANDLE v11; // rcx
  int v12; // edi
  HANDLE v13; // rcx
  HANDLE v14; // rcx
  __int64 v16; // [rsp+30h] [rbp-20h]
  __int64 v17; // [rsp+38h] [rbp-18h]
  HANDLE Handles[2]; // [rsp+40h] [rbp-10h] BYREF
  int v19; // [rsp+80h] [rbp+30h] BYREF
  int v20; // [rsp+88h] [rbp+38h] BYREF
  int v21; // [rsp+90h] [rbp+40h] BYREF

  *(_OWORD *)Handles = 0;
  v2 = CoInitializeEx(0, 0);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 0;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
      0x22Eu,
      L"CWmsSelfHealingSvc::ThreadProc",
      L"CHRA",
      L"hr",
      v2);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
        558,
        L"CWmsSelfHealingSvc::ThreadProc",
        L"CHRA",
        L"hr",
        v3,
        Handles[0],
        Handles[1]);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
        558,
        L"CWmsSelfHealingSvc::ThreadProc",
        L"CHRA",
        L"hr",
        v3);
    goto LABEL_20;
  }
  v4 = 1;
  DEBUGMSG(L"CWmsSelfHealingSvc::ThreadProc - Waiting for WNF_DEP_OOBE_COMPLETE to be set\n");
  while ( 1 )
  {
    v20 = 0;
    v19 = 4;
    v21 = 0;
    v5 = NtQueryWnfStateData(WNF_DEP_OOBE_COMPLETE, 0, 0, &v21, &v20, &v19);
    if ( v5 < 0 )
    {
      DEBUGMSG(
        L"CWmsSelfHealingSvc::IsMachineOobeCompleted - NtQueryWnfStateData failed, status = %x\n",
        (unsigned int)v5);
      LOGASSERTHR(
        L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
        0x28Cu,
        L"CWmsSelfHealingSvc::IsMachineOobeCompleted",
        L"CBRA",
        L"(((NTSTATUS)(status)) >= 0)",
        -2147467259);
      if ( IsDebuggerPresent() )
      {
        LODWORD(v17) = -2147467259;
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
          652,
          L"CWmsSelfHealingSvc::IsMachineOobeCompleted",
          L"CBRA",
          L"(((NTSTATUS)(status)) >= 0)",
          v17,
          Handles[0],
          Handles[1]);
      }
      else
      {
        LODWORD(v16) = -2147467259;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
          652,
          L"CWmsSelfHealingSvc::IsMachineOobeCompleted",
          L"CBRA",
          L"(((NTSTATUS)(status)) >= 0)",
          v16);
      }
      goto LABEL_12;
    }
    if ( v19 == 4 && v20 == 1 )
      break;
LABEL_12:
    v6 = WaitForSingleObject(this[111], 0x1F4u);
    if ( !v6 )
    {
      DEBUGMSG(L"CWmsSelfHealingSvc::ThreadProc - Service was shutdown while waiting for WNF_DEP_OOBE_COMPLETE to be set\n");
      goto LABEL_20;
    }
    if ( v6 != 258 )
      goto LABEL_20;
    CNTService::SetStatus((CNTService *)this, 2u);
  }
  DEBUGMSG(L"CWmsSelfHealingSvc::ThreadProc - WNF_DEP_OOBE_COMPLETE was set\n");
  CNTService::SetStatus((CNTService *)this, 4u);
  if ( (int)CWmsSelfHealingSvc::StartUp(this) >= 0 )
  {
    Handles[0] = this[111];
    Handles[1] = this[108];
    if ( WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF) == 1
      && CWmsSelfHealingSvc::DisplayStatusMessage(v7, 0x514u) >= 0 )
    {
      Reboot(v9, v8, v10);
    }
  }
LABEL_20:
  CNTService::SetStatus((CNTService *)this, 3u);
  v11 = this[107];
  if ( v11 )
  {
    ResetEvent(v11);
    DEBUGMSG(L"CWmsSelfHealingSvc::ShutDown - reset service ready event\n");
  }
  v12 = 0;
  DEBUGMSG(L"CWmsSelfHealingSvc::StopMonitoring\n");
  v13 = this[109];
  if ( !v13 || (v12 = (*(__int64 (__fastcall **)(HANDLE))(*(_QWORD *)v13 + 32LL))(v13), v12 >= 0) )
  {
    v14 = this[109];
    if ( v14 )
    {
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v14 + 16LL))(v14);
      this[109] = 0;
    }
  }
  DEBUGMSG(L"CWmsSelfHealingSvc::StopMonitoring - hr = 0x%08X\n", (unsigned int)v12);
  SetEvent(this[106]);
  if ( v4 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x140002c94  push    rbp
0x140002c96  push    rbx
0x140002c97  push    rdi
0x140002c98  push    r13
0x140002c9a  push    r14
0x140002c9c  mov     rbp, rsp
0x140002c9f  sub     rsp, 50h
0x140002ca3  mov     rbx, rcx
0x140002ca6  xorps   xmm0, xmm0
0x140002ca9  xor     ecx, ecx; pvReserved
0x140002cab  xor     edx, edx; dwCoInit
0x140002cad  movups  xmmword ptr [rbp+Handles], xmm0
0x140002cb1  call    cs:__imp_CoInitializeEx
0x140002cb7  mov     edi, eax
0x140002cb9  test    eax, eax
0x140002cbb  jns     loc_140002D79
0x140002cc1  mov     [rsp+50h+var_28], eax; int
0x140002cc5  lea     r13, aCwmsselfhealin_10; "CWmsSelfHealingSvc::ThreadProc"
0x140002ccc  lea     rax, aHr; "hr"
0x140002cd3  mov     r8, r13; unsigned __int16 *
0x140002cd6  lea     r9, aChra; "CHRA"
0x140002cdd  mov     [rsp+50h+var_30], rax; unsigned __int16 *
0x140002ce2  mov     edx, 22Eh; unsigned int
0x140002ce7  lea     rcx, aTermsrvWmsSrcP; "termsrv\\wms\\src\\platform\\wmsselfhea"...
0x140002cee  xor     r14d, r14d
0x140002cf1  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140002cf6  call    cs:__imp_IsDebuggerPresent
0x140002cfc  test    eax, eax
0x140002cfe  lea     rax, aHr; "hr"
0x140002d05  jz      short loc_140002D43
0x140002d07  mov     dword ptr [rsp+50h+var_18], edi
0x140002d0b  lea     r8, aTermsrvWmsSrcP; "termsrv\\wms\\src\\platform\\wmsselfhea"...
0x140002d12  mov     [rsp+50h+var_20], rax
0x140002d17  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140002d1e  lea     rax, aChra; "CHRA"
0x140002d25  mov     r9d, 22Eh
0x140002d2b  mov     qword ptr [rsp+50h+var_28], rax
0x140002d30  lea     ecx, [r14+2]; unsigned __int8
0x140002d34  mov     [rsp+50h+var_30], r13
0x140002d39  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140002d3e  jmp     loc_140002F58
0x140002d43  mov     dword ptr [rsp+50h+var_20], edi
0x140002d47  lea     rdx, aTermsrvWmsSrcP; "termsrv\\wms\\src\\platform\\wmsselfhea"...
0x140002d4e  mov     qword ptr [rsp+50h+var_28], rax
0x140002d53  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140002d5a  lea     rax, aChra; "CHRA"
0x140002d61  mov     r9, r13
0x140002d64  mov     r8d, 22Eh
0x140002d6a  mov     [rsp+50h+var_30], rax
0x140002d6f  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140002d74  jmp     loc_140002F58
0x140002d79  lea     rcx, aCwmsselfhealin_29; "CWmsSelfHealingSvc::ThreadProc - Waitin"...
0x140002d80  mov     r14d, 1
0x140002d86  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140002d8b  lea     edi, [r14+1]
0x140002d8f  mov     r13d, 80004005h
0x140002d95  lea     rax, [rbp+arg_0]
0x140002d99  mov     [rbp+arg_8], 0
0x140002da0  mov     qword ptr [rsp+50h+var_28], rax
0x140002da5  lea     r9, [rbp+arg_10]
0x140002da9  lea     rax, [rbp+arg_8]
0x140002dad  mov     [rbp+arg_0], 4
0x140002db4  xor     r8d, r8d
0x140002db7  mov     [rsp+50h+var_30], rax
0x140002dbc  xor     edx, edx
0x140002dbe  mov     [rbp+arg_10], 0
0x140002dc5  lea     rcx, WNF_DEP_OOBE_COMPLETE
0x140002dcc  call    cs:__imp_NtQueryWnfStateData
0x140002dd2  test    eax, eax
0x140002dd4  jns     loc_140002EA0
0x140002dda  mov     edx, eax
0x140002ddc  lea     rcx, aCwmsselfhealin_18; "CWmsSelfHealingSvc::IsMachineOobeComple"...
0x140002de3  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140002de8  lea     rax, aNtstatusStatus; "(((NTSTATUS)(status)) >= 0)"
0x140002def  mov     [rsp+50h+var_28], r13d; int
0x140002df4  lea     r9, aCbra; "CBRA"
0x140002dfb  mov     [rsp+50h+var_30], rax; unsigned __int16 *
0x140002e00  lea     r8, aCwmsselfhealin_2; "CWmsSelfHealingSvc::IsMachineOobeComple"...
0x140002e07  mov     edx, 28Ch; unsigned int
0x140002e0c  lea     rcx, aTermsrvWmsSrcP; "termsrv\\wms\\src\\platform\\wmsselfhea"...
0x140002e13  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140002e18  call    cs:__imp_IsDebuggerPresent
0x140002e1e  test    eax, eax
0x140002e20  lea     rax, aNtstatusStatus; "(((NTSTATUS)(status)) >= 0)"
0x140002e27  jz      short loc_140002E68
0x140002e29  mov     dword ptr [rsp+50h+var_18], r13d
0x140002e2e  lea     r8, aTermsrvWmsSrcP; "termsrv\\wms\\src\\platform\\wmsselfhea"...
0x140002e35  mov     [rsp+50h+var_20], rax
0x140002e3a  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140002e41  lea     rax, aCbra; "CBRA"
0x140002e48  mov     r9d, 28Ch
0x140002e4e  mov     qword ptr [rsp+50h+var_28], rax
0x140002e53  mov     ecx, edi; unsigned __int8
0x140002e55  lea     rax, aCwmsselfhealin_2; "CWmsSelfHealingSvc::IsMachineOobeComple"...
0x140002e5c  mov     [rsp+50h+var_30], rax
0x140002e61  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140002e66  jmp     short loc_140002EAC
0x140002e68  mov     dword ptr [rsp+50h+var_20], r13d
0x140002e6d  lea     r9, aCwmsselfhealin_2; "CWmsSelfHealingSvc::IsMachineOobeComple"...
0x140002e74  mov     qword ptr [rsp+50h+var_28], rax
0x140002e79  lea     rdx, aTermsrvWmsSrcP; "termsrv\\wms\\src\\platform\\wmsselfhea"...
0x140002e80  lea     rax, aCbra; "CBRA"
0x140002e87  mov     r8d, 28Ch
0x140002e8d  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140002e94  mov     [rsp+50h+var_30], rax
0x140002e99  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140002e9e  jmp     short loc_140002EAC
0x140002ea0  cmp     [rbp+arg_0], 4
0x140002ea4  jnz     short loc_140002EAC
0x140002ea6  cmp     [rbp+arg_8], r14d
0x140002eaa  jz      short loc_140002EE0
0x140002eac  mov     rcx, [rbx+378h]; hHandle
0x140002eb3  mov     edx, 1F4h; dwMilliseconds
0x140002eb8  call    cs:__imp_WaitForSingleObject
0x140002ebe  test    eax, eax
0x140002ec0  jz      loc_140002F4C
0x140002ec6  cmp     eax, 102h
0x140002ecb  jnz     loc_140002F58
0x140002ed1  mov     edx, edi; unsigned int
0x140002ed3  mov     rcx, rbx; this
0x140002ed6  call    ?SetStatus@CNTService@@QEAAXK@Z; CNTService::SetStatus(ulong)
0x140002edb  jmp     loc_140002D95
0x140002ee0  lea     rcx, aCwmsselfhealin_20; "CWmsSelfHealingSvc::ThreadProc - WNF_DE"...
0x140002ee7  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140002eec  mov     edx, 4; unsigned int
0x140002ef1  mov     rcx, rbx; this
0x140002ef4  call    ?SetStatus@CNTService@@QEAAXK@Z; CNTService::SetStatus(ulong)
0x140002ef9  mov     rcx, rbx; this
0x140002efc  call    ?StartUp@CWmsSelfHealingSvc@@AEAAJXZ; CWmsSelfHealingSvc::StartUp(void)
0x140002f01  test    eax, eax
0x140002f03  js      short loc_140002F58
0x140002f05  mov     rax, [rbx+378h]
0x140002f0c  lea     rdx, [rbp+Handles]; lpHandles
0x140002f10  mov     [rbp+Handles], rax
0x140002f14  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x140002f18  mov     rax, [rbx+360h]
0x140002f1f  xor     r8d, r8d; bWaitAll
0x140002f22  mov     ecx, edi; nCount
0x140002f24  mov     [rbp+Handles+8], rax
0x140002f28  call    cs:__imp_WaitForMultipleObjects
0x140002f2e  test    eax, eax
0x140002f30  jz      short loc_140002F58
0x140002f32  cmp     eax, r14d
0x140002f35  jnz     short loc_140002F58
0x140002f37  mov     edx, 514h; unsigned int
0x140002f3c  call    ?DisplayStatusMessage@CWmsSelfHealingSvc@@AEAAJI@Z; CWmsSelfHealingSvc::DisplayStatusMessage(uint)
0x140002f41  test    eax, eax
0x140002f43  js      short loc_140002F58
0x140002f45  call    ?Reboot@@YAJPEBGKK@Z; Reboot(ushort const *,ulong,ulong)
0x140002f4a  jmp     short loc_140002F58
0x140002f4c  lea     rcx, aCwmsselfhealin_11; "CWmsSelfHealingSvc::ThreadProc - Servic"...
0x140002f53  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140002f58  mov     edx, 3; unsigned int
0x140002f5d  mov     rcx, rbx; this
0x140002f60  call    ?SetStatus@CNTService@@QEAAXK@Z; CNTService::SetStatus(ulong)
0x140002f65  mov     rcx, [rbx+358h]; hEvent
0x140002f6c  test    rcx, rcx
0x140002f6f  jz      short loc_140002F83
0x140002f71  call    cs:__imp_ResetEvent
0x140002f77  lea     rcx, aCwmsselfhealin_24; "CWmsSelfHealingSvc::ShutDown - reset se"...
0x140002f7e  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140002f83  lea     rcx, aCwmsselfhealin_5; "CWmsSelfHealingSvc::StopMonitoring\n"
0x140002f8a  xor     edi, edi
0x140002f8c  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140002f91  mov     rcx, [rbx+368h]
0x140002f98  test    rcx, rcx
0x140002f9b  jz      short loc_140002FAF
0x140002f9d  mov     rax, [rcx]
0x140002fa0  mov     rax, [rax+20h]
0x140002fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002fa9  mov     edi, eax
0x140002fab  test    eax, eax
0x140002fad  js      short loc_140002FD2
0x140002faf  mov     rcx, [rbx+368h]
0x140002fb6  test    rcx, rcx
0x140002fb9  jz      short loc_140002FD2
0x140002fbb  mov     rdx, [rcx]
0x140002fbe  mov     rax, [rdx+10h]
0x140002fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002fc7  mov     qword ptr [rbx+368h], 0
0x140002fd2  mov     edx, edi
0x140002fd4  lea     rcx, aCwmsselfhealin_23; "CWmsSelfHealingSvc::StopMonitoring - hr"...
0x140002fdb  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140002fe0  mov     rcx, [rbx+350h]; hEvent
0x140002fe7  call    cs:__imp_SetEvent
0x140002fed  test    r14d, r14d
0x140002ff0  jz      short loc_140002FF8
0x140002ff2  call    cs:__imp_CoUninitialize
0x140002ff8  xor     eax, eax
0x140002ffa  add     rsp, 50h
0x140002ffe  pop     r14
0x140003000  pop     r13
0x140003002  pop     rdi
0x140003003  pop     rbx
0x140003004  pop     rbp
0x140003005  retn
```
