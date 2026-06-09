# CSpWmiMethod<_SPACES_StoragePool_GetSecurityDescriptor>::RunMethod<CSpStoragePool::GetSecurityDescriptor,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800bb624`
- end: `0x1800bb972`
- name: `??$RunMethod@VGetSecurityDescriptor@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_SPACES_StoragePool_GetSecurityDescriptor@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

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
- `0x1800bb624`
- `0x1800bdfc8`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb7f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb7f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bb7d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bb7d1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bb7e6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bb7e6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bb7b7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bb7b7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bb890`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bb890`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bb943`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bb943`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bb935`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bb935`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StoragePool_GetSecurityDescriptor>::RunMethod<CSpStoragePool::GetSecurityDescriptor,11>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 SecurityDescriptor; // rax
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
  CSpStoragePool::GetSecurityDescriptor *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStoragePool::GetSecurityDescriptor *)operator new(0x168u);
  SecurityDescriptor = CSpStoragePool::GetSecurityDescriptor::GetSecurityDescriptor(v25);
  v8 = SecurityDescriptor;
  if ( SecurityDescriptor )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)SecurityDescriptor + 8LL))(SecurityDescriptor, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStoragePool::GetSecurityDescriptor *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_18032B5E5,
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
0x1800bb624  mov     [rsp-38h+arg_18], rbx
0x1800bb629  push    rbp
0x1800bb62a  push    rsi
0x1800bb62b  push    rdi
0x1800bb62c  push    r12
0x1800bb62e  push    r13
0x1800bb630  push    r14
0x1800bb632  push    r15
0x1800bb634  mov     rbp, rsp
0x1800bb637  sub     rsp, 80h
0x1800bb63e  mov     rax, cs:__security_cookie
0x1800bb645  xor     rax, rsp
0x1800bb648  mov     [rbp+var_8], rax
0x1800bb64c  xor     eax, eax
0x1800bb64e  mov     rsi, rcx
0x1800bb651  xorps   xmm0, xmm0
0x1800bb654  mov     [rbp+var_10], eax
0x1800bb657  mov     ecx, 168h; Size
0x1800bb65c  mov     [rbp+var_40], eax
0x1800bb65f  movups  [rbp+var_20], xmm0
0x1800bb663  mov     [rbp+TokenHandle], rax
0x1800bb667  mov     r12, r8
0x1800bb66a  mov     r13, rdx
0x1800bb66d  xor     r14d, r14d
0x1800bb670  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bb675  mov     rcx, rax; this
0x1800bb678  mov     [rbp+var_28], rax
0x1800bb67c  call    ??0GetSecurityDescriptor@CSpStoragePool@@QEAA@XZ; CSpStoragePool::GetSecurityDescriptor::GetSecurityDescriptor(void)
0x1800bb681  mov     rdi, rax
0x1800bb684  test    rax, rax
0x1800bb687  jnz     short loc_1800BB691
0x1800bb689  lea     ebx, [rax+1Bh]
0x1800bb68c  jmp     loc_1800BB92C
0x1800bb691  mov     rax, [rax]
0x1800bb694  mov     rdx, rsi
0x1800bb697  mov     rcx, rdi
0x1800bb69a  xor     r15d, r15d
0x1800bb69d  mov     rax, [rax+8]
0x1800bb6a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb6a6  lea     rcx, [rbp+var_40]
0x1800bb6aa  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800bb6af  mov     [rdi+1Ch], eax
0x1800bb6b2  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800bb6b6  mov     ecx, [rsi+14h]; unsigned int
0x1800bb6b9  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800bb6be  mov     eax, cs:dword_180397B68
0x1800bb6c4  cmp     eax, 5
0x1800bb6c7  jbe     short loc_1800BB737
0x1800bb6c9  mov     rdx, 400000000000h
0x1800bb6d3  lea     rcx, dword_180397B68
0x1800bb6da  call    _tlgKeywordOn
0x1800bb6df  test    al, al
0x1800bb6e1  jz      short loc_1800BB737
0x1800bb6e3  mov     eax, [rbp+var_40]
0x1800bb6e6  lea     rdx, byte_18032B5E5
0x1800bb6ed  xor     ecx, ecx
0x1800bb6ef  cmp     [rdi+1Ch], eax
0x1800bb6f2  movzx   eax, word ptr [rbp+var_10]
0x1800bb6f6  mov     word ptr [rbp+var_40], ax
0x1800bb6fa  setnz   cl
0x1800bb6fd  mov     eax, [rsi+14h]
0x1800bb700  mov     [rbp+var_38], eax
0x1800bb703  lea     rax, [rbp+var_20]
0x1800bb707  mov     [rbp+var_28], rax
0x1800bb70b  lea     rax, [rbp+var_3C]
0x1800bb70f  mov     [rsp+80h+var_48], rax
0x1800bb714  lea     rax, [rbp+var_40]
0x1800bb718  mov     [rsp+80h+var_50], rax
0x1800bb71d  lea     rax, [rbp+var_38]
0x1800bb721  mov     [rsp+80h+var_58], rax
0x1800bb726  lea     rax, [rbp+var_28]
0x1800bb72a  mov     [rsp+80h+var_60], rax
0x1800bb72f  mov     [rbp+var_3C], ecx
0x1800bb732  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800bb737  mov     rcx, [rsi]
0x1800bb73a  test    rcx, rcx
0x1800bb73d  jz      loc_1800BB902
0x1800bb743  mov     rax, [rcx]
0x1800bb746  test    rax, rax
0x1800bb749  jz      loc_1800BB902
0x1800bb74f  mov     rax, [rax+18h]
0x1800bb753  lea     r8, [rdi+20h]
0x1800bb757  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800bb75e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb763  mov     ebx, eax
0x1800bb765  test    eax, eax
0x1800bb767  jnz     loc_1800BB907
0x1800bb76d  cmp     [rsi+10h], r14d
0x1800bb771  jz      loc_1800BB89B
0x1800bb777  lea     rbx, [rdi+148h]
0x1800bb77e  mov     rcx, rbx
0x1800bb781  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800bb786  mov     rcx, rbx; struct CSpJobMgr **
0x1800bb789  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800bb78e  test    eax, eax
0x1800bb790  jnz     short loc_1800BB79A
0x1800bb792  lea     ebx, [rax+1Ch]
0x1800bb795  jmp     loc_1800BB907
0x1800bb79a  mov     ecx, 10h; Size
0x1800bb79f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bb7a4  xor     r8d, r8d; pcbe
0x1800bb7a7  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800bb7ae  mov     rdx, rax; pv
0x1800bb7b1  mov     r15, rax
0x1800bb7b4  mov     [rax], rdi
0x1800bb7b7  call    cs:__imp_CreateThreadpoolWork
0x1800bb7bd  mov     r14, rax
0x1800bb7c0  test    rax, rax
0x1800bb7c3  jnz     short loc_1800BB7D1
0x1800bb7c5  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800bb7ca  mov     ebx, eax
0x1800bb7cc  jmp     loc_1800BB907
0x1800bb7d1  call    cs:__imp_GetCurrentThread
0x1800bb7d7  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800bb7db  xor     r8d, r8d; OpenAsSelf
0x1800bb7de  mov     rcx, rax; ThreadHandle
0x1800bb7e1  mov     edx, 2000Ch; DesiredAccess
0x1800bb7e6  call    cs:__imp_OpenThreadToken
0x1800bb7ec  test    eax, eax
0x1800bb7ee  jnz     short loc_1800BB7FD
0x1800bb7f0  call    cs:__imp_GetLastError
0x1800bb7f6  cmp     eax, 3F0h
0x1800bb7fb  jnz     short loc_1800BB7C5
0x1800bb7fd  mov     rax, [rbp+TokenHandle]
0x1800bb801  mov     r8, r13
0x1800bb804  mov     [r15+8], rax
0x1800bb808  mov     rcx, rdi
0x1800bb80b  mov     rax, [rdi]
0x1800bb80e  mov     rdx, [rsi+8]
0x1800bb812  mov     rax, [rax+18h]
0x1800bb816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb81b  mov     rax, [rdi]
0x1800bb81e  mov     rdx, r12
0x1800bb821  mov     rcx, rdi
0x1800bb824  mov     rax, [rax+28h]
0x1800bb828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb82d  mov     ebx, eax
0x1800bb82f  test    eax, eax
0x1800bb831  jz      short loc_1800BB83C
0x1800bb833  cmp     eax, 7
0x1800bb836  jnz     loc_1800BB907
0x1800bb83c  mov     rax, [rdi]
0x1800bb83f  mov     rdx, r12
0x1800bb842  mov     rcx, rdi
0x1800bb845  mov     rax, [rax+38h]
0x1800bb849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb84e  mov     ebx, eax
0x1800bb850  test    eax, eax
0x1800bb852  jnz     loc_1800BB907
0x1800bb858  mov     rax, [rdi+150h]
0x1800bb85f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bb866  jnz     short loc_1800BB87C
0x1800bb868  mov     rax, [rdi+158h]
0x1800bb86f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800bb876  jz      loc_1800BB907
0x1800bb87c  mov     rdx, r12
0x1800bb87f  mov     rcx, rdi
0x1800bb882  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800bb887  mov     ebx, eax
0x1800bb889  test    eax, eax
0x1800bb88b  jnz     short loc_1800BB907
0x1800bb88d  mov     rcx, r14; pwk
0x1800bb890  call    cs:__imp_SubmitThreadpoolWork
0x1800bb896  jmp     loc_1800BB949
0x1800bb89b  mov     rax, [rdi]
0x1800bb89e  mov     r8, r13
0x1800bb8a1  mov     rdx, [rsi+8]
0x1800bb8a5  mov     rcx, rdi
0x1800bb8a8  mov     rax, [rax+10h]
0x1800bb8ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb8b1  mov     rax, [rdi]
0x1800bb8b4  mov     rdx, r12
0x1800bb8b7  mov     rcx, rdi
0x1800bb8ba  mov     rax, [rax+30h]
0x1800bb8be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb8c3  mov     ebx, eax
0x1800bb8c5  test    eax, eax
0x1800bb8c7  jz      short loc_1800BB8CE
0x1800bb8c9  cmp     eax, 7
0x1800bb8cc  jnz     short loc_1800BB907
0x1800bb8ce  mov     rax, [rdi]
0x1800bb8d1  mov     rdx, r12
0x1800bb8d4  mov     rcx, rdi
0x1800bb8d7  mov     rax, [rax+28h]
0x1800bb8db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb8e0  mov     ebx, eax
0x1800bb8e2  test    eax, eax
0x1800bb8e4  jz      short loc_1800BB8EB
0x1800bb8e6  cmp     eax, 7
0x1800bb8e9  jnz     short loc_1800BB907
0x1800bb8eb  mov     rax, [rdi]
0x1800bb8ee  mov     rdx, r12
0x1800bb8f1  mov     rcx, rdi
0x1800bb8f4  mov     rax, [rax+38h]
0x1800bb8f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb8fd  jmp     loc_1800BB7CA
0x1800bb902  mov     ebx, 4
0x1800bb907  mov     rax, [rdi]
0x1800bb90a  mov     edx, 1
0x1800bb90f  mov     rcx, rdi
0x1800bb912  mov     rax, [rax]
0x1800bb915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb91a  test    r15, r15
0x1800bb91d  jz      short loc_1800BB92C
0x1800bb91f  mov     edx, 10h
0x1800bb924  mov     rcx, r15; Block
0x1800bb927  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800bb92c  mov     rcx, [rbp+TokenHandle]; hObject
0x1800bb930  test    rcx, rcx
0x1800bb933  jz      short loc_1800BB93B
0x1800bb935  call    cs:__imp_CloseHandle
0x1800bb93b  test    r14, r14
0x1800bb93e  jz      short loc_1800BB949
0x1800bb940  mov     rcx, r14; pwk
0x1800bb943  call    cs:__imp_CloseThreadpoolWork
0x1800bb949  mov     eax, ebx
0x1800bb94b  mov     rcx, [rbp+var_8]
0x1800bb94f  xor     rcx, rsp; StackCookie
0x1800bb952  call    __security_check_cookie
0x1800bb957  mov     rbx, [rsp+80h+arg_18]
0x1800bb95f  add     rsp, 80h
0x1800bb966  pop     r15
0x1800bb968  pop     r14
0x1800bb96a  pop     r13
0x1800bb96c  pop     r12
0x1800bb96e  pop     rdi
0x1800bb96f  pop     rsi
0x1800bb970  pop     rbp
0x1800bb971  retn
```
