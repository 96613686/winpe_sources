# CSpWmiMethod<_SPACES_StorageJob_GetMessages>::RunMethod<CSpStorageJob::GetMessages,9>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18005fe4c`
- end: `0x180060104`
- name: `??$RunMethod@VGetMessages@CSpStorageJob@@$08@?$CSpWmiMethod@U_SPACES_StorageJob_GetMessages@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x18005fe4c`
- `0x180060740`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ff8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ff8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005ff6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005ff6b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005ff81`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005ff81`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18005ff51`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18005ff51`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006002c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006002c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800600e0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800600e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800600d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800600d2`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageJob_GetMessages>::RunMethod<CSpStorageJob::GetMessages,9>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // rsi
  __int64 Messages; // rax
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
  CSpStorageJob::GetMessages *v19; // [rsp+28h] [rbp-60h] BYREF
  __int128 v20; // [rsp+30h] [rbp-58h]
  int v21; // [rsp+40h] [rbp-48h]

  v21 = 0;
  TokenHandle = 0;
  v20 = 0;
  ThreadpoolWork = 0;
  v19 = (CSpStorageJob::GetMessages *)operator new(0x178u);
  Messages = CSpStorageJob::GetMessages::GetMessages(v19);
  v8 = Messages;
  if ( Messages )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)Messages + 8LL))(Messages, a1);
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
0x18005fe4c  push    rbx
0x18005fe4e  push    rbp
0x18005fe4f  push    rsi
0x18005fe50  push    rdi
0x18005fe51  push    r12
0x18005fe53  push    r14
0x18005fe55  push    r15
0x18005fe57  sub     rsp, 50h
0x18005fe5b  mov     rax, cs:__security_cookie
0x18005fe62  xor     rax, rsp
0x18005fe65  mov     [rsp+88h+var_40], rax
0x18005fe6a  xor     eax, eax
0x18005fe6c  mov     r15, rcx
0x18005fe6f  xorps   xmm0, xmm0
0x18005fe72  mov     [rsp+88h+var_48], eax
0x18005fe76  mov     ecx, 178h; Size
0x18005fe7b  mov     [rsp+88h+TokenHandle], rax
0x18005fe80  movups  [rsp+88h+var_58], xmm0
0x18005fe85  mov     rbp, r8
0x18005fe88  mov     r12, rdx
0x18005fe8b  xor     esi, esi
0x18005fe8d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005fe92  mov     rcx, rax; this
0x18005fe95  mov     [rsp+88h+var_60], rax
0x18005fe9a  call    ??0GetMessages@CSpStorageJob@@QEAA@XZ; CSpStorageJob::GetMessages::GetMessages(void)
0x18005fe9f  mov     rdi, rax
0x18005fea2  test    rax, rax
0x18005fea5  jnz     short loc_18005FEAF
0x18005fea7  lea     ebx, [rsi+1Bh]
0x18005feaa  jmp     loc_1800600C8
0x18005feaf  mov     rax, [rax]
0x18005feb2  mov     rdx, r15
0x18005feb5  mov     rcx, rdi
0x18005feb8  xor     r14d, r14d
0x18005febb  mov     rax, [rax+8]
0x18005febf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fec4  lea     rcx, [rsp+88h+var_60]
0x18005fec9  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18005fece  mov     [rdi+1Ch], eax
0x18005fed1  mov     rcx, [r15]
0x18005fed4  test    rcx, rcx
0x18005fed7  jz      loc_18006009E
0x18005fedd  mov     rax, [rcx]
0x18005fee0  test    rax, rax
0x18005fee3  jz      loc_18006009E
0x18005fee9  mov     rax, [rax+18h]
0x18005feed  lea     r8, [rdi+20h]
0x18005fef1  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18005fef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fefd  mov     ebx, eax
0x18005feff  test    eax, eax
0x18005ff01  jnz     loc_1800600A3
0x18005ff07  cmp     [r15+10h], esi
0x18005ff0b  jz      loc_180060037
0x18005ff11  lea     rbx, [rdi+148h]
0x18005ff18  mov     rcx, rbx
0x18005ff1b  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18005ff20  mov     rcx, rbx; struct CSpJobMgr **
0x18005ff23  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18005ff28  test    eax, eax
0x18005ff2a  jnz     short loc_18005FF34
0x18005ff2c  lea     ebx, [rax+1Ch]
0x18005ff2f  jmp     loc_1800600A3
0x18005ff34  mov     ecx, 10h; Size
0x18005ff39  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005ff3e  xor     r8d, r8d; pcbe
0x18005ff41  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18005ff48  mov     rdx, rax; pv
0x18005ff4b  mov     r14, rax
0x18005ff4e  mov     [rax], rdi
0x18005ff51  call    cs:__imp_CreateThreadpoolWork
0x18005ff57  mov     rsi, rax
0x18005ff5a  test    rax, rax
0x18005ff5d  jnz     short loc_18005FF6B
0x18005ff5f  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18005ff64  mov     ebx, eax
0x18005ff66  jmp     loc_1800600A3
0x18005ff6b  call    cs:__imp_GetCurrentThread
0x18005ff71  lea     r9, [rsp+88h+TokenHandle]; TokenHandle
0x18005ff76  xor     r8d, r8d; OpenAsSelf
0x18005ff79  mov     rcx, rax; ThreadHandle
0x18005ff7c  mov     edx, 2000Ch; DesiredAccess
0x18005ff81  call    cs:__imp_OpenThreadToken
0x18005ff87  test    eax, eax
0x18005ff89  jnz     short loc_18005FF98
0x18005ff8b  call    cs:__imp_GetLastError
0x18005ff91  cmp     eax, 3F0h
0x18005ff96  jnz     short loc_18005FF5F
0x18005ff98  mov     rax, [rsp+88h+TokenHandle]
0x18005ff9d  mov     r8, r12
0x18005ffa0  mov     [r14+8], rax
0x18005ffa4  mov     rcx, rdi
0x18005ffa7  mov     rax, [rdi]
0x18005ffaa  mov     rdx, [r15+8]
0x18005ffae  mov     rax, [rax+18h]
0x18005ffb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ffb7  mov     rax, [rdi]
0x18005ffba  mov     rdx, rbp
0x18005ffbd  mov     rcx, rdi
0x18005ffc0  mov     rax, [rax+28h]
0x18005ffc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ffc9  mov     ebx, eax
0x18005ffcb  test    eax, eax
0x18005ffcd  jz      short loc_18005FFD8
0x18005ffcf  cmp     eax, 7
0x18005ffd2  jnz     loc_1800600A3
0x18005ffd8  mov     rax, [rdi]
0x18005ffdb  mov     rdx, rbp
0x18005ffde  mov     rcx, rdi
0x18005ffe1  mov     rax, [rax+38h]
0x18005ffe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ffea  mov     ebx, eax
0x18005ffec  test    eax, eax
0x18005ffee  jnz     loc_1800600A3
0x18005fff4  mov     rax, [rdi+150h]
0x18005fffb  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180060002  jnz     short loc_180060018
0x180060004  mov     rax, [rdi+158h]
0x18006000b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180060012  jz      loc_1800600A3
0x180060018  mov     rdx, rbp
0x18006001b  mov     rcx, rdi
0x18006001e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x180060023  mov     ebx, eax
0x180060025  test    eax, eax
0x180060027  jnz     short loc_1800600A3
0x180060029  mov     rcx, rsi; pwk
0x18006002c  call    cs:__imp_SubmitThreadpoolWork
0x180060032  jmp     loc_1800600E6
0x180060037  mov     rax, [rdi]
0x18006003a  mov     r8, r12
0x18006003d  mov     rdx, [r15+8]
0x180060041  mov     rcx, rdi
0x180060044  mov     rax, [rax+10h]
0x180060048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006004d  mov     rax, [rdi]
0x180060050  mov     rdx, rbp
0x180060053  mov     rcx, rdi
0x180060056  mov     rax, [rax+30h]
0x18006005a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006005f  mov     ebx, eax
0x180060061  test    eax, eax
0x180060063  jz      short loc_18006006A
0x180060065  cmp     eax, 7
0x180060068  jnz     short loc_1800600A3
0x18006006a  mov     rax, [rdi]
0x18006006d  mov     rdx, rbp
0x180060070  mov     rcx, rdi
0x180060073  mov     rax, [rax+28h]
0x180060077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006007c  mov     ebx, eax
0x18006007e  test    eax, eax
0x180060080  jz      short loc_180060087
0x180060082  cmp     eax, 7
0x180060085  jnz     short loc_1800600A3
0x180060087  mov     rax, [rdi]
0x18006008a  mov     rdx, rbp
0x18006008d  mov     rcx, rdi
0x180060090  mov     rax, [rax+38h]
0x180060094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060099  jmp     loc_18005FF64
0x18006009e  mov     ebx, 4
0x1800600a3  mov     rax, [rdi]
0x1800600a6  mov     edx, 1
0x1800600ab  mov     rcx, rdi
0x1800600ae  mov     rax, [rax]
0x1800600b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800600b6  test    r14, r14
0x1800600b9  jz      short loc_1800600C8
0x1800600bb  mov     edx, 10h
0x1800600c0  mov     rcx, r14; Block
0x1800600c3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800600c8  mov     rcx, [rsp+88h+TokenHandle]; hObject
0x1800600cd  test    rcx, rcx
0x1800600d0  jz      short loc_1800600D8
0x1800600d2  call    cs:__imp_CloseHandle
0x1800600d8  test    rsi, rsi
0x1800600db  jz      short loc_1800600E6
0x1800600dd  mov     rcx, rsi; pwk
0x1800600e0  call    cs:__imp_CloseThreadpoolWork
0x1800600e6  mov     eax, ebx
0x1800600e8  mov     rcx, [rsp+88h+var_40]
0x1800600ed  xor     rcx, rsp; StackCookie
0x1800600f0  call    __security_check_cookie
0x1800600f5  add     rsp, 50h
0x1800600f9  pop     r15
0x1800600fb  pop     r14
0x1800600fd  pop     r12
0x1800600ff  pop     rdi
0x180060100  pop     rsi
0x180060101  pop     rbp
0x180060102  pop     rbx
0x180060103  retn
```
