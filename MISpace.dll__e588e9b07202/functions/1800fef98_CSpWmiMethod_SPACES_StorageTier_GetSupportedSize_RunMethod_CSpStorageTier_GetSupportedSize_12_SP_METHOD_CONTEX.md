# CSpWmiMethod<_SPACES_StorageTier_GetSupportedSize>::RunMethod<CSpStorageTier::GetSupportedSize,12>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800fef98`
- end: `0x1800ff2e6`
- name: `??$RunMethod@VGetSupportedSize@CSpStorageTier@@$0M@@?$CSpWmiMethod@U_SPACES_StorageTier_GetSupportedSize@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800fef98`
- `0x1801004f0`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ff164`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ff164`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ff145`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ff145`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ff15a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ff15a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ff12b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ff12b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800ff204`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800ff204`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ff2b7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ff2b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ff2a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ff2a9`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageTier_GetSupportedSize>::RunMethod<CSpStorageTier::GetSupportedSize,12>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 SupportedSize; // rax
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
  CSpStorageTier::GetSupportedSize *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageTier::GetSupportedSize *)operator new(0x178u);
  SupportedSize = CSpStorageTier::GetSupportedSize::GetSupportedSize(v25);
  v8 = SupportedSize;
  if ( SupportedSize )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)SupportedSize + 8LL))(SupportedSize, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStorageTier::GetSupportedSize *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_18033A121,
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
0x1800fef98  mov     [rsp-38h+arg_18], rbx
0x1800fef9d  push    rbp
0x1800fef9e  push    rsi
0x1800fef9f  push    rdi
0x1800fefa0  push    r12
0x1800fefa2  push    r13
0x1800fefa4  push    r14
0x1800fefa6  push    r15
0x1800fefa8  mov     rbp, rsp
0x1800fefab  sub     rsp, 80h
0x1800fefb2  mov     rax, cs:__security_cookie
0x1800fefb9  xor     rax, rsp
0x1800fefbc  mov     [rbp+var_8], rax
0x1800fefc0  xor     eax, eax
0x1800fefc2  mov     rsi, rcx
0x1800fefc5  xorps   xmm0, xmm0
0x1800fefc8  mov     [rbp+var_10], eax
0x1800fefcb  mov     ecx, 178h; Size
0x1800fefd0  mov     [rbp+var_40], eax
0x1800fefd3  movups  [rbp+var_20], xmm0
0x1800fefd7  mov     [rbp+TokenHandle], rax
0x1800fefdb  mov     r12, r8
0x1800fefde  mov     r13, rdx
0x1800fefe1  xor     r14d, r14d
0x1800fefe4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800fefe9  mov     rcx, rax; this
0x1800fefec  mov     [rbp+var_28], rax
0x1800feff0  call    ??0GetSupportedSize@CSpStorageTier@@QEAA@XZ; CSpStorageTier::GetSupportedSize::GetSupportedSize(void)
0x1800feff5  mov     rdi, rax
0x1800feff8  test    rax, rax
0x1800feffb  jnz     short loc_1800FF005
0x1800feffd  lea     ebx, [rax+1Bh]
0x1800ff000  jmp     loc_1800FF2A0
0x1800ff005  mov     rax, [rax]
0x1800ff008  mov     rdx, rsi
0x1800ff00b  mov     rcx, rdi
0x1800ff00e  xor     r15d, r15d
0x1800ff011  mov     rax, [rax+8]
0x1800ff015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff01a  lea     rcx, [rbp+var_40]
0x1800ff01e  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800ff023  mov     [rdi+1Ch], eax
0x1800ff026  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800ff02a  mov     ecx, [rsi+14h]; unsigned int
0x1800ff02d  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800ff032  mov     eax, cs:dword_180397B68
0x1800ff038  cmp     eax, 5
0x1800ff03b  jbe     short loc_1800FF0AB
0x1800ff03d  mov     rdx, 400000000000h
0x1800ff047  lea     rcx, dword_180397B68
0x1800ff04e  call    _tlgKeywordOn
0x1800ff053  test    al, al
0x1800ff055  jz      short loc_1800FF0AB
0x1800ff057  mov     eax, [rbp+var_40]
0x1800ff05a  lea     rdx, byte_18033A121
0x1800ff061  xor     ecx, ecx
0x1800ff063  cmp     [rdi+1Ch], eax
0x1800ff066  movzx   eax, word ptr [rbp+var_10]
0x1800ff06a  mov     word ptr [rbp+var_40], ax
0x1800ff06e  setnz   cl
0x1800ff071  mov     eax, [rsi+14h]
0x1800ff074  mov     [rbp+var_38], eax
0x1800ff077  lea     rax, [rbp+var_20]
0x1800ff07b  mov     [rbp+var_28], rax
0x1800ff07f  lea     rax, [rbp+var_3C]
0x1800ff083  mov     [rsp+80h+var_48], rax
0x1800ff088  lea     rax, [rbp+var_40]
0x1800ff08c  mov     [rsp+80h+var_50], rax
0x1800ff091  lea     rax, [rbp+var_38]
0x1800ff095  mov     [rsp+80h+var_58], rax
0x1800ff09a  lea     rax, [rbp+var_28]
0x1800ff09e  mov     [rsp+80h+var_60], rax
0x1800ff0a3  mov     [rbp+var_3C], ecx
0x1800ff0a6  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800ff0ab  mov     rcx, [rsi]
0x1800ff0ae  test    rcx, rcx
0x1800ff0b1  jz      loc_1800FF276
0x1800ff0b7  mov     rax, [rcx]
0x1800ff0ba  test    rax, rax
0x1800ff0bd  jz      loc_1800FF276
0x1800ff0c3  mov     rax, [rax+18h]
0x1800ff0c7  lea     r8, [rdi+20h]
0x1800ff0cb  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800ff0d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff0d7  mov     ebx, eax
0x1800ff0d9  test    eax, eax
0x1800ff0db  jnz     loc_1800FF27B
0x1800ff0e1  cmp     [rsi+10h], r14d
0x1800ff0e5  jz      loc_1800FF20F
0x1800ff0eb  lea     rbx, [rdi+148h]
0x1800ff0f2  mov     rcx, rbx
0x1800ff0f5  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800ff0fa  mov     rcx, rbx; struct CSpJobMgr **
0x1800ff0fd  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800ff102  test    eax, eax
0x1800ff104  jnz     short loc_1800FF10E
0x1800ff106  lea     ebx, [rax+1Ch]
0x1800ff109  jmp     loc_1800FF27B
0x1800ff10e  mov     ecx, 10h; Size
0x1800ff113  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ff118  xor     r8d, r8d; pcbe
0x1800ff11b  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800ff122  mov     rdx, rax; pv
0x1800ff125  mov     r15, rax
0x1800ff128  mov     [rax], rdi
0x1800ff12b  call    cs:__imp_CreateThreadpoolWork
0x1800ff131  mov     r14, rax
0x1800ff134  test    rax, rax
0x1800ff137  jnz     short loc_1800FF145
0x1800ff139  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800ff13e  mov     ebx, eax
0x1800ff140  jmp     loc_1800FF27B
0x1800ff145  call    cs:__imp_GetCurrentThread
0x1800ff14b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800ff14f  xor     r8d, r8d; OpenAsSelf
0x1800ff152  mov     rcx, rax; ThreadHandle
0x1800ff155  mov     edx, 2000Ch; DesiredAccess
0x1800ff15a  call    cs:__imp_OpenThreadToken
0x1800ff160  test    eax, eax
0x1800ff162  jnz     short loc_1800FF171
0x1800ff164  call    cs:__imp_GetLastError
0x1800ff16a  cmp     eax, 3F0h
0x1800ff16f  jnz     short loc_1800FF139
0x1800ff171  mov     rax, [rbp+TokenHandle]
0x1800ff175  mov     r8, r13
0x1800ff178  mov     [r15+8], rax
0x1800ff17c  mov     rcx, rdi
0x1800ff17f  mov     rax, [rdi]
0x1800ff182  mov     rdx, [rsi+8]
0x1800ff186  mov     rax, [rax+18h]
0x1800ff18a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff18f  mov     rax, [rdi]
0x1800ff192  mov     rdx, r12
0x1800ff195  mov     rcx, rdi
0x1800ff198  mov     rax, [rax+28h]
0x1800ff19c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff1a1  mov     ebx, eax
0x1800ff1a3  test    eax, eax
0x1800ff1a5  jz      short loc_1800FF1B0
0x1800ff1a7  cmp     eax, 7
0x1800ff1aa  jnz     loc_1800FF27B
0x1800ff1b0  mov     rax, [rdi]
0x1800ff1b3  mov     rdx, r12
0x1800ff1b6  mov     rcx, rdi
0x1800ff1b9  mov     rax, [rax+38h]
0x1800ff1bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff1c2  mov     ebx, eax
0x1800ff1c4  test    eax, eax
0x1800ff1c6  jnz     loc_1800FF27B
0x1800ff1cc  mov     rax, [rdi+150h]
0x1800ff1d3  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800ff1da  jnz     short loc_1800FF1F0
0x1800ff1dc  mov     rax, [rdi+158h]
0x1800ff1e3  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800ff1ea  jz      loc_1800FF27B
0x1800ff1f0  mov     rdx, r12
0x1800ff1f3  mov     rcx, rdi
0x1800ff1f6  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800ff1fb  mov     ebx, eax
0x1800ff1fd  test    eax, eax
0x1800ff1ff  jnz     short loc_1800FF27B
0x1800ff201  mov     rcx, r14; pwk
0x1800ff204  call    cs:__imp_SubmitThreadpoolWork
0x1800ff20a  jmp     loc_1800FF2BD
0x1800ff20f  mov     rax, [rdi]
0x1800ff212  mov     r8, r13
0x1800ff215  mov     rdx, [rsi+8]
0x1800ff219  mov     rcx, rdi
0x1800ff21c  mov     rax, [rax+10h]
0x1800ff220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff225  mov     rax, [rdi]
0x1800ff228  mov     rdx, r12
0x1800ff22b  mov     rcx, rdi
0x1800ff22e  mov     rax, [rax+30h]
0x1800ff232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff237  mov     ebx, eax
0x1800ff239  test    eax, eax
0x1800ff23b  jz      short loc_1800FF242
0x1800ff23d  cmp     eax, 7
0x1800ff240  jnz     short loc_1800FF27B
0x1800ff242  mov     rax, [rdi]
0x1800ff245  mov     rdx, r12
0x1800ff248  mov     rcx, rdi
0x1800ff24b  mov     rax, [rax+28h]
0x1800ff24f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff254  mov     ebx, eax
0x1800ff256  test    eax, eax
0x1800ff258  jz      short loc_1800FF25F
0x1800ff25a  cmp     eax, 7
0x1800ff25d  jnz     short loc_1800FF27B
0x1800ff25f  mov     rax, [rdi]
0x1800ff262  mov     rdx, r12
0x1800ff265  mov     rcx, rdi
0x1800ff268  mov     rax, [rax+38h]
0x1800ff26c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff271  jmp     loc_1800FF13E
0x1800ff276  mov     ebx, 4
0x1800ff27b  mov     rax, [rdi]
0x1800ff27e  mov     edx, 1
0x1800ff283  mov     rcx, rdi
0x1800ff286  mov     rax, [rax]
0x1800ff289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff28e  test    r15, r15
0x1800ff291  jz      short loc_1800FF2A0
0x1800ff293  mov     edx, 10h
0x1800ff298  mov     rcx, r15; Block
0x1800ff29b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ff2a0  mov     rcx, [rbp+TokenHandle]; hObject
0x1800ff2a4  test    rcx, rcx
0x1800ff2a7  jz      short loc_1800FF2AF
0x1800ff2a9  call    cs:__imp_CloseHandle
0x1800ff2af  test    r14, r14
0x1800ff2b2  jz      short loc_1800FF2BD
0x1800ff2b4  mov     rcx, r14; pwk
0x1800ff2b7  call    cs:__imp_CloseThreadpoolWork
0x1800ff2bd  mov     eax, ebx
0x1800ff2bf  mov     rcx, [rbp+var_8]
0x1800ff2c3  xor     rcx, rsp; StackCookie
0x1800ff2c6  call    __security_check_cookie
0x1800ff2cb  mov     rbx, [rsp+80h+arg_18]
0x1800ff2d3  add     rsp, 80h
0x1800ff2da  pop     r15
0x1800ff2dc  pop     r14
0x1800ff2de  pop     r13
0x1800ff2e0  pop     r12
0x1800ff2e2  pop     rdi
0x1800ff2e3  pop     rsi
0x1800ff2e4  pop     rbp
0x1800ff2e5  retn
```
