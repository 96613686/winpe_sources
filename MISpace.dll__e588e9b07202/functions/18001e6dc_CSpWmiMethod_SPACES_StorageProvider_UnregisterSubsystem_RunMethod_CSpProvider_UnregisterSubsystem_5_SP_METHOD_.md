# CSpWmiMethod<_SPACES_StorageProvider_UnregisterSubsystem>::RunMethod<CSpProvider::_UnregisterSubsystem,5>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18001e6dc`
- end: `0x18001ea2a`
- name: `??$RunMethod@V_UnregisterSubsystem@CSpProvider@@$04@?$CSpWmiMethod@U_SPACES_StorageProvider_UnregisterSubsystem@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800227d0`

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
- `0x18001e6dc`
- `0x18001eb9c`
- `0x180024dfc`
- `0x18005d58c`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e8a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e8a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e889`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e889`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e89e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e89e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001e86f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001e86f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001e948`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001e948`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001e9fb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001e9fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e9ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e9ed`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageProvider_UnregisterSubsystem>::RunMethod<CSpProvider::_UnregisterSubsystem,5>(
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
  CSpProvider::_UnregisterSubsystem *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpProvider::_UnregisterSubsystem *)operator new(0x160u);
  v7 = CSpProvider::_UnregisterSubsystem::_UnregisterSubsystem(v25);
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
      v25 = (CSpProvider::_UnregisterSubsystem *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_1802F2343,
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
0x18001e6dc  mov     [rsp-38h+arg_18], rbx
0x18001e6e1  push    rbp
0x18001e6e2  push    rsi
0x18001e6e3  push    rdi
0x18001e6e4  push    r12
0x18001e6e6  push    r13
0x18001e6e8  push    r14
0x18001e6ea  push    r15
0x18001e6ec  mov     rbp, rsp
0x18001e6ef  sub     rsp, 80h
0x18001e6f6  mov     rax, cs:__security_cookie
0x18001e6fd  xor     rax, rsp
0x18001e700  mov     [rbp+var_8], rax
0x18001e704  xor     eax, eax
0x18001e706  mov     rsi, rcx
0x18001e709  xorps   xmm0, xmm0
0x18001e70c  mov     [rbp+var_10], eax
0x18001e70f  mov     ecx, 160h; Size
0x18001e714  mov     [rbp+var_40], eax
0x18001e717  movups  [rbp+var_20], xmm0
0x18001e71b  mov     [rbp+TokenHandle], rax
0x18001e71f  mov     r12, r8
0x18001e722  mov     r13, rdx
0x18001e725  xor     r14d, r14d
0x18001e728  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e72d  mov     rcx, rax; this
0x18001e730  mov     [rbp+var_28], rax
0x18001e734  call    ??0_UnregisterSubsystem@CSpProvider@@QEAA@XZ; CSpProvider::_UnregisterSubsystem::_UnregisterSubsystem(void)
0x18001e739  mov     rdi, rax
0x18001e73c  test    rax, rax
0x18001e73f  jnz     short loc_18001E749
0x18001e741  lea     ebx, [rax+1Bh]
0x18001e744  jmp     loc_18001E9E4
0x18001e749  mov     rax, [rax]
0x18001e74c  mov     rdx, rsi
0x18001e74f  mov     rcx, rdi
0x18001e752  xor     r15d, r15d
0x18001e755  mov     rax, [rax+8]
0x18001e759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e75e  lea     rcx, [rbp+var_40]
0x18001e762  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18001e767  mov     [rdi+1Ch], eax
0x18001e76a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18001e76e  mov     ecx, [rsi+14h]; unsigned int
0x18001e771  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18001e776  mov     eax, cs:dword_180397B68
0x18001e77c  cmp     eax, 5
0x18001e77f  jbe     short loc_18001E7EF
0x18001e781  mov     rdx, 400000000000h
0x18001e78b  lea     rcx, dword_180397B68
0x18001e792  call    _tlgKeywordOn
0x18001e797  test    al, al
0x18001e799  jz      short loc_18001E7EF
0x18001e79b  mov     eax, [rbp+var_40]
0x18001e79e  lea     rdx, byte_1802F2343
0x18001e7a5  xor     ecx, ecx
0x18001e7a7  cmp     [rdi+1Ch], eax
0x18001e7aa  movzx   eax, word ptr [rbp+var_10]
0x18001e7ae  mov     word ptr [rbp+var_40], ax
0x18001e7b2  setnz   cl
0x18001e7b5  mov     eax, [rsi+14h]
0x18001e7b8  mov     [rbp+var_38], eax
0x18001e7bb  lea     rax, [rbp+var_20]
0x18001e7bf  mov     [rbp+var_28], rax
0x18001e7c3  lea     rax, [rbp+var_3C]
0x18001e7c7  mov     [rsp+80h+var_48], rax
0x18001e7cc  lea     rax, [rbp+var_40]
0x18001e7d0  mov     [rsp+80h+var_50], rax
0x18001e7d5  lea     rax, [rbp+var_38]
0x18001e7d9  mov     [rsp+80h+var_58], rax
0x18001e7de  lea     rax, [rbp+var_28]
0x18001e7e2  mov     [rsp+80h+var_60], rax
0x18001e7e7  mov     [rbp+var_3C], ecx
0x18001e7ea  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18001e7ef  mov     rcx, [rsi]
0x18001e7f2  test    rcx, rcx
0x18001e7f5  jz      loc_18001E9BA
0x18001e7fb  mov     rax, [rcx]
0x18001e7fe  test    rax, rax
0x18001e801  jz      loc_18001E9BA
0x18001e807  mov     rax, [rax+18h]
0x18001e80b  lea     r8, [rdi+20h]
0x18001e80f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18001e816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e81b  mov     ebx, eax
0x18001e81d  test    eax, eax
0x18001e81f  jnz     loc_18001E9BF
0x18001e825  cmp     [rsi+10h], r14d
0x18001e829  jz      loc_18001E953
0x18001e82f  lea     rbx, [rdi+148h]
0x18001e836  mov     rcx, rbx
0x18001e839  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18001e83e  mov     rcx, rbx; struct CSpJobMgr **
0x18001e841  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18001e846  test    eax, eax
0x18001e848  jnz     short loc_18001E852
0x18001e84a  lea     ebx, [rax+1Ch]
0x18001e84d  jmp     loc_18001E9BF
0x18001e852  mov     ecx, 10h; Size
0x18001e857  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e85c  xor     r8d, r8d; pcbe
0x18001e85f  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001e866  mov     rdx, rax; pv
0x18001e869  mov     r15, rax
0x18001e86c  mov     [rax], rdi
0x18001e86f  call    cs:__imp_CreateThreadpoolWork
0x18001e875  mov     r14, rax
0x18001e878  test    rax, rax
0x18001e87b  jnz     short loc_18001E889
0x18001e87d  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18001e882  mov     ebx, eax
0x18001e884  jmp     loc_18001E9BF
0x18001e889  call    cs:__imp_GetCurrentThread
0x18001e88f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001e893  xor     r8d, r8d; OpenAsSelf
0x18001e896  mov     rcx, rax; ThreadHandle
0x18001e899  mov     edx, 2000Ch; DesiredAccess
0x18001e89e  call    cs:__imp_OpenThreadToken
0x18001e8a4  test    eax, eax
0x18001e8a6  jnz     short loc_18001E8B5
0x18001e8a8  call    cs:__imp_GetLastError
0x18001e8ae  cmp     eax, 3F0h
0x18001e8b3  jnz     short loc_18001E87D
0x18001e8b5  mov     rax, [rbp+TokenHandle]
0x18001e8b9  mov     r8, r13
0x18001e8bc  mov     [r15+8], rax
0x18001e8c0  mov     rcx, rdi
0x18001e8c3  mov     rax, [rdi]
0x18001e8c6  mov     rdx, [rsi+8]
0x18001e8ca  mov     rax, [rax+18h]
0x18001e8ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8d3  mov     rax, [rdi]
0x18001e8d6  mov     rdx, r12
0x18001e8d9  mov     rcx, rdi
0x18001e8dc  mov     rax, [rax+28h]
0x18001e8e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8e5  mov     ebx, eax
0x18001e8e7  test    eax, eax
0x18001e8e9  jz      short loc_18001E8F4
0x18001e8eb  cmp     eax, 7
0x18001e8ee  jnz     loc_18001E9BF
0x18001e8f4  mov     rax, [rdi]
0x18001e8f7  mov     rdx, r12
0x18001e8fa  mov     rcx, rdi
0x18001e8fd  mov     rax, [rax+38h]
0x18001e901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e906  mov     ebx, eax
0x18001e908  test    eax, eax
0x18001e90a  jnz     loc_18001E9BF
0x18001e910  mov     rax, [rdi+150h]
0x18001e917  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18001e91e  jnz     short loc_18001E934
0x18001e920  mov     rax, [rdi+158h]
0x18001e927  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18001e92e  jz      loc_18001E9BF
0x18001e934  mov     rdx, r12
0x18001e937  mov     rcx, rdi
0x18001e93a  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18001e93f  mov     ebx, eax
0x18001e941  test    eax, eax
0x18001e943  jnz     short loc_18001E9BF
0x18001e945  mov     rcx, r14; pwk
0x18001e948  call    cs:__imp_SubmitThreadpoolWork
0x18001e94e  jmp     loc_18001EA01
0x18001e953  mov     rax, [rdi]
0x18001e956  mov     r8, r13
0x18001e959  mov     rdx, [rsi+8]
0x18001e95d  mov     rcx, rdi
0x18001e960  mov     rax, [rax+10h]
0x18001e964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e969  mov     rax, [rdi]
0x18001e96c  mov     rdx, r12
0x18001e96f  mov     rcx, rdi
0x18001e972  mov     rax, [rax+30h]
0x18001e976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e97b  mov     ebx, eax
0x18001e97d  test    eax, eax
0x18001e97f  jz      short loc_18001E986
0x18001e981  cmp     eax, 7
0x18001e984  jnz     short loc_18001E9BF
0x18001e986  mov     rax, [rdi]
0x18001e989  mov     rdx, r12
0x18001e98c  mov     rcx, rdi
0x18001e98f  mov     rax, [rax+28h]
0x18001e993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e998  mov     ebx, eax
0x18001e99a  test    eax, eax
0x18001e99c  jz      short loc_18001E9A3
0x18001e99e  cmp     eax, 7
0x18001e9a1  jnz     short loc_18001E9BF
0x18001e9a3  mov     rax, [rdi]
0x18001e9a6  mov     rdx, r12
0x18001e9a9  mov     rcx, rdi
0x18001e9ac  mov     rax, [rax+38h]
0x18001e9b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9b5  jmp     loc_18001E882
0x18001e9ba  mov     ebx, 4
0x18001e9bf  mov     rax, [rdi]
0x18001e9c2  mov     edx, 1
0x18001e9c7  mov     rcx, rdi
0x18001e9ca  mov     rax, [rax]
0x18001e9cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9d2  test    r15, r15
0x18001e9d5  jz      short loc_18001E9E4
0x18001e9d7  mov     edx, 10h
0x18001e9dc  mov     rcx, r15; Block
0x18001e9df  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e9e4  mov     rcx, [rbp+TokenHandle]; hObject
0x18001e9e8  test    rcx, rcx
0x18001e9eb  jz      short loc_18001E9F3
0x18001e9ed  call    cs:__imp_CloseHandle
0x18001e9f3  test    r14, r14
0x18001e9f6  jz      short loc_18001EA01
0x18001e9f8  mov     rcx, r14; pwk
0x18001e9fb  call    cs:__imp_CloseThreadpoolWork
0x18001ea01  mov     eax, ebx
0x18001ea03  mov     rcx, [rbp+var_8]
0x18001ea07  xor     rcx, rsp; StackCookie
0x18001ea0a  call    __security_check_cookie
0x18001ea0f  mov     rbx, [rsp+80h+arg_18]
0x18001ea17  add     rsp, 80h
0x18001ea1e  pop     r15
0x18001ea20  pop     r14
0x18001ea22  pop     r13
0x18001ea24  pop     r12
0x18001ea26  pop     rdi
0x18001ea27  pop     rsi
0x18001ea28  pop     rbp
0x18001ea29  retn
```
