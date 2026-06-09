# CSpWmiMethod<_SPACES_StorageSubsystem_GetActions>::RunMethod<CSpSubsystem::GetActions,13>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18006a6b0`
- end: `0x18006a9fe`
- name: `??$RunMethod@VGetActions@CSpSubsystem@@$0N@@?$CSpWmiMethod@U_SPACES_StorageSubsystem_GetActions@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

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
- `0x18006a6b0`
- `0x18006bec4`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a87c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a87c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006a85d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006a85d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006a872`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006a872`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006a843`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006a843`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006a91c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006a91c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006a9cf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006a9cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006a9c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006a9c1`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageSubsystem_GetActions>::RunMethod<CSpSubsystem::GetActions,13>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 Actions; // rax
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
  CSpSubsystem::GetActions *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpSubsystem::GetActions *)operator new(0x168u);
  Actions = CSpSubsystem::GetActions::GetActions(v25);
  v8 = Actions;
  if ( Actions )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)Actions + 8LL))(Actions, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpSubsystem::GetActions *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&dword_18030F294,
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
0x18006a6b0  mov     [rsp-38h+arg_18], rbx
0x18006a6b5  push    rbp
0x18006a6b6  push    rsi
0x18006a6b7  push    rdi
0x18006a6b8  push    r12
0x18006a6ba  push    r13
0x18006a6bc  push    r14
0x18006a6be  push    r15
0x18006a6c0  mov     rbp, rsp
0x18006a6c3  sub     rsp, 80h
0x18006a6ca  mov     rax, cs:__security_cookie
0x18006a6d1  xor     rax, rsp
0x18006a6d4  mov     [rbp+var_8], rax
0x18006a6d8  xor     eax, eax
0x18006a6da  mov     rsi, rcx
0x18006a6dd  xorps   xmm0, xmm0
0x18006a6e0  mov     [rbp+var_10], eax
0x18006a6e3  mov     ecx, 168h; Size
0x18006a6e8  mov     [rbp+var_40], eax
0x18006a6eb  movups  [rbp+var_20], xmm0
0x18006a6ef  mov     [rbp+TokenHandle], rax
0x18006a6f3  mov     r12, r8
0x18006a6f6  mov     r13, rdx
0x18006a6f9  xor     r14d, r14d
0x18006a6fc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006a701  mov     rcx, rax; this
0x18006a704  mov     [rbp+var_28], rax
0x18006a708  call    ??0GetActions@CSpSubsystem@@QEAA@XZ; CSpSubsystem::GetActions::GetActions(void)
0x18006a70d  mov     rdi, rax
0x18006a710  test    rax, rax
0x18006a713  jnz     short loc_18006A71D
0x18006a715  lea     ebx, [rax+1Bh]
0x18006a718  jmp     loc_18006A9B8
0x18006a71d  mov     rax, [rax]
0x18006a720  mov     rdx, rsi
0x18006a723  mov     rcx, rdi
0x18006a726  xor     r15d, r15d
0x18006a729  mov     rax, [rax+8]
0x18006a72d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a732  lea     rcx, [rbp+var_40]
0x18006a736  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18006a73b  mov     [rdi+1Ch], eax
0x18006a73e  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18006a742  mov     ecx, [rsi+14h]; unsigned int
0x18006a745  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18006a74a  mov     eax, cs:dword_180397B68
0x18006a750  cmp     eax, 5
0x18006a753  jbe     short loc_18006A7C3
0x18006a755  mov     rdx, 400000000000h
0x18006a75f  lea     rcx, dword_180397B68
0x18006a766  call    _tlgKeywordOn
0x18006a76b  test    al, al
0x18006a76d  jz      short loc_18006A7C3
0x18006a76f  mov     eax, [rbp+var_40]
0x18006a772  lea     rdx, dword_18030F294
0x18006a779  xor     ecx, ecx
0x18006a77b  cmp     [rdi+1Ch], eax
0x18006a77e  movzx   eax, word ptr [rbp+var_10]
0x18006a782  mov     word ptr [rbp+var_40], ax
0x18006a786  setnz   cl
0x18006a789  mov     eax, [rsi+14h]
0x18006a78c  mov     [rbp+var_38], eax
0x18006a78f  lea     rax, [rbp+var_20]
0x18006a793  mov     [rbp+var_28], rax
0x18006a797  lea     rax, [rbp+var_3C]
0x18006a79b  mov     [rsp+80h+var_48], rax
0x18006a7a0  lea     rax, [rbp+var_40]
0x18006a7a4  mov     [rsp+80h+var_50], rax
0x18006a7a9  lea     rax, [rbp+var_38]
0x18006a7ad  mov     [rsp+80h+var_58], rax
0x18006a7b2  lea     rax, [rbp+var_28]
0x18006a7b6  mov     [rsp+80h+var_60], rax
0x18006a7bb  mov     [rbp+var_3C], ecx
0x18006a7be  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18006a7c3  mov     rcx, [rsi]
0x18006a7c6  test    rcx, rcx
0x18006a7c9  jz      loc_18006A98E
0x18006a7cf  mov     rax, [rcx]
0x18006a7d2  test    rax, rax
0x18006a7d5  jz      loc_18006A98E
0x18006a7db  mov     rax, [rax+18h]
0x18006a7df  lea     r8, [rdi+20h]
0x18006a7e3  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18006a7ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a7ef  mov     ebx, eax
0x18006a7f1  test    eax, eax
0x18006a7f3  jnz     loc_18006A993
0x18006a7f9  cmp     [rsi+10h], r14d
0x18006a7fd  jz      loc_18006A927
0x18006a803  lea     rbx, [rdi+148h]
0x18006a80a  mov     rcx, rbx
0x18006a80d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18006a812  mov     rcx, rbx; struct CSpJobMgr **
0x18006a815  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18006a81a  test    eax, eax
0x18006a81c  jnz     short loc_18006A826
0x18006a81e  lea     ebx, [rax+1Ch]
0x18006a821  jmp     loc_18006A993
0x18006a826  mov     ecx, 10h; Size
0x18006a82b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006a830  xor     r8d, r8d; pcbe
0x18006a833  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18006a83a  mov     rdx, rax; pv
0x18006a83d  mov     r15, rax
0x18006a840  mov     [rax], rdi
0x18006a843  call    cs:__imp_CreateThreadpoolWork
0x18006a849  mov     r14, rax
0x18006a84c  test    rax, rax
0x18006a84f  jnz     short loc_18006A85D
0x18006a851  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18006a856  mov     ebx, eax
0x18006a858  jmp     loc_18006A993
0x18006a85d  call    cs:__imp_GetCurrentThread
0x18006a863  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18006a867  xor     r8d, r8d; OpenAsSelf
0x18006a86a  mov     rcx, rax; ThreadHandle
0x18006a86d  mov     edx, 2000Ch; DesiredAccess
0x18006a872  call    cs:__imp_OpenThreadToken
0x18006a878  test    eax, eax
0x18006a87a  jnz     short loc_18006A889
0x18006a87c  call    cs:__imp_GetLastError
0x18006a882  cmp     eax, 3F0h
0x18006a887  jnz     short loc_18006A851
0x18006a889  mov     rax, [rbp+TokenHandle]
0x18006a88d  mov     r8, r13
0x18006a890  mov     [r15+8], rax
0x18006a894  mov     rcx, rdi
0x18006a897  mov     rax, [rdi]
0x18006a89a  mov     rdx, [rsi+8]
0x18006a89e  mov     rax, [rax+18h]
0x18006a8a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a8a7  mov     rax, [rdi]
0x18006a8aa  mov     rdx, r12
0x18006a8ad  mov     rcx, rdi
0x18006a8b0  mov     rax, [rax+28h]
0x18006a8b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a8b9  mov     ebx, eax
0x18006a8bb  test    eax, eax
0x18006a8bd  jz      short loc_18006A8C8
0x18006a8bf  cmp     eax, 7
0x18006a8c2  jnz     loc_18006A993
0x18006a8c8  mov     rax, [rdi]
0x18006a8cb  mov     rdx, r12
0x18006a8ce  mov     rcx, rdi
0x18006a8d1  mov     rax, [rax+38h]
0x18006a8d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a8da  mov     ebx, eax
0x18006a8dc  test    eax, eax
0x18006a8de  jnz     loc_18006A993
0x18006a8e4  mov     rax, [rdi+150h]
0x18006a8eb  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18006a8f2  jnz     short loc_18006A908
0x18006a8f4  mov     rax, [rdi+158h]
0x18006a8fb  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18006a902  jz      loc_18006A993
0x18006a908  mov     rdx, r12
0x18006a90b  mov     rcx, rdi
0x18006a90e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18006a913  mov     ebx, eax
0x18006a915  test    eax, eax
0x18006a917  jnz     short loc_18006A993
0x18006a919  mov     rcx, r14; pwk
0x18006a91c  call    cs:__imp_SubmitThreadpoolWork
0x18006a922  jmp     loc_18006A9D5
0x18006a927  mov     rax, [rdi]
0x18006a92a  mov     r8, r13
0x18006a92d  mov     rdx, [rsi+8]
0x18006a931  mov     rcx, rdi
0x18006a934  mov     rax, [rax+10h]
0x18006a938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a93d  mov     rax, [rdi]
0x18006a940  mov     rdx, r12
0x18006a943  mov     rcx, rdi
0x18006a946  mov     rax, [rax+30h]
0x18006a94a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a94f  mov     ebx, eax
0x18006a951  test    eax, eax
0x18006a953  jz      short loc_18006A95A
0x18006a955  cmp     eax, 7
0x18006a958  jnz     short loc_18006A993
0x18006a95a  mov     rax, [rdi]
0x18006a95d  mov     rdx, r12
0x18006a960  mov     rcx, rdi
0x18006a963  mov     rax, [rax+28h]
0x18006a967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a96c  mov     ebx, eax
0x18006a96e  test    eax, eax
0x18006a970  jz      short loc_18006A977
0x18006a972  cmp     eax, 7
0x18006a975  jnz     short loc_18006A993
0x18006a977  mov     rax, [rdi]
0x18006a97a  mov     rdx, r12
0x18006a97d  mov     rcx, rdi
0x18006a980  mov     rax, [rax+38h]
0x18006a984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a989  jmp     loc_18006A856
0x18006a98e  mov     ebx, 4
0x18006a993  mov     rax, [rdi]
0x18006a996  mov     edx, 1
0x18006a99b  mov     rcx, rdi
0x18006a99e  mov     rax, [rax]
0x18006a9a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a9a6  test    r15, r15
0x18006a9a9  jz      short loc_18006A9B8
0x18006a9ab  mov     edx, 10h
0x18006a9b0  mov     rcx, r15; Block
0x18006a9b3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006a9b8  mov     rcx, [rbp+TokenHandle]; hObject
0x18006a9bc  test    rcx, rcx
0x18006a9bf  jz      short loc_18006A9C7
0x18006a9c1  call    cs:__imp_CloseHandle
0x18006a9c7  test    r14, r14
0x18006a9ca  jz      short loc_18006A9D5
0x18006a9cc  mov     rcx, r14; pwk
0x18006a9cf  call    cs:__imp_CloseThreadpoolWork
0x18006a9d5  mov     eax, ebx
0x18006a9d7  mov     rcx, [rbp+var_8]
0x18006a9db  xor     rcx, rsp; StackCookie
0x18006a9de  call    __security_check_cookie
0x18006a9e3  mov     rbx, [rsp+80h+arg_18]
0x18006a9eb  add     rsp, 80h
0x18006a9f2  pop     r15
0x18006a9f4  pop     r14
0x18006a9f6  pop     r13
0x18006a9f8  pop     r12
0x18006a9fa  pop     rdi
0x18006a9fb  pop     rsi
0x18006a9fc  pop     rbp
0x18006a9fd  retn
```
