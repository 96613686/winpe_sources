# CSpWmiMethod<_SPACES_StoragePool_Upgrade>::RunMethod<CSpStoragePool::Upgrade,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800bd434`
- end: `0x1800bd782`
- name: `??$RunMethod@VUpgrade@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_SPACES_StoragePool_Upgrade@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800c1f80`

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
- `0x1800bd434`
- `0x1800be38c`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd600`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bd5e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bd5e1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bd5f6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bd5f6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bd5c7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bd5c7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bd6a0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bd6a0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bd753`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bd753`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd745`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd745`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StoragePool_Upgrade>::RunMethod<CSpStoragePool::Upgrade,11>(
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
  CSpStoragePool::Upgrade *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStoragePool::Upgrade *)operator new(0x160u);
  v7 = CSpStoragePool::Upgrade::Upgrade(v25);
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
      v25 = (CSpStoragePool::Upgrade *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_1803269B9,
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
0x1800bd434  mov     [rsp-38h+arg_18], rbx
0x1800bd439  push    rbp
0x1800bd43a  push    rsi
0x1800bd43b  push    rdi
0x1800bd43c  push    r12
0x1800bd43e  push    r13
0x1800bd440  push    r14
0x1800bd442  push    r15
0x1800bd444  mov     rbp, rsp
0x1800bd447  sub     rsp, 80h
0x1800bd44e  mov     rax, cs:__security_cookie
0x1800bd455  xor     rax, rsp
0x1800bd458  mov     [rbp+var_8], rax
0x1800bd45c  xor     eax, eax
0x1800bd45e  mov     rsi, rcx
0x1800bd461  xorps   xmm0, xmm0
0x1800bd464  mov     [rbp+var_10], eax
0x1800bd467  mov     ecx, 160h; Size
0x1800bd46c  mov     [rbp+var_40], eax
0x1800bd46f  movups  [rbp+var_20], xmm0
0x1800bd473  mov     [rbp+TokenHandle], rax
0x1800bd477  mov     r12, r8
0x1800bd47a  mov     r13, rdx
0x1800bd47d  xor     r14d, r14d
0x1800bd480  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bd485  mov     rcx, rax; this
0x1800bd488  mov     [rbp+var_28], rax
0x1800bd48c  call    ??0Upgrade@CSpStoragePool@@QEAA@XZ; CSpStoragePool::Upgrade::Upgrade(void)
0x1800bd491  mov     rdi, rax
0x1800bd494  test    rax, rax
0x1800bd497  jnz     short loc_1800BD4A1
0x1800bd499  lea     ebx, [rax+1Bh]
0x1800bd49c  jmp     loc_1800BD73C
0x1800bd4a1  mov     rax, [rax]
0x1800bd4a4  mov     rdx, rsi
0x1800bd4a7  mov     rcx, rdi
0x1800bd4aa  xor     r15d, r15d
0x1800bd4ad  mov     rax, [rax+8]
0x1800bd4b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd4b6  lea     rcx, [rbp+var_40]
0x1800bd4ba  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800bd4bf  mov     [rdi+1Ch], eax
0x1800bd4c2  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800bd4c6  mov     ecx, [rsi+14h]; unsigned int
0x1800bd4c9  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800bd4ce  mov     eax, cs:dword_180397B68
0x1800bd4d4  cmp     eax, 5
0x1800bd4d7  jbe     short loc_1800BD547
0x1800bd4d9  mov     rdx, 400000000000h
0x1800bd4e3  lea     rcx, dword_180397B68
0x1800bd4ea  call    _tlgKeywordOn
0x1800bd4ef  test    al, al
0x1800bd4f1  jz      short loc_1800BD547
0x1800bd4f3  mov     eax, [rbp+var_40]
0x1800bd4f6  lea     rdx, byte_1803269B9
0x1800bd4fd  xor     ecx, ecx
0x1800bd4ff  cmp     [rdi+1Ch], eax
0x1800bd502  movzx   eax, word ptr [rbp+var_10]
0x1800bd506  mov     word ptr [rbp+var_40], ax
0x1800bd50a  setnz   cl
0x1800bd50d  mov     eax, [rsi+14h]
0x1800bd510  mov     [rbp+var_38], eax
0x1800bd513  lea     rax, [rbp+var_20]
0x1800bd517  mov     [rbp+var_28], rax
0x1800bd51b  lea     rax, [rbp+var_3C]
0x1800bd51f  mov     [rsp+80h+var_48], rax
0x1800bd524  lea     rax, [rbp+var_40]
0x1800bd528  mov     [rsp+80h+var_50], rax
0x1800bd52d  lea     rax, [rbp+var_38]
0x1800bd531  mov     [rsp+80h+var_58], rax
0x1800bd536  lea     rax, [rbp+var_28]
0x1800bd53a  mov     [rsp+80h+var_60], rax
0x1800bd53f  mov     [rbp+var_3C], ecx
0x1800bd542  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800bd547  mov     rcx, [rsi]
0x1800bd54a  test    rcx, rcx
0x1800bd54d  jz      loc_1800BD712
0x1800bd553  mov     rax, [rcx]
0x1800bd556  test    rax, rax
0x1800bd559  jz      loc_1800BD712
0x1800bd55f  mov     rax, [rax+18h]
0x1800bd563  lea     r8, [rdi+20h]
0x1800bd567  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800bd56e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd573  mov     ebx, eax
0x1800bd575  test    eax, eax
0x1800bd577  jnz     loc_1800BD717
0x1800bd57d  cmp     [rsi+10h], r14d
0x1800bd581  jz      loc_1800BD6AB
0x1800bd587  lea     rbx, [rdi+148h]
0x1800bd58e  mov     rcx, rbx
0x1800bd591  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800bd596  mov     rcx, rbx; struct CSpJobMgr **
0x1800bd599  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800bd59e  test    eax, eax
0x1800bd5a0  jnz     short loc_1800BD5AA
0x1800bd5a2  lea     ebx, [rax+1Ch]
0x1800bd5a5  jmp     loc_1800BD717
0x1800bd5aa  mov     ecx, 10h; Size
0x1800bd5af  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bd5b4  xor     r8d, r8d; pcbe
0x1800bd5b7  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800bd5be  mov     rdx, rax; pv
0x1800bd5c1  mov     r15, rax
0x1800bd5c4  mov     [rax], rdi
0x1800bd5c7  call    cs:__imp_CreateThreadpoolWork
0x1800bd5cd  mov     r14, rax
0x1800bd5d0  test    rax, rax
0x1800bd5d3  jnz     short loc_1800BD5E1
0x1800bd5d5  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800bd5da  mov     ebx, eax
0x1800bd5dc  jmp     loc_1800BD717
0x1800bd5e1  call    cs:__imp_GetCurrentThread
0x1800bd5e7  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800bd5eb  xor     r8d, r8d; OpenAsSelf
0x1800bd5ee  mov     rcx, rax; ThreadHandle
0x1800bd5f1  mov     edx, 2000Ch; DesiredAccess
0x1800bd5f6  call    cs:__imp_OpenThreadToken
0x1800bd5fc  test    eax, eax
0x1800bd5fe  jnz     short loc_1800BD60D
0x1800bd600  call    cs:__imp_GetLastError
0x1800bd606  cmp     eax, 3F0h
0x1800bd60b  jnz     short loc_1800BD5D5
0x1800bd60d  mov     rax, [rbp+TokenHandle]
0x1800bd611  mov     r8, r13
0x1800bd614  mov     [r15+8], rax
0x1800bd618  mov     rcx, rdi
0x1800bd61b  mov     rax, [rdi]
0x1800bd61e  mov     rdx, [rsi+8]
0x1800bd622  mov     rax, [rax+18h]
0x1800bd626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd62b  mov     rax, [rdi]
0x1800bd62e  mov     rdx, r12
0x1800bd631  mov     rcx, rdi
0x1800bd634  mov     rax, [rax+28h]
0x1800bd638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd63d  mov     ebx, eax
0x1800bd63f  test    eax, eax
0x1800bd641  jz      short loc_1800BD64C
0x1800bd643  cmp     eax, 7
0x1800bd646  jnz     loc_1800BD717
0x1800bd64c  mov     rax, [rdi]
0x1800bd64f  mov     rdx, r12
0x1800bd652  mov     rcx, rdi
0x1800bd655  mov     rax, [rax+38h]
0x1800bd659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd65e  mov     ebx, eax
0x1800bd660  test    eax, eax
0x1800bd662  jnz     loc_1800BD717
0x1800bd668  mov     rax, [rdi+150h]
0x1800bd66f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bd676  jnz     short loc_1800BD68C
0x1800bd678  mov     rax, [rdi+158h]
0x1800bd67f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800bd686  jz      loc_1800BD717
0x1800bd68c  mov     rdx, r12
0x1800bd68f  mov     rcx, rdi
0x1800bd692  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800bd697  mov     ebx, eax
0x1800bd699  test    eax, eax
0x1800bd69b  jnz     short loc_1800BD717
0x1800bd69d  mov     rcx, r14; pwk
0x1800bd6a0  call    cs:__imp_SubmitThreadpoolWork
0x1800bd6a6  jmp     loc_1800BD759
0x1800bd6ab  mov     rax, [rdi]
0x1800bd6ae  mov     r8, r13
0x1800bd6b1  mov     rdx, [rsi+8]
0x1800bd6b5  mov     rcx, rdi
0x1800bd6b8  mov     rax, [rax+10h]
0x1800bd6bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd6c1  mov     rax, [rdi]
0x1800bd6c4  mov     rdx, r12
0x1800bd6c7  mov     rcx, rdi
0x1800bd6ca  mov     rax, [rax+30h]
0x1800bd6ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd6d3  mov     ebx, eax
0x1800bd6d5  test    eax, eax
0x1800bd6d7  jz      short loc_1800BD6DE
0x1800bd6d9  cmp     eax, 7
0x1800bd6dc  jnz     short loc_1800BD717
0x1800bd6de  mov     rax, [rdi]
0x1800bd6e1  mov     rdx, r12
0x1800bd6e4  mov     rcx, rdi
0x1800bd6e7  mov     rax, [rax+28h]
0x1800bd6eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd6f0  mov     ebx, eax
0x1800bd6f2  test    eax, eax
0x1800bd6f4  jz      short loc_1800BD6FB
0x1800bd6f6  cmp     eax, 7
0x1800bd6f9  jnz     short loc_1800BD717
0x1800bd6fb  mov     rax, [rdi]
0x1800bd6fe  mov     rdx, r12
0x1800bd701  mov     rcx, rdi
0x1800bd704  mov     rax, [rax+38h]
0x1800bd708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd70d  jmp     loc_1800BD5DA
0x1800bd712  mov     ebx, 4
0x1800bd717  mov     rax, [rdi]
0x1800bd71a  mov     edx, 1
0x1800bd71f  mov     rcx, rdi
0x1800bd722  mov     rax, [rax]
0x1800bd725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd72a  test    r15, r15
0x1800bd72d  jz      short loc_1800BD73C
0x1800bd72f  mov     edx, 10h
0x1800bd734  mov     rcx, r15; Block
0x1800bd737  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800bd73c  mov     rcx, [rbp+TokenHandle]; hObject
0x1800bd740  test    rcx, rcx
0x1800bd743  jz      short loc_1800BD74B
0x1800bd745  call    cs:__imp_CloseHandle
0x1800bd74b  test    r14, r14
0x1800bd74e  jz      short loc_1800BD759
0x1800bd750  mov     rcx, r14; pwk
0x1800bd753  call    cs:__imp_CloseThreadpoolWork
0x1800bd759  mov     eax, ebx
0x1800bd75b  mov     rcx, [rbp+var_8]
0x1800bd75f  xor     rcx, rsp; StackCookie
0x1800bd762  call    __security_check_cookie
0x1800bd767  mov     rbx, [rsp+80h+arg_18]
0x1800bd76f  add     rsp, 80h
0x1800bd776  pop     r15
0x1800bd778  pop     r14
0x1800bd77a  pop     r13
0x1800bd77c  pop     r12
0x1800bd77e  pop     rdi
0x1800bd77f  pop     rsi
0x1800bd780  pop     rbp
0x1800bd781  retn
```
