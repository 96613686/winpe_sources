# CSpWmiMethod<_SPACES_StorageReliabilityCounter_Reset>::RunMethod<CSpReliabilityCounter::Reset,6>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800faeb4`
- end: `0x1800fb202`
- name: `??$RunMethod@VReset@CSpReliabilityCounter@@$05@?$CSpWmiMethod@U_SPACES_StorageReliabilityCounter_Reset@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800fba80`

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
- `0x18005d58c`
- `0x1800d4ad8`
- `0x1800faeb4`
- `0x1800fb208`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fb080`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fb080`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800fb061`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800fb061`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800fb076`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800fb076`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800fb047`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800fb047`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800fb120`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800fb120`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800fb1d3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800fb1d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fb1c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fb1c5`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageReliabilityCounter_Reset>::RunMethod<CSpReliabilityCounter::Reset,6>(
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
  CSpReliabilityCounter::Reset *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpReliabilityCounter::Reset *)operator new(0x160u);
  v7 = CSpReliabilityCounter::Reset::Reset(v25);
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
      v25 = (CSpReliabilityCounter::Reset *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_180337D2D,
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
                v9 = CSpWmiMethod<_SPACES_StorageReliabilityCounter_Reset>::SetCreatedJob(v8, a3);
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
0x1800faeb4  mov     [rsp-38h+arg_18], rbx
0x1800faeb9  push    rbp
0x1800faeba  push    rsi
0x1800faebb  push    rdi
0x1800faebc  push    r12
0x1800faebe  push    r13
0x1800faec0  push    r14
0x1800faec2  push    r15
0x1800faec4  mov     rbp, rsp
0x1800faec7  sub     rsp, 80h
0x1800faece  mov     rax, cs:__security_cookie
0x1800faed5  xor     rax, rsp
0x1800faed8  mov     [rbp+var_8], rax
0x1800faedc  xor     eax, eax
0x1800faede  mov     rsi, rcx
0x1800faee1  xorps   xmm0, xmm0
0x1800faee4  mov     [rbp+var_10], eax
0x1800faee7  mov     ecx, 160h; Size
0x1800faeec  mov     [rbp+var_40], eax
0x1800faeef  movups  [rbp+var_20], xmm0
0x1800faef3  mov     [rbp+TokenHandle], rax
0x1800faef7  mov     r12, r8
0x1800faefa  mov     r13, rdx
0x1800faefd  xor     r14d, r14d
0x1800faf00  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800faf05  mov     rcx, rax; this
0x1800faf08  mov     [rbp+var_28], rax
0x1800faf0c  call    ??0Reset@CSpReliabilityCounter@@QEAA@XZ; CSpReliabilityCounter::Reset::Reset(void)
0x1800faf11  mov     rdi, rax
0x1800faf14  test    rax, rax
0x1800faf17  jnz     short loc_1800FAF21
0x1800faf19  lea     ebx, [rax+1Bh]
0x1800faf1c  jmp     loc_1800FB1BC
0x1800faf21  mov     rax, [rax]
0x1800faf24  mov     rdx, rsi
0x1800faf27  mov     rcx, rdi
0x1800faf2a  xor     r15d, r15d
0x1800faf2d  mov     rax, [rax+8]
0x1800faf31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800faf36  lea     rcx, [rbp+var_40]
0x1800faf3a  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800faf3f  mov     [rdi+1Ch], eax
0x1800faf42  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800faf46  mov     ecx, [rsi+14h]; unsigned int
0x1800faf49  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800faf4e  mov     eax, cs:dword_180397B68
0x1800faf54  cmp     eax, 5
0x1800faf57  jbe     short loc_1800FAFC7
0x1800faf59  mov     rdx, 400000000000h
0x1800faf63  lea     rcx, dword_180397B68
0x1800faf6a  call    _tlgKeywordOn
0x1800faf6f  test    al, al
0x1800faf71  jz      short loc_1800FAFC7
0x1800faf73  mov     eax, [rbp+var_40]
0x1800faf76  lea     rdx, byte_180337D2D
0x1800faf7d  xor     ecx, ecx
0x1800faf7f  cmp     [rdi+1Ch], eax
0x1800faf82  movzx   eax, word ptr [rbp+var_10]
0x1800faf86  mov     word ptr [rbp+var_40], ax
0x1800faf8a  setnz   cl
0x1800faf8d  mov     eax, [rsi+14h]
0x1800faf90  mov     [rbp+var_38], eax
0x1800faf93  lea     rax, [rbp+var_20]
0x1800faf97  mov     [rbp+var_28], rax
0x1800faf9b  lea     rax, [rbp+var_3C]
0x1800faf9f  mov     [rsp+80h+var_48], rax
0x1800fafa4  lea     rax, [rbp+var_40]
0x1800fafa8  mov     [rsp+80h+var_50], rax
0x1800fafad  lea     rax, [rbp+var_38]
0x1800fafb1  mov     [rsp+80h+var_58], rax
0x1800fafb6  lea     rax, [rbp+var_28]
0x1800fafba  mov     [rsp+80h+var_60], rax
0x1800fafbf  mov     [rbp+var_3C], ecx
0x1800fafc2  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800fafc7  mov     rcx, [rsi]
0x1800fafca  test    rcx, rcx
0x1800fafcd  jz      loc_1800FB192
0x1800fafd3  mov     rax, [rcx]
0x1800fafd6  test    rax, rax
0x1800fafd9  jz      loc_1800FB192
0x1800fafdf  mov     rax, [rax+18h]
0x1800fafe3  lea     r8, [rdi+20h]
0x1800fafe7  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800fafee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800faff3  mov     ebx, eax
0x1800faff5  test    eax, eax
0x1800faff7  jnz     loc_1800FB197
0x1800faffd  cmp     [rsi+10h], r14d
0x1800fb001  jz      loc_1800FB12B
0x1800fb007  lea     rbx, [rdi+148h]
0x1800fb00e  mov     rcx, rbx
0x1800fb011  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800fb016  mov     rcx, rbx; struct CSpJobMgr **
0x1800fb019  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800fb01e  test    eax, eax
0x1800fb020  jnz     short loc_1800FB02A
0x1800fb022  lea     ebx, [rax+1Ch]
0x1800fb025  jmp     loc_1800FB197
0x1800fb02a  mov     ecx, 10h; Size
0x1800fb02f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800fb034  xor     r8d, r8d; pcbe
0x1800fb037  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800fb03e  mov     rdx, rax; pv
0x1800fb041  mov     r15, rax
0x1800fb044  mov     [rax], rdi
0x1800fb047  call    cs:__imp_CreateThreadpoolWork
0x1800fb04d  mov     r14, rax
0x1800fb050  test    rax, rax
0x1800fb053  jnz     short loc_1800FB061
0x1800fb055  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800fb05a  mov     ebx, eax
0x1800fb05c  jmp     loc_1800FB197
0x1800fb061  call    cs:__imp_GetCurrentThread
0x1800fb067  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800fb06b  xor     r8d, r8d; OpenAsSelf
0x1800fb06e  mov     rcx, rax; ThreadHandle
0x1800fb071  mov     edx, 2000Ch; DesiredAccess
0x1800fb076  call    cs:__imp_OpenThreadToken
0x1800fb07c  test    eax, eax
0x1800fb07e  jnz     short loc_1800FB08D
0x1800fb080  call    cs:__imp_GetLastError
0x1800fb086  cmp     eax, 3F0h
0x1800fb08b  jnz     short loc_1800FB055
0x1800fb08d  mov     rax, [rbp+TokenHandle]
0x1800fb091  mov     r8, r13
0x1800fb094  mov     [r15+8], rax
0x1800fb098  mov     rcx, rdi
0x1800fb09b  mov     rax, [rdi]
0x1800fb09e  mov     rdx, [rsi+8]
0x1800fb0a2  mov     rax, [rax+18h]
0x1800fb0a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb0ab  mov     rax, [rdi]
0x1800fb0ae  mov     rdx, r12
0x1800fb0b1  mov     rcx, rdi
0x1800fb0b4  mov     rax, [rax+28h]
0x1800fb0b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb0bd  mov     ebx, eax
0x1800fb0bf  test    eax, eax
0x1800fb0c1  jz      short loc_1800FB0CC
0x1800fb0c3  cmp     eax, 7
0x1800fb0c6  jnz     loc_1800FB197
0x1800fb0cc  mov     rax, [rdi]
0x1800fb0cf  mov     rdx, r12
0x1800fb0d2  mov     rcx, rdi
0x1800fb0d5  mov     rax, [rax+38h]
0x1800fb0d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb0de  mov     ebx, eax
0x1800fb0e0  test    eax, eax
0x1800fb0e2  jnz     loc_1800FB197
0x1800fb0e8  mov     rax, [rdi+150h]
0x1800fb0ef  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800fb0f6  jnz     short loc_1800FB10C
0x1800fb0f8  mov     rax, [rdi+158h]
0x1800fb0ff  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800fb106  jz      loc_1800FB197
0x1800fb10c  mov     rdx, r12
0x1800fb10f  mov     rcx, rdi
0x1800fb112  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StorageReliabilityCounter_Reset@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StorageReliabilityCounter_Reset@@@Z; CSpWmiMethod<_SPACES_StorageReliabilityCounter_Reset>::SetCreatedJob(_SPACES_StorageReliabilityCounter_Reset *)
0x1800fb117  mov     ebx, eax
0x1800fb119  test    eax, eax
0x1800fb11b  jnz     short loc_1800FB197
0x1800fb11d  mov     rcx, r14; pwk
0x1800fb120  call    cs:__imp_SubmitThreadpoolWork
0x1800fb126  jmp     loc_1800FB1D9
0x1800fb12b  mov     rax, [rdi]
0x1800fb12e  mov     r8, r13
0x1800fb131  mov     rdx, [rsi+8]
0x1800fb135  mov     rcx, rdi
0x1800fb138  mov     rax, [rax+10h]
0x1800fb13c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb141  mov     rax, [rdi]
0x1800fb144  mov     rdx, r12
0x1800fb147  mov     rcx, rdi
0x1800fb14a  mov     rax, [rax+30h]
0x1800fb14e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb153  mov     ebx, eax
0x1800fb155  test    eax, eax
0x1800fb157  jz      short loc_1800FB15E
0x1800fb159  cmp     eax, 7
0x1800fb15c  jnz     short loc_1800FB197
0x1800fb15e  mov     rax, [rdi]
0x1800fb161  mov     rdx, r12
0x1800fb164  mov     rcx, rdi
0x1800fb167  mov     rax, [rax+28h]
0x1800fb16b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb170  mov     ebx, eax
0x1800fb172  test    eax, eax
0x1800fb174  jz      short loc_1800FB17B
0x1800fb176  cmp     eax, 7
0x1800fb179  jnz     short loc_1800FB197
0x1800fb17b  mov     rax, [rdi]
0x1800fb17e  mov     rdx, r12
0x1800fb181  mov     rcx, rdi
0x1800fb184  mov     rax, [rax+38h]
0x1800fb188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb18d  jmp     loc_1800FB05A
0x1800fb192  mov     ebx, 4
0x1800fb197  mov     rax, [rdi]
0x1800fb19a  mov     edx, 1
0x1800fb19f  mov     rcx, rdi
0x1800fb1a2  mov     rax, [rax]
0x1800fb1a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb1aa  test    r15, r15
0x1800fb1ad  jz      short loc_1800FB1BC
0x1800fb1af  mov     edx, 10h
0x1800fb1b4  mov     rcx, r15; Block
0x1800fb1b7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800fb1bc  mov     rcx, [rbp+TokenHandle]; hObject
0x1800fb1c0  test    rcx, rcx
0x1800fb1c3  jz      short loc_1800FB1CB
0x1800fb1c5  call    cs:__imp_CloseHandle
0x1800fb1cb  test    r14, r14
0x1800fb1ce  jz      short loc_1800FB1D9
0x1800fb1d0  mov     rcx, r14; pwk
0x1800fb1d3  call    cs:__imp_CloseThreadpoolWork
0x1800fb1d9  mov     eax, ebx
0x1800fb1db  mov     rcx, [rbp+var_8]
0x1800fb1df  xor     rcx, rsp; StackCookie
0x1800fb1e2  call    __security_check_cookie
0x1800fb1e7  mov     rbx, [rsp+80h+arg_18]
0x1800fb1ef  add     rsp, 80h
0x1800fb1f6  pop     r15
0x1800fb1f8  pop     r14
0x1800fb1fa  pop     r13
0x1800fb1fc  pop     r12
0x1800fb1fe  pop     rdi
0x1800fb1ff  pop     rsi
0x1800fb200  pop     rbp
0x1800fb201  retn
```
