# CSpWmiMethod<_SPACES_StorageSubsystem_CreateFileServer>::RunMethod<CSpSubsystem::CreateFileServer,13>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x180069960`
- end: `0x180069cae`
- name: `??$RunMethod@VCreateFileServer@CSpSubsystem@@$0N@@?$CSpWmiMethod@U_SPACES_StorageSubsystem_CreateFileServer@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x180069960`
- `0x18006bc34`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069b2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069b2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180069b0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180069b0d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180069b22`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180069b22`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180069af3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180069af3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180069bcc`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180069bcc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180069c7f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180069c7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069c71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069c71`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageSubsystem_CreateFileServer>::RunMethod<CSpSubsystem::CreateFileServer,13>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 FileServer; // rax
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
  CSpSubsystem::CreateFileServer *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpSubsystem::CreateFileServer *)operator new(0x178u);
  FileServer = CSpSubsystem::CreateFileServer::CreateFileServer(v25);
  v8 = FileServer;
  if ( FileServer )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)FileServer + 8LL))(FileServer, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpSubsystem::CreateFileServer *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&unk_180311E98,
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
0x180069960  mov     [rsp-38h+arg_18], rbx
0x180069965  push    rbp
0x180069966  push    rsi
0x180069967  push    rdi
0x180069968  push    r12
0x18006996a  push    r13
0x18006996c  push    r14
0x18006996e  push    r15
0x180069970  mov     rbp, rsp
0x180069973  sub     rsp, 80h
0x18006997a  mov     rax, cs:__security_cookie
0x180069981  xor     rax, rsp
0x180069984  mov     [rbp+var_8], rax
0x180069988  xor     eax, eax
0x18006998a  mov     rsi, rcx
0x18006998d  xorps   xmm0, xmm0
0x180069990  mov     [rbp+var_10], eax
0x180069993  mov     ecx, 178h; Size
0x180069998  mov     [rbp+var_40], eax
0x18006999b  movups  [rbp+var_20], xmm0
0x18006999f  mov     [rbp+TokenHandle], rax
0x1800699a3  mov     r12, r8
0x1800699a6  mov     r13, rdx
0x1800699a9  xor     r14d, r14d
0x1800699ac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800699b1  mov     rcx, rax; this
0x1800699b4  mov     [rbp+var_28], rax
0x1800699b8  call    ??0CreateFileServer@CSpSubsystem@@QEAA@XZ; CSpSubsystem::CreateFileServer::CreateFileServer(void)
0x1800699bd  mov     rdi, rax
0x1800699c0  test    rax, rax
0x1800699c3  jnz     short loc_1800699CD
0x1800699c5  lea     ebx, [rax+1Bh]
0x1800699c8  jmp     loc_180069C68
0x1800699cd  mov     rax, [rax]
0x1800699d0  mov     rdx, rsi
0x1800699d3  mov     rcx, rdi
0x1800699d6  xor     r15d, r15d
0x1800699d9  mov     rax, [rax+8]
0x1800699dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800699e2  lea     rcx, [rbp+var_40]
0x1800699e6  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800699eb  mov     [rdi+1Ch], eax
0x1800699ee  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800699f2  mov     ecx, [rsi+14h]; unsigned int
0x1800699f5  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800699fa  mov     eax, cs:dword_180397B68
0x180069a00  cmp     eax, 5
0x180069a03  jbe     short loc_180069A73
0x180069a05  mov     rdx, 400000000000h
0x180069a0f  lea     rcx, dword_180397B68
0x180069a16  call    _tlgKeywordOn
0x180069a1b  test    al, al
0x180069a1d  jz      short loc_180069A73
0x180069a1f  mov     eax, [rbp+var_40]
0x180069a22  lea     rdx, unk_180311E98
0x180069a29  xor     ecx, ecx
0x180069a2b  cmp     [rdi+1Ch], eax
0x180069a2e  movzx   eax, word ptr [rbp+var_10]
0x180069a32  mov     word ptr [rbp+var_40], ax
0x180069a36  setnz   cl
0x180069a39  mov     eax, [rsi+14h]
0x180069a3c  mov     [rbp+var_38], eax
0x180069a3f  lea     rax, [rbp+var_20]
0x180069a43  mov     [rbp+var_28], rax
0x180069a47  lea     rax, [rbp+var_3C]
0x180069a4b  mov     [rsp+80h+var_48], rax
0x180069a50  lea     rax, [rbp+var_40]
0x180069a54  mov     [rsp+80h+var_50], rax
0x180069a59  lea     rax, [rbp+var_38]
0x180069a5d  mov     [rsp+80h+var_58], rax
0x180069a62  lea     rax, [rbp+var_28]
0x180069a66  mov     [rsp+80h+var_60], rax
0x180069a6b  mov     [rbp+var_3C], ecx
0x180069a6e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x180069a73  mov     rcx, [rsi]
0x180069a76  test    rcx, rcx
0x180069a79  jz      loc_180069C3E
0x180069a7f  mov     rax, [rcx]
0x180069a82  test    rax, rax
0x180069a85  jz      loc_180069C3E
0x180069a8b  mov     rax, [rax+18h]
0x180069a8f  lea     r8, [rdi+20h]
0x180069a93  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x180069a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069a9f  mov     ebx, eax
0x180069aa1  test    eax, eax
0x180069aa3  jnz     loc_180069C43
0x180069aa9  cmp     [rsi+10h], r14d
0x180069aad  jz      loc_180069BD7
0x180069ab3  lea     rbx, [rdi+148h]
0x180069aba  mov     rcx, rbx
0x180069abd  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180069ac2  mov     rcx, rbx; struct CSpJobMgr **
0x180069ac5  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x180069aca  test    eax, eax
0x180069acc  jnz     short loc_180069AD6
0x180069ace  lea     ebx, [rax+1Ch]
0x180069ad1  jmp     loc_180069C43
0x180069ad6  mov     ecx, 10h; Size
0x180069adb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180069ae0  xor     r8d, r8d; pcbe
0x180069ae3  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180069aea  mov     rdx, rax; pv
0x180069aed  mov     r15, rax
0x180069af0  mov     [rax], rdi
0x180069af3  call    cs:__imp_CreateThreadpoolWork
0x180069af9  mov     r14, rax
0x180069afc  test    rax, rax
0x180069aff  jnz     short loc_180069B0D
0x180069b01  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x180069b06  mov     ebx, eax
0x180069b08  jmp     loc_180069C43
0x180069b0d  call    cs:__imp_GetCurrentThread
0x180069b13  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180069b17  xor     r8d, r8d; OpenAsSelf
0x180069b1a  mov     rcx, rax; ThreadHandle
0x180069b1d  mov     edx, 2000Ch; DesiredAccess
0x180069b22  call    cs:__imp_OpenThreadToken
0x180069b28  test    eax, eax
0x180069b2a  jnz     short loc_180069B39
0x180069b2c  call    cs:__imp_GetLastError
0x180069b32  cmp     eax, 3F0h
0x180069b37  jnz     short loc_180069B01
0x180069b39  mov     rax, [rbp+TokenHandle]
0x180069b3d  mov     r8, r13
0x180069b40  mov     [r15+8], rax
0x180069b44  mov     rcx, rdi
0x180069b47  mov     rax, [rdi]
0x180069b4a  mov     rdx, [rsi+8]
0x180069b4e  mov     rax, [rax+18h]
0x180069b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069b57  mov     rax, [rdi]
0x180069b5a  mov     rdx, r12
0x180069b5d  mov     rcx, rdi
0x180069b60  mov     rax, [rax+28h]
0x180069b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069b69  mov     ebx, eax
0x180069b6b  test    eax, eax
0x180069b6d  jz      short loc_180069B78
0x180069b6f  cmp     eax, 7
0x180069b72  jnz     loc_180069C43
0x180069b78  mov     rax, [rdi]
0x180069b7b  mov     rdx, r12
0x180069b7e  mov     rcx, rdi
0x180069b81  mov     rax, [rax+38h]
0x180069b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069b8a  mov     ebx, eax
0x180069b8c  test    eax, eax
0x180069b8e  jnz     loc_180069C43
0x180069b94  mov     rax, [rdi+150h]
0x180069b9b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180069ba2  jnz     short loc_180069BB8
0x180069ba4  mov     rax, [rdi+158h]
0x180069bab  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180069bb2  jz      loc_180069C43
0x180069bb8  mov     rdx, r12
0x180069bbb  mov     rcx, rdi
0x180069bbe  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x180069bc3  mov     ebx, eax
0x180069bc5  test    eax, eax
0x180069bc7  jnz     short loc_180069C43
0x180069bc9  mov     rcx, r14; pwk
0x180069bcc  call    cs:__imp_SubmitThreadpoolWork
0x180069bd2  jmp     loc_180069C85
0x180069bd7  mov     rax, [rdi]
0x180069bda  mov     r8, r13
0x180069bdd  mov     rdx, [rsi+8]
0x180069be1  mov     rcx, rdi
0x180069be4  mov     rax, [rax+10h]
0x180069be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069bed  mov     rax, [rdi]
0x180069bf0  mov     rdx, r12
0x180069bf3  mov     rcx, rdi
0x180069bf6  mov     rax, [rax+30h]
0x180069bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069bff  mov     ebx, eax
0x180069c01  test    eax, eax
0x180069c03  jz      short loc_180069C0A
0x180069c05  cmp     eax, 7
0x180069c08  jnz     short loc_180069C43
0x180069c0a  mov     rax, [rdi]
0x180069c0d  mov     rdx, r12
0x180069c10  mov     rcx, rdi
0x180069c13  mov     rax, [rax+28h]
0x180069c17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069c1c  mov     ebx, eax
0x180069c1e  test    eax, eax
0x180069c20  jz      short loc_180069C27
0x180069c22  cmp     eax, 7
0x180069c25  jnz     short loc_180069C43
0x180069c27  mov     rax, [rdi]
0x180069c2a  mov     rdx, r12
0x180069c2d  mov     rcx, rdi
0x180069c30  mov     rax, [rax+38h]
0x180069c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069c39  jmp     loc_180069B06
0x180069c3e  mov     ebx, 4
0x180069c43  mov     rax, [rdi]
0x180069c46  mov     edx, 1
0x180069c4b  mov     rcx, rdi
0x180069c4e  mov     rax, [rax]
0x180069c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069c56  test    r15, r15
0x180069c59  jz      short loc_180069C68
0x180069c5b  mov     edx, 10h
0x180069c60  mov     rcx, r15; Block
0x180069c63  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180069c68  mov     rcx, [rbp+TokenHandle]; hObject
0x180069c6c  test    rcx, rcx
0x180069c6f  jz      short loc_180069C77
0x180069c71  call    cs:__imp_CloseHandle
0x180069c77  test    r14, r14
0x180069c7a  jz      short loc_180069C85
0x180069c7c  mov     rcx, r14; pwk
0x180069c7f  call    cs:__imp_CloseThreadpoolWork
0x180069c85  mov     eax, ebx
0x180069c87  mov     rcx, [rbp+var_8]
0x180069c8b  xor     rcx, rsp; StackCookie
0x180069c8e  call    __security_check_cookie
0x180069c93  mov     rbx, [rsp+80h+arg_18]
0x180069c9b  add     rsp, 80h
0x180069ca2  pop     r15
0x180069ca4  pop     r14
0x180069ca6  pop     r13
0x180069ca8  pop     r12
0x180069caa  pop     rdi
0x180069cab  pop     rsi
0x180069cac  pop     rbp
0x180069cad  retn
```
