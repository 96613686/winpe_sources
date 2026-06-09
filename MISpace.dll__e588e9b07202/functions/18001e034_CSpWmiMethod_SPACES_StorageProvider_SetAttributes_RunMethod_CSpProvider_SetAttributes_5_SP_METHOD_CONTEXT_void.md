# CSpWmiMethod<_SPACES_StorageProvider_SetAttributes>::RunMethod<CSpProvider::SetAttributes,5>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18001e034`
- end: `0x18001e382`
- name: `??$RunMethod@VSetAttributes@CSpProvider@@$04@?$CSpWmiMethod@U_SPACES_StorageProvider_SetAttributes@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800227d0`

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
- `0x18001e034`
- `0x18001eac4`
- `0x180024dfc`
- `0x18005d58c`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e200`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e1e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e1e1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e1f6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e1f6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001e1c7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001e1c7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001e2a0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001e2a0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001e353`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001e353`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e345`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e345`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageProvider_SetAttributes>::RunMethod<CSpProvider::SetAttributes,5>(
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
  CSpProvider::SetAttributes *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpProvider::SetAttributes *)operator new(0x160u);
  v7 = CSpProvider::SetAttributes::SetAttributes(v25);
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
      v25 = (CSpProvider::SetAttributes *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_1802F46F1,
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
0x18001e034  mov     [rsp-38h+arg_18], rbx
0x18001e039  push    rbp
0x18001e03a  push    rsi
0x18001e03b  push    rdi
0x18001e03c  push    r12
0x18001e03e  push    r13
0x18001e040  push    r14
0x18001e042  push    r15
0x18001e044  mov     rbp, rsp
0x18001e047  sub     rsp, 80h
0x18001e04e  mov     rax, cs:__security_cookie
0x18001e055  xor     rax, rsp
0x18001e058  mov     [rbp+var_8], rax
0x18001e05c  xor     eax, eax
0x18001e05e  mov     rsi, rcx
0x18001e061  xorps   xmm0, xmm0
0x18001e064  mov     [rbp+var_10], eax
0x18001e067  mov     ecx, 160h; Size
0x18001e06c  mov     [rbp+var_40], eax
0x18001e06f  movups  [rbp+var_20], xmm0
0x18001e073  mov     [rbp+TokenHandle], rax
0x18001e077  mov     r12, r8
0x18001e07a  mov     r13, rdx
0x18001e07d  xor     r14d, r14d
0x18001e080  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e085  mov     rcx, rax; this
0x18001e088  mov     [rbp+var_28], rax
0x18001e08c  call    ??0SetAttributes@CSpProvider@@QEAA@XZ; CSpProvider::SetAttributes::SetAttributes(void)
0x18001e091  mov     rdi, rax
0x18001e094  test    rax, rax
0x18001e097  jnz     short loc_18001E0A1
0x18001e099  lea     ebx, [rax+1Bh]
0x18001e09c  jmp     loc_18001E33C
0x18001e0a1  mov     rax, [rax]
0x18001e0a4  mov     rdx, rsi
0x18001e0a7  mov     rcx, rdi
0x18001e0aa  xor     r15d, r15d
0x18001e0ad  mov     rax, [rax+8]
0x18001e0b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0b6  lea     rcx, [rbp+var_40]
0x18001e0ba  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18001e0bf  mov     [rdi+1Ch], eax
0x18001e0c2  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18001e0c6  mov     ecx, [rsi+14h]; unsigned int
0x18001e0c9  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18001e0ce  mov     eax, cs:dword_180397B68
0x18001e0d4  cmp     eax, 5
0x18001e0d7  jbe     short loc_18001E147
0x18001e0d9  mov     rdx, 400000000000h
0x18001e0e3  lea     rcx, dword_180397B68
0x18001e0ea  call    _tlgKeywordOn
0x18001e0ef  test    al, al
0x18001e0f1  jz      short loc_18001E147
0x18001e0f3  mov     eax, [rbp+var_40]
0x18001e0f6  lea     rdx, byte_1802F46F1
0x18001e0fd  xor     ecx, ecx
0x18001e0ff  cmp     [rdi+1Ch], eax
0x18001e102  movzx   eax, word ptr [rbp+var_10]
0x18001e106  mov     word ptr [rbp+var_40], ax
0x18001e10a  setnz   cl
0x18001e10d  mov     eax, [rsi+14h]
0x18001e110  mov     [rbp+var_38], eax
0x18001e113  lea     rax, [rbp+var_20]
0x18001e117  mov     [rbp+var_28], rax
0x18001e11b  lea     rax, [rbp+var_3C]
0x18001e11f  mov     [rsp+80h+var_48], rax
0x18001e124  lea     rax, [rbp+var_40]
0x18001e128  mov     [rsp+80h+var_50], rax
0x18001e12d  lea     rax, [rbp+var_38]
0x18001e131  mov     [rsp+80h+var_58], rax
0x18001e136  lea     rax, [rbp+var_28]
0x18001e13a  mov     [rsp+80h+var_60], rax
0x18001e13f  mov     [rbp+var_3C], ecx
0x18001e142  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18001e147  mov     rcx, [rsi]
0x18001e14a  test    rcx, rcx
0x18001e14d  jz      loc_18001E312
0x18001e153  mov     rax, [rcx]
0x18001e156  test    rax, rax
0x18001e159  jz      loc_18001E312
0x18001e15f  mov     rax, [rax+18h]
0x18001e163  lea     r8, [rdi+20h]
0x18001e167  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18001e16e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e173  mov     ebx, eax
0x18001e175  test    eax, eax
0x18001e177  jnz     loc_18001E317
0x18001e17d  cmp     [rsi+10h], r14d
0x18001e181  jz      loc_18001E2AB
0x18001e187  lea     rbx, [rdi+148h]
0x18001e18e  mov     rcx, rbx
0x18001e191  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18001e196  mov     rcx, rbx; struct CSpJobMgr **
0x18001e199  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18001e19e  test    eax, eax
0x18001e1a0  jnz     short loc_18001E1AA
0x18001e1a2  lea     ebx, [rax+1Ch]
0x18001e1a5  jmp     loc_18001E317
0x18001e1aa  mov     ecx, 10h; Size
0x18001e1af  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e1b4  xor     r8d, r8d; pcbe
0x18001e1b7  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001e1be  mov     rdx, rax; pv
0x18001e1c1  mov     r15, rax
0x18001e1c4  mov     [rax], rdi
0x18001e1c7  call    cs:__imp_CreateThreadpoolWork
0x18001e1cd  mov     r14, rax
0x18001e1d0  test    rax, rax
0x18001e1d3  jnz     short loc_18001E1E1
0x18001e1d5  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18001e1da  mov     ebx, eax
0x18001e1dc  jmp     loc_18001E317
0x18001e1e1  call    cs:__imp_GetCurrentThread
0x18001e1e7  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001e1eb  xor     r8d, r8d; OpenAsSelf
0x18001e1ee  mov     rcx, rax; ThreadHandle
0x18001e1f1  mov     edx, 2000Ch; DesiredAccess
0x18001e1f6  call    cs:__imp_OpenThreadToken
0x18001e1fc  test    eax, eax
0x18001e1fe  jnz     short loc_18001E20D
0x18001e200  call    cs:__imp_GetLastError
0x18001e206  cmp     eax, 3F0h
0x18001e20b  jnz     short loc_18001E1D5
0x18001e20d  mov     rax, [rbp+TokenHandle]
0x18001e211  mov     r8, r13
0x18001e214  mov     [r15+8], rax
0x18001e218  mov     rcx, rdi
0x18001e21b  mov     rax, [rdi]
0x18001e21e  mov     rdx, [rsi+8]
0x18001e222  mov     rax, [rax+18h]
0x18001e226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e22b  mov     rax, [rdi]
0x18001e22e  mov     rdx, r12
0x18001e231  mov     rcx, rdi
0x18001e234  mov     rax, [rax+28h]
0x18001e238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e23d  mov     ebx, eax
0x18001e23f  test    eax, eax
0x18001e241  jz      short loc_18001E24C
0x18001e243  cmp     eax, 7
0x18001e246  jnz     loc_18001E317
0x18001e24c  mov     rax, [rdi]
0x18001e24f  mov     rdx, r12
0x18001e252  mov     rcx, rdi
0x18001e255  mov     rax, [rax+38h]
0x18001e259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e25e  mov     ebx, eax
0x18001e260  test    eax, eax
0x18001e262  jnz     loc_18001E317
0x18001e268  mov     rax, [rdi+150h]
0x18001e26f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18001e276  jnz     short loc_18001E28C
0x18001e278  mov     rax, [rdi+158h]
0x18001e27f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18001e286  jz      loc_18001E317
0x18001e28c  mov     rdx, r12
0x18001e28f  mov     rcx, rdi
0x18001e292  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18001e297  mov     ebx, eax
0x18001e299  test    eax, eax
0x18001e29b  jnz     short loc_18001E317
0x18001e29d  mov     rcx, r14; pwk
0x18001e2a0  call    cs:__imp_SubmitThreadpoolWork
0x18001e2a6  jmp     loc_18001E359
0x18001e2ab  mov     rax, [rdi]
0x18001e2ae  mov     r8, r13
0x18001e2b1  mov     rdx, [rsi+8]
0x18001e2b5  mov     rcx, rdi
0x18001e2b8  mov     rax, [rax+10h]
0x18001e2bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2c1  mov     rax, [rdi]
0x18001e2c4  mov     rdx, r12
0x18001e2c7  mov     rcx, rdi
0x18001e2ca  mov     rax, [rax+30h]
0x18001e2ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2d3  mov     ebx, eax
0x18001e2d5  test    eax, eax
0x18001e2d7  jz      short loc_18001E2DE
0x18001e2d9  cmp     eax, 7
0x18001e2dc  jnz     short loc_18001E317
0x18001e2de  mov     rax, [rdi]
0x18001e2e1  mov     rdx, r12
0x18001e2e4  mov     rcx, rdi
0x18001e2e7  mov     rax, [rax+28h]
0x18001e2eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2f0  mov     ebx, eax
0x18001e2f2  test    eax, eax
0x18001e2f4  jz      short loc_18001E2FB
0x18001e2f6  cmp     eax, 7
0x18001e2f9  jnz     short loc_18001E317
0x18001e2fb  mov     rax, [rdi]
0x18001e2fe  mov     rdx, r12
0x18001e301  mov     rcx, rdi
0x18001e304  mov     rax, [rax+38h]
0x18001e308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e30d  jmp     loc_18001E1DA
0x18001e312  mov     ebx, 4
0x18001e317  mov     rax, [rdi]
0x18001e31a  mov     edx, 1
0x18001e31f  mov     rcx, rdi
0x18001e322  mov     rax, [rax]
0x18001e325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e32a  test    r15, r15
0x18001e32d  jz      short loc_18001E33C
0x18001e32f  mov     edx, 10h
0x18001e334  mov     rcx, r15; Block
0x18001e337  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e33c  mov     rcx, [rbp+TokenHandle]; hObject
0x18001e340  test    rcx, rcx
0x18001e343  jz      short loc_18001E34B
0x18001e345  call    cs:__imp_CloseHandle
0x18001e34b  test    r14, r14
0x18001e34e  jz      short loc_18001E359
0x18001e350  mov     rcx, r14; pwk
0x18001e353  call    cs:__imp_CloseThreadpoolWork
0x18001e359  mov     eax, ebx
0x18001e35b  mov     rcx, [rbp+var_8]
0x18001e35f  xor     rcx, rsp; StackCookie
0x18001e362  call    __security_check_cookie
0x18001e367  mov     rbx, [rsp+80h+arg_18]
0x18001e36f  add     rsp, 80h
0x18001e376  pop     r15
0x18001e378  pop     r14
0x18001e37a  pop     r13
0x18001e37c  pop     r12
0x18001e37e  pop     rdi
0x18001e37f  pop     rsi
0x18001e380  pop     rbp
0x18001e381  retn
```
