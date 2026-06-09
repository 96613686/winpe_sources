# CSpWmiMethod<_SPACES_VirtualDisk_AddStorageFaultDomain>::RunMethod<CSpVirtualDisk::AddStorageFaultDomain,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800dd4c4`
- end: `0x1800dd812`
- name: `??$RunMethod@VAddStorageFaultDomain@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_AddStorageFaultDomain@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800e4700`

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
- `0x1800dd4c4`
- `0x1800e071c`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd690`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd690`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dd671`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dd671`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dd686`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dd686`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800dd657`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800dd657`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800dd730`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800dd730`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800dd7e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800dd7e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dd7d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dd7d5`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_AddStorageFaultDomain>::RunMethod<CSpVirtualDisk::AddStorageFaultDomain,16>(
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
  CSpVirtualDisk::AddStorageFaultDomain *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::AddStorageFaultDomain *)operator new(0x160u);
  v7 = CSpVirtualDisk::AddStorageFaultDomain::AddStorageFaultDomain(v25);
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
      v25 = (CSpVirtualDisk::AddStorageFaultDomain *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_180333A5D,
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
0x1800dd4c4  mov     [rsp-38h+arg_18], rbx
0x1800dd4c9  push    rbp
0x1800dd4ca  push    rsi
0x1800dd4cb  push    rdi
0x1800dd4cc  push    r12
0x1800dd4ce  push    r13
0x1800dd4d0  push    r14
0x1800dd4d2  push    r15
0x1800dd4d4  mov     rbp, rsp
0x1800dd4d7  sub     rsp, 80h
0x1800dd4de  mov     rax, cs:__security_cookie
0x1800dd4e5  xor     rax, rsp
0x1800dd4e8  mov     [rbp+var_8], rax
0x1800dd4ec  xor     eax, eax
0x1800dd4ee  mov     rsi, rcx
0x1800dd4f1  xorps   xmm0, xmm0
0x1800dd4f4  mov     [rbp+var_10], eax
0x1800dd4f7  mov     ecx, 160h; Size
0x1800dd4fc  mov     [rbp+var_40], eax
0x1800dd4ff  movups  [rbp+var_20], xmm0
0x1800dd503  mov     [rbp+TokenHandle], rax
0x1800dd507  mov     r12, r8
0x1800dd50a  mov     r13, rdx
0x1800dd50d  xor     r14d, r14d
0x1800dd510  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800dd515  mov     rcx, rax; this
0x1800dd518  mov     [rbp+var_28], rax
0x1800dd51c  call    ??0AddStorageFaultDomain@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::AddStorageFaultDomain::AddStorageFaultDomain(void)
0x1800dd521  mov     rdi, rax
0x1800dd524  test    rax, rax
0x1800dd527  jnz     short loc_1800DD531
0x1800dd529  lea     ebx, [rax+1Bh]
0x1800dd52c  jmp     loc_1800DD7CC
0x1800dd531  mov     rax, [rax]
0x1800dd534  mov     rdx, rsi
0x1800dd537  mov     rcx, rdi
0x1800dd53a  xor     r15d, r15d
0x1800dd53d  mov     rax, [rax+8]
0x1800dd541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd546  lea     rcx, [rbp+var_40]
0x1800dd54a  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800dd54f  mov     [rdi+1Ch], eax
0x1800dd552  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800dd556  mov     ecx, [rsi+14h]; unsigned int
0x1800dd559  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800dd55e  mov     eax, cs:dword_180397B68
0x1800dd564  cmp     eax, 5
0x1800dd567  jbe     short loc_1800DD5D7
0x1800dd569  mov     rdx, 400000000000h
0x1800dd573  lea     rcx, dword_180397B68
0x1800dd57a  call    _tlgKeywordOn
0x1800dd57f  test    al, al
0x1800dd581  jz      short loc_1800DD5D7
0x1800dd583  mov     eax, [rbp+var_40]
0x1800dd586  lea     rdx, byte_180333A5D
0x1800dd58d  xor     ecx, ecx
0x1800dd58f  cmp     [rdi+1Ch], eax
0x1800dd592  movzx   eax, word ptr [rbp+var_10]
0x1800dd596  mov     word ptr [rbp+var_40], ax
0x1800dd59a  setnz   cl
0x1800dd59d  mov     eax, [rsi+14h]
0x1800dd5a0  mov     [rbp+var_38], eax
0x1800dd5a3  lea     rax, [rbp+var_20]
0x1800dd5a7  mov     [rbp+var_28], rax
0x1800dd5ab  lea     rax, [rbp+var_3C]
0x1800dd5af  mov     [rsp+80h+var_48], rax
0x1800dd5b4  lea     rax, [rbp+var_40]
0x1800dd5b8  mov     [rsp+80h+var_50], rax
0x1800dd5bd  lea     rax, [rbp+var_38]
0x1800dd5c1  mov     [rsp+80h+var_58], rax
0x1800dd5c6  lea     rax, [rbp+var_28]
0x1800dd5ca  mov     [rsp+80h+var_60], rax
0x1800dd5cf  mov     [rbp+var_3C], ecx
0x1800dd5d2  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800dd5d7  mov     rcx, [rsi]
0x1800dd5da  test    rcx, rcx
0x1800dd5dd  jz      loc_1800DD7A2
0x1800dd5e3  mov     rax, [rcx]
0x1800dd5e6  test    rax, rax
0x1800dd5e9  jz      loc_1800DD7A2
0x1800dd5ef  mov     rax, [rax+18h]
0x1800dd5f3  lea     r8, [rdi+20h]
0x1800dd5f7  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800dd5fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd603  mov     ebx, eax
0x1800dd605  test    eax, eax
0x1800dd607  jnz     loc_1800DD7A7
0x1800dd60d  cmp     [rsi+10h], r14d
0x1800dd611  jz      loc_1800DD73B
0x1800dd617  lea     rbx, [rdi+148h]
0x1800dd61e  mov     rcx, rbx
0x1800dd621  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800dd626  mov     rcx, rbx; struct CSpJobMgr **
0x1800dd629  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800dd62e  test    eax, eax
0x1800dd630  jnz     short loc_1800DD63A
0x1800dd632  lea     ebx, [rax+1Ch]
0x1800dd635  jmp     loc_1800DD7A7
0x1800dd63a  mov     ecx, 10h; Size
0x1800dd63f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800dd644  xor     r8d, r8d; pcbe
0x1800dd647  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800dd64e  mov     rdx, rax; pv
0x1800dd651  mov     r15, rax
0x1800dd654  mov     [rax], rdi
0x1800dd657  call    cs:__imp_CreateThreadpoolWork
0x1800dd65d  mov     r14, rax
0x1800dd660  test    rax, rax
0x1800dd663  jnz     short loc_1800DD671
0x1800dd665  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800dd66a  mov     ebx, eax
0x1800dd66c  jmp     loc_1800DD7A7
0x1800dd671  call    cs:__imp_GetCurrentThread
0x1800dd677  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800dd67b  xor     r8d, r8d; OpenAsSelf
0x1800dd67e  mov     rcx, rax; ThreadHandle
0x1800dd681  mov     edx, 2000Ch; DesiredAccess
0x1800dd686  call    cs:__imp_OpenThreadToken
0x1800dd68c  test    eax, eax
0x1800dd68e  jnz     short loc_1800DD69D
0x1800dd690  call    cs:__imp_GetLastError
0x1800dd696  cmp     eax, 3F0h
0x1800dd69b  jnz     short loc_1800DD665
0x1800dd69d  mov     rax, [rbp+TokenHandle]
0x1800dd6a1  mov     r8, r13
0x1800dd6a4  mov     [r15+8], rax
0x1800dd6a8  mov     rcx, rdi
0x1800dd6ab  mov     rax, [rdi]
0x1800dd6ae  mov     rdx, [rsi+8]
0x1800dd6b2  mov     rax, [rax+18h]
0x1800dd6b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd6bb  mov     rax, [rdi]
0x1800dd6be  mov     rdx, r12
0x1800dd6c1  mov     rcx, rdi
0x1800dd6c4  mov     rax, [rax+28h]
0x1800dd6c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd6cd  mov     ebx, eax
0x1800dd6cf  test    eax, eax
0x1800dd6d1  jz      short loc_1800DD6DC
0x1800dd6d3  cmp     eax, 7
0x1800dd6d6  jnz     loc_1800DD7A7
0x1800dd6dc  mov     rax, [rdi]
0x1800dd6df  mov     rdx, r12
0x1800dd6e2  mov     rcx, rdi
0x1800dd6e5  mov     rax, [rax+38h]
0x1800dd6e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd6ee  mov     ebx, eax
0x1800dd6f0  test    eax, eax
0x1800dd6f2  jnz     loc_1800DD7A7
0x1800dd6f8  mov     rax, [rdi+150h]
0x1800dd6ff  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800dd706  jnz     short loc_1800DD71C
0x1800dd708  mov     rax, [rdi+158h]
0x1800dd70f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800dd716  jz      loc_1800DD7A7
0x1800dd71c  mov     rdx, r12
0x1800dd71f  mov     rcx, rdi
0x1800dd722  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800dd727  mov     ebx, eax
0x1800dd729  test    eax, eax
0x1800dd72b  jnz     short loc_1800DD7A7
0x1800dd72d  mov     rcx, r14; pwk
0x1800dd730  call    cs:__imp_SubmitThreadpoolWork
0x1800dd736  jmp     loc_1800DD7E9
0x1800dd73b  mov     rax, [rdi]
0x1800dd73e  mov     r8, r13
0x1800dd741  mov     rdx, [rsi+8]
0x1800dd745  mov     rcx, rdi
0x1800dd748  mov     rax, [rax+10h]
0x1800dd74c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd751  mov     rax, [rdi]
0x1800dd754  mov     rdx, r12
0x1800dd757  mov     rcx, rdi
0x1800dd75a  mov     rax, [rax+30h]
0x1800dd75e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd763  mov     ebx, eax
0x1800dd765  test    eax, eax
0x1800dd767  jz      short loc_1800DD76E
0x1800dd769  cmp     eax, 7
0x1800dd76c  jnz     short loc_1800DD7A7
0x1800dd76e  mov     rax, [rdi]
0x1800dd771  mov     rdx, r12
0x1800dd774  mov     rcx, rdi
0x1800dd777  mov     rax, [rax+28h]
0x1800dd77b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd780  mov     ebx, eax
0x1800dd782  test    eax, eax
0x1800dd784  jz      short loc_1800DD78B
0x1800dd786  cmp     eax, 7
0x1800dd789  jnz     short loc_1800DD7A7
0x1800dd78b  mov     rax, [rdi]
0x1800dd78e  mov     rdx, r12
0x1800dd791  mov     rcx, rdi
0x1800dd794  mov     rax, [rax+38h]
0x1800dd798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd79d  jmp     loc_1800DD66A
0x1800dd7a2  mov     ebx, 4
0x1800dd7a7  mov     rax, [rdi]
0x1800dd7aa  mov     edx, 1
0x1800dd7af  mov     rcx, rdi
0x1800dd7b2  mov     rax, [rax]
0x1800dd7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd7ba  test    r15, r15
0x1800dd7bd  jz      short loc_1800DD7CC
0x1800dd7bf  mov     edx, 10h
0x1800dd7c4  mov     rcx, r15; Block
0x1800dd7c7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800dd7cc  mov     rcx, [rbp+TokenHandle]; hObject
0x1800dd7d0  test    rcx, rcx
0x1800dd7d3  jz      short loc_1800DD7DB
0x1800dd7d5  call    cs:__imp_CloseHandle
0x1800dd7db  test    r14, r14
0x1800dd7de  jz      short loc_1800DD7E9
0x1800dd7e0  mov     rcx, r14; pwk
0x1800dd7e3  call    cs:__imp_CloseThreadpoolWork
0x1800dd7e9  mov     eax, ebx
0x1800dd7eb  mov     rcx, [rbp+var_8]
0x1800dd7ef  xor     rcx, rsp; StackCookie
0x1800dd7f2  call    __security_check_cookie
0x1800dd7f7  mov     rbx, [rsp+80h+arg_18]
0x1800dd7ff  add     rsp, 80h
0x1800dd806  pop     r15
0x1800dd808  pop     r14
0x1800dd80a  pop     r13
0x1800dd80c  pop     r12
0x1800dd80e  pop     rdi
0x1800dd80f  pop     rsi
0x1800dd810  pop     rbp
0x1800dd811  retn
```
