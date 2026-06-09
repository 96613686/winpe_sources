# CSpWmiMethod<_SPACES_VirtualDisk_SetUsage>::RunMethod<CSpVirtualDisk::SetUsage,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800e035c`
- end: `0x1800e06aa`
- name: `??$RunMethod@VSetUsage@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_SetUsage@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800e035c`
- `0x1800e0d40`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0528`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e0509`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e0509`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e051e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e051e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e04ef`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e04ef`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e05c8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e05c8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e067b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e067b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e066d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e066d`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_SetUsage>::RunMethod<CSpVirtualDisk::SetUsage,16>(
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
  CSpVirtualDisk::SetUsage *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::SetUsage *)operator new(0x160u);
  v7 = CSpVirtualDisk::SetUsage::SetUsage(v25);
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
      v25 = (CSpVirtualDisk::SetUsage *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&unk_180332748,
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
0x1800e035c  mov     [rsp-38h+arg_18], rbx
0x1800e0361  push    rbp
0x1800e0362  push    rsi
0x1800e0363  push    rdi
0x1800e0364  push    r12
0x1800e0366  push    r13
0x1800e0368  push    r14
0x1800e036a  push    r15
0x1800e036c  mov     rbp, rsp
0x1800e036f  sub     rsp, 80h
0x1800e0376  mov     rax, cs:__security_cookie
0x1800e037d  xor     rax, rsp
0x1800e0380  mov     [rbp+var_8], rax
0x1800e0384  xor     eax, eax
0x1800e0386  mov     rsi, rcx
0x1800e0389  xorps   xmm0, xmm0
0x1800e038c  mov     [rbp+var_10], eax
0x1800e038f  mov     ecx, 160h; Size
0x1800e0394  mov     [rbp+var_40], eax
0x1800e0397  movups  [rbp+var_20], xmm0
0x1800e039b  mov     [rbp+TokenHandle], rax
0x1800e039f  mov     r12, r8
0x1800e03a2  mov     r13, rdx
0x1800e03a5  xor     r14d, r14d
0x1800e03a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e03ad  mov     rcx, rax; this
0x1800e03b0  mov     [rbp+var_28], rax
0x1800e03b4  call    ??0SetUsage@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::SetUsage::SetUsage(void)
0x1800e03b9  mov     rdi, rax
0x1800e03bc  test    rax, rax
0x1800e03bf  jnz     short loc_1800E03C9
0x1800e03c1  lea     ebx, [rax+1Bh]
0x1800e03c4  jmp     loc_1800E0664
0x1800e03c9  mov     rax, [rax]
0x1800e03cc  mov     rdx, rsi
0x1800e03cf  mov     rcx, rdi
0x1800e03d2  xor     r15d, r15d
0x1800e03d5  mov     rax, [rax+8]
0x1800e03d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e03de  lea     rcx, [rbp+var_40]
0x1800e03e2  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800e03e7  mov     [rdi+1Ch], eax
0x1800e03ea  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800e03ee  mov     ecx, [rsi+14h]; unsigned int
0x1800e03f1  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800e03f6  mov     eax, cs:dword_180397B68
0x1800e03fc  cmp     eax, 5
0x1800e03ff  jbe     short loc_1800E046F
0x1800e0401  mov     rdx, 400000000000h
0x1800e040b  lea     rcx, dword_180397B68
0x1800e0412  call    _tlgKeywordOn
0x1800e0417  test    al, al
0x1800e0419  jz      short loc_1800E046F
0x1800e041b  mov     eax, [rbp+var_40]
0x1800e041e  lea     rdx, unk_180332748
0x1800e0425  xor     ecx, ecx
0x1800e0427  cmp     [rdi+1Ch], eax
0x1800e042a  movzx   eax, word ptr [rbp+var_10]
0x1800e042e  mov     word ptr [rbp+var_40], ax
0x1800e0432  setnz   cl
0x1800e0435  mov     eax, [rsi+14h]
0x1800e0438  mov     [rbp+var_38], eax
0x1800e043b  lea     rax, [rbp+var_20]
0x1800e043f  mov     [rbp+var_28], rax
0x1800e0443  lea     rax, [rbp+var_3C]
0x1800e0447  mov     [rsp+80h+var_48], rax
0x1800e044c  lea     rax, [rbp+var_40]
0x1800e0450  mov     [rsp+80h+var_50], rax
0x1800e0455  lea     rax, [rbp+var_38]
0x1800e0459  mov     [rsp+80h+var_58], rax
0x1800e045e  lea     rax, [rbp+var_28]
0x1800e0462  mov     [rsp+80h+var_60], rax
0x1800e0467  mov     [rbp+var_3C], ecx
0x1800e046a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800e046f  mov     rcx, [rsi]
0x1800e0472  test    rcx, rcx
0x1800e0475  jz      loc_1800E063A
0x1800e047b  mov     rax, [rcx]
0x1800e047e  test    rax, rax
0x1800e0481  jz      loc_1800E063A
0x1800e0487  mov     rax, [rax+18h]
0x1800e048b  lea     r8, [rdi+20h]
0x1800e048f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800e0496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e049b  mov     ebx, eax
0x1800e049d  test    eax, eax
0x1800e049f  jnz     loc_1800E063F
0x1800e04a5  cmp     [rsi+10h], r14d
0x1800e04a9  jz      loc_1800E05D3
0x1800e04af  lea     rbx, [rdi+148h]
0x1800e04b6  mov     rcx, rbx
0x1800e04b9  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800e04be  mov     rcx, rbx; struct CSpJobMgr **
0x1800e04c1  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800e04c6  test    eax, eax
0x1800e04c8  jnz     short loc_1800E04D2
0x1800e04ca  lea     ebx, [rax+1Ch]
0x1800e04cd  jmp     loc_1800E063F
0x1800e04d2  mov     ecx, 10h; Size
0x1800e04d7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e04dc  xor     r8d, r8d; pcbe
0x1800e04df  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800e04e6  mov     rdx, rax; pv
0x1800e04e9  mov     r15, rax
0x1800e04ec  mov     [rax], rdi
0x1800e04ef  call    cs:__imp_CreateThreadpoolWork
0x1800e04f5  mov     r14, rax
0x1800e04f8  test    rax, rax
0x1800e04fb  jnz     short loc_1800E0509
0x1800e04fd  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800e0502  mov     ebx, eax
0x1800e0504  jmp     loc_1800E063F
0x1800e0509  call    cs:__imp_GetCurrentThread
0x1800e050f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800e0513  xor     r8d, r8d; OpenAsSelf
0x1800e0516  mov     rcx, rax; ThreadHandle
0x1800e0519  mov     edx, 2000Ch; DesiredAccess
0x1800e051e  call    cs:__imp_OpenThreadToken
0x1800e0524  test    eax, eax
0x1800e0526  jnz     short loc_1800E0535
0x1800e0528  call    cs:__imp_GetLastError
0x1800e052e  cmp     eax, 3F0h
0x1800e0533  jnz     short loc_1800E04FD
0x1800e0535  mov     rax, [rbp+TokenHandle]
0x1800e0539  mov     r8, r13
0x1800e053c  mov     [r15+8], rax
0x1800e0540  mov     rcx, rdi
0x1800e0543  mov     rax, [rdi]
0x1800e0546  mov     rdx, [rsi+8]
0x1800e054a  mov     rax, [rax+18h]
0x1800e054e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0553  mov     rax, [rdi]
0x1800e0556  mov     rdx, r12
0x1800e0559  mov     rcx, rdi
0x1800e055c  mov     rax, [rax+28h]
0x1800e0560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0565  mov     ebx, eax
0x1800e0567  test    eax, eax
0x1800e0569  jz      short loc_1800E0574
0x1800e056b  cmp     eax, 7
0x1800e056e  jnz     loc_1800E063F
0x1800e0574  mov     rax, [rdi]
0x1800e0577  mov     rdx, r12
0x1800e057a  mov     rcx, rdi
0x1800e057d  mov     rax, [rax+38h]
0x1800e0581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0586  mov     ebx, eax
0x1800e0588  test    eax, eax
0x1800e058a  jnz     loc_1800E063F
0x1800e0590  mov     rax, [rdi+150h]
0x1800e0597  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800e059e  jnz     short loc_1800E05B4
0x1800e05a0  mov     rax, [rdi+158h]
0x1800e05a7  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800e05ae  jz      loc_1800E063F
0x1800e05b4  mov     rdx, r12
0x1800e05b7  mov     rcx, rdi
0x1800e05ba  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800e05bf  mov     ebx, eax
0x1800e05c1  test    eax, eax
0x1800e05c3  jnz     short loc_1800E063F
0x1800e05c5  mov     rcx, r14; pwk
0x1800e05c8  call    cs:__imp_SubmitThreadpoolWork
0x1800e05ce  jmp     loc_1800E0681
0x1800e05d3  mov     rax, [rdi]
0x1800e05d6  mov     r8, r13
0x1800e05d9  mov     rdx, [rsi+8]
0x1800e05dd  mov     rcx, rdi
0x1800e05e0  mov     rax, [rax+10h]
0x1800e05e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e05e9  mov     rax, [rdi]
0x1800e05ec  mov     rdx, r12
0x1800e05ef  mov     rcx, rdi
0x1800e05f2  mov     rax, [rax+30h]
0x1800e05f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e05fb  mov     ebx, eax
0x1800e05fd  test    eax, eax
0x1800e05ff  jz      short loc_1800E0606
0x1800e0601  cmp     eax, 7
0x1800e0604  jnz     short loc_1800E063F
0x1800e0606  mov     rax, [rdi]
0x1800e0609  mov     rdx, r12
0x1800e060c  mov     rcx, rdi
0x1800e060f  mov     rax, [rax+28h]
0x1800e0613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0618  mov     ebx, eax
0x1800e061a  test    eax, eax
0x1800e061c  jz      short loc_1800E0623
0x1800e061e  cmp     eax, 7
0x1800e0621  jnz     short loc_1800E063F
0x1800e0623  mov     rax, [rdi]
0x1800e0626  mov     rdx, r12
0x1800e0629  mov     rcx, rdi
0x1800e062c  mov     rax, [rax+38h]
0x1800e0630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0635  jmp     loc_1800E0502
0x1800e063a  mov     ebx, 4
0x1800e063f  mov     rax, [rdi]
0x1800e0642  mov     edx, 1
0x1800e0647  mov     rcx, rdi
0x1800e064a  mov     rax, [rax]
0x1800e064d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0652  test    r15, r15
0x1800e0655  jz      short loc_1800E0664
0x1800e0657  mov     edx, 10h
0x1800e065c  mov     rcx, r15; Block
0x1800e065f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e0664  mov     rcx, [rbp+TokenHandle]; hObject
0x1800e0668  test    rcx, rcx
0x1800e066b  jz      short loc_1800E0673
0x1800e066d  call    cs:__imp_CloseHandle
0x1800e0673  test    r14, r14
0x1800e0676  jz      short loc_1800E0681
0x1800e0678  mov     rcx, r14; pwk
0x1800e067b  call    cs:__imp_CloseThreadpoolWork
0x1800e0681  mov     eax, ebx
0x1800e0683  mov     rcx, [rbp+var_8]
0x1800e0687  xor     rcx, rsp; StackCookie
0x1800e068a  call    __security_check_cookie
0x1800e068f  mov     rbx, [rsp+80h+arg_18]
0x1800e0697  add     rsp, 80h
0x1800e069e  pop     r15
0x1800e06a0  pop     r14
0x1800e06a2  pop     r13
0x1800e06a4  pop     r12
0x1800e06a6  pop     rdi
0x1800e06a7  pop     rsi
0x1800e06a8  pop     rbp
0x1800e06a9  retn
```
