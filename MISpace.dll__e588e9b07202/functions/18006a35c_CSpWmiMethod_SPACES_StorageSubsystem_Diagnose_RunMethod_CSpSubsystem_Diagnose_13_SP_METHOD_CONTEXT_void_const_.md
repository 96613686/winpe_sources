# CSpWmiMethod<_SPACES_StorageSubsystem_Diagnose>::RunMethod<CSpSubsystem::Diagnose,13>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18006a35c`
- end: `0x18006a6aa`
- name: `??$RunMethod@VDiagnose@CSpSubsystem@@$0N@@?$CSpWmiMethod@U_SPACES_StorageSubsystem_Diagnose@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x18006a35c`
- `0x18006be58`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a528`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006a509`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006a509`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006a51e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006a51e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006a4ef`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006a4ef`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006a5c8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006a5c8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006a67b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006a67b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006a66d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006a66d`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageSubsystem_Diagnose>::RunMethod<CSpSubsystem::Diagnose,13>(
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
  CSpSubsystem::Diagnose *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpSubsystem::Diagnose *)operator new(0x168u);
  v7 = CSpSubsystem::Diagnose::Diagnose(v25);
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
      v25 = (CSpSubsystem::Diagnose *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&unk_180311278,
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
0x18006a35c  mov     [rsp-38h+arg_18], rbx
0x18006a361  push    rbp
0x18006a362  push    rsi
0x18006a363  push    rdi
0x18006a364  push    r12
0x18006a366  push    r13
0x18006a368  push    r14
0x18006a36a  push    r15
0x18006a36c  mov     rbp, rsp
0x18006a36f  sub     rsp, 80h
0x18006a376  mov     rax, cs:__security_cookie
0x18006a37d  xor     rax, rsp
0x18006a380  mov     [rbp+var_8], rax
0x18006a384  xor     eax, eax
0x18006a386  mov     rsi, rcx
0x18006a389  xorps   xmm0, xmm0
0x18006a38c  mov     [rbp+var_10], eax
0x18006a38f  mov     ecx, 168h; Size
0x18006a394  mov     [rbp+var_40], eax
0x18006a397  movups  [rbp+var_20], xmm0
0x18006a39b  mov     [rbp+TokenHandle], rax
0x18006a39f  mov     r12, r8
0x18006a3a2  mov     r13, rdx
0x18006a3a5  xor     r14d, r14d
0x18006a3a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006a3ad  mov     rcx, rax; this
0x18006a3b0  mov     [rbp+var_28], rax
0x18006a3b4  call    ??0Diagnose@CSpSubsystem@@QEAA@XZ; CSpSubsystem::Diagnose::Diagnose(void)
0x18006a3b9  mov     rdi, rax
0x18006a3bc  test    rax, rax
0x18006a3bf  jnz     short loc_18006A3C9
0x18006a3c1  lea     ebx, [rax+1Bh]
0x18006a3c4  jmp     loc_18006A664
0x18006a3c9  mov     rax, [rax]
0x18006a3cc  mov     rdx, rsi
0x18006a3cf  mov     rcx, rdi
0x18006a3d2  xor     r15d, r15d
0x18006a3d5  mov     rax, [rax+8]
0x18006a3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a3de  lea     rcx, [rbp+var_40]
0x18006a3e2  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18006a3e7  mov     [rdi+1Ch], eax
0x18006a3ea  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18006a3ee  mov     ecx, [rsi+14h]; unsigned int
0x18006a3f1  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18006a3f6  mov     eax, cs:dword_180397B68
0x18006a3fc  cmp     eax, 5
0x18006a3ff  jbe     short loc_18006A46F
0x18006a401  mov     rdx, 400000000000h
0x18006a40b  lea     rcx, dword_180397B68
0x18006a412  call    _tlgKeywordOn
0x18006a417  test    al, al
0x18006a419  jz      short loc_18006A46F
0x18006a41b  mov     eax, [rbp+var_40]
0x18006a41e  lea     rdx, unk_180311278
0x18006a425  xor     ecx, ecx
0x18006a427  cmp     [rdi+1Ch], eax
0x18006a42a  movzx   eax, word ptr [rbp+var_10]
0x18006a42e  mov     word ptr [rbp+var_40], ax
0x18006a432  setnz   cl
0x18006a435  mov     eax, [rsi+14h]
0x18006a438  mov     [rbp+var_38], eax
0x18006a43b  lea     rax, [rbp+var_20]
0x18006a43f  mov     [rbp+var_28], rax
0x18006a443  lea     rax, [rbp+var_3C]
0x18006a447  mov     [rsp+80h+var_48], rax
0x18006a44c  lea     rax, [rbp+var_40]
0x18006a450  mov     [rsp+80h+var_50], rax
0x18006a455  lea     rax, [rbp+var_38]
0x18006a459  mov     [rsp+80h+var_58], rax
0x18006a45e  lea     rax, [rbp+var_28]
0x18006a462  mov     [rsp+80h+var_60], rax
0x18006a467  mov     [rbp+var_3C], ecx
0x18006a46a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18006a46f  mov     rcx, [rsi]
0x18006a472  test    rcx, rcx
0x18006a475  jz      loc_18006A63A
0x18006a47b  mov     rax, [rcx]
0x18006a47e  test    rax, rax
0x18006a481  jz      loc_18006A63A
0x18006a487  mov     rax, [rax+18h]
0x18006a48b  lea     r8, [rdi+20h]
0x18006a48f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18006a496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a49b  mov     ebx, eax
0x18006a49d  test    eax, eax
0x18006a49f  jnz     loc_18006A63F
0x18006a4a5  cmp     [rsi+10h], r14d
0x18006a4a9  jz      loc_18006A5D3
0x18006a4af  lea     rbx, [rdi+148h]
0x18006a4b6  mov     rcx, rbx
0x18006a4b9  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18006a4be  mov     rcx, rbx; struct CSpJobMgr **
0x18006a4c1  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18006a4c6  test    eax, eax
0x18006a4c8  jnz     short loc_18006A4D2
0x18006a4ca  lea     ebx, [rax+1Ch]
0x18006a4cd  jmp     loc_18006A63F
0x18006a4d2  mov     ecx, 10h; Size
0x18006a4d7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006a4dc  xor     r8d, r8d; pcbe
0x18006a4df  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18006a4e6  mov     rdx, rax; pv
0x18006a4e9  mov     r15, rax
0x18006a4ec  mov     [rax], rdi
0x18006a4ef  call    cs:__imp_CreateThreadpoolWork
0x18006a4f5  mov     r14, rax
0x18006a4f8  test    rax, rax
0x18006a4fb  jnz     short loc_18006A509
0x18006a4fd  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18006a502  mov     ebx, eax
0x18006a504  jmp     loc_18006A63F
0x18006a509  call    cs:__imp_GetCurrentThread
0x18006a50f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18006a513  xor     r8d, r8d; OpenAsSelf
0x18006a516  mov     rcx, rax; ThreadHandle
0x18006a519  mov     edx, 2000Ch; DesiredAccess
0x18006a51e  call    cs:__imp_OpenThreadToken
0x18006a524  test    eax, eax
0x18006a526  jnz     short loc_18006A535
0x18006a528  call    cs:__imp_GetLastError
0x18006a52e  cmp     eax, 3F0h
0x18006a533  jnz     short loc_18006A4FD
0x18006a535  mov     rax, [rbp+TokenHandle]
0x18006a539  mov     r8, r13
0x18006a53c  mov     [r15+8], rax
0x18006a540  mov     rcx, rdi
0x18006a543  mov     rax, [rdi]
0x18006a546  mov     rdx, [rsi+8]
0x18006a54a  mov     rax, [rax+18h]
0x18006a54e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a553  mov     rax, [rdi]
0x18006a556  mov     rdx, r12
0x18006a559  mov     rcx, rdi
0x18006a55c  mov     rax, [rax+28h]
0x18006a560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a565  mov     ebx, eax
0x18006a567  test    eax, eax
0x18006a569  jz      short loc_18006A574
0x18006a56b  cmp     eax, 7
0x18006a56e  jnz     loc_18006A63F
0x18006a574  mov     rax, [rdi]
0x18006a577  mov     rdx, r12
0x18006a57a  mov     rcx, rdi
0x18006a57d  mov     rax, [rax+38h]
0x18006a581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a586  mov     ebx, eax
0x18006a588  test    eax, eax
0x18006a58a  jnz     loc_18006A63F
0x18006a590  mov     rax, [rdi+150h]
0x18006a597  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18006a59e  jnz     short loc_18006A5B4
0x18006a5a0  mov     rax, [rdi+158h]
0x18006a5a7  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18006a5ae  jz      loc_18006A63F
0x18006a5b4  mov     rdx, r12
0x18006a5b7  mov     rcx, rdi
0x18006a5ba  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18006a5bf  mov     ebx, eax
0x18006a5c1  test    eax, eax
0x18006a5c3  jnz     short loc_18006A63F
0x18006a5c5  mov     rcx, r14; pwk
0x18006a5c8  call    cs:__imp_SubmitThreadpoolWork
0x18006a5ce  jmp     loc_18006A681
0x18006a5d3  mov     rax, [rdi]
0x18006a5d6  mov     r8, r13
0x18006a5d9  mov     rdx, [rsi+8]
0x18006a5dd  mov     rcx, rdi
0x18006a5e0  mov     rax, [rax+10h]
0x18006a5e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a5e9  mov     rax, [rdi]
0x18006a5ec  mov     rdx, r12
0x18006a5ef  mov     rcx, rdi
0x18006a5f2  mov     rax, [rax+30h]
0x18006a5f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a5fb  mov     ebx, eax
0x18006a5fd  test    eax, eax
0x18006a5ff  jz      short loc_18006A606
0x18006a601  cmp     eax, 7
0x18006a604  jnz     short loc_18006A63F
0x18006a606  mov     rax, [rdi]
0x18006a609  mov     rdx, r12
0x18006a60c  mov     rcx, rdi
0x18006a60f  mov     rax, [rax+28h]
0x18006a613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a618  mov     ebx, eax
0x18006a61a  test    eax, eax
0x18006a61c  jz      short loc_18006A623
0x18006a61e  cmp     eax, 7
0x18006a621  jnz     short loc_18006A63F
0x18006a623  mov     rax, [rdi]
0x18006a626  mov     rdx, r12
0x18006a629  mov     rcx, rdi
0x18006a62c  mov     rax, [rax+38h]
0x18006a630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a635  jmp     loc_18006A502
0x18006a63a  mov     ebx, 4
0x18006a63f  mov     rax, [rdi]
0x18006a642  mov     edx, 1
0x18006a647  mov     rcx, rdi
0x18006a64a  mov     rax, [rax]
0x18006a64d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a652  test    r15, r15
0x18006a655  jz      short loc_18006A664
0x18006a657  mov     edx, 10h
0x18006a65c  mov     rcx, r15; Block
0x18006a65f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006a664  mov     rcx, [rbp+TokenHandle]; hObject
0x18006a668  test    rcx, rcx
0x18006a66b  jz      short loc_18006A673
0x18006a66d  call    cs:__imp_CloseHandle
0x18006a673  test    r14, r14
0x18006a676  jz      short loc_18006A681
0x18006a678  mov     rcx, r14; pwk
0x18006a67b  call    cs:__imp_CloseThreadpoolWork
0x18006a681  mov     eax, ebx
0x18006a683  mov     rcx, [rbp+var_8]
0x18006a687  xor     rcx, rsp; StackCookie
0x18006a68a  call    __security_check_cookie
0x18006a68f  mov     rbx, [rsp+80h+arg_18]
0x18006a697  add     rsp, 80h
0x18006a69e  pop     r15
0x18006a6a0  pop     r14
0x18006a6a2  pop     r13
0x18006a6a4  pop     r12
0x18006a6a6  pop     rdi
0x18006a6a7  pop     rsi
0x18006a6a8  pop     rbp
0x18006a6a9  retn
```
