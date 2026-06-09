# CEffectCompilationService::BeginCompile(CCompiledEffectTemplate *,Windows::UI::Composition::IEffectDescription *,CEffectCompilationTask * *)

- ea: `0x1800f8708`
- end: `0x1800f8b5d`
- name: `?BeginCompile@CEffectCompilationService@@QEAAJPEAVCCompiledEffectTemplate@@PEAUIEffectDescription@Composition@UI@Windows@@PEAPEAVCEffectCompilationTask@@@Z`
- size: `1109`
- prototype: `__int64 __fastcall(CEffectCompilationService *__hidden this, struct CCompiledEffectTemplate *, struct Windows::UI::Composition::IEffectDescription *, struct CEffectCompilationTask **)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800f83f4`

## callees

- `0x180035124`
- `0x18003e2ec`
- `0x180040a20`
- `0x180042de0`
- `0x180048ac0`
- `0x1800c75bc`
- `0x1800f8708`
- `0x1800f8b64`
- `0x1800f8c10`
- `0x18014b6cc`
- `0x1801bf108`
- `0x1801e3418`
- `0x1801efe50`
- `0x180204100`
- `0x18021bfb4`
- `0x1802341b8`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f8879`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f894d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f8879`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f894d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f87f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f87f2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800f8869`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800f8869`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f8888`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f8888`

## pseudocode

```c
__int64 __fastcall CEffectCompilationService::BeginCompile(
        CEffectCompilationService *this,
        struct CCompiledEffectTemplate *a2,
        struct Windows::UI::Composition::IEffectDescription *a3,
        struct CEffectCompilationTask **a4)
{
  __int64 v4; // rax
  PTP_WORK *v6; // rdi
  CNotificationResource *v8; // r12
  char *v9; // r13
  __int64 v10; // rdx
  __int64 v11; // rcx
  _QWORD *v12; // rbx
  _QWORD *v13; // r12
  PTP_WORK *v14; // rbx
  unsigned __int8 v15; // r13
  int v16; // eax
  int v17; // ebx
  __int64 *v18; // r15
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rcx
  unsigned int v22; // edx
  int v23; // esi
  __int64 v24; // r9
  __int64 v25; // r8
  __int64 v26; // rcx
  struct CEffectCompilationTask *v27; // rax
  unsigned int v29; // eax
  int v30; // r9d
  CEffectCompilationTask *v31; // rax
  CEffectCompilationTask *v32; // rax
  int v33; // eax
  __int64 v34; // rax
  int (__fastcall *v35)(struct Windows::UI::Composition::IEffectDescription *, PVOID *); // rbx
  const char *v36; // r15
  PVOID v37; // rcx
  char v38; // bl
  unsigned int ChannelCallbackId; // eax
  int v40; // edx
  int v41; // eax
  _QWORD v42[2]; // [rsp+40h] [rbp-28h] BYREF
  char v43[24]; // [rsp+50h] [rbp-18h] BYREF
  void *retaddr; // [rsp+A8h] [rbp+40h]
  PVOID pv; // [rsp+B0h] [rbp+48h] BYREF
  struct CCompiledEffectTemplate *v46; // [rsp+B8h] [rbp+50h]
  char *v47; // [rsp+C0h] [rbp+58h]
  struct CEffectCompilationTask **v48; // [rsp+C8h] [rbp+60h]

  v48 = a4;
  v46 = a2;
  v4 = *(_QWORD *)a3;
  v6 = 0;
  v42[1] = a3;
  pv = 0;
  v8 = a2;
  v9 = (char *)this + 96;
  v42[0] = (*(__int64 (__fastcall **)(struct Windows::UI::Composition::IEffectDescription *))(v4 + 104))(a3);
  v10 = *((_QWORD *)this + 15);
  v11 = 2LL * (v42[0] & *((_QWORD *)this + 18));
  v47 = (char *)this + 96;
  v12 = *(_QWORD **)(v10 + 8 * v11 + 8);
  if ( v12 == *((_QWORD **)this + 13) )
  {
LABEL_7:
    v12 = 0;
    goto LABEL_8;
  }
  v13 = *(_QWORD **)(v10 + 8 * v11);
  while ( 1 )
  {
    if ( v42[0] != v12[2] )
      goto LABEL_4;
    if ( (*(unsigned __int8 (__fastcall **)(struct Windows::UI::Composition::IEffectDescription *, _QWORD))(*(_QWORD *)a3 + 96LL))(
           a3,
           v12[3]) )
    {
      break;
    }
    MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_4:
    if ( v12 == v13 )
    {
      v8 = v46;
      goto LABEL_7;
    }
    v12 = (_QWORD *)v12[1];
  }
  v8 = v46;
LABEL_8:
  if ( !v12 )
    v12 = (_QWORD *)*((_QWORD *)this + 13);
  if ( v12 == *((_QWORD **)this + 13) )
  {
    v31 = (CEffectCompilationTask *)DefaultHeap::AllocClear(0x68u);
    if ( !v31 )
      ModuleFailFastForHRESULT(-2147024882, retaddr);
    v32 = CEffectCompilationTask::CEffectCompilationTask(v31, this, a3);
    Microsoft::WRL::ComPtr<CManipulationContext>::operator=(&pv, v32);
    v6 = (PTP_WORK *)pv;
    if ( !pv )
    {
      v17 = -2147024882;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024882, 0x70u, 0);
      goto LABEL_31;
    }
    if ( CCommonRegistryData::EnableEffectCaching )
      std::_Hash<std::_Umap_traits<EffectDescriptionKey,CEffectCompilationTask *,std::_Uhash_compare<EffectDescriptionKey,std::hash<EffectDescriptionKey>,std::equal_to<EffectDescriptionKey>>,std::allocator<std::pair<EffectDescriptionKey const,CEffectCompilationTask *>>,0>>::emplace<EffectDescriptionKey &,CEffectCompilationTask *>(
        (char *)this + 96,
        v43,
        v42,
        &pv);
    v33 = CEffectCompilationTask::Initialize(v6);
    v17 = v33;
    if ( v33 >= 0 )
    {
      v15 = 0;
      goto LABEL_14;
    }
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v33, 0x77u, 0);
  }
  else
  {
    v14 = (PTP_WORK *)v12[4];
    v15 = 1;
    if ( v14 )
    {
      (*(void (__fastcall **)(PTP_WORK *))*v14)(v14);
      v6 = v14;
    }
    CEffectCompilationService::TryReviveDeadTask(this, (const struct CEffectCompilationTask *)v6);
LABEL_14:
    if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x10) != 0 )
    {
      v34 = *(_QWORD *)a3;
      pv = 0;
      v35 = *(int (__fastcall **)(struct Windows::UI::Composition::IEffectDescription *, PVOID *))(v34 + 88);
      Microsoft::WRL::ComPtr<CBrushRenderingGraph>::InternalRelease(&pv);
      if ( v35(a3, &pv) >= 0 )
        v36 = (const char *)(*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)pv + 16LL))(pv);
      else
        v36 = "null";
      if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x10) != 0 )
      {
        v38 = (*(__int64 (__fastcall **)(struct Windows::UI::Composition::IEffectDescription *))(*(_QWORD *)a3 + 32LL))(a3);
        (*(void (__fastcall **)(struct Windows::UI::Composition::IEffectDescription *))(*(_QWORD *)a3 + 80LL))(a3);
        ChannelCallbackId = CNotificationResource::GetChannelCallbackId(v8);
        McTemplateU0pdsddt_EventWriteTransfer(v15, v40, (_DWORD)v6, ChannelCallbackId, (__int64)v36, v40, v38, v15);
      }
      v37 = pv;
      if ( pv )
      {
        pv = 0;
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)v37 + 8LL))(v37);
      }
    }
    v16 = CEffectCompilationTask::AddTemplate_RenderThread((CEffectCompilationTask *)v6, v8);
    v17 = v16;
    if ( v16 >= 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      v18 = (__int64 *)((char *)this + 64);
      v19 = 0;
      v20 = *((_QWORD *)this + 8);
      v21 = *((unsigned int *)this + 22);
      while ( (unsigned int)v19 < (unsigned int)v21 )
      {
        if ( v6 == *(PTP_WORK **)(v20 + 8 * v19) )
          goto LABEL_26;
        v19 = (unsigned int)(v19 + 1);
      }
      v22 = v21 + 1;
      pv = v6;
      if ( (int)v21 + 1 < (unsigned int)v21 )
      {
        v17 = -2147024362;
        v29 = 183;
        v23 = -2147024362;
        v30 = -2147024362;
      }
      else
      {
        if ( v22 <= *((_DWORD *)this + 21) )
        {
          *(_QWORD *)(v20 + 8 * v21) = v6;
          v23 = 0;
          *((_DWORD *)this + 22) = v22;
LABEL_23:
          if ( *((_BYTE *)v6 + 96) )
          {
            v24 = *v18;
            v25 = *((unsigned int *)this + 50);
            v26 = *(_QWORD *)(*v18 + 8LL * (unsigned int)(*((_DWORD *)this + 22) - 1));
            *(_QWORD *)(v24 + 8LL * (unsigned int)(*((_DWORD *)this + 22) - 1)) = *(_QWORD *)(*v18 + 8 * v25);
            *(_QWORD *)(v24 + 8 * v25) = v26;
            ++*((_DWORD *)this + 50);
            SetEvent(*((HANDLE *)this + 7));
          }
          v17 = v23;
LABEL_26:
          if ( this != (CEffectCompilationService *)-16LL )
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
          if ( !v15 )
            SubmitThreadpoolWork(v6[8]);
          v27 = (struct CEffectCompilationTask *)v6;
          v6 = 0;
          *v48 = v27;
          if ( v17 < 0 )
            goto LABEL_35;
LABEL_31:
          if ( v6 )
            (*((void (__fastcall **)(PTP_WORK *))*v6 + 1))(v6);
          return (unsigned int)v17;
        }
        v41 = DynArrayImpl<0>::AddMultipleAndSet((char *)this + 64, 8, 1, &pv);
        v23 = v41;
        if ( v41 >= 0 )
          goto LABEL_23;
        v17 = v41;
        v30 = v41;
        v29 = 194;
      }
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v30, v29, 0);
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v23, 0x9Cu, 0);
      if ( this != (CEffectCompilationService *)-16LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      goto LABEL_35;
    }
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v16, 0x94u, 0);
LABEL_35:
    v9 = v47;
  }
  if ( v6 )
  {
    std::_Hash<std::_Umap_traits<EffectDescriptionKey,CEffectCompilationTask *,std::_Uhash_compare<EffectDescriptionKey,std::hash<EffectDescriptionKey>,std::equal_to<EffectDescriptionKey>>,std::allocator<std::pair<EffectDescriptionKey const,CEffectCompilationTask *>>,0>>::_Erase<EffectDescriptionKey>(
      v9,
      v42);
    goto LABEL_31;
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800f8708  mov     [rsp-40h+arg_18], r9
0x1800f870d  mov     [rsp-40h+arg_8], rdx
0x1800f8712  push    rbp
0x1800f8713  push    rbx
0x1800f8714  push    rsi
0x1800f8715  push    rdi
0x1800f8716  push    r12
0x1800f8718  push    r13
0x1800f871a  push    r14
0x1800f871c  push    r15
0x1800f871e  mov     rbp, rsp
0x1800f8721  sub     rsp, 68h
0x1800f8725  mov     rax, [r8]
0x1800f8728  mov     r14, rcx
0x1800f872b  xor     edi, edi
0x1800f872d  mov     [rbp+var_20], r8
0x1800f8731  mov     rcx, r8
0x1800f8734  mov     [rbp+pv], rdi
0x1800f8738  mov     rsi, r8
0x1800f873b  mov     r12, rdx
0x1800f873e  mov     rax, [rax+68h]
0x1800f8742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8747  lea     r13, [r14+60h]
0x1800f874b  mov     [rbp+var_28], rax
0x1800f874f  mov     rcx, [r13+30h]
0x1800f8753  mov     r15, rax
0x1800f8756  mov     rdx, [r13+18h]
0x1800f875a  and     rcx, rax
0x1800f875d  add     rcx, rcx
0x1800f8760  mov     [rbp+arg_10], r13
0x1800f8764  mov     rbx, [rdx+rcx*8+8]
0x1800f8769  cmp     rbx, [r13+8]
0x1800f876d  jz      short loc_1800F878C
0x1800f876f  mov     r12, [rdx+rcx*8]
0x1800f8773  cmp     r15, [rbx+10h]
0x1800f8777  jz      loc_1800F8AD0
0x1800f877d  cmp     rbx, r12
0x1800f8780  jz      short loc_1800F8788
0x1800f8782  mov     rbx, [rbx+8]
0x1800f8786  jmp     short loc_1800F8773
0x1800f8788  mov     r12, [rbp+arg_8]
0x1800f878c  xor     ebx, ebx
0x1800f878e  test    rbx, rbx
0x1800f8791  jz      loc_1800F8AFA
0x1800f8797  cmp     rbx, [r14+68h]
0x1800f879b  jz      loc_1800F8955
0x1800f87a1  mov     rbx, [rbx+20h]
0x1800f87a5  mov     r13b, 1
0x1800f87a8  test    rbx, rbx
0x1800f87ab  jz      short loc_1800F87BE
0x1800f87ad  mov     rax, [rbx]
0x1800f87b0  mov     rcx, rbx
0x1800f87b3  mov     rax, [rax]
0x1800f87b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f87bb  mov     rdi, rbx
0x1800f87be  mov     rdx, rdi; struct CEffectCompilationTask *
0x1800f87c1  mov     rcx, r14; this
0x1800f87c4  call    ?TryReviveDeadTask@CEffectCompilationService@@AEAAXPEBVCEffectCompilationTask@@@Z; CEffectCompilationService::TryReviveDeadTask(CEffectCompilationTask const *)
0x1800f87c9  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 10h
0x1800f87d0  jnz     loc_1800F89B6
0x1800f87d6  mov     rdx, r12; struct CCompiledEffectTemplate *
0x1800f87d9  mov     rcx, rdi; this
0x1800f87dc  call    ?AddTemplate_RenderThread@CEffectCompilationTask@@AEAAJPEAVCCompiledEffectTemplate@@@Z; CEffectCompilationTask::AddTemplate_RenderThread(CCompiledEffectTemplate *)
0x1800f87e1  mov     ebx, eax
0x1800f87e3  test    eax, eax
0x1800f87e5  js      loc_1800F88C5
0x1800f87eb  lea     r12, [r14+10h]
0x1800f87ef  mov     rcx, r12; lpCriticalSection
0x1800f87f2  call    cs:__imp_EnterCriticalSection
0x1800f87f8  lea     r15, [r14+40h]
0x1800f87fc  xor     edx, edx
0x1800f87fe  mov     r8, [r15]
0x1800f8801  mov     ecx, [r15+18h]
0x1800f8805  cmp     edx, ecx
0x1800f8807  jnb     short loc_1800F8813
0x1800f8809  cmp     rdi, [r8+rdx*8]
0x1800f880d  jz      short loc_1800F8871
0x1800f880f  inc     edx
0x1800f8811  jmp     short loc_1800F8805
0x1800f8813  lea     edx, [rcx+1]
0x1800f8816  mov     [rbp+pv], rdi
0x1800f881a  cmp     edx, ecx
0x1800f881c  jb      loc_1800F88FD
0x1800f8822  cmp     edx, [r15+14h]
0x1800f8826  ja      loc_1800F8B2F
0x1800f882c  mov     [r8+rcx*8], rdi
0x1800f8830  xor     esi, esi
0x1800f8832  mov     [r15+18h], edx
0x1800f8836  cmp     byte ptr [rdi+60h], 0
0x1800f883a  jz      short loc_1800F886F
0x1800f883c  mov     r9, [r15]
0x1800f883f  mov     ecx, [r14+58h]
0x1800f8843  mov     r8d, [r14+0C8h]
0x1800f884a  dec     ecx
0x1800f884c  mov     edx, ecx
0x1800f884e  mov     rcx, [r9+rcx*8]
0x1800f8852  mov     rax, [r9+r8*8]
0x1800f8856  mov     [r9+rdx*8], rax
0x1800f885a  mov     [r9+r8*8], rcx
0x1800f885e  inc     dword ptr [r14+0C8h]
0x1800f8865  mov     rcx, [r14+38h]; hEvent
0x1800f8869  call    cs:__imp_SetEvent
0x1800f886f  mov     ebx, esi
0x1800f8871  test    r12, r12
0x1800f8874  jz      short loc_1800F887F
0x1800f8876  mov     rcx, r12; lpCriticalSection
0x1800f8879  call    cs:__imp_LeaveCriticalSection
0x1800f887f  test    r13b, r13b
0x1800f8882  jnz     short loc_1800F888E
0x1800f8884  mov     rcx, [rdi+40h]; pwk
0x1800f8888  call    cs:__imp_SubmitThreadpoolWork
0x1800f888e  mov     rcx, [rbp+arg_18]
0x1800f8892  mov     rax, rdi
0x1800f8895  xor     edi, edi
0x1800f8897  mov     [rcx], rax
0x1800f889a  test    ebx, ebx
0x1800f889c  js      short loc_1800F88E6
0x1800f889e  test    rdi, rdi
0x1800f88a1  jz      short loc_1800F88B2
0x1800f88a3  mov     rax, [rdi]
0x1800f88a6  mov     rcx, rdi
0x1800f88a9  mov     rax, [rax+8]
0x1800f88ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f88b2  mov     eax, ebx
0x1800f88b4  add     rsp, 68h
0x1800f88b8  pop     r15
0x1800f88ba  pop     r14
0x1800f88bc  pop     r13
0x1800f88be  pop     r12
0x1800f88c0  pop     rdi
0x1800f88c1  pop     rsi
0x1800f88c2  pop     rbx
0x1800f88c3  pop     rbp
0x1800f88c4  retn
0x1800f88c5  xor     edx, edx; int *
0x1800f88c7  mov     [rsp+68h+var_40], 0; void *
0x1800f88d0  mov     r9d, eax; int
0x1800f88d3  mov     [rsp+68h+var_48], 94h; unsigned int
0x1800f88db  xor     r8d, r8d; unsigned int
0x1800f88de  lea     ecx, [rdx+14h]; unsigned int
0x1800f88e1  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800f88e6  mov     r13, [rbp+arg_10]
0x1800f88ea  test    rdi, rdi
0x1800f88ed  jz      short loc_1800F88B2
0x1800f88ef  lea     rdx, [rbp+var_28]
0x1800f88f3  mov     rcx, r13
0x1800f88f6  call    ??$_Erase@UEffectDescriptionKey@@@?$_Hash@V?$_Umap_traits@UEffectDescriptionKey@@PEAVCEffectCompilationTask@@V?$_Uhash_compare@UEffectDescriptionKey@@U?$hash@UEffectDescriptionKey@@@std@@U?$equal_to@UEffectDescriptionKey@@@3@@std@@V?$allocator@U?$pair@$$CBUEffectDescriptionKey@@PEAVCEffectCompilationTask@@@std@@@4@$0A@@std@@@std@@AEAA_KAEBUEffectDescriptionKey@@@Z; std::_Hash<std::_Umap_traits<EffectDescriptionKey,CEffectCompilationTask *,std::_Uhash_compare<EffectDescriptionKey,std::hash<EffectDescriptionKey>,std::equal_to<EffectDescriptionKey>>,std::allocator<std::pair<EffectDescriptionKey const,CEffectCompilationTask *>>,0>>::_Erase<EffectDescriptionKey>(EffectDescriptionKey const &)
0x1800f88fb  jmp     short loc_1800F889E
0x1800f88fd  mov     ebx, 80070216h
0x1800f8902  mov     eax, 0B7h
0x1800f8907  mov     esi, ebx
0x1800f8909  mov     r9d, ebx; int
0x1800f890c  xor     ecx, ecx
0x1800f890e  xor     edx, edx; int *
0x1800f8910  mov     [rsp+68h+var_40], rcx; void *
0x1800f8915  xor     r8d, r8d; unsigned int
0x1800f8918  mov     [rsp+68h+var_48], eax; unsigned int
0x1800f891c  lea     ecx, [rdx+14h]; unsigned int
0x1800f891f  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800f8924  xor     edx, edx; int *
0x1800f8926  mov     [rsp+68h+var_40], 0; void *
0x1800f892f  mov     r9d, esi; int
0x1800f8932  mov     [rsp+68h+var_48], 9Ch; unsigned int
0x1800f893a  xor     r8d, r8d; unsigned int
0x1800f893d  lea     ecx, [rdx+14h]; unsigned int
0x1800f8940  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800f8945  test    r12, r12
0x1800f8948  jz      short loc_1800F88E6
0x1800f894a  mov     rcx, r12; lpCriticalSection
0x1800f894d  call    cs:__imp_LeaveCriticalSection
0x1800f8953  jmp     short loc_1800F88E6
0x1800f8955  mov     ecx, 68h ; 'h'; unsigned __int64
0x1800f895a  call    ?AllocClear@DefaultHeap@@SAPEAX_K@Z; DefaultHeap::AllocClear(unsigned __int64)
0x1800f895f  test    rax, rax
0x1800f8962  jz      loc_1800F8B03
0x1800f8968  mov     r8, rsi; struct Windows::UI::Composition::IEffectDescription *
0x1800f896b  mov     rdx, r14; struct CEffectCompilationService *
0x1800f896e  mov     rcx, rax; this
0x1800f8971  call    ??0CEffectCompilationTask@@AEAA@PEAVCEffectCompilationService@@PEAUIEffectDescription@Composition@UI@Windows@@@Z; CEffectCompilationTask::CEffectCompilationTask(CEffectCompilationService *,Windows::UI::Composition::IEffectDescription *)
0x1800f8976  mov     rdx, rax
0x1800f8979  lea     rcx, [rbp+pv]
0x1800f897d  call    ??4?$ComPtr@VCManipulationContext@@@WRL@Microsoft@@QEAAAEAV012@PEAVCManipulationContext@@@Z; Microsoft::WRL::ComPtr<CManipulationContext>::operator=(CManipulationContext *)
0x1800f8982  mov     rdi, [rbp+pv]
0x1800f8986  test    rdi, rdi
0x1800f8989  jz      loc_1800F8A8D
0x1800f898f  cmp     cs:?EnableEffectCaching@CCommonRegistryData@@2V?$CRegistryKey@_N_N@details@@B, 0; details::CRegistryKey<bool,bool> const CCommonRegistryData::EnableEffectCaching
0x1800f8996  jnz     loc_1800F8B12
0x1800f899c  mov     rcx, rdi; pv
0x1800f899f  call    ?Initialize@CEffectCompilationTask@@AEAAJXZ; CEffectCompilationTask::Initialize(void)
0x1800f89a4  mov     ebx, eax
0x1800f89a6  test    eax, eax
0x1800f89a8  js      loc_1800F8A67
0x1800f89ae  xor     r13b, r13b
0x1800f89b1  jmp     loc_1800F87C9
0x1800f89b6  mov     rax, [rsi]
0x1800f89b9  lea     rcx, [rbp+pv]
0x1800f89bd  mov     [rbp+pv], 0
0x1800f89c5  mov     rbx, [rax+58h]
0x1800f89c9  call    ?InternalRelease@?$ComPtr@VCBrushRenderingGraph@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CBrushRenderingGraph>::InternalRelease(void)
0x1800f89ce  lea     rdx, [rbp+pv]
0x1800f89d2  mov     rcx, rsi
0x1800f89d5  mov     rax, rbx
0x1800f89d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f89dd  test    eax, eax
0x1800f89df  jns     loc_1800F8AB8
0x1800f89e5  lea     r15, aNull_1; "null"
0x1800f89ec  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 10h
0x1800f89f3  jnz     short loc_1800F8A1B
0x1800f89f5  mov     rcx, [rbp+pv]
0x1800f89f9  test    rcx, rcx
0x1800f89fc  jz      loc_1800F87D6
0x1800f8a02  mov     [rbp+pv], 0
0x1800f8a0a  mov     rax, [rcx]
0x1800f8a0d  mov     rax, [rax+8]
0x1800f8a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8a16  jmp     loc_1800F87D6
0x1800f8a1b  mov     rax, [rsi]
0x1800f8a1e  mov     rcx, rsi
0x1800f8a21  mov     rax, [rax+20h]
0x1800f8a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8a2a  mov     rcx, [rsi]
0x1800f8a2d  mov     ebx, eax
0x1800f8a2f  mov     rax, [rcx+50h]
0x1800f8a33  mov     rcx, rsi
0x1800f8a36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8a3b  mov     rcx, r12; this
0x1800f8a3e  mov     edx, eax
0x1800f8a40  call    ?GetChannelCallbackId@CNotificationResource@@IEBAIXZ; CNotificationResource::GetChannelCallbackId(void)
0x1800f8a45  movzx   ecx, r13b
0x1800f8a49  mov     r9d, eax
0x1800f8a4c  mov     [rsp+68h+var_30], ecx
0x1800f8a50  mov     r8, rdi
0x1800f8a53  mov     [rsp+68h+var_38], ebx
0x1800f8a57  mov     dword ptr [rsp+68h+var_40], edx
0x1800f8a5b  mov     qword ptr [rsp+68h+var_48], r15
0x1800f8a60  call    McTemplateU0pdsddt_EventWriteTransfer
0x1800f8a65  jmp     short loc_1800F89F5
0x1800f8a67  xor     edx, edx; int *
0x1800f8a69  mov     [rsp+68h+var_40], 0; void *
0x1800f8a72  mov     r9d, eax; int
0x1800f8a75  mov     [rsp+68h+var_48], 77h ; 'w'; unsigned int
0x1800f8a7d  xor     r8d, r8d; unsigned int
0x1800f8a80  lea     ecx, [rdx+14h]; unsigned int
0x1800f8a83  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800f8a88  jmp     loc_1800F88EA
0x1800f8a8d  xor     edx, edx; int *
0x1800f8a8f  mov     [rsp+68h+var_40], 0; void *
0x1800f8a98  mov     ebx, 8007000Eh
0x1800f8a9d  mov     [rsp+68h+var_48], 70h ; 'p'; unsigned int
0x1800f8aa5  mov     r9d, ebx; int
0x1800f8aa8  xor     r8d, r8d; unsigned int
0x1800f8aab  lea     ecx, [rdx+14h]; unsigned int
0x1800f8aae  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800f8ab3  jmp     loc_1800F889E
0x1800f8ab8  mov     rcx, [rbp+pv]
0x1800f8abc  mov     rax, [rcx]
0x1800f8abf  mov     rax, [rax+10h]
0x1800f8ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8ac8  mov     r15, rax
0x1800f8acb  jmp     loc_1800F89EC
0x1800f8ad0  mov     rax, [rsi]
0x1800f8ad3  mov     rcx, rsi
0x1800f8ad6  mov     rdx, [rbx+18h]
0x1800f8ada  mov     rax, [rax+60h]
0x1800f8ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8ae3  test    al, al
0x1800f8ae5  jz      short loc_1800F8AF0
0x1800f8ae7  mov     r12, [rbp+arg_8]
0x1800f8aeb  jmp     loc_1800F878E
0x1800f8af0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800f8af5  jmp     loc_1800F877D
0x1800f8afa  mov     rbx, [r13+8]
0x1800f8afe  jmp     loc_1800F8797
0x1800f8b03  mov     rdx, [rbp+40h]; void *
0x1800f8b07  mov     ecx, 8007000Eh; int
0x1800f8b0c  call    ModuleFailFastForHRESULT
0x1800f8b12  lea     r9, [rbp+pv]
0x1800f8b16  mov     [rbp+pv], rdi
0x1800f8b1a  lea     r8, [rbp+var_28]
0x1800f8b1e  mov     rcx, r13
0x1800f8b21  lea     rdx, [rbp+var_18]
0x1800f8b25  call    ??$emplace@AEAUEffectDescriptionKey@@PEAVCEffectCompilationTask@@@?$_Hash@V?$_Umap_traits@UEffectDescriptionKey@@PEAVCEffectCompilationTask@@V?$_Uhash_compare@UEffectDescriptionKey@@U?$hash@UEffectDescriptionKey@@@std@@U?$equal_to@UEffectDescriptionKey@@@3@@std@@V?$allocator@U?$pair@$$CBUEffectDescriptionKey@@PEAVCEffectCompilationTask@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUEffectDescriptionKey@@PEAVCEffectCompilationTask@@@std@@@std@@@std@@@std@@_N@1@AEAUEffectDescriptionKey@@$$QEAPEAVCEffectCompilationTask@@@Z; std::_Hash<std::_Umap_traits<EffectDescriptionKey,CEffectCompilationTask *,std::_Uhash_compare<EffectDescriptionKey,std::hash<EffectDescriptionKey>,std::equal_to<EffectDescriptionKey>>,std::allocator<std::pair<EffectDescriptionKey const,CEffectCompilationTask *>>,0>>::emplace<EffectDescriptionKey &,CEffectCompilationTask *>(EffectDescriptionKey &,CEffectCompilationTask * &&)
0x1800f8b2a  jmp     loc_1800F899C
0x1800f8b2f  mov     edx, 8
0x1800f8b34  lea     r9, [rbp+pv]
0x1800f8b38  mov     rcx, r15
0x1800f8b3b  lea     r8d, [rdx-7]
0x1800f8b3f  call    ?AddMultipleAndSet@?$DynArrayImpl@$0A@@@IEAAJIIPEBX@Z; DynArrayImpl<0>::AddMultipleAndSet(uint,uint,void const *)
0x1800f8b44  mov     esi, eax
0x1800f8b46  test    eax, eax
0x1800f8b48  jns     loc_1800F8836
0x1800f8b4e  mov     ebx, eax
0x1800f8b50  mov     r9d, eax
0x1800f8b53  mov     eax, 0C2h
0x1800f8b58  jmp     loc_1800F890C
```
