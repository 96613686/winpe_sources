# CSpWmiMethod<_SPACES_StorageSubsystem_GetDiagnosticInfo>::RunMethod<CSpSubsystem::GetDiagnosticInfo,13>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18006aa04`
- end: `0x18006ad52`
- name: `??$RunMethod@VGetDiagnosticInfo@CSpSubsystem@@$0N@@?$CSpWmiMethod@U_SPACES_StorageSubsystem_GetDiagnosticInfo@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x18006aa04`
- `0x18006bf30`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006abd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006abd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006abb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006abb1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006abc6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006abc6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006ab97`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006ab97`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006ac70`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006ac70`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006ad23`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006ad23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ad15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ad15`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageSubsystem_GetDiagnosticInfo>::RunMethod<CSpSubsystem::GetDiagnosticInfo,13>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 DiagnosticInfo; // rax
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
  CSpSubsystem::GetDiagnosticInfo *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpSubsystem::GetDiagnosticInfo *)operator new(0x160u);
  DiagnosticInfo = CSpSubsystem::GetDiagnosticInfo::GetDiagnosticInfo(v25);
  v8 = DiagnosticInfo;
  if ( DiagnosticInfo )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)DiagnosticInfo + 8LL))(DiagnosticInfo, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpSubsystem::GetDiagnosticInfo *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&byte_18031146F,
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
0x18006aa04  mov     [rsp-38h+arg_18], rbx
0x18006aa09  push    rbp
0x18006aa0a  push    rsi
0x18006aa0b  push    rdi
0x18006aa0c  push    r12
0x18006aa0e  push    r13
0x18006aa10  push    r14
0x18006aa12  push    r15
0x18006aa14  mov     rbp, rsp
0x18006aa17  sub     rsp, 80h
0x18006aa1e  mov     rax, cs:__security_cookie
0x18006aa25  xor     rax, rsp
0x18006aa28  mov     [rbp+var_8], rax
0x18006aa2c  xor     eax, eax
0x18006aa2e  mov     rsi, rcx
0x18006aa31  xorps   xmm0, xmm0
0x18006aa34  mov     [rbp+var_10], eax
0x18006aa37  mov     ecx, 160h; Size
0x18006aa3c  mov     [rbp+var_40], eax
0x18006aa3f  movups  [rbp+var_20], xmm0
0x18006aa43  mov     [rbp+TokenHandle], rax
0x18006aa47  mov     r12, r8
0x18006aa4a  mov     r13, rdx
0x18006aa4d  xor     r14d, r14d
0x18006aa50  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006aa55  mov     rcx, rax; this
0x18006aa58  mov     [rbp+var_28], rax
0x18006aa5c  call    ??0GetDiagnosticInfo@CSpSubsystem@@QEAA@XZ; CSpSubsystem::GetDiagnosticInfo::GetDiagnosticInfo(void)
0x18006aa61  mov     rdi, rax
0x18006aa64  test    rax, rax
0x18006aa67  jnz     short loc_18006AA71
0x18006aa69  lea     ebx, [rax+1Bh]
0x18006aa6c  jmp     loc_18006AD0C
0x18006aa71  mov     rax, [rax]
0x18006aa74  mov     rdx, rsi
0x18006aa77  mov     rcx, rdi
0x18006aa7a  xor     r15d, r15d
0x18006aa7d  mov     rax, [rax+8]
0x18006aa81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aa86  lea     rcx, [rbp+var_40]
0x18006aa8a  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18006aa8f  mov     [rdi+1Ch], eax
0x18006aa92  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18006aa96  mov     ecx, [rsi+14h]; unsigned int
0x18006aa99  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18006aa9e  mov     eax, cs:dword_180397B68
0x18006aaa4  cmp     eax, 5
0x18006aaa7  jbe     short loc_18006AB17
0x18006aaa9  mov     rdx, 400000000000h
0x18006aab3  lea     rcx, dword_180397B68
0x18006aaba  call    _tlgKeywordOn
0x18006aabf  test    al, al
0x18006aac1  jz      short loc_18006AB17
0x18006aac3  mov     eax, [rbp+var_40]
0x18006aac6  lea     rdx, byte_18031146F
0x18006aacd  xor     ecx, ecx
0x18006aacf  cmp     [rdi+1Ch], eax
0x18006aad2  movzx   eax, word ptr [rbp+var_10]
0x18006aad6  mov     word ptr [rbp+var_40], ax
0x18006aada  setnz   cl
0x18006aadd  mov     eax, [rsi+14h]
0x18006aae0  mov     [rbp+var_38], eax
0x18006aae3  lea     rax, [rbp+var_20]
0x18006aae7  mov     [rbp+var_28], rax
0x18006aaeb  lea     rax, [rbp+var_3C]
0x18006aaef  mov     [rsp+80h+var_48], rax
0x18006aaf4  lea     rax, [rbp+var_40]
0x18006aaf8  mov     [rsp+80h+var_50], rax
0x18006aafd  lea     rax, [rbp+var_38]
0x18006ab01  mov     [rsp+80h+var_58], rax
0x18006ab06  lea     rax, [rbp+var_28]
0x18006ab0a  mov     [rsp+80h+var_60], rax
0x18006ab0f  mov     [rbp+var_3C], ecx
0x18006ab12  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18006ab17  mov     rcx, [rsi]
0x18006ab1a  test    rcx, rcx
0x18006ab1d  jz      loc_18006ACE2
0x18006ab23  mov     rax, [rcx]
0x18006ab26  test    rax, rax
0x18006ab29  jz      loc_18006ACE2
0x18006ab2f  mov     rax, [rax+18h]
0x18006ab33  lea     r8, [rdi+20h]
0x18006ab37  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18006ab3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ab43  mov     ebx, eax
0x18006ab45  test    eax, eax
0x18006ab47  jnz     loc_18006ACE7
0x18006ab4d  cmp     [rsi+10h], r14d
0x18006ab51  jz      loc_18006AC7B
0x18006ab57  lea     rbx, [rdi+148h]
0x18006ab5e  mov     rcx, rbx
0x18006ab61  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18006ab66  mov     rcx, rbx; struct CSpJobMgr **
0x18006ab69  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18006ab6e  test    eax, eax
0x18006ab70  jnz     short loc_18006AB7A
0x18006ab72  lea     ebx, [rax+1Ch]
0x18006ab75  jmp     loc_18006ACE7
0x18006ab7a  mov     ecx, 10h; Size
0x18006ab7f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006ab84  xor     r8d, r8d; pcbe
0x18006ab87  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18006ab8e  mov     rdx, rax; pv
0x18006ab91  mov     r15, rax
0x18006ab94  mov     [rax], rdi
0x18006ab97  call    cs:__imp_CreateThreadpoolWork
0x18006ab9d  mov     r14, rax
0x18006aba0  test    rax, rax
0x18006aba3  jnz     short loc_18006ABB1
0x18006aba5  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18006abaa  mov     ebx, eax
0x18006abac  jmp     loc_18006ACE7
0x18006abb1  call    cs:__imp_GetCurrentThread
0x18006abb7  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18006abbb  xor     r8d, r8d; OpenAsSelf
0x18006abbe  mov     rcx, rax; ThreadHandle
0x18006abc1  mov     edx, 2000Ch; DesiredAccess
0x18006abc6  call    cs:__imp_OpenThreadToken
0x18006abcc  test    eax, eax
0x18006abce  jnz     short loc_18006ABDD
0x18006abd0  call    cs:__imp_GetLastError
0x18006abd6  cmp     eax, 3F0h
0x18006abdb  jnz     short loc_18006ABA5
0x18006abdd  mov     rax, [rbp+TokenHandle]
0x18006abe1  mov     r8, r13
0x18006abe4  mov     [r15+8], rax
0x18006abe8  mov     rcx, rdi
0x18006abeb  mov     rax, [rdi]
0x18006abee  mov     rdx, [rsi+8]
0x18006abf2  mov     rax, [rax+18h]
0x18006abf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006abfb  mov     rax, [rdi]
0x18006abfe  mov     rdx, r12
0x18006ac01  mov     rcx, rdi
0x18006ac04  mov     rax, [rax+28h]
0x18006ac08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac0d  mov     ebx, eax
0x18006ac0f  test    eax, eax
0x18006ac11  jz      short loc_18006AC1C
0x18006ac13  cmp     eax, 7
0x18006ac16  jnz     loc_18006ACE7
0x18006ac1c  mov     rax, [rdi]
0x18006ac1f  mov     rdx, r12
0x18006ac22  mov     rcx, rdi
0x18006ac25  mov     rax, [rax+38h]
0x18006ac29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac2e  mov     ebx, eax
0x18006ac30  test    eax, eax
0x18006ac32  jnz     loc_18006ACE7
0x18006ac38  mov     rax, [rdi+150h]
0x18006ac3f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18006ac46  jnz     short loc_18006AC5C
0x18006ac48  mov     rax, [rdi+158h]
0x18006ac4f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18006ac56  jz      loc_18006ACE7
0x18006ac5c  mov     rdx, r12
0x18006ac5f  mov     rcx, rdi
0x18006ac62  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18006ac67  mov     ebx, eax
0x18006ac69  test    eax, eax
0x18006ac6b  jnz     short loc_18006ACE7
0x18006ac6d  mov     rcx, r14; pwk
0x18006ac70  call    cs:__imp_SubmitThreadpoolWork
0x18006ac76  jmp     loc_18006AD29
0x18006ac7b  mov     rax, [rdi]
0x18006ac7e  mov     r8, r13
0x18006ac81  mov     rdx, [rsi+8]
0x18006ac85  mov     rcx, rdi
0x18006ac88  mov     rax, [rax+10h]
0x18006ac8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac91  mov     rax, [rdi]
0x18006ac94  mov     rdx, r12
0x18006ac97  mov     rcx, rdi
0x18006ac9a  mov     rax, [rax+30h]
0x18006ac9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aca3  mov     ebx, eax
0x18006aca5  test    eax, eax
0x18006aca7  jz      short loc_18006ACAE
0x18006aca9  cmp     eax, 7
0x18006acac  jnz     short loc_18006ACE7
0x18006acae  mov     rax, [rdi]
0x18006acb1  mov     rdx, r12
0x18006acb4  mov     rcx, rdi
0x18006acb7  mov     rax, [rax+28h]
0x18006acbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006acc0  mov     ebx, eax
0x18006acc2  test    eax, eax
0x18006acc4  jz      short loc_18006ACCB
0x18006acc6  cmp     eax, 7
0x18006acc9  jnz     short loc_18006ACE7
0x18006accb  mov     rax, [rdi]
0x18006acce  mov     rdx, r12
0x18006acd1  mov     rcx, rdi
0x18006acd4  mov     rax, [rax+38h]
0x18006acd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006acdd  jmp     loc_18006ABAA
0x18006ace2  mov     ebx, 4
0x18006ace7  mov     rax, [rdi]
0x18006acea  mov     edx, 1
0x18006acef  mov     rcx, rdi
0x18006acf2  mov     rax, [rax]
0x18006acf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006acfa  test    r15, r15
0x18006acfd  jz      short loc_18006AD0C
0x18006acff  mov     edx, 10h
0x18006ad04  mov     rcx, r15; Block
0x18006ad07  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006ad0c  mov     rcx, [rbp+TokenHandle]; hObject
0x18006ad10  test    rcx, rcx
0x18006ad13  jz      short loc_18006AD1B
0x18006ad15  call    cs:__imp_CloseHandle
0x18006ad1b  test    r14, r14
0x18006ad1e  jz      short loc_18006AD29
0x18006ad20  mov     rcx, r14; pwk
0x18006ad23  call    cs:__imp_CloseThreadpoolWork
0x18006ad29  mov     eax, ebx
0x18006ad2b  mov     rcx, [rbp+var_8]
0x18006ad2f  xor     rcx, rsp; StackCookie
0x18006ad32  call    __security_check_cookie
0x18006ad37  mov     rbx, [rsp+80h+arg_18]
0x18006ad3f  add     rsp, 80h
0x18006ad46  pop     r15
0x18006ad48  pop     r14
0x18006ad4a  pop     r13
0x18006ad4c  pop     r12
0x18006ad4e  pop     rdi
0x18006ad4f  pop     rsi
0x18006ad50  pop     rbp
0x18006ad51  retn
```
