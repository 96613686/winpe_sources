# CSpWmiMethod<_MI_Instance>::RunMethod<CSpStoragePool::CreateStorageTier,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800ba8d4`
- end: `0x1800bac22`
- name: `??$RunMethod@VCreateStorageTier@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_MI_Instance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800ba8d4`
- `0x1800bdc28`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800baaa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800baaa0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800baa81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800baa81`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800baa96`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800baa96`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800baa67`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800baa67`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bab40`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bab40`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800babf3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800babf3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800babe5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800babe5`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_MI_Instance>::RunMethod<CSpStoragePool::CreateStorageTier,11>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 StorageTier; // rax
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
  CSpStoragePool::CreateStorageTier *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStoragePool::CreateStorageTier *)operator new(0x1D0u);
  StorageTier = CSpStoragePool::CreateStorageTier::CreateStorageTier(v25);
  v8 = StorageTier;
  if ( StorageTier )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)StorageTier + 8LL))(StorageTier, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStoragePool::CreateStorageTier *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&word_18032BBA6,
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
0x1800ba8d4  mov     [rsp-38h+arg_18], rbx
0x1800ba8d9  push    rbp
0x1800ba8da  push    rsi
0x1800ba8db  push    rdi
0x1800ba8dc  push    r12
0x1800ba8de  push    r13
0x1800ba8e0  push    r14
0x1800ba8e2  push    r15
0x1800ba8e4  mov     rbp, rsp
0x1800ba8e7  sub     rsp, 80h
0x1800ba8ee  mov     rax, cs:__security_cookie
0x1800ba8f5  xor     rax, rsp
0x1800ba8f8  mov     [rbp+var_8], rax
0x1800ba8fc  xor     eax, eax
0x1800ba8fe  mov     rsi, rcx
0x1800ba901  xorps   xmm0, xmm0
0x1800ba904  mov     [rbp+var_10], eax
0x1800ba907  mov     ecx, 1D0h; Size
0x1800ba90c  mov     [rbp+var_40], eax
0x1800ba90f  movups  [rbp+var_20], xmm0
0x1800ba913  mov     [rbp+TokenHandle], rax
0x1800ba917  mov     r12, r8
0x1800ba91a  mov     r13, rdx
0x1800ba91d  xor     r14d, r14d
0x1800ba920  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ba925  mov     rcx, rax; this
0x1800ba928  mov     [rbp+var_28], rax
0x1800ba92c  call    ??0CreateStorageTier@CSpStoragePool@@QEAA@XZ; CSpStoragePool::CreateStorageTier::CreateStorageTier(void)
0x1800ba931  mov     rdi, rax
0x1800ba934  test    rax, rax
0x1800ba937  jnz     short loc_1800BA941
0x1800ba939  lea     ebx, [rax+1Bh]
0x1800ba93c  jmp     loc_1800BABDC
0x1800ba941  mov     rax, [rax]
0x1800ba944  mov     rdx, rsi
0x1800ba947  mov     rcx, rdi
0x1800ba94a  xor     r15d, r15d
0x1800ba94d  mov     rax, [rax+8]
0x1800ba951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba956  lea     rcx, [rbp+var_40]
0x1800ba95a  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800ba95f  mov     [rdi+1Ch], eax
0x1800ba962  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800ba966  mov     ecx, [rsi+14h]; unsigned int
0x1800ba969  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800ba96e  mov     eax, cs:dword_180397B68
0x1800ba974  cmp     eax, 5
0x1800ba977  jbe     short loc_1800BA9E7
0x1800ba979  mov     rdx, 400000000000h
0x1800ba983  lea     rcx, dword_180397B68
0x1800ba98a  call    _tlgKeywordOn
0x1800ba98f  test    al, al
0x1800ba991  jz      short loc_1800BA9E7
0x1800ba993  mov     eax, [rbp+var_40]
0x1800ba996  lea     rdx, word_18032BBA6
0x1800ba99d  xor     ecx, ecx
0x1800ba99f  cmp     [rdi+1Ch], eax
0x1800ba9a2  movzx   eax, word ptr [rbp+var_10]
0x1800ba9a6  mov     word ptr [rbp+var_40], ax
0x1800ba9aa  setnz   cl
0x1800ba9ad  mov     eax, [rsi+14h]
0x1800ba9b0  mov     [rbp+var_38], eax
0x1800ba9b3  lea     rax, [rbp+var_20]
0x1800ba9b7  mov     [rbp+var_28], rax
0x1800ba9bb  lea     rax, [rbp+var_3C]
0x1800ba9bf  mov     [rsp+80h+var_48], rax
0x1800ba9c4  lea     rax, [rbp+var_40]
0x1800ba9c8  mov     [rsp+80h+var_50], rax
0x1800ba9cd  lea     rax, [rbp+var_38]
0x1800ba9d1  mov     [rsp+80h+var_58], rax
0x1800ba9d6  lea     rax, [rbp+var_28]
0x1800ba9da  mov     [rsp+80h+var_60], rax
0x1800ba9df  mov     [rbp+var_3C], ecx
0x1800ba9e2  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800ba9e7  mov     rcx, [rsi]
0x1800ba9ea  test    rcx, rcx
0x1800ba9ed  jz      loc_1800BABB2
0x1800ba9f3  mov     rax, [rcx]
0x1800ba9f6  test    rax, rax
0x1800ba9f9  jz      loc_1800BABB2
0x1800ba9ff  mov     rax, [rax+18h]
0x1800baa03  lea     r8, [rdi+20h]
0x1800baa07  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800baa0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baa13  mov     ebx, eax
0x1800baa15  test    eax, eax
0x1800baa17  jnz     loc_1800BABB7
0x1800baa1d  cmp     [rsi+10h], r14d
0x1800baa21  jz      loc_1800BAB4B
0x1800baa27  lea     rbx, [rdi+148h]
0x1800baa2e  mov     rcx, rbx
0x1800baa31  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800baa36  mov     rcx, rbx; struct CSpJobMgr **
0x1800baa39  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800baa3e  test    eax, eax
0x1800baa40  jnz     short loc_1800BAA4A
0x1800baa42  lea     ebx, [rax+1Ch]
0x1800baa45  jmp     loc_1800BABB7
0x1800baa4a  mov     ecx, 10h; Size
0x1800baa4f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800baa54  xor     r8d, r8d; pcbe
0x1800baa57  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800baa5e  mov     rdx, rax; pv
0x1800baa61  mov     r15, rax
0x1800baa64  mov     [rax], rdi
0x1800baa67  call    cs:__imp_CreateThreadpoolWork
0x1800baa6d  mov     r14, rax
0x1800baa70  test    rax, rax
0x1800baa73  jnz     short loc_1800BAA81
0x1800baa75  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800baa7a  mov     ebx, eax
0x1800baa7c  jmp     loc_1800BABB7
0x1800baa81  call    cs:__imp_GetCurrentThread
0x1800baa87  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800baa8b  xor     r8d, r8d; OpenAsSelf
0x1800baa8e  mov     rcx, rax; ThreadHandle
0x1800baa91  mov     edx, 2000Ch; DesiredAccess
0x1800baa96  call    cs:__imp_OpenThreadToken
0x1800baa9c  test    eax, eax
0x1800baa9e  jnz     short loc_1800BAAAD
0x1800baaa0  call    cs:__imp_GetLastError
0x1800baaa6  cmp     eax, 3F0h
0x1800baaab  jnz     short loc_1800BAA75
0x1800baaad  mov     rax, [rbp+TokenHandle]
0x1800baab1  mov     r8, r13
0x1800baab4  mov     [r15+8], rax
0x1800baab8  mov     rcx, rdi
0x1800baabb  mov     rax, [rdi]
0x1800baabe  mov     rdx, [rsi+8]
0x1800baac2  mov     rax, [rax+18h]
0x1800baac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baacb  mov     rax, [rdi]
0x1800baace  mov     rdx, r12
0x1800baad1  mov     rcx, rdi
0x1800baad4  mov     rax, [rax+28h]
0x1800baad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baadd  mov     ebx, eax
0x1800baadf  test    eax, eax
0x1800baae1  jz      short loc_1800BAAEC
0x1800baae3  cmp     eax, 7
0x1800baae6  jnz     loc_1800BABB7
0x1800baaec  mov     rax, [rdi]
0x1800baaef  mov     rdx, r12
0x1800baaf2  mov     rcx, rdi
0x1800baaf5  mov     rax, [rax+38h]
0x1800baaf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baafe  mov     ebx, eax
0x1800bab00  test    eax, eax
0x1800bab02  jnz     loc_1800BABB7
0x1800bab08  mov     rax, [rdi+150h]
0x1800bab0f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bab16  jnz     short loc_1800BAB2C
0x1800bab18  mov     rax, [rdi+158h]
0x1800bab1f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800bab26  jz      loc_1800BABB7
0x1800bab2c  mov     rdx, r12
0x1800bab2f  mov     rcx, rdi
0x1800bab32  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800bab37  mov     ebx, eax
0x1800bab39  test    eax, eax
0x1800bab3b  jnz     short loc_1800BABB7
0x1800bab3d  mov     rcx, r14; pwk
0x1800bab40  call    cs:__imp_SubmitThreadpoolWork
0x1800bab46  jmp     loc_1800BABF9
0x1800bab4b  mov     rax, [rdi]
0x1800bab4e  mov     r8, r13
0x1800bab51  mov     rdx, [rsi+8]
0x1800bab55  mov     rcx, rdi
0x1800bab58  mov     rax, [rax+10h]
0x1800bab5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bab61  mov     rax, [rdi]
0x1800bab64  mov     rdx, r12
0x1800bab67  mov     rcx, rdi
0x1800bab6a  mov     rax, [rax+30h]
0x1800bab6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bab73  mov     ebx, eax
0x1800bab75  test    eax, eax
0x1800bab77  jz      short loc_1800BAB7E
0x1800bab79  cmp     eax, 7
0x1800bab7c  jnz     short loc_1800BABB7
0x1800bab7e  mov     rax, [rdi]
0x1800bab81  mov     rdx, r12
0x1800bab84  mov     rcx, rdi
0x1800bab87  mov     rax, [rax+28h]
0x1800bab8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bab90  mov     ebx, eax
0x1800bab92  test    eax, eax
0x1800bab94  jz      short loc_1800BAB9B
0x1800bab96  cmp     eax, 7
0x1800bab99  jnz     short loc_1800BABB7
0x1800bab9b  mov     rax, [rdi]
0x1800bab9e  mov     rdx, r12
0x1800baba1  mov     rcx, rdi
0x1800baba4  mov     rax, [rax+38h]
0x1800baba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800babad  jmp     loc_1800BAA7A
0x1800babb2  mov     ebx, 4
0x1800babb7  mov     rax, [rdi]
0x1800babba  mov     edx, 1
0x1800babbf  mov     rcx, rdi
0x1800babc2  mov     rax, [rax]
0x1800babc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800babca  test    r15, r15
0x1800babcd  jz      short loc_1800BABDC
0x1800babcf  mov     edx, 10h
0x1800babd4  mov     rcx, r15; Block
0x1800babd7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800babdc  mov     rcx, [rbp+TokenHandle]; hObject
0x1800babe0  test    rcx, rcx
0x1800babe3  jz      short loc_1800BABEB
0x1800babe5  call    cs:__imp_CloseHandle
0x1800babeb  test    r14, r14
0x1800babee  jz      short loc_1800BABF9
0x1800babf0  mov     rcx, r14; pwk
0x1800babf3  call    cs:__imp_CloseThreadpoolWork
0x1800babf9  mov     eax, ebx
0x1800babfb  mov     rcx, [rbp+var_8]
0x1800babff  xor     rcx, rsp; StackCookie
0x1800bac02  call    __security_check_cookie
0x1800bac07  mov     rbx, [rsp+80h+arg_18]
0x1800bac0f  add     rsp, 80h
0x1800bac16  pop     r15
0x1800bac18  pop     r14
0x1800bac1a  pop     r13
0x1800bac1c  pop     r12
0x1800bac1e  pop     rdi
0x1800bac1f  pop     rsi
0x1800bac20  pop     rbp
0x1800bac21  retn
```
