# CSpWmiMethod<_SPACES_VirtualDisk_SetProperties>::RunMethod<CSpVirtualDisk::SetProperties,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800dfcb4`
- end: `0x1800e0002`
- name: `??$RunMethod@VSetProperties@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_SetProperties@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800dfcb4`
- `0x1800e0c68`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfe80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfe80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dfe61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dfe61`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dfe76`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dfe76`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800dfe47`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800dfe47`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800dff20`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800dff20`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800dffd3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800dffd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dffc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dffc5`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_SetProperties>::RunMethod<CSpVirtualDisk::SetProperties,16>(
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
  CSpVirtualDisk::SetProperties *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::SetProperties *)operator new(0x160u);
  v7 = CSpVirtualDisk::SetProperties::SetProperties(v25);
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
      v25 = (CSpVirtualDisk::SetProperties *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&unk_1803338F0,
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
0x1800dfcb4  mov     [rsp-38h+arg_18], rbx
0x1800dfcb9  push    rbp
0x1800dfcba  push    rsi
0x1800dfcbb  push    rdi
0x1800dfcbc  push    r12
0x1800dfcbe  push    r13
0x1800dfcc0  push    r14
0x1800dfcc2  push    r15
0x1800dfcc4  mov     rbp, rsp
0x1800dfcc7  sub     rsp, 80h
0x1800dfcce  mov     rax, cs:__security_cookie
0x1800dfcd5  xor     rax, rsp
0x1800dfcd8  mov     [rbp+var_8], rax
0x1800dfcdc  xor     eax, eax
0x1800dfcde  mov     rsi, rcx
0x1800dfce1  xorps   xmm0, xmm0
0x1800dfce4  mov     [rbp+var_10], eax
0x1800dfce7  mov     ecx, 160h; Size
0x1800dfcec  mov     [rbp+var_40], eax
0x1800dfcef  movups  [rbp+var_20], xmm0
0x1800dfcf3  mov     [rbp+TokenHandle], rax
0x1800dfcf7  mov     r12, r8
0x1800dfcfa  mov     r13, rdx
0x1800dfcfd  xor     r14d, r14d
0x1800dfd00  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800dfd05  mov     rcx, rax; this
0x1800dfd08  mov     [rbp+var_28], rax
0x1800dfd0c  call    ??0SetProperties@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::SetProperties::SetProperties(void)
0x1800dfd11  mov     rdi, rax
0x1800dfd14  test    rax, rax
0x1800dfd17  jnz     short loc_1800DFD21
0x1800dfd19  lea     ebx, [rax+1Bh]
0x1800dfd1c  jmp     loc_1800DFFBC
0x1800dfd21  mov     rax, [rax]
0x1800dfd24  mov     rdx, rsi
0x1800dfd27  mov     rcx, rdi
0x1800dfd2a  xor     r15d, r15d
0x1800dfd2d  mov     rax, [rax+8]
0x1800dfd31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfd36  lea     rcx, [rbp+var_40]
0x1800dfd3a  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800dfd3f  mov     [rdi+1Ch], eax
0x1800dfd42  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800dfd46  mov     ecx, [rsi+14h]; unsigned int
0x1800dfd49  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800dfd4e  mov     eax, cs:dword_180397B68
0x1800dfd54  cmp     eax, 5
0x1800dfd57  jbe     short loc_1800DFDC7
0x1800dfd59  mov     rdx, 400000000000h
0x1800dfd63  lea     rcx, dword_180397B68
0x1800dfd6a  call    _tlgKeywordOn
0x1800dfd6f  test    al, al
0x1800dfd71  jz      short loc_1800DFDC7
0x1800dfd73  mov     eax, [rbp+var_40]
0x1800dfd76  lea     rdx, unk_1803338F0
0x1800dfd7d  xor     ecx, ecx
0x1800dfd7f  cmp     [rdi+1Ch], eax
0x1800dfd82  movzx   eax, word ptr [rbp+var_10]
0x1800dfd86  mov     word ptr [rbp+var_40], ax
0x1800dfd8a  setnz   cl
0x1800dfd8d  mov     eax, [rsi+14h]
0x1800dfd90  mov     [rbp+var_38], eax
0x1800dfd93  lea     rax, [rbp+var_20]
0x1800dfd97  mov     [rbp+var_28], rax
0x1800dfd9b  lea     rax, [rbp+var_3C]
0x1800dfd9f  mov     [rsp+80h+var_48], rax
0x1800dfda4  lea     rax, [rbp+var_40]
0x1800dfda8  mov     [rsp+80h+var_50], rax
0x1800dfdad  lea     rax, [rbp+var_38]
0x1800dfdb1  mov     [rsp+80h+var_58], rax
0x1800dfdb6  lea     rax, [rbp+var_28]
0x1800dfdba  mov     [rsp+80h+var_60], rax
0x1800dfdbf  mov     [rbp+var_3C], ecx
0x1800dfdc2  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800dfdc7  mov     rcx, [rsi]
0x1800dfdca  test    rcx, rcx
0x1800dfdcd  jz      loc_1800DFF92
0x1800dfdd3  mov     rax, [rcx]
0x1800dfdd6  test    rax, rax
0x1800dfdd9  jz      loc_1800DFF92
0x1800dfddf  mov     rax, [rax+18h]
0x1800dfde3  lea     r8, [rdi+20h]
0x1800dfde7  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800dfdee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfdf3  mov     ebx, eax
0x1800dfdf5  test    eax, eax
0x1800dfdf7  jnz     loc_1800DFF97
0x1800dfdfd  cmp     [rsi+10h], r14d
0x1800dfe01  jz      loc_1800DFF2B
0x1800dfe07  lea     rbx, [rdi+148h]
0x1800dfe0e  mov     rcx, rbx
0x1800dfe11  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800dfe16  mov     rcx, rbx; struct CSpJobMgr **
0x1800dfe19  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800dfe1e  test    eax, eax
0x1800dfe20  jnz     short loc_1800DFE2A
0x1800dfe22  lea     ebx, [rax+1Ch]
0x1800dfe25  jmp     loc_1800DFF97
0x1800dfe2a  mov     ecx, 10h; Size
0x1800dfe2f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800dfe34  xor     r8d, r8d; pcbe
0x1800dfe37  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800dfe3e  mov     rdx, rax; pv
0x1800dfe41  mov     r15, rax
0x1800dfe44  mov     [rax], rdi
0x1800dfe47  call    cs:__imp_CreateThreadpoolWork
0x1800dfe4d  mov     r14, rax
0x1800dfe50  test    rax, rax
0x1800dfe53  jnz     short loc_1800DFE61
0x1800dfe55  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800dfe5a  mov     ebx, eax
0x1800dfe5c  jmp     loc_1800DFF97
0x1800dfe61  call    cs:__imp_GetCurrentThread
0x1800dfe67  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800dfe6b  xor     r8d, r8d; OpenAsSelf
0x1800dfe6e  mov     rcx, rax; ThreadHandle
0x1800dfe71  mov     edx, 2000Ch; DesiredAccess
0x1800dfe76  call    cs:__imp_OpenThreadToken
0x1800dfe7c  test    eax, eax
0x1800dfe7e  jnz     short loc_1800DFE8D
0x1800dfe80  call    cs:__imp_GetLastError
0x1800dfe86  cmp     eax, 3F0h
0x1800dfe8b  jnz     short loc_1800DFE55
0x1800dfe8d  mov     rax, [rbp+TokenHandle]
0x1800dfe91  mov     r8, r13
0x1800dfe94  mov     [r15+8], rax
0x1800dfe98  mov     rcx, rdi
0x1800dfe9b  mov     rax, [rdi]
0x1800dfe9e  mov     rdx, [rsi+8]
0x1800dfea2  mov     rax, [rax+18h]
0x1800dfea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfeab  mov     rax, [rdi]
0x1800dfeae  mov     rdx, r12
0x1800dfeb1  mov     rcx, rdi
0x1800dfeb4  mov     rax, [rax+28h]
0x1800dfeb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfebd  mov     ebx, eax
0x1800dfebf  test    eax, eax
0x1800dfec1  jz      short loc_1800DFECC
0x1800dfec3  cmp     eax, 7
0x1800dfec6  jnz     loc_1800DFF97
0x1800dfecc  mov     rax, [rdi]
0x1800dfecf  mov     rdx, r12
0x1800dfed2  mov     rcx, rdi
0x1800dfed5  mov     rax, [rax+38h]
0x1800dfed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfede  mov     ebx, eax
0x1800dfee0  test    eax, eax
0x1800dfee2  jnz     loc_1800DFF97
0x1800dfee8  mov     rax, [rdi+150h]
0x1800dfeef  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800dfef6  jnz     short loc_1800DFF0C
0x1800dfef8  mov     rax, [rdi+158h]
0x1800dfeff  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800dff06  jz      loc_1800DFF97
0x1800dff0c  mov     rdx, r12
0x1800dff0f  mov     rcx, rdi
0x1800dff12  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800dff17  mov     ebx, eax
0x1800dff19  test    eax, eax
0x1800dff1b  jnz     short loc_1800DFF97
0x1800dff1d  mov     rcx, r14; pwk
0x1800dff20  call    cs:__imp_SubmitThreadpoolWork
0x1800dff26  jmp     loc_1800DFFD9
0x1800dff2b  mov     rax, [rdi]
0x1800dff2e  mov     r8, r13
0x1800dff31  mov     rdx, [rsi+8]
0x1800dff35  mov     rcx, rdi
0x1800dff38  mov     rax, [rax+10h]
0x1800dff3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dff41  mov     rax, [rdi]
0x1800dff44  mov     rdx, r12
0x1800dff47  mov     rcx, rdi
0x1800dff4a  mov     rax, [rax+30h]
0x1800dff4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dff53  mov     ebx, eax
0x1800dff55  test    eax, eax
0x1800dff57  jz      short loc_1800DFF5E
0x1800dff59  cmp     eax, 7
0x1800dff5c  jnz     short loc_1800DFF97
0x1800dff5e  mov     rax, [rdi]
0x1800dff61  mov     rdx, r12
0x1800dff64  mov     rcx, rdi
0x1800dff67  mov     rax, [rax+28h]
0x1800dff6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dff70  mov     ebx, eax
0x1800dff72  test    eax, eax
0x1800dff74  jz      short loc_1800DFF7B
0x1800dff76  cmp     eax, 7
0x1800dff79  jnz     short loc_1800DFF97
0x1800dff7b  mov     rax, [rdi]
0x1800dff7e  mov     rdx, r12
0x1800dff81  mov     rcx, rdi
0x1800dff84  mov     rax, [rax+38h]
0x1800dff88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dff8d  jmp     loc_1800DFE5A
0x1800dff92  mov     ebx, 4
0x1800dff97  mov     rax, [rdi]
0x1800dff9a  mov     edx, 1
0x1800dff9f  mov     rcx, rdi
0x1800dffa2  mov     rax, [rax]
0x1800dffa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dffaa  test    r15, r15
0x1800dffad  jz      short loc_1800DFFBC
0x1800dffaf  mov     edx, 10h
0x1800dffb4  mov     rcx, r15; Block
0x1800dffb7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800dffbc  mov     rcx, [rbp+TokenHandle]; hObject
0x1800dffc0  test    rcx, rcx
0x1800dffc3  jz      short loc_1800DFFCB
0x1800dffc5  call    cs:__imp_CloseHandle
0x1800dffcb  test    r14, r14
0x1800dffce  jz      short loc_1800DFFD9
0x1800dffd0  mov     rcx, r14; pwk
0x1800dffd3  call    cs:__imp_CloseThreadpoolWork
0x1800dffd9  mov     eax, ebx
0x1800dffdb  mov     rcx, [rbp+var_8]
0x1800dffdf  xor     rcx, rsp; StackCookie
0x1800dffe2  call    __security_check_cookie
0x1800dffe7  mov     rbx, [rsp+80h+arg_18]
0x1800dffef  add     rsp, 80h
0x1800dfff6  pop     r15
0x1800dfff8  pop     r14
0x1800dfffa  pop     r13
0x1800dfffc  pop     r12
0x1800dfffe  pop     rdi
0x1800dffff  pop     rsi
0x1800e0000  pop     rbp
0x1800e0001  retn
```
