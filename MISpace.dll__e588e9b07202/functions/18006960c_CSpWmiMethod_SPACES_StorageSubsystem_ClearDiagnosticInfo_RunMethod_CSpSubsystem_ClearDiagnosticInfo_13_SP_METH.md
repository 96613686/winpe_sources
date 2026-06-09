# CSpWmiMethod<_SPACES_StorageSubsystem_ClearDiagnosticInfo>::RunMethod<CSpSubsystem::ClearDiagnosticInfo,13>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18006960c`
- end: `0x18006995a`
- name: `??$RunMethod@VClearDiagnosticInfo@CSpSubsystem@@$0N@@?$CSpWmiMethod@U_SPACES_StorageSubsystem_ClearDiagnosticInfo@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800555c0`
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
- `0x18006960c`
- `0x18006bbc8`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800697d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800697d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800697b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800697b9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800697ce`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800697ce`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006979f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006979f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180069878`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180069878`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006992b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006992b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006991d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006991d`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageSubsystem_ClearDiagnosticInfo>::RunMethod<CSpSubsystem::ClearDiagnosticInfo,13>(
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
  CSpSubsystem::ClearDiagnosticInfo *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpSubsystem::ClearDiagnosticInfo *)operator new(0x160u);
  v7 = CSpSubsystem::ClearDiagnosticInfo::ClearDiagnosticInfo(v25);
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
      v25 = (CSpSubsystem::ClearDiagnosticInfo *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_18030F35D,
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
0x18006960c  mov     [rsp-38h+arg_18], rbx
0x180069611  push    rbp
0x180069612  push    rsi
0x180069613  push    rdi
0x180069614  push    r12
0x180069616  push    r13
0x180069618  push    r14
0x18006961a  push    r15
0x18006961c  mov     rbp, rsp
0x18006961f  sub     rsp, 80h
0x180069626  mov     rax, cs:__security_cookie
0x18006962d  xor     rax, rsp
0x180069630  mov     [rbp+var_8], rax
0x180069634  xor     eax, eax
0x180069636  mov     rsi, rcx
0x180069639  xorps   xmm0, xmm0
0x18006963c  mov     [rbp+var_10], eax
0x18006963f  mov     ecx, 160h; Size
0x180069644  mov     [rbp+var_40], eax
0x180069647  movups  [rbp+var_20], xmm0
0x18006964b  mov     [rbp+TokenHandle], rax
0x18006964f  mov     r12, r8
0x180069652  mov     r13, rdx
0x180069655  xor     r14d, r14d
0x180069658  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006965d  mov     rcx, rax; this
0x180069660  mov     [rbp+var_28], rax
0x180069664  call    ??0ClearDiagnosticInfo@CSpSubsystem@@QEAA@XZ; CSpSubsystem::ClearDiagnosticInfo::ClearDiagnosticInfo(void)
0x180069669  mov     rdi, rax
0x18006966c  test    rax, rax
0x18006966f  jnz     short loc_180069679
0x180069671  lea     ebx, [rax+1Bh]
0x180069674  jmp     loc_180069914
0x180069679  mov     rax, [rax]
0x18006967c  mov     rdx, rsi
0x18006967f  mov     rcx, rdi
0x180069682  xor     r15d, r15d
0x180069685  mov     rax, [rax+8]
0x180069689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006968e  lea     rcx, [rbp+var_40]
0x180069692  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x180069697  mov     [rdi+1Ch], eax
0x18006969a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18006969e  mov     ecx, [rsi+14h]; unsigned int
0x1800696a1  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800696a6  mov     eax, cs:dword_180397B68
0x1800696ac  cmp     eax, 5
0x1800696af  jbe     short loc_18006971F
0x1800696b1  mov     rdx, 400000000000h
0x1800696bb  lea     rcx, dword_180397B68
0x1800696c2  call    _tlgKeywordOn
0x1800696c7  test    al, al
0x1800696c9  jz      short loc_18006971F
0x1800696cb  mov     eax, [rbp+var_40]
0x1800696ce  lea     rdx, byte_18030F35D
0x1800696d5  xor     ecx, ecx
0x1800696d7  cmp     [rdi+1Ch], eax
0x1800696da  movzx   eax, word ptr [rbp+var_10]
0x1800696de  mov     word ptr [rbp+var_40], ax
0x1800696e2  setnz   cl
0x1800696e5  mov     eax, [rsi+14h]
0x1800696e8  mov     [rbp+var_38], eax
0x1800696eb  lea     rax, [rbp+var_20]
0x1800696ef  mov     [rbp+var_28], rax
0x1800696f3  lea     rax, [rbp+var_3C]
0x1800696f7  mov     [rsp+80h+var_48], rax
0x1800696fc  lea     rax, [rbp+var_40]
0x180069700  mov     [rsp+80h+var_50], rax
0x180069705  lea     rax, [rbp+var_38]
0x180069709  mov     [rsp+80h+var_58], rax
0x18006970e  lea     rax, [rbp+var_28]
0x180069712  mov     [rsp+80h+var_60], rax
0x180069717  mov     [rbp+var_3C], ecx
0x18006971a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18006971f  mov     rcx, [rsi]
0x180069722  test    rcx, rcx
0x180069725  jz      loc_1800698EA
0x18006972b  mov     rax, [rcx]
0x18006972e  test    rax, rax
0x180069731  jz      loc_1800698EA
0x180069737  mov     rax, [rax+18h]
0x18006973b  lea     r8, [rdi+20h]
0x18006973f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x180069746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006974b  mov     ebx, eax
0x18006974d  test    eax, eax
0x18006974f  jnz     loc_1800698EF
0x180069755  cmp     [rsi+10h], r14d
0x180069759  jz      loc_180069883
0x18006975f  lea     rbx, [rdi+148h]
0x180069766  mov     rcx, rbx
0x180069769  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18006976e  mov     rcx, rbx; struct CSpJobMgr **
0x180069771  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x180069776  test    eax, eax
0x180069778  jnz     short loc_180069782
0x18006977a  lea     ebx, [rax+1Ch]
0x18006977d  jmp     loc_1800698EF
0x180069782  mov     ecx, 10h; Size
0x180069787  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006978c  xor     r8d, r8d; pcbe
0x18006978f  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180069796  mov     rdx, rax; pv
0x180069799  mov     r15, rax
0x18006979c  mov     [rax], rdi
0x18006979f  call    cs:__imp_CreateThreadpoolWork
0x1800697a5  mov     r14, rax
0x1800697a8  test    rax, rax
0x1800697ab  jnz     short loc_1800697B9
0x1800697ad  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800697b2  mov     ebx, eax
0x1800697b4  jmp     loc_1800698EF
0x1800697b9  call    cs:__imp_GetCurrentThread
0x1800697bf  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800697c3  xor     r8d, r8d; OpenAsSelf
0x1800697c6  mov     rcx, rax; ThreadHandle
0x1800697c9  mov     edx, 2000Ch; DesiredAccess
0x1800697ce  call    cs:__imp_OpenThreadToken
0x1800697d4  test    eax, eax
0x1800697d6  jnz     short loc_1800697E5
0x1800697d8  call    cs:__imp_GetLastError
0x1800697de  cmp     eax, 3F0h
0x1800697e3  jnz     short loc_1800697AD
0x1800697e5  mov     rax, [rbp+TokenHandle]
0x1800697e9  mov     r8, r13
0x1800697ec  mov     [r15+8], rax
0x1800697f0  mov     rcx, rdi
0x1800697f3  mov     rax, [rdi]
0x1800697f6  mov     rdx, [rsi+8]
0x1800697fa  mov     rax, [rax+18h]
0x1800697fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069803  mov     rax, [rdi]
0x180069806  mov     rdx, r12
0x180069809  mov     rcx, rdi
0x18006980c  mov     rax, [rax+28h]
0x180069810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069815  mov     ebx, eax
0x180069817  test    eax, eax
0x180069819  jz      short loc_180069824
0x18006981b  cmp     eax, 7
0x18006981e  jnz     loc_1800698EF
0x180069824  mov     rax, [rdi]
0x180069827  mov     rdx, r12
0x18006982a  mov     rcx, rdi
0x18006982d  mov     rax, [rax+38h]
0x180069831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069836  mov     ebx, eax
0x180069838  test    eax, eax
0x18006983a  jnz     loc_1800698EF
0x180069840  mov     rax, [rdi+150h]
0x180069847  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18006984e  jnz     short loc_180069864
0x180069850  mov     rax, [rdi+158h]
0x180069857  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18006985e  jz      loc_1800698EF
0x180069864  mov     rdx, r12
0x180069867  mov     rcx, rdi
0x18006986a  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18006986f  mov     ebx, eax
0x180069871  test    eax, eax
0x180069873  jnz     short loc_1800698EF
0x180069875  mov     rcx, r14; pwk
0x180069878  call    cs:__imp_SubmitThreadpoolWork
0x18006987e  jmp     loc_180069931
0x180069883  mov     rax, [rdi]
0x180069886  mov     r8, r13
0x180069889  mov     rdx, [rsi+8]
0x18006988d  mov     rcx, rdi
0x180069890  mov     rax, [rax+10h]
0x180069894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069899  mov     rax, [rdi]
0x18006989c  mov     rdx, r12
0x18006989f  mov     rcx, rdi
0x1800698a2  mov     rax, [rax+30h]
0x1800698a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800698ab  mov     ebx, eax
0x1800698ad  test    eax, eax
0x1800698af  jz      short loc_1800698B6
0x1800698b1  cmp     eax, 7
0x1800698b4  jnz     short loc_1800698EF
0x1800698b6  mov     rax, [rdi]
0x1800698b9  mov     rdx, r12
0x1800698bc  mov     rcx, rdi
0x1800698bf  mov     rax, [rax+28h]
0x1800698c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800698c8  mov     ebx, eax
0x1800698ca  test    eax, eax
0x1800698cc  jz      short loc_1800698D3
0x1800698ce  cmp     eax, 7
0x1800698d1  jnz     short loc_1800698EF
0x1800698d3  mov     rax, [rdi]
0x1800698d6  mov     rdx, r12
0x1800698d9  mov     rcx, rdi
0x1800698dc  mov     rax, [rax+38h]
0x1800698e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800698e5  jmp     loc_1800697B2
0x1800698ea  mov     ebx, 4
0x1800698ef  mov     rax, [rdi]
0x1800698f2  mov     edx, 1
0x1800698f7  mov     rcx, rdi
0x1800698fa  mov     rax, [rax]
0x1800698fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069902  test    r15, r15
0x180069905  jz      short loc_180069914
0x180069907  mov     edx, 10h
0x18006990c  mov     rcx, r15; Block
0x18006990f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180069914  mov     rcx, [rbp+TokenHandle]; hObject
0x180069918  test    rcx, rcx
0x18006991b  jz      short loc_180069923
0x18006991d  call    cs:__imp_CloseHandle
0x180069923  test    r14, r14
0x180069926  jz      short loc_180069931
0x180069928  mov     rcx, r14; pwk
0x18006992b  call    cs:__imp_CloseThreadpoolWork
0x180069931  mov     eax, ebx
0x180069933  mov     rcx, [rbp+var_8]
0x180069937  xor     rcx, rsp; StackCookie
0x18006993a  call    __security_check_cookie
0x18006993f  mov     rbx, [rsp+80h+arg_18]
0x180069947  add     rsp, 80h
0x18006994e  pop     r15
0x180069950  pop     r14
0x180069952  pop     r13
0x180069954  pop     r12
0x180069956  pop     rdi
0x180069957  pop     rsi
0x180069958  pop     rbp
0x180069959  retn
```
