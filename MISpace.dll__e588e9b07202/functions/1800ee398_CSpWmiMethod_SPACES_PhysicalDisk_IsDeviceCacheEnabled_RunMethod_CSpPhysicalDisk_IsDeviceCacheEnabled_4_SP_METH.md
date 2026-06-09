# CSpWmiMethod<_SPACES_PhysicalDisk_IsDeviceCacheEnabled>::RunMethod<CSpPhysicalDisk::IsDeviceCacheEnabled,4>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800ee398`
- end: `0x1800ee6e6`
- name: `??$RunMethod@VIsDeviceCacheEnabled@CSpPhysicalDisk@@$03@?$CSpWmiMethod@U_SPACES_PhysicalDisk_IsDeviceCacheEnabled@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800f3f30`

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
- `0x1800ee398`
- `0x1800f0384`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee564`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee564`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ee545`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ee545`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ee55a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ee55a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ee52b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ee52b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800ee604`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800ee604`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ee6b7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ee6b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ee6a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ee6a9`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_PhysicalDisk_IsDeviceCacheEnabled>::RunMethod<CSpPhysicalDisk::IsDeviceCacheEnabled,4>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 IsDeviceCacheEnabled; // rax
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
  CSpPhysicalDisk::IsDeviceCacheEnabled *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpPhysicalDisk::IsDeviceCacheEnabled *)operator new(0x168u);
  IsDeviceCacheEnabled = CSpPhysicalDisk::IsDeviceCacheEnabled::IsDeviceCacheEnabled(v25);
  v8 = IsDeviceCacheEnabled;
  if ( IsDeviceCacheEnabled )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)IsDeviceCacheEnabled + 8LL))(IsDeviceCacheEnabled, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpPhysicalDisk::IsDeviceCacheEnabled *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&unk_180334750,
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
0x1800ee398  mov     [rsp-38h+arg_18], rbx
0x1800ee39d  push    rbp
0x1800ee39e  push    rsi
0x1800ee39f  push    rdi
0x1800ee3a0  push    r12
0x1800ee3a2  push    r13
0x1800ee3a4  push    r14
0x1800ee3a6  push    r15
0x1800ee3a8  mov     rbp, rsp
0x1800ee3ab  sub     rsp, 80h
0x1800ee3b2  mov     rax, cs:__security_cookie
0x1800ee3b9  xor     rax, rsp
0x1800ee3bc  mov     [rbp+var_8], rax
0x1800ee3c0  xor     eax, eax
0x1800ee3c2  mov     rsi, rcx
0x1800ee3c5  xorps   xmm0, xmm0
0x1800ee3c8  mov     [rbp+var_10], eax
0x1800ee3cb  mov     ecx, 168h; Size
0x1800ee3d0  mov     [rbp+var_40], eax
0x1800ee3d3  movups  [rbp+var_20], xmm0
0x1800ee3d7  mov     [rbp+TokenHandle], rax
0x1800ee3db  mov     r12, r8
0x1800ee3de  mov     r13, rdx
0x1800ee3e1  xor     r14d, r14d
0x1800ee3e4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ee3e9  mov     rcx, rax; this
0x1800ee3ec  mov     [rbp+var_28], rax
0x1800ee3f0  call    ??0IsDeviceCacheEnabled@CSpPhysicalDisk@@QEAA@XZ; CSpPhysicalDisk::IsDeviceCacheEnabled::IsDeviceCacheEnabled(void)
0x1800ee3f5  mov     rdi, rax
0x1800ee3f8  test    rax, rax
0x1800ee3fb  jnz     short loc_1800EE405
0x1800ee3fd  lea     ebx, [rax+1Bh]
0x1800ee400  jmp     loc_1800EE6A0
0x1800ee405  mov     rax, [rax]
0x1800ee408  mov     rdx, rsi
0x1800ee40b  mov     rcx, rdi
0x1800ee40e  xor     r15d, r15d
0x1800ee411  mov     rax, [rax+8]
0x1800ee415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee41a  lea     rcx, [rbp+var_40]
0x1800ee41e  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800ee423  mov     [rdi+1Ch], eax
0x1800ee426  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800ee42a  mov     ecx, [rsi+14h]; unsigned int
0x1800ee42d  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800ee432  mov     eax, cs:dword_180397B68
0x1800ee438  cmp     eax, 5
0x1800ee43b  jbe     short loc_1800EE4AB
0x1800ee43d  mov     rdx, 400000000000h
0x1800ee447  lea     rcx, dword_180397B68
0x1800ee44e  call    _tlgKeywordOn
0x1800ee453  test    al, al
0x1800ee455  jz      short loc_1800EE4AB
0x1800ee457  mov     eax, [rbp+var_40]
0x1800ee45a  lea     rdx, unk_180334750
0x1800ee461  xor     ecx, ecx
0x1800ee463  cmp     [rdi+1Ch], eax
0x1800ee466  movzx   eax, word ptr [rbp+var_10]
0x1800ee46a  mov     word ptr [rbp+var_40], ax
0x1800ee46e  setnz   cl
0x1800ee471  mov     eax, [rsi+14h]
0x1800ee474  mov     [rbp+var_38], eax
0x1800ee477  lea     rax, [rbp+var_20]
0x1800ee47b  mov     [rbp+var_28], rax
0x1800ee47f  lea     rax, [rbp+var_3C]
0x1800ee483  mov     [rsp+80h+var_48], rax
0x1800ee488  lea     rax, [rbp+var_40]
0x1800ee48c  mov     [rsp+80h+var_50], rax
0x1800ee491  lea     rax, [rbp+var_38]
0x1800ee495  mov     [rsp+80h+var_58], rax
0x1800ee49a  lea     rax, [rbp+var_28]
0x1800ee49e  mov     [rsp+80h+var_60], rax
0x1800ee4a3  mov     [rbp+var_3C], ecx
0x1800ee4a6  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800ee4ab  mov     rcx, [rsi]
0x1800ee4ae  test    rcx, rcx
0x1800ee4b1  jz      loc_1800EE676
0x1800ee4b7  mov     rax, [rcx]
0x1800ee4ba  test    rax, rax
0x1800ee4bd  jz      loc_1800EE676
0x1800ee4c3  mov     rax, [rax+18h]
0x1800ee4c7  lea     r8, [rdi+20h]
0x1800ee4cb  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800ee4d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee4d7  mov     ebx, eax
0x1800ee4d9  test    eax, eax
0x1800ee4db  jnz     loc_1800EE67B
0x1800ee4e1  cmp     [rsi+10h], r14d
0x1800ee4e5  jz      loc_1800EE60F
0x1800ee4eb  lea     rbx, [rdi+148h]
0x1800ee4f2  mov     rcx, rbx
0x1800ee4f5  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800ee4fa  mov     rcx, rbx; struct CSpJobMgr **
0x1800ee4fd  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800ee502  test    eax, eax
0x1800ee504  jnz     short loc_1800EE50E
0x1800ee506  lea     ebx, [rax+1Ch]
0x1800ee509  jmp     loc_1800EE67B
0x1800ee50e  mov     ecx, 10h; Size
0x1800ee513  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ee518  xor     r8d, r8d; pcbe
0x1800ee51b  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800ee522  mov     rdx, rax; pv
0x1800ee525  mov     r15, rax
0x1800ee528  mov     [rax], rdi
0x1800ee52b  call    cs:__imp_CreateThreadpoolWork
0x1800ee531  mov     r14, rax
0x1800ee534  test    rax, rax
0x1800ee537  jnz     short loc_1800EE545
0x1800ee539  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800ee53e  mov     ebx, eax
0x1800ee540  jmp     loc_1800EE67B
0x1800ee545  call    cs:__imp_GetCurrentThread
0x1800ee54b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800ee54f  xor     r8d, r8d; OpenAsSelf
0x1800ee552  mov     rcx, rax; ThreadHandle
0x1800ee555  mov     edx, 2000Ch; DesiredAccess
0x1800ee55a  call    cs:__imp_OpenThreadToken
0x1800ee560  test    eax, eax
0x1800ee562  jnz     short loc_1800EE571
0x1800ee564  call    cs:__imp_GetLastError
0x1800ee56a  cmp     eax, 3F0h
0x1800ee56f  jnz     short loc_1800EE539
0x1800ee571  mov     rax, [rbp+TokenHandle]
0x1800ee575  mov     r8, r13
0x1800ee578  mov     [r15+8], rax
0x1800ee57c  mov     rcx, rdi
0x1800ee57f  mov     rax, [rdi]
0x1800ee582  mov     rdx, [rsi+8]
0x1800ee586  mov     rax, [rax+18h]
0x1800ee58a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee58f  mov     rax, [rdi]
0x1800ee592  mov     rdx, r12
0x1800ee595  mov     rcx, rdi
0x1800ee598  mov     rax, [rax+28h]
0x1800ee59c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee5a1  mov     ebx, eax
0x1800ee5a3  test    eax, eax
0x1800ee5a5  jz      short loc_1800EE5B0
0x1800ee5a7  cmp     eax, 7
0x1800ee5aa  jnz     loc_1800EE67B
0x1800ee5b0  mov     rax, [rdi]
0x1800ee5b3  mov     rdx, r12
0x1800ee5b6  mov     rcx, rdi
0x1800ee5b9  mov     rax, [rax+38h]
0x1800ee5bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee5c2  mov     ebx, eax
0x1800ee5c4  test    eax, eax
0x1800ee5c6  jnz     loc_1800EE67B
0x1800ee5cc  mov     rax, [rdi+150h]
0x1800ee5d3  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800ee5da  jnz     short loc_1800EE5F0
0x1800ee5dc  mov     rax, [rdi+158h]
0x1800ee5e3  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800ee5ea  jz      loc_1800EE67B
0x1800ee5f0  mov     rdx, r12
0x1800ee5f3  mov     rcx, rdi
0x1800ee5f6  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800ee5fb  mov     ebx, eax
0x1800ee5fd  test    eax, eax
0x1800ee5ff  jnz     short loc_1800EE67B
0x1800ee601  mov     rcx, r14; pwk
0x1800ee604  call    cs:__imp_SubmitThreadpoolWork
0x1800ee60a  jmp     loc_1800EE6BD
0x1800ee60f  mov     rax, [rdi]
0x1800ee612  mov     r8, r13
0x1800ee615  mov     rdx, [rsi+8]
0x1800ee619  mov     rcx, rdi
0x1800ee61c  mov     rax, [rax+10h]
0x1800ee620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee625  mov     rax, [rdi]
0x1800ee628  mov     rdx, r12
0x1800ee62b  mov     rcx, rdi
0x1800ee62e  mov     rax, [rax+30h]
0x1800ee632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee637  mov     ebx, eax
0x1800ee639  test    eax, eax
0x1800ee63b  jz      short loc_1800EE642
0x1800ee63d  cmp     eax, 7
0x1800ee640  jnz     short loc_1800EE67B
0x1800ee642  mov     rax, [rdi]
0x1800ee645  mov     rdx, r12
0x1800ee648  mov     rcx, rdi
0x1800ee64b  mov     rax, [rax+28h]
0x1800ee64f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee654  mov     ebx, eax
0x1800ee656  test    eax, eax
0x1800ee658  jz      short loc_1800EE65F
0x1800ee65a  cmp     eax, 7
0x1800ee65d  jnz     short loc_1800EE67B
0x1800ee65f  mov     rax, [rdi]
0x1800ee662  mov     rdx, r12
0x1800ee665  mov     rcx, rdi
0x1800ee668  mov     rax, [rax+38h]
0x1800ee66c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee671  jmp     loc_1800EE53E
0x1800ee676  mov     ebx, 4
0x1800ee67b  mov     rax, [rdi]
0x1800ee67e  mov     edx, 1
0x1800ee683  mov     rcx, rdi
0x1800ee686  mov     rax, [rax]
0x1800ee689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee68e  test    r15, r15
0x1800ee691  jz      short loc_1800EE6A0
0x1800ee693  mov     edx, 10h
0x1800ee698  mov     rcx, r15; Block
0x1800ee69b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ee6a0  mov     rcx, [rbp+TokenHandle]; hObject
0x1800ee6a4  test    rcx, rcx
0x1800ee6a7  jz      short loc_1800EE6AF
0x1800ee6a9  call    cs:__imp_CloseHandle
0x1800ee6af  test    r14, r14
0x1800ee6b2  jz      short loc_1800EE6BD
0x1800ee6b4  mov     rcx, r14; pwk
0x1800ee6b7  call    cs:__imp_CloseThreadpoolWork
0x1800ee6bd  mov     eax, ebx
0x1800ee6bf  mov     rcx, [rbp+var_8]
0x1800ee6c3  xor     rcx, rsp; StackCookie
0x1800ee6c6  call    __security_check_cookie
0x1800ee6cb  mov     rbx, [rsp+80h+arg_18]
0x1800ee6d3  add     rsp, 80h
0x1800ee6da  pop     r15
0x1800ee6dc  pop     r14
0x1800ee6de  pop     r13
0x1800ee6e0  pop     r12
0x1800ee6e2  pop     rdi
0x1800ee6e3  pop     rsi
0x1800ee6e4  pop     rbp
0x1800ee6e5  retn
```
