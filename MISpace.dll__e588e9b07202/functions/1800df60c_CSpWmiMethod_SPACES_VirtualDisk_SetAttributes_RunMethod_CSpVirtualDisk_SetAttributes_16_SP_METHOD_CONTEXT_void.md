# CSpWmiMethod<_SPACES_VirtualDisk_SetAttributes>::RunMethod<CSpVirtualDisk::SetAttributes,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800df60c`
- end: `0x1800df95a`
- name: `??$RunMethod@VSetAttributes@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_SetAttributes@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800df60c`
- `0x1800e0b90`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df7d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df7d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800df7b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800df7b9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800df7ce`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800df7ce`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800df79f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800df79f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800df878`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800df878`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800df92b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800df92b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800df91d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800df91d`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_SetAttributes>::RunMethod<CSpVirtualDisk::SetAttributes,16>(
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
  CSpVirtualDisk::SetAttributes *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::SetAttributes *)operator new(0x160u);
  v7 = CSpVirtualDisk::SetAttributes::SetAttributes(v25);
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
      v25 = (CSpVirtualDisk::SetAttributes *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)word_1803327AA,
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
0x1800df60c  mov     [rsp-38h+arg_18], rbx
0x1800df611  push    rbp
0x1800df612  push    rsi
0x1800df613  push    rdi
0x1800df614  push    r12
0x1800df616  push    r13
0x1800df618  push    r14
0x1800df61a  push    r15
0x1800df61c  mov     rbp, rsp
0x1800df61f  sub     rsp, 80h
0x1800df626  mov     rax, cs:__security_cookie
0x1800df62d  xor     rax, rsp
0x1800df630  mov     [rbp+var_8], rax
0x1800df634  xor     eax, eax
0x1800df636  mov     rsi, rcx
0x1800df639  xorps   xmm0, xmm0
0x1800df63c  mov     [rbp+var_10], eax
0x1800df63f  mov     ecx, 160h; Size
0x1800df644  mov     [rbp+var_40], eax
0x1800df647  movups  [rbp+var_20], xmm0
0x1800df64b  mov     [rbp+TokenHandle], rax
0x1800df64f  mov     r12, r8
0x1800df652  mov     r13, rdx
0x1800df655  xor     r14d, r14d
0x1800df658  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800df65d  mov     rcx, rax; this
0x1800df660  mov     [rbp+var_28], rax
0x1800df664  call    ??0SetAttributes@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::SetAttributes::SetAttributes(void)
0x1800df669  mov     rdi, rax
0x1800df66c  test    rax, rax
0x1800df66f  jnz     short loc_1800DF679
0x1800df671  lea     ebx, [rax+1Bh]
0x1800df674  jmp     loc_1800DF914
0x1800df679  mov     rax, [rax]
0x1800df67c  mov     rdx, rsi
0x1800df67f  mov     rcx, rdi
0x1800df682  xor     r15d, r15d
0x1800df685  mov     rax, [rax+8]
0x1800df689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df68e  lea     rcx, [rbp+var_40]
0x1800df692  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800df697  mov     [rdi+1Ch], eax
0x1800df69a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800df69e  mov     ecx, [rsi+14h]; unsigned int
0x1800df6a1  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800df6a6  mov     eax, cs:dword_180397B68
0x1800df6ac  cmp     eax, 5
0x1800df6af  jbe     short loc_1800DF71F
0x1800df6b1  mov     rdx, 400000000000h
0x1800df6bb  lea     rcx, dword_180397B68
0x1800df6c2  call    _tlgKeywordOn
0x1800df6c7  test    al, al
0x1800df6c9  jz      short loc_1800DF71F
0x1800df6cb  mov     eax, [rbp+var_40]
0x1800df6ce  lea     rdx, word_1803327AA
0x1800df6d5  xor     ecx, ecx
0x1800df6d7  cmp     [rdi+1Ch], eax
0x1800df6da  movzx   eax, word ptr [rbp+var_10]
0x1800df6de  mov     word ptr [rbp+var_40], ax
0x1800df6e2  setnz   cl
0x1800df6e5  mov     eax, [rsi+14h]
0x1800df6e8  mov     [rbp+var_38], eax
0x1800df6eb  lea     rax, [rbp+var_20]
0x1800df6ef  mov     [rbp+var_28], rax
0x1800df6f3  lea     rax, [rbp+var_3C]
0x1800df6f7  mov     [rsp+80h+var_48], rax
0x1800df6fc  lea     rax, [rbp+var_40]
0x1800df700  mov     [rsp+80h+var_50], rax
0x1800df705  lea     rax, [rbp+var_38]
0x1800df709  mov     [rsp+80h+var_58], rax
0x1800df70e  lea     rax, [rbp+var_28]
0x1800df712  mov     [rsp+80h+var_60], rax
0x1800df717  mov     [rbp+var_3C], ecx
0x1800df71a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800df71f  mov     rcx, [rsi]
0x1800df722  test    rcx, rcx
0x1800df725  jz      loc_1800DF8EA
0x1800df72b  mov     rax, [rcx]
0x1800df72e  test    rax, rax
0x1800df731  jz      loc_1800DF8EA
0x1800df737  mov     rax, [rax+18h]
0x1800df73b  lea     r8, [rdi+20h]
0x1800df73f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800df746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df74b  mov     ebx, eax
0x1800df74d  test    eax, eax
0x1800df74f  jnz     loc_1800DF8EF
0x1800df755  cmp     [rsi+10h], r14d
0x1800df759  jz      loc_1800DF883
0x1800df75f  lea     rbx, [rdi+148h]
0x1800df766  mov     rcx, rbx
0x1800df769  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800df76e  mov     rcx, rbx; struct CSpJobMgr **
0x1800df771  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800df776  test    eax, eax
0x1800df778  jnz     short loc_1800DF782
0x1800df77a  lea     ebx, [rax+1Ch]
0x1800df77d  jmp     loc_1800DF8EF
0x1800df782  mov     ecx, 10h; Size
0x1800df787  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800df78c  xor     r8d, r8d; pcbe
0x1800df78f  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800df796  mov     rdx, rax; pv
0x1800df799  mov     r15, rax
0x1800df79c  mov     [rax], rdi
0x1800df79f  call    cs:__imp_CreateThreadpoolWork
0x1800df7a5  mov     r14, rax
0x1800df7a8  test    rax, rax
0x1800df7ab  jnz     short loc_1800DF7B9
0x1800df7ad  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800df7b2  mov     ebx, eax
0x1800df7b4  jmp     loc_1800DF8EF
0x1800df7b9  call    cs:__imp_GetCurrentThread
0x1800df7bf  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800df7c3  xor     r8d, r8d; OpenAsSelf
0x1800df7c6  mov     rcx, rax; ThreadHandle
0x1800df7c9  mov     edx, 2000Ch; DesiredAccess
0x1800df7ce  call    cs:__imp_OpenThreadToken
0x1800df7d4  test    eax, eax
0x1800df7d6  jnz     short loc_1800DF7E5
0x1800df7d8  call    cs:__imp_GetLastError
0x1800df7de  cmp     eax, 3F0h
0x1800df7e3  jnz     short loc_1800DF7AD
0x1800df7e5  mov     rax, [rbp+TokenHandle]
0x1800df7e9  mov     r8, r13
0x1800df7ec  mov     [r15+8], rax
0x1800df7f0  mov     rcx, rdi
0x1800df7f3  mov     rax, [rdi]
0x1800df7f6  mov     rdx, [rsi+8]
0x1800df7fa  mov     rax, [rax+18h]
0x1800df7fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df803  mov     rax, [rdi]
0x1800df806  mov     rdx, r12
0x1800df809  mov     rcx, rdi
0x1800df80c  mov     rax, [rax+28h]
0x1800df810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df815  mov     ebx, eax
0x1800df817  test    eax, eax
0x1800df819  jz      short loc_1800DF824
0x1800df81b  cmp     eax, 7
0x1800df81e  jnz     loc_1800DF8EF
0x1800df824  mov     rax, [rdi]
0x1800df827  mov     rdx, r12
0x1800df82a  mov     rcx, rdi
0x1800df82d  mov     rax, [rax+38h]
0x1800df831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df836  mov     ebx, eax
0x1800df838  test    eax, eax
0x1800df83a  jnz     loc_1800DF8EF
0x1800df840  mov     rax, [rdi+150h]
0x1800df847  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800df84e  jnz     short loc_1800DF864
0x1800df850  mov     rax, [rdi+158h]
0x1800df857  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800df85e  jz      loc_1800DF8EF
0x1800df864  mov     rdx, r12
0x1800df867  mov     rcx, rdi
0x1800df86a  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800df86f  mov     ebx, eax
0x1800df871  test    eax, eax
0x1800df873  jnz     short loc_1800DF8EF
0x1800df875  mov     rcx, r14; pwk
0x1800df878  call    cs:__imp_SubmitThreadpoolWork
0x1800df87e  jmp     loc_1800DF931
0x1800df883  mov     rax, [rdi]
0x1800df886  mov     r8, r13
0x1800df889  mov     rdx, [rsi+8]
0x1800df88d  mov     rcx, rdi
0x1800df890  mov     rax, [rax+10h]
0x1800df894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df899  mov     rax, [rdi]
0x1800df89c  mov     rdx, r12
0x1800df89f  mov     rcx, rdi
0x1800df8a2  mov     rax, [rax+30h]
0x1800df8a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df8ab  mov     ebx, eax
0x1800df8ad  test    eax, eax
0x1800df8af  jz      short loc_1800DF8B6
0x1800df8b1  cmp     eax, 7
0x1800df8b4  jnz     short loc_1800DF8EF
0x1800df8b6  mov     rax, [rdi]
0x1800df8b9  mov     rdx, r12
0x1800df8bc  mov     rcx, rdi
0x1800df8bf  mov     rax, [rax+28h]
0x1800df8c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df8c8  mov     ebx, eax
0x1800df8ca  test    eax, eax
0x1800df8cc  jz      short loc_1800DF8D3
0x1800df8ce  cmp     eax, 7
0x1800df8d1  jnz     short loc_1800DF8EF
0x1800df8d3  mov     rax, [rdi]
0x1800df8d6  mov     rdx, r12
0x1800df8d9  mov     rcx, rdi
0x1800df8dc  mov     rax, [rax+38h]
0x1800df8e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df8e5  jmp     loc_1800DF7B2
0x1800df8ea  mov     ebx, 4
0x1800df8ef  mov     rax, [rdi]
0x1800df8f2  mov     edx, 1
0x1800df8f7  mov     rcx, rdi
0x1800df8fa  mov     rax, [rax]
0x1800df8fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df902  test    r15, r15
0x1800df905  jz      short loc_1800DF914
0x1800df907  mov     edx, 10h
0x1800df90c  mov     rcx, r15; Block
0x1800df90f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800df914  mov     rcx, [rbp+TokenHandle]; hObject
0x1800df918  test    rcx, rcx
0x1800df91b  jz      short loc_1800DF923
0x1800df91d  call    cs:__imp_CloseHandle
0x1800df923  test    r14, r14
0x1800df926  jz      short loc_1800DF931
0x1800df928  mov     rcx, r14; pwk
0x1800df92b  call    cs:__imp_CloseThreadpoolWork
0x1800df931  mov     eax, ebx
0x1800df933  mov     rcx, [rbp+var_8]
0x1800df937  xor     rcx, rsp; StackCookie
0x1800df93a  call    __security_check_cookie
0x1800df93f  mov     rbx, [rsp+80h+arg_18]
0x1800df947  add     rsp, 80h
0x1800df94e  pop     r15
0x1800df950  pop     r14
0x1800df952  pop     r13
0x1800df954  pop     r12
0x1800df956  pop     rdi
0x1800df957  pop     rsi
0x1800df958  pop     rbp
0x1800df959  retn
```
