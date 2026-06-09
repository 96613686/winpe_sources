# CSpWmiMethod<_SPACES_StorageEnclosure_UpdateFirmware>::RunMethod<CSpStorageEnclosure::UpdateFirmware,8>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800d6d78`
- end: `0x1800d70c6`
- name: `??$RunMethod@VUpdateFirmware@CSpStorageEnclosure@@$07@?$CSpWmiMethod@U_SPACES_StorageEnclosure_UpdateFirmware@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x1800d8f20`

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
- `0x1800d6d78`
- `0x1800d7300`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6f44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6f44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d6f25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d6f25`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d6f3a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d6f3a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d6f0b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d6f0b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d6fe4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d6fe4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d7097`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d7097`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d7089`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d7089`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageEnclosure_UpdateFirmware>::RunMethod<CSpStorageEnclosure::UpdateFirmware,8>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 updated; // rax
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
  CSpStorageEnclosure::UpdateFirmware *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageEnclosure::UpdateFirmware *)operator new(0x160u);
  updated = CSpStorageEnclosure::UpdateFirmware::UpdateFirmware(v25);
  v8 = updated;
  if ( updated )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)updated + 8LL))(updated, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStorageEnclosure::UpdateFirmware *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_18032F533,
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
0x1800d6d78  mov     [rsp-38h+arg_18], rbx
0x1800d6d7d  push    rbp
0x1800d6d7e  push    rsi
0x1800d6d7f  push    rdi
0x1800d6d80  push    r12
0x1800d6d82  push    r13
0x1800d6d84  push    r14
0x1800d6d86  push    r15
0x1800d6d88  mov     rbp, rsp
0x1800d6d8b  sub     rsp, 80h
0x1800d6d92  mov     rax, cs:__security_cookie
0x1800d6d99  xor     rax, rsp
0x1800d6d9c  mov     [rbp+var_8], rax
0x1800d6da0  xor     eax, eax
0x1800d6da2  mov     rsi, rcx
0x1800d6da5  xorps   xmm0, xmm0
0x1800d6da8  mov     [rbp+var_10], eax
0x1800d6dab  mov     ecx, 160h; Size
0x1800d6db0  mov     [rbp+var_40], eax
0x1800d6db3  movups  [rbp+var_20], xmm0
0x1800d6db7  mov     [rbp+TokenHandle], rax
0x1800d6dbb  mov     r12, r8
0x1800d6dbe  mov     r13, rdx
0x1800d6dc1  xor     r14d, r14d
0x1800d6dc4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d6dc9  mov     rcx, rax; this
0x1800d6dcc  mov     [rbp+var_28], rax
0x1800d6dd0  call    ??0UpdateFirmware@CSpStorageEnclosure@@QEAA@XZ; CSpStorageEnclosure::UpdateFirmware::UpdateFirmware(void)
0x1800d6dd5  mov     rdi, rax
0x1800d6dd8  test    rax, rax
0x1800d6ddb  jnz     short loc_1800D6DE5
0x1800d6ddd  lea     ebx, [rax+1Bh]
0x1800d6de0  jmp     loc_1800D7080
0x1800d6de5  mov     rax, [rax]
0x1800d6de8  mov     rdx, rsi
0x1800d6deb  mov     rcx, rdi
0x1800d6dee  xor     r15d, r15d
0x1800d6df1  mov     rax, [rax+8]
0x1800d6df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6dfa  lea     rcx, [rbp+var_40]
0x1800d6dfe  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800d6e03  mov     [rdi+1Ch], eax
0x1800d6e06  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800d6e0a  mov     ecx, [rsi+14h]; unsigned int
0x1800d6e0d  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800d6e12  mov     eax, cs:dword_180397B68
0x1800d6e18  cmp     eax, 5
0x1800d6e1b  jbe     short loc_1800D6E8B
0x1800d6e1d  mov     rdx, 400000000000h
0x1800d6e27  lea     rcx, dword_180397B68
0x1800d6e2e  call    _tlgKeywordOn
0x1800d6e33  test    al, al
0x1800d6e35  jz      short loc_1800D6E8B
0x1800d6e37  mov     eax, [rbp+var_40]
0x1800d6e3a  lea     rdx, byte_18032F533
0x1800d6e41  xor     ecx, ecx
0x1800d6e43  cmp     [rdi+1Ch], eax
0x1800d6e46  movzx   eax, word ptr [rbp+var_10]
0x1800d6e4a  mov     word ptr [rbp+var_40], ax
0x1800d6e4e  setnz   cl
0x1800d6e51  mov     eax, [rsi+14h]
0x1800d6e54  mov     [rbp+var_38], eax
0x1800d6e57  lea     rax, [rbp+var_20]
0x1800d6e5b  mov     [rbp+var_28], rax
0x1800d6e5f  lea     rax, [rbp+var_3C]
0x1800d6e63  mov     [rsp+80h+var_48], rax
0x1800d6e68  lea     rax, [rbp+var_40]
0x1800d6e6c  mov     [rsp+80h+var_50], rax
0x1800d6e71  lea     rax, [rbp+var_38]
0x1800d6e75  mov     [rsp+80h+var_58], rax
0x1800d6e7a  lea     rax, [rbp+var_28]
0x1800d6e7e  mov     [rsp+80h+var_60], rax
0x1800d6e83  mov     [rbp+var_3C], ecx
0x1800d6e86  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800d6e8b  mov     rcx, [rsi]
0x1800d6e8e  test    rcx, rcx
0x1800d6e91  jz      loc_1800D7056
0x1800d6e97  mov     rax, [rcx]
0x1800d6e9a  test    rax, rax
0x1800d6e9d  jz      loc_1800D7056
0x1800d6ea3  mov     rax, [rax+18h]
0x1800d6ea7  lea     r8, [rdi+20h]
0x1800d6eab  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800d6eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6eb7  mov     ebx, eax
0x1800d6eb9  test    eax, eax
0x1800d6ebb  jnz     loc_1800D705B
0x1800d6ec1  cmp     [rsi+10h], r14d
0x1800d6ec5  jz      loc_1800D6FEF
0x1800d6ecb  lea     rbx, [rdi+148h]
0x1800d6ed2  mov     rcx, rbx
0x1800d6ed5  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800d6eda  mov     rcx, rbx; struct CSpJobMgr **
0x1800d6edd  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800d6ee2  test    eax, eax
0x1800d6ee4  jnz     short loc_1800D6EEE
0x1800d6ee6  lea     ebx, [rax+1Ch]
0x1800d6ee9  jmp     loc_1800D705B
0x1800d6eee  mov     ecx, 10h; Size
0x1800d6ef3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d6ef8  xor     r8d, r8d; pcbe
0x1800d6efb  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800d6f02  mov     rdx, rax; pv
0x1800d6f05  mov     r15, rax
0x1800d6f08  mov     [rax], rdi
0x1800d6f0b  call    cs:__imp_CreateThreadpoolWork
0x1800d6f11  mov     r14, rax
0x1800d6f14  test    rax, rax
0x1800d6f17  jnz     short loc_1800D6F25
0x1800d6f19  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800d6f1e  mov     ebx, eax
0x1800d6f20  jmp     loc_1800D705B
0x1800d6f25  call    cs:__imp_GetCurrentThread
0x1800d6f2b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800d6f2f  xor     r8d, r8d; OpenAsSelf
0x1800d6f32  mov     rcx, rax; ThreadHandle
0x1800d6f35  mov     edx, 2000Ch; DesiredAccess
0x1800d6f3a  call    cs:__imp_OpenThreadToken
0x1800d6f40  test    eax, eax
0x1800d6f42  jnz     short loc_1800D6F51
0x1800d6f44  call    cs:__imp_GetLastError
0x1800d6f4a  cmp     eax, 3F0h
0x1800d6f4f  jnz     short loc_1800D6F19
0x1800d6f51  mov     rax, [rbp+TokenHandle]
0x1800d6f55  mov     r8, r13
0x1800d6f58  mov     [r15+8], rax
0x1800d6f5c  mov     rcx, rdi
0x1800d6f5f  mov     rax, [rdi]
0x1800d6f62  mov     rdx, [rsi+8]
0x1800d6f66  mov     rax, [rax+18h]
0x1800d6f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6f6f  mov     rax, [rdi]
0x1800d6f72  mov     rdx, r12
0x1800d6f75  mov     rcx, rdi
0x1800d6f78  mov     rax, [rax+28h]
0x1800d6f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6f81  mov     ebx, eax
0x1800d6f83  test    eax, eax
0x1800d6f85  jz      short loc_1800D6F90
0x1800d6f87  cmp     eax, 7
0x1800d6f8a  jnz     loc_1800D705B
0x1800d6f90  mov     rax, [rdi]
0x1800d6f93  mov     rdx, r12
0x1800d6f96  mov     rcx, rdi
0x1800d6f99  mov     rax, [rax+38h]
0x1800d6f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6fa2  mov     ebx, eax
0x1800d6fa4  test    eax, eax
0x1800d6fa6  jnz     loc_1800D705B
0x1800d6fac  mov     rax, [rdi+150h]
0x1800d6fb3  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800d6fba  jnz     short loc_1800D6FD0
0x1800d6fbc  mov     rax, [rdi+158h]
0x1800d6fc3  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800d6fca  jz      loc_1800D705B
0x1800d6fd0  mov     rdx, r12
0x1800d6fd3  mov     rcx, rdi
0x1800d6fd6  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800d6fdb  mov     ebx, eax
0x1800d6fdd  test    eax, eax
0x1800d6fdf  jnz     short loc_1800D705B
0x1800d6fe1  mov     rcx, r14; pwk
0x1800d6fe4  call    cs:__imp_SubmitThreadpoolWork
0x1800d6fea  jmp     loc_1800D709D
0x1800d6fef  mov     rax, [rdi]
0x1800d6ff2  mov     r8, r13
0x1800d6ff5  mov     rdx, [rsi+8]
0x1800d6ff9  mov     rcx, rdi
0x1800d6ffc  mov     rax, [rax+10h]
0x1800d7000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7005  mov     rax, [rdi]
0x1800d7008  mov     rdx, r12
0x1800d700b  mov     rcx, rdi
0x1800d700e  mov     rax, [rax+30h]
0x1800d7012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7017  mov     ebx, eax
0x1800d7019  test    eax, eax
0x1800d701b  jz      short loc_1800D7022
0x1800d701d  cmp     eax, 7
0x1800d7020  jnz     short loc_1800D705B
0x1800d7022  mov     rax, [rdi]
0x1800d7025  mov     rdx, r12
0x1800d7028  mov     rcx, rdi
0x1800d702b  mov     rax, [rax+28h]
0x1800d702f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7034  mov     ebx, eax
0x1800d7036  test    eax, eax
0x1800d7038  jz      short loc_1800D703F
0x1800d703a  cmp     eax, 7
0x1800d703d  jnz     short loc_1800D705B
0x1800d703f  mov     rax, [rdi]
0x1800d7042  mov     rdx, r12
0x1800d7045  mov     rcx, rdi
0x1800d7048  mov     rax, [rax+38h]
0x1800d704c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7051  jmp     loc_1800D6F1E
0x1800d7056  mov     ebx, 4
0x1800d705b  mov     rax, [rdi]
0x1800d705e  mov     edx, 1
0x1800d7063  mov     rcx, rdi
0x1800d7066  mov     rax, [rax]
0x1800d7069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d706e  test    r15, r15
0x1800d7071  jz      short loc_1800D7080
0x1800d7073  mov     edx, 10h
0x1800d7078  mov     rcx, r15; Block
0x1800d707b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800d7080  mov     rcx, [rbp+TokenHandle]; hObject
0x1800d7084  test    rcx, rcx
0x1800d7087  jz      short loc_1800D708F
0x1800d7089  call    cs:__imp_CloseHandle
0x1800d708f  test    r14, r14
0x1800d7092  jz      short loc_1800D709D
0x1800d7094  mov     rcx, r14; pwk
0x1800d7097  call    cs:__imp_CloseThreadpoolWork
0x1800d709d  mov     eax, ebx
0x1800d709f  mov     rcx, [rbp+var_8]
0x1800d70a3  xor     rcx, rsp; StackCookie
0x1800d70a6  call    __security_check_cookie
0x1800d70ab  mov     rbx, [rsp+80h+arg_18]
0x1800d70b3  add     rsp, 80h
0x1800d70ba  pop     r15
0x1800d70bc  pop     r14
0x1800d70be  pop     r13
0x1800d70c0  pop     r12
0x1800d70c2  pop     rdi
0x1800d70c3  pop     rsi
0x1800d70c4  pop     rbp
0x1800d70c5  retn
```
