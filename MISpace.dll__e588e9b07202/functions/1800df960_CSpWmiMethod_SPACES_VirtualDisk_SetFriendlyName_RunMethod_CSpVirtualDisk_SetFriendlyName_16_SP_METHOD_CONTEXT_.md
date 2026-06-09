# CSpWmiMethod<_SPACES_VirtualDisk_SetFriendlyName>::RunMethod<CSpVirtualDisk::SetFriendlyName,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800df960`
- end: `0x1800dfcae`
- name: `??$RunMethod@VSetFriendlyName@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_SetFriendlyName@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800df960`
- `0x1800e0bfc`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfb2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfb2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dfb0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dfb0d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dfb22`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dfb22`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800dfaf3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800dfaf3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800dfbcc`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800dfbcc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800dfc7f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800dfc7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dfc71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dfc71`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_SetFriendlyName>::RunMethod<CSpVirtualDisk::SetFriendlyName,16>(
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
  CSpVirtualDisk::SetFriendlyName *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::SetFriendlyName *)operator new(0x160u);
  v7 = CSpVirtualDisk::SetFriendlyName::SetFriendlyName(v25);
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
      v25 = (CSpVirtualDisk::SetFriendlyName *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&dword_180332D94,
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
0x1800df960  mov     [rsp-38h+arg_18], rbx
0x1800df965  push    rbp
0x1800df966  push    rsi
0x1800df967  push    rdi
0x1800df968  push    r12
0x1800df96a  push    r13
0x1800df96c  push    r14
0x1800df96e  push    r15
0x1800df970  mov     rbp, rsp
0x1800df973  sub     rsp, 80h
0x1800df97a  mov     rax, cs:__security_cookie
0x1800df981  xor     rax, rsp
0x1800df984  mov     [rbp+var_8], rax
0x1800df988  xor     eax, eax
0x1800df98a  mov     rsi, rcx
0x1800df98d  xorps   xmm0, xmm0
0x1800df990  mov     [rbp+var_10], eax
0x1800df993  mov     ecx, 160h; Size
0x1800df998  mov     [rbp+var_40], eax
0x1800df99b  movups  [rbp+var_20], xmm0
0x1800df99f  mov     [rbp+TokenHandle], rax
0x1800df9a3  mov     r12, r8
0x1800df9a6  mov     r13, rdx
0x1800df9a9  xor     r14d, r14d
0x1800df9ac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800df9b1  mov     rcx, rax; this
0x1800df9b4  mov     [rbp+var_28], rax
0x1800df9b8  call    ??0SetFriendlyName@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::SetFriendlyName::SetFriendlyName(void)
0x1800df9bd  mov     rdi, rax
0x1800df9c0  test    rax, rax
0x1800df9c3  jnz     short loc_1800DF9CD
0x1800df9c5  lea     ebx, [rax+1Bh]
0x1800df9c8  jmp     loc_1800DFC68
0x1800df9cd  mov     rax, [rax]
0x1800df9d0  mov     rdx, rsi
0x1800df9d3  mov     rcx, rdi
0x1800df9d6  xor     r15d, r15d
0x1800df9d9  mov     rax, [rax+8]
0x1800df9dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df9e2  lea     rcx, [rbp+var_40]
0x1800df9e6  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800df9eb  mov     [rdi+1Ch], eax
0x1800df9ee  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800df9f2  mov     ecx, [rsi+14h]; unsigned int
0x1800df9f5  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800df9fa  mov     eax, cs:dword_180397B68
0x1800dfa00  cmp     eax, 5
0x1800dfa03  jbe     short loc_1800DFA73
0x1800dfa05  mov     rdx, 400000000000h
0x1800dfa0f  lea     rcx, dword_180397B68
0x1800dfa16  call    _tlgKeywordOn
0x1800dfa1b  test    al, al
0x1800dfa1d  jz      short loc_1800DFA73
0x1800dfa1f  mov     eax, [rbp+var_40]
0x1800dfa22  lea     rdx, dword_180332D94
0x1800dfa29  xor     ecx, ecx
0x1800dfa2b  cmp     [rdi+1Ch], eax
0x1800dfa2e  movzx   eax, word ptr [rbp+var_10]
0x1800dfa32  mov     word ptr [rbp+var_40], ax
0x1800dfa36  setnz   cl
0x1800dfa39  mov     eax, [rsi+14h]
0x1800dfa3c  mov     [rbp+var_38], eax
0x1800dfa3f  lea     rax, [rbp+var_20]
0x1800dfa43  mov     [rbp+var_28], rax
0x1800dfa47  lea     rax, [rbp+var_3C]
0x1800dfa4b  mov     [rsp+80h+var_48], rax
0x1800dfa50  lea     rax, [rbp+var_40]
0x1800dfa54  mov     [rsp+80h+var_50], rax
0x1800dfa59  lea     rax, [rbp+var_38]
0x1800dfa5d  mov     [rsp+80h+var_58], rax
0x1800dfa62  lea     rax, [rbp+var_28]
0x1800dfa66  mov     [rsp+80h+var_60], rax
0x1800dfa6b  mov     [rbp+var_3C], ecx
0x1800dfa6e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800dfa73  mov     rcx, [rsi]
0x1800dfa76  test    rcx, rcx
0x1800dfa79  jz      loc_1800DFC3E
0x1800dfa7f  mov     rax, [rcx]
0x1800dfa82  test    rax, rax
0x1800dfa85  jz      loc_1800DFC3E
0x1800dfa8b  mov     rax, [rax+18h]
0x1800dfa8f  lea     r8, [rdi+20h]
0x1800dfa93  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800dfa9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfa9f  mov     ebx, eax
0x1800dfaa1  test    eax, eax
0x1800dfaa3  jnz     loc_1800DFC43
0x1800dfaa9  cmp     [rsi+10h], r14d
0x1800dfaad  jz      loc_1800DFBD7
0x1800dfab3  lea     rbx, [rdi+148h]
0x1800dfaba  mov     rcx, rbx
0x1800dfabd  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800dfac2  mov     rcx, rbx; struct CSpJobMgr **
0x1800dfac5  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800dfaca  test    eax, eax
0x1800dfacc  jnz     short loc_1800DFAD6
0x1800dface  lea     ebx, [rax+1Ch]
0x1800dfad1  jmp     loc_1800DFC43
0x1800dfad6  mov     ecx, 10h; Size
0x1800dfadb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800dfae0  xor     r8d, r8d; pcbe
0x1800dfae3  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800dfaea  mov     rdx, rax; pv
0x1800dfaed  mov     r15, rax
0x1800dfaf0  mov     [rax], rdi
0x1800dfaf3  call    cs:__imp_CreateThreadpoolWork
0x1800dfaf9  mov     r14, rax
0x1800dfafc  test    rax, rax
0x1800dfaff  jnz     short loc_1800DFB0D
0x1800dfb01  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800dfb06  mov     ebx, eax
0x1800dfb08  jmp     loc_1800DFC43
0x1800dfb0d  call    cs:__imp_GetCurrentThread
0x1800dfb13  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800dfb17  xor     r8d, r8d; OpenAsSelf
0x1800dfb1a  mov     rcx, rax; ThreadHandle
0x1800dfb1d  mov     edx, 2000Ch; DesiredAccess
0x1800dfb22  call    cs:__imp_OpenThreadToken
0x1800dfb28  test    eax, eax
0x1800dfb2a  jnz     short loc_1800DFB39
0x1800dfb2c  call    cs:__imp_GetLastError
0x1800dfb32  cmp     eax, 3F0h
0x1800dfb37  jnz     short loc_1800DFB01
0x1800dfb39  mov     rax, [rbp+TokenHandle]
0x1800dfb3d  mov     r8, r13
0x1800dfb40  mov     [r15+8], rax
0x1800dfb44  mov     rcx, rdi
0x1800dfb47  mov     rax, [rdi]
0x1800dfb4a  mov     rdx, [rsi+8]
0x1800dfb4e  mov     rax, [rax+18h]
0x1800dfb52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfb57  mov     rax, [rdi]
0x1800dfb5a  mov     rdx, r12
0x1800dfb5d  mov     rcx, rdi
0x1800dfb60  mov     rax, [rax+28h]
0x1800dfb64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfb69  mov     ebx, eax
0x1800dfb6b  test    eax, eax
0x1800dfb6d  jz      short loc_1800DFB78
0x1800dfb6f  cmp     eax, 7
0x1800dfb72  jnz     loc_1800DFC43
0x1800dfb78  mov     rax, [rdi]
0x1800dfb7b  mov     rdx, r12
0x1800dfb7e  mov     rcx, rdi
0x1800dfb81  mov     rax, [rax+38h]
0x1800dfb85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfb8a  mov     ebx, eax
0x1800dfb8c  test    eax, eax
0x1800dfb8e  jnz     loc_1800DFC43
0x1800dfb94  mov     rax, [rdi+150h]
0x1800dfb9b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800dfba2  jnz     short loc_1800DFBB8
0x1800dfba4  mov     rax, [rdi+158h]
0x1800dfbab  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800dfbb2  jz      loc_1800DFC43
0x1800dfbb8  mov     rdx, r12
0x1800dfbbb  mov     rcx, rdi
0x1800dfbbe  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800dfbc3  mov     ebx, eax
0x1800dfbc5  test    eax, eax
0x1800dfbc7  jnz     short loc_1800DFC43
0x1800dfbc9  mov     rcx, r14; pwk
0x1800dfbcc  call    cs:__imp_SubmitThreadpoolWork
0x1800dfbd2  jmp     loc_1800DFC85
0x1800dfbd7  mov     rax, [rdi]
0x1800dfbda  mov     r8, r13
0x1800dfbdd  mov     rdx, [rsi+8]
0x1800dfbe1  mov     rcx, rdi
0x1800dfbe4  mov     rax, [rax+10h]
0x1800dfbe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfbed  mov     rax, [rdi]
0x1800dfbf0  mov     rdx, r12
0x1800dfbf3  mov     rcx, rdi
0x1800dfbf6  mov     rax, [rax+30h]
0x1800dfbfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfbff  mov     ebx, eax
0x1800dfc01  test    eax, eax
0x1800dfc03  jz      short loc_1800DFC0A
0x1800dfc05  cmp     eax, 7
0x1800dfc08  jnz     short loc_1800DFC43
0x1800dfc0a  mov     rax, [rdi]
0x1800dfc0d  mov     rdx, r12
0x1800dfc10  mov     rcx, rdi
0x1800dfc13  mov     rax, [rax+28h]
0x1800dfc17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfc1c  mov     ebx, eax
0x1800dfc1e  test    eax, eax
0x1800dfc20  jz      short loc_1800DFC27
0x1800dfc22  cmp     eax, 7
0x1800dfc25  jnz     short loc_1800DFC43
0x1800dfc27  mov     rax, [rdi]
0x1800dfc2a  mov     rdx, r12
0x1800dfc2d  mov     rcx, rdi
0x1800dfc30  mov     rax, [rax+38h]
0x1800dfc34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfc39  jmp     loc_1800DFB06
0x1800dfc3e  mov     ebx, 4
0x1800dfc43  mov     rax, [rdi]
0x1800dfc46  mov     edx, 1
0x1800dfc4b  mov     rcx, rdi
0x1800dfc4e  mov     rax, [rax]
0x1800dfc51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfc56  test    r15, r15
0x1800dfc59  jz      short loc_1800DFC68
0x1800dfc5b  mov     edx, 10h
0x1800dfc60  mov     rcx, r15; Block
0x1800dfc63  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800dfc68  mov     rcx, [rbp+TokenHandle]; hObject
0x1800dfc6c  test    rcx, rcx
0x1800dfc6f  jz      short loc_1800DFC77
0x1800dfc71  call    cs:__imp_CloseHandle
0x1800dfc77  test    r14, r14
0x1800dfc7a  jz      short loc_1800DFC85
0x1800dfc7c  mov     rcx, r14; pwk
0x1800dfc7f  call    cs:__imp_CloseThreadpoolWork
0x1800dfc85  mov     eax, ebx
0x1800dfc87  mov     rcx, [rbp+var_8]
0x1800dfc8b  xor     rcx, rsp; StackCookie
0x1800dfc8e  call    __security_check_cookie
0x1800dfc93  mov     rbx, [rsp+80h+arg_18]
0x1800dfc9b  add     rsp, 80h
0x1800dfca2  pop     r15
0x1800dfca4  pop     r14
0x1800dfca6  pop     r13
0x1800dfca8  pop     r12
0x1800dfcaa  pop     rdi
0x1800dfcab  pop     rsi
0x1800dfcac  pop     rbp
0x1800dfcad  retn
```
