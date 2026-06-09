# CSpWmiMethod<_MI_Instance>::RunMethod<CSpPhysicalDisk::Maintenance,4>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800eea40`
- end: `0x1800eeda1`
- name: `??$RunMethod@VMaintenance@CSpPhysicalDisk@@$03@?$CSpWmiMethod@U_MI_Instance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `865`
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
- `0x1800eea40`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eec1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eec1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800eebfe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800eebfe`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800eec13`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800eec13`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800eebe4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800eebe4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800eecbe`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800eecbe`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800eed72`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800eed72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800eed64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800eed64`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_MI_Instance>::RunMethod<CSpPhysicalDisk::Maintenance,4>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int128 **v4; // r14
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

  v20 = 0;
  TokenHandle = 0;
  v26 = 0;
  v4 = 0;
  ThreadpoolWork = 0;
  v25 = 0;
  v24 = (__int128 *)operator new(0x178u);
  v8 = v24;
  CSpWmiMethod<_MI_Instance>::CSpWmiMethod<_MI_Instance>(v24);
  *(_QWORD *)v24 = &CSpPhysicalDisk::Maintenance::`vftable';
  *((_DWORD *)v8 + 90) = 0;
  *((_WORD *)v8 + 182) = 0;
  (*(void (__fastcall **)(__int128 *, __int64 *))(*(_QWORD *)v8 + 8LL))(v8, a1);
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
      (unsigned int)&byte_180336567,
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
      v4 = (__int128 **)operator new(0x10u);
      *v4 = v8;
      ThreadpoolWork = CreateThreadpoolWork(
                         CSpWmiMethod<_SPACES_PhysicalDisk_GetPhysicalExtent>::ResumeMethodWorker,
                         v4,
                         0);
      if ( ThreadpoolWork )
      {
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 0x2000Cu, 0, &TokenHandle) || GetLastError() == 1008 )
        {
          v4[1] = (__int128 *)TokenHandle;
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
  if ( v4 )
    operator delete(v4);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( ThreadpoolWork )
    CloseThreadpoolWork(ThreadpoolWork);
  return v13;
}

```

## disassembly

```asm
0x1800eea40  mov     [rsp-38h+arg_18], rbx
0x1800eea45  push    rbp
0x1800eea46  push    rsi
0x1800eea47  push    rdi
0x1800eea48  push    r12
0x1800eea4a  push    r13
0x1800eea4c  push    r14
0x1800eea4e  push    r15
0x1800eea50  mov     rbp, rsp
0x1800eea53  sub     rsp, 80h
0x1800eea5a  mov     rax, cs:__security_cookie
0x1800eea61  xor     rax, rsp
0x1800eea64  mov     [rbp+var_8], rax
0x1800eea68  xor     ebx, ebx
0x1800eea6a  mov     r12, rcx
0x1800eea6d  xorps   xmm0, xmm0
0x1800eea70  mov     [rbp+var_40], ebx
0x1800eea73  xor     eax, eax
0x1800eea75  mov     [rbp+TokenHandle], rbx
0x1800eea79  mov     ecx, 178h; Size
0x1800eea7e  mov     [rbp+var_10], eax
0x1800eea81  mov     r14d, ebx
0x1800eea84  mov     esi, ebx
0x1800eea86  movups  [rbp+var_20], xmm0
0x1800eea8a  mov     r15, r8
0x1800eea8d  mov     r13, rdx
0x1800eea90  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800eea95  mov     rcx, rax
0x1800eea98  mov     [rbp+var_28], rax
0x1800eea9c  mov     rdi, rax
0x1800eea9f  call    ??0?$CSpWmiMethod@U_MI_Instance@@@@QEAA@XZ; CSpWmiMethod<_MI_Instance>::CSpWmiMethod<_MI_Instance>(void)
0x1800eeaa4  lea     rax, ??_7Maintenance@CSpPhysicalDisk@@6B@; const CSpPhysicalDisk::Maintenance::`vftable'
0x1800eeaab  mov     rdx, r12
0x1800eeaae  mov     [rdi], rax
0x1800eeab1  mov     rcx, rdi
0x1800eeab4  mov     [rdi+168h], ebx
0x1800eeaba  mov     [rdi+16Ch], bx
0x1800eeac1  mov     rax, [rdi]
0x1800eeac4  mov     rax, [rax+8]
0x1800eeac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eeacd  lea     rcx, [rbp+var_40]
0x1800eead1  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800eead6  mov     [rdi+1Ch], eax
0x1800eead9  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800eeadd  mov     ecx, [r12+14h]; unsigned int
0x1800eeae2  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800eeae7  mov     eax, cs:dword_180397B68
0x1800eeaed  cmp     eax, 5
0x1800eeaf0  jbe     short loc_1800EEB62
0x1800eeaf2  mov     rdx, 400000000000h
0x1800eeafc  lea     rcx, dword_180397B68
0x1800eeb03  call    _tlgKeywordOn
0x1800eeb08  test    al, al
0x1800eeb0a  jz      short loc_1800EEB62
0x1800eeb0c  mov     eax, [rbp+var_40]
0x1800eeb0f  lea     rdx, byte_180336567
0x1800eeb16  cmp     [rdi+1Ch], eax
0x1800eeb19  mov     ecx, ebx
0x1800eeb1b  movzx   eax, word ptr [rbp+var_10]
0x1800eeb1f  mov     word ptr [rbp+var_40], ax
0x1800eeb23  setnz   cl
0x1800eeb26  mov     eax, [r12+14h]
0x1800eeb2b  mov     [rbp+var_38], eax
0x1800eeb2e  lea     rax, [rbp+var_20]
0x1800eeb32  mov     [rbp+var_28], rax
0x1800eeb36  lea     rax, [rbp+var_3C]
0x1800eeb3a  mov     [rsp+80h+var_48], rax
0x1800eeb3f  lea     rax, [rbp+var_40]
0x1800eeb43  mov     [rsp+80h+var_50], rax
0x1800eeb48  lea     rax, [rbp+var_38]
0x1800eeb4c  mov     [rsp+80h+var_58], rax
0x1800eeb51  lea     rax, [rbp+var_28]
0x1800eeb55  mov     [rsp+80h+var_60], rax
0x1800eeb5a  mov     [rbp+var_3C], ecx
0x1800eeb5d  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800eeb62  mov     rcx, [r12]
0x1800eeb66  test    rcx, rcx
0x1800eeb69  jz      loc_1800EED31
0x1800eeb6f  mov     rax, [rcx]
0x1800eeb72  test    rax, rax
0x1800eeb75  jz      loc_1800EED31
0x1800eeb7b  mov     rax, [rax+18h]
0x1800eeb7f  lea     r8, [rdi+20h]
0x1800eeb83  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800eeb8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eeb8f  mov     ebx, eax
0x1800eeb91  test    eax, eax
0x1800eeb93  jnz     loc_1800EED36
0x1800eeb99  cmp     [r12+10h], esi
0x1800eeb9e  jz      loc_1800EECC9
0x1800eeba4  lea     rbx, [rdi+148h]
0x1800eebab  mov     rcx, rbx
0x1800eebae  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800eebb3  mov     rcx, rbx; struct CSpJobMgr **
0x1800eebb6  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800eebbb  test    eax, eax
0x1800eebbd  jnz     short loc_1800EEBC7
0x1800eebbf  lea     ebx, [rax+1Ch]
0x1800eebc2  jmp     loc_1800EED36
0x1800eebc7  mov     ecx, 10h; Size
0x1800eebcc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800eebd1  xor     r8d, r8d; pcbe
0x1800eebd4  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800eebdb  mov     rdx, rax; pv
0x1800eebde  mov     r14, rax
0x1800eebe1  mov     [rax], rdi
0x1800eebe4  call    cs:__imp_CreateThreadpoolWork
0x1800eebea  mov     rsi, rax
0x1800eebed  test    rax, rax
0x1800eebf0  jnz     short loc_1800EEBFE
0x1800eebf2  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800eebf7  mov     ebx, eax
0x1800eebf9  jmp     loc_1800EED36
0x1800eebfe  call    cs:__imp_GetCurrentThread
0x1800eec04  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800eec08  xor     r8d, r8d; OpenAsSelf
0x1800eec0b  mov     rcx, rax; ThreadHandle
0x1800eec0e  mov     edx, 2000Ch; DesiredAccess
0x1800eec13  call    cs:__imp_OpenThreadToken
0x1800eec19  test    eax, eax
0x1800eec1b  jnz     short loc_1800EEC2A
0x1800eec1d  call    cs:__imp_GetLastError
0x1800eec23  cmp     eax, 3F0h
0x1800eec28  jnz     short loc_1800EEBF2
0x1800eec2a  mov     rax, [rbp+TokenHandle]
0x1800eec2e  mov     r8, r13
0x1800eec31  mov     [r14+8], rax
0x1800eec35  mov     rcx, rdi
0x1800eec38  mov     rax, [rdi]
0x1800eec3b  mov     rdx, [r12+8]
0x1800eec40  mov     rax, [rax+18h]
0x1800eec44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eec49  mov     rax, [rdi]
0x1800eec4c  mov     rdx, r15
0x1800eec4f  mov     rcx, rdi
0x1800eec52  mov     rax, [rax+28h]
0x1800eec56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eec5b  mov     ebx, eax
0x1800eec5d  test    eax, eax
0x1800eec5f  jz      short loc_1800EEC6A
0x1800eec61  cmp     eax, 7
0x1800eec64  jnz     loc_1800EED36
0x1800eec6a  mov     rax, [rdi]
0x1800eec6d  mov     rdx, r15
0x1800eec70  mov     rcx, rdi
0x1800eec73  mov     rax, [rax+38h]
0x1800eec77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eec7c  mov     ebx, eax
0x1800eec7e  test    eax, eax
0x1800eec80  jnz     loc_1800EED36
0x1800eec86  mov     rax, [rdi+150h]
0x1800eec8d  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800eec94  jnz     short loc_1800EECAA
0x1800eec96  mov     rax, [rdi+158h]
0x1800eec9d  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800eeca4  jz      loc_1800EED36
0x1800eecaa  mov     rdx, r15
0x1800eecad  mov     rcx, rdi
0x1800eecb0  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800eecb5  mov     ebx, eax
0x1800eecb7  test    eax, eax
0x1800eecb9  jnz     short loc_1800EED36
0x1800eecbb  mov     rcx, rsi; pwk
0x1800eecbe  call    cs:__imp_SubmitThreadpoolWork
0x1800eecc4  jmp     loc_1800EED78
0x1800eecc9  mov     rax, [rdi]
0x1800eeccc  mov     r8, r13
0x1800eeccf  mov     rdx, [r12+8]
0x1800eecd4  mov     rcx, rdi
0x1800eecd7  mov     rax, [rax+10h]
0x1800eecdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eece0  mov     rax, [rdi]
0x1800eece3  mov     rdx, r15
0x1800eece6  mov     rcx, rdi
0x1800eece9  mov     rax, [rax+30h]
0x1800eeced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eecf2  mov     ebx, eax
0x1800eecf4  test    eax, eax
0x1800eecf6  jz      short loc_1800EECFD
0x1800eecf8  cmp     eax, 7
0x1800eecfb  jnz     short loc_1800EED36
0x1800eecfd  mov     rax, [rdi]
0x1800eed00  mov     rdx, r15
0x1800eed03  mov     rcx, rdi
0x1800eed06  mov     rax, [rax+28h]
0x1800eed0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eed0f  mov     ebx, eax
0x1800eed11  test    eax, eax
0x1800eed13  jz      short loc_1800EED1A
0x1800eed15  cmp     eax, 7
0x1800eed18  jnz     short loc_1800EED36
0x1800eed1a  mov     rax, [rdi]
0x1800eed1d  mov     rdx, r15
0x1800eed20  mov     rcx, rdi
0x1800eed23  mov     rax, [rax+38h]
0x1800eed27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eed2c  jmp     loc_1800EEBF7
0x1800eed31  mov     ebx, 4
0x1800eed36  mov     rax, [rdi]
0x1800eed39  mov     edx, 1
0x1800eed3e  mov     rcx, rdi
0x1800eed41  mov     rax, [rax]
0x1800eed44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eed49  test    r14, r14
0x1800eed4c  jz      short loc_1800EED5B
0x1800eed4e  mov     edx, 10h
0x1800eed53  mov     rcx, r14; Block
0x1800eed56  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800eed5b  mov     rcx, [rbp+TokenHandle]; hObject
0x1800eed5f  test    rcx, rcx
0x1800eed62  jz      short loc_1800EED6A
0x1800eed64  call    cs:__imp_CloseHandle
0x1800eed6a  test    rsi, rsi
0x1800eed6d  jz      short loc_1800EED78
0x1800eed6f  mov     rcx, rsi; pwk
0x1800eed72  call    cs:__imp_CloseThreadpoolWork
0x1800eed78  mov     eax, ebx
0x1800eed7a  mov     rcx, [rbp+var_8]
0x1800eed7e  xor     rcx, rsp; StackCookie
0x1800eed81  call    __security_check_cookie
0x1800eed86  mov     rbx, [rsp+80h+arg_18]
0x1800eed8e  add     rsp, 80h
0x1800eed95  pop     r15
0x1800eed97  pop     r14
0x1800eed99  pop     r13
0x1800eed9b  pop     r12
0x1800eed9d  pop     rdi
0x1800eed9e  pop     rsi
0x1800eed9f  pop     rbp
0x1800eeda0  retn
```
