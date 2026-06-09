# CSpWmiMethod<_SPACES_VirtualDisk_SetSecurityDescriptor>::RunMethod<CSpVirtualDisk::SetSecurityDescriptor,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800e0008`
- end: `0x1800e0356`
- name: `??$RunMethod@VSetSecurityDescriptor@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_SetSecurityDescriptor@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

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
- `0x1800e0008`
- `0x1800e0cd4`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e01d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e01d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e01b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e01b5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e01ca`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e01ca`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e019b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e019b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e0274`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e0274`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e0327`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e0327`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e0319`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e0319`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_SetSecurityDescriptor>::RunMethod<CSpVirtualDisk::SetSecurityDescriptor,16>(
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
  CSpVirtualDisk::SetSecurityDescriptor *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::SetSecurityDescriptor *)operator new(0x160u);
  v7 = CSpVirtualDisk::SetSecurityDescriptor::SetSecurityDescriptor(v25);
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
      v25 = (CSpVirtualDisk::SetSecurityDescriptor *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&word_180332DF6,
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
0x1800e0008  mov     [rsp-38h+arg_18], rbx
0x1800e000d  push    rbp
0x1800e000e  push    rsi
0x1800e000f  push    rdi
0x1800e0010  push    r12
0x1800e0012  push    r13
0x1800e0014  push    r14
0x1800e0016  push    r15
0x1800e0018  mov     rbp, rsp
0x1800e001b  sub     rsp, 80h
0x1800e0022  mov     rax, cs:__security_cookie
0x1800e0029  xor     rax, rsp
0x1800e002c  mov     [rbp+var_8], rax
0x1800e0030  xor     eax, eax
0x1800e0032  mov     rsi, rcx
0x1800e0035  xorps   xmm0, xmm0
0x1800e0038  mov     [rbp+var_10], eax
0x1800e003b  mov     ecx, 160h; Size
0x1800e0040  mov     [rbp+var_40], eax
0x1800e0043  movups  [rbp+var_20], xmm0
0x1800e0047  mov     [rbp+TokenHandle], rax
0x1800e004b  mov     r12, r8
0x1800e004e  mov     r13, rdx
0x1800e0051  xor     r14d, r14d
0x1800e0054  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e0059  mov     rcx, rax; this
0x1800e005c  mov     [rbp+var_28], rax
0x1800e0060  call    ??0SetSecurityDescriptor@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::SetSecurityDescriptor::SetSecurityDescriptor(void)
0x1800e0065  mov     rdi, rax
0x1800e0068  test    rax, rax
0x1800e006b  jnz     short loc_1800E0075
0x1800e006d  lea     ebx, [rax+1Bh]
0x1800e0070  jmp     loc_1800E0310
0x1800e0075  mov     rax, [rax]
0x1800e0078  mov     rdx, rsi
0x1800e007b  mov     rcx, rdi
0x1800e007e  xor     r15d, r15d
0x1800e0081  mov     rax, [rax+8]
0x1800e0085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e008a  lea     rcx, [rbp+var_40]
0x1800e008e  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800e0093  mov     [rdi+1Ch], eax
0x1800e0096  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800e009a  mov     ecx, [rsi+14h]; unsigned int
0x1800e009d  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800e00a2  mov     eax, cs:dword_180397B68
0x1800e00a8  cmp     eax, 5
0x1800e00ab  jbe     short loc_1800E011B
0x1800e00ad  mov     rdx, 400000000000h
0x1800e00b7  lea     rcx, dword_180397B68
0x1800e00be  call    _tlgKeywordOn
0x1800e00c3  test    al, al
0x1800e00c5  jz      short loc_1800E011B
0x1800e00c7  mov     eax, [rbp+var_40]
0x1800e00ca  lea     rdx, word_180332DF6
0x1800e00d1  xor     ecx, ecx
0x1800e00d3  cmp     [rdi+1Ch], eax
0x1800e00d6  movzx   eax, word ptr [rbp+var_10]
0x1800e00da  mov     word ptr [rbp+var_40], ax
0x1800e00de  setnz   cl
0x1800e00e1  mov     eax, [rsi+14h]
0x1800e00e4  mov     [rbp+var_38], eax
0x1800e00e7  lea     rax, [rbp+var_20]
0x1800e00eb  mov     [rbp+var_28], rax
0x1800e00ef  lea     rax, [rbp+var_3C]
0x1800e00f3  mov     [rsp+80h+var_48], rax
0x1800e00f8  lea     rax, [rbp+var_40]
0x1800e00fc  mov     [rsp+80h+var_50], rax
0x1800e0101  lea     rax, [rbp+var_38]
0x1800e0105  mov     [rsp+80h+var_58], rax
0x1800e010a  lea     rax, [rbp+var_28]
0x1800e010e  mov     [rsp+80h+var_60], rax
0x1800e0113  mov     [rbp+var_3C], ecx
0x1800e0116  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800e011b  mov     rcx, [rsi]
0x1800e011e  test    rcx, rcx
0x1800e0121  jz      loc_1800E02E6
0x1800e0127  mov     rax, [rcx]
0x1800e012a  test    rax, rax
0x1800e012d  jz      loc_1800E02E6
0x1800e0133  mov     rax, [rax+18h]
0x1800e0137  lea     r8, [rdi+20h]
0x1800e013b  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800e0142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0147  mov     ebx, eax
0x1800e0149  test    eax, eax
0x1800e014b  jnz     loc_1800E02EB
0x1800e0151  cmp     [rsi+10h], r14d
0x1800e0155  jz      loc_1800E027F
0x1800e015b  lea     rbx, [rdi+148h]
0x1800e0162  mov     rcx, rbx
0x1800e0165  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800e016a  mov     rcx, rbx; struct CSpJobMgr **
0x1800e016d  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800e0172  test    eax, eax
0x1800e0174  jnz     short loc_1800E017E
0x1800e0176  lea     ebx, [rax+1Ch]
0x1800e0179  jmp     loc_1800E02EB
0x1800e017e  mov     ecx, 10h; Size
0x1800e0183  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e0188  xor     r8d, r8d; pcbe
0x1800e018b  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800e0192  mov     rdx, rax; pv
0x1800e0195  mov     r15, rax
0x1800e0198  mov     [rax], rdi
0x1800e019b  call    cs:__imp_CreateThreadpoolWork
0x1800e01a1  mov     r14, rax
0x1800e01a4  test    rax, rax
0x1800e01a7  jnz     short loc_1800E01B5
0x1800e01a9  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800e01ae  mov     ebx, eax
0x1800e01b0  jmp     loc_1800E02EB
0x1800e01b5  call    cs:__imp_GetCurrentThread
0x1800e01bb  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800e01bf  xor     r8d, r8d; OpenAsSelf
0x1800e01c2  mov     rcx, rax; ThreadHandle
0x1800e01c5  mov     edx, 2000Ch; DesiredAccess
0x1800e01ca  call    cs:__imp_OpenThreadToken
0x1800e01d0  test    eax, eax
0x1800e01d2  jnz     short loc_1800E01E1
0x1800e01d4  call    cs:__imp_GetLastError
0x1800e01da  cmp     eax, 3F0h
0x1800e01df  jnz     short loc_1800E01A9
0x1800e01e1  mov     rax, [rbp+TokenHandle]
0x1800e01e5  mov     r8, r13
0x1800e01e8  mov     [r15+8], rax
0x1800e01ec  mov     rcx, rdi
0x1800e01ef  mov     rax, [rdi]
0x1800e01f2  mov     rdx, [rsi+8]
0x1800e01f6  mov     rax, [rax+18h]
0x1800e01fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e01ff  mov     rax, [rdi]
0x1800e0202  mov     rdx, r12
0x1800e0205  mov     rcx, rdi
0x1800e0208  mov     rax, [rax+28h]
0x1800e020c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0211  mov     ebx, eax
0x1800e0213  test    eax, eax
0x1800e0215  jz      short loc_1800E0220
0x1800e0217  cmp     eax, 7
0x1800e021a  jnz     loc_1800E02EB
0x1800e0220  mov     rax, [rdi]
0x1800e0223  mov     rdx, r12
0x1800e0226  mov     rcx, rdi
0x1800e0229  mov     rax, [rax+38h]
0x1800e022d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0232  mov     ebx, eax
0x1800e0234  test    eax, eax
0x1800e0236  jnz     loc_1800E02EB
0x1800e023c  mov     rax, [rdi+150h]
0x1800e0243  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800e024a  jnz     short loc_1800E0260
0x1800e024c  mov     rax, [rdi+158h]
0x1800e0253  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800e025a  jz      loc_1800E02EB
0x1800e0260  mov     rdx, r12
0x1800e0263  mov     rcx, rdi
0x1800e0266  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800e026b  mov     ebx, eax
0x1800e026d  test    eax, eax
0x1800e026f  jnz     short loc_1800E02EB
0x1800e0271  mov     rcx, r14; pwk
0x1800e0274  call    cs:__imp_SubmitThreadpoolWork
0x1800e027a  jmp     loc_1800E032D
0x1800e027f  mov     rax, [rdi]
0x1800e0282  mov     r8, r13
0x1800e0285  mov     rdx, [rsi+8]
0x1800e0289  mov     rcx, rdi
0x1800e028c  mov     rax, [rax+10h]
0x1800e0290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0295  mov     rax, [rdi]
0x1800e0298  mov     rdx, r12
0x1800e029b  mov     rcx, rdi
0x1800e029e  mov     rax, [rax+30h]
0x1800e02a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e02a7  mov     ebx, eax
0x1800e02a9  test    eax, eax
0x1800e02ab  jz      short loc_1800E02B2
0x1800e02ad  cmp     eax, 7
0x1800e02b0  jnz     short loc_1800E02EB
0x1800e02b2  mov     rax, [rdi]
0x1800e02b5  mov     rdx, r12
0x1800e02b8  mov     rcx, rdi
0x1800e02bb  mov     rax, [rax+28h]
0x1800e02bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e02c4  mov     ebx, eax
0x1800e02c6  test    eax, eax
0x1800e02c8  jz      short loc_1800E02CF
0x1800e02ca  cmp     eax, 7
0x1800e02cd  jnz     short loc_1800E02EB
0x1800e02cf  mov     rax, [rdi]
0x1800e02d2  mov     rdx, r12
0x1800e02d5  mov     rcx, rdi
0x1800e02d8  mov     rax, [rax+38h]
0x1800e02dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e02e1  jmp     loc_1800E01AE
0x1800e02e6  mov     ebx, 4
0x1800e02eb  mov     rax, [rdi]
0x1800e02ee  mov     edx, 1
0x1800e02f3  mov     rcx, rdi
0x1800e02f6  mov     rax, [rax]
0x1800e02f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e02fe  test    r15, r15
0x1800e0301  jz      short loc_1800E0310
0x1800e0303  mov     edx, 10h
0x1800e0308  mov     rcx, r15; Block
0x1800e030b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e0310  mov     rcx, [rbp+TokenHandle]; hObject
0x1800e0314  test    rcx, rcx
0x1800e0317  jz      short loc_1800E031F
0x1800e0319  call    cs:__imp_CloseHandle
0x1800e031f  test    r14, r14
0x1800e0322  jz      short loc_1800E032D
0x1800e0324  mov     rcx, r14; pwk
0x1800e0327  call    cs:__imp_CloseThreadpoolWork
0x1800e032d  mov     eax, ebx
0x1800e032f  mov     rcx, [rbp+var_8]
0x1800e0333  xor     rcx, rsp; StackCookie
0x1800e0336  call    __security_check_cookie
0x1800e033b  mov     rbx, [rsp+80h+arg_18]
0x1800e0343  add     rsp, 80h
0x1800e034a  pop     r15
0x1800e034c  pop     r14
0x1800e034e  pop     r13
0x1800e0350  pop     r12
0x1800e0352  pop     rdi
0x1800e0353  pop     rsi
0x1800e0354  pop     rbp
0x1800e0355  retn
```
