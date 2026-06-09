# CSpWmiMethod<_SPACES_VirtualDisk_Attach>::RunMethod<CSpVirtualDisk::Attach,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800dd818`
- end: `0x1800ddb66`
- name: `??$RunMethod@VAttach@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_Attach@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800dd818`
- `0x1800e0788`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd9e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd9e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dd9c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dd9c5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dd9da`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dd9da`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800dd9ab`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800dd9ab`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800dda84`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800dda84`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ddb37`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ddb37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ddb29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ddb29`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_Attach>::RunMethod<CSpVirtualDisk::Attach,16>(
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
  CSpVirtualDisk::Attach *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::Attach *)operator new(0x160u);
  v7 = CSpVirtualDisk::Attach::Attach(v25);
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
      v25 = (CSpVirtualDisk::Attach *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)word_180332872,
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
0x1800dd818  mov     [rsp-38h+arg_18], rbx
0x1800dd81d  push    rbp
0x1800dd81e  push    rsi
0x1800dd81f  push    rdi
0x1800dd820  push    r12
0x1800dd822  push    r13
0x1800dd824  push    r14
0x1800dd826  push    r15
0x1800dd828  mov     rbp, rsp
0x1800dd82b  sub     rsp, 80h
0x1800dd832  mov     rax, cs:__security_cookie
0x1800dd839  xor     rax, rsp
0x1800dd83c  mov     [rbp+var_8], rax
0x1800dd840  xor     eax, eax
0x1800dd842  mov     rsi, rcx
0x1800dd845  xorps   xmm0, xmm0
0x1800dd848  mov     [rbp+var_10], eax
0x1800dd84b  mov     ecx, 160h; Size
0x1800dd850  mov     [rbp+var_40], eax
0x1800dd853  movups  [rbp+var_20], xmm0
0x1800dd857  mov     [rbp+TokenHandle], rax
0x1800dd85b  mov     r12, r8
0x1800dd85e  mov     r13, rdx
0x1800dd861  xor     r14d, r14d
0x1800dd864  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800dd869  mov     rcx, rax; this
0x1800dd86c  mov     [rbp+var_28], rax
0x1800dd870  call    ??0Attach@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::Attach::Attach(void)
0x1800dd875  mov     rdi, rax
0x1800dd878  test    rax, rax
0x1800dd87b  jnz     short loc_1800DD885
0x1800dd87d  lea     ebx, [rax+1Bh]
0x1800dd880  jmp     loc_1800DDB20
0x1800dd885  mov     rax, [rax]
0x1800dd888  mov     rdx, rsi
0x1800dd88b  mov     rcx, rdi
0x1800dd88e  xor     r15d, r15d
0x1800dd891  mov     rax, [rax+8]
0x1800dd895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd89a  lea     rcx, [rbp+var_40]
0x1800dd89e  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800dd8a3  mov     [rdi+1Ch], eax
0x1800dd8a6  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800dd8aa  mov     ecx, [rsi+14h]; unsigned int
0x1800dd8ad  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800dd8b2  mov     eax, cs:dword_180397B68
0x1800dd8b8  cmp     eax, 5
0x1800dd8bb  jbe     short loc_1800DD92B
0x1800dd8bd  mov     rdx, 400000000000h
0x1800dd8c7  lea     rcx, dword_180397B68
0x1800dd8ce  call    _tlgKeywordOn
0x1800dd8d3  test    al, al
0x1800dd8d5  jz      short loc_1800DD92B
0x1800dd8d7  mov     eax, [rbp+var_40]
0x1800dd8da  lea     rdx, word_180332872
0x1800dd8e1  xor     ecx, ecx
0x1800dd8e3  cmp     [rdi+1Ch], eax
0x1800dd8e6  movzx   eax, word ptr [rbp+var_10]
0x1800dd8ea  mov     word ptr [rbp+var_40], ax
0x1800dd8ee  setnz   cl
0x1800dd8f1  mov     eax, [rsi+14h]
0x1800dd8f4  mov     [rbp+var_38], eax
0x1800dd8f7  lea     rax, [rbp+var_20]
0x1800dd8fb  mov     [rbp+var_28], rax
0x1800dd8ff  lea     rax, [rbp+var_3C]
0x1800dd903  mov     [rsp+80h+var_48], rax
0x1800dd908  lea     rax, [rbp+var_40]
0x1800dd90c  mov     [rsp+80h+var_50], rax
0x1800dd911  lea     rax, [rbp+var_38]
0x1800dd915  mov     [rsp+80h+var_58], rax
0x1800dd91a  lea     rax, [rbp+var_28]
0x1800dd91e  mov     [rsp+80h+var_60], rax
0x1800dd923  mov     [rbp+var_3C], ecx
0x1800dd926  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800dd92b  mov     rcx, [rsi]
0x1800dd92e  test    rcx, rcx
0x1800dd931  jz      loc_1800DDAF6
0x1800dd937  mov     rax, [rcx]
0x1800dd93a  test    rax, rax
0x1800dd93d  jz      loc_1800DDAF6
0x1800dd943  mov     rax, [rax+18h]
0x1800dd947  lea     r8, [rdi+20h]
0x1800dd94b  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800dd952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd957  mov     ebx, eax
0x1800dd959  test    eax, eax
0x1800dd95b  jnz     loc_1800DDAFB
0x1800dd961  cmp     [rsi+10h], r14d
0x1800dd965  jz      loc_1800DDA8F
0x1800dd96b  lea     rbx, [rdi+148h]
0x1800dd972  mov     rcx, rbx
0x1800dd975  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800dd97a  mov     rcx, rbx; struct CSpJobMgr **
0x1800dd97d  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800dd982  test    eax, eax
0x1800dd984  jnz     short loc_1800DD98E
0x1800dd986  lea     ebx, [rax+1Ch]
0x1800dd989  jmp     loc_1800DDAFB
0x1800dd98e  mov     ecx, 10h; Size
0x1800dd993  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800dd998  xor     r8d, r8d; pcbe
0x1800dd99b  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800dd9a2  mov     rdx, rax; pv
0x1800dd9a5  mov     r15, rax
0x1800dd9a8  mov     [rax], rdi
0x1800dd9ab  call    cs:__imp_CreateThreadpoolWork
0x1800dd9b1  mov     r14, rax
0x1800dd9b4  test    rax, rax
0x1800dd9b7  jnz     short loc_1800DD9C5
0x1800dd9b9  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800dd9be  mov     ebx, eax
0x1800dd9c0  jmp     loc_1800DDAFB
0x1800dd9c5  call    cs:__imp_GetCurrentThread
0x1800dd9cb  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800dd9cf  xor     r8d, r8d; OpenAsSelf
0x1800dd9d2  mov     rcx, rax; ThreadHandle
0x1800dd9d5  mov     edx, 2000Ch; DesiredAccess
0x1800dd9da  call    cs:__imp_OpenThreadToken
0x1800dd9e0  test    eax, eax
0x1800dd9e2  jnz     short loc_1800DD9F1
0x1800dd9e4  call    cs:__imp_GetLastError
0x1800dd9ea  cmp     eax, 3F0h
0x1800dd9ef  jnz     short loc_1800DD9B9
0x1800dd9f1  mov     rax, [rbp+TokenHandle]
0x1800dd9f5  mov     r8, r13
0x1800dd9f8  mov     [r15+8], rax
0x1800dd9fc  mov     rcx, rdi
0x1800dd9ff  mov     rax, [rdi]
0x1800dda02  mov     rdx, [rsi+8]
0x1800dda06  mov     rax, [rax+18h]
0x1800dda0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dda0f  mov     rax, [rdi]
0x1800dda12  mov     rdx, r12
0x1800dda15  mov     rcx, rdi
0x1800dda18  mov     rax, [rax+28h]
0x1800dda1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dda21  mov     ebx, eax
0x1800dda23  test    eax, eax
0x1800dda25  jz      short loc_1800DDA30
0x1800dda27  cmp     eax, 7
0x1800dda2a  jnz     loc_1800DDAFB
0x1800dda30  mov     rax, [rdi]
0x1800dda33  mov     rdx, r12
0x1800dda36  mov     rcx, rdi
0x1800dda39  mov     rax, [rax+38h]
0x1800dda3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dda42  mov     ebx, eax
0x1800dda44  test    eax, eax
0x1800dda46  jnz     loc_1800DDAFB
0x1800dda4c  mov     rax, [rdi+150h]
0x1800dda53  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800dda5a  jnz     short loc_1800DDA70
0x1800dda5c  mov     rax, [rdi+158h]
0x1800dda63  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800dda6a  jz      loc_1800DDAFB
0x1800dda70  mov     rdx, r12
0x1800dda73  mov     rcx, rdi
0x1800dda76  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800dda7b  mov     ebx, eax
0x1800dda7d  test    eax, eax
0x1800dda7f  jnz     short loc_1800DDAFB
0x1800dda81  mov     rcx, r14; pwk
0x1800dda84  call    cs:__imp_SubmitThreadpoolWork
0x1800dda8a  jmp     loc_1800DDB3D
0x1800dda8f  mov     rax, [rdi]
0x1800dda92  mov     r8, r13
0x1800dda95  mov     rdx, [rsi+8]
0x1800dda99  mov     rcx, rdi
0x1800dda9c  mov     rax, [rax+10h]
0x1800ddaa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddaa5  mov     rax, [rdi]
0x1800ddaa8  mov     rdx, r12
0x1800ddaab  mov     rcx, rdi
0x1800ddaae  mov     rax, [rax+30h]
0x1800ddab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddab7  mov     ebx, eax
0x1800ddab9  test    eax, eax
0x1800ddabb  jz      short loc_1800DDAC2
0x1800ddabd  cmp     eax, 7
0x1800ddac0  jnz     short loc_1800DDAFB
0x1800ddac2  mov     rax, [rdi]
0x1800ddac5  mov     rdx, r12
0x1800ddac8  mov     rcx, rdi
0x1800ddacb  mov     rax, [rax+28h]
0x1800ddacf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddad4  mov     ebx, eax
0x1800ddad6  test    eax, eax
0x1800ddad8  jz      short loc_1800DDADF
0x1800ddada  cmp     eax, 7
0x1800ddadd  jnz     short loc_1800DDAFB
0x1800ddadf  mov     rax, [rdi]
0x1800ddae2  mov     rdx, r12
0x1800ddae5  mov     rcx, rdi
0x1800ddae8  mov     rax, [rax+38h]
0x1800ddaec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddaf1  jmp     loc_1800DD9BE
0x1800ddaf6  mov     ebx, 4
0x1800ddafb  mov     rax, [rdi]
0x1800ddafe  mov     edx, 1
0x1800ddb03  mov     rcx, rdi
0x1800ddb06  mov     rax, [rax]
0x1800ddb09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddb0e  test    r15, r15
0x1800ddb11  jz      short loc_1800DDB20
0x1800ddb13  mov     edx, 10h
0x1800ddb18  mov     rcx, r15; Block
0x1800ddb1b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ddb20  mov     rcx, [rbp+TokenHandle]; hObject
0x1800ddb24  test    rcx, rcx
0x1800ddb27  jz      short loc_1800DDB2F
0x1800ddb29  call    cs:__imp_CloseHandle
0x1800ddb2f  test    r14, r14
0x1800ddb32  jz      short loc_1800DDB3D
0x1800ddb34  mov     rcx, r14; pwk
0x1800ddb37  call    cs:__imp_CloseThreadpoolWork
0x1800ddb3d  mov     eax, ebx
0x1800ddb3f  mov     rcx, [rbp+var_8]
0x1800ddb43  xor     rcx, rsp; StackCookie
0x1800ddb46  call    __security_check_cookie
0x1800ddb4b  mov     rbx, [rsp+80h+arg_18]
0x1800ddb53  add     rsp, 80h
0x1800ddb5a  pop     r15
0x1800ddb5c  pop     r14
0x1800ddb5e  pop     r13
0x1800ddb60  pop     r12
0x1800ddb62  pop     rdi
0x1800ddb63  pop     rsi
0x1800ddb64  pop     rbp
0x1800ddb65  retn
```
