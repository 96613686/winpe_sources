# PhoneController::_Dial(PH_DIAL_PARAMETERS const &,PH_PHONE_CALL_COUNTS const &,uint *,ISecurityToken *)

- ea: `0x180037804`
- end: `0x180037ef4`
- name: `?_Dial@PhoneController@@AEAAJAEBUPH_DIAL_PARAMETERS@@AEBUPH_PHONE_CALL_COUNTS@@PEAIPEAUISecurityToken@@@Z`
- size: `1776`
- prototype: `__int64 __usercall@<rax>(PhoneController *__hidden this@<rcx>, const struct PH_DIAL_PARAMETERS *@<rdx>, const struct PH_PHONE_CALL_COUNTS *@<r8>, unsigned int *@<r9>, struct ISecurityToken *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180049cec`

## callees

- `0x1800056a0`
- `0x180006e94`
- `0x18002c574`
- `0x18002c580`
- `0x1800361f8`
- `0x180036564`
- `0x180036ce4`
- `0x18003723c`
- `0x180037804`
- `0x180051e44`
- `0x18005292c`
- `0x18006df58`
- `0x18006ffcc`
- `0x180077918`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037845`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037869`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800378f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037913`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037845`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037869`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800378f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037913`

## string_xrefs

- `0x18003784b`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180037907`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180037966`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x1800379dc`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180037a06`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180037a60`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180037a9e`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180037add`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180037b10`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180037b69`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180037c5a`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180037e0a`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_Dial(
        PhoneController *this,
        const struct PH_DIAL_PARAMETERS *a2,
        const struct PH_PHONE_CALL_COUNTS *a3,
        unsigned int *a4,
        struct ISecurityToken *a5)
{
  BackTraceCollection *v8; // rcx
  int v9; // edi
  unsigned int v10; // ebx
  BackTraceCollection *v11; // rcx
  __int64 v12; // r9
  _WORD *v14; // rcx
  int v15; // r12d
  int v16; // ebx
  __int64 v17; // rcx
  __int64 v18; // rcx
  struct PhoneLine *v19; // rbx
  unsigned int v20; // edi
  BackTraceCollection *v21; // rcx
  BackTraceCollection *v22; // rcx
  __int64 v23; // r9
  __int64 v24; // rdx
  int v25; // eax
  BackTraceCollection *v26; // rcx
  int v27; // eax
  BackTraceCollection *v28; // rcx
  PhoneLineStorage *v29; // rcx
  int PhoneLine; // eax
  BackTraceCollection *v31; // rcx
  struct PhoneLine *v32; // rbx
  int v33; // eax
  BackTraceCollection *v34; // rcx
  const unsigned __int16 *v35; // r8
  int v36; // eax
  BackTraceCollection *v37; // rcx
  struct PhoneLine *v38; // rdi
  int v39; // r13d
  int v40; // r9d
  __int64 v41; // r8
  _WORD *v42; // rdx
  int v43; // eax
  BackTraceCollection *v44; // rcx
  const unsigned __int16 *v45; // r9
  unsigned int v46; // r12d
  __int64 v47; // r9
  bool v48; // zf
  struct PH_PHONE_CALL_COUNTS *v49; // r13
  int v50; // eax
  BackTraceCollection *v51; // rcx
  int DialQueue; // eax
  BackTraceCollection *v53; // rcx
  int v54; // eax
  BackTraceCollection *v55; // rcx
  _WORD *v56; // rcx
  __int128 v57; // xmm0
  __int128 v58; // xmm2
  unsigned int v59; // r15d
  __int64 v60; // rcx
  int v61; // eax
  BackTraceCollection *v62; // rcx
  unsigned int v63; // r14d
  __int16 *v64; // rcx
  unsigned int v65; // [rsp+20h] [rbp-E0h]
  struct PhoneLine *v66; // [rsp+30h] [rbp-D0h] BYREF
  struct PH_PHONE_CALL_COUNTS *v67; // [rsp+38h] [rbp-C8h]
  unsigned int *v68; // [rsp+40h] [rbp-C0h]
  _QWORD v69[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v70; // [rsp+58h] [rbp-A8h]
  int v71; // [rsp+5Ch] [rbp-A4h]
  _OWORD v72[3]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v73; // [rsp+90h] [rbp-70h]
  __int128 v74; // [rsp+A0h] [rbp-60h]
  __int64 v75; // [rsp+B0h] [rbp-50h]
  void *Block[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v77; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v78; // [rsp+D2h] [rbp-2Eh]
  int v79; // [rsp+DAh] [rbp-26h]
  __int16 v80; // [rsp+DEh] [rbp-22h]
  void *v81; // [rsp+E0h] [rbp-20h]
  __int16 *v82; // [rsp+E8h] [rbp-18h]
  __int16 v83; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v84; // [rsp+F2h] [rbp-Eh]
  int v85; // [rsp+FAh] [rbp-6h]
  __int16 v86; // [rsp+FEh] [rbp-2h]

  v68 = a4;
  v67 = a3;
  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v8, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 5213);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v9 = 0;
  *a4 = 0;
  if ( (*(_DWORD *)a2 & 0xFFFFEE86) != 0 )
  {
    v10 = -2147024809;
    BackTraceCollection::Capture(v8, -2147024809);
    Log_HREvent_7(2147942487LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 5071);
    BackTraceCollection::Capture(v11, -2147024809);
    v12 = 5218;
LABEL_6:
    Log_HREvent_7(v10, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v12);
    return v10;
  }
  v14 = (_WORD *)*((_QWORD *)a2 + 1);
  if ( !v14 || (v15 = 1, !*v14) )
    v15 = 0;
  if ( !*((_QWORD *)a2 + 3) || (v16 = 1, !*((_DWORD *)a2 + 8)) )
    v16 = 0;
  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v17, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 5299);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( !v16 && !v15 )
  {
    v18 = *((_QWORD *)this + 12);
    v66 = 0;
    PhoneCallStorage::FindCallByState(v18, &v66, 3, 0);
    v19 = v66;
    if ( !v66 )
    {
      v20 = -2147023728;
      Log_HREvent_7(2147943568LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 5306);
LABEL_26:
      BackTraceCollection::Capture(v21, v20);
      Log_HREvent_7(v20, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 5225);
      return v20;
    }
    LODWORD(v66) = *((_DWORD *)v66 + 767);
    if ( !(*(unsigned int (__fastcall **)(PhoneController *, struct PhoneLine **))(*(_QWORD *)this + 56LL))(this, &v66) )
    {
      v20 = -2147467259;
      BackTraceCollection::Capture(v22, -2147467259);
      v23 = 5308;
      v24 = 0;
LABEL_25:
      Log_HREvent_7(v20, v24, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v23);
      (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v19 + 16LL))(v19);
      goto LABEL_26;
    }
    v25 = DialQueue::ExecuteAction(*((_QWORD *)v19 + 832), 3, 0);
    v20 = v25;
    if ( v25 < 0 )
    {
      BackTraceCollection::Capture(v26, v25);
      v23 = 5310;
      v24 = 1;
      goto LABEL_25;
    }
    v9 = 1;
    (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v19 + 16LL))(v19);
  }
  if ( v9 )
  {
    v27 = (*(__int64 (__fastcall **)(PhoneController *))(*(_QWORD *)this + 872LL))(this);
    v10 = v27;
    if ( v27 < 0 )
    {
      BackTraceCollection::Capture(v28, v27);
      v12 = 5231;
      goto LABEL_6;
    }
    return 0;
  }
  v29 = (PhoneLineStorage *)*((_QWORD *)this + 19);
  v66 = 0;
  PhoneLine = PhoneLineStorage::GetPhoneLine(v29, (const struct _GUID *)a2 + 3, &v66, a5);
  v10 = PhoneLine;
  if ( PhoneLine < 0 )
  {
    BackTraceCollection::Capture(v31, PhoneLine);
    Log_HREvent_7(v10, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 5238);
    if ( v66 )
      (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v66 + 16LL))(v66);
    return v10;
  }
  v32 = v66;
  if ( !v66 )
  {
    Log_AssertionEvent_3(v31, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 5239);
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v33 = PhoneLine::CheckOwnershipPolicy(v32, *((const unsigned __int16 **)a2 + 10), a5);
  v20 = v33;
  if ( v33 < 0 )
  {
    BackTraceCollection::Capture(v34, v33);
    Log_HREvent_7(v20, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 5241);
    if ( !v32 )
      return v20;
LABEL_39:
    (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v32 + 16LL))(v32);
    return v20;
  }
  v35 = (const unsigned __int16 *)*((_QWORD *)a2 + 1);
  v66 = 0;
  v36 = PhoneController::_CheckInCallCommand(this, v32, v35, &v66);
  v20 = v36;
  if ( v36 < 0 )
  {
    BackTraceCollection::Capture(v37, v36);
    Log_HREvent_7(v20, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 5244);
    if ( v66 )
      (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v66 + 16LL))(v66);
    if ( !v32 )
      return v20;
    goto LABEL_39;
  }
  v38 = v66;
  v39 = 0;
  if ( v66 )
  {
    v39 = 1;
    if ( v32 != v66 )
    {
      (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v66 + 8LL))(v66);
      if ( v32 )
        (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v32 + 16LL))(v32);
      v32 = v38;
    }
  }
  v40 = *((_DWORD *)a2 + 8);
  v41 = *((_QWORD *)a2 + 3);
  v42 = (_WORD *)*((_QWORD *)a2 + 1);
  v81 = &v83;
  v82 = &v83;
  Block[0] = &v77;
  Block[1] = &v77;
  v84 = 0;
  v85 = 0;
  v86 = 0;
  v83 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v77 = 0;
  v43 = PhoneController::_DetermineDialString((__int64)this, v42, v41, v40, v65, Block);
  v46 = v43;
  if ( v43 < 0 )
  {
    BackTraceCollection::Capture(v44, v43);
    v47 = 5259;
LABEL_52:
    Log_HREvent_7(v46, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v47);
    if ( Block[0] != &v77 )
      operator delete(Block[0]);
    if ( v81 != &v83 )
      operator delete(v81);
    if ( v38 )
      (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v38 + 16LL))(v38);
    if ( v32 )
      (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v32 + 16LL))(v32);
    return v46;
  }
  v48 = v39 == 0;
  v49 = v67;
  if ( v48 )
  {
    v50 = PhoneController::_CheckDialAvailability(this, v32, v67);
    v46 = v50;
    if ( v50 < 0 )
    {
      BackTraceCollection::Capture(v51, v50);
      v47 = 5264;
      goto LABEL_52;
    }
  }
  DialQueue = PhoneController::_CreateDialQueue(this, v32, (const unsigned __int16 *)Block[0], v45, *(_DWORD *)a2);
  v46 = DialQueue;
  if ( DialQueue < 0 )
  {
    BackTraceCollection::Capture(v53, DialQueue);
    v47 = 5268;
    goto LABEL_52;
  }
  LODWORD(v66) = 0;
  v54 = PhoneLine::GeneratePhoneCallId((unsigned int *)&v66);
  v46 = v54;
  if ( v54 < 0 )
  {
    BackTraceCollection::Capture(v55, v54);
    v47 = 5274;
    goto LABEL_52;
  }
  v56 = (_WORD *)*((_QWORD *)a2 + 1);
  v72[1] = *((_OWORD *)a2 + 1);
  v57 = *((_OWORD *)a2 + 3);
  v72[2] = *((_OWORD *)a2 + 2);
  v73 = v57;
  v75 = *((_QWORD *)a2 + 10);
  v58 = *(_OWORD *)a2;
  v74 = *((_OWORD *)a2 + 4);
  v72[0] = v58;
  v73 = *(_OWORD *)((char *)v32 + 88);
  if ( !v56 || !*v56 )
    *((void **)&v72[0] + 1) = Block[0];
  v59 = (unsigned int)v66;
  v69[1] = Block[0];
  v48 = *((_DWORD *)v49 + 10) - *((_DWORD *)v49 + 9) == *((_DWORD *)v49 + 2);
  v69[0] = v72;
  v60 = *((_QWORD *)this + 27);
  v71 = 0;
  v70 = (int)v66;
  v61 = DialQueue::ExecuteAction(v60, !v48, v69);
  v63 = v61;
  if ( v61 >= 0 )
  {
    v64 = (__int16 *)Block[0];
    *v68 = v59;
    if ( v64 != &v77 )
      operator delete(v64);
    if ( v81 != &v83 )
      operator delete(v81);
    if ( v38 )
      (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v38 + 16LL))(v38);
    (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v32 + 16LL))(v32);
    return 0;
  }
  BackTraceCollection::Capture(v62, v61);
  Log_HREvent_7(v63, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 5291);
  if ( Block[0] != &v77 )
    operator delete(Block[0]);
  if ( v81 != &v83 )
    operator delete(v81);
  if ( v38 )
    (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v38 + 16LL))(v38);
  (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v32 + 16LL))(v32);
  return v63;
}

```

## disassembly

```asm
0x180037804  push    rbp
0x180037806  push    rbx
0x180037807  push    rsi
0x180037808  push    rdi
0x180037809  push    r12
0x18003780b  push    r13
0x18003780d  push    r14
0x18003780f  push    r15
0x180037811  lea     rbp, [rsp-18h]
0x180037816  sub     rsp, 118h
0x18003781d  mov     rax, cs:__security_cookie
0x180037824  xor     rax, rsp
0x180037827  mov     [rbp+50h+var_50], rax
0x18003782b  mov     r13, [rbp+50h+arg_20]
0x180037832  mov     rbx, r9
0x180037835  mov     [rsp+150h+var_110], rbx
0x18003783a  mov     r15, rdx
0x18003783d  mov     [rsp+150h+var_118], r8
0x180037842  mov     r14, rcx
0x180037845  call    cs:__imp_GetCurrentThreadId
0x18003784b  lea     rsi, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180037852  cmp     [r14+0F0h], eax
0x180037859  jz      short loc_18003787D
0x18003785b  mov     r8d, 145Dh
0x180037861  mov     rdx, rsi
0x180037864  call    Log_AssertionEvent_3
0x180037869  call    cs:__imp_GetCurrentThreadId
0x18003786f  cmp     [r14+0F0h], eax
0x180037876  jz      short loc_18003787D
0x180037878  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003787d  xor     edi, edi
0x18003787f  mov     [rbx], edi
0x180037881  test    dword ptr [r15], 0FFFFEE86h
0x180037888  jz      short loc_1800378C9
0x18003788a  mov     ebx, 80070057h
0x18003788f  mov     edx, ebx; int
0x180037891  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180037896  mov     r9d, 13CFh
0x18003789c  mov     r8, rsi
0x18003789f  xor     edx, edx
0x1800378a1  mov     ecx, ebx
0x1800378a3  call    Log_HREvent_7
0x1800378a8  mov     edx, ebx; int
0x1800378aa  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800378af  mov     r9d, 1462h
0x1800378b5  lea     edx, [rdi+1]
0x1800378b8  mov     r8, rsi
0x1800378bb  mov     ecx, ebx
0x1800378bd  call    Log_HREvent_7
0x1800378c2  mov     eax, ebx
0x1800378c4  jmp     loc_180037ED4
0x1800378c9  mov     rcx, [r15+8]
0x1800378cd  mov     esi, 1
0x1800378d2  test    rcx, rcx
0x1800378d5  jz      short loc_1800378DF
0x1800378d7  mov     r12d, esi
0x1800378da  cmp     di, [rcx]
0x1800378dd  jnz     short loc_1800378E2
0x1800378df  mov     r12d, edi
0x1800378e2  cmp     [r15+18h], rdi
0x1800378e6  jz      short loc_1800378F0
0x1800378e8  mov     ebx, esi
0x1800378ea  cmp     [r15+20h], edi
0x1800378ee  jnz     short loc_1800378F2
0x1800378f0  mov     ebx, edi
0x1800378f2  call    cs:__imp_GetCurrentThreadId
0x1800378f8  cmp     [r14+0F0h], eax
0x1800378ff  jz      short loc_180037927
0x180037901  mov     r8d, 14B3h
0x180037907  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003790e  call    Log_AssertionEvent_3
0x180037913  call    cs:__imp_GetCurrentThreadId
0x180037919  cmp     [r14+0F0h], eax
0x180037920  jz      short loc_180037927
0x180037922  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180037927  test    ebx, ebx
0x180037929  jnz     loc_180037A30
0x18003792f  test    r12d, r12d
0x180037932  jnz     loc_180037A30
0x180037938  mov     rcx, [r14+60h]
0x18003793c  lea     edi, [rbx+3]
0x18003793f  xor     r12d, r12d
0x180037942  lea     rdx, [rsp+150h+var_120]
0x180037947  mov     r8d, edi
0x18003794a  mov     [rsp+150h+var_120], r12
0x18003794f  xor     r9d, r9d
0x180037952  call    ?FindCallByState@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@W4PH_CALLSTATE@@PEAUISecurityToken@@@Z; PhoneCallStorage::FindCallByState(PH_CALLSTATE,ISecurityToken *)
0x180037957  mov     rbx, [rsp+150h+var_120]
0x18003795c  test    rbx, rbx
0x18003795f  jnz     short loc_18003797E
0x180037961  mov     edi, 80070490h
0x180037966  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003796d  mov     ecx, edi
0x18003796f  mov     r9d, 14BAh
0x180037975  xor     edx, edx
0x180037977  call    Log_HREvent_7
0x18003797c  jmp     short loc_1800379F9
0x18003797e  mov     eax, [rbx+0BFCh]
0x180037984  lea     rdx, [rsp+150h+var_120]
0x180037989  mov     dword ptr [rsp+150h+var_120], eax
0x18003798d  mov     rcx, r14
0x180037990  mov     rax, [r14]
0x180037993  mov     rax, [rax+38h]
0x180037997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003799c  test    eax, eax
0x18003799e  jnz     short loc_1800379B6
0x1800379a0  mov     edi, 80004005h
0x1800379a5  mov     edx, edi; int
0x1800379a7  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800379ac  mov     r9d, 14BCh
0x1800379b2  xor     edx, edx
0x1800379b4  jmp     short loc_1800379DC
0x1800379b6  mov     rcx, [rbx+1A00h]
0x1800379bd  xor     r8d, r8d
0x1800379c0  mov     edx, edi
0x1800379c2  call    ?ExecuteAction@DialQueue@@QEAAJW4EXECUTEQUEUE@@PEAX@Z; DialQueue::ExecuteAction(EXECUTEQUEUE,void *)
0x1800379c7  mov     edi, eax
0x1800379c9  test    eax, eax
0x1800379cb  jns     short loc_180037A1D
0x1800379cd  mov     edx, eax; int
0x1800379cf  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800379d4  mov     r9d, 14BEh
0x1800379da  mov     edx, esi
0x1800379dc  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800379e3  mov     ecx, edi
0x1800379e5  call    Log_HREvent_7
0x1800379ea  mov     rax, [rbx]
0x1800379ed  mov     rcx, rbx
0x1800379f0  mov     rax, [rax+10h]
0x1800379f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800379f9  mov     edx, edi; int
0x1800379fb  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180037a00  mov     r9d, 1469h
0x180037a06  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180037a0d  mov     edx, esi
0x180037a0f  mov     ecx, edi
0x180037a11  call    Log_HREvent_7
0x180037a16  mov     eax, edi
0x180037a18  jmp     loc_180037ED4
0x180037a1d  mov     rax, [rbx]
0x180037a20  mov     rcx, rbx
0x180037a23  mov     edi, esi
0x180037a25  mov     rax, [rax+10h]
0x180037a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a2e  jmp     short loc_180037A33
0x180037a30  xor     r12d, r12d
0x180037a33  test    edi, edi
0x180037a35  jz      short loc_180037A6E
0x180037a37  mov     rax, [r14]
0x180037a3a  mov     rcx, r14
0x180037a3d  mov     rax, [rax+368h]
0x180037a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a49  mov     ebx, eax
0x180037a4b  test    eax, eax
0x180037a4d  jns     loc_180037ED2
0x180037a53  mov     edx, eax; int
0x180037a55  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180037a5a  mov     r9d, 146Fh
0x180037a60  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180037a67  mov     edx, esi
0x180037a69  jmp     loc_1800378BB
0x180037a6e  mov     rcx, [r14+98h]; this
0x180037a75  lea     rdx, [r15+30h]; struct _GUID *
0x180037a79  mov     r9, r13; struct ISecurityToken *
0x180037a7c  mov     [rsp+150h+var_120], r12
0x180037a81  lea     r8, [rsp+150h+var_120]; struct PhoneLine **
0x180037a86  call    ?GetPhoneLine@PhoneLineStorage@@QEAAJAEBU_GUID@@PEAPEAVPhoneLine@@PEAUISecurityToken@@@Z; PhoneLineStorage::GetPhoneLine(_GUID const &,PhoneLine * *,ISecurityToken *)
0x180037a8b  mov     ebx, eax
0x180037a8d  test    eax, eax
0x180037a8f  jns     short loc_180037ACD
0x180037a91  mov     edx, eax; int
0x180037a93  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180037a98  mov     r9d, 1476h
0x180037a9e  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180037aa5  mov     edx, esi
0x180037aa7  mov     ecx, ebx
0x180037aa9  call    Log_HREvent_7
0x180037aae  mov     rcx, [rsp+150h+var_120]
0x180037ab3  test    rcx, rcx
0x180037ab6  jz      loc_1800378C2
0x180037abc  mov     rax, [rcx]
0x180037abf  mov     rax, [rax+10h]
0x180037ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037ac8  jmp     loc_1800378C2
0x180037acd  mov     rbx, [rsp+150h+var_120]
0x180037ad2  test    rbx, rbx
0x180037ad5  jnz     short loc_180037AEE
0x180037ad7  mov     r8d, 1477h
0x180037add  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180037ae4  call    Log_AssertionEvent_3
0x180037ae9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180037aee  mov     rdx, [r15+50h]; unsigned __int16 *
0x180037af2  mov     r8, r13; struct ISecurityToken *
0x180037af5  mov     rcx, rbx; this
0x180037af8  call    ?CheckOwnershipPolicy@PhoneLine@@QEAAJPEBGPEAUISecurityToken@@@Z; PhoneLine::CheckOwnershipPolicy(ushort const *,ISecurityToken *)
0x180037afd  mov     edi, eax
0x180037aff  test    eax, eax
0x180037b01  jns     short loc_180037B3D
0x180037b03  mov     edx, eax; int
0x180037b05  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180037b0a  mov     r9d, 1479h
0x180037b10  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180037b17  mov     edx, esi
0x180037b19  mov     ecx, edi
0x180037b1b  call    Log_HREvent_7
0x180037b20  test    rbx, rbx
0x180037b23  jz      loc_180037A16
0x180037b29  mov     rcx, [rbx]
0x180037b2c  mov     rax, [rcx+10h]
0x180037b30  mov     rcx, rbx
0x180037b33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037b38  jmp     loc_180037A16
0x180037b3d  mov     r8, [r15+8]; unsigned __int16 *
0x180037b41  lea     r9, [rsp+150h+var_120]; struct PhoneLine **
0x180037b46  mov     rdx, rbx; struct PhoneLine *
0x180037b49  mov     [rsp+150h+var_120], r12
0x180037b4e  mov     rcx, r14; this
0x180037b51  call    ?_CheckInCallCommand@PhoneController@@AEAAJPEAVPhoneLine@@PEBGPEAPEAV2@@Z; PhoneController::_CheckInCallCommand(PhoneLine *,ushort const *,PhoneLine * *)
0x180037b56  mov     edi, eax
0x180037b58  test    eax, eax
0x180037b5a  jns     short loc_180037BA1
0x180037b5c  mov     edx, eax; int
0x180037b5e  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180037b63  mov     r9d, 147Ch
0x180037b69  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180037b70  mov     edx, esi
0x180037b72  mov     ecx, edi
0x180037b74  call    Log_HREvent_7
0x180037b79  mov     rcx, [rsp+150h+var_120]
0x180037b7e  test    rcx, rcx
0x180037b81  jz      short loc_180037B8F
0x180037b83  mov     rax, [rcx]
0x180037b86  mov     rax, [rax+10h]
0x180037b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037b8f  test    rbx, rbx
0x180037b92  jz      loc_180037A16
0x180037b98  mov     rax, [rbx]
0x180037b9b  mov     rax, [rax+10h]
0x180037b9f  jmp     short loc_180037B30
0x180037ba1  mov     rdi, [rsp+150h+var_120]
0x180037ba6  mov     r13d, r12d
0x180037ba9  test    rdi, rdi
0x180037bac  jz      short loc_180037BE1
0x180037bae  mov     r13d, esi
0x180037bb1  cmp     rbx, rdi
0x180037bb4  jz      short loc_180037BE1
0x180037bb6  test    rdi, rdi
0x180037bb9  jz      short loc_180037BCA
0x180037bbb  mov     rax, [rdi]
0x180037bbe  mov     rcx, rdi
0x180037bc1  mov     rax, [rax+8]
0x180037bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037bca  test    rbx, rbx
0x180037bcd  jz      short loc_180037BDE
0x180037bcf  mov     rax, [rbx]
0x180037bd2  mov     rcx, rbx
0x180037bd5  mov     rax, [rax+10h]
0x180037bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037bde  mov     rbx, rdi
0x180037be1  mov     r9d, [r15+20h]
0x180037be5  lea     rax, [rbp+50h+var_60]
0x180037be9  mov     r8, [r15+18h]
0x180037bed  mov     rcx, r14
0x180037bf0  mov     rdx, [r15+8]
0x180037bf4  mov     [rbp+50h+var_70], rax
0x180037bf8  lea     rax, [rbp+50h+var_60]
0x180037bfc  mov     [rbp+50h+var_68], rax
0x180037c00  lea     rax, [rbp+50h+var_80]
0x180037c04  mov     [rbp+50h+Block], rax
0x180037c08  lea     rax, [rbp+50h+var_80]
0x180037c0c  mov     [rbp+50h+var_88], rax
0x180037c10  lea     rax, [rbp+50h+Block]
0x180037c14  mov     [rsp+150h+var_128], rax
0x180037c19  mov     [rbp+50h+var_5E], r12
0x180037c1d  mov     [rbp+50h+var_56], r12d
0x180037c21  mov     [rbp+50h+var_52], r12w
0x180037c26  mov     [rbp+50h+var_60], r12w
0x180037c2b  mov     [rbp+50h+var_7E], r12
0x180037c2f  mov     [rbp+50h+var_76], r12d
0x180037c33  mov     [rbp+50h+var_72], r12w
0x180037c38  mov     [rbp+50h+var_80], r12w
0x180037c3d  call    ?_DetermineDialString@PhoneController@@AEAAJPEBGPEBUOLITEMID@@KPEAVPhoneLine@@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; PhoneController::_DetermineDialString(ushort const *,OLITEMID const *,ulong,PhoneLine *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180037c42  mov     r12d, eax
0x180037c45  test    eax, eax
0x180037c47  jns     loc_180037CCD
0x180037c4d  mov     edx, eax; int
0x180037c4f  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180037c54  mov     r9d, 148Bh
0x180037c5a  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180037c61  mov     edx, esi
0x180037c63  mov     ecx, r12d
0x180037c66  call    Log_HREvent_7
0x180037c6b  mov     rcx, [rbp+50h+Block]; Block
0x180037c6f  lea     rax, [rbp+50h+var_80]
0x180037c73  cmp     rcx, rax
0x180037c76  jz      short loc_180037C84
0x180037c78  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180037c7f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180037c84  mov     rcx, [rbp+50h+var_70]; Block
0x180037c88  lea     rax, [rbp+50h+var_60]
  ... truncated ...
```
