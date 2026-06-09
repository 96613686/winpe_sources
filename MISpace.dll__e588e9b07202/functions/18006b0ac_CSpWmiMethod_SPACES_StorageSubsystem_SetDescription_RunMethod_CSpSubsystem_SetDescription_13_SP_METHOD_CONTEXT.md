# CSpWmiMethod<_SPACES_StorageSubsystem_SetDescription>::RunMethod<CSpSubsystem::SetDescription,13>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18006b0ac`
- end: `0x18006b3fa`
- name: `??$RunMethod@VSetDescription@CSpSubsystem@@$0N@@?$CSpWmiMethod@U_SPACES_StorageSubsystem_SetDescription@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x18006b0ac`
- `0x18006bfe8`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b278`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b278`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006b259`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006b259`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006b26e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006b26e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006b23f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006b23f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006b318`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006b318`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006b3cb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006b3cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006b3bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006b3bd`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageSubsystem_SetDescription>::RunMethod<CSpSubsystem::SetDescription,13>(
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
  CSpSubsystem::SetDescription *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpSubsystem::SetDescription *)operator new(0x160u);
  v7 = CSpSubsystem::SetDescription::SetDescription(v25);
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
      v25 = (CSpSubsystem::SetDescription *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_18030E5B1,
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
0x18006b0ac  mov     [rsp-38h+arg_18], rbx
0x18006b0b1  push    rbp
0x18006b0b2  push    rsi
0x18006b0b3  push    rdi
0x18006b0b4  push    r12
0x18006b0b6  push    r13
0x18006b0b8  push    r14
0x18006b0ba  push    r15
0x18006b0bc  mov     rbp, rsp
0x18006b0bf  sub     rsp, 80h
0x18006b0c6  mov     rax, cs:__security_cookie
0x18006b0cd  xor     rax, rsp
0x18006b0d0  mov     [rbp+var_8], rax
0x18006b0d4  xor     eax, eax
0x18006b0d6  mov     rsi, rcx
0x18006b0d9  xorps   xmm0, xmm0
0x18006b0dc  mov     [rbp+var_10], eax
0x18006b0df  mov     ecx, 160h; Size
0x18006b0e4  mov     [rbp+var_40], eax
0x18006b0e7  movups  [rbp+var_20], xmm0
0x18006b0eb  mov     [rbp+TokenHandle], rax
0x18006b0ef  mov     r12, r8
0x18006b0f2  mov     r13, rdx
0x18006b0f5  xor     r14d, r14d
0x18006b0f8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006b0fd  mov     rcx, rax; this
0x18006b100  mov     [rbp+var_28], rax
0x18006b104  call    ??0SetDescription@CSpSubsystem@@QEAA@XZ; CSpSubsystem::SetDescription::SetDescription(void)
0x18006b109  mov     rdi, rax
0x18006b10c  test    rax, rax
0x18006b10f  jnz     short loc_18006B119
0x18006b111  lea     ebx, [rax+1Bh]
0x18006b114  jmp     loc_18006B3B4
0x18006b119  mov     rax, [rax]
0x18006b11c  mov     rdx, rsi
0x18006b11f  mov     rcx, rdi
0x18006b122  xor     r15d, r15d
0x18006b125  mov     rax, [rax+8]
0x18006b129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b12e  lea     rcx, [rbp+var_40]
0x18006b132  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18006b137  mov     [rdi+1Ch], eax
0x18006b13a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18006b13e  mov     ecx, [rsi+14h]; unsigned int
0x18006b141  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18006b146  mov     eax, cs:dword_180397B68
0x18006b14c  cmp     eax, 5
0x18006b14f  jbe     short loc_18006B1BF
0x18006b151  mov     rdx, 400000000000h
0x18006b15b  lea     rcx, dword_180397B68
0x18006b162  call    _tlgKeywordOn
0x18006b167  test    al, al
0x18006b169  jz      short loc_18006B1BF
0x18006b16b  mov     eax, [rbp+var_40]
0x18006b16e  lea     rdx, byte_18030E5B1
0x18006b175  xor     ecx, ecx
0x18006b177  cmp     [rdi+1Ch], eax
0x18006b17a  movzx   eax, word ptr [rbp+var_10]
0x18006b17e  mov     word ptr [rbp+var_40], ax
0x18006b182  setnz   cl
0x18006b185  mov     eax, [rsi+14h]
0x18006b188  mov     [rbp+var_38], eax
0x18006b18b  lea     rax, [rbp+var_20]
0x18006b18f  mov     [rbp+var_28], rax
0x18006b193  lea     rax, [rbp+var_3C]
0x18006b197  mov     [rsp+80h+var_48], rax
0x18006b19c  lea     rax, [rbp+var_40]
0x18006b1a0  mov     [rsp+80h+var_50], rax
0x18006b1a5  lea     rax, [rbp+var_38]
0x18006b1a9  mov     [rsp+80h+var_58], rax
0x18006b1ae  lea     rax, [rbp+var_28]
0x18006b1b2  mov     [rsp+80h+var_60], rax
0x18006b1b7  mov     [rbp+var_3C], ecx
0x18006b1ba  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18006b1bf  mov     rcx, [rsi]
0x18006b1c2  test    rcx, rcx
0x18006b1c5  jz      loc_18006B38A
0x18006b1cb  mov     rax, [rcx]
0x18006b1ce  test    rax, rax
0x18006b1d1  jz      loc_18006B38A
0x18006b1d7  mov     rax, [rax+18h]
0x18006b1db  lea     r8, [rdi+20h]
0x18006b1df  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18006b1e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b1eb  mov     ebx, eax
0x18006b1ed  test    eax, eax
0x18006b1ef  jnz     loc_18006B38F
0x18006b1f5  cmp     [rsi+10h], r14d
0x18006b1f9  jz      loc_18006B323
0x18006b1ff  lea     rbx, [rdi+148h]
0x18006b206  mov     rcx, rbx
0x18006b209  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18006b20e  mov     rcx, rbx; struct CSpJobMgr **
0x18006b211  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18006b216  test    eax, eax
0x18006b218  jnz     short loc_18006B222
0x18006b21a  lea     ebx, [rax+1Ch]
0x18006b21d  jmp     loc_18006B38F
0x18006b222  mov     ecx, 10h; Size
0x18006b227  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006b22c  xor     r8d, r8d; pcbe
0x18006b22f  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18006b236  mov     rdx, rax; pv
0x18006b239  mov     r15, rax
0x18006b23c  mov     [rax], rdi
0x18006b23f  call    cs:__imp_CreateThreadpoolWork
0x18006b245  mov     r14, rax
0x18006b248  test    rax, rax
0x18006b24b  jnz     short loc_18006B259
0x18006b24d  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18006b252  mov     ebx, eax
0x18006b254  jmp     loc_18006B38F
0x18006b259  call    cs:__imp_GetCurrentThread
0x18006b25f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18006b263  xor     r8d, r8d; OpenAsSelf
0x18006b266  mov     rcx, rax; ThreadHandle
0x18006b269  mov     edx, 2000Ch; DesiredAccess
0x18006b26e  call    cs:__imp_OpenThreadToken
0x18006b274  test    eax, eax
0x18006b276  jnz     short loc_18006B285
0x18006b278  call    cs:__imp_GetLastError
0x18006b27e  cmp     eax, 3F0h
0x18006b283  jnz     short loc_18006B24D
0x18006b285  mov     rax, [rbp+TokenHandle]
0x18006b289  mov     r8, r13
0x18006b28c  mov     [r15+8], rax
0x18006b290  mov     rcx, rdi
0x18006b293  mov     rax, [rdi]
0x18006b296  mov     rdx, [rsi+8]
0x18006b29a  mov     rax, [rax+18h]
0x18006b29e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b2a3  mov     rax, [rdi]
0x18006b2a6  mov     rdx, r12
0x18006b2a9  mov     rcx, rdi
0x18006b2ac  mov     rax, [rax+28h]
0x18006b2b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b2b5  mov     ebx, eax
0x18006b2b7  test    eax, eax
0x18006b2b9  jz      short loc_18006B2C4
0x18006b2bb  cmp     eax, 7
0x18006b2be  jnz     loc_18006B38F
0x18006b2c4  mov     rax, [rdi]
0x18006b2c7  mov     rdx, r12
0x18006b2ca  mov     rcx, rdi
0x18006b2cd  mov     rax, [rax+38h]
0x18006b2d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b2d6  mov     ebx, eax
0x18006b2d8  test    eax, eax
0x18006b2da  jnz     loc_18006B38F
0x18006b2e0  mov     rax, [rdi+150h]
0x18006b2e7  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18006b2ee  jnz     short loc_18006B304
0x18006b2f0  mov     rax, [rdi+158h]
0x18006b2f7  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18006b2fe  jz      loc_18006B38F
0x18006b304  mov     rdx, r12
0x18006b307  mov     rcx, rdi
0x18006b30a  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18006b30f  mov     ebx, eax
0x18006b311  test    eax, eax
0x18006b313  jnz     short loc_18006B38F
0x18006b315  mov     rcx, r14; pwk
0x18006b318  call    cs:__imp_SubmitThreadpoolWork
0x18006b31e  jmp     loc_18006B3D1
0x18006b323  mov     rax, [rdi]
0x18006b326  mov     r8, r13
0x18006b329  mov     rdx, [rsi+8]
0x18006b32d  mov     rcx, rdi
0x18006b330  mov     rax, [rax+10h]
0x18006b334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b339  mov     rax, [rdi]
0x18006b33c  mov     rdx, r12
0x18006b33f  mov     rcx, rdi
0x18006b342  mov     rax, [rax+30h]
0x18006b346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b34b  mov     ebx, eax
0x18006b34d  test    eax, eax
0x18006b34f  jz      short loc_18006B356
0x18006b351  cmp     eax, 7
0x18006b354  jnz     short loc_18006B38F
0x18006b356  mov     rax, [rdi]
0x18006b359  mov     rdx, r12
0x18006b35c  mov     rcx, rdi
0x18006b35f  mov     rax, [rax+28h]
0x18006b363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b368  mov     ebx, eax
0x18006b36a  test    eax, eax
0x18006b36c  jz      short loc_18006B373
0x18006b36e  cmp     eax, 7
0x18006b371  jnz     short loc_18006B38F
0x18006b373  mov     rax, [rdi]
0x18006b376  mov     rdx, r12
0x18006b379  mov     rcx, rdi
0x18006b37c  mov     rax, [rax+38h]
0x18006b380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b385  jmp     loc_18006B252
0x18006b38a  mov     ebx, 4
0x18006b38f  mov     rax, [rdi]
0x18006b392  mov     edx, 1
0x18006b397  mov     rcx, rdi
0x18006b39a  mov     rax, [rax]
0x18006b39d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b3a2  test    r15, r15
0x18006b3a5  jz      short loc_18006B3B4
0x18006b3a7  mov     edx, 10h
0x18006b3ac  mov     rcx, r15; Block
0x18006b3af  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006b3b4  mov     rcx, [rbp+TokenHandle]; hObject
0x18006b3b8  test    rcx, rcx
0x18006b3bb  jz      short loc_18006B3C3
0x18006b3bd  call    cs:__imp_CloseHandle
0x18006b3c3  test    r14, r14
0x18006b3c6  jz      short loc_18006B3D1
0x18006b3c8  mov     rcx, r14; pwk
0x18006b3cb  call    cs:__imp_CloseThreadpoolWork
0x18006b3d1  mov     eax, ebx
0x18006b3d3  mov     rcx, [rbp+var_8]
0x18006b3d7  xor     rcx, rsp; StackCookie
0x18006b3da  call    __security_check_cookie
0x18006b3df  mov     rbx, [rsp+80h+arg_18]
0x18006b3e7  add     rsp, 80h
0x18006b3ee  pop     r15
0x18006b3f0  pop     r14
0x18006b3f2  pop     r13
0x18006b3f4  pop     r12
0x18006b3f6  pop     rdi
0x18006b3f7  pop     rsi
0x18006b3f8  pop     rbp
0x18006b3f9  retn
```
