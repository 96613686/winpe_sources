# CSpWmiMethod<_SPACES_PhysicalDisk_IsPowerProtected>::RunMethod<CSpPhysicalDisk::IsPowerProtected,4>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800ee6ec`
- end: `0x1800eea3a`
- name: `??$RunMethod@VIsPowerProtected@CSpPhysicalDisk@@$03@?$CSpWmiMethod@U_SPACES_PhysicalDisk_IsPowerProtected@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800ee6ec`
- `0x1800f0404`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee8b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee8b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ee899`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ee899`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ee8ae`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ee8ae`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ee87f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ee87f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800ee958`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800ee958`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800eea0b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800eea0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ee9fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ee9fd`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_PhysicalDisk_IsPowerProtected>::RunMethod<CSpPhysicalDisk::IsPowerProtected,4>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 IsPowerProtected; // rax
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
  CSpPhysicalDisk::IsPowerProtected *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpPhysicalDisk::IsPowerProtected *)operator new(0x168u);
  IsPowerProtected = CSpPhysicalDisk::IsPowerProtected::IsPowerProtected(v25);
  v8 = IsPowerProtected;
  if ( IsPowerProtected )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)IsPowerProtected + 8LL))(IsPowerProtected, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpPhysicalDisk::IsPowerProtected *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&byte_18033538F,
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
0x1800ee6ec  mov     [rsp-38h+arg_18], rbx
0x1800ee6f1  push    rbp
0x1800ee6f2  push    rsi
0x1800ee6f3  push    rdi
0x1800ee6f4  push    r12
0x1800ee6f6  push    r13
0x1800ee6f8  push    r14
0x1800ee6fa  push    r15
0x1800ee6fc  mov     rbp, rsp
0x1800ee6ff  sub     rsp, 80h
0x1800ee706  mov     rax, cs:__security_cookie
0x1800ee70d  xor     rax, rsp
0x1800ee710  mov     [rbp+var_8], rax
0x1800ee714  xor     eax, eax
0x1800ee716  mov     rsi, rcx
0x1800ee719  xorps   xmm0, xmm0
0x1800ee71c  mov     [rbp+var_10], eax
0x1800ee71f  mov     ecx, 168h; Size
0x1800ee724  mov     [rbp+var_40], eax
0x1800ee727  movups  [rbp+var_20], xmm0
0x1800ee72b  mov     [rbp+TokenHandle], rax
0x1800ee72f  mov     r12, r8
0x1800ee732  mov     r13, rdx
0x1800ee735  xor     r14d, r14d
0x1800ee738  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ee73d  mov     rcx, rax; this
0x1800ee740  mov     [rbp+var_28], rax
0x1800ee744  call    ??0IsPowerProtected@CSpPhysicalDisk@@QEAA@XZ; CSpPhysicalDisk::IsPowerProtected::IsPowerProtected(void)
0x1800ee749  mov     rdi, rax
0x1800ee74c  test    rax, rax
0x1800ee74f  jnz     short loc_1800EE759
0x1800ee751  lea     ebx, [rax+1Bh]
0x1800ee754  jmp     loc_1800EE9F4
0x1800ee759  mov     rax, [rax]
0x1800ee75c  mov     rdx, rsi
0x1800ee75f  mov     rcx, rdi
0x1800ee762  xor     r15d, r15d
0x1800ee765  mov     rax, [rax+8]
0x1800ee769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee76e  lea     rcx, [rbp+var_40]
0x1800ee772  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800ee777  mov     [rdi+1Ch], eax
0x1800ee77a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800ee77e  mov     ecx, [rsi+14h]; unsigned int
0x1800ee781  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800ee786  mov     eax, cs:dword_180397B68
0x1800ee78c  cmp     eax, 5
0x1800ee78f  jbe     short loc_1800EE7FF
0x1800ee791  mov     rdx, 400000000000h
0x1800ee79b  lea     rcx, dword_180397B68
0x1800ee7a2  call    _tlgKeywordOn
0x1800ee7a7  test    al, al
0x1800ee7a9  jz      short loc_1800EE7FF
0x1800ee7ab  mov     eax, [rbp+var_40]
0x1800ee7ae  lea     rdx, byte_18033538F
0x1800ee7b5  xor     ecx, ecx
0x1800ee7b7  cmp     [rdi+1Ch], eax
0x1800ee7ba  movzx   eax, word ptr [rbp+var_10]
0x1800ee7be  mov     word ptr [rbp+var_40], ax
0x1800ee7c2  setnz   cl
0x1800ee7c5  mov     eax, [rsi+14h]
0x1800ee7c8  mov     [rbp+var_38], eax
0x1800ee7cb  lea     rax, [rbp+var_20]
0x1800ee7cf  mov     [rbp+var_28], rax
0x1800ee7d3  lea     rax, [rbp+var_3C]
0x1800ee7d7  mov     [rsp+80h+var_48], rax
0x1800ee7dc  lea     rax, [rbp+var_40]
0x1800ee7e0  mov     [rsp+80h+var_50], rax
0x1800ee7e5  lea     rax, [rbp+var_38]
0x1800ee7e9  mov     [rsp+80h+var_58], rax
0x1800ee7ee  lea     rax, [rbp+var_28]
0x1800ee7f2  mov     [rsp+80h+var_60], rax
0x1800ee7f7  mov     [rbp+var_3C], ecx
0x1800ee7fa  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800ee7ff  mov     rcx, [rsi]
0x1800ee802  test    rcx, rcx
0x1800ee805  jz      loc_1800EE9CA
0x1800ee80b  mov     rax, [rcx]
0x1800ee80e  test    rax, rax
0x1800ee811  jz      loc_1800EE9CA
0x1800ee817  mov     rax, [rax+18h]
0x1800ee81b  lea     r8, [rdi+20h]
0x1800ee81f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800ee826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee82b  mov     ebx, eax
0x1800ee82d  test    eax, eax
0x1800ee82f  jnz     loc_1800EE9CF
0x1800ee835  cmp     [rsi+10h], r14d
0x1800ee839  jz      loc_1800EE963
0x1800ee83f  lea     rbx, [rdi+148h]
0x1800ee846  mov     rcx, rbx
0x1800ee849  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800ee84e  mov     rcx, rbx; struct CSpJobMgr **
0x1800ee851  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800ee856  test    eax, eax
0x1800ee858  jnz     short loc_1800EE862
0x1800ee85a  lea     ebx, [rax+1Ch]
0x1800ee85d  jmp     loc_1800EE9CF
0x1800ee862  mov     ecx, 10h; Size
0x1800ee867  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ee86c  xor     r8d, r8d; pcbe
0x1800ee86f  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800ee876  mov     rdx, rax; pv
0x1800ee879  mov     r15, rax
0x1800ee87c  mov     [rax], rdi
0x1800ee87f  call    cs:__imp_CreateThreadpoolWork
0x1800ee885  mov     r14, rax
0x1800ee888  test    rax, rax
0x1800ee88b  jnz     short loc_1800EE899
0x1800ee88d  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800ee892  mov     ebx, eax
0x1800ee894  jmp     loc_1800EE9CF
0x1800ee899  call    cs:__imp_GetCurrentThread
0x1800ee89f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800ee8a3  xor     r8d, r8d; OpenAsSelf
0x1800ee8a6  mov     rcx, rax; ThreadHandle
0x1800ee8a9  mov     edx, 2000Ch; DesiredAccess
0x1800ee8ae  call    cs:__imp_OpenThreadToken
0x1800ee8b4  test    eax, eax
0x1800ee8b6  jnz     short loc_1800EE8C5
0x1800ee8b8  call    cs:__imp_GetLastError
0x1800ee8be  cmp     eax, 3F0h
0x1800ee8c3  jnz     short loc_1800EE88D
0x1800ee8c5  mov     rax, [rbp+TokenHandle]
0x1800ee8c9  mov     r8, r13
0x1800ee8cc  mov     [r15+8], rax
0x1800ee8d0  mov     rcx, rdi
0x1800ee8d3  mov     rax, [rdi]
0x1800ee8d6  mov     rdx, [rsi+8]
0x1800ee8da  mov     rax, [rax+18h]
0x1800ee8de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee8e3  mov     rax, [rdi]
0x1800ee8e6  mov     rdx, r12
0x1800ee8e9  mov     rcx, rdi
0x1800ee8ec  mov     rax, [rax+28h]
0x1800ee8f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee8f5  mov     ebx, eax
0x1800ee8f7  test    eax, eax
0x1800ee8f9  jz      short loc_1800EE904
0x1800ee8fb  cmp     eax, 7
0x1800ee8fe  jnz     loc_1800EE9CF
0x1800ee904  mov     rax, [rdi]
0x1800ee907  mov     rdx, r12
0x1800ee90a  mov     rcx, rdi
0x1800ee90d  mov     rax, [rax+38h]
0x1800ee911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee916  mov     ebx, eax
0x1800ee918  test    eax, eax
0x1800ee91a  jnz     loc_1800EE9CF
0x1800ee920  mov     rax, [rdi+150h]
0x1800ee927  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800ee92e  jnz     short loc_1800EE944
0x1800ee930  mov     rax, [rdi+158h]
0x1800ee937  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800ee93e  jz      loc_1800EE9CF
0x1800ee944  mov     rdx, r12
0x1800ee947  mov     rcx, rdi
0x1800ee94a  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800ee94f  mov     ebx, eax
0x1800ee951  test    eax, eax
0x1800ee953  jnz     short loc_1800EE9CF
0x1800ee955  mov     rcx, r14; pwk
0x1800ee958  call    cs:__imp_SubmitThreadpoolWork
0x1800ee95e  jmp     loc_1800EEA11
0x1800ee963  mov     rax, [rdi]
0x1800ee966  mov     r8, r13
0x1800ee969  mov     rdx, [rsi+8]
0x1800ee96d  mov     rcx, rdi
0x1800ee970  mov     rax, [rax+10h]
0x1800ee974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee979  mov     rax, [rdi]
0x1800ee97c  mov     rdx, r12
0x1800ee97f  mov     rcx, rdi
0x1800ee982  mov     rax, [rax+30h]
0x1800ee986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee98b  mov     ebx, eax
0x1800ee98d  test    eax, eax
0x1800ee98f  jz      short loc_1800EE996
0x1800ee991  cmp     eax, 7
0x1800ee994  jnz     short loc_1800EE9CF
0x1800ee996  mov     rax, [rdi]
0x1800ee999  mov     rdx, r12
0x1800ee99c  mov     rcx, rdi
0x1800ee99f  mov     rax, [rax+28h]
0x1800ee9a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee9a8  mov     ebx, eax
0x1800ee9aa  test    eax, eax
0x1800ee9ac  jz      short loc_1800EE9B3
0x1800ee9ae  cmp     eax, 7
0x1800ee9b1  jnz     short loc_1800EE9CF
0x1800ee9b3  mov     rax, [rdi]
0x1800ee9b6  mov     rdx, r12
0x1800ee9b9  mov     rcx, rdi
0x1800ee9bc  mov     rax, [rax+38h]
0x1800ee9c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee9c5  jmp     loc_1800EE892
0x1800ee9ca  mov     ebx, 4
0x1800ee9cf  mov     rax, [rdi]
0x1800ee9d2  mov     edx, 1
0x1800ee9d7  mov     rcx, rdi
0x1800ee9da  mov     rax, [rax]
0x1800ee9dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee9e2  test    r15, r15
0x1800ee9e5  jz      short loc_1800EE9F4
0x1800ee9e7  mov     edx, 10h
0x1800ee9ec  mov     rcx, r15; Block
0x1800ee9ef  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ee9f4  mov     rcx, [rbp+TokenHandle]; hObject
0x1800ee9f8  test    rcx, rcx
0x1800ee9fb  jz      short loc_1800EEA03
0x1800ee9fd  call    cs:__imp_CloseHandle
0x1800eea03  test    r14, r14
0x1800eea06  jz      short loc_1800EEA11
0x1800eea08  mov     rcx, r14; pwk
0x1800eea0b  call    cs:__imp_CloseThreadpoolWork
0x1800eea11  mov     eax, ebx
0x1800eea13  mov     rcx, [rbp+var_8]
0x1800eea17  xor     rcx, rsp; StackCookie
0x1800eea1a  call    __security_check_cookie
0x1800eea1f  mov     rbx, [rsp+80h+arg_18]
0x1800eea27  add     rsp, 80h
0x1800eea2e  pop     r15
0x1800eea30  pop     r14
0x1800eea32  pop     r13
0x1800eea34  pop     r12
0x1800eea36  pop     rdi
0x1800eea37  pop     rsi
0x1800eea38  pop     rbp
0x1800eea39  retn
```
