# CSpWmiMethod<_SPACES_VirtualDisk_RemovePhysicalDisk>::RunMethod<CSpVirtualDisk::RemovePhysicalDisk,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800de8bc`
- end: `0x1800dec0a`
- name: `??$RunMethod@VRemovePhysicalDisk@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_RemovePhysicalDisk@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800de8bc`
- `0x1800e09d4`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dea88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dea88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dea69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dea69`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dea7e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dea7e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800dea4f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800dea4f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800deb28`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800deb28`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800debdb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800debdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800debcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800debcd`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_RemovePhysicalDisk>::RunMethod<CSpVirtualDisk::RemovePhysicalDisk,16>(
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
  CSpVirtualDisk::RemovePhysicalDisk *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::RemovePhysicalDisk *)operator new(0x160u);
  v7 = CSpVirtualDisk::RemovePhysicalDisk::RemovePhysicalDisk(v25);
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
      v25 = (CSpVirtualDisk::RemovePhysicalDisk *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&dword_180333CC4,
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
0x1800de8bc  mov     [rsp-38h+arg_18], rbx
0x1800de8c1  push    rbp
0x1800de8c2  push    rsi
0x1800de8c3  push    rdi
0x1800de8c4  push    r12
0x1800de8c6  push    r13
0x1800de8c8  push    r14
0x1800de8ca  push    r15
0x1800de8cc  mov     rbp, rsp
0x1800de8cf  sub     rsp, 80h
0x1800de8d6  mov     rax, cs:__security_cookie
0x1800de8dd  xor     rax, rsp
0x1800de8e0  mov     [rbp+var_8], rax
0x1800de8e4  xor     eax, eax
0x1800de8e6  mov     rsi, rcx
0x1800de8e9  xorps   xmm0, xmm0
0x1800de8ec  mov     [rbp+var_10], eax
0x1800de8ef  mov     ecx, 160h; Size
0x1800de8f4  mov     [rbp+var_40], eax
0x1800de8f7  movups  [rbp+var_20], xmm0
0x1800de8fb  mov     [rbp+TokenHandle], rax
0x1800de8ff  mov     r12, r8
0x1800de902  mov     r13, rdx
0x1800de905  xor     r14d, r14d
0x1800de908  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800de90d  mov     rcx, rax; this
0x1800de910  mov     [rbp+var_28], rax
0x1800de914  call    ??0RemovePhysicalDisk@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::RemovePhysicalDisk::RemovePhysicalDisk(void)
0x1800de919  mov     rdi, rax
0x1800de91c  test    rax, rax
0x1800de91f  jnz     short loc_1800DE929
0x1800de921  lea     ebx, [rax+1Bh]
0x1800de924  jmp     loc_1800DEBC4
0x1800de929  mov     rax, [rax]
0x1800de92c  mov     rdx, rsi
0x1800de92f  mov     rcx, rdi
0x1800de932  xor     r15d, r15d
0x1800de935  mov     rax, [rax+8]
0x1800de939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de93e  lea     rcx, [rbp+var_40]
0x1800de942  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800de947  mov     [rdi+1Ch], eax
0x1800de94a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800de94e  mov     ecx, [rsi+14h]; unsigned int
0x1800de951  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800de956  mov     eax, cs:dword_180397B68
0x1800de95c  cmp     eax, 5
0x1800de95f  jbe     short loc_1800DE9CF
0x1800de961  mov     rdx, 400000000000h
0x1800de96b  lea     rcx, dword_180397B68
0x1800de972  call    _tlgKeywordOn
0x1800de977  test    al, al
0x1800de979  jz      short loc_1800DE9CF
0x1800de97b  mov     eax, [rbp+var_40]
0x1800de97e  lea     rdx, dword_180333CC4
0x1800de985  xor     ecx, ecx
0x1800de987  cmp     [rdi+1Ch], eax
0x1800de98a  movzx   eax, word ptr [rbp+var_10]
0x1800de98e  mov     word ptr [rbp+var_40], ax
0x1800de992  setnz   cl
0x1800de995  mov     eax, [rsi+14h]
0x1800de998  mov     [rbp+var_38], eax
0x1800de99b  lea     rax, [rbp+var_20]
0x1800de99f  mov     [rbp+var_28], rax
0x1800de9a3  lea     rax, [rbp+var_3C]
0x1800de9a7  mov     [rsp+80h+var_48], rax
0x1800de9ac  lea     rax, [rbp+var_40]
0x1800de9b0  mov     [rsp+80h+var_50], rax
0x1800de9b5  lea     rax, [rbp+var_38]
0x1800de9b9  mov     [rsp+80h+var_58], rax
0x1800de9be  lea     rax, [rbp+var_28]
0x1800de9c2  mov     [rsp+80h+var_60], rax
0x1800de9c7  mov     [rbp+var_3C], ecx
0x1800de9ca  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800de9cf  mov     rcx, [rsi]
0x1800de9d2  test    rcx, rcx
0x1800de9d5  jz      loc_1800DEB9A
0x1800de9db  mov     rax, [rcx]
0x1800de9de  test    rax, rax
0x1800de9e1  jz      loc_1800DEB9A
0x1800de9e7  mov     rax, [rax+18h]
0x1800de9eb  lea     r8, [rdi+20h]
0x1800de9ef  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800de9f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de9fb  mov     ebx, eax
0x1800de9fd  test    eax, eax
0x1800de9ff  jnz     loc_1800DEB9F
0x1800dea05  cmp     [rsi+10h], r14d
0x1800dea09  jz      loc_1800DEB33
0x1800dea0f  lea     rbx, [rdi+148h]
0x1800dea16  mov     rcx, rbx
0x1800dea19  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800dea1e  mov     rcx, rbx; struct CSpJobMgr **
0x1800dea21  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800dea26  test    eax, eax
0x1800dea28  jnz     short loc_1800DEA32
0x1800dea2a  lea     ebx, [rax+1Ch]
0x1800dea2d  jmp     loc_1800DEB9F
0x1800dea32  mov     ecx, 10h; Size
0x1800dea37  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800dea3c  xor     r8d, r8d; pcbe
0x1800dea3f  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800dea46  mov     rdx, rax; pv
0x1800dea49  mov     r15, rax
0x1800dea4c  mov     [rax], rdi
0x1800dea4f  call    cs:__imp_CreateThreadpoolWork
0x1800dea55  mov     r14, rax
0x1800dea58  test    rax, rax
0x1800dea5b  jnz     short loc_1800DEA69
0x1800dea5d  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800dea62  mov     ebx, eax
0x1800dea64  jmp     loc_1800DEB9F
0x1800dea69  call    cs:__imp_GetCurrentThread
0x1800dea6f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800dea73  xor     r8d, r8d; OpenAsSelf
0x1800dea76  mov     rcx, rax; ThreadHandle
0x1800dea79  mov     edx, 2000Ch; DesiredAccess
0x1800dea7e  call    cs:__imp_OpenThreadToken
0x1800dea84  test    eax, eax
0x1800dea86  jnz     short loc_1800DEA95
0x1800dea88  call    cs:__imp_GetLastError
0x1800dea8e  cmp     eax, 3F0h
0x1800dea93  jnz     short loc_1800DEA5D
0x1800dea95  mov     rax, [rbp+TokenHandle]
0x1800dea99  mov     r8, r13
0x1800dea9c  mov     [r15+8], rax
0x1800deaa0  mov     rcx, rdi
0x1800deaa3  mov     rax, [rdi]
0x1800deaa6  mov     rdx, [rsi+8]
0x1800deaaa  mov     rax, [rax+18h]
0x1800deaae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800deab3  mov     rax, [rdi]
0x1800deab6  mov     rdx, r12
0x1800deab9  mov     rcx, rdi
0x1800deabc  mov     rax, [rax+28h]
0x1800deac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800deac5  mov     ebx, eax
0x1800deac7  test    eax, eax
0x1800deac9  jz      short loc_1800DEAD4
0x1800deacb  cmp     eax, 7
0x1800deace  jnz     loc_1800DEB9F
0x1800dead4  mov     rax, [rdi]
0x1800dead7  mov     rdx, r12
0x1800deada  mov     rcx, rdi
0x1800deadd  mov     rax, [rax+38h]
0x1800deae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800deae6  mov     ebx, eax
0x1800deae8  test    eax, eax
0x1800deaea  jnz     loc_1800DEB9F
0x1800deaf0  mov     rax, [rdi+150h]
0x1800deaf7  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800deafe  jnz     short loc_1800DEB14
0x1800deb00  mov     rax, [rdi+158h]
0x1800deb07  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800deb0e  jz      loc_1800DEB9F
0x1800deb14  mov     rdx, r12
0x1800deb17  mov     rcx, rdi
0x1800deb1a  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800deb1f  mov     ebx, eax
0x1800deb21  test    eax, eax
0x1800deb23  jnz     short loc_1800DEB9F
0x1800deb25  mov     rcx, r14; pwk
0x1800deb28  call    cs:__imp_SubmitThreadpoolWork
0x1800deb2e  jmp     loc_1800DEBE1
0x1800deb33  mov     rax, [rdi]
0x1800deb36  mov     r8, r13
0x1800deb39  mov     rdx, [rsi+8]
0x1800deb3d  mov     rcx, rdi
0x1800deb40  mov     rax, [rax+10h]
0x1800deb44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800deb49  mov     rax, [rdi]
0x1800deb4c  mov     rdx, r12
0x1800deb4f  mov     rcx, rdi
0x1800deb52  mov     rax, [rax+30h]
0x1800deb56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800deb5b  mov     ebx, eax
0x1800deb5d  test    eax, eax
0x1800deb5f  jz      short loc_1800DEB66
0x1800deb61  cmp     eax, 7
0x1800deb64  jnz     short loc_1800DEB9F
0x1800deb66  mov     rax, [rdi]
0x1800deb69  mov     rdx, r12
0x1800deb6c  mov     rcx, rdi
0x1800deb6f  mov     rax, [rax+28h]
0x1800deb73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800deb78  mov     ebx, eax
0x1800deb7a  test    eax, eax
0x1800deb7c  jz      short loc_1800DEB83
0x1800deb7e  cmp     eax, 7
0x1800deb81  jnz     short loc_1800DEB9F
0x1800deb83  mov     rax, [rdi]
0x1800deb86  mov     rdx, r12
0x1800deb89  mov     rcx, rdi
0x1800deb8c  mov     rax, [rax+38h]
0x1800deb90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800deb95  jmp     loc_1800DEA62
0x1800deb9a  mov     ebx, 4
0x1800deb9f  mov     rax, [rdi]
0x1800deba2  mov     edx, 1
0x1800deba7  mov     rcx, rdi
0x1800debaa  mov     rax, [rax]
0x1800debad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800debb2  test    r15, r15
0x1800debb5  jz      short loc_1800DEBC4
0x1800debb7  mov     edx, 10h
0x1800debbc  mov     rcx, r15; Block
0x1800debbf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800debc4  mov     rcx, [rbp+TokenHandle]; hObject
0x1800debc8  test    rcx, rcx
0x1800debcb  jz      short loc_1800DEBD3
0x1800debcd  call    cs:__imp_CloseHandle
0x1800debd3  test    r14, r14
0x1800debd6  jz      short loc_1800DEBE1
0x1800debd8  mov     rcx, r14; pwk
0x1800debdb  call    cs:__imp_CloseThreadpoolWork
0x1800debe1  mov     eax, ebx
0x1800debe3  mov     rcx, [rbp+var_8]
0x1800debe7  xor     rcx, rsp; StackCookie
0x1800debea  call    __security_check_cookie
0x1800debef  mov     rbx, [rsp+80h+arg_18]
0x1800debf7  add     rsp, 80h
0x1800debfe  pop     r15
0x1800dec00  pop     r14
0x1800dec02  pop     r13
0x1800dec04  pop     r12
0x1800dec06  pop     rdi
0x1800dec07  pop     rsi
0x1800dec08  pop     rbp
0x1800dec09  retn
```
