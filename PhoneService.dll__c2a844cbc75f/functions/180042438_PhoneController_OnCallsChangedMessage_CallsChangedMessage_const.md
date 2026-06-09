# PhoneController::_OnCallsChangedMessage(CallsChangedMessage const *)

- ea: `0x180042438`
- end: `0x1800426eb`
- name: `?_OnCallsChangedMessage@PhoneController@@IEAAJPEBVCallsChangedMessage@@@Z`
- size: `691`
- prototype: `__int64 __fastcall(PhoneController *__hidden this, const struct CallsChangedMessage *)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800454bc`

## callees

- `0x180006e94`
- `0x18001de50`
- `0x18001f514`
- `0x18002c574`
- `0x18002c580`
- `0x18003617c`
- `0x180036b60`
- `0x18003f550`
- `0x180041858`
- `0x180042438`
- `0x18004841c`
- `0x180051e44`
- `0x180070bb0`
- `0x18007f9ec`
- `0x18008d95a`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800425ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800425ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800425ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800425ce`

## string_xrefs

- `0x1800424d3`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180042519`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x1800425c2`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18004265c`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180042673`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_OnCallsChangedMessage(PhoneController *this, const struct _GUID *a2)
{
  int v4; // eax
  BackTraceCollection *v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // r9
  int v8; // eax
  BackTraceCollection *v9; // rcx
  PhoneLineStorage *v10; // rcx
  int PhoneLine; // eax
  BackTraceCollection *v12; // rcx
  int v14; // r12d
  struct PhoneLine *v15; // rbx
  char Capabilities; // al
  int v17; // r14d
  __int64 v18; // rcx
  int v19; // eax
  BackTraceCollection *v20; // rcx
  unsigned int v21; // r14d
  struct PhoneLine *v22; // [rsp+30h] [rbp-59h] BYREF
  _OWORD v23[2]; // [rsp+38h] [rbp-51h] BYREF
  __int128 v24; // [rsp+58h] [rbp-31h]
  LPCRITICAL_SECTION v25[8]; // [rsp+70h] [rbp-19h] BYREF

  memset_0(v25, 0, sizeof(v25));
  AutoLockWithWatchdog::AutoLockWithWatchdog(
    (AutoLockWithWatchdog *)v25,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 224),
    "PhoneController::_OnCallsChangedMessage");
  v4 = PhoneController::_CheckControllerActive(this);
  v6 = v4;
  if ( v4 < 0 )
  {
    BackTraceCollection::Capture(v5, v4);
    v7 = 1615;
LABEL_5:
    Log_HREvent_7(v6, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v7);
LABEL_9:
    AutoLockWithWatchdog::~AutoLockWithWatchdog(v25);
    return v6;
  }
  v8 = PhoneController::_OnCallsChanged(this, (struct _GUID *)&a2[2], (__int64)&a2[3]);
  v6 = v8;
  if ( v8 < 0 )
  {
    BackTraceCollection::Capture(v9, v8);
    v7 = 1617;
    goto LABEL_5;
  }
  v10 = (PhoneLineStorage *)*((_QWORD *)this + 19);
  v22 = 0;
  PhoneLine = PhoneLineStorage::GetPhoneLine(v10, a2 + 2, &v22, 0);
  v6 = PhoneLine;
  if ( PhoneLine < 0 )
  {
    BackTraceCollection::Capture(v12, PhoneLine);
    Log_HREvent_7(v6, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 1620);
    if ( v22 )
      (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v22 + 16LL))(v22);
    goto LABEL_9;
  }
  v14 = 0;
  memset(v23, 0, sizeof(v23));
  v24 = 0;
  PhoneController::_ComputeCallCounts(this, 1, (struct PH_PHONE_CALL_COUNTS *)v23, 0);
  v15 = v22;
  Capabilities = PhoneLine::GetCapabilities(v22);
  v17 = DWORD1(v24);
  if ( (Capabilities & 0x40) != 0 && DWORD1(v24) == DWORD2(v24) && *((_DWORD *)this + 78) && !*((_DWORD *)this + 79) )
  {
    v14 = 1;
    *((_DWORD *)this + 79) = 1;
  }
  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v18, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 9292);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( v17 == DWORD2(v24) )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 60) + 40LL))(*((_QWORD *)this + 60));
    if ( *((_QWORD *)this + 82) != *((_QWORD *)this + 83)
      && *((_DWORD *)this + 158)
      && (*(_QWORD *)((char *)this + 636) != *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1
       || *(_QWORD *)((char *)this + 644) != *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4)
      && !*((_DWORD *)this + 163) )
    {
      v19 = PhoneController::_InitiateVideoCallUpgrade(this);
      v21 = v19;
      if ( v19 < 0 )
      {
        BackTraceCollection::Capture(v20, v19);
        Log_HREvent_7(v21, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 9302);
        Log_HREvent_7(v21, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 1647);
      }
    }
  }
  if ( v15 )
    (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v15 + 16LL))(v15);
  AutoLockWithWatchdog::~AutoLockWithWatchdog(v25);
  if ( v14 )
    PhoneController::_SendImmediateControllerMessage(this, 14, &a2[2], 0, 0);
  return 0;
}

```

## disassembly

```asm
0x180042438  mov     [rsp-8+arg_10], rbx
0x18004243d  mov     [rsp-8+arg_18], rsi
0x180042442  push    rbp
0x180042443  push    rdi
0x180042444  push    r12
0x180042446  push    r14
0x180042448  push    r15
0x18004244a  lea     rbp, [rsp-37h]
0x18004244f  sub     rsp, 0C0h
0x180042456  mov     rax, cs:__security_cookie
0x18004245d  xor     rax, rsp
0x180042460  mov     [rbp+57h+var_30], rax
0x180042464  mov     rsi, rdx
0x180042467  mov     rdi, rcx
0x18004246a  xor     edx, edx; Val
0x18004246c  lea     rcx, [rbp+57h+var_70]; void *
0x180042470  lea     r8d, [rdx+40h]; Size
0x180042474  call    memset_0
0x180042479  lea     rdx, [rdi+0E0h]; struct utl::recursive_mutex *
0x180042480  lea     r8, aPhonecontrolle_53; "PhoneController::_OnCallsChangedMessage"
0x180042487  lea     rcx, [rbp+57h+var_70]; this
0x18004248b  call    ??0AutoLockWithWatchdog@@QEAA@PEAVrecursive_mutex@utl@@PEBD@Z; AutoLockWithWatchdog::AutoLockWithWatchdog(utl::recursive_mutex *,char const *)
0x180042490  mov     rcx, rdi; this
0x180042493  call    ?_CheckControllerActive@PhoneController@@IEAAJXZ; PhoneController::_CheckControllerActive(void)
0x180042498  mov     ebx, eax
0x18004249a  test    eax, eax
0x18004249c  jns     short loc_1800424AD
0x18004249e  mov     edx, eax; int
0x1800424a0  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800424a5  mov     r9d, 64Fh
0x1800424ab  jmp     short loc_1800424D3
0x1800424ad  lea     r15, [rsi+20h]
0x1800424b1  mov     rcx, rdi; this
0x1800424b4  mov     rdx, r15; struct _GUID *
0x1800424b7  lea     r8, [rsi+30h]
0x1800424bb  call    ?_OnCallsChanged@PhoneController@@IEAAJAEBU_GUID@@AEBV?$vector@UCallUpdate@@V?$allocator@UCallUpdate@@@utl@@@utl@@@Z; PhoneController::_OnCallsChanged(_GUID const &,utl::vector<CallUpdate,utl::allocator<CallUpdate>> const &)
0x1800424c0  mov     ebx, eax
0x1800424c2  test    eax, eax
0x1800424c4  jns     short loc_1800424E8
0x1800424c6  mov     edx, eax; int
0x1800424c8  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800424cd  mov     r9d, 651h
0x1800424d3  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800424da  mov     edx, 1
0x1800424df  mov     ecx, ebx
0x1800424e1  call    Log_HREvent_7
0x1800424e6  jmp     short loc_180042541
0x1800424e8  mov     rcx, [rdi+98h]; this
0x1800424ef  lea     r8, [rbp+57h+var_B0]; struct PhoneLine **
0x1800424f3  xor     r9d, r9d; struct ISecurityToken *
0x1800424f6  mov     [rbp+57h+var_B0], 0
0x1800424fe  mov     rdx, r15; struct _GUID *
0x180042501  call    ?GetPhoneLine@PhoneLineStorage@@QEAAJAEBU_GUID@@PEAPEAVPhoneLine@@PEAUISecurityToken@@@Z; PhoneLineStorage::GetPhoneLine(_GUID const &,PhoneLine * *,ISecurityToken *)
0x180042506  mov     ebx, eax
0x180042508  test    eax, eax
0x18004250a  jns     short loc_180042551
0x18004250c  mov     edx, eax; int
0x18004250e  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180042513  mov     r9d, 654h
0x180042519  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180042520  mov     edx, 1
0x180042525  mov     ecx, ebx
0x180042527  call    Log_HREvent_7
0x18004252c  mov     rcx, [rbp+57h+var_B0]
0x180042530  test    rcx, rcx
0x180042533  jz      short loc_180042541
0x180042535  mov     rax, [rcx]
0x180042538  mov     rax, [rax+10h]
0x18004253c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042541  lea     rcx, [rbp+57h+var_70]; this
0x180042545  call    ??1AutoLockWithWatchdog@@QEAA@XZ; AutoLockWithWatchdog::~AutoLockWithWatchdog(void)
0x18004254a  mov     eax, ebx
0x18004254c  jmp     loc_1800426C3
0x180042551  xorps   xmm0, xmm0
0x180042554  lea     r8, [rbp+57h+var_A8]; struct PH_PHONE_CALL_COUNTS *
0x180042558  xor     r12d, r12d
0x18004255b  xor     r9d, r9d; struct ISecurityToken *
0x18004255e  mov     rcx, rdi; this
0x180042561  movups  [rbp+57h+var_A8], xmm0
0x180042565  lea     esi, [r12+1]
0x18004256a  mov     edx, esi; int
0x18004256c  movups  [rbp+57h+var_98], xmm0
0x180042570  movups  [rbp+57h+var_88], xmm0
0x180042574  call    ?_ComputeCallCounts@PhoneController@@IEAAXHPEAUPH_PHONE_CALL_COUNTS@@PEAUISecurityToken@@@Z; PhoneController::_ComputeCallCounts(int,PH_PHONE_CALL_COUNTS *,ISecurityToken *)
0x180042579  mov     rbx, [rbp+57h+var_B0]
0x18004257d  mov     rcx, rbx
0x180042580  call    ?GetCapabilities@PhoneLine@@QEAA?AW4PhoneLineCapabilities@@XZ; PhoneLine::GetCapabilities(void)
0x180042585  mov     r14d, dword ptr [rbp+57h+var_88+4]
0x180042589  test    al, 40h
0x18004258b  jz      short loc_1800425AE
0x18004258d  cmp     r14d, dword ptr [rbp+57h+var_88+8]
0x180042591  jnz     short loc_1800425AE
0x180042593  cmp     [rdi+138h], r12d
0x18004259a  jz      short loc_1800425AE
0x18004259c  cmp     [rdi+13Ch], r12d
0x1800425a3  jnz     short loc_1800425AE
0x1800425a5  mov     r12d, esi
0x1800425a8  mov     [rdi+13Ch], esi
0x1800425ae  call    cs:__imp_GetCurrentThreadId
0x1800425b4  cmp     [rdi+0F0h], eax
0x1800425ba  jz      short loc_1800425E1
0x1800425bc  mov     r8d, 244Ch
0x1800425c2  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800425c9  call    Log_AssertionEvent_3
0x1800425ce  call    cs:__imp_GetCurrentThreadId
0x1800425d4  cmp     [rdi+0F0h], eax
0x1800425da  jz      short loc_1800425E1
0x1800425dc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800425e1  cmp     r14d, dword ptr [rbp+57h+var_88+8]
0x1800425e5  jnz     loc_180042684
0x1800425eb  mov     rcx, [rdi+1E0h]
0x1800425f2  mov     rax, [rcx]
0x1800425f5  mov     rax, [rax+28h]
0x1800425f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800425fe  mov     rax, [rdi+298h]
0x180042605  cmp     [rdi+290h], rax
0x18004260c  jz      short loc_180042684
0x18004260e  cmp     dword ptr [rdi+278h], 0
0x180042615  jz      short loc_180042684
0x180042617  mov     rax, [rdi+27Ch]
0x18004261e  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180042625  jnz     short loc_180042637
0x180042627  mov     rax, [rdi+284h]
0x18004262e  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x180042635  jz      short loc_180042684
0x180042637  cmp     dword ptr [rdi+28Ch], 0
0x18004263e  jnz     short loc_180042684
0x180042640  mov     rcx, rdi; this
0x180042643  call    ?_InitiateVideoCallUpgrade@PhoneController@@IEAAJXZ; PhoneController::_InitiateVideoCallUpgrade(void)
0x180042648  mov     r14d, eax
0x18004264b  test    eax, eax
0x18004264d  jns     short loc_180042684
0x18004264f  mov     edx, eax; int
0x180042651  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180042656  mov     r9d, 2456h
0x18004265c  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180042663  mov     edx, esi
0x180042665  mov     ecx, r14d
0x180042668  call    Log_HREvent_7
0x18004266d  mov     r9d, 66Fh
0x180042673  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004267a  xor     edx, edx
0x18004267c  mov     ecx, r14d
0x18004267f  call    Log_HREvent_7
0x180042684  test    rbx, rbx
0x180042687  jz      short loc_180042698
0x180042689  mov     rax, [rbx]
0x18004268c  mov     rcx, rbx
0x18004268f  mov     rax, [rax+10h]
0x180042693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042698  lea     rcx, [rbp+57h+var_70]; this
0x18004269c  call    ??1AutoLockWithWatchdog@@QEAA@XZ; AutoLockWithWatchdog::~AutoLockWithWatchdog(void)
0x1800426a1  test    r12d, r12d
0x1800426a4  jz      short loc_1800426C1
0x1800426a6  xor     r9d, r9d
0x1800426a9  mov     [rsp+0E0h+var_C0], 0
0x1800426b2  mov     r8, r15
0x1800426b5  mov     rcx, rdi
0x1800426b8  lea     edx, [r9+0Eh]
0x1800426bc  call    ?_SendImmediateControllerMessage@PhoneController@@IEAAXW4tagPH_MSG@@AEBU_GUID@@PEBG2@Z; PhoneController::_SendImmediateControllerMessage(tagPH_MSG,_GUID const &,ushort const *,ushort const *)
0x1800426c1  xor     eax, eax
0x1800426c3  mov     rcx, [rbp+57h+var_30]
0x1800426c7  xor     rcx, rsp; StackCookie
0x1800426ca  call    __security_check_cookie
0x1800426cf  lea     r11, [rsp+0E0h+var_20]
0x1800426d7  mov     rbx, [r11+40h]
0x1800426db  mov     rsi, [r11+48h]
0x1800426df  mov     rsp, r11
0x1800426e2  pop     r15
0x1800426e4  pop     r14
0x1800426e6  pop     r12
0x1800426e8  pop     rdi
0x1800426e9  pop     rbp
0x1800426ea  retn
```
