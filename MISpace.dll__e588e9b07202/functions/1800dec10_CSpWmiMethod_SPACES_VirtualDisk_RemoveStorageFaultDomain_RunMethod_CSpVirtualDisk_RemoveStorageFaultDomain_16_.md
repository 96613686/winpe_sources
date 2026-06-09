# CSpWmiMethod<_SPACES_VirtualDisk_RemoveStorageFaultDomain>::RunMethod<CSpVirtualDisk::RemoveStorageFaultDomain,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800dec10`
- end: `0x1800def5e`
- name: `??$RunMethod@VRemoveStorageFaultDomain@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_RemoveStorageFaultDomain@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800dec10`
- `0x1800e0a40`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800deddc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800deddc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dedbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dedbd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dedd2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dedd2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800deda3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800deda3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800dee7c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800dee7c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800def2f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800def2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800def21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800def21`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_RemoveStorageFaultDomain>::RunMethod<CSpVirtualDisk::RemoveStorageFaultDomain,16>(
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
  CSpVirtualDisk::RemoveStorageFaultDomain *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::RemoveStorageFaultDomain *)operator new(0x160u);
  v7 = CSpVirtualDisk::RemoveStorageFaultDomain::RemoveStorageFaultDomain(v25);
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
      v25 = (CSpVirtualDisk::RemoveStorageFaultDomain *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&byte_180330A0F,
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
0x1800dec10  mov     [rsp-38h+arg_18], rbx
0x1800dec15  push    rbp
0x1800dec16  push    rsi
0x1800dec17  push    rdi
0x1800dec18  push    r12
0x1800dec1a  push    r13
0x1800dec1c  push    r14
0x1800dec1e  push    r15
0x1800dec20  mov     rbp, rsp
0x1800dec23  sub     rsp, 80h
0x1800dec2a  mov     rax, cs:__security_cookie
0x1800dec31  xor     rax, rsp
0x1800dec34  mov     [rbp+var_8], rax
0x1800dec38  xor     eax, eax
0x1800dec3a  mov     rsi, rcx
0x1800dec3d  xorps   xmm0, xmm0
0x1800dec40  mov     [rbp+var_10], eax
0x1800dec43  mov     ecx, 160h; Size
0x1800dec48  mov     [rbp+var_40], eax
0x1800dec4b  movups  [rbp+var_20], xmm0
0x1800dec4f  mov     [rbp+TokenHandle], rax
0x1800dec53  mov     r12, r8
0x1800dec56  mov     r13, rdx
0x1800dec59  xor     r14d, r14d
0x1800dec5c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800dec61  mov     rcx, rax; this
0x1800dec64  mov     [rbp+var_28], rax
0x1800dec68  call    ??0RemoveStorageFaultDomain@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::RemoveStorageFaultDomain::RemoveStorageFaultDomain(void)
0x1800dec6d  mov     rdi, rax
0x1800dec70  test    rax, rax
0x1800dec73  jnz     short loc_1800DEC7D
0x1800dec75  lea     ebx, [rax+1Bh]
0x1800dec78  jmp     loc_1800DEF18
0x1800dec7d  mov     rax, [rax]
0x1800dec80  mov     rdx, rsi
0x1800dec83  mov     rcx, rdi
0x1800dec86  xor     r15d, r15d
0x1800dec89  mov     rax, [rax+8]
0x1800dec8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dec92  lea     rcx, [rbp+var_40]
0x1800dec96  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800dec9b  mov     [rdi+1Ch], eax
0x1800dec9e  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800deca2  mov     ecx, [rsi+14h]; unsigned int
0x1800deca5  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800decaa  mov     eax, cs:dword_180397B68
0x1800decb0  cmp     eax, 5
0x1800decb3  jbe     short loc_1800DED23
0x1800decb5  mov     rdx, 400000000000h
0x1800decbf  lea     rcx, dword_180397B68
0x1800decc6  call    _tlgKeywordOn
0x1800deccb  test    al, al
0x1800deccd  jz      short loc_1800DED23
0x1800deccf  mov     eax, [rbp+var_40]
0x1800decd2  lea     rdx, byte_180330A0F
0x1800decd9  xor     ecx, ecx
0x1800decdb  cmp     [rdi+1Ch], eax
0x1800decde  movzx   eax, word ptr [rbp+var_10]
0x1800dece2  mov     word ptr [rbp+var_40], ax
0x1800dece6  setnz   cl
0x1800dece9  mov     eax, [rsi+14h]
0x1800decec  mov     [rbp+var_38], eax
0x1800decef  lea     rax, [rbp+var_20]
0x1800decf3  mov     [rbp+var_28], rax
0x1800decf7  lea     rax, [rbp+var_3C]
0x1800decfb  mov     [rsp+80h+var_48], rax
0x1800ded00  lea     rax, [rbp+var_40]
0x1800ded04  mov     [rsp+80h+var_50], rax
0x1800ded09  lea     rax, [rbp+var_38]
0x1800ded0d  mov     [rsp+80h+var_58], rax
0x1800ded12  lea     rax, [rbp+var_28]
0x1800ded16  mov     [rsp+80h+var_60], rax
0x1800ded1b  mov     [rbp+var_3C], ecx
0x1800ded1e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800ded23  mov     rcx, [rsi]
0x1800ded26  test    rcx, rcx
0x1800ded29  jz      loc_1800DEEEE
0x1800ded2f  mov     rax, [rcx]
0x1800ded32  test    rax, rax
0x1800ded35  jz      loc_1800DEEEE
0x1800ded3b  mov     rax, [rax+18h]
0x1800ded3f  lea     r8, [rdi+20h]
0x1800ded43  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800ded4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ded4f  mov     ebx, eax
0x1800ded51  test    eax, eax
0x1800ded53  jnz     loc_1800DEEF3
0x1800ded59  cmp     [rsi+10h], r14d
0x1800ded5d  jz      loc_1800DEE87
0x1800ded63  lea     rbx, [rdi+148h]
0x1800ded6a  mov     rcx, rbx
0x1800ded6d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800ded72  mov     rcx, rbx; struct CSpJobMgr **
0x1800ded75  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800ded7a  test    eax, eax
0x1800ded7c  jnz     short loc_1800DED86
0x1800ded7e  lea     ebx, [rax+1Ch]
0x1800ded81  jmp     loc_1800DEEF3
0x1800ded86  mov     ecx, 10h; Size
0x1800ded8b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ded90  xor     r8d, r8d; pcbe
0x1800ded93  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800ded9a  mov     rdx, rax; pv
0x1800ded9d  mov     r15, rax
0x1800deda0  mov     [rax], rdi
0x1800deda3  call    cs:__imp_CreateThreadpoolWork
0x1800deda9  mov     r14, rax
0x1800dedac  test    rax, rax
0x1800dedaf  jnz     short loc_1800DEDBD
0x1800dedb1  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800dedb6  mov     ebx, eax
0x1800dedb8  jmp     loc_1800DEEF3
0x1800dedbd  call    cs:__imp_GetCurrentThread
0x1800dedc3  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800dedc7  xor     r8d, r8d; OpenAsSelf
0x1800dedca  mov     rcx, rax; ThreadHandle
0x1800dedcd  mov     edx, 2000Ch; DesiredAccess
0x1800dedd2  call    cs:__imp_OpenThreadToken
0x1800dedd8  test    eax, eax
0x1800dedda  jnz     short loc_1800DEDE9
0x1800deddc  call    cs:__imp_GetLastError
0x1800dede2  cmp     eax, 3F0h
0x1800dede7  jnz     short loc_1800DEDB1
0x1800dede9  mov     rax, [rbp+TokenHandle]
0x1800deded  mov     r8, r13
0x1800dedf0  mov     [r15+8], rax
0x1800dedf4  mov     rcx, rdi
0x1800dedf7  mov     rax, [rdi]
0x1800dedfa  mov     rdx, [rsi+8]
0x1800dedfe  mov     rax, [rax+18h]
0x1800dee02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dee07  mov     rax, [rdi]
0x1800dee0a  mov     rdx, r12
0x1800dee0d  mov     rcx, rdi
0x1800dee10  mov     rax, [rax+28h]
0x1800dee14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dee19  mov     ebx, eax
0x1800dee1b  test    eax, eax
0x1800dee1d  jz      short loc_1800DEE28
0x1800dee1f  cmp     eax, 7
0x1800dee22  jnz     loc_1800DEEF3
0x1800dee28  mov     rax, [rdi]
0x1800dee2b  mov     rdx, r12
0x1800dee2e  mov     rcx, rdi
0x1800dee31  mov     rax, [rax+38h]
0x1800dee35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dee3a  mov     ebx, eax
0x1800dee3c  test    eax, eax
0x1800dee3e  jnz     loc_1800DEEF3
0x1800dee44  mov     rax, [rdi+150h]
0x1800dee4b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800dee52  jnz     short loc_1800DEE68
0x1800dee54  mov     rax, [rdi+158h]
0x1800dee5b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800dee62  jz      loc_1800DEEF3
0x1800dee68  mov     rdx, r12
0x1800dee6b  mov     rcx, rdi
0x1800dee6e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800dee73  mov     ebx, eax
0x1800dee75  test    eax, eax
0x1800dee77  jnz     short loc_1800DEEF3
0x1800dee79  mov     rcx, r14; pwk
0x1800dee7c  call    cs:__imp_SubmitThreadpoolWork
0x1800dee82  jmp     loc_1800DEF35
0x1800dee87  mov     rax, [rdi]
0x1800dee8a  mov     r8, r13
0x1800dee8d  mov     rdx, [rsi+8]
0x1800dee91  mov     rcx, rdi
0x1800dee94  mov     rax, [rax+10h]
0x1800dee98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dee9d  mov     rax, [rdi]
0x1800deea0  mov     rdx, r12
0x1800deea3  mov     rcx, rdi
0x1800deea6  mov     rax, [rax+30h]
0x1800deeaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800deeaf  mov     ebx, eax
0x1800deeb1  test    eax, eax
0x1800deeb3  jz      short loc_1800DEEBA
0x1800deeb5  cmp     eax, 7
0x1800deeb8  jnz     short loc_1800DEEF3
0x1800deeba  mov     rax, [rdi]
0x1800deebd  mov     rdx, r12
0x1800deec0  mov     rcx, rdi
0x1800deec3  mov     rax, [rax+28h]
0x1800deec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800deecc  mov     ebx, eax
0x1800deece  test    eax, eax
0x1800deed0  jz      short loc_1800DEED7
0x1800deed2  cmp     eax, 7
0x1800deed5  jnz     short loc_1800DEEF3
0x1800deed7  mov     rax, [rdi]
0x1800deeda  mov     rdx, r12
0x1800deedd  mov     rcx, rdi
0x1800deee0  mov     rax, [rax+38h]
0x1800deee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800deee9  jmp     loc_1800DEDB6
0x1800deeee  mov     ebx, 4
0x1800deef3  mov     rax, [rdi]
0x1800deef6  mov     edx, 1
0x1800deefb  mov     rcx, rdi
0x1800deefe  mov     rax, [rax]
0x1800def01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800def06  test    r15, r15
0x1800def09  jz      short loc_1800DEF18
0x1800def0b  mov     edx, 10h
0x1800def10  mov     rcx, r15; Block
0x1800def13  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800def18  mov     rcx, [rbp+TokenHandle]; hObject
0x1800def1c  test    rcx, rcx
0x1800def1f  jz      short loc_1800DEF27
0x1800def21  call    cs:__imp_CloseHandle
0x1800def27  test    r14, r14
0x1800def2a  jz      short loc_1800DEF35
0x1800def2c  mov     rcx, r14; pwk
0x1800def2f  call    cs:__imp_CloseThreadpoolWork
0x1800def35  mov     eax, ebx
0x1800def37  mov     rcx, [rbp+var_8]
0x1800def3b  xor     rcx, rsp; StackCookie
0x1800def3e  call    __security_check_cookie
0x1800def43  mov     rbx, [rsp+80h+arg_18]
0x1800def4b  add     rsp, 80h
0x1800def52  pop     r15
0x1800def54  pop     r14
0x1800def56  pop     r13
0x1800def58  pop     r12
0x1800def5a  pop     rdi
0x1800def5b  pop     rsi
0x1800def5c  pop     rbp
0x1800def5d  retn
```
