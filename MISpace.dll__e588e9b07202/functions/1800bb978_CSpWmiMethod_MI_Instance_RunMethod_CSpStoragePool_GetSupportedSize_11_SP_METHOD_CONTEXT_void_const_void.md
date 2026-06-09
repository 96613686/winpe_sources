# CSpWmiMethod<_MI_Instance>::RunMethod<CSpStoragePool::GetSupportedSize,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800bb978`
- end: `0x1800bbce0`
- name: `??$RunMethod@VGetSupportedSize@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_MI_Instance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `872`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800c1f80`

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
- `0x1800bb978`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbb5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbb5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bbb3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bbb3d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bbb52`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bbb52`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bbb23`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bbb23`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bbbfd`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bbbfd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bbcb1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bbcb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bbca3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bbca3`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_MI_Instance>::RunMethod<CSpStoragePool::GetSupportedSize,11>(
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
  v24 = (__int128 *)operator new(0x188u);
  v8 = v24;
  CSpWmiMethod<_MI_Instance>::CSpWmiMethod<_MI_Instance>(v24);
  *((_QWORD *)v24 + 44) = 0;
  *(_QWORD *)v8 = &CSpStoragePool::GetSupportedSize::`vftable';
  *((_BYTE *)v8 + 360) = 0;
  *((_WORD *)v8 + 181) = 0;
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
      (unsigned int)&dword_18032C104,
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
  v13 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int128 *))(*(_QWORD *)v12 + 24LL))(
          v12,
          &MSFT_StorageExtendedStatus_rtti,
          v8 + 2);
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
0x1800bb978  mov     [rsp-38h+arg_18], rbx
0x1800bb97d  push    rbp
0x1800bb97e  push    rsi
0x1800bb97f  push    rdi
0x1800bb980  push    r12
0x1800bb982  push    r13
0x1800bb984  push    r14
0x1800bb986  push    r15
0x1800bb988  mov     rbp, rsp
0x1800bb98b  sub     rsp, 80h
0x1800bb992  mov     rax, cs:__security_cookie
0x1800bb999  xor     rax, rsp
0x1800bb99c  mov     [rbp+var_8], rax
0x1800bb9a0  xor     ebx, ebx
0x1800bb9a2  mov     r12, rcx
0x1800bb9a5  xorps   xmm0, xmm0
0x1800bb9a8  mov     [rbp+var_40], ebx
0x1800bb9ab  xor     eax, eax
0x1800bb9ad  mov     [rbp+TokenHandle], rbx
0x1800bb9b1  mov     ecx, 188h; Size
0x1800bb9b6  mov     [rbp+var_10], eax
0x1800bb9b9  mov     r14d, ebx
0x1800bb9bc  mov     esi, ebx
0x1800bb9be  movups  [rbp+var_20], xmm0
0x1800bb9c2  mov     r15, r8
0x1800bb9c5  mov     r13, rdx
0x1800bb9c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bb9cd  mov     rcx, rax
0x1800bb9d0  mov     [rbp+var_28], rax
0x1800bb9d4  mov     rdi, rax
0x1800bb9d7  call    ??0?$CSpWmiMethod@U_MI_Instance@@@@QEAA@XZ; CSpWmiMethod<_MI_Instance>::CSpWmiMethod<_MI_Instance>(void)
0x1800bb9dc  mov     [rdi+160h], rbx
0x1800bb9e3  lea     rax, ??_7GetSupportedSize@CSpStoragePool@@6B@; const CSpStoragePool::GetSupportedSize::`vftable'
0x1800bb9ea  mov     [rdi], rax
0x1800bb9ed  mov     rdx, r12
0x1800bb9f0  mov     [rdi+168h], bl
0x1800bb9f6  mov     rcx, rdi
0x1800bb9f9  mov     [rdi+16Ah], bx
0x1800bba00  mov     rax, [rdi]
0x1800bba03  mov     rax, [rax+8]
0x1800bba07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bba0c  lea     rcx, [rbp+var_40]
0x1800bba10  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800bba15  mov     [rdi+1Ch], eax
0x1800bba18  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800bba1c  mov     ecx, [r12+14h]; unsigned int
0x1800bba21  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800bba26  mov     eax, cs:dword_180397B68
0x1800bba2c  cmp     eax, 5
0x1800bba2f  jbe     short loc_1800BBAA1
0x1800bba31  mov     rdx, 400000000000h
0x1800bba3b  lea     rcx, dword_180397B68
0x1800bba42  call    _tlgKeywordOn
0x1800bba47  test    al, al
0x1800bba49  jz      short loc_1800BBAA1
0x1800bba4b  mov     eax, [rbp+var_40]
0x1800bba4e  lea     rdx, dword_18032C104
0x1800bba55  cmp     [rdi+1Ch], eax
0x1800bba58  mov     ecx, ebx
0x1800bba5a  movzx   eax, word ptr [rbp+var_10]
0x1800bba5e  mov     word ptr [rbp+var_40], ax
0x1800bba62  setnz   cl
0x1800bba65  mov     eax, [r12+14h]
0x1800bba6a  mov     [rbp+var_38], eax
0x1800bba6d  lea     rax, [rbp+var_20]
0x1800bba71  mov     [rbp+var_28], rax
0x1800bba75  lea     rax, [rbp+var_3C]
0x1800bba79  mov     [rsp+80h+var_48], rax
0x1800bba7e  lea     rax, [rbp+var_40]
0x1800bba82  mov     [rsp+80h+var_50], rax
0x1800bba87  lea     rax, [rbp+var_38]
0x1800bba8b  mov     [rsp+80h+var_58], rax
0x1800bba90  lea     rax, [rbp+var_28]
0x1800bba94  mov     [rsp+80h+var_60], rax
0x1800bba99  mov     [rbp+var_3C], ecx
0x1800bba9c  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800bbaa1  mov     rcx, [r12]
0x1800bbaa5  test    rcx, rcx
0x1800bbaa8  jz      loc_1800BBC70
0x1800bbaae  mov     rax, [rcx]
0x1800bbab1  test    rax, rax
0x1800bbab4  jz      loc_1800BBC70
0x1800bbaba  mov     rax, [rax+18h]
0x1800bbabe  lea     r8, [rdi+20h]
0x1800bbac2  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800bbac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbace  mov     ebx, eax
0x1800bbad0  test    eax, eax
0x1800bbad2  jnz     loc_1800BBC75
0x1800bbad8  cmp     [r12+10h], esi
0x1800bbadd  jz      loc_1800BBC08
0x1800bbae3  lea     rbx, [rdi+148h]
0x1800bbaea  mov     rcx, rbx
0x1800bbaed  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800bbaf2  mov     rcx, rbx; struct CSpJobMgr **
0x1800bbaf5  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800bbafa  test    eax, eax
0x1800bbafc  jnz     short loc_1800BBB06
0x1800bbafe  lea     ebx, [rax+1Ch]
0x1800bbb01  jmp     loc_1800BBC75
0x1800bbb06  mov     ecx, 10h; Size
0x1800bbb0b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bbb10  xor     r8d, r8d; pcbe
0x1800bbb13  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800bbb1a  mov     rdx, rax; pv
0x1800bbb1d  mov     r14, rax
0x1800bbb20  mov     [rax], rdi
0x1800bbb23  call    cs:__imp_CreateThreadpoolWork
0x1800bbb29  mov     rsi, rax
0x1800bbb2c  test    rax, rax
0x1800bbb2f  jnz     short loc_1800BBB3D
0x1800bbb31  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800bbb36  mov     ebx, eax
0x1800bbb38  jmp     loc_1800BBC75
0x1800bbb3d  call    cs:__imp_GetCurrentThread
0x1800bbb43  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800bbb47  xor     r8d, r8d; OpenAsSelf
0x1800bbb4a  mov     rcx, rax; ThreadHandle
0x1800bbb4d  mov     edx, 2000Ch; DesiredAccess
0x1800bbb52  call    cs:__imp_OpenThreadToken
0x1800bbb58  test    eax, eax
0x1800bbb5a  jnz     short loc_1800BBB69
0x1800bbb5c  call    cs:__imp_GetLastError
0x1800bbb62  cmp     eax, 3F0h
0x1800bbb67  jnz     short loc_1800BBB31
0x1800bbb69  mov     rax, [rbp+TokenHandle]
0x1800bbb6d  mov     r8, r13
0x1800bbb70  mov     [r14+8], rax
0x1800bbb74  mov     rcx, rdi
0x1800bbb77  mov     rax, [rdi]
0x1800bbb7a  mov     rdx, [r12+8]
0x1800bbb7f  mov     rax, [rax+18h]
0x1800bbb83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbb88  mov     rax, [rdi]
0x1800bbb8b  mov     rdx, r15
0x1800bbb8e  mov     rcx, rdi
0x1800bbb91  mov     rax, [rax+28h]
0x1800bbb95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbb9a  mov     ebx, eax
0x1800bbb9c  test    eax, eax
0x1800bbb9e  jz      short loc_1800BBBA9
0x1800bbba0  cmp     eax, 7
0x1800bbba3  jnz     loc_1800BBC75
0x1800bbba9  mov     rax, [rdi]
0x1800bbbac  mov     rdx, r15
0x1800bbbaf  mov     rcx, rdi
0x1800bbbb2  mov     rax, [rax+38h]
0x1800bbbb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbbbb  mov     ebx, eax
0x1800bbbbd  test    eax, eax
0x1800bbbbf  jnz     loc_1800BBC75
0x1800bbbc5  mov     rax, [rdi+150h]
0x1800bbbcc  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bbbd3  jnz     short loc_1800BBBE9
0x1800bbbd5  mov     rax, [rdi+158h]
0x1800bbbdc  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800bbbe3  jz      loc_1800BBC75
0x1800bbbe9  mov     rdx, r15
0x1800bbbec  mov     rcx, rdi
0x1800bbbef  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800bbbf4  mov     ebx, eax
0x1800bbbf6  test    eax, eax
0x1800bbbf8  jnz     short loc_1800BBC75
0x1800bbbfa  mov     rcx, rsi; pwk
0x1800bbbfd  call    cs:__imp_SubmitThreadpoolWork
0x1800bbc03  jmp     loc_1800BBCB7
0x1800bbc08  mov     rax, [rdi]
0x1800bbc0b  mov     r8, r13
0x1800bbc0e  mov     rdx, [r12+8]
0x1800bbc13  mov     rcx, rdi
0x1800bbc16  mov     rax, [rax+10h]
0x1800bbc1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbc1f  mov     rax, [rdi]
0x1800bbc22  mov     rdx, r15
0x1800bbc25  mov     rcx, rdi
0x1800bbc28  mov     rax, [rax+30h]
0x1800bbc2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbc31  mov     ebx, eax
0x1800bbc33  test    eax, eax
0x1800bbc35  jz      short loc_1800BBC3C
0x1800bbc37  cmp     eax, 7
0x1800bbc3a  jnz     short loc_1800BBC75
0x1800bbc3c  mov     rax, [rdi]
0x1800bbc3f  mov     rdx, r15
0x1800bbc42  mov     rcx, rdi
0x1800bbc45  mov     rax, [rax+28h]
0x1800bbc49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbc4e  mov     ebx, eax
0x1800bbc50  test    eax, eax
0x1800bbc52  jz      short loc_1800BBC59
0x1800bbc54  cmp     eax, 7
0x1800bbc57  jnz     short loc_1800BBC75
0x1800bbc59  mov     rax, [rdi]
0x1800bbc5c  mov     rdx, r15
0x1800bbc5f  mov     rcx, rdi
0x1800bbc62  mov     rax, [rax+38h]
0x1800bbc66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbc6b  jmp     loc_1800BBB36
0x1800bbc70  mov     ebx, 4
0x1800bbc75  mov     rax, [rdi]
0x1800bbc78  mov     edx, 1
0x1800bbc7d  mov     rcx, rdi
0x1800bbc80  mov     rax, [rax]
0x1800bbc83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbc88  test    r14, r14
0x1800bbc8b  jz      short loc_1800BBC9A
0x1800bbc8d  mov     edx, 10h
0x1800bbc92  mov     rcx, r14; Block
0x1800bbc95  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800bbc9a  mov     rcx, [rbp+TokenHandle]; hObject
0x1800bbc9e  test    rcx, rcx
0x1800bbca1  jz      short loc_1800BBCA9
0x1800bbca3  call    cs:__imp_CloseHandle
0x1800bbca9  test    rsi, rsi
0x1800bbcac  jz      short loc_1800BBCB7
0x1800bbcae  mov     rcx, rsi; pwk
0x1800bbcb1  call    cs:__imp_CloseThreadpoolWork
0x1800bbcb7  mov     eax, ebx
0x1800bbcb9  mov     rcx, [rbp+var_8]
0x1800bbcbd  xor     rcx, rsp; StackCookie
0x1800bbcc0  call    __security_check_cookie
0x1800bbcc5  mov     rbx, [rsp+80h+arg_18]
0x1800bbccd  add     rsp, 80h
0x1800bbcd4  pop     r15
0x1800bbcd6  pop     r14
0x1800bbcd8  pop     r13
0x1800bbcda  pop     r12
0x1800bbcdc  pop     rdi
0x1800bbcdd  pop     rsi
0x1800bbcde  pop     rbp
0x1800bbcdf  retn
```
