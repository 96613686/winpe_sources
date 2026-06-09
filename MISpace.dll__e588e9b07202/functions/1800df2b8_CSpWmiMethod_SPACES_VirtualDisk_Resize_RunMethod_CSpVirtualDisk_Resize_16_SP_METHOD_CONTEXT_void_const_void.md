# CSpWmiMethod<_SPACES_VirtualDisk_Resize>::RunMethod<CSpVirtualDisk::Resize,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800df2b8`
- end: `0x1800df606`
- name: `??$RunMethod@VResize@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_Resize@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800df2b8`
- `0x1800e0b24`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df484`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df484`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800df465`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800df465`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800df47a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800df47a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800df44b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800df44b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800df524`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800df524`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800df5d7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800df5d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800df5c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800df5c9`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_Resize>::RunMethod<CSpVirtualDisk::Resize,16>(
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
  CSpVirtualDisk::Resize *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::Resize *)operator new(0x160u);
  v7 = CSpVirtualDisk::Resize::Resize(v25);
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
      v25 = (CSpVirtualDisk::Resize *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_180332081,
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
0x1800df2b8  mov     [rsp-38h+arg_18], rbx
0x1800df2bd  push    rbp
0x1800df2be  push    rsi
0x1800df2bf  push    rdi
0x1800df2c0  push    r12
0x1800df2c2  push    r13
0x1800df2c4  push    r14
0x1800df2c6  push    r15
0x1800df2c8  mov     rbp, rsp
0x1800df2cb  sub     rsp, 80h
0x1800df2d2  mov     rax, cs:__security_cookie
0x1800df2d9  xor     rax, rsp
0x1800df2dc  mov     [rbp+var_8], rax
0x1800df2e0  xor     eax, eax
0x1800df2e2  mov     rsi, rcx
0x1800df2e5  xorps   xmm0, xmm0
0x1800df2e8  mov     [rbp+var_10], eax
0x1800df2eb  mov     ecx, 160h; Size
0x1800df2f0  mov     [rbp+var_40], eax
0x1800df2f3  movups  [rbp+var_20], xmm0
0x1800df2f7  mov     [rbp+TokenHandle], rax
0x1800df2fb  mov     r12, r8
0x1800df2fe  mov     r13, rdx
0x1800df301  xor     r14d, r14d
0x1800df304  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800df309  mov     rcx, rax; this
0x1800df30c  mov     [rbp+var_28], rax
0x1800df310  call    ??0Resize@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::Resize::Resize(void)
0x1800df315  mov     rdi, rax
0x1800df318  test    rax, rax
0x1800df31b  jnz     short loc_1800DF325
0x1800df31d  lea     ebx, [rax+1Bh]
0x1800df320  jmp     loc_1800DF5C0
0x1800df325  mov     rax, [rax]
0x1800df328  mov     rdx, rsi
0x1800df32b  mov     rcx, rdi
0x1800df32e  xor     r15d, r15d
0x1800df331  mov     rax, [rax+8]
0x1800df335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df33a  lea     rcx, [rbp+var_40]
0x1800df33e  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800df343  mov     [rdi+1Ch], eax
0x1800df346  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800df34a  mov     ecx, [rsi+14h]; unsigned int
0x1800df34d  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800df352  mov     eax, cs:dword_180397B68
0x1800df358  cmp     eax, 5
0x1800df35b  jbe     short loc_1800DF3CB
0x1800df35d  mov     rdx, 400000000000h
0x1800df367  lea     rcx, dword_180397B68
0x1800df36e  call    _tlgKeywordOn
0x1800df373  test    al, al
0x1800df375  jz      short loc_1800DF3CB
0x1800df377  mov     eax, [rbp+var_40]
0x1800df37a  lea     rdx, byte_180332081
0x1800df381  xor     ecx, ecx
0x1800df383  cmp     [rdi+1Ch], eax
0x1800df386  movzx   eax, word ptr [rbp+var_10]
0x1800df38a  mov     word ptr [rbp+var_40], ax
0x1800df38e  setnz   cl
0x1800df391  mov     eax, [rsi+14h]
0x1800df394  mov     [rbp+var_38], eax
0x1800df397  lea     rax, [rbp+var_20]
0x1800df39b  mov     [rbp+var_28], rax
0x1800df39f  lea     rax, [rbp+var_3C]
0x1800df3a3  mov     [rsp+80h+var_48], rax
0x1800df3a8  lea     rax, [rbp+var_40]
0x1800df3ac  mov     [rsp+80h+var_50], rax
0x1800df3b1  lea     rax, [rbp+var_38]
0x1800df3b5  mov     [rsp+80h+var_58], rax
0x1800df3ba  lea     rax, [rbp+var_28]
0x1800df3be  mov     [rsp+80h+var_60], rax
0x1800df3c3  mov     [rbp+var_3C], ecx
0x1800df3c6  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800df3cb  mov     rcx, [rsi]
0x1800df3ce  test    rcx, rcx
0x1800df3d1  jz      loc_1800DF596
0x1800df3d7  mov     rax, [rcx]
0x1800df3da  test    rax, rax
0x1800df3dd  jz      loc_1800DF596
0x1800df3e3  mov     rax, [rax+18h]
0x1800df3e7  lea     r8, [rdi+20h]
0x1800df3eb  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800df3f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df3f7  mov     ebx, eax
0x1800df3f9  test    eax, eax
0x1800df3fb  jnz     loc_1800DF59B
0x1800df401  cmp     [rsi+10h], r14d
0x1800df405  jz      loc_1800DF52F
0x1800df40b  lea     rbx, [rdi+148h]
0x1800df412  mov     rcx, rbx
0x1800df415  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800df41a  mov     rcx, rbx; struct CSpJobMgr **
0x1800df41d  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800df422  test    eax, eax
0x1800df424  jnz     short loc_1800DF42E
0x1800df426  lea     ebx, [rax+1Ch]
0x1800df429  jmp     loc_1800DF59B
0x1800df42e  mov     ecx, 10h; Size
0x1800df433  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800df438  xor     r8d, r8d; pcbe
0x1800df43b  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800df442  mov     rdx, rax; pv
0x1800df445  mov     r15, rax
0x1800df448  mov     [rax], rdi
0x1800df44b  call    cs:__imp_CreateThreadpoolWork
0x1800df451  mov     r14, rax
0x1800df454  test    rax, rax
0x1800df457  jnz     short loc_1800DF465
0x1800df459  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800df45e  mov     ebx, eax
0x1800df460  jmp     loc_1800DF59B
0x1800df465  call    cs:__imp_GetCurrentThread
0x1800df46b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800df46f  xor     r8d, r8d; OpenAsSelf
0x1800df472  mov     rcx, rax; ThreadHandle
0x1800df475  mov     edx, 2000Ch; DesiredAccess
0x1800df47a  call    cs:__imp_OpenThreadToken
0x1800df480  test    eax, eax
0x1800df482  jnz     short loc_1800DF491
0x1800df484  call    cs:__imp_GetLastError
0x1800df48a  cmp     eax, 3F0h
0x1800df48f  jnz     short loc_1800DF459
0x1800df491  mov     rax, [rbp+TokenHandle]
0x1800df495  mov     r8, r13
0x1800df498  mov     [r15+8], rax
0x1800df49c  mov     rcx, rdi
0x1800df49f  mov     rax, [rdi]
0x1800df4a2  mov     rdx, [rsi+8]
0x1800df4a6  mov     rax, [rax+18h]
0x1800df4aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df4af  mov     rax, [rdi]
0x1800df4b2  mov     rdx, r12
0x1800df4b5  mov     rcx, rdi
0x1800df4b8  mov     rax, [rax+28h]
0x1800df4bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df4c1  mov     ebx, eax
0x1800df4c3  test    eax, eax
0x1800df4c5  jz      short loc_1800DF4D0
0x1800df4c7  cmp     eax, 7
0x1800df4ca  jnz     loc_1800DF59B
0x1800df4d0  mov     rax, [rdi]
0x1800df4d3  mov     rdx, r12
0x1800df4d6  mov     rcx, rdi
0x1800df4d9  mov     rax, [rax+38h]
0x1800df4dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df4e2  mov     ebx, eax
0x1800df4e4  test    eax, eax
0x1800df4e6  jnz     loc_1800DF59B
0x1800df4ec  mov     rax, [rdi+150h]
0x1800df4f3  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800df4fa  jnz     short loc_1800DF510
0x1800df4fc  mov     rax, [rdi+158h]
0x1800df503  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800df50a  jz      loc_1800DF59B
0x1800df510  mov     rdx, r12
0x1800df513  mov     rcx, rdi
0x1800df516  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800df51b  mov     ebx, eax
0x1800df51d  test    eax, eax
0x1800df51f  jnz     short loc_1800DF59B
0x1800df521  mov     rcx, r14; pwk
0x1800df524  call    cs:__imp_SubmitThreadpoolWork
0x1800df52a  jmp     loc_1800DF5DD
0x1800df52f  mov     rax, [rdi]
0x1800df532  mov     r8, r13
0x1800df535  mov     rdx, [rsi+8]
0x1800df539  mov     rcx, rdi
0x1800df53c  mov     rax, [rax+10h]
0x1800df540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df545  mov     rax, [rdi]
0x1800df548  mov     rdx, r12
0x1800df54b  mov     rcx, rdi
0x1800df54e  mov     rax, [rax+30h]
0x1800df552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df557  mov     ebx, eax
0x1800df559  test    eax, eax
0x1800df55b  jz      short loc_1800DF562
0x1800df55d  cmp     eax, 7
0x1800df560  jnz     short loc_1800DF59B
0x1800df562  mov     rax, [rdi]
0x1800df565  mov     rdx, r12
0x1800df568  mov     rcx, rdi
0x1800df56b  mov     rax, [rax+28h]
0x1800df56f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df574  mov     ebx, eax
0x1800df576  test    eax, eax
0x1800df578  jz      short loc_1800DF57F
0x1800df57a  cmp     eax, 7
0x1800df57d  jnz     short loc_1800DF59B
0x1800df57f  mov     rax, [rdi]
0x1800df582  mov     rdx, r12
0x1800df585  mov     rcx, rdi
0x1800df588  mov     rax, [rax+38h]
0x1800df58c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df591  jmp     loc_1800DF45E
0x1800df596  mov     ebx, 4
0x1800df59b  mov     rax, [rdi]
0x1800df59e  mov     edx, 1
0x1800df5a3  mov     rcx, rdi
0x1800df5a6  mov     rax, [rax]
0x1800df5a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df5ae  test    r15, r15
0x1800df5b1  jz      short loc_1800DF5C0
0x1800df5b3  mov     edx, 10h
0x1800df5b8  mov     rcx, r15; Block
0x1800df5bb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800df5c0  mov     rcx, [rbp+TokenHandle]; hObject
0x1800df5c4  test    rcx, rcx
0x1800df5c7  jz      short loc_1800DF5CF
0x1800df5c9  call    cs:__imp_CloseHandle
0x1800df5cf  test    r14, r14
0x1800df5d2  jz      short loc_1800DF5DD
0x1800df5d4  mov     rcx, r14; pwk
0x1800df5d7  call    cs:__imp_CloseThreadpoolWork
0x1800df5dd  mov     eax, ebx
0x1800df5df  mov     rcx, [rbp+var_8]
0x1800df5e3  xor     rcx, rsp; StackCookie
0x1800df5e6  call    __security_check_cookie
0x1800df5eb  mov     rbx, [rsp+80h+arg_18]
0x1800df5f3  add     rsp, 80h
0x1800df5fa  pop     r15
0x1800df5fc  pop     r14
0x1800df5fe  pop     r13
0x1800df600  pop     r12
0x1800df602  pop     rdi
0x1800df603  pop     rsi
0x1800df604  pop     rbp
0x1800df605  retn
```
