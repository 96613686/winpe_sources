# CSpWmiMethod<_SPACES_StorageTier_GetPhysicalExtent>::RunMethod<CSpStorageTier::GetPhysicalExtent,12>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800fec44`
- end: `0x1800fef92`
- name: `??$RunMethod@VGetPhysicalExtent@CSpStorageTier@@$0M@@?$CSpWmiMethod@U_SPACES_StorageTier_GetPhysicalExtent@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180102030`

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
- `0x1800fec44`
- `0x18010046c`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fee10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fee10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800fedf1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800fedf1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800fee06`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800fee06`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800fedd7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800fedd7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800feeb0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800feeb0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800fef63`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800fef63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fef55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fef55`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageTier_GetPhysicalExtent>::RunMethod<CSpStorageTier::GetPhysicalExtent,12>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 PhysicalExtent; // rax
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
  CSpStorageTier::GetPhysicalExtent *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageTier::GetPhysicalExtent *)operator new(0x170u);
  PhysicalExtent = CSpStorageTier::GetPhysicalExtent::GetPhysicalExtent(v25);
  v8 = PhysicalExtent;
  if ( PhysicalExtent )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)PhysicalExtent + 8LL))(PhysicalExtent, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStorageTier::GetPhysicalExtent *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&dword_18033896C,
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
0x1800fec44  mov     [rsp-38h+arg_18], rbx
0x1800fec49  push    rbp
0x1800fec4a  push    rsi
0x1800fec4b  push    rdi
0x1800fec4c  push    r12
0x1800fec4e  push    r13
0x1800fec50  push    r14
0x1800fec52  push    r15
0x1800fec54  mov     rbp, rsp
0x1800fec57  sub     rsp, 80h
0x1800fec5e  mov     rax, cs:__security_cookie
0x1800fec65  xor     rax, rsp
0x1800fec68  mov     [rbp+var_8], rax
0x1800fec6c  xor     eax, eax
0x1800fec6e  mov     rsi, rcx
0x1800fec71  xorps   xmm0, xmm0
0x1800fec74  mov     [rbp+var_10], eax
0x1800fec77  mov     ecx, 170h; Size
0x1800fec7c  mov     [rbp+var_40], eax
0x1800fec7f  movups  [rbp+var_20], xmm0
0x1800fec83  mov     [rbp+TokenHandle], rax
0x1800fec87  mov     r12, r8
0x1800fec8a  mov     r13, rdx
0x1800fec8d  xor     r14d, r14d
0x1800fec90  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800fec95  mov     rcx, rax; this
0x1800fec98  mov     [rbp+var_28], rax
0x1800fec9c  call    ??0GetPhysicalExtent@CSpStorageTier@@QEAA@XZ; CSpStorageTier::GetPhysicalExtent::GetPhysicalExtent(void)
0x1800feca1  mov     rdi, rax
0x1800feca4  test    rax, rax
0x1800feca7  jnz     short loc_1800FECB1
0x1800feca9  lea     ebx, [rax+1Bh]
0x1800fecac  jmp     loc_1800FEF4C
0x1800fecb1  mov     rax, [rax]
0x1800fecb4  mov     rdx, rsi
0x1800fecb7  mov     rcx, rdi
0x1800fecba  xor     r15d, r15d
0x1800fecbd  mov     rax, [rax+8]
0x1800fecc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fecc6  lea     rcx, [rbp+var_40]
0x1800fecca  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800feccf  mov     [rdi+1Ch], eax
0x1800fecd2  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800fecd6  mov     ecx, [rsi+14h]; unsigned int
0x1800fecd9  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800fecde  mov     eax, cs:dword_180397B68
0x1800fece4  cmp     eax, 5
0x1800fece7  jbe     short loc_1800FED57
0x1800fece9  mov     rdx, 400000000000h
0x1800fecf3  lea     rcx, dword_180397B68
0x1800fecfa  call    _tlgKeywordOn
0x1800fecff  test    al, al
0x1800fed01  jz      short loc_1800FED57
0x1800fed03  mov     eax, [rbp+var_40]
0x1800fed06  lea     rdx, dword_18033896C
0x1800fed0d  xor     ecx, ecx
0x1800fed0f  cmp     [rdi+1Ch], eax
0x1800fed12  movzx   eax, word ptr [rbp+var_10]
0x1800fed16  mov     word ptr [rbp+var_40], ax
0x1800fed1a  setnz   cl
0x1800fed1d  mov     eax, [rsi+14h]
0x1800fed20  mov     [rbp+var_38], eax
0x1800fed23  lea     rax, [rbp+var_20]
0x1800fed27  mov     [rbp+var_28], rax
0x1800fed2b  lea     rax, [rbp+var_3C]
0x1800fed2f  mov     [rsp+80h+var_48], rax
0x1800fed34  lea     rax, [rbp+var_40]
0x1800fed38  mov     [rsp+80h+var_50], rax
0x1800fed3d  lea     rax, [rbp+var_38]
0x1800fed41  mov     [rsp+80h+var_58], rax
0x1800fed46  lea     rax, [rbp+var_28]
0x1800fed4a  mov     [rsp+80h+var_60], rax
0x1800fed4f  mov     [rbp+var_3C], ecx
0x1800fed52  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800fed57  mov     rcx, [rsi]
0x1800fed5a  test    rcx, rcx
0x1800fed5d  jz      loc_1800FEF22
0x1800fed63  mov     rax, [rcx]
0x1800fed66  test    rax, rax
0x1800fed69  jz      loc_1800FEF22
0x1800fed6f  mov     rax, [rax+18h]
0x1800fed73  lea     r8, [rdi+20h]
0x1800fed77  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800fed7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fed83  mov     ebx, eax
0x1800fed85  test    eax, eax
0x1800fed87  jnz     loc_1800FEF27
0x1800fed8d  cmp     [rsi+10h], r14d
0x1800fed91  jz      loc_1800FEEBB
0x1800fed97  lea     rbx, [rdi+148h]
0x1800fed9e  mov     rcx, rbx
0x1800feda1  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800feda6  mov     rcx, rbx; struct CSpJobMgr **
0x1800feda9  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800fedae  test    eax, eax
0x1800fedb0  jnz     short loc_1800FEDBA
0x1800fedb2  lea     ebx, [rax+1Ch]
0x1800fedb5  jmp     loc_1800FEF27
0x1800fedba  mov     ecx, 10h; Size
0x1800fedbf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800fedc4  xor     r8d, r8d; pcbe
0x1800fedc7  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800fedce  mov     rdx, rax; pv
0x1800fedd1  mov     r15, rax
0x1800fedd4  mov     [rax], rdi
0x1800fedd7  call    cs:__imp_CreateThreadpoolWork
0x1800feddd  mov     r14, rax
0x1800fede0  test    rax, rax
0x1800fede3  jnz     short loc_1800FEDF1
0x1800fede5  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800fedea  mov     ebx, eax
0x1800fedec  jmp     loc_1800FEF27
0x1800fedf1  call    cs:__imp_GetCurrentThread
0x1800fedf7  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800fedfb  xor     r8d, r8d; OpenAsSelf
0x1800fedfe  mov     rcx, rax; ThreadHandle
0x1800fee01  mov     edx, 2000Ch; DesiredAccess
0x1800fee06  call    cs:__imp_OpenThreadToken
0x1800fee0c  test    eax, eax
0x1800fee0e  jnz     short loc_1800FEE1D
0x1800fee10  call    cs:__imp_GetLastError
0x1800fee16  cmp     eax, 3F0h
0x1800fee1b  jnz     short loc_1800FEDE5
0x1800fee1d  mov     rax, [rbp+TokenHandle]
0x1800fee21  mov     r8, r13
0x1800fee24  mov     [r15+8], rax
0x1800fee28  mov     rcx, rdi
0x1800fee2b  mov     rax, [rdi]
0x1800fee2e  mov     rdx, [rsi+8]
0x1800fee32  mov     rax, [rax+18h]
0x1800fee36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fee3b  mov     rax, [rdi]
0x1800fee3e  mov     rdx, r12
0x1800fee41  mov     rcx, rdi
0x1800fee44  mov     rax, [rax+28h]
0x1800fee48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fee4d  mov     ebx, eax
0x1800fee4f  test    eax, eax
0x1800fee51  jz      short loc_1800FEE5C
0x1800fee53  cmp     eax, 7
0x1800fee56  jnz     loc_1800FEF27
0x1800fee5c  mov     rax, [rdi]
0x1800fee5f  mov     rdx, r12
0x1800fee62  mov     rcx, rdi
0x1800fee65  mov     rax, [rax+38h]
0x1800fee69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fee6e  mov     ebx, eax
0x1800fee70  test    eax, eax
0x1800fee72  jnz     loc_1800FEF27
0x1800fee78  mov     rax, [rdi+150h]
0x1800fee7f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800fee86  jnz     short loc_1800FEE9C
0x1800fee88  mov     rax, [rdi+158h]
0x1800fee8f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800fee96  jz      loc_1800FEF27
0x1800fee9c  mov     rdx, r12
0x1800fee9f  mov     rcx, rdi
0x1800feea2  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800feea7  mov     ebx, eax
0x1800feea9  test    eax, eax
0x1800feeab  jnz     short loc_1800FEF27
0x1800feead  mov     rcx, r14; pwk
0x1800feeb0  call    cs:__imp_SubmitThreadpoolWork
0x1800feeb6  jmp     loc_1800FEF69
0x1800feebb  mov     rax, [rdi]
0x1800feebe  mov     r8, r13
0x1800feec1  mov     rdx, [rsi+8]
0x1800feec5  mov     rcx, rdi
0x1800feec8  mov     rax, [rax+10h]
0x1800feecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800feed1  mov     rax, [rdi]
0x1800feed4  mov     rdx, r12
0x1800feed7  mov     rcx, rdi
0x1800feeda  mov     rax, [rax+30h]
0x1800feede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800feee3  mov     ebx, eax
0x1800feee5  test    eax, eax
0x1800feee7  jz      short loc_1800FEEEE
0x1800feee9  cmp     eax, 7
0x1800feeec  jnz     short loc_1800FEF27
0x1800feeee  mov     rax, [rdi]
0x1800feef1  mov     rdx, r12
0x1800feef4  mov     rcx, rdi
0x1800feef7  mov     rax, [rax+28h]
0x1800feefb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fef00  mov     ebx, eax
0x1800fef02  test    eax, eax
0x1800fef04  jz      short loc_1800FEF0B
0x1800fef06  cmp     eax, 7
0x1800fef09  jnz     short loc_1800FEF27
0x1800fef0b  mov     rax, [rdi]
0x1800fef0e  mov     rdx, r12
0x1800fef11  mov     rcx, rdi
0x1800fef14  mov     rax, [rax+38h]
0x1800fef18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fef1d  jmp     loc_1800FEDEA
0x1800fef22  mov     ebx, 4
0x1800fef27  mov     rax, [rdi]
0x1800fef2a  mov     edx, 1
0x1800fef2f  mov     rcx, rdi
0x1800fef32  mov     rax, [rax]
0x1800fef35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fef3a  test    r15, r15
0x1800fef3d  jz      short loc_1800FEF4C
0x1800fef3f  mov     edx, 10h
0x1800fef44  mov     rcx, r15; Block
0x1800fef47  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800fef4c  mov     rcx, [rbp+TokenHandle]; hObject
0x1800fef50  test    rcx, rcx
0x1800fef53  jz      short loc_1800FEF5B
0x1800fef55  call    cs:__imp_CloseHandle
0x1800fef5b  test    r14, r14
0x1800fef5e  jz      short loc_1800FEF69
0x1800fef60  mov     rcx, r14; pwk
0x1800fef63  call    cs:__imp_CloseThreadpoolWork
0x1800fef69  mov     eax, ebx
0x1800fef6b  mov     rcx, [rbp+var_8]
0x1800fef6f  xor     rcx, rsp; StackCookie
0x1800fef72  call    __security_check_cookie
0x1800fef77  mov     rbx, [rsp+80h+arg_18]
0x1800fef7f  add     rsp, 80h
0x1800fef86  pop     r15
0x1800fef88  pop     r14
0x1800fef8a  pop     r13
0x1800fef8c  pop     r12
0x1800fef8e  pop     rdi
0x1800fef8f  pop     rsi
0x1800fef90  pop     rbp
0x1800fef91  retn
```
