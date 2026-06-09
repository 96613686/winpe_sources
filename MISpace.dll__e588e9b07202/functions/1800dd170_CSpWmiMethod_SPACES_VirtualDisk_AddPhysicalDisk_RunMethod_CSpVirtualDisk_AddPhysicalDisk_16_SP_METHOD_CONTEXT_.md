# CSpWmiMethod<_SPACES_VirtualDisk_AddPhysicalDisk>::RunMethod<CSpVirtualDisk::AddPhysicalDisk,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800dd170`
- end: `0x1800dd4be`
- name: `??$RunMethod@VAddPhysicalDisk@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_AddPhysicalDisk@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800dd170`
- `0x1800e06b0`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd33c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd33c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dd31d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dd31d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dd332`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dd332`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800dd303`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800dd303`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800dd3dc`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800dd3dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800dd48f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800dd48f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dd481`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dd481`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_AddPhysicalDisk>::RunMethod<CSpVirtualDisk::AddPhysicalDisk,16>(
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
  CSpVirtualDisk::AddPhysicalDisk *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::AddPhysicalDisk *)operator new(0x160u);
  v7 = CSpVirtualDisk::AddPhysicalDisk::AddPhysicalDisk(v25);
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
      v25 = (CSpVirtualDisk::AddPhysicalDisk *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_180331541,
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
0x1800dd170  mov     [rsp-38h+arg_18], rbx
0x1800dd175  push    rbp
0x1800dd176  push    rsi
0x1800dd177  push    rdi
0x1800dd178  push    r12
0x1800dd17a  push    r13
0x1800dd17c  push    r14
0x1800dd17e  push    r15
0x1800dd180  mov     rbp, rsp
0x1800dd183  sub     rsp, 80h
0x1800dd18a  mov     rax, cs:__security_cookie
0x1800dd191  xor     rax, rsp
0x1800dd194  mov     [rbp+var_8], rax
0x1800dd198  xor     eax, eax
0x1800dd19a  mov     rsi, rcx
0x1800dd19d  xorps   xmm0, xmm0
0x1800dd1a0  mov     [rbp+var_10], eax
0x1800dd1a3  mov     ecx, 160h; Size
0x1800dd1a8  mov     [rbp+var_40], eax
0x1800dd1ab  movups  [rbp+var_20], xmm0
0x1800dd1af  mov     [rbp+TokenHandle], rax
0x1800dd1b3  mov     r12, r8
0x1800dd1b6  mov     r13, rdx
0x1800dd1b9  xor     r14d, r14d
0x1800dd1bc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800dd1c1  mov     rcx, rax; this
0x1800dd1c4  mov     [rbp+var_28], rax
0x1800dd1c8  call    ??0AddPhysicalDisk@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::AddPhysicalDisk::AddPhysicalDisk(void)
0x1800dd1cd  mov     rdi, rax
0x1800dd1d0  test    rax, rax
0x1800dd1d3  jnz     short loc_1800DD1DD
0x1800dd1d5  lea     ebx, [rax+1Bh]
0x1800dd1d8  jmp     loc_1800DD478
0x1800dd1dd  mov     rax, [rax]
0x1800dd1e0  mov     rdx, rsi
0x1800dd1e3  mov     rcx, rdi
0x1800dd1e6  xor     r15d, r15d
0x1800dd1e9  mov     rax, [rax+8]
0x1800dd1ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd1f2  lea     rcx, [rbp+var_40]
0x1800dd1f6  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800dd1fb  mov     [rdi+1Ch], eax
0x1800dd1fe  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800dd202  mov     ecx, [rsi+14h]; unsigned int
0x1800dd205  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800dd20a  mov     eax, cs:dword_180397B68
0x1800dd210  cmp     eax, 5
0x1800dd213  jbe     short loc_1800DD283
0x1800dd215  mov     rdx, 400000000000h
0x1800dd21f  lea     rcx, dword_180397B68
0x1800dd226  call    _tlgKeywordOn
0x1800dd22b  test    al, al
0x1800dd22d  jz      short loc_1800DD283
0x1800dd22f  mov     eax, [rbp+var_40]
0x1800dd232  lea     rdx, byte_180331541
0x1800dd239  xor     ecx, ecx
0x1800dd23b  cmp     [rdi+1Ch], eax
0x1800dd23e  movzx   eax, word ptr [rbp+var_10]
0x1800dd242  mov     word ptr [rbp+var_40], ax
0x1800dd246  setnz   cl
0x1800dd249  mov     eax, [rsi+14h]
0x1800dd24c  mov     [rbp+var_38], eax
0x1800dd24f  lea     rax, [rbp+var_20]
0x1800dd253  mov     [rbp+var_28], rax
0x1800dd257  lea     rax, [rbp+var_3C]
0x1800dd25b  mov     [rsp+80h+var_48], rax
0x1800dd260  lea     rax, [rbp+var_40]
0x1800dd264  mov     [rsp+80h+var_50], rax
0x1800dd269  lea     rax, [rbp+var_38]
0x1800dd26d  mov     [rsp+80h+var_58], rax
0x1800dd272  lea     rax, [rbp+var_28]
0x1800dd276  mov     [rsp+80h+var_60], rax
0x1800dd27b  mov     [rbp+var_3C], ecx
0x1800dd27e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800dd283  mov     rcx, [rsi]
0x1800dd286  test    rcx, rcx
0x1800dd289  jz      loc_1800DD44E
0x1800dd28f  mov     rax, [rcx]
0x1800dd292  test    rax, rax
0x1800dd295  jz      loc_1800DD44E
0x1800dd29b  mov     rax, [rax+18h]
0x1800dd29f  lea     r8, [rdi+20h]
0x1800dd2a3  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800dd2aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd2af  mov     ebx, eax
0x1800dd2b1  test    eax, eax
0x1800dd2b3  jnz     loc_1800DD453
0x1800dd2b9  cmp     [rsi+10h], r14d
0x1800dd2bd  jz      loc_1800DD3E7
0x1800dd2c3  lea     rbx, [rdi+148h]
0x1800dd2ca  mov     rcx, rbx
0x1800dd2cd  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800dd2d2  mov     rcx, rbx; struct CSpJobMgr **
0x1800dd2d5  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800dd2da  test    eax, eax
0x1800dd2dc  jnz     short loc_1800DD2E6
0x1800dd2de  lea     ebx, [rax+1Ch]
0x1800dd2e1  jmp     loc_1800DD453
0x1800dd2e6  mov     ecx, 10h; Size
0x1800dd2eb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800dd2f0  xor     r8d, r8d; pcbe
0x1800dd2f3  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800dd2fa  mov     rdx, rax; pv
0x1800dd2fd  mov     r15, rax
0x1800dd300  mov     [rax], rdi
0x1800dd303  call    cs:__imp_CreateThreadpoolWork
0x1800dd309  mov     r14, rax
0x1800dd30c  test    rax, rax
0x1800dd30f  jnz     short loc_1800DD31D
0x1800dd311  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800dd316  mov     ebx, eax
0x1800dd318  jmp     loc_1800DD453
0x1800dd31d  call    cs:__imp_GetCurrentThread
0x1800dd323  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800dd327  xor     r8d, r8d; OpenAsSelf
0x1800dd32a  mov     rcx, rax; ThreadHandle
0x1800dd32d  mov     edx, 2000Ch; DesiredAccess
0x1800dd332  call    cs:__imp_OpenThreadToken
0x1800dd338  test    eax, eax
0x1800dd33a  jnz     short loc_1800DD349
0x1800dd33c  call    cs:__imp_GetLastError
0x1800dd342  cmp     eax, 3F0h
0x1800dd347  jnz     short loc_1800DD311
0x1800dd349  mov     rax, [rbp+TokenHandle]
0x1800dd34d  mov     r8, r13
0x1800dd350  mov     [r15+8], rax
0x1800dd354  mov     rcx, rdi
0x1800dd357  mov     rax, [rdi]
0x1800dd35a  mov     rdx, [rsi+8]
0x1800dd35e  mov     rax, [rax+18h]
0x1800dd362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd367  mov     rax, [rdi]
0x1800dd36a  mov     rdx, r12
0x1800dd36d  mov     rcx, rdi
0x1800dd370  mov     rax, [rax+28h]
0x1800dd374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd379  mov     ebx, eax
0x1800dd37b  test    eax, eax
0x1800dd37d  jz      short loc_1800DD388
0x1800dd37f  cmp     eax, 7
0x1800dd382  jnz     loc_1800DD453
0x1800dd388  mov     rax, [rdi]
0x1800dd38b  mov     rdx, r12
0x1800dd38e  mov     rcx, rdi
0x1800dd391  mov     rax, [rax+38h]
0x1800dd395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd39a  mov     ebx, eax
0x1800dd39c  test    eax, eax
0x1800dd39e  jnz     loc_1800DD453
0x1800dd3a4  mov     rax, [rdi+150h]
0x1800dd3ab  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800dd3b2  jnz     short loc_1800DD3C8
0x1800dd3b4  mov     rax, [rdi+158h]
0x1800dd3bb  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800dd3c2  jz      loc_1800DD453
0x1800dd3c8  mov     rdx, r12
0x1800dd3cb  mov     rcx, rdi
0x1800dd3ce  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800dd3d3  mov     ebx, eax
0x1800dd3d5  test    eax, eax
0x1800dd3d7  jnz     short loc_1800DD453
0x1800dd3d9  mov     rcx, r14; pwk
0x1800dd3dc  call    cs:__imp_SubmitThreadpoolWork
0x1800dd3e2  jmp     loc_1800DD495
0x1800dd3e7  mov     rax, [rdi]
0x1800dd3ea  mov     r8, r13
0x1800dd3ed  mov     rdx, [rsi+8]
0x1800dd3f1  mov     rcx, rdi
0x1800dd3f4  mov     rax, [rax+10h]
0x1800dd3f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd3fd  mov     rax, [rdi]
0x1800dd400  mov     rdx, r12
0x1800dd403  mov     rcx, rdi
0x1800dd406  mov     rax, [rax+30h]
0x1800dd40a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd40f  mov     ebx, eax
0x1800dd411  test    eax, eax
0x1800dd413  jz      short loc_1800DD41A
0x1800dd415  cmp     eax, 7
0x1800dd418  jnz     short loc_1800DD453
0x1800dd41a  mov     rax, [rdi]
0x1800dd41d  mov     rdx, r12
0x1800dd420  mov     rcx, rdi
0x1800dd423  mov     rax, [rax+28h]
0x1800dd427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd42c  mov     ebx, eax
0x1800dd42e  test    eax, eax
0x1800dd430  jz      short loc_1800DD437
0x1800dd432  cmp     eax, 7
0x1800dd435  jnz     short loc_1800DD453
0x1800dd437  mov     rax, [rdi]
0x1800dd43a  mov     rdx, r12
0x1800dd43d  mov     rcx, rdi
0x1800dd440  mov     rax, [rax+38h]
0x1800dd444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd449  jmp     loc_1800DD316
0x1800dd44e  mov     ebx, 4
0x1800dd453  mov     rax, [rdi]
0x1800dd456  mov     edx, 1
0x1800dd45b  mov     rcx, rdi
0x1800dd45e  mov     rax, [rax]
0x1800dd461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd466  test    r15, r15
0x1800dd469  jz      short loc_1800DD478
0x1800dd46b  mov     edx, 10h
0x1800dd470  mov     rcx, r15; Block
0x1800dd473  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800dd478  mov     rcx, [rbp+TokenHandle]; hObject
0x1800dd47c  test    rcx, rcx
0x1800dd47f  jz      short loc_1800DD487
0x1800dd481  call    cs:__imp_CloseHandle
0x1800dd487  test    r14, r14
0x1800dd48a  jz      short loc_1800DD495
0x1800dd48c  mov     rcx, r14; pwk
0x1800dd48f  call    cs:__imp_CloseThreadpoolWork
0x1800dd495  mov     eax, ebx
0x1800dd497  mov     rcx, [rbp+var_8]
0x1800dd49b  xor     rcx, rsp; StackCookie
0x1800dd49e  call    __security_check_cookie
0x1800dd4a3  mov     rbx, [rsp+80h+arg_18]
0x1800dd4ab  add     rsp, 80h
0x1800dd4b2  pop     r15
0x1800dd4b4  pop     r14
0x1800dd4b6  pop     r13
0x1800dd4b8  pop     r12
0x1800dd4ba  pop     rdi
0x1800dd4bb  pop     rsi
0x1800dd4bc  pop     rbp
0x1800dd4bd  retn
```
