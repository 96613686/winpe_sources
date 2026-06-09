# CWmsSelfHealingSvc::StartMonitoring(__MIDL___MIDL_itf_wmsconfigtasks_0000_0000_0003)

- ea: `0x140002838`
- end: `0x1400029df`
- name: `?StartMonitoring@CWmsSelfHealingSvc@@AEAAJW4__MIDL___MIDL_itf_wmsconfigtasks_0000_0000_0003@@@Z`
- size: `423`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400029e8`

## callees

- `0x140002838`
- `0x1400036a0`
- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x140006544`
- `0x14000c010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1400028f7`
- `KERNEL32!IsDebuggerPresent` at `0x1400028f7`
- `KERNEL32!GetLastError` at `0x14000289e`
- `KERNEL32!GetLastError` at `0x14000289e`
- `KERNEL32!CreateEventW` at `0x140002888`
- `KERNEL32!CreateEventW` at `0x140002888`
- `ole32!CoCreateInstance` at `0x140002974`
- `ole32!CoCreateInstance` at `0x140002974`
- `OLEAUT32!__imp_VariantInit` at `0x140002874`
- `OLEAUT32!__imp_VariantInit` at `0x140002874`
- `OLEAUT32!__imp_VariantClear` at `0x1400029ca`
- `OLEAUT32!__imp_VariantClear` at `0x1400029ca`

## pseudocode

```c
__int64 __fastcall CWmsSelfHealingSvc::StartMonitoring(__int64 a1, unsigned int a2)
{
  __int64 v4; // rax
  HANDLE EventW; // rax
  signed int LastError; // eax
  int Instance; // ebx
  const unsigned __int16 *v8; // r14
  const unsigned __int16 *v9; // r15
  unsigned int v10; // ebp
  VARIANTARG pvarg; // [rsp+40h] [rbp-58h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  v4 = Utils::ExecutionModeToString(a2);
  DEBUGMSG(L"CWmsSelfHealingSvc::StartMonitoring - eMode = %s\n", v4);
  VariantInit(&pvarg);
  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)(a1 + 864) = EventW;
  if ( EventW )
  {
    Instance = CoCreateInstance(
                 &CLSID_WmsConfigMonitor,
                 0,
                 1u,
                 &GUID_ee67c5d5_46c1_4245_8969_6ccfb2e7f69b,
                 (LPVOID *)(a1 + 872));
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, VARIANTARG *))(**(_QWORD **)(a1 + 872) + 24LL))(
                   *(_QWORD *)(a1 + 872),
                   a2,
                   *(_QWORD *)(a1 + 864),
                   &pvarg);
      goto LABEL_13;
    }
    v8 = L"hr";
    v10 = 194;
    v9 = L"CHRA";
  }
  else
  {
    LastError = GetLastError();
    Instance = LastError;
    if ( LastError > 0 )
      Instance = (unsigned __int16)LastError | 0x80070000;
    v8 = L"m_hRebootEvent != 0";
    v9 = L"CBRAEx";
    if ( Instance >= 0 )
      Instance = -2147467259;
    v10 = 189;
  }
  LOGASSERTHR(
    L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
    v10,
    L"CWmsSelfHealingSvc::StartMonitoring",
    v9,
    v8,
    Instance);
  if ( IsDebuggerPresent() )
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
      v10,
      L"CWmsSelfHealingSvc::StartMonitoring",
      v9,
      v8,
      Instance,
      *(_OWORD *)&pvarg.vt,
      pvarg.pRecInfo);
  else
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\platform\\wmsselfhealingsvc\\wmsselfhealingsvc.cpp",
      v10,
      L"CWmsSelfHealingSvc::StartMonitoring",
      v9,
      v8,
      Instance);
LABEL_13:
  DEBUGMSG(L"CWmsSelfHealingSvc::StartMonitoring - hr = 0x%08X\n", (unsigned int)Instance);
  VariantClear(&pvarg);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x140002838  push    rbx
0x14000283a  push    rbp
0x14000283b  push    rsi
0x14000283c  push    rdi
0x14000283d  push    r14
0x14000283f  push    r15
0x140002841  sub     rsp, 68h
0x140002845  mov     rsi, rcx
0x140002848  xorps   xmm0, xmm0
0x14000284b  xor     eax, eax
0x14000284d  mov     ecx, edx
0x14000284f  movups  xmmword ptr [rsp+98h+pvarg], xmm0
0x140002854  mov     qword ptr [rsp+98h+pvarg+10h], rax
0x140002859  mov     ebp, edx
0x14000285b  call    ?ExecutionModeToString@Utils@@YAPEBGW4__MIDL___MIDL_itf_wmsconfigtasks_0000_0000_0003@@@Z; Utils::ExecutionModeToString(__MIDL___MIDL_itf_wmsconfigtasks_0000_0000_0003)
0x140002860  mov     rdx, rax
0x140002863  lea     rcx, aCwmsselfhealin_17; "CWmsSelfHealingSvc::StartMonitoring - e"...
0x14000286a  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000286f  lea     rcx, [rsp+98h+pvarg]; pvarg
0x140002874  call    cs:__imp_VariantInit
0x14000287a  xor     r9d, r9d; lpName
0x14000287d  xor     r8d, r8d; bInitialState
0x140002880  xor     ecx, ecx; lpEventAttributes
0x140002882  lea     ebx, [r9+1]
0x140002886  mov     edx, ebx; bManualReset
0x140002888  call    cs:__imp_CreateEventW
0x14000288e  mov     [rsi+360h], rax
0x140002895  test    rax, rax
0x140002898  jnz     loc_140002955
0x14000289e  call    cs:__imp_GetLastError
0x1400028a4  mov     ebx, eax
0x1400028a6  test    eax, eax
0x1400028a8  jle     short loc_1400028B3
0x1400028aa  movzx   ebx, ax
0x1400028ad  or      ebx, 80070000h
0x1400028b3  test    ebx, ebx
0x1400028b5  lea     r14, aMHrebootevent0; "m_hRebootEvent != 0"
0x1400028bc  mov     eax, 80004005h
0x1400028c1  lea     r15, aCbraex; "CBRAEx"
0x1400028c8  cmovns  ebx, eax
0x1400028cb  mov     ebp, 0BDh
0x1400028d0  lea     rsi, aCwmsselfhealin_1; "CWmsSelfHealingSvc::StartMonitoring"
0x1400028d7  mov     [rsp+98h+var_70], ebx; int
0x1400028db  lea     rdi, aTermsrvWmsSrcP; "termsrv\\wms\\src\\platform\\wmsselfhea"...
0x1400028e2  mov     [rsp+98h+ppv], r14; unsigned __int16 *
0x1400028e7  mov     r8, rsi; unsigned __int16 *
0x1400028ea  mov     rcx, rdi; unsigned __int16 *
0x1400028ed  mov     r9, r15; unsigned __int16 *
0x1400028f0  mov     edx, ebp; unsigned int
0x1400028f2  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400028f7  call    cs:__imp_IsDebuggerPresent
0x1400028fd  test    eax, eax
0x1400028ff  jz      short loc_140002930
0x140002901  mov     [rsp+98h+var_60], ebx
0x140002905  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000290c  mov     [rsp+98h+var_68], r14
0x140002911  mov     r9d, ebp
0x140002914  mov     qword ptr [rsp+98h+var_70], r15
0x140002919  mov     r8, rdi
0x14000291c  mov     ecx, 2; unsigned __int8
0x140002921  mov     [rsp+98h+ppv], rsi
0x140002926  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000292b  jmp     loc_1400029B7
0x140002930  mov     dword ptr [rsp+98h+var_68], ebx
0x140002934  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000293b  mov     qword ptr [rsp+98h+var_70], r14
0x140002940  mov     r9, rsi
0x140002943  mov     r8d, ebp
0x140002946  mov     [rsp+98h+ppv], r15
0x14000294b  mov     rdx, rdi
0x14000294e  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140002953  jmp     short loc_1400029B7
0x140002955  lea     rdi, [rsi+368h]
0x14000295c  mov     r8d, ebx; dwClsContext
0x14000295f  lea     r9, _GUID_ee67c5d5_46c1_4245_8969_6ccfb2e7f69b; riid
0x140002966  mov     [rsp+98h+ppv], rdi; ppv
0x14000296b  xor     edx, edx; pUnkOuter
0x14000296d  lea     rcx, CLSID_WmsConfigMonitor; rclsid
0x140002974  call    cs:__imp_CoCreateInstance
0x14000297a  mov     ebx, eax
0x14000297c  test    eax, eax
0x14000297e  jns     short loc_140002998
0x140002980  lea     r14, aHr; "hr"
0x140002987  mov     ebp, 0C2h
0x14000298c  lea     r15, aChra; "CHRA"
0x140002993  jmp     loc_1400028D0
0x140002998  mov     rcx, [rdi]
0x14000299b  lea     r9, [rsp+98h+pvarg]
0x1400029a0  mov     r8, [rsi+360h]
0x1400029a7  mov     edx, ebp
0x1400029a9  mov     rax, [rcx]
0x1400029ac  mov     rax, [rax+18h]
0x1400029b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400029b5  mov     ebx, eax
0x1400029b7  mov     edx, ebx
0x1400029b9  lea     rcx, aCwmsselfhealin_9; "CWmsSelfHealingSvc::StartMonitoring - h"...
0x1400029c0  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400029c5  lea     rcx, [rsp+98h+pvarg]; pvarg
0x1400029ca  call    cs:__imp_VariantClear
0x1400029d0  mov     eax, ebx
0x1400029d2  add     rsp, 68h
0x1400029d6  pop     r15
0x1400029d8  pop     r14
0x1400029da  pop     rdi
0x1400029db  pop     rsi
0x1400029dc  pop     rbp
0x1400029dd  pop     rbx
0x1400029de  retn
```
