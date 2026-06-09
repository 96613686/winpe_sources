# CSpWmiMethod<_SPACES_StorageSubsystem_CreateReplicationGroup>::RunMethod<CSpSubsystem::CreateReplicationGroup,13>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x180069cb4`
- end: `0x18006a002`
- name: `??$RunMethod@VCreateReplicationGroup@CSpSubsystem@@$0N@@?$CSpWmiMethod@U_SPACES_StorageSubsystem_CreateReplicationGroup@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x180069cb4`
- `0x18006bcc4`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069e80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069e80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180069e61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180069e61`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180069e76`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180069e76`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180069e47`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180069e47`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180069f20`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180069f20`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180069fd3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180069fd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069fc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069fc5`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageSubsystem_CreateReplicationGroup>::RunMethod<CSpSubsystem::CreateReplicationGroup,13>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 ReplicationGroup; // rax
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
  CSpSubsystem::CreateReplicationGroup *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpSubsystem::CreateReplicationGroup *)operator new(0x180u);
  ReplicationGroup = CSpSubsystem::CreateReplicationGroup::CreateReplicationGroup(v25);
  v8 = ReplicationGroup;
  if ( ReplicationGroup )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)ReplicationGroup + 8LL))(ReplicationGroup, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpSubsystem::CreateReplicationGroup *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&word_18030EA8E,
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
0x180069cb4  mov     [rsp-38h+arg_18], rbx
0x180069cb9  push    rbp
0x180069cba  push    rsi
0x180069cbb  push    rdi
0x180069cbc  push    r12
0x180069cbe  push    r13
0x180069cc0  push    r14
0x180069cc2  push    r15
0x180069cc4  mov     rbp, rsp
0x180069cc7  sub     rsp, 80h
0x180069cce  mov     rax, cs:__security_cookie
0x180069cd5  xor     rax, rsp
0x180069cd8  mov     [rbp+var_8], rax
0x180069cdc  xor     eax, eax
0x180069cde  mov     rsi, rcx
0x180069ce1  xorps   xmm0, xmm0
0x180069ce4  mov     [rbp+var_10], eax
0x180069ce7  mov     ecx, 180h; Size
0x180069cec  mov     [rbp+var_40], eax
0x180069cef  movups  [rbp+var_20], xmm0
0x180069cf3  mov     [rbp+TokenHandle], rax
0x180069cf7  mov     r12, r8
0x180069cfa  mov     r13, rdx
0x180069cfd  xor     r14d, r14d
0x180069d00  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180069d05  mov     rcx, rax; this
0x180069d08  mov     [rbp+var_28], rax
0x180069d0c  call    ??0CreateReplicationGroup@CSpSubsystem@@QEAA@XZ; CSpSubsystem::CreateReplicationGroup::CreateReplicationGroup(void)
0x180069d11  mov     rdi, rax
0x180069d14  test    rax, rax
0x180069d17  jnz     short loc_180069D21
0x180069d19  lea     ebx, [rax+1Bh]
0x180069d1c  jmp     loc_180069FBC
0x180069d21  mov     rax, [rax]
0x180069d24  mov     rdx, rsi
0x180069d27  mov     rcx, rdi
0x180069d2a  xor     r15d, r15d
0x180069d2d  mov     rax, [rax+8]
0x180069d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069d36  lea     rcx, [rbp+var_40]
0x180069d3a  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x180069d3f  mov     [rdi+1Ch], eax
0x180069d42  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x180069d46  mov     ecx, [rsi+14h]; unsigned int
0x180069d49  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x180069d4e  mov     eax, cs:dword_180397B68
0x180069d54  cmp     eax, 5
0x180069d57  jbe     short loc_180069DC7
0x180069d59  mov     rdx, 400000000000h
0x180069d63  lea     rcx, dword_180397B68
0x180069d6a  call    _tlgKeywordOn
0x180069d6f  test    al, al
0x180069d71  jz      short loc_180069DC7
0x180069d73  mov     eax, [rbp+var_40]
0x180069d76  lea     rdx, word_18030EA8E
0x180069d7d  xor     ecx, ecx
0x180069d7f  cmp     [rdi+1Ch], eax
0x180069d82  movzx   eax, word ptr [rbp+var_10]
0x180069d86  mov     word ptr [rbp+var_40], ax
0x180069d8a  setnz   cl
0x180069d8d  mov     eax, [rsi+14h]
0x180069d90  mov     [rbp+var_38], eax
0x180069d93  lea     rax, [rbp+var_20]
0x180069d97  mov     [rbp+var_28], rax
0x180069d9b  lea     rax, [rbp+var_3C]
0x180069d9f  mov     [rsp+80h+var_48], rax
0x180069da4  lea     rax, [rbp+var_40]
0x180069da8  mov     [rsp+80h+var_50], rax
0x180069dad  lea     rax, [rbp+var_38]
0x180069db1  mov     [rsp+80h+var_58], rax
0x180069db6  lea     rax, [rbp+var_28]
0x180069dba  mov     [rsp+80h+var_60], rax
0x180069dbf  mov     [rbp+var_3C], ecx
0x180069dc2  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x180069dc7  mov     rcx, [rsi]
0x180069dca  test    rcx, rcx
0x180069dcd  jz      loc_180069F92
0x180069dd3  mov     rax, [rcx]
0x180069dd6  test    rax, rax
0x180069dd9  jz      loc_180069F92
0x180069ddf  mov     rax, [rax+18h]
0x180069de3  lea     r8, [rdi+20h]
0x180069de7  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x180069dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069df3  mov     ebx, eax
0x180069df5  test    eax, eax
0x180069df7  jnz     loc_180069F97
0x180069dfd  cmp     [rsi+10h], r14d
0x180069e01  jz      loc_180069F2B
0x180069e07  lea     rbx, [rdi+148h]
0x180069e0e  mov     rcx, rbx
0x180069e11  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180069e16  mov     rcx, rbx; struct CSpJobMgr **
0x180069e19  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x180069e1e  test    eax, eax
0x180069e20  jnz     short loc_180069E2A
0x180069e22  lea     ebx, [rax+1Ch]
0x180069e25  jmp     loc_180069F97
0x180069e2a  mov     ecx, 10h; Size
0x180069e2f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180069e34  xor     r8d, r8d; pcbe
0x180069e37  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180069e3e  mov     rdx, rax; pv
0x180069e41  mov     r15, rax
0x180069e44  mov     [rax], rdi
0x180069e47  call    cs:__imp_CreateThreadpoolWork
0x180069e4d  mov     r14, rax
0x180069e50  test    rax, rax
0x180069e53  jnz     short loc_180069E61
0x180069e55  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x180069e5a  mov     ebx, eax
0x180069e5c  jmp     loc_180069F97
0x180069e61  call    cs:__imp_GetCurrentThread
0x180069e67  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180069e6b  xor     r8d, r8d; OpenAsSelf
0x180069e6e  mov     rcx, rax; ThreadHandle
0x180069e71  mov     edx, 2000Ch; DesiredAccess
0x180069e76  call    cs:__imp_OpenThreadToken
0x180069e7c  test    eax, eax
0x180069e7e  jnz     short loc_180069E8D
0x180069e80  call    cs:__imp_GetLastError
0x180069e86  cmp     eax, 3F0h
0x180069e8b  jnz     short loc_180069E55
0x180069e8d  mov     rax, [rbp+TokenHandle]
0x180069e91  mov     r8, r13
0x180069e94  mov     [r15+8], rax
0x180069e98  mov     rcx, rdi
0x180069e9b  mov     rax, [rdi]
0x180069e9e  mov     rdx, [rsi+8]
0x180069ea2  mov     rax, [rax+18h]
0x180069ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069eab  mov     rax, [rdi]
0x180069eae  mov     rdx, r12
0x180069eb1  mov     rcx, rdi
0x180069eb4  mov     rax, [rax+28h]
0x180069eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069ebd  mov     ebx, eax
0x180069ebf  test    eax, eax
0x180069ec1  jz      short loc_180069ECC
0x180069ec3  cmp     eax, 7
0x180069ec6  jnz     loc_180069F97
0x180069ecc  mov     rax, [rdi]
0x180069ecf  mov     rdx, r12
0x180069ed2  mov     rcx, rdi
0x180069ed5  mov     rax, [rax+38h]
0x180069ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069ede  mov     ebx, eax
0x180069ee0  test    eax, eax
0x180069ee2  jnz     loc_180069F97
0x180069ee8  mov     rax, [rdi+150h]
0x180069eef  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180069ef6  jnz     short loc_180069F0C
0x180069ef8  mov     rax, [rdi+158h]
0x180069eff  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180069f06  jz      loc_180069F97
0x180069f0c  mov     rdx, r12
0x180069f0f  mov     rcx, rdi
0x180069f12  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x180069f17  mov     ebx, eax
0x180069f19  test    eax, eax
0x180069f1b  jnz     short loc_180069F97
0x180069f1d  mov     rcx, r14; pwk
0x180069f20  call    cs:__imp_SubmitThreadpoolWork
0x180069f26  jmp     loc_180069FD9
0x180069f2b  mov     rax, [rdi]
0x180069f2e  mov     r8, r13
0x180069f31  mov     rdx, [rsi+8]
0x180069f35  mov     rcx, rdi
0x180069f38  mov     rax, [rax+10h]
0x180069f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069f41  mov     rax, [rdi]
0x180069f44  mov     rdx, r12
0x180069f47  mov     rcx, rdi
0x180069f4a  mov     rax, [rax+30h]
0x180069f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069f53  mov     ebx, eax
0x180069f55  test    eax, eax
0x180069f57  jz      short loc_180069F5E
0x180069f59  cmp     eax, 7
0x180069f5c  jnz     short loc_180069F97
0x180069f5e  mov     rax, [rdi]
0x180069f61  mov     rdx, r12
0x180069f64  mov     rcx, rdi
0x180069f67  mov     rax, [rax+28h]
0x180069f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069f70  mov     ebx, eax
0x180069f72  test    eax, eax
0x180069f74  jz      short loc_180069F7B
0x180069f76  cmp     eax, 7
0x180069f79  jnz     short loc_180069F97
0x180069f7b  mov     rax, [rdi]
0x180069f7e  mov     rdx, r12
0x180069f81  mov     rcx, rdi
0x180069f84  mov     rax, [rax+38h]
0x180069f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069f8d  jmp     loc_180069E5A
0x180069f92  mov     ebx, 4
0x180069f97  mov     rax, [rdi]
0x180069f9a  mov     edx, 1
0x180069f9f  mov     rcx, rdi
0x180069fa2  mov     rax, [rax]
0x180069fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069faa  test    r15, r15
0x180069fad  jz      short loc_180069FBC
0x180069faf  mov     edx, 10h
0x180069fb4  mov     rcx, r15; Block
0x180069fb7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180069fbc  mov     rcx, [rbp+TokenHandle]; hObject
0x180069fc0  test    rcx, rcx
0x180069fc3  jz      short loc_180069FCB
0x180069fc5  call    cs:__imp_CloseHandle
0x180069fcb  test    r14, r14
0x180069fce  jz      short loc_180069FD9
0x180069fd0  mov     rcx, r14; pwk
0x180069fd3  call    cs:__imp_CloseThreadpoolWork
0x180069fd9  mov     eax, ebx
0x180069fdb  mov     rcx, [rbp+var_8]
0x180069fdf  xor     rcx, rsp; StackCookie
0x180069fe2  call    __security_check_cookie
0x180069fe7  mov     rbx, [rsp+80h+arg_18]
0x180069fef  add     rsp, 80h
0x180069ff6  pop     r15
0x180069ff8  pop     r14
0x180069ffa  pop     r13
0x180069ffc  pop     r12
0x180069ffe  pop     rdi
0x180069fff  pop     rsi
0x18006a000  pop     rbp
0x18006a001  retn
```
