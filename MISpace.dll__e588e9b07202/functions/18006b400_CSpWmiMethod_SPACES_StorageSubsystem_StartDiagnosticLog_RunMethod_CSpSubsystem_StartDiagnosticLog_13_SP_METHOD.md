# CSpWmiMethod<_SPACES_StorageSubsystem_StartDiagnosticLog>::RunMethod<CSpSubsystem::StartDiagnosticLog,13>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18006b400`
- end: `0x18006b74e`
- name: `??$RunMethod@VStartDiagnosticLog@CSpSubsystem@@$0N@@?$CSpWmiMethod@U_SPACES_StorageSubsystem_StartDiagnosticLog@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800555c0`
- `0x180072020`

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
- `0x18006b400`
- `0x18006c054`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b5cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b5cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006b5ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006b5ad`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006b5c2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006b5c2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006b593`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006b593`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006b66c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006b66c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006b71f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006b71f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006b711`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006b711`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageSubsystem_StartDiagnosticLog>::RunMethod<CSpSubsystem::StartDiagnosticLog,13>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 started; // rax
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
  CSpSubsystem::StartDiagnosticLog *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpSubsystem::StartDiagnosticLog *)operator new(0x160u);
  started = CSpSubsystem::StartDiagnosticLog::StartDiagnosticLog(v25);
  v8 = started;
  if ( started )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)started + 8LL))(started, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpSubsystem::StartDiagnosticLog *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_18030F4FB,
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
0x18006b400  mov     [rsp-38h+arg_18], rbx
0x18006b405  push    rbp
0x18006b406  push    rsi
0x18006b407  push    rdi
0x18006b408  push    r12
0x18006b40a  push    r13
0x18006b40c  push    r14
0x18006b40e  push    r15
0x18006b410  mov     rbp, rsp
0x18006b413  sub     rsp, 80h
0x18006b41a  mov     rax, cs:__security_cookie
0x18006b421  xor     rax, rsp
0x18006b424  mov     [rbp+var_8], rax
0x18006b428  xor     eax, eax
0x18006b42a  mov     rsi, rcx
0x18006b42d  xorps   xmm0, xmm0
0x18006b430  mov     [rbp+var_10], eax
0x18006b433  mov     ecx, 160h; Size
0x18006b438  mov     [rbp+var_40], eax
0x18006b43b  movups  [rbp+var_20], xmm0
0x18006b43f  mov     [rbp+TokenHandle], rax
0x18006b443  mov     r12, r8
0x18006b446  mov     r13, rdx
0x18006b449  xor     r14d, r14d
0x18006b44c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006b451  mov     rcx, rax; this
0x18006b454  mov     [rbp+var_28], rax
0x18006b458  call    ??0StartDiagnosticLog@CSpSubsystem@@QEAA@XZ; CSpSubsystem::StartDiagnosticLog::StartDiagnosticLog(void)
0x18006b45d  mov     rdi, rax
0x18006b460  test    rax, rax
0x18006b463  jnz     short loc_18006B46D
0x18006b465  lea     ebx, [rax+1Bh]
0x18006b468  jmp     loc_18006B708
0x18006b46d  mov     rax, [rax]
0x18006b470  mov     rdx, rsi
0x18006b473  mov     rcx, rdi
0x18006b476  xor     r15d, r15d
0x18006b479  mov     rax, [rax+8]
0x18006b47d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b482  lea     rcx, [rbp+var_40]
0x18006b486  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18006b48b  mov     [rdi+1Ch], eax
0x18006b48e  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18006b492  mov     ecx, [rsi+14h]; unsigned int
0x18006b495  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18006b49a  mov     eax, cs:dword_180397B68
0x18006b4a0  cmp     eax, 5
0x18006b4a3  jbe     short loc_18006B513
0x18006b4a5  mov     rdx, 400000000000h
0x18006b4af  lea     rcx, dword_180397B68
0x18006b4b6  call    _tlgKeywordOn
0x18006b4bb  test    al, al
0x18006b4bd  jz      short loc_18006B513
0x18006b4bf  mov     eax, [rbp+var_40]
0x18006b4c2  lea     rdx, byte_18030F4FB
0x18006b4c9  xor     ecx, ecx
0x18006b4cb  cmp     [rdi+1Ch], eax
0x18006b4ce  movzx   eax, word ptr [rbp+var_10]
0x18006b4d2  mov     word ptr [rbp+var_40], ax
0x18006b4d6  setnz   cl
0x18006b4d9  mov     eax, [rsi+14h]
0x18006b4dc  mov     [rbp+var_38], eax
0x18006b4df  lea     rax, [rbp+var_20]
0x18006b4e3  mov     [rbp+var_28], rax
0x18006b4e7  lea     rax, [rbp+var_3C]
0x18006b4eb  mov     [rsp+80h+var_48], rax
0x18006b4f0  lea     rax, [rbp+var_40]
0x18006b4f4  mov     [rsp+80h+var_50], rax
0x18006b4f9  lea     rax, [rbp+var_38]
0x18006b4fd  mov     [rsp+80h+var_58], rax
0x18006b502  lea     rax, [rbp+var_28]
0x18006b506  mov     [rsp+80h+var_60], rax
0x18006b50b  mov     [rbp+var_3C], ecx
0x18006b50e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18006b513  mov     rcx, [rsi]
0x18006b516  test    rcx, rcx
0x18006b519  jz      loc_18006B6DE
0x18006b51f  mov     rax, [rcx]
0x18006b522  test    rax, rax
0x18006b525  jz      loc_18006B6DE
0x18006b52b  mov     rax, [rax+18h]
0x18006b52f  lea     r8, [rdi+20h]
0x18006b533  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18006b53a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b53f  mov     ebx, eax
0x18006b541  test    eax, eax
0x18006b543  jnz     loc_18006B6E3
0x18006b549  cmp     [rsi+10h], r14d
0x18006b54d  jz      loc_18006B677
0x18006b553  lea     rbx, [rdi+148h]
0x18006b55a  mov     rcx, rbx
0x18006b55d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18006b562  mov     rcx, rbx; struct CSpJobMgr **
0x18006b565  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18006b56a  test    eax, eax
0x18006b56c  jnz     short loc_18006B576
0x18006b56e  lea     ebx, [rax+1Ch]
0x18006b571  jmp     loc_18006B6E3
0x18006b576  mov     ecx, 10h; Size
0x18006b57b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006b580  xor     r8d, r8d; pcbe
0x18006b583  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18006b58a  mov     rdx, rax; pv
0x18006b58d  mov     r15, rax
0x18006b590  mov     [rax], rdi
0x18006b593  call    cs:__imp_CreateThreadpoolWork
0x18006b599  mov     r14, rax
0x18006b59c  test    rax, rax
0x18006b59f  jnz     short loc_18006B5AD
0x18006b5a1  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18006b5a6  mov     ebx, eax
0x18006b5a8  jmp     loc_18006B6E3
0x18006b5ad  call    cs:__imp_GetCurrentThread
0x18006b5b3  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18006b5b7  xor     r8d, r8d; OpenAsSelf
0x18006b5ba  mov     rcx, rax; ThreadHandle
0x18006b5bd  mov     edx, 2000Ch; DesiredAccess
0x18006b5c2  call    cs:__imp_OpenThreadToken
0x18006b5c8  test    eax, eax
0x18006b5ca  jnz     short loc_18006B5D9
0x18006b5cc  call    cs:__imp_GetLastError
0x18006b5d2  cmp     eax, 3F0h
0x18006b5d7  jnz     short loc_18006B5A1
0x18006b5d9  mov     rax, [rbp+TokenHandle]
0x18006b5dd  mov     r8, r13
0x18006b5e0  mov     [r15+8], rax
0x18006b5e4  mov     rcx, rdi
0x18006b5e7  mov     rax, [rdi]
0x18006b5ea  mov     rdx, [rsi+8]
0x18006b5ee  mov     rax, [rax+18h]
0x18006b5f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b5f7  mov     rax, [rdi]
0x18006b5fa  mov     rdx, r12
0x18006b5fd  mov     rcx, rdi
0x18006b600  mov     rax, [rax+28h]
0x18006b604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b609  mov     ebx, eax
0x18006b60b  test    eax, eax
0x18006b60d  jz      short loc_18006B618
0x18006b60f  cmp     eax, 7
0x18006b612  jnz     loc_18006B6E3
0x18006b618  mov     rax, [rdi]
0x18006b61b  mov     rdx, r12
0x18006b61e  mov     rcx, rdi
0x18006b621  mov     rax, [rax+38h]
0x18006b625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b62a  mov     ebx, eax
0x18006b62c  test    eax, eax
0x18006b62e  jnz     loc_18006B6E3
0x18006b634  mov     rax, [rdi+150h]
0x18006b63b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18006b642  jnz     short loc_18006B658
0x18006b644  mov     rax, [rdi+158h]
0x18006b64b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18006b652  jz      loc_18006B6E3
0x18006b658  mov     rdx, r12
0x18006b65b  mov     rcx, rdi
0x18006b65e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18006b663  mov     ebx, eax
0x18006b665  test    eax, eax
0x18006b667  jnz     short loc_18006B6E3
0x18006b669  mov     rcx, r14; pwk
0x18006b66c  call    cs:__imp_SubmitThreadpoolWork
0x18006b672  jmp     loc_18006B725
0x18006b677  mov     rax, [rdi]
0x18006b67a  mov     r8, r13
0x18006b67d  mov     rdx, [rsi+8]
0x18006b681  mov     rcx, rdi
0x18006b684  mov     rax, [rax+10h]
0x18006b688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b68d  mov     rax, [rdi]
0x18006b690  mov     rdx, r12
0x18006b693  mov     rcx, rdi
0x18006b696  mov     rax, [rax+30h]
0x18006b69a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b69f  mov     ebx, eax
0x18006b6a1  test    eax, eax
0x18006b6a3  jz      short loc_18006B6AA
0x18006b6a5  cmp     eax, 7
0x18006b6a8  jnz     short loc_18006B6E3
0x18006b6aa  mov     rax, [rdi]
0x18006b6ad  mov     rdx, r12
0x18006b6b0  mov     rcx, rdi
0x18006b6b3  mov     rax, [rax+28h]
0x18006b6b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b6bc  mov     ebx, eax
0x18006b6be  test    eax, eax
0x18006b6c0  jz      short loc_18006B6C7
0x18006b6c2  cmp     eax, 7
0x18006b6c5  jnz     short loc_18006B6E3
0x18006b6c7  mov     rax, [rdi]
0x18006b6ca  mov     rdx, r12
0x18006b6cd  mov     rcx, rdi
0x18006b6d0  mov     rax, [rax+38h]
0x18006b6d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b6d9  jmp     loc_18006B5A6
0x18006b6de  mov     ebx, 4
0x18006b6e3  mov     rax, [rdi]
0x18006b6e6  mov     edx, 1
0x18006b6eb  mov     rcx, rdi
0x18006b6ee  mov     rax, [rax]
0x18006b6f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b6f6  test    r15, r15
0x18006b6f9  jz      short loc_18006B708
0x18006b6fb  mov     edx, 10h
0x18006b700  mov     rcx, r15; Block
0x18006b703  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006b708  mov     rcx, [rbp+TokenHandle]; hObject
0x18006b70c  test    rcx, rcx
0x18006b70f  jz      short loc_18006B717
0x18006b711  call    cs:__imp_CloseHandle
0x18006b717  test    r14, r14
0x18006b71a  jz      short loc_18006B725
0x18006b71c  mov     rcx, r14; pwk
0x18006b71f  call    cs:__imp_CloseThreadpoolWork
0x18006b725  mov     eax, ebx
0x18006b727  mov     rcx, [rbp+var_8]
0x18006b72b  xor     rcx, rsp; StackCookie
0x18006b72e  call    __security_check_cookie
0x18006b733  mov     rbx, [rsp+80h+arg_18]
0x18006b73b  add     rsp, 80h
0x18006b742  pop     r15
0x18006b744  pop     r14
0x18006b746  pop     r13
0x18006b748  pop     r12
0x18006b74a  pop     rdi
0x18006b74b  pop     rsi
0x18006b74c  pop     rbp
0x18006b74d  retn
```
