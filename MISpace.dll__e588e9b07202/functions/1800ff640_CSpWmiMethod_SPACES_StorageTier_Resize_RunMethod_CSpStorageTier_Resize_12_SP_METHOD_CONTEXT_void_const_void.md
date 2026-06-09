# CSpWmiMethod<_SPACES_StorageTier_Resize>::RunMethod<CSpStorageTier::Resize,12>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800ff640`
- end: `0x1800ff98e`
- name: `??$RunMethod@VResize@CSpStorageTier@@$0M@@?$CSpWmiMethod@U_SPACES_StorageTier_Resize@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180102030`

## callees

- `0x1800014ec`
- `0x180001970`
- `0x180006290`
- `0x1800062e0`
- `0x1800062ec`
- `0x18000c704`
- `0x180013898`
- `0x180014000`
- `0x180014720`
- `0x180024dfc`
- `0x18005d58c`
- `0x1800ff640`
- `0x1801005c8`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ff80c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ff80c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ff7ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ff7ed`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ff802`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ff802`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ff7d3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ff7d3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800ff8ac`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800ff8ac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ff95f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ff95f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ff951`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ff951`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageTier_Resize>::RunMethod<CSpStorageTier::Resize,12>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 v7; // rax
  __int64 v8; // rdi
  unsigned int v9; // ebx
  __int64 *v10; // r15
  int v11; // r8d
  int v12; // r9d
  bool v13; // zf
  __int64 v14; // rcx
  enum _MI_Result v15; // eax
  HANDLE CurrentThread; // rax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  int v21; // [rsp+40h] [rbp-40h] BYREF
  BOOL v22; // [rsp+44h] [rbp-3Ch] BYREF
  int v23; // [rsp+48h] [rbp-38h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-30h] BYREF
  CSpStorageTier::Resize *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageTier::Resize *)operator new(0x160u);
  v7 = CSpStorageTier::Resize::Resize(v25);
  v8 = v7;
  if ( v7 )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 8LL))(v7, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStorageTier::Resize *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_18033A2EB,
        v11,
        v12,
        (__int64)&v25,
        (__int64)&v23,
        (__int64)&v21,
        (__int64)&v22);
    }
    v14 = *a1;
    if ( *a1 && *(_QWORD *)v14 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v14 + 24LL))(
             v14,
             &MSFT_StorageExtendedStatus_rtti,
             v8 + 32);
      if ( v9 )
        goto LABEL_30;
      if ( *((_DWORD *)a1 + 4) )
      {
        CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(v8 + 328);
        if ( !(unsigned int)CSpJobMgr::GetInstance((struct CSpJobMgr **)(v8 + 328)) )
        {
          v9 = 28;
          goto LABEL_30;
        }
        v10 = (__int64 *)operator new(0x10u);
        *v10 = v8;
        ThreadpoolWork = CreateThreadpoolWork(
                           CSpWmiMethod<_SPACES_PhysicalDisk_GetPhysicalExtent>::ResumeMethodWorker,
                           v10,
                           0);
        if ( ThreadpoolWork )
        {
          CurrentThread = GetCurrentThread();
          if ( OpenThreadToken(CurrentThread, 0x2000Cu, 0, &TokenHandle) || GetLastError() == 1008 )
          {
            v10[1] = (__int64)TokenHandle;
            (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v8 + 24LL))(v8, a1[1], a2);
            v17 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
            v9 = v17;
            if ( !v17 || v17 == 7 )
            {
              v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 56LL))(v8, a3);
              if ( !v9
                && (*(_QWORD *)(v8 + 336) != *(_QWORD *)&GUID_NULL.Data1
                 || *(_QWORD *)(v8 + 344) != *(_QWORD *)GUID_NULL.Data4) )
              {
                v9 = CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(v8, a3);
                if ( !v9 )
                {
                  SubmitThreadpoolWork(ThreadpoolWork);
                  return v9;
                }
              }
            }
            goto LABEL_30;
          }
        }
        v15 = GleToMiResult();
        goto LABEL_14;
      }
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v8 + 16LL))(v8, a1[1], a2);
      v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 48LL))(v8, a3);
      v9 = v18;
      if ( !v18 || v18 == 7 )
      {
        v19 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
        v9 = v19;
        if ( !v19 || v19 == 7 )
        {
          v15 = (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 56LL))(v8, a3);
LABEL_14:
          v9 = v15;
        }
      }
    }
    else
    {
      v9 = 4;
    }
LABEL_30:
    (**(void (__fastcall ***)(__int64, __int64))v8)(v8, 1);
    if ( v10 )
      operator delete(v10);
    goto LABEL_32;
  }
  v9 = 27;
LABEL_32:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( ThreadpoolWork )
    CloseThreadpoolWork(ThreadpoolWork);
  return v9;
}

```

## disassembly

```asm
0x1800ff640  mov     [rsp-38h+arg_18], rbx
0x1800ff645  push    rbp
0x1800ff646  push    rsi
0x1800ff647  push    rdi
0x1800ff648  push    r12
0x1800ff64a  push    r13
0x1800ff64c  push    r14
0x1800ff64e  push    r15
0x1800ff650  mov     rbp, rsp
0x1800ff653  sub     rsp, 80h
0x1800ff65a  mov     rax, cs:__security_cookie
0x1800ff661  xor     rax, rsp
0x1800ff664  mov     [rbp+var_8], rax
0x1800ff668  xor     eax, eax
0x1800ff66a  mov     rsi, rcx
0x1800ff66d  xorps   xmm0, xmm0
0x1800ff670  mov     [rbp+var_10], eax
0x1800ff673  mov     ecx, 160h; Size
0x1800ff678  mov     [rbp+var_40], eax
0x1800ff67b  movups  [rbp+var_20], xmm0
0x1800ff67f  mov     [rbp+TokenHandle], rax
0x1800ff683  mov     r12, r8
0x1800ff686  mov     r13, rdx
0x1800ff689  xor     r14d, r14d
0x1800ff68c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ff691  mov     rcx, rax; this
0x1800ff694  mov     [rbp+var_28], rax
0x1800ff698  call    ??0Resize@CSpStorageTier@@QEAA@XZ; CSpStorageTier::Resize::Resize(void)
0x1800ff69d  mov     rdi, rax
0x1800ff6a0  test    rax, rax
0x1800ff6a3  jnz     short loc_1800FF6AD
0x1800ff6a5  lea     ebx, [rax+1Bh]
0x1800ff6a8  jmp     loc_1800FF948
0x1800ff6ad  mov     rax, [rax]
0x1800ff6b0  mov     rdx, rsi
0x1800ff6b3  mov     rcx, rdi
0x1800ff6b6  xor     r15d, r15d
0x1800ff6b9  mov     rax, [rax+8]
0x1800ff6bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff6c2  lea     rcx, [rbp+var_40]
0x1800ff6c6  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800ff6cb  mov     [rdi+1Ch], eax
0x1800ff6ce  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800ff6d2  mov     ecx, [rsi+14h]; unsigned int
0x1800ff6d5  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800ff6da  mov     eax, cs:dword_180397B68
0x1800ff6e0  cmp     eax, 5
0x1800ff6e3  jbe     short loc_1800FF753
0x1800ff6e5  mov     rdx, 400000000000h
0x1800ff6ef  lea     rcx, dword_180397B68
0x1800ff6f6  call    _tlgKeywordOn
0x1800ff6fb  test    al, al
0x1800ff6fd  jz      short loc_1800FF753
0x1800ff6ff  mov     eax, [rbp+var_40]
0x1800ff702  lea     rdx, byte_18033A2EB
0x1800ff709  xor     ecx, ecx
0x1800ff70b  cmp     [rdi+1Ch], eax
0x1800ff70e  movzx   eax, word ptr [rbp+var_10]
0x1800ff712  mov     word ptr [rbp+var_40], ax
0x1800ff716  setnz   cl
0x1800ff719  mov     eax, [rsi+14h]
0x1800ff71c  mov     [rbp+var_38], eax
0x1800ff71f  lea     rax, [rbp+var_20]
0x1800ff723  mov     [rbp+var_28], rax
0x1800ff727  lea     rax, [rbp+var_3C]
0x1800ff72b  mov     [rsp+80h+var_48], rax
0x1800ff730  lea     rax, [rbp+var_40]
0x1800ff734  mov     [rsp+80h+var_50], rax
0x1800ff739  lea     rax, [rbp+var_38]
0x1800ff73d  mov     [rsp+80h+var_58], rax
0x1800ff742  lea     rax, [rbp+var_28]
0x1800ff746  mov     [rsp+80h+var_60], rax
0x1800ff74b  mov     [rbp+var_3C], ecx
0x1800ff74e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800ff753  mov     rcx, [rsi]
0x1800ff756  test    rcx, rcx
0x1800ff759  jz      loc_1800FF91E
0x1800ff75f  mov     rax, [rcx]
0x1800ff762  test    rax, rax
0x1800ff765  jz      loc_1800FF91E
0x1800ff76b  mov     rax, [rax+18h]
0x1800ff76f  lea     r8, [rdi+20h]
0x1800ff773  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800ff77a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff77f  mov     ebx, eax
0x1800ff781  test    eax, eax
0x1800ff783  jnz     loc_1800FF923
0x1800ff789  cmp     [rsi+10h], r14d
0x1800ff78d  jz      loc_1800FF8B7
0x1800ff793  lea     rbx, [rdi+148h]
0x1800ff79a  mov     rcx, rbx
0x1800ff79d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800ff7a2  mov     rcx, rbx; struct CSpJobMgr **
0x1800ff7a5  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800ff7aa  test    eax, eax
0x1800ff7ac  jnz     short loc_1800FF7B6
0x1800ff7ae  lea     ebx, [rax+1Ch]
0x1800ff7b1  jmp     loc_1800FF923
0x1800ff7b6  mov     ecx, 10h; Size
0x1800ff7bb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ff7c0  xor     r8d, r8d; pcbe
0x1800ff7c3  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800ff7ca  mov     rdx, rax; pv
0x1800ff7cd  mov     r15, rax
0x1800ff7d0  mov     [rax], rdi
0x1800ff7d3  call    cs:__imp_CreateThreadpoolWork
0x1800ff7d9  mov     r14, rax
0x1800ff7dc  test    rax, rax
0x1800ff7df  jnz     short loc_1800FF7ED
0x1800ff7e1  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800ff7e6  mov     ebx, eax
0x1800ff7e8  jmp     loc_1800FF923
0x1800ff7ed  call    cs:__imp_GetCurrentThread
0x1800ff7f3  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800ff7f7  xor     r8d, r8d; OpenAsSelf
0x1800ff7fa  mov     rcx, rax; ThreadHandle
0x1800ff7fd  mov     edx, 2000Ch; DesiredAccess
0x1800ff802  call    cs:__imp_OpenThreadToken
0x1800ff808  test    eax, eax
0x1800ff80a  jnz     short loc_1800FF819
0x1800ff80c  call    cs:__imp_GetLastError
0x1800ff812  cmp     eax, 3F0h
0x1800ff817  jnz     short loc_1800FF7E1
0x1800ff819  mov     rax, [rbp+TokenHandle]
0x1800ff81d  mov     r8, r13
0x1800ff820  mov     [r15+8], rax
0x1800ff824  mov     rcx, rdi
0x1800ff827  mov     rax, [rdi]
0x1800ff82a  mov     rdx, [rsi+8]
0x1800ff82e  mov     rax, [rax+18h]
0x1800ff832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff837  mov     rax, [rdi]
0x1800ff83a  mov     rdx, r12
0x1800ff83d  mov     rcx, rdi
0x1800ff840  mov     rax, [rax+28h]
0x1800ff844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff849  mov     ebx, eax
0x1800ff84b  test    eax, eax
0x1800ff84d  jz      short loc_1800FF858
0x1800ff84f  cmp     eax, 7
0x1800ff852  jnz     loc_1800FF923
0x1800ff858  mov     rax, [rdi]
0x1800ff85b  mov     rdx, r12
0x1800ff85e  mov     rcx, rdi
0x1800ff861  mov     rax, [rax+38h]
0x1800ff865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff86a  mov     ebx, eax
0x1800ff86c  test    eax, eax
0x1800ff86e  jnz     loc_1800FF923
0x1800ff874  mov     rax, [rdi+150h]
0x1800ff87b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800ff882  jnz     short loc_1800FF898
0x1800ff884  mov     rax, [rdi+158h]
0x1800ff88b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800ff892  jz      loc_1800FF923
0x1800ff898  mov     rdx, r12
0x1800ff89b  mov     rcx, rdi
0x1800ff89e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800ff8a3  mov     ebx, eax
0x1800ff8a5  test    eax, eax
0x1800ff8a7  jnz     short loc_1800FF923
0x1800ff8a9  mov     rcx, r14; pwk
0x1800ff8ac  call    cs:__imp_SubmitThreadpoolWork
0x1800ff8b2  jmp     loc_1800FF965
0x1800ff8b7  mov     rax, [rdi]
0x1800ff8ba  mov     r8, r13
0x1800ff8bd  mov     rdx, [rsi+8]
0x1800ff8c1  mov     rcx, rdi
0x1800ff8c4  mov     rax, [rax+10h]
0x1800ff8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff8cd  mov     rax, [rdi]
0x1800ff8d0  mov     rdx, r12
0x1800ff8d3  mov     rcx, rdi
0x1800ff8d6  mov     rax, [rax+30h]
0x1800ff8da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff8df  mov     ebx, eax
0x1800ff8e1  test    eax, eax
0x1800ff8e3  jz      short loc_1800FF8EA
0x1800ff8e5  cmp     eax, 7
0x1800ff8e8  jnz     short loc_1800FF923
0x1800ff8ea  mov     rax, [rdi]
0x1800ff8ed  mov     rdx, r12
0x1800ff8f0  mov     rcx, rdi
0x1800ff8f3  mov     rax, [rax+28h]
0x1800ff8f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff8fc  mov     ebx, eax
0x1800ff8fe  test    eax, eax
0x1800ff900  jz      short loc_1800FF907
0x1800ff902  cmp     eax, 7
0x1800ff905  jnz     short loc_1800FF923
0x1800ff907  mov     rax, [rdi]
0x1800ff90a  mov     rdx, r12
0x1800ff90d  mov     rcx, rdi
0x1800ff910  mov     rax, [rax+38h]
0x1800ff914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff919  jmp     loc_1800FF7E6
0x1800ff91e  mov     ebx, 4
0x1800ff923  mov     rax, [rdi]
0x1800ff926  mov     edx, 1
0x1800ff92b  mov     rcx, rdi
0x1800ff92e  mov     rax, [rax]
0x1800ff931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff936  test    r15, r15
0x1800ff939  jz      short loc_1800FF948
0x1800ff93b  mov     edx, 10h
0x1800ff940  mov     rcx, r15; Block
0x1800ff943  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ff948  mov     rcx, [rbp+TokenHandle]; hObject
0x1800ff94c  test    rcx, rcx
0x1800ff94f  jz      short loc_1800FF957
0x1800ff951  call    cs:__imp_CloseHandle
0x1800ff957  test    r14, r14
0x1800ff95a  jz      short loc_1800FF965
0x1800ff95c  mov     rcx, r14; pwk
0x1800ff95f  call    cs:__imp_CloseThreadpoolWork
0x1800ff965  mov     eax, ebx
0x1800ff967  mov     rcx, [rbp+var_8]
0x1800ff96b  xor     rcx, rsp; StackCookie
0x1800ff96e  call    __security_check_cookie
0x1800ff973  mov     rbx, [rsp+80h+arg_18]
0x1800ff97b  add     rsp, 80h
0x1800ff982  pop     r15
0x1800ff984  pop     r14
0x1800ff986  pop     r13
0x1800ff988  pop     r12
0x1800ff98a  pop     rdi
0x1800ff98b  pop     rsi
0x1800ff98c  pop     rbp
0x1800ff98d  retn
```
