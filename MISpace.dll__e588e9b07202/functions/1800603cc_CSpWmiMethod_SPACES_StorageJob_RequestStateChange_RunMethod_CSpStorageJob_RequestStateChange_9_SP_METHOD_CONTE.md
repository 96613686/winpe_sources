# CSpWmiMethod<_SPACES_StorageJob_RequestStateChange>::RunMethod<CSpStorageJob::RequestStateChange,9>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800603cc`
- end: `0x180060684`
- name: `??$RunMethod@VRequestStateChange@CSpStorageJob@@$08@?$CSpWmiMethod@U_SPACES_StorageJob_RequestStateChange@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `696`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180062110`

## callees

- `0x180006290`
- `0x1800062e0`
- `0x1800062ec`
- `0x18000c704`
- `0x180013898`
- `0x180014720`
- `0x180024dfc`
- `0x18005d58c`
- `0x1800603cc`
- `0x180060874`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006050b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006050b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800604eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800604eb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180060501`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180060501`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800604d1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800604d1`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800605ac`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800605ac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180060660`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180060660`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060652`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060652`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageJob_RequestStateChange>::RunMethod<CSpStorageJob::RequestStateChange,9>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // rsi
  __int64 v7; // rax
  __int64 v8; // rdi
  unsigned int v9; // ebx
  __int64 *v10; // r14
  __int64 v11; // rcx
  enum _MI_Result v12; // eax
  HANDLE CurrentThread; // rax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  void *TokenHandle; // [rsp+20h] [rbp-68h] BYREF
  CSpStorageJob::RequestStateChange *v19; // [rsp+28h] [rbp-60h] BYREF
  __int128 v20; // [rsp+30h] [rbp-58h]
  int v21; // [rsp+40h] [rbp-48h]

  v21 = 0;
  TokenHandle = 0;
  v20 = 0;
  ThreadpoolWork = 0;
  v19 = (CSpStorageJob::RequestStateChange *)operator new(0x160u);
  v7 = CSpStorageJob::RequestStateChange::RequestStateChange(v19);
  v8 = v7;
  if ( v7 )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 8LL))(v7, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v19);
    v11 = *a1;
    if ( *a1 && *(_QWORD *)v11 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v11 + 24LL))(
             v11,
             &MSFT_StorageExtendedStatus_rtti,
             v8 + 32);
      if ( v9 )
        goto LABEL_27;
      if ( *((_DWORD *)a1 + 4) )
      {
        CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(v8 + 328);
        if ( !(unsigned int)CSpJobMgr::GetInstance((struct CSpJobMgr **)(v8 + 328)) )
        {
          v9 = 28;
          goto LABEL_27;
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
            v14 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
            v9 = v14;
            if ( !v14 || v14 == 7 )
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
            goto LABEL_27;
          }
        }
        v12 = GleToMiResult();
        goto LABEL_11;
      }
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v8 + 16LL))(v8, a1[1], a2);
      v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 48LL))(v8, a3);
      v9 = v15;
      if ( !v15 || v15 == 7 )
      {
        v16 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
        v9 = v16;
        if ( !v16 || v16 == 7 )
        {
          v12 = (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 56LL))(v8, a3);
LABEL_11:
          v9 = v12;
        }
      }
    }
    else
    {
      v9 = 4;
    }
LABEL_27:
    (**(void (__fastcall ***)(__int64, __int64))v8)(v8, 1);
    if ( v10 )
      operator delete(v10);
    goto LABEL_29;
  }
  v9 = 27;
LABEL_29:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( ThreadpoolWork )
    CloseThreadpoolWork(ThreadpoolWork);
  return v9;
}

```

## disassembly

```asm
0x1800603cc  push    rbx
0x1800603ce  push    rbp
0x1800603cf  push    rsi
0x1800603d0  push    rdi
0x1800603d1  push    r12
0x1800603d3  push    r14
0x1800603d5  push    r15
0x1800603d7  sub     rsp, 50h
0x1800603db  mov     rax, cs:__security_cookie
0x1800603e2  xor     rax, rsp
0x1800603e5  mov     [rsp+88h+var_40], rax
0x1800603ea  xor     eax, eax
0x1800603ec  mov     r15, rcx
0x1800603ef  xorps   xmm0, xmm0
0x1800603f2  mov     [rsp+88h+var_48], eax
0x1800603f6  mov     ecx, 160h; Size
0x1800603fb  mov     [rsp+88h+TokenHandle], rax
0x180060400  movups  [rsp+88h+var_58], xmm0
0x180060405  mov     rbp, r8
0x180060408  mov     r12, rdx
0x18006040b  xor     esi, esi
0x18006040d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180060412  mov     rcx, rax; this
0x180060415  mov     [rsp+88h+var_60], rax
0x18006041a  call    ??0RequestStateChange@CSpStorageJob@@QEAA@XZ; CSpStorageJob::RequestStateChange::RequestStateChange(void)
0x18006041f  mov     rdi, rax
0x180060422  test    rax, rax
0x180060425  jnz     short loc_18006042F
0x180060427  lea     ebx, [rsi+1Bh]
0x18006042a  jmp     loc_180060648
0x18006042f  mov     rax, [rax]
0x180060432  mov     rdx, r15
0x180060435  mov     rcx, rdi
0x180060438  xor     r14d, r14d
0x18006043b  mov     rax, [rax+8]
0x18006043f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060444  lea     rcx, [rsp+88h+var_60]
0x180060449  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18006044e  mov     [rdi+1Ch], eax
0x180060451  mov     rcx, [r15]
0x180060454  test    rcx, rcx
0x180060457  jz      loc_18006061E
0x18006045d  mov     rax, [rcx]
0x180060460  test    rax, rax
0x180060463  jz      loc_18006061E
0x180060469  mov     rax, [rax+18h]
0x18006046d  lea     r8, [rdi+20h]
0x180060471  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x180060478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006047d  mov     ebx, eax
0x18006047f  test    eax, eax
0x180060481  jnz     loc_180060623
0x180060487  cmp     [r15+10h], esi
0x18006048b  jz      loc_1800605B7
0x180060491  lea     rbx, [rdi+148h]
0x180060498  mov     rcx, rbx
0x18006049b  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800604a0  mov     rcx, rbx; struct CSpJobMgr **
0x1800604a3  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800604a8  test    eax, eax
0x1800604aa  jnz     short loc_1800604B4
0x1800604ac  lea     ebx, [rax+1Ch]
0x1800604af  jmp     loc_180060623
0x1800604b4  mov     ecx, 10h; Size
0x1800604b9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800604be  xor     r8d, r8d; pcbe
0x1800604c1  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800604c8  mov     rdx, rax; pv
0x1800604cb  mov     r14, rax
0x1800604ce  mov     [rax], rdi
0x1800604d1  call    cs:__imp_CreateThreadpoolWork
0x1800604d7  mov     rsi, rax
0x1800604da  test    rax, rax
0x1800604dd  jnz     short loc_1800604EB
0x1800604df  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800604e4  mov     ebx, eax
0x1800604e6  jmp     loc_180060623
0x1800604eb  call    cs:__imp_GetCurrentThread
0x1800604f1  lea     r9, [rsp+88h+TokenHandle]; TokenHandle
0x1800604f6  xor     r8d, r8d; OpenAsSelf
0x1800604f9  mov     rcx, rax; ThreadHandle
0x1800604fc  mov     edx, 2000Ch; DesiredAccess
0x180060501  call    cs:__imp_OpenThreadToken
0x180060507  test    eax, eax
0x180060509  jnz     short loc_180060518
0x18006050b  call    cs:__imp_GetLastError
0x180060511  cmp     eax, 3F0h
0x180060516  jnz     short loc_1800604DF
0x180060518  mov     rax, [rsp+88h+TokenHandle]
0x18006051d  mov     r8, r12
0x180060520  mov     [r14+8], rax
0x180060524  mov     rcx, rdi
0x180060527  mov     rax, [rdi]
0x18006052a  mov     rdx, [r15+8]
0x18006052e  mov     rax, [rax+18h]
0x180060532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060537  mov     rax, [rdi]
0x18006053a  mov     rdx, rbp
0x18006053d  mov     rcx, rdi
0x180060540  mov     rax, [rax+28h]
0x180060544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060549  mov     ebx, eax
0x18006054b  test    eax, eax
0x18006054d  jz      short loc_180060558
0x18006054f  cmp     eax, 7
0x180060552  jnz     loc_180060623
0x180060558  mov     rax, [rdi]
0x18006055b  mov     rdx, rbp
0x18006055e  mov     rcx, rdi
0x180060561  mov     rax, [rax+38h]
0x180060565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006056a  mov     ebx, eax
0x18006056c  test    eax, eax
0x18006056e  jnz     loc_180060623
0x180060574  mov     rax, [rdi+150h]
0x18006057b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180060582  jnz     short loc_180060598
0x180060584  mov     rax, [rdi+158h]
0x18006058b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180060592  jz      loc_180060623
0x180060598  mov     rdx, rbp
0x18006059b  mov     rcx, rdi
0x18006059e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800605a3  mov     ebx, eax
0x1800605a5  test    eax, eax
0x1800605a7  jnz     short loc_180060623
0x1800605a9  mov     rcx, rsi; pwk
0x1800605ac  call    cs:__imp_SubmitThreadpoolWork
0x1800605b2  jmp     loc_180060666
0x1800605b7  mov     rax, [rdi]
0x1800605ba  mov     r8, r12
0x1800605bd  mov     rdx, [r15+8]
0x1800605c1  mov     rcx, rdi
0x1800605c4  mov     rax, [rax+10h]
0x1800605c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800605cd  mov     rax, [rdi]
0x1800605d0  mov     rdx, rbp
0x1800605d3  mov     rcx, rdi
0x1800605d6  mov     rax, [rax+30h]
0x1800605da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800605df  mov     ebx, eax
0x1800605e1  test    eax, eax
0x1800605e3  jz      short loc_1800605EA
0x1800605e5  cmp     eax, 7
0x1800605e8  jnz     short loc_180060623
0x1800605ea  mov     rax, [rdi]
0x1800605ed  mov     rdx, rbp
0x1800605f0  mov     rcx, rdi
0x1800605f3  mov     rax, [rax+28h]
0x1800605f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800605fc  mov     ebx, eax
0x1800605fe  test    eax, eax
0x180060600  jz      short loc_180060607
0x180060602  cmp     eax, 7
0x180060605  jnz     short loc_180060623
0x180060607  mov     rax, [rdi]
0x18006060a  mov     rdx, rbp
0x18006060d  mov     rcx, rdi
0x180060610  mov     rax, [rax+38h]
0x180060614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060619  jmp     loc_1800604E4
0x18006061e  mov     ebx, 4
0x180060623  mov     rax, [rdi]
0x180060626  mov     edx, 1
0x18006062b  mov     rcx, rdi
0x18006062e  mov     rax, [rax]
0x180060631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060636  test    r14, r14
0x180060639  jz      short loc_180060648
0x18006063b  mov     edx, 10h
0x180060640  mov     rcx, r14; Block
0x180060643  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180060648  mov     rcx, [rsp+88h+TokenHandle]; hObject
0x18006064d  test    rcx, rcx
0x180060650  jz      short loc_180060658
0x180060652  call    cs:__imp_CloseHandle
0x180060658  test    rsi, rsi
0x18006065b  jz      short loc_180060666
0x18006065d  mov     rcx, rsi; pwk
0x180060660  call    cs:__imp_CloseThreadpoolWork
0x180060666  mov     eax, ebx
0x180060668  mov     rcx, [rsp+88h+var_40]
0x18006066d  xor     rcx, rsp; StackCookie
0x180060670  call    __security_check_cookie
0x180060675  add     rsp, 50h
0x180060679  pop     r15
0x18006067b  pop     r14
0x18006067d  pop     r12
0x18006067f  pop     rdi
0x180060680  pop     rsi
0x180060681  pop     rbp
0x180060682  pop     rbx
0x180060683  retn
```
