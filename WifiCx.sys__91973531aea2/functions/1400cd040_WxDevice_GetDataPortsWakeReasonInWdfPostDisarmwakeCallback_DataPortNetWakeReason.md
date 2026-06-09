# WxDevice::GetDataPortsWakeReasonInWdfPostDisarmwakeCallback(DataPortNetWakeReason *)

- ea: `0x1400cd040`
- end: `0x1400cd401`
- name: `?GetDataPortsWakeReasonInWdfPostDisarmwakeCallback@WxDevice@@QEAAJPEAUDataPortNetWakeReason@@@Z`
- size: `961`
- prototype: `__int64 __fastcall(WxDevice *__hidden this, struct DataPortNetWakeReason *)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400d6f94`
- `0x1400d9b7c`

## callees

- `0x140009420`
- `0x14000c778`
- `0x14001a1e0`
- `0x14001a20c`
- `0x14001dec0`
- `0x14002b148`
- `0x1400520a8`
- `0x140053f90`
- `0x1400592e8`
- `0x1400685d4`
- `0x140069494`
- `0x1400cd040`
- `0x1400dfd40`

## string_xrefs

- `0x1400cd35a`: `completionNotifier`

## pseudocode

```c
__int64 __fastcall WxDevice::GetDataPortsWakeReasonInWdfPostDisarmwakeCallback(
        WxDevice *this,
        struct DataPortNetWakeReason *a2)
{
  int v4; // edx
  CJobBase *v5; // rdi
  int v6; // r8d
  unsigned int NextActivityId; // eax
  __int64 v8; // r8
  int v9; // edx
  unsigned int v10; // esi
  void (__fastcall *v11)(CJobBase *, __int64); // rax
  struct IOperationCompletionCallback *v13; // rax
  int v14; // edx
  int v15; // r8d
  struct IOperationCompletionCallback *v16; // r14
  int v17; // ebx
  int v18; // edx
  int v19; // edx
  int v20; // edx
  int v21; // ecx
  struct IOperationCompletionCallback *v22; // [rsp+30h] [rbp-20h] BYREF
  __int64 *v23; // [rsp+38h] [rbp-18h] BYREF
  struct IEventContext *v24; // [rsp+40h] [rbp-10h] BYREF
  char v25; // [rsp+48h] [rbp-8h]
  int v26; // [rsp+90h] [rbp+40h] BYREF
  __int64 v27; // [rsp+98h] [rbp+48h] BYREF

  *(_QWORD *)a2 = 0;
  *((_DWORD *)a2 + 2) = 0;
  v5 = (CJobBase *)operator new(0x230u);
  if ( !v5 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 2;
      WPP_RECORDER_SF_s(
        WPP_GLOBAL_Control->DeviceExtension,
        v4,
        v6,
        55,
        (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
        (__int64)"getDataPortWakeReasonJob");
    }
    return 3221225626LL;
  }
  NextActivityId = IActivityId::get_NextActivityId();
  CJobBase::CJobBase(v5, NextActivityId);
  *((_QWORD *)v5 + 67) = 0;
  *(_QWORD *)v5 = &CNetAdapterGetDataPathWakeReasonJob::`vftable'{for `IOperationCompletionCallback'};
  *((_QWORD *)v5 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
  *((_DWORD *)v5 + 136) = 0;
  *((_QWORD *)v5 + 69) = 0;
  *((_BYTE *)v5 + 42) = 1;
  if ( (unsigned int)CNetAdapterGetDataPathWakeReasonJob::InitializeFromWdfCallback(v5, (char *)this + 56, v8, a2) )
  {
    v10 = -1073741823;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        1,
        56,
        (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
        -1073741823);
    }
    v11 = *(void (__fastcall **)(CJobBase *, __int64))(*(_QWORD *)v5 + 40LL);
LABEL_6:
    v11(v5, 1);
    return v10;
  }
  *((_BYTE *)v5 + 507) = 0;
  v13 = (struct IOperationCompletionCallback *)operator new(0x18u);
  v16 = v13;
  if ( !v13 )
  {
    v22 = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_s(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        v15,
        57,
        (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
        (__int64)"completionNotifier");
    }
    wistd::unique_ptr<CJobCompleteNotifier,wistd::default_delete<CJobCompleteNotifier>>::reset(&v22, 0);
    (*(void (__fastcall **)(CJobBase *, __int64))(*(_QWORD *)v5 + 40LL))(v5, 1);
    return 3221225626LL;
  }
  *((_QWORD *)v13 + 1) = 0;
  *(_QWORD *)v13 = &CJobCompleteNotifier::`vftable';
  *((_QWORD *)v13 + 2) = 0;
  v23 = &v27;
  v22 = v13;
  v27 = 0;
  v24 = 0;
  v25 = 1;
  v10 = -1073741823;
  v17 = IEventContext::CreateInstance(&v24);
  wil::details::out_param_t<wistd::unique_ptr<IEventContext,wistd::default_delete<IEventContext>>>::~out_param_t<wistd::unique_ptr<IEventContext,wistd::default_delete<IEventContext>>>(&v23);
  if ( !v17 )
  {
    v26 = 0;
    *((_QWORD *)v16 + 1) = v27;
    *((_QWORD *)v16 + 2) = &v26;
    if ( (unsigned int)ActiveJobsList::StartAddNewJob((WxDevice *)((char *)this + 984), v5, v16, 0) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v19) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v19,
          1,
          60,
          (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
          -1073741823,
          v22,
          v23);
      }
    }
    else
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 24LL))(v27);
      v21 = v26;
      if ( !v26 )
        goto LABEL_20;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v20) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v20,
          1,
          61,
          (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
          v26);
        v21 = v26;
      }
      if ( !v21 )
LABEL_20:
        v10 = 0;
    }
    wistd::unique_ptr<IEventContext,wistd::default_delete<IEventContext>>::reset(&v27, 0);
    wistd::unique_ptr<CJobCompleteNotifier,wistd::default_delete<CJobCompleteNotifier>>::reset(&v22, 0);
    v11 = *(void (__fastcall **)(CJobBase *, __int64))(*(_QWORD *)v5 + 40LL);
    goto LABEL_6;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v18) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v18,
      1,
      58,
      (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
      v17 != 0 ? 0xC0000001 : 0,
      v22,
      v23);
  }
  wistd::unique_ptr<IEventContext,wistd::default_delete<IEventContext>>::reset(&v27, 0);
  wistd::unique_ptr<CJobCompleteNotifier,wistd::default_delete<CJobCompleteNotifier>>::reset(&v22, 0);
  (*(void (__fastcall **)(CJobBase *, __int64))(*(_QWORD *)v5 + 40LL))(v5, 1);
  return v17 != 0 ? 0xC0000001 : 0;
}

```

## disassembly

```asm
0x1400cd040  mov     [rsp-28h+arg_0], rbx
0x1400cd045  mov     [rsp-28h+arg_8], rsi
0x1400cd04a  push    rbp
0x1400cd04b  push    rdi
0x1400cd04c  push    r13
0x1400cd04e  push    r14
0x1400cd050  push    r15
0x1400cd052  mov     rbp, rsp
0x1400cd055  sub     rsp, 50h
0x1400cd059  xor     eax, eax
0x1400cd05b  mov     r13, rcx
0x1400cd05e  mov     [rdx], rax
0x1400cd061  mov     ecx, 230h; unsigned __int64
0x1400cd066  mov     [rdx+8], eax
0x1400cd069  mov     rbx, rdx
0x1400cd06c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400cd071  mov     rdi, rax
0x1400cd074  test    rax, rax
0x1400cd077  jz      loc_1400CD3A2
0x1400cd07d  call    ?get_NextActivityId@IActivityId@@SAKXZ; IActivityId::get_NextActivityId(void)
0x1400cd082  mov     edx, eax; unsigned int
0x1400cd084  mov     rcx, rdi; this
0x1400cd087  call    ??0CJobBase@@IEAA@K@Z; CJobBase::CJobBase(ulong)
0x1400cd08c  lea     rcx, ??_7CNetAdapterGetDataPathWakeReasonJob@@6BIOperationCompletionCallback@@@; const CNetAdapterGetDataPathWakeReasonJob::`vftable'{for `IOperationCompletionCallback'}
0x1400cd093  mov     qword ptr [rdi+218h], 0
0x1400cd09e  mov     [rdi], rcx
0x1400cd0a1  lea     rax, ??_7CSetStaAssociationIEsJob@@6BIEventQueueCallback@@@; const CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'}
0x1400cd0a8  mov     r15d, 1
0x1400cd0ae  mov     [rdi+8], rax
0x1400cd0b2  mov     rcx, rdi
0x1400cd0b5  mov     dword ptr [rdi+220h], 0
0x1400cd0bf  lea     rdx, [r13+38h]
0x1400cd0c3  mov     qword ptr [rdi+228h], 0
0x1400cd0ce  mov     r9, rbx
0x1400cd0d1  mov     [rdi+2Ah], r15b
0x1400cd0d5  call    ?InitializeFromWdfCallback@CNetAdapterGetDataPathWakeReasonJob@@QEAAHPEAVCAdapter@@W4_WFC_PORT_TYPE@@PEAUDataPortNetWakeReason@@@Z; CNetAdapterGetDataPathWakeReasonJob::InitializeFromWdfCallback(CAdapter *,_WFC_PORT_TYPE,DataPortNetWakeReason *)
0x1400cd0da  test    eax, eax
0x1400cd0dc  jz      short loc_1400CD135
0x1400cd0de  lea     rax, WPP_RECORDER_INITIALIZED
0x1400cd0e5  mov     esi, 0C0000001h
0x1400cd0ea  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400cd0f1  jz      short loc_1400CD11C
0x1400cd0f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cd0fa  lea     rax, WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids
0x1400cd101  lea     r9d, [r15+37h]
0x1400cd105  mov     dword ptr [rsp+50h+var_28], esi
0x1400cd109  mov     r8d, r15d
0x1400cd10c  mov     [rsp+50h+var_30], rax
0x1400cd111  mov     dl, 2
0x1400cd113  mov     rcx, [rcx+40h]
0x1400cd117  call    WPP_RECORDER_SF_d
0x1400cd11c  mov     rax, [rdi]
0x1400cd11f  mov     edx, r15d
0x1400cd122  mov     rax, [rax+28h]
0x1400cd126  mov     rcx, rdi
0x1400cd129  call    _guard_dispatch_icall
0x1400cd12e  mov     eax, esi
0x1400cd130  jmp     loc_1400CD3E7
0x1400cd135  mov     ecx, 18h; unsigned __int64
0x1400cd13a  mov     byte ptr [rdi+1FBh], 0
0x1400cd141  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400cd146  mov     r14, rax
0x1400cd149  test    rax, rax
0x1400cd14c  jz      loc_1400CD33B
0x1400cd152  lea     rax, ??_7CJobCompleteNotifier@@6B@; const CJobCompleteNotifier::`vftable'
0x1400cd159  mov     qword ptr [r14+8], 0
0x1400cd161  mov     [r14], rax
0x1400cd164  lea     rcx, [rbp+var_10]; struct IEventContext **
0x1400cd168  lea     rax, [rbp+arg_18]
0x1400cd16c  mov     qword ptr [r14+10h], 0
0x1400cd174  mov     [rbp+var_18], rax
0x1400cd178  mov     [rbp+var_20], r14
0x1400cd17c  mov     [rbp+arg_18], 0
0x1400cd184  mov     [rbp+var_10], 0
0x1400cd18c  mov     [rbp+var_8], r15b
0x1400cd190  call    ?CreateInstance@IEventContext@@SAHPEAPEAV1@@Z; IEventContext::CreateInstance(IEventContext * *)
0x1400cd195  mov     ecx, eax
0x1400cd197  mov     esi, 0C0000001h
0x1400cd19c  neg     ecx
0x1400cd19e  mov     ebx, eax
0x1400cd1a0  lea     rcx, [rbp+var_18]
0x1400cd1a4  sbb     r15d, r15d
0x1400cd1a7  and     r15d, esi
0x1400cd1aa  call    ??1?$out_param_t@V?$unique_ptr@VIEventContext@@U?$default_delete@VIEventContext@@@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<IEventContext,wistd::default_delete<IEventContext>>>::~out_param_t<wistd::unique_ptr<IEventContext,wistd::default_delete<IEventContext>>>(void)
0x1400cd1af  test    ebx, ebx
0x1400cd1b1  jz      short loc_1400CD222
0x1400cd1b3  lea     rax, WPP_RECORDER_INITIALIZED
0x1400cd1ba  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400cd1c1  jz      short loc_1400CD1F0
0x1400cd1c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cd1ca  lea     rax, WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids
0x1400cd1d1  mov     r9d, 3Ah ; ':'
0x1400cd1d7  mov     dword ptr [rsp+50h+var_28], r15d
0x1400cd1dc  mov     dl, 2
0x1400cd1de  mov     [rsp+50h+var_30], rax
0x1400cd1e3  mov     rcx, [rcx+40h]
0x1400cd1e7  lea     r8d, [r9-39h]
0x1400cd1eb  call    WPP_RECORDER_SF_d
0x1400cd1f0  xor     edx, edx
0x1400cd1f2  lea     rcx, [rbp+arg_18]
0x1400cd1f6  call    ?reset@?$unique_ptr@VIEventContext@@U?$default_delete@VIEventContext@@@wistd@@@wistd@@QEAAXPEAVIEventContext@@@Z; wistd::unique_ptr<IEventContext,wistd::default_delete<IEventContext>>::reset(IEventContext *)
0x1400cd1fb  xor     edx, edx
0x1400cd1fd  lea     rcx, [rbp+var_20]
0x1400cd201  call    ?reset@?$unique_ptr@VCJobCompleteNotifier@@U?$default_delete@VCJobCompleteNotifier@@@wistd@@@wistd@@QEAAXPEAVCJobCompleteNotifier@@@Z; wistd::unique_ptr<CJobCompleteNotifier,wistd::default_delete<CJobCompleteNotifier>>::reset(CJobCompleteNotifier *)
0x1400cd206  mov     rcx, [rdi]
0x1400cd209  mov     edx, 1
0x1400cd20e  mov     rax, [rcx+28h]
0x1400cd212  mov     rcx, rdi
0x1400cd215  call    _guard_dispatch_icall
0x1400cd21a  mov     eax, r15d
0x1400cd21d  jmp     loc_1400CD3E7
0x1400cd222  mov     rax, [rbp+arg_18]
0x1400cd226  lea     rcx, [r13+3D8h]; this
0x1400cd22d  mov     [rbp+arg_10], 0
0x1400cd234  xor     r9d, r9d; void *
0x1400cd237  mov     [r14+8], rax
0x1400cd23b  mov     r8, r14; struct IOperationCompletionCallback *
0x1400cd23e  lea     rax, [rbp+arg_10]
0x1400cd242  mov     rdx, rdi; struct CJobBase *
0x1400cd245  mov     [r14+10h], rax
0x1400cd249  call    ?StartAddNewJob@ActiveJobsList@@QEAAHPEAVCJobBase@@PEAVIOperationCompletionCallback@@PEAX@Z; ActiveJobsList::StartAddNewJob(CJobBase *,IOperationCompletionCallback *,void *)
0x1400cd24e  test    eax, eax
0x1400cd250  jz      short loc_1400CD2B5
0x1400cd252  lea     rax, WPP_RECORDER_INITIALIZED
0x1400cd259  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400cd260  jz      short loc_1400CD28E
0x1400cd262  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cd269  lea     rax, WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids
0x1400cd270  mov     r9d, 3Ch ; '<'
0x1400cd276  mov     dword ptr [rsp+50h+var_28], esi
0x1400cd27a  mov     dl, 2
0x1400cd27c  mov     [rsp+50h+var_30], rax
0x1400cd281  mov     rcx, [rcx+40h]
0x1400cd285  lea     r8d, [r9-3Bh]
0x1400cd289  call    WPP_RECORDER_SF_d
0x1400cd28e  xor     edx, edx
0x1400cd290  lea     rcx, [rbp+arg_18]
0x1400cd294  call    ?reset@?$unique_ptr@VIEventContext@@U?$default_delete@VIEventContext@@@wistd@@@wistd@@QEAAXPEAVIEventContext@@@Z; wistd::unique_ptr<IEventContext,wistd::default_delete<IEventContext>>::reset(IEventContext *)
0x1400cd299  xor     edx, edx
0x1400cd29b  lea     rcx, [rbp+var_20]
0x1400cd29f  call    ?reset@?$unique_ptr@VCJobCompleteNotifier@@U?$default_delete@VCJobCompleteNotifier@@@wistd@@@wistd@@QEAAXPEAVCJobCompleteNotifier@@@Z; wistd::unique_ptr<CJobCompleteNotifier,wistd::default_delete<CJobCompleteNotifier>>::reset(CJobCompleteNotifier *)
0x1400cd2a4  mov     rax, [rdi]
0x1400cd2a7  mov     rax, [rax+28h]
0x1400cd2ab  mov     edx, 1
0x1400cd2b0  jmp     loc_1400CD126
0x1400cd2b5  mov     rcx, [rbp+arg_18]
0x1400cd2b9  mov     [rbp+var_20], 0
0x1400cd2c1  mov     rax, [rcx]
0x1400cd2c4  mov     rax, [rax+18h]
0x1400cd2c8  call    _guard_dispatch_icall
0x1400cd2cd  mov     ecx, [rbp+arg_10]
0x1400cd2d0  test    ecx, ecx
0x1400cd2d2  jz      short loc_1400CD317
0x1400cd2d4  lea     rax, WPP_RECORDER_INITIALIZED
0x1400cd2db  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400cd2e2  jz      short loc_1400CD313
0x1400cd2e4  mov     dword ptr [rsp+50h+var_28], ecx
0x1400cd2e8  lea     rax, WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids
0x1400cd2ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cd2f6  mov     r9d, 3Dh ; '='
0x1400cd2fc  mov     dl, 2
0x1400cd2fe  mov     [rsp+50h+var_30], rax
0x1400cd303  mov     rcx, [rcx+40h]
0x1400cd307  lea     r8d, [r9-3Ch]
0x1400cd30b  call    WPP_RECORDER_SF_d
0x1400cd310  mov     ecx, [rbp+arg_10]
0x1400cd313  test    ecx, ecx
0x1400cd315  jnz     short loc_1400CD319
0x1400cd317  xor     esi, esi
0x1400cd319  xor     edx, edx
0x1400cd31b  lea     rcx, [rbp+arg_18]
0x1400cd31f  call    ?reset@?$unique_ptr@VIEventContext@@U?$default_delete@VIEventContext@@@wistd@@@wistd@@QEAAXPEAVIEventContext@@@Z; wistd::unique_ptr<IEventContext,wistd::default_delete<IEventContext>>::reset(IEventContext *)
0x1400cd324  xor     edx, edx
0x1400cd326  lea     rcx, [rbp+var_20]
0x1400cd32a  call    ?reset@?$unique_ptr@VCJobCompleteNotifier@@U?$default_delete@VCJobCompleteNotifier@@@wistd@@@wistd@@QEAAXPEAVCJobCompleteNotifier@@@Z; wistd::unique_ptr<CJobCompleteNotifier,wistd::default_delete<CJobCompleteNotifier>>::reset(CJobCompleteNotifier *)
0x1400cd32f  mov     rcx, [rdi]
0x1400cd332  mov     rax, [rcx+28h]
0x1400cd336  jmp     loc_1400CD2AB
0x1400cd33b  mov     [rbp+var_20], 0
0x1400cd343  lea     rax, WPP_RECORDER_INITIALIZED
0x1400cd34a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400cd351  jz      short loc_1400CD383
0x1400cd353  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cd35a  lea     rax, aCompletionnoti; "completionNotifier"
0x1400cd361  mov     [rsp+50h+var_28], rax
0x1400cd366  mov     r9d, 39h ; '9'
0x1400cd36c  lea     rax, WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids
0x1400cd373  mov     dl, 2
0x1400cd375  mov     [rsp+50h+var_30], rax
0x1400cd37a  mov     rcx, [rcx+40h]
0x1400cd37e  call    WPP_RECORDER_SF_s
0x1400cd383  xor     edx, edx
0x1400cd385  lea     rcx, [rbp+var_20]
0x1400cd389  call    ?reset@?$unique_ptr@VCJobCompleteNotifier@@U?$default_delete@VCJobCompleteNotifier@@@wistd@@@wistd@@QEAAXPEAVCJobCompleteNotifier@@@Z; wistd::unique_ptr<CJobCompleteNotifier,wistd::default_delete<CJobCompleteNotifier>>::reset(CJobCompleteNotifier *)
0x1400cd38e  mov     rax, [rdi]
0x1400cd391  mov     edx, r15d
0x1400cd394  mov     rcx, rdi
0x1400cd397  mov     rax, [rax+28h]
0x1400cd39b  call    _guard_dispatch_icall
0x1400cd3a0  jmp     short loc_1400CD3E2
0x1400cd3a2  lea     rax, WPP_RECORDER_INITIALIZED
0x1400cd3a9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400cd3b0  jz      short loc_1400CD3E2
0x1400cd3b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cd3b9  lea     rax, aGetdataportwak; "getDataPortWakeReasonJob"
0x1400cd3c0  mov     [rsp+50h+var_28], rax
0x1400cd3c5  mov     r9d, 37h ; '7'
0x1400cd3cb  lea     rax, WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids
0x1400cd3d2  mov     dl, 2
0x1400cd3d4  mov     [rsp+50h+var_30], rax
0x1400cd3d9  mov     rcx, [rcx+40h]
0x1400cd3dd  call    WPP_RECORDER_SF_s
0x1400cd3e2  mov     eax, 0C000009Ah
0x1400cd3e7  lea     r11, [rsp+50h+var_s0]
0x1400cd3ec  mov     rbx, [r11+30h]
0x1400cd3f0  mov     rsi, [r11+38h]
0x1400cd3f4  mov     rsp, r11
0x1400cd3f7  pop     r15
0x1400cd3f9  pop     r14
0x1400cd3fb  pop     r13
0x1400cd3fd  pop     rdi
0x1400cd3fe  pop     rbp
0x1400cd3ff  retn
```
