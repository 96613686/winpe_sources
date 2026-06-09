# CSpWmiMethod<_SPACES_PhysicalDisk_GetFirmwareInformation>::RunMethod<CSpPhysicalDisk::GetFirmwareInformation,4>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800edcf0`
- end: `0x1800ee03e`
- name: `??$RunMethod@VGetFirmwareInformation@CSpPhysicalDisk@@$03@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetFirmwareInformation@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800f3f30`

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
- `0x1800edcf0`
- `0x1800f0288`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800edebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800edebc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ede9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ede9d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800edeb2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800edeb2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ede83`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ede83`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800edf5c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800edf5c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ee00f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ee00f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ee001`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ee001`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_PhysicalDisk_GetFirmwareInformation>::RunMethod<CSpPhysicalDisk::GetFirmwareInformation,4>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 FirmwareInformation; // rax
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
  CSpPhysicalDisk::GetFirmwareInformation *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpPhysicalDisk::GetFirmwareInformation *)operator new(0x168u);
  FirmwareInformation = CSpPhysicalDisk::GetFirmwareInformation::GetFirmwareInformation(v25);
  v8 = FirmwareInformation;
  if ( FirmwareInformation )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)FirmwareInformation + 8LL))(FirmwareInformation, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpPhysicalDisk::GetFirmwareInformation *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_18033559B,
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
0x1800edcf0  mov     [rsp-38h+arg_18], rbx
0x1800edcf5  push    rbp
0x1800edcf6  push    rsi
0x1800edcf7  push    rdi
0x1800edcf8  push    r12
0x1800edcfa  push    r13
0x1800edcfc  push    r14
0x1800edcfe  push    r15
0x1800edd00  mov     rbp, rsp
0x1800edd03  sub     rsp, 80h
0x1800edd0a  mov     rax, cs:__security_cookie
0x1800edd11  xor     rax, rsp
0x1800edd14  mov     [rbp+var_8], rax
0x1800edd18  xor     eax, eax
0x1800edd1a  mov     rsi, rcx
0x1800edd1d  xorps   xmm0, xmm0
0x1800edd20  mov     [rbp+var_10], eax
0x1800edd23  mov     ecx, 168h; Size
0x1800edd28  mov     [rbp+var_40], eax
0x1800edd2b  movups  [rbp+var_20], xmm0
0x1800edd2f  mov     [rbp+TokenHandle], rax
0x1800edd33  mov     r12, r8
0x1800edd36  mov     r13, rdx
0x1800edd39  xor     r14d, r14d
0x1800edd3c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800edd41  mov     rcx, rax; this
0x1800edd44  mov     [rbp+var_28], rax
0x1800edd48  call    ??0GetFirmwareInformation@CSpPhysicalDisk@@QEAA@XZ; CSpPhysicalDisk::GetFirmwareInformation::GetFirmwareInformation(void)
0x1800edd4d  mov     rdi, rax
0x1800edd50  test    rax, rax
0x1800edd53  jnz     short loc_1800EDD5D
0x1800edd55  lea     ebx, [rax+1Bh]
0x1800edd58  jmp     loc_1800EDFF8
0x1800edd5d  mov     rax, [rax]
0x1800edd60  mov     rdx, rsi
0x1800edd63  mov     rcx, rdi
0x1800edd66  xor     r15d, r15d
0x1800edd69  mov     rax, [rax+8]
0x1800edd6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edd72  lea     rcx, [rbp+var_40]
0x1800edd76  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800edd7b  mov     [rdi+1Ch], eax
0x1800edd7e  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800edd82  mov     ecx, [rsi+14h]; unsigned int
0x1800edd85  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800edd8a  mov     eax, cs:dword_180397B68
0x1800edd90  cmp     eax, 5
0x1800edd93  jbe     short loc_1800EDE03
0x1800edd95  mov     rdx, 400000000000h
0x1800edd9f  lea     rcx, dword_180397B68
0x1800edda6  call    _tlgKeywordOn
0x1800eddab  test    al, al
0x1800eddad  jz      short loc_1800EDE03
0x1800eddaf  mov     eax, [rbp+var_40]
0x1800eddb2  lea     rdx, byte_18033559B
0x1800eddb9  xor     ecx, ecx
0x1800eddbb  cmp     [rdi+1Ch], eax
0x1800eddbe  movzx   eax, word ptr [rbp+var_10]
0x1800eddc2  mov     word ptr [rbp+var_40], ax
0x1800eddc6  setnz   cl
0x1800eddc9  mov     eax, [rsi+14h]
0x1800eddcc  mov     [rbp+var_38], eax
0x1800eddcf  lea     rax, [rbp+var_20]
0x1800eddd3  mov     [rbp+var_28], rax
0x1800eddd7  lea     rax, [rbp+var_3C]
0x1800edddb  mov     [rsp+80h+var_48], rax
0x1800edde0  lea     rax, [rbp+var_40]
0x1800edde4  mov     [rsp+80h+var_50], rax
0x1800edde9  lea     rax, [rbp+var_38]
0x1800edded  mov     [rsp+80h+var_58], rax
0x1800eddf2  lea     rax, [rbp+var_28]
0x1800eddf6  mov     [rsp+80h+var_60], rax
0x1800eddfb  mov     [rbp+var_3C], ecx
0x1800eddfe  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800ede03  mov     rcx, [rsi]
0x1800ede06  test    rcx, rcx
0x1800ede09  jz      loc_1800EDFCE
0x1800ede0f  mov     rax, [rcx]
0x1800ede12  test    rax, rax
0x1800ede15  jz      loc_1800EDFCE
0x1800ede1b  mov     rax, [rax+18h]
0x1800ede1f  lea     r8, [rdi+20h]
0x1800ede23  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800ede2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ede2f  mov     ebx, eax
0x1800ede31  test    eax, eax
0x1800ede33  jnz     loc_1800EDFD3
0x1800ede39  cmp     [rsi+10h], r14d
0x1800ede3d  jz      loc_1800EDF67
0x1800ede43  lea     rbx, [rdi+148h]
0x1800ede4a  mov     rcx, rbx
0x1800ede4d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800ede52  mov     rcx, rbx; struct CSpJobMgr **
0x1800ede55  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800ede5a  test    eax, eax
0x1800ede5c  jnz     short loc_1800EDE66
0x1800ede5e  lea     ebx, [rax+1Ch]
0x1800ede61  jmp     loc_1800EDFD3
0x1800ede66  mov     ecx, 10h; Size
0x1800ede6b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ede70  xor     r8d, r8d; pcbe
0x1800ede73  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800ede7a  mov     rdx, rax; pv
0x1800ede7d  mov     r15, rax
0x1800ede80  mov     [rax], rdi
0x1800ede83  call    cs:__imp_CreateThreadpoolWork
0x1800ede89  mov     r14, rax
0x1800ede8c  test    rax, rax
0x1800ede8f  jnz     short loc_1800EDE9D
0x1800ede91  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800ede96  mov     ebx, eax
0x1800ede98  jmp     loc_1800EDFD3
0x1800ede9d  call    cs:__imp_GetCurrentThread
0x1800edea3  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800edea7  xor     r8d, r8d; OpenAsSelf
0x1800edeaa  mov     rcx, rax; ThreadHandle
0x1800edead  mov     edx, 2000Ch; DesiredAccess
0x1800edeb2  call    cs:__imp_OpenThreadToken
0x1800edeb8  test    eax, eax
0x1800edeba  jnz     short loc_1800EDEC9
0x1800edebc  call    cs:__imp_GetLastError
0x1800edec2  cmp     eax, 3F0h
0x1800edec7  jnz     short loc_1800EDE91
0x1800edec9  mov     rax, [rbp+TokenHandle]
0x1800edecd  mov     r8, r13
0x1800eded0  mov     [r15+8], rax
0x1800eded4  mov     rcx, rdi
0x1800eded7  mov     rax, [rdi]
0x1800ededa  mov     rdx, [rsi+8]
0x1800edede  mov     rax, [rax+18h]
0x1800edee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edee7  mov     rax, [rdi]
0x1800edeea  mov     rdx, r12
0x1800edeed  mov     rcx, rdi
0x1800edef0  mov     rax, [rax+28h]
0x1800edef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edef9  mov     ebx, eax
0x1800edefb  test    eax, eax
0x1800edefd  jz      short loc_1800EDF08
0x1800edeff  cmp     eax, 7
0x1800edf02  jnz     loc_1800EDFD3
0x1800edf08  mov     rax, [rdi]
0x1800edf0b  mov     rdx, r12
0x1800edf0e  mov     rcx, rdi
0x1800edf11  mov     rax, [rax+38h]
0x1800edf15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edf1a  mov     ebx, eax
0x1800edf1c  test    eax, eax
0x1800edf1e  jnz     loc_1800EDFD3
0x1800edf24  mov     rax, [rdi+150h]
0x1800edf2b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800edf32  jnz     short loc_1800EDF48
0x1800edf34  mov     rax, [rdi+158h]
0x1800edf3b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800edf42  jz      loc_1800EDFD3
0x1800edf48  mov     rdx, r12
0x1800edf4b  mov     rcx, rdi
0x1800edf4e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800edf53  mov     ebx, eax
0x1800edf55  test    eax, eax
0x1800edf57  jnz     short loc_1800EDFD3
0x1800edf59  mov     rcx, r14; pwk
0x1800edf5c  call    cs:__imp_SubmitThreadpoolWork
0x1800edf62  jmp     loc_1800EE015
0x1800edf67  mov     rax, [rdi]
0x1800edf6a  mov     r8, r13
0x1800edf6d  mov     rdx, [rsi+8]
0x1800edf71  mov     rcx, rdi
0x1800edf74  mov     rax, [rax+10h]
0x1800edf78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edf7d  mov     rax, [rdi]
0x1800edf80  mov     rdx, r12
0x1800edf83  mov     rcx, rdi
0x1800edf86  mov     rax, [rax+30h]
0x1800edf8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edf8f  mov     ebx, eax
0x1800edf91  test    eax, eax
0x1800edf93  jz      short loc_1800EDF9A
0x1800edf95  cmp     eax, 7
0x1800edf98  jnz     short loc_1800EDFD3
0x1800edf9a  mov     rax, [rdi]
0x1800edf9d  mov     rdx, r12
0x1800edfa0  mov     rcx, rdi
0x1800edfa3  mov     rax, [rax+28h]
0x1800edfa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edfac  mov     ebx, eax
0x1800edfae  test    eax, eax
0x1800edfb0  jz      short loc_1800EDFB7
0x1800edfb2  cmp     eax, 7
0x1800edfb5  jnz     short loc_1800EDFD3
0x1800edfb7  mov     rax, [rdi]
0x1800edfba  mov     rdx, r12
0x1800edfbd  mov     rcx, rdi
0x1800edfc0  mov     rax, [rax+38h]
0x1800edfc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edfc9  jmp     loc_1800EDE96
0x1800edfce  mov     ebx, 4
0x1800edfd3  mov     rax, [rdi]
0x1800edfd6  mov     edx, 1
0x1800edfdb  mov     rcx, rdi
0x1800edfde  mov     rax, [rax]
0x1800edfe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edfe6  test    r15, r15
0x1800edfe9  jz      short loc_1800EDFF8
0x1800edfeb  mov     edx, 10h
0x1800edff0  mov     rcx, r15; Block
0x1800edff3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800edff8  mov     rcx, [rbp+TokenHandle]; hObject
0x1800edffc  test    rcx, rcx
0x1800edfff  jz      short loc_1800EE007
0x1800ee001  call    cs:__imp_CloseHandle
0x1800ee007  test    r14, r14
0x1800ee00a  jz      short loc_1800EE015
0x1800ee00c  mov     rcx, r14; pwk
0x1800ee00f  call    cs:__imp_CloseThreadpoolWork
0x1800ee015  mov     eax, ebx
0x1800ee017  mov     rcx, [rbp+var_8]
0x1800ee01b  xor     rcx, rsp; StackCookie
0x1800ee01e  call    __security_check_cookie
0x1800ee023  mov     rbx, [rsp+80h+arg_18]
0x1800ee02b  add     rsp, 80h
0x1800ee032  pop     r15
0x1800ee034  pop     r14
0x1800ee036  pop     r13
0x1800ee038  pop     r12
0x1800ee03a  pop     rdi
0x1800ee03b  pop     rsi
0x1800ee03c  pop     rbp
0x1800ee03d  retn
```
