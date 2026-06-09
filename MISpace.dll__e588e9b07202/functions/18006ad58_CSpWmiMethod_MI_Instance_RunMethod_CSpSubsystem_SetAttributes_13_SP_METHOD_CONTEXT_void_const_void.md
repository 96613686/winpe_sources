# CSpWmiMethod<_MI_Instance>::RunMethod<CSpSubsystem::SetAttributes,13>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18006ad58`
- end: `0x18006b0a6`
- name: `??$RunMethod@VSetAttributes@CSpSubsystem@@$0N@@?$CSpWmiMethod@U_MI_Instance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

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
- `0x18006ad58`
- `0x18006bf9c`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006af24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006af24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006af05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006af05`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006af1a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006af1a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006aeeb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006aeeb`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006afc4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006afc4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006b077`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006b077`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006b069`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006b069`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_MI_Instance>::RunMethod<CSpSubsystem::SetAttributes,13>(
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
  CSpSubsystem::SetAttributes *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpSubsystem::SetAttributes *)operator new(0x170u);
  v7 = CSpSubsystem::SetAttributes::SetAttributes(v25);
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
      v25 = (CSpSubsystem::SetAttributes *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&byte_1803102EF,
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
0x18006ad58  mov     [rsp-38h+arg_18], rbx
0x18006ad5d  push    rbp
0x18006ad5e  push    rsi
0x18006ad5f  push    rdi
0x18006ad60  push    r12
0x18006ad62  push    r13
0x18006ad64  push    r14
0x18006ad66  push    r15
0x18006ad68  mov     rbp, rsp
0x18006ad6b  sub     rsp, 80h
0x18006ad72  mov     rax, cs:__security_cookie
0x18006ad79  xor     rax, rsp
0x18006ad7c  mov     [rbp+var_8], rax
0x18006ad80  xor     eax, eax
0x18006ad82  mov     rsi, rcx
0x18006ad85  xorps   xmm0, xmm0
0x18006ad88  mov     [rbp+var_10], eax
0x18006ad8b  mov     ecx, 170h; Size
0x18006ad90  mov     [rbp+var_40], eax
0x18006ad93  movups  [rbp+var_20], xmm0
0x18006ad97  mov     [rbp+TokenHandle], rax
0x18006ad9b  mov     r12, r8
0x18006ad9e  mov     r13, rdx
0x18006ada1  xor     r14d, r14d
0x18006ada4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006ada9  mov     rcx, rax; this
0x18006adac  mov     [rbp+var_28], rax
0x18006adb0  call    ??0SetAttributes@CSpSubsystem@@QEAA@XZ; CSpSubsystem::SetAttributes::SetAttributes(void)
0x18006adb5  mov     rdi, rax
0x18006adb8  test    rax, rax
0x18006adbb  jnz     short loc_18006ADC5
0x18006adbd  lea     ebx, [rax+1Bh]
0x18006adc0  jmp     loc_18006B060
0x18006adc5  mov     rax, [rax]
0x18006adc8  mov     rdx, rsi
0x18006adcb  mov     rcx, rdi
0x18006adce  xor     r15d, r15d
0x18006add1  mov     rax, [rax+8]
0x18006add5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006adda  lea     rcx, [rbp+var_40]
0x18006adde  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18006ade3  mov     [rdi+1Ch], eax
0x18006ade6  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18006adea  mov     ecx, [rsi+14h]; unsigned int
0x18006aded  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18006adf2  mov     eax, cs:dword_180397B68
0x18006adf8  cmp     eax, 5
0x18006adfb  jbe     short loc_18006AE6B
0x18006adfd  mov     rdx, 400000000000h
0x18006ae07  lea     rcx, dword_180397B68
0x18006ae0e  call    _tlgKeywordOn
0x18006ae13  test    al, al
0x18006ae15  jz      short loc_18006AE6B
0x18006ae17  mov     eax, [rbp+var_40]
0x18006ae1a  lea     rdx, byte_1803102EF
0x18006ae21  xor     ecx, ecx
0x18006ae23  cmp     [rdi+1Ch], eax
0x18006ae26  movzx   eax, word ptr [rbp+var_10]
0x18006ae2a  mov     word ptr [rbp+var_40], ax
0x18006ae2e  setnz   cl
0x18006ae31  mov     eax, [rsi+14h]
0x18006ae34  mov     [rbp+var_38], eax
0x18006ae37  lea     rax, [rbp+var_20]
0x18006ae3b  mov     [rbp+var_28], rax
0x18006ae3f  lea     rax, [rbp+var_3C]
0x18006ae43  mov     [rsp+80h+var_48], rax
0x18006ae48  lea     rax, [rbp+var_40]
0x18006ae4c  mov     [rsp+80h+var_50], rax
0x18006ae51  lea     rax, [rbp+var_38]
0x18006ae55  mov     [rsp+80h+var_58], rax
0x18006ae5a  lea     rax, [rbp+var_28]
0x18006ae5e  mov     [rsp+80h+var_60], rax
0x18006ae63  mov     [rbp+var_3C], ecx
0x18006ae66  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18006ae6b  mov     rcx, [rsi]
0x18006ae6e  test    rcx, rcx
0x18006ae71  jz      loc_18006B036
0x18006ae77  mov     rax, [rcx]
0x18006ae7a  test    rax, rax
0x18006ae7d  jz      loc_18006B036
0x18006ae83  mov     rax, [rax+18h]
0x18006ae87  lea     r8, [rdi+20h]
0x18006ae8b  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18006ae92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ae97  mov     ebx, eax
0x18006ae99  test    eax, eax
0x18006ae9b  jnz     loc_18006B03B
0x18006aea1  cmp     [rsi+10h], r14d
0x18006aea5  jz      loc_18006AFCF
0x18006aeab  lea     rbx, [rdi+148h]
0x18006aeb2  mov     rcx, rbx
0x18006aeb5  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18006aeba  mov     rcx, rbx; struct CSpJobMgr **
0x18006aebd  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18006aec2  test    eax, eax
0x18006aec4  jnz     short loc_18006AECE
0x18006aec6  lea     ebx, [rax+1Ch]
0x18006aec9  jmp     loc_18006B03B
0x18006aece  mov     ecx, 10h; Size
0x18006aed3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006aed8  xor     r8d, r8d; pcbe
0x18006aedb  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18006aee2  mov     rdx, rax; pv
0x18006aee5  mov     r15, rax
0x18006aee8  mov     [rax], rdi
0x18006aeeb  call    cs:__imp_CreateThreadpoolWork
0x18006aef1  mov     r14, rax
0x18006aef4  test    rax, rax
0x18006aef7  jnz     short loc_18006AF05
0x18006aef9  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18006aefe  mov     ebx, eax
0x18006af00  jmp     loc_18006B03B
0x18006af05  call    cs:__imp_GetCurrentThread
0x18006af0b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18006af0f  xor     r8d, r8d; OpenAsSelf
0x18006af12  mov     rcx, rax; ThreadHandle
0x18006af15  mov     edx, 2000Ch; DesiredAccess
0x18006af1a  call    cs:__imp_OpenThreadToken
0x18006af20  test    eax, eax
0x18006af22  jnz     short loc_18006AF31
0x18006af24  call    cs:__imp_GetLastError
0x18006af2a  cmp     eax, 3F0h
0x18006af2f  jnz     short loc_18006AEF9
0x18006af31  mov     rax, [rbp+TokenHandle]
0x18006af35  mov     r8, r13
0x18006af38  mov     [r15+8], rax
0x18006af3c  mov     rcx, rdi
0x18006af3f  mov     rax, [rdi]
0x18006af42  mov     rdx, [rsi+8]
0x18006af46  mov     rax, [rax+18h]
0x18006af4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af4f  mov     rax, [rdi]
0x18006af52  mov     rdx, r12
0x18006af55  mov     rcx, rdi
0x18006af58  mov     rax, [rax+28h]
0x18006af5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af61  mov     ebx, eax
0x18006af63  test    eax, eax
0x18006af65  jz      short loc_18006AF70
0x18006af67  cmp     eax, 7
0x18006af6a  jnz     loc_18006B03B
0x18006af70  mov     rax, [rdi]
0x18006af73  mov     rdx, r12
0x18006af76  mov     rcx, rdi
0x18006af79  mov     rax, [rax+38h]
0x18006af7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af82  mov     ebx, eax
0x18006af84  test    eax, eax
0x18006af86  jnz     loc_18006B03B
0x18006af8c  mov     rax, [rdi+150h]
0x18006af93  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18006af9a  jnz     short loc_18006AFB0
0x18006af9c  mov     rax, [rdi+158h]
0x18006afa3  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18006afaa  jz      loc_18006B03B
0x18006afb0  mov     rdx, r12
0x18006afb3  mov     rcx, rdi
0x18006afb6  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18006afbb  mov     ebx, eax
0x18006afbd  test    eax, eax
0x18006afbf  jnz     short loc_18006B03B
0x18006afc1  mov     rcx, r14; pwk
0x18006afc4  call    cs:__imp_SubmitThreadpoolWork
0x18006afca  jmp     loc_18006B07D
0x18006afcf  mov     rax, [rdi]
0x18006afd2  mov     r8, r13
0x18006afd5  mov     rdx, [rsi+8]
0x18006afd9  mov     rcx, rdi
0x18006afdc  mov     rax, [rax+10h]
0x18006afe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006afe5  mov     rax, [rdi]
0x18006afe8  mov     rdx, r12
0x18006afeb  mov     rcx, rdi
0x18006afee  mov     rax, [rax+30h]
0x18006aff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aff7  mov     ebx, eax
0x18006aff9  test    eax, eax
0x18006affb  jz      short loc_18006B002
0x18006affd  cmp     eax, 7
0x18006b000  jnz     short loc_18006B03B
0x18006b002  mov     rax, [rdi]
0x18006b005  mov     rdx, r12
0x18006b008  mov     rcx, rdi
0x18006b00b  mov     rax, [rax+28h]
0x18006b00f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b014  mov     ebx, eax
0x18006b016  test    eax, eax
0x18006b018  jz      short loc_18006B01F
0x18006b01a  cmp     eax, 7
0x18006b01d  jnz     short loc_18006B03B
0x18006b01f  mov     rax, [rdi]
0x18006b022  mov     rdx, r12
0x18006b025  mov     rcx, rdi
0x18006b028  mov     rax, [rax+38h]
0x18006b02c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b031  jmp     loc_18006AEFE
0x18006b036  mov     ebx, 4
0x18006b03b  mov     rax, [rdi]
0x18006b03e  mov     edx, 1
0x18006b043  mov     rcx, rdi
0x18006b046  mov     rax, [rax]
0x18006b049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b04e  test    r15, r15
0x18006b051  jz      short loc_18006B060
0x18006b053  mov     edx, 10h
0x18006b058  mov     rcx, r15; Block
0x18006b05b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006b060  mov     rcx, [rbp+TokenHandle]; hObject
0x18006b064  test    rcx, rcx
0x18006b067  jz      short loc_18006B06F
0x18006b069  call    cs:__imp_CloseHandle
0x18006b06f  test    r14, r14
0x18006b072  jz      short loc_18006B07D
0x18006b074  mov     rcx, r14; pwk
0x18006b077  call    cs:__imp_CloseThreadpoolWork
0x18006b07d  mov     eax, ebx
0x18006b07f  mov     rcx, [rbp+var_8]
0x18006b083  xor     rcx, rsp; StackCookie
0x18006b086  call    __security_check_cookie
0x18006b08b  mov     rbx, [rsp+80h+arg_18]
0x18006b093  add     rsp, 80h
0x18006b09a  pop     r15
0x18006b09c  pop     r14
0x18006b09e  pop     r13
0x18006b0a0  pop     r12
0x18006b0a2  pop     rdi
0x18006b0a3  pop     rsi
0x18006b0a4  pop     rbp
0x18006b0a5  retn
```
