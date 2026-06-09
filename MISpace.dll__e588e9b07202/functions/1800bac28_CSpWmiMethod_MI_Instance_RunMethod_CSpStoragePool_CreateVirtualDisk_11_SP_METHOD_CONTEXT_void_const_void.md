# CSpWmiMethod<_MI_Instance>::RunMethod<CSpStoragePool::CreateVirtualDisk,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800bac28`
- end: `0x1800baf76`
- name: `??$RunMethod@VCreateVirtualDisk@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_MI_Instance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800c1f80`
- `0x1800c9d40`

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
- `0x1800bac28`
- `0x1800bdd04`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800badf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800badf4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800badd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800badd5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800badea`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800badea`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800badbb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800badbb`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bae94`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bae94`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800baf47`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800baf47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800baf39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800baf39`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_MI_Instance>::RunMethod<CSpStoragePool::CreateVirtualDisk,11>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 VirtualDisk; // rax
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
  CSpStoragePool::CreateVirtualDisk *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStoragePool::CreateVirtualDisk *)operator new(0x260u);
  VirtualDisk = CSpStoragePool::CreateVirtualDisk::CreateVirtualDisk(v25);
  v8 = VirtualDisk;
  if ( VirtualDisk )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)VirtualDisk + 8LL))(VirtualDisk, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStoragePool::CreateVirtualDisk *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_180328193,
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
0x1800bac28  mov     [rsp-38h+arg_18], rbx
0x1800bac2d  push    rbp
0x1800bac2e  push    rsi
0x1800bac2f  push    rdi
0x1800bac30  push    r12
0x1800bac32  push    r13
0x1800bac34  push    r14
0x1800bac36  push    r15
0x1800bac38  mov     rbp, rsp
0x1800bac3b  sub     rsp, 80h
0x1800bac42  mov     rax, cs:__security_cookie
0x1800bac49  xor     rax, rsp
0x1800bac4c  mov     [rbp+var_8], rax
0x1800bac50  xor     eax, eax
0x1800bac52  mov     rsi, rcx
0x1800bac55  xorps   xmm0, xmm0
0x1800bac58  mov     [rbp+var_10], eax
0x1800bac5b  mov     ecx, 260h; Size
0x1800bac60  mov     [rbp+var_40], eax
0x1800bac63  movups  [rbp+var_20], xmm0
0x1800bac67  mov     [rbp+TokenHandle], rax
0x1800bac6b  mov     r12, r8
0x1800bac6e  mov     r13, rdx
0x1800bac71  xor     r14d, r14d
0x1800bac74  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bac79  mov     rcx, rax; this
0x1800bac7c  mov     [rbp+var_28], rax
0x1800bac80  call    ??0CreateVirtualDisk@CSpStoragePool@@QEAA@XZ; CSpStoragePool::CreateVirtualDisk::CreateVirtualDisk(void)
0x1800bac85  mov     rdi, rax
0x1800bac88  test    rax, rax
0x1800bac8b  jnz     short loc_1800BAC95
0x1800bac8d  lea     ebx, [rax+1Bh]
0x1800bac90  jmp     loc_1800BAF30
0x1800bac95  mov     rax, [rax]
0x1800bac98  mov     rdx, rsi
0x1800bac9b  mov     rcx, rdi
0x1800bac9e  xor     r15d, r15d
0x1800baca1  mov     rax, [rax+8]
0x1800baca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bacaa  lea     rcx, [rbp+var_40]
0x1800bacae  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800bacb3  mov     [rdi+1Ch], eax
0x1800bacb6  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800bacba  mov     ecx, [rsi+14h]; unsigned int
0x1800bacbd  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800bacc2  mov     eax, cs:dword_180397B68
0x1800bacc8  cmp     eax, 5
0x1800baccb  jbe     short loc_1800BAD3B
0x1800baccd  mov     rdx, 400000000000h
0x1800bacd7  lea     rcx, dword_180397B68
0x1800bacde  call    _tlgKeywordOn
0x1800bace3  test    al, al
0x1800bace5  jz      short loc_1800BAD3B
0x1800bace7  mov     eax, [rbp+var_40]
0x1800bacea  lea     rdx, byte_180328193
0x1800bacf1  xor     ecx, ecx
0x1800bacf3  cmp     [rdi+1Ch], eax
0x1800bacf6  movzx   eax, word ptr [rbp+var_10]
0x1800bacfa  mov     word ptr [rbp+var_40], ax
0x1800bacfe  setnz   cl
0x1800bad01  mov     eax, [rsi+14h]
0x1800bad04  mov     [rbp+var_38], eax
0x1800bad07  lea     rax, [rbp+var_20]
0x1800bad0b  mov     [rbp+var_28], rax
0x1800bad0f  lea     rax, [rbp+var_3C]
0x1800bad13  mov     [rsp+80h+var_48], rax
0x1800bad18  lea     rax, [rbp+var_40]
0x1800bad1c  mov     [rsp+80h+var_50], rax
0x1800bad21  lea     rax, [rbp+var_38]
0x1800bad25  mov     [rsp+80h+var_58], rax
0x1800bad2a  lea     rax, [rbp+var_28]
0x1800bad2e  mov     [rsp+80h+var_60], rax
0x1800bad33  mov     [rbp+var_3C], ecx
0x1800bad36  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800bad3b  mov     rcx, [rsi]
0x1800bad3e  test    rcx, rcx
0x1800bad41  jz      loc_1800BAF06
0x1800bad47  mov     rax, [rcx]
0x1800bad4a  test    rax, rax
0x1800bad4d  jz      loc_1800BAF06
0x1800bad53  mov     rax, [rax+18h]
0x1800bad57  lea     r8, [rdi+20h]
0x1800bad5b  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800bad62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bad67  mov     ebx, eax
0x1800bad69  test    eax, eax
0x1800bad6b  jnz     loc_1800BAF0B
0x1800bad71  cmp     [rsi+10h], r14d
0x1800bad75  jz      loc_1800BAE9F
0x1800bad7b  lea     rbx, [rdi+148h]
0x1800bad82  mov     rcx, rbx
0x1800bad85  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800bad8a  mov     rcx, rbx; struct CSpJobMgr **
0x1800bad8d  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800bad92  test    eax, eax
0x1800bad94  jnz     short loc_1800BAD9E
0x1800bad96  lea     ebx, [rax+1Ch]
0x1800bad99  jmp     loc_1800BAF0B
0x1800bad9e  mov     ecx, 10h; Size
0x1800bada3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bada8  xor     r8d, r8d; pcbe
0x1800badab  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800badb2  mov     rdx, rax; pv
0x1800badb5  mov     r15, rax
0x1800badb8  mov     [rax], rdi
0x1800badbb  call    cs:__imp_CreateThreadpoolWork
0x1800badc1  mov     r14, rax
0x1800badc4  test    rax, rax
0x1800badc7  jnz     short loc_1800BADD5
0x1800badc9  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800badce  mov     ebx, eax
0x1800badd0  jmp     loc_1800BAF0B
0x1800badd5  call    cs:__imp_GetCurrentThread
0x1800baddb  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800baddf  xor     r8d, r8d; OpenAsSelf
0x1800bade2  mov     rcx, rax; ThreadHandle
0x1800bade5  mov     edx, 2000Ch; DesiredAccess
0x1800badea  call    cs:__imp_OpenThreadToken
0x1800badf0  test    eax, eax
0x1800badf2  jnz     short loc_1800BAE01
0x1800badf4  call    cs:__imp_GetLastError
0x1800badfa  cmp     eax, 3F0h
0x1800badff  jnz     short loc_1800BADC9
0x1800bae01  mov     rax, [rbp+TokenHandle]
0x1800bae05  mov     r8, r13
0x1800bae08  mov     [r15+8], rax
0x1800bae0c  mov     rcx, rdi
0x1800bae0f  mov     rax, [rdi]
0x1800bae12  mov     rdx, [rsi+8]
0x1800bae16  mov     rax, [rax+18h]
0x1800bae1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bae1f  mov     rax, [rdi]
0x1800bae22  mov     rdx, r12
0x1800bae25  mov     rcx, rdi
0x1800bae28  mov     rax, [rax+28h]
0x1800bae2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bae31  mov     ebx, eax
0x1800bae33  test    eax, eax
0x1800bae35  jz      short loc_1800BAE40
0x1800bae37  cmp     eax, 7
0x1800bae3a  jnz     loc_1800BAF0B
0x1800bae40  mov     rax, [rdi]
0x1800bae43  mov     rdx, r12
0x1800bae46  mov     rcx, rdi
0x1800bae49  mov     rax, [rax+38h]
0x1800bae4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bae52  mov     ebx, eax
0x1800bae54  test    eax, eax
0x1800bae56  jnz     loc_1800BAF0B
0x1800bae5c  mov     rax, [rdi+150h]
0x1800bae63  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bae6a  jnz     short loc_1800BAE80
0x1800bae6c  mov     rax, [rdi+158h]
0x1800bae73  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800bae7a  jz      loc_1800BAF0B
0x1800bae80  mov     rdx, r12
0x1800bae83  mov     rcx, rdi
0x1800bae86  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800bae8b  mov     ebx, eax
0x1800bae8d  test    eax, eax
0x1800bae8f  jnz     short loc_1800BAF0B
0x1800bae91  mov     rcx, r14; pwk
0x1800bae94  call    cs:__imp_SubmitThreadpoolWork
0x1800bae9a  jmp     loc_1800BAF4D
0x1800bae9f  mov     rax, [rdi]
0x1800baea2  mov     r8, r13
0x1800baea5  mov     rdx, [rsi+8]
0x1800baea9  mov     rcx, rdi
0x1800baeac  mov     rax, [rax+10h]
0x1800baeb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baeb5  mov     rax, [rdi]
0x1800baeb8  mov     rdx, r12
0x1800baebb  mov     rcx, rdi
0x1800baebe  mov     rax, [rax+30h]
0x1800baec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baec7  mov     ebx, eax
0x1800baec9  test    eax, eax
0x1800baecb  jz      short loc_1800BAED2
0x1800baecd  cmp     eax, 7
0x1800baed0  jnz     short loc_1800BAF0B
0x1800baed2  mov     rax, [rdi]
0x1800baed5  mov     rdx, r12
0x1800baed8  mov     rcx, rdi
0x1800baedb  mov     rax, [rax+28h]
0x1800baedf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baee4  mov     ebx, eax
0x1800baee6  test    eax, eax
0x1800baee8  jz      short loc_1800BAEEF
0x1800baeea  cmp     eax, 7
0x1800baeed  jnz     short loc_1800BAF0B
0x1800baeef  mov     rax, [rdi]
0x1800baef2  mov     rdx, r12
0x1800baef5  mov     rcx, rdi
0x1800baef8  mov     rax, [rax+38h]
0x1800baefc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baf01  jmp     loc_1800BADCE
0x1800baf06  mov     ebx, 4
0x1800baf0b  mov     rax, [rdi]
0x1800baf0e  mov     edx, 1
0x1800baf13  mov     rcx, rdi
0x1800baf16  mov     rax, [rax]
0x1800baf19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baf1e  test    r15, r15
0x1800baf21  jz      short loc_1800BAF30
0x1800baf23  mov     edx, 10h
0x1800baf28  mov     rcx, r15; Block
0x1800baf2b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800baf30  mov     rcx, [rbp+TokenHandle]; hObject
0x1800baf34  test    rcx, rcx
0x1800baf37  jz      short loc_1800BAF3F
0x1800baf39  call    cs:__imp_CloseHandle
0x1800baf3f  test    r14, r14
0x1800baf42  jz      short loc_1800BAF4D
0x1800baf44  mov     rcx, r14; pwk
0x1800baf47  call    cs:__imp_CloseThreadpoolWork
0x1800baf4d  mov     eax, ebx
0x1800baf4f  mov     rcx, [rbp+var_8]
0x1800baf53  xor     rcx, rsp; StackCookie
0x1800baf56  call    __security_check_cookie
0x1800baf5b  mov     rbx, [rsp+80h+arg_18]
0x1800baf63  add     rsp, 80h
0x1800baf6a  pop     r15
0x1800baf6c  pop     r14
0x1800baf6e  pop     r13
0x1800baf70  pop     r12
0x1800baf72  pop     rdi
0x1800baf73  pop     rsi
0x1800baf74  pop     rbp
0x1800baf75  retn
```
