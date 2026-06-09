# CSpWmiMethod<_SPACES_VirtualDisk_GetPhysicalExtent>::RunMethod<CSpVirtualDisk::GetPhysicalExtent,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800de214`
- end: `0x1800de562`
- name: `??$RunMethod@VGetPhysicalExtent@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_GetPhysicalExtent@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800de214`
- `0x1800e08d8`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de3e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de3e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800de3c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800de3c1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800de3d6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800de3d6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800de3a7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800de3a7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800de480`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800de480`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800de533`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800de533`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800de525`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800de525`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_GetPhysicalExtent>::RunMethod<CSpVirtualDisk::GetPhysicalExtent,16>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 PhysicalExtent; // rax
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
  CSpVirtualDisk::GetPhysicalExtent *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::GetPhysicalExtent *)operator new(0x170u);
  PhysicalExtent = CSpVirtualDisk::GetPhysicalExtent::GetPhysicalExtent(v25);
  v8 = PhysicalExtent;
  if ( PhysicalExtent )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)PhysicalExtent + 8LL))(PhysicalExtent, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpVirtualDisk::GetPhysicalExtent *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)word_180333C62,
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
0x1800de214  mov     [rsp-38h+arg_18], rbx
0x1800de219  push    rbp
0x1800de21a  push    rsi
0x1800de21b  push    rdi
0x1800de21c  push    r12
0x1800de21e  push    r13
0x1800de220  push    r14
0x1800de222  push    r15
0x1800de224  mov     rbp, rsp
0x1800de227  sub     rsp, 80h
0x1800de22e  mov     rax, cs:__security_cookie
0x1800de235  xor     rax, rsp
0x1800de238  mov     [rbp+var_8], rax
0x1800de23c  xor     eax, eax
0x1800de23e  mov     rsi, rcx
0x1800de241  xorps   xmm0, xmm0
0x1800de244  mov     [rbp+var_10], eax
0x1800de247  mov     ecx, 170h; Size
0x1800de24c  mov     [rbp+var_40], eax
0x1800de24f  movups  [rbp+var_20], xmm0
0x1800de253  mov     [rbp+TokenHandle], rax
0x1800de257  mov     r12, r8
0x1800de25a  mov     r13, rdx
0x1800de25d  xor     r14d, r14d
0x1800de260  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800de265  mov     rcx, rax; this
0x1800de268  mov     [rbp+var_28], rax
0x1800de26c  call    ??0GetPhysicalExtent@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::GetPhysicalExtent::GetPhysicalExtent(void)
0x1800de271  mov     rdi, rax
0x1800de274  test    rax, rax
0x1800de277  jnz     short loc_1800DE281
0x1800de279  lea     ebx, [rax+1Bh]
0x1800de27c  jmp     loc_1800DE51C
0x1800de281  mov     rax, [rax]
0x1800de284  mov     rdx, rsi
0x1800de287  mov     rcx, rdi
0x1800de28a  xor     r15d, r15d
0x1800de28d  mov     rax, [rax+8]
0x1800de291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de296  lea     rcx, [rbp+var_40]
0x1800de29a  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800de29f  mov     [rdi+1Ch], eax
0x1800de2a2  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800de2a6  mov     ecx, [rsi+14h]; unsigned int
0x1800de2a9  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800de2ae  mov     eax, cs:dword_180397B68
0x1800de2b4  cmp     eax, 5
0x1800de2b7  jbe     short loc_1800DE327
0x1800de2b9  mov     rdx, 400000000000h
0x1800de2c3  lea     rcx, dword_180397B68
0x1800de2ca  call    _tlgKeywordOn
0x1800de2cf  test    al, al
0x1800de2d1  jz      short loc_1800DE327
0x1800de2d3  mov     eax, [rbp+var_40]
0x1800de2d6  lea     rdx, word_180333C62
0x1800de2dd  xor     ecx, ecx
0x1800de2df  cmp     [rdi+1Ch], eax
0x1800de2e2  movzx   eax, word ptr [rbp+var_10]
0x1800de2e6  mov     word ptr [rbp+var_40], ax
0x1800de2ea  setnz   cl
0x1800de2ed  mov     eax, [rsi+14h]
0x1800de2f0  mov     [rbp+var_38], eax
0x1800de2f3  lea     rax, [rbp+var_20]
0x1800de2f7  mov     [rbp+var_28], rax
0x1800de2fb  lea     rax, [rbp+var_3C]
0x1800de2ff  mov     [rsp+80h+var_48], rax
0x1800de304  lea     rax, [rbp+var_40]
0x1800de308  mov     [rsp+80h+var_50], rax
0x1800de30d  lea     rax, [rbp+var_38]
0x1800de311  mov     [rsp+80h+var_58], rax
0x1800de316  lea     rax, [rbp+var_28]
0x1800de31a  mov     [rsp+80h+var_60], rax
0x1800de31f  mov     [rbp+var_3C], ecx
0x1800de322  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800de327  mov     rcx, [rsi]
0x1800de32a  test    rcx, rcx
0x1800de32d  jz      loc_1800DE4F2
0x1800de333  mov     rax, [rcx]
0x1800de336  test    rax, rax
0x1800de339  jz      loc_1800DE4F2
0x1800de33f  mov     rax, [rax+18h]
0x1800de343  lea     r8, [rdi+20h]
0x1800de347  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800de34e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de353  mov     ebx, eax
0x1800de355  test    eax, eax
0x1800de357  jnz     loc_1800DE4F7
0x1800de35d  cmp     [rsi+10h], r14d
0x1800de361  jz      loc_1800DE48B
0x1800de367  lea     rbx, [rdi+148h]
0x1800de36e  mov     rcx, rbx
0x1800de371  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800de376  mov     rcx, rbx; struct CSpJobMgr **
0x1800de379  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800de37e  test    eax, eax
0x1800de380  jnz     short loc_1800DE38A
0x1800de382  lea     ebx, [rax+1Ch]
0x1800de385  jmp     loc_1800DE4F7
0x1800de38a  mov     ecx, 10h; Size
0x1800de38f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800de394  xor     r8d, r8d; pcbe
0x1800de397  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800de39e  mov     rdx, rax; pv
0x1800de3a1  mov     r15, rax
0x1800de3a4  mov     [rax], rdi
0x1800de3a7  call    cs:__imp_CreateThreadpoolWork
0x1800de3ad  mov     r14, rax
0x1800de3b0  test    rax, rax
0x1800de3b3  jnz     short loc_1800DE3C1
0x1800de3b5  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800de3ba  mov     ebx, eax
0x1800de3bc  jmp     loc_1800DE4F7
0x1800de3c1  call    cs:__imp_GetCurrentThread
0x1800de3c7  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800de3cb  xor     r8d, r8d; OpenAsSelf
0x1800de3ce  mov     rcx, rax; ThreadHandle
0x1800de3d1  mov     edx, 2000Ch; DesiredAccess
0x1800de3d6  call    cs:__imp_OpenThreadToken
0x1800de3dc  test    eax, eax
0x1800de3de  jnz     short loc_1800DE3ED
0x1800de3e0  call    cs:__imp_GetLastError
0x1800de3e6  cmp     eax, 3F0h
0x1800de3eb  jnz     short loc_1800DE3B5
0x1800de3ed  mov     rax, [rbp+TokenHandle]
0x1800de3f1  mov     r8, r13
0x1800de3f4  mov     [r15+8], rax
0x1800de3f8  mov     rcx, rdi
0x1800de3fb  mov     rax, [rdi]
0x1800de3fe  mov     rdx, [rsi+8]
0x1800de402  mov     rax, [rax+18h]
0x1800de406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de40b  mov     rax, [rdi]
0x1800de40e  mov     rdx, r12
0x1800de411  mov     rcx, rdi
0x1800de414  mov     rax, [rax+28h]
0x1800de418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de41d  mov     ebx, eax
0x1800de41f  test    eax, eax
0x1800de421  jz      short loc_1800DE42C
0x1800de423  cmp     eax, 7
0x1800de426  jnz     loc_1800DE4F7
0x1800de42c  mov     rax, [rdi]
0x1800de42f  mov     rdx, r12
0x1800de432  mov     rcx, rdi
0x1800de435  mov     rax, [rax+38h]
0x1800de439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de43e  mov     ebx, eax
0x1800de440  test    eax, eax
0x1800de442  jnz     loc_1800DE4F7
0x1800de448  mov     rax, [rdi+150h]
0x1800de44f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800de456  jnz     short loc_1800DE46C
0x1800de458  mov     rax, [rdi+158h]
0x1800de45f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800de466  jz      loc_1800DE4F7
0x1800de46c  mov     rdx, r12
0x1800de46f  mov     rcx, rdi
0x1800de472  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800de477  mov     ebx, eax
0x1800de479  test    eax, eax
0x1800de47b  jnz     short loc_1800DE4F7
0x1800de47d  mov     rcx, r14; pwk
0x1800de480  call    cs:__imp_SubmitThreadpoolWork
0x1800de486  jmp     loc_1800DE539
0x1800de48b  mov     rax, [rdi]
0x1800de48e  mov     r8, r13
0x1800de491  mov     rdx, [rsi+8]
0x1800de495  mov     rcx, rdi
0x1800de498  mov     rax, [rax+10h]
0x1800de49c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de4a1  mov     rax, [rdi]
0x1800de4a4  mov     rdx, r12
0x1800de4a7  mov     rcx, rdi
0x1800de4aa  mov     rax, [rax+30h]
0x1800de4ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de4b3  mov     ebx, eax
0x1800de4b5  test    eax, eax
0x1800de4b7  jz      short loc_1800DE4BE
0x1800de4b9  cmp     eax, 7
0x1800de4bc  jnz     short loc_1800DE4F7
0x1800de4be  mov     rax, [rdi]
0x1800de4c1  mov     rdx, r12
0x1800de4c4  mov     rcx, rdi
0x1800de4c7  mov     rax, [rax+28h]
0x1800de4cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de4d0  mov     ebx, eax
0x1800de4d2  test    eax, eax
0x1800de4d4  jz      short loc_1800DE4DB
0x1800de4d6  cmp     eax, 7
0x1800de4d9  jnz     short loc_1800DE4F7
0x1800de4db  mov     rax, [rdi]
0x1800de4de  mov     rdx, r12
0x1800de4e1  mov     rcx, rdi
0x1800de4e4  mov     rax, [rax+38h]
0x1800de4e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de4ed  jmp     loc_1800DE3BA
0x1800de4f2  mov     ebx, 4
0x1800de4f7  mov     rax, [rdi]
0x1800de4fa  mov     edx, 1
0x1800de4ff  mov     rcx, rdi
0x1800de502  mov     rax, [rax]
0x1800de505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de50a  test    r15, r15
0x1800de50d  jz      short loc_1800DE51C
0x1800de50f  mov     edx, 10h
0x1800de514  mov     rcx, r15; Block
0x1800de517  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800de51c  mov     rcx, [rbp+TokenHandle]; hObject
0x1800de520  test    rcx, rcx
0x1800de523  jz      short loc_1800DE52B
0x1800de525  call    cs:__imp_CloseHandle
0x1800de52b  test    r14, r14
0x1800de52e  jz      short loc_1800DE539
0x1800de530  mov     rcx, r14; pwk
0x1800de533  call    cs:__imp_CloseThreadpoolWork
0x1800de539  mov     eax, ebx
0x1800de53b  mov     rcx, [rbp+var_8]
0x1800de53f  xor     rcx, rsp; StackCookie
0x1800de542  call    __security_check_cookie
0x1800de547  mov     rbx, [rsp+80h+arg_18]
0x1800de54f  add     rsp, 80h
0x1800de556  pop     r15
0x1800de558  pop     r14
0x1800de55a  pop     r13
0x1800de55c  pop     r12
0x1800de55e  pop     rdi
0x1800de55f  pop     rsi
0x1800de560  pop     rbp
0x1800de561  retn
```
