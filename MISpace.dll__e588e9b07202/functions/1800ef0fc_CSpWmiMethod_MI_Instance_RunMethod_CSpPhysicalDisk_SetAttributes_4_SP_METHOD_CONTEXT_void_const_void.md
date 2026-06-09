# CSpWmiMethod<_MI_Instance>::RunMethod<CSpPhysicalDisk::SetAttributes,4>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800ef0fc`
- end: `0x1800ef44e`
- name: `??$RunMethod@VSetAttributes@CSpPhysicalDisk@@$03@?$CSpWmiMethod@U_MI_Instance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `850`
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
- `0x18006baa8`
- `0x1800ef0fc`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef2ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef2ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ef2ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ef2ab`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ef2c0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ef2c0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ef291`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ef291`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800ef36b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800ef36b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ef41f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ef41f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ef411`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ef411`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_MI_Instance>::RunMethod<CSpPhysicalDisk::SetAttributes,4>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int128 **v6; // r14
  struct _TP_WORK *ThreadpoolWork; // rsi
  __int128 *v8; // rdi
  int v9; // r8d
  int v10; // r9d
  bool v11; // zf
  __int64 v12; // rcx
  unsigned int v13; // ebx
  enum _MI_Result v14; // eax
  HANDLE CurrentThread; // rax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  int v20; // [rsp+40h] [rbp-40h] BYREF
  BOOL v21; // [rsp+44h] [rbp-3Ch] BYREF
  int v22; // [rsp+48h] [rbp-38h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-30h] BYREF
  __int128 *v24; // [rsp+58h] [rbp-28h] BYREF
  __int128 v25; // [rsp+60h] [rbp-20h] BYREF
  int v26; // [rsp+70h] [rbp-10h]

  v26 = 0;
  v20 = 0;
  v25 = 0;
  TokenHandle = 0;
  v6 = 0;
  ThreadpoolWork = 0;
  v24 = (__int128 *)operator new(0x160u);
  v8 = v24;
  CSpWmiMethod<_MI_Instance>::CSpWmiMethod<_MI_Instance>(v24);
  *(_QWORD *)v24 = &CSpPhysicalDisk::SetAttributes::`vftable';
  ((void (__fastcall *)(__int128 *, __int64 *))CSpWmiMethod<_SPACES_PhysicalDisk_GetPhysicalExtent>::SetContext)(v8, a1);
  *((_DWORD *)v8 + 7) = _GetSubsystemVersion(&v20);
  WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v25);
  if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
  {
    v11 = *((_DWORD *)v8 + 7) == v20;
    LOWORD(v20) = v26;
    v22 = *((_DWORD *)a1 + 5);
    v24 = &v25;
    v21 = !v11;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      v21,
      (unsigned int)byte_1803377C9,
      v9,
      v10,
      (__int64)&v24,
      (__int64)&v22,
      (__int64)&v20,
      (__int64)&v21);
  }
  v12 = *a1;
  if ( !*a1 || !*(_QWORD *)v12 )
  {
    v13 = 4;
    goto LABEL_28;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD *))(*(_QWORD *)v12 + 24LL))(
          v12,
          &MSFT_StorageExtendedStatus_rtti,
          (_QWORD *)v8 + 4);
  if ( !v13 )
  {
    if ( *((_DWORD *)a1 + 4) )
    {
      CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release((char *)v8 + 328);
      if ( !(unsigned int)CSpJobMgr::GetInstance((struct CSpJobMgr **)v8 + 41) )
      {
        v13 = 28;
        goto LABEL_28;
      }
      v6 = (__int128 **)operator new(0x10u);
      *v6 = v8;
      ThreadpoolWork = CreateThreadpoolWork(
                         CSpWmiMethod<_SPACES_PhysicalDisk_GetPhysicalExtent>::ResumeMethodWorker,
                         v6,
                         0);
      if ( ThreadpoolWork )
      {
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 0x2000Cu, 0, &TokenHandle) || GetLastError() == 1008 )
        {
          v6[1] = (__int128 *)TokenHandle;
          (*(void (__fastcall **)(__int128 *, __int64, __int64))(*(_QWORD *)v8 + 24LL))(v8, a1[1], a2);
          v16 = (*(__int64 (__fastcall **)(__int128 *, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
          v13 = v16;
          if ( !v16 || v16 == 7 )
          {
            v13 = (*(__int64 (__fastcall **)(__int128 *, __int64))(*(_QWORD *)v8 + 56LL))(v8, a3);
            if ( !v13
              && (*((_QWORD *)v8 + 42) != *(_QWORD *)&GUID_NULL.Data1
               || *((_QWORD *)v8 + 43) != *(_QWORD *)GUID_NULL.Data4) )
            {
              v13 = CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(v8, a3);
              if ( !v13 )
              {
                SubmitThreadpoolWork(ThreadpoolWork);
                return v13;
              }
            }
          }
          goto LABEL_28;
        }
      }
      v14 = GleToMiResult();
    }
    else
    {
      (*(void (__fastcall **)(__int128 *, __int64, __int64))(*(_QWORD *)v8 + 16LL))(v8, a1[1], a2);
      v17 = (*(__int64 (__fastcall **)(__int128 *, __int64))(*(_QWORD *)v8 + 48LL))(v8, a3);
      v13 = v17;
      if ( v17 && v17 != 7 )
        goto LABEL_28;
      v18 = (*(__int64 (__fastcall **)(__int128 *, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
      v13 = v18;
      if ( v18 )
      {
        if ( v18 != 7 )
          goto LABEL_28;
      }
      v14 = (*(unsigned int (__fastcall **)(__int128 *, __int64))(*(_QWORD *)v8 + 56LL))(v8, a3);
    }
    v13 = v14;
  }
LABEL_28:
  (**(void (__fastcall ***)(__int128 *, __int64))v8)(v8, 1);
  if ( v6 )
    operator delete(v6);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( ThreadpoolWork )
    CloseThreadpoolWork(ThreadpoolWork);
  return v13;
}

```

## disassembly

```asm
0x1800ef0fc  mov     [rsp-38h+arg_18], rbx
0x1800ef101  push    rbp
0x1800ef102  push    rsi
0x1800ef103  push    rdi
0x1800ef104  push    r12
0x1800ef106  push    r13
0x1800ef108  push    r14
0x1800ef10a  push    r15
0x1800ef10c  mov     rbp, rsp
0x1800ef10f  sub     rsp, 80h
0x1800ef116  mov     rax, cs:__security_cookie
0x1800ef11d  xor     rax, rsp
0x1800ef120  mov     [rbp+var_8], rax
0x1800ef124  xor     eax, eax
0x1800ef126  mov     r12, rcx
0x1800ef129  xorps   xmm0, xmm0
0x1800ef12c  mov     [rbp+var_10], eax
0x1800ef12f  mov     ecx, 160h; Size
0x1800ef134  mov     [rbp+var_40], eax
0x1800ef137  movups  [rbp+var_20], xmm0
0x1800ef13b  mov     [rbp+TokenHandle], rax
0x1800ef13f  mov     r15, r8
0x1800ef142  mov     r13, rdx
0x1800ef145  xor     r14d, r14d
0x1800ef148  xor     esi, esi
0x1800ef14a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ef14f  mov     rcx, rax
0x1800ef152  mov     [rbp+var_28], rax
0x1800ef156  mov     rdi, rax
0x1800ef159  call    ??0?$CSpWmiMethod@U_MI_Instance@@@@QEAA@XZ; CSpWmiMethod<_MI_Instance>::CSpWmiMethod<_MI_Instance>(void)
0x1800ef15e  lea     rax, ??_7SetAttributes@CSpPhysicalDisk@@6B@; const CSpPhysicalDisk::SetAttributes::`vftable'
0x1800ef165  mov     rdx, r12
0x1800ef168  mov     [rdi], rax
0x1800ef16b  mov     rcx, rdi
0x1800ef16e  mov     rax, cs:off_180202D80
0x1800ef175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef17a  lea     rcx, [rbp+var_40]
0x1800ef17e  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800ef183  mov     [rdi+1Ch], eax
0x1800ef186  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800ef18a  mov     ecx, [r12+14h]; unsigned int
0x1800ef18f  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800ef194  mov     eax, cs:dword_180397B68
0x1800ef19a  cmp     eax, 5
0x1800ef19d  jbe     short loc_1800EF20F
0x1800ef19f  mov     rdx, 400000000000h
0x1800ef1a9  lea     rcx, dword_180397B68
0x1800ef1b0  call    _tlgKeywordOn
0x1800ef1b5  test    al, al
0x1800ef1b7  jz      short loc_1800EF20F
0x1800ef1b9  mov     eax, [rbp+var_40]
0x1800ef1bc  lea     rdx, byte_1803377C9
0x1800ef1c3  xor     ecx, ecx
0x1800ef1c5  cmp     [rdi+1Ch], eax
0x1800ef1c8  movzx   eax, word ptr [rbp+var_10]
0x1800ef1cc  mov     word ptr [rbp+var_40], ax
0x1800ef1d0  setnz   cl
0x1800ef1d3  mov     eax, [r12+14h]
0x1800ef1d8  mov     [rbp+var_38], eax
0x1800ef1db  lea     rax, [rbp+var_20]
0x1800ef1df  mov     [rbp+var_28], rax
0x1800ef1e3  lea     rax, [rbp+var_3C]
0x1800ef1e7  mov     [rsp+80h+var_48], rax
0x1800ef1ec  lea     rax, [rbp+var_40]
0x1800ef1f0  mov     [rsp+80h+var_50], rax
0x1800ef1f5  lea     rax, [rbp+var_38]
0x1800ef1f9  mov     [rsp+80h+var_58], rax
0x1800ef1fe  lea     rax, [rbp+var_28]
0x1800ef202  mov     [rsp+80h+var_60], rax
0x1800ef207  mov     [rbp+var_3C], ecx
0x1800ef20a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800ef20f  mov     rcx, [r12]
0x1800ef213  test    rcx, rcx
0x1800ef216  jz      loc_1800EF3DE
0x1800ef21c  mov     rax, [rcx]
0x1800ef21f  test    rax, rax
0x1800ef222  jz      loc_1800EF3DE
0x1800ef228  mov     rax, [rax+18h]
0x1800ef22c  lea     r8, [rdi+20h]
0x1800ef230  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800ef237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef23c  mov     ebx, eax
0x1800ef23e  test    eax, eax
0x1800ef240  jnz     loc_1800EF3E3
0x1800ef246  cmp     [r12+10h], esi
0x1800ef24b  jz      loc_1800EF376
0x1800ef251  lea     rbx, [rdi+148h]
0x1800ef258  mov     rcx, rbx
0x1800ef25b  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800ef260  mov     rcx, rbx; struct CSpJobMgr **
0x1800ef263  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800ef268  test    eax, eax
0x1800ef26a  jnz     short loc_1800EF274
0x1800ef26c  lea     ebx, [rax+1Ch]
0x1800ef26f  jmp     loc_1800EF3E3
0x1800ef274  mov     ecx, 10h; Size
0x1800ef279  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ef27e  xor     r8d, r8d; pcbe
0x1800ef281  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800ef288  mov     rdx, rax; pv
0x1800ef28b  mov     r14, rax
0x1800ef28e  mov     [rax], rdi
0x1800ef291  call    cs:__imp_CreateThreadpoolWork
0x1800ef297  mov     rsi, rax
0x1800ef29a  test    rax, rax
0x1800ef29d  jnz     short loc_1800EF2AB
0x1800ef29f  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800ef2a4  mov     ebx, eax
0x1800ef2a6  jmp     loc_1800EF3E3
0x1800ef2ab  call    cs:__imp_GetCurrentThread
0x1800ef2b1  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800ef2b5  xor     r8d, r8d; OpenAsSelf
0x1800ef2b8  mov     rcx, rax; ThreadHandle
0x1800ef2bb  mov     edx, 2000Ch; DesiredAccess
0x1800ef2c0  call    cs:__imp_OpenThreadToken
0x1800ef2c6  test    eax, eax
0x1800ef2c8  jnz     short loc_1800EF2D7
0x1800ef2ca  call    cs:__imp_GetLastError
0x1800ef2d0  cmp     eax, 3F0h
0x1800ef2d5  jnz     short loc_1800EF29F
0x1800ef2d7  mov     rax, [rbp+TokenHandle]
0x1800ef2db  mov     r8, r13
0x1800ef2de  mov     [r14+8], rax
0x1800ef2e2  mov     rcx, rdi
0x1800ef2e5  mov     rax, [rdi]
0x1800ef2e8  mov     rdx, [r12+8]
0x1800ef2ed  mov     rax, [rax+18h]
0x1800ef2f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef2f6  mov     rax, [rdi]
0x1800ef2f9  mov     rdx, r15
0x1800ef2fc  mov     rcx, rdi
0x1800ef2ff  mov     rax, [rax+28h]
0x1800ef303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef308  mov     ebx, eax
0x1800ef30a  test    eax, eax
0x1800ef30c  jz      short loc_1800EF317
0x1800ef30e  cmp     eax, 7
0x1800ef311  jnz     loc_1800EF3E3
0x1800ef317  mov     rax, [rdi]
0x1800ef31a  mov     rdx, r15
0x1800ef31d  mov     rcx, rdi
0x1800ef320  mov     rax, [rax+38h]
0x1800ef324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef329  mov     ebx, eax
0x1800ef32b  test    eax, eax
0x1800ef32d  jnz     loc_1800EF3E3
0x1800ef333  mov     rax, [rdi+150h]
0x1800ef33a  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800ef341  jnz     short loc_1800EF357
0x1800ef343  mov     rax, [rdi+158h]
0x1800ef34a  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800ef351  jz      loc_1800EF3E3
0x1800ef357  mov     rdx, r15
0x1800ef35a  mov     rcx, rdi
0x1800ef35d  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800ef362  mov     ebx, eax
0x1800ef364  test    eax, eax
0x1800ef366  jnz     short loc_1800EF3E3
0x1800ef368  mov     rcx, rsi; pwk
0x1800ef36b  call    cs:__imp_SubmitThreadpoolWork
0x1800ef371  jmp     loc_1800EF425
0x1800ef376  mov     rax, [rdi]
0x1800ef379  mov     r8, r13
0x1800ef37c  mov     rdx, [r12+8]
0x1800ef381  mov     rcx, rdi
0x1800ef384  mov     rax, [rax+10h]
0x1800ef388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef38d  mov     rax, [rdi]
0x1800ef390  mov     rdx, r15
0x1800ef393  mov     rcx, rdi
0x1800ef396  mov     rax, [rax+30h]
0x1800ef39a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef39f  mov     ebx, eax
0x1800ef3a1  test    eax, eax
0x1800ef3a3  jz      short loc_1800EF3AA
0x1800ef3a5  cmp     eax, 7
0x1800ef3a8  jnz     short loc_1800EF3E3
0x1800ef3aa  mov     rax, [rdi]
0x1800ef3ad  mov     rdx, r15
0x1800ef3b0  mov     rcx, rdi
0x1800ef3b3  mov     rax, [rax+28h]
0x1800ef3b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef3bc  mov     ebx, eax
0x1800ef3be  test    eax, eax
0x1800ef3c0  jz      short loc_1800EF3C7
0x1800ef3c2  cmp     eax, 7
0x1800ef3c5  jnz     short loc_1800EF3E3
0x1800ef3c7  mov     rax, [rdi]
0x1800ef3ca  mov     rdx, r15
0x1800ef3cd  mov     rcx, rdi
0x1800ef3d0  mov     rax, [rax+38h]
0x1800ef3d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef3d9  jmp     loc_1800EF2A4
0x1800ef3de  mov     ebx, 4
0x1800ef3e3  mov     rax, [rdi]
0x1800ef3e6  mov     edx, 1
0x1800ef3eb  mov     rcx, rdi
0x1800ef3ee  mov     rax, [rax]
0x1800ef3f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef3f6  test    r14, r14
0x1800ef3f9  jz      short loc_1800EF408
0x1800ef3fb  mov     edx, 10h
0x1800ef400  mov     rcx, r14; Block
0x1800ef403  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ef408  mov     rcx, [rbp+TokenHandle]; hObject
0x1800ef40c  test    rcx, rcx
0x1800ef40f  jz      short loc_1800EF417
0x1800ef411  call    cs:__imp_CloseHandle
0x1800ef417  test    rsi, rsi
0x1800ef41a  jz      short loc_1800EF425
0x1800ef41c  mov     rcx, rsi; pwk
0x1800ef41f  call    cs:__imp_CloseThreadpoolWork
0x1800ef425  mov     eax, ebx
0x1800ef427  mov     rcx, [rbp+var_8]
0x1800ef42b  xor     rcx, rsp; StackCookie
0x1800ef42e  call    __security_check_cookie
0x1800ef433  mov     rbx, [rsp+80h+arg_18]
0x1800ef43b  add     rsp, 80h
0x1800ef442  pop     r15
0x1800ef444  pop     r14
0x1800ef446  pop     r13
0x1800ef448  pop     r12
0x1800ef44a  pop     rdi
0x1800ef44b  pop     rsi
0x1800ef44c  pop     rbp
0x1800ef44d  retn
```
