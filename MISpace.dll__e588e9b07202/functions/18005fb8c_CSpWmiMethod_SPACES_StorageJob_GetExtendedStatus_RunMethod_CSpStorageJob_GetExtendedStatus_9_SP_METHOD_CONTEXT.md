# CSpWmiMethod<_SPACES_StorageJob_GetExtendedStatus>::RunMethod<CSpStorageJob::GetExtendedStatus,9>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18005fb8c`
- end: `0x18005fe44`
- name: `??$RunMethod@VGetExtendedStatus@CSpStorageJob@@$08@?$CSpWmiMethod@U_SPACES_StorageJob_GetExtendedStatus@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x18005fb8c`
- `0x1800606d4`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fccb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fccb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005fcab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005fcab`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005fcc1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005fcc1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18005fc91`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18005fc91`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18005fd6c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18005fd6c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005fe20`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005fe20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005fe12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005fe12`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageJob_GetExtendedStatus>::RunMethod<CSpStorageJob::GetExtendedStatus,9>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // rsi
  __int64 ExtendedStatus; // rax
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
  CSpStorageJob::GetExtendedStatus *v19; // [rsp+28h] [rbp-60h] BYREF
  __int128 v20; // [rsp+30h] [rbp-58h]
  int v21; // [rsp+40h] [rbp-48h]

  v21 = 0;
  TokenHandle = 0;
  v20 = 0;
  ThreadpoolWork = 0;
  v19 = (CSpStorageJob::GetExtendedStatus *)operator new(0x160u);
  ExtendedStatus = CSpStorageJob::GetExtendedStatus::GetExtendedStatus(v19);
  v8 = ExtendedStatus;
  if ( ExtendedStatus )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)ExtendedStatus + 8LL))(ExtendedStatus, a1);
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
0x18005fb8c  push    rbx
0x18005fb8e  push    rbp
0x18005fb8f  push    rsi
0x18005fb90  push    rdi
0x18005fb91  push    r12
0x18005fb93  push    r14
0x18005fb95  push    r15
0x18005fb97  sub     rsp, 50h
0x18005fb9b  mov     rax, cs:__security_cookie
0x18005fba2  xor     rax, rsp
0x18005fba5  mov     [rsp+88h+var_40], rax
0x18005fbaa  xor     eax, eax
0x18005fbac  mov     r15, rcx
0x18005fbaf  xorps   xmm0, xmm0
0x18005fbb2  mov     [rsp+88h+var_48], eax
0x18005fbb6  mov     ecx, 160h; Size
0x18005fbbb  mov     [rsp+88h+TokenHandle], rax
0x18005fbc0  movups  [rsp+88h+var_58], xmm0
0x18005fbc5  mov     rbp, r8
0x18005fbc8  mov     r12, rdx
0x18005fbcb  xor     esi, esi
0x18005fbcd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005fbd2  mov     rcx, rax; this
0x18005fbd5  mov     [rsp+88h+var_60], rax
0x18005fbda  call    ??0GetExtendedStatus@CSpStorageJob@@QEAA@XZ; CSpStorageJob::GetExtendedStatus::GetExtendedStatus(void)
0x18005fbdf  mov     rdi, rax
0x18005fbe2  test    rax, rax
0x18005fbe5  jnz     short loc_18005FBEF
0x18005fbe7  lea     ebx, [rsi+1Bh]
0x18005fbea  jmp     loc_18005FE08
0x18005fbef  mov     rax, [rax]
0x18005fbf2  mov     rdx, r15
0x18005fbf5  mov     rcx, rdi
0x18005fbf8  xor     r14d, r14d
0x18005fbfb  mov     rax, [rax+8]
0x18005fbff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fc04  lea     rcx, [rsp+88h+var_60]
0x18005fc09  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18005fc0e  mov     [rdi+1Ch], eax
0x18005fc11  mov     rcx, [r15]
0x18005fc14  test    rcx, rcx
0x18005fc17  jz      loc_18005FDDE
0x18005fc1d  mov     rax, [rcx]
0x18005fc20  test    rax, rax
0x18005fc23  jz      loc_18005FDDE
0x18005fc29  mov     rax, [rax+18h]
0x18005fc2d  lea     r8, [rdi+20h]
0x18005fc31  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18005fc38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fc3d  mov     ebx, eax
0x18005fc3f  test    eax, eax
0x18005fc41  jnz     loc_18005FDE3
0x18005fc47  cmp     [r15+10h], esi
0x18005fc4b  jz      loc_18005FD77
0x18005fc51  lea     rbx, [rdi+148h]
0x18005fc58  mov     rcx, rbx
0x18005fc5b  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18005fc60  mov     rcx, rbx; struct CSpJobMgr **
0x18005fc63  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18005fc68  test    eax, eax
0x18005fc6a  jnz     short loc_18005FC74
0x18005fc6c  lea     ebx, [rax+1Ch]
0x18005fc6f  jmp     loc_18005FDE3
0x18005fc74  mov     ecx, 10h; Size
0x18005fc79  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005fc7e  xor     r8d, r8d; pcbe
0x18005fc81  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18005fc88  mov     rdx, rax; pv
0x18005fc8b  mov     r14, rax
0x18005fc8e  mov     [rax], rdi
0x18005fc91  call    cs:__imp_CreateThreadpoolWork
0x18005fc97  mov     rsi, rax
0x18005fc9a  test    rax, rax
0x18005fc9d  jnz     short loc_18005FCAB
0x18005fc9f  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18005fca4  mov     ebx, eax
0x18005fca6  jmp     loc_18005FDE3
0x18005fcab  call    cs:__imp_GetCurrentThread
0x18005fcb1  lea     r9, [rsp+88h+TokenHandle]; TokenHandle
0x18005fcb6  xor     r8d, r8d; OpenAsSelf
0x18005fcb9  mov     rcx, rax; ThreadHandle
0x18005fcbc  mov     edx, 2000Ch; DesiredAccess
0x18005fcc1  call    cs:__imp_OpenThreadToken
0x18005fcc7  test    eax, eax
0x18005fcc9  jnz     short loc_18005FCD8
0x18005fccb  call    cs:__imp_GetLastError
0x18005fcd1  cmp     eax, 3F0h
0x18005fcd6  jnz     short loc_18005FC9F
0x18005fcd8  mov     rax, [rsp+88h+TokenHandle]
0x18005fcdd  mov     r8, r12
0x18005fce0  mov     [r14+8], rax
0x18005fce4  mov     rcx, rdi
0x18005fce7  mov     rax, [rdi]
0x18005fcea  mov     rdx, [r15+8]
0x18005fcee  mov     rax, [rax+18h]
0x18005fcf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fcf7  mov     rax, [rdi]
0x18005fcfa  mov     rdx, rbp
0x18005fcfd  mov     rcx, rdi
0x18005fd00  mov     rax, [rax+28h]
0x18005fd04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd09  mov     ebx, eax
0x18005fd0b  test    eax, eax
0x18005fd0d  jz      short loc_18005FD18
0x18005fd0f  cmp     eax, 7
0x18005fd12  jnz     loc_18005FDE3
0x18005fd18  mov     rax, [rdi]
0x18005fd1b  mov     rdx, rbp
0x18005fd1e  mov     rcx, rdi
0x18005fd21  mov     rax, [rax+38h]
0x18005fd25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd2a  mov     ebx, eax
0x18005fd2c  test    eax, eax
0x18005fd2e  jnz     loc_18005FDE3
0x18005fd34  mov     rax, [rdi+150h]
0x18005fd3b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18005fd42  jnz     short loc_18005FD58
0x18005fd44  mov     rax, [rdi+158h]
0x18005fd4b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18005fd52  jz      loc_18005FDE3
0x18005fd58  mov     rdx, rbp
0x18005fd5b  mov     rcx, rdi
0x18005fd5e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18005fd63  mov     ebx, eax
0x18005fd65  test    eax, eax
0x18005fd67  jnz     short loc_18005FDE3
0x18005fd69  mov     rcx, rsi; pwk
0x18005fd6c  call    cs:__imp_SubmitThreadpoolWork
0x18005fd72  jmp     loc_18005FE26
0x18005fd77  mov     rax, [rdi]
0x18005fd7a  mov     r8, r12
0x18005fd7d  mov     rdx, [r15+8]
0x18005fd81  mov     rcx, rdi
0x18005fd84  mov     rax, [rax+10h]
0x18005fd88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd8d  mov     rax, [rdi]
0x18005fd90  mov     rdx, rbp
0x18005fd93  mov     rcx, rdi
0x18005fd96  mov     rax, [rax+30h]
0x18005fd9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd9f  mov     ebx, eax
0x18005fda1  test    eax, eax
0x18005fda3  jz      short loc_18005FDAA
0x18005fda5  cmp     eax, 7
0x18005fda8  jnz     short loc_18005FDE3
0x18005fdaa  mov     rax, [rdi]
0x18005fdad  mov     rdx, rbp
0x18005fdb0  mov     rcx, rdi
0x18005fdb3  mov     rax, [rax+28h]
0x18005fdb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fdbc  mov     ebx, eax
0x18005fdbe  test    eax, eax
0x18005fdc0  jz      short loc_18005FDC7
0x18005fdc2  cmp     eax, 7
0x18005fdc5  jnz     short loc_18005FDE3
0x18005fdc7  mov     rax, [rdi]
0x18005fdca  mov     rdx, rbp
0x18005fdcd  mov     rcx, rdi
0x18005fdd0  mov     rax, [rax+38h]
0x18005fdd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fdd9  jmp     loc_18005FCA4
0x18005fdde  mov     ebx, 4
0x18005fde3  mov     rax, [rdi]
0x18005fde6  mov     edx, 1
0x18005fdeb  mov     rcx, rdi
0x18005fdee  mov     rax, [rax]
0x18005fdf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fdf6  test    r14, r14
0x18005fdf9  jz      short loc_18005FE08
0x18005fdfb  mov     edx, 10h
0x18005fe00  mov     rcx, r14; Block
0x18005fe03  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005fe08  mov     rcx, [rsp+88h+TokenHandle]; hObject
0x18005fe0d  test    rcx, rcx
0x18005fe10  jz      short loc_18005FE18
0x18005fe12  call    cs:__imp_CloseHandle
0x18005fe18  test    rsi, rsi
0x18005fe1b  jz      short loc_18005FE26
0x18005fe1d  mov     rcx, rsi; pwk
0x18005fe20  call    cs:__imp_CloseThreadpoolWork
0x18005fe26  mov     eax, ebx
0x18005fe28  mov     rcx, [rsp+88h+var_40]
0x18005fe2d  xor     rcx, rsp; StackCookie
0x18005fe30  call    __security_check_cookie
0x18005fe35  add     rsp, 50h
0x18005fe39  pop     r15
0x18005fe3b  pop     r14
0x18005fe3d  pop     r12
0x18005fe3f  pop     rdi
0x18005fe40  pop     rsi
0x18005fe41  pop     rbp
0x18005fe42  pop     rbx
0x18005fe43  retn
```
