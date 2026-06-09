# CSpWmiMethod<_SPACES_StorageTier_RemoveStorageFaultDomain>::RunMethod<CSpStorageTier::RemoveStorageFaultDomain,12>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800ff2ec`
- end: `0x1800ff63a`
- name: `??$RunMethod@VRemoveStorageFaultDomain@CSpStorageTier@@$0M@@?$CSpWmiMethod@U_SPACES_StorageTier_RemoveStorageFaultDomain@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800ff2ec`
- `0x18010055c`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ff4b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ff4b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ff499`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ff499`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ff4ae`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ff4ae`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ff47f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ff47f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800ff558`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800ff558`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ff60b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ff60b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ff5fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ff5fd`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageTier_RemoveStorageFaultDomain>::RunMethod<CSpStorageTier::RemoveStorageFaultDomain,12>(
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
  CSpStorageTier::RemoveStorageFaultDomain *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageTier::RemoveStorageFaultDomain *)operator new(0x160u);
  v7 = CSpStorageTier::RemoveStorageFaultDomain::RemoveStorageFaultDomain(v25);
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
      v25 = (CSpStorageTier::RemoveStorageFaultDomain *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&dword_1803392E4,
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
0x1800ff2ec  mov     [rsp-38h+arg_18], rbx
0x1800ff2f1  push    rbp
0x1800ff2f2  push    rsi
0x1800ff2f3  push    rdi
0x1800ff2f4  push    r12
0x1800ff2f6  push    r13
0x1800ff2f8  push    r14
0x1800ff2fa  push    r15
0x1800ff2fc  mov     rbp, rsp
0x1800ff2ff  sub     rsp, 80h
0x1800ff306  mov     rax, cs:__security_cookie
0x1800ff30d  xor     rax, rsp
0x1800ff310  mov     [rbp+var_8], rax
0x1800ff314  xor     eax, eax
0x1800ff316  mov     rsi, rcx
0x1800ff319  xorps   xmm0, xmm0
0x1800ff31c  mov     [rbp+var_10], eax
0x1800ff31f  mov     ecx, 160h; Size
0x1800ff324  mov     [rbp+var_40], eax
0x1800ff327  movups  [rbp+var_20], xmm0
0x1800ff32b  mov     [rbp+TokenHandle], rax
0x1800ff32f  mov     r12, r8
0x1800ff332  mov     r13, rdx
0x1800ff335  xor     r14d, r14d
0x1800ff338  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ff33d  mov     rcx, rax; this
0x1800ff340  mov     [rbp+var_28], rax
0x1800ff344  call    ??0RemoveStorageFaultDomain@CSpStorageTier@@QEAA@XZ; CSpStorageTier::RemoveStorageFaultDomain::RemoveStorageFaultDomain(void)
0x1800ff349  mov     rdi, rax
0x1800ff34c  test    rax, rax
0x1800ff34f  jnz     short loc_1800FF359
0x1800ff351  lea     ebx, [rax+1Bh]
0x1800ff354  jmp     loc_1800FF5F4
0x1800ff359  mov     rax, [rax]
0x1800ff35c  mov     rdx, rsi
0x1800ff35f  mov     rcx, rdi
0x1800ff362  xor     r15d, r15d
0x1800ff365  mov     rax, [rax+8]
0x1800ff369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff36e  lea     rcx, [rbp+var_40]
0x1800ff372  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800ff377  mov     [rdi+1Ch], eax
0x1800ff37a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800ff37e  mov     ecx, [rsi+14h]; unsigned int
0x1800ff381  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800ff386  mov     eax, cs:dword_180397B68
0x1800ff38c  cmp     eax, 5
0x1800ff38f  jbe     short loc_1800FF3FF
0x1800ff391  mov     rdx, 400000000000h
0x1800ff39b  lea     rcx, dword_180397B68
0x1800ff3a2  call    _tlgKeywordOn
0x1800ff3a7  test    al, al
0x1800ff3a9  jz      short loc_1800FF3FF
0x1800ff3ab  mov     eax, [rbp+var_40]
0x1800ff3ae  lea     rdx, dword_1803392E4
0x1800ff3b5  xor     ecx, ecx
0x1800ff3b7  cmp     [rdi+1Ch], eax
0x1800ff3ba  movzx   eax, word ptr [rbp+var_10]
0x1800ff3be  mov     word ptr [rbp+var_40], ax
0x1800ff3c2  setnz   cl
0x1800ff3c5  mov     eax, [rsi+14h]
0x1800ff3c8  mov     [rbp+var_38], eax
0x1800ff3cb  lea     rax, [rbp+var_20]
0x1800ff3cf  mov     [rbp+var_28], rax
0x1800ff3d3  lea     rax, [rbp+var_3C]
0x1800ff3d7  mov     [rsp+80h+var_48], rax
0x1800ff3dc  lea     rax, [rbp+var_40]
0x1800ff3e0  mov     [rsp+80h+var_50], rax
0x1800ff3e5  lea     rax, [rbp+var_38]
0x1800ff3e9  mov     [rsp+80h+var_58], rax
0x1800ff3ee  lea     rax, [rbp+var_28]
0x1800ff3f2  mov     [rsp+80h+var_60], rax
0x1800ff3f7  mov     [rbp+var_3C], ecx
0x1800ff3fa  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800ff3ff  mov     rcx, [rsi]
0x1800ff402  test    rcx, rcx
0x1800ff405  jz      loc_1800FF5CA
0x1800ff40b  mov     rax, [rcx]
0x1800ff40e  test    rax, rax
0x1800ff411  jz      loc_1800FF5CA
0x1800ff417  mov     rax, [rax+18h]
0x1800ff41b  lea     r8, [rdi+20h]
0x1800ff41f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800ff426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff42b  mov     ebx, eax
0x1800ff42d  test    eax, eax
0x1800ff42f  jnz     loc_1800FF5CF
0x1800ff435  cmp     [rsi+10h], r14d
0x1800ff439  jz      loc_1800FF563
0x1800ff43f  lea     rbx, [rdi+148h]
0x1800ff446  mov     rcx, rbx
0x1800ff449  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800ff44e  mov     rcx, rbx; struct CSpJobMgr **
0x1800ff451  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800ff456  test    eax, eax
0x1800ff458  jnz     short loc_1800FF462
0x1800ff45a  lea     ebx, [rax+1Ch]
0x1800ff45d  jmp     loc_1800FF5CF
0x1800ff462  mov     ecx, 10h; Size
0x1800ff467  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ff46c  xor     r8d, r8d; pcbe
0x1800ff46f  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800ff476  mov     rdx, rax; pv
0x1800ff479  mov     r15, rax
0x1800ff47c  mov     [rax], rdi
0x1800ff47f  call    cs:__imp_CreateThreadpoolWork
0x1800ff485  mov     r14, rax
0x1800ff488  test    rax, rax
0x1800ff48b  jnz     short loc_1800FF499
0x1800ff48d  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800ff492  mov     ebx, eax
0x1800ff494  jmp     loc_1800FF5CF
0x1800ff499  call    cs:__imp_GetCurrentThread
0x1800ff49f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800ff4a3  xor     r8d, r8d; OpenAsSelf
0x1800ff4a6  mov     rcx, rax; ThreadHandle
0x1800ff4a9  mov     edx, 2000Ch; DesiredAccess
0x1800ff4ae  call    cs:__imp_OpenThreadToken
0x1800ff4b4  test    eax, eax
0x1800ff4b6  jnz     short loc_1800FF4C5
0x1800ff4b8  call    cs:__imp_GetLastError
0x1800ff4be  cmp     eax, 3F0h
0x1800ff4c3  jnz     short loc_1800FF48D
0x1800ff4c5  mov     rax, [rbp+TokenHandle]
0x1800ff4c9  mov     r8, r13
0x1800ff4cc  mov     [r15+8], rax
0x1800ff4d0  mov     rcx, rdi
0x1800ff4d3  mov     rax, [rdi]
0x1800ff4d6  mov     rdx, [rsi+8]
0x1800ff4da  mov     rax, [rax+18h]
0x1800ff4de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff4e3  mov     rax, [rdi]
0x1800ff4e6  mov     rdx, r12
0x1800ff4e9  mov     rcx, rdi
0x1800ff4ec  mov     rax, [rax+28h]
0x1800ff4f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff4f5  mov     ebx, eax
0x1800ff4f7  test    eax, eax
0x1800ff4f9  jz      short loc_1800FF504
0x1800ff4fb  cmp     eax, 7
0x1800ff4fe  jnz     loc_1800FF5CF
0x1800ff504  mov     rax, [rdi]
0x1800ff507  mov     rdx, r12
0x1800ff50a  mov     rcx, rdi
0x1800ff50d  mov     rax, [rax+38h]
0x1800ff511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff516  mov     ebx, eax
0x1800ff518  test    eax, eax
0x1800ff51a  jnz     loc_1800FF5CF
0x1800ff520  mov     rax, [rdi+150h]
0x1800ff527  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800ff52e  jnz     short loc_1800FF544
0x1800ff530  mov     rax, [rdi+158h]
0x1800ff537  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800ff53e  jz      loc_1800FF5CF
0x1800ff544  mov     rdx, r12
0x1800ff547  mov     rcx, rdi
0x1800ff54a  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800ff54f  mov     ebx, eax
0x1800ff551  test    eax, eax
0x1800ff553  jnz     short loc_1800FF5CF
0x1800ff555  mov     rcx, r14; pwk
0x1800ff558  call    cs:__imp_SubmitThreadpoolWork
0x1800ff55e  jmp     loc_1800FF611
0x1800ff563  mov     rax, [rdi]
0x1800ff566  mov     r8, r13
0x1800ff569  mov     rdx, [rsi+8]
0x1800ff56d  mov     rcx, rdi
0x1800ff570  mov     rax, [rax+10h]
0x1800ff574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff579  mov     rax, [rdi]
0x1800ff57c  mov     rdx, r12
0x1800ff57f  mov     rcx, rdi
0x1800ff582  mov     rax, [rax+30h]
0x1800ff586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff58b  mov     ebx, eax
0x1800ff58d  test    eax, eax
0x1800ff58f  jz      short loc_1800FF596
0x1800ff591  cmp     eax, 7
0x1800ff594  jnz     short loc_1800FF5CF
0x1800ff596  mov     rax, [rdi]
0x1800ff599  mov     rdx, r12
0x1800ff59c  mov     rcx, rdi
0x1800ff59f  mov     rax, [rax+28h]
0x1800ff5a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff5a8  mov     ebx, eax
0x1800ff5aa  test    eax, eax
0x1800ff5ac  jz      short loc_1800FF5B3
0x1800ff5ae  cmp     eax, 7
0x1800ff5b1  jnz     short loc_1800FF5CF
0x1800ff5b3  mov     rax, [rdi]
0x1800ff5b6  mov     rdx, r12
0x1800ff5b9  mov     rcx, rdi
0x1800ff5bc  mov     rax, [rax+38h]
0x1800ff5c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff5c5  jmp     loc_1800FF492
0x1800ff5ca  mov     ebx, 4
0x1800ff5cf  mov     rax, [rdi]
0x1800ff5d2  mov     edx, 1
0x1800ff5d7  mov     rcx, rdi
0x1800ff5da  mov     rax, [rax]
0x1800ff5dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff5e2  test    r15, r15
0x1800ff5e5  jz      short loc_1800FF5F4
0x1800ff5e7  mov     edx, 10h
0x1800ff5ec  mov     rcx, r15; Block
0x1800ff5ef  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ff5f4  mov     rcx, [rbp+TokenHandle]; hObject
0x1800ff5f8  test    rcx, rcx
0x1800ff5fb  jz      short loc_1800FF603
0x1800ff5fd  call    cs:__imp_CloseHandle
0x1800ff603  test    r14, r14
0x1800ff606  jz      short loc_1800FF611
0x1800ff608  mov     rcx, r14; pwk
0x1800ff60b  call    cs:__imp_CloseThreadpoolWork
0x1800ff611  mov     eax, ebx
0x1800ff613  mov     rcx, [rbp+var_8]
0x1800ff617  xor     rcx, rsp; StackCookie
0x1800ff61a  call    __security_check_cookie
0x1800ff61f  mov     rbx, [rsp+80h+arg_18]
0x1800ff627  add     rsp, 80h
0x1800ff62e  pop     r15
0x1800ff630  pop     r14
0x1800ff632  pop     r13
0x1800ff634  pop     r12
0x1800ff636  pop     rdi
0x1800ff637  pop     rsi
0x1800ff638  pop     rbp
0x1800ff639  retn
```
