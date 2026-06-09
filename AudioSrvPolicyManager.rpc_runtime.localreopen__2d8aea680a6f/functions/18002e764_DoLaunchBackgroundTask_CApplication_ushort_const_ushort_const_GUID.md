# DoLaunchBackgroundTask(CApplication *,ushort const *,ushort const *,_GUID *)

- ea: `0x18002e764`
- end: `0x18002ea4b`
- name: `?DoLaunchBackgroundTask@@YAJPEAVCApplication@@PEBG1PEAU_GUID@@@Z`
- size: `743`
- prototype: `__int64 __fastcall(struct CApplication *, const unsigned __int16 *, const unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180042b54`

## callees

- `0x180001d40`
- `0x18000a384`
- `0x18000f040`
- `0x18001d070`
- `0x18001d8a0`
- `0x18002e764`
- `0x18002ea54`
- `0x180031960`
- `0x1800327f8`
- `0x18004192c`
- `0x1800421a0`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e7e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e91b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ea23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e7e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e91b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ea23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002e841`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002e841`
- `ntdll!NtOpenThreadToken` at `0x18002e857`
- `ntdll!NtOpenThreadToken` at `0x18002e857`
- `ntdll!NtQueryInformationToken` at `0x18002e8ae`
- `ntdll!NtQueryInformationToken` at `0x18002e8ae`
- `OnDemandBrokerClient!CreateOnDemandBrokerClient` at `0x18002e8ec`
- `OnDemandBrokerClient!CreateOnDemandBrokerClient` at `0x18002e8ec`
- `RPCRT4!RpcRevertToSelf` at `0x18002e885`
- `RPCRT4!RpcRevertToSelf` at `0x18002e8c9`
- `RPCRT4!RpcRevertToSelf` at `0x18002e885`
- `RPCRT4!RpcRevertToSelf` at `0x18002e8c9`
- `RPCRT4!RpcImpersonateClient` at `0x18002e805`
- `RPCRT4!RpcImpersonateClient` at `0x18002e805`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DoLaunchBackgroundTask(
        struct CApplication *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _GUID *a4)
{
  int v4; // r14d
  signed int v6; // ebx
  __int64 v7; // rdx
  RPC_STATUS v9; // eax
  HANDLE CurrentThread; // rax
  NTSTATUS InformationToken; // eax
  __int64 v12; // rdx
  struct TSSession *v13; // rbx
  _QWORD *v14; // rsi
  int v15; // eax
  unsigned int v16; // edi
  __int64 *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  PULONG ReturnLength; // [rsp+20h] [rbp-E0h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+70h] [rbp-90h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v23; // [rsp+80h] [rbp-80h] BYREF
  struct TSSession *v24; // [rsp+88h] [rbp-78h] BYREF
  ULONG v25[4]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD TokenInformation[12]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v4 = (int)a2;
  CWindowsPolicyManager::Lock(a1, &lpCriticalSection);
  v24 = 0;
  v6 = TsSessionFromSessionId(*((_DWORD *)a1 + 53), 0, &v24);
  if ( v6 < 0 )
  {
    v7 = 466;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
      (const char *)(unsigned int)v6,
      (int)ReturnLength);
LABEL_4:
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    return (unsigned int)v6;
  }
  memset_0(TokenInformation, 0, 0x58u);
  v9 = RpcImpersonateClient(0);
  v6 = v9;
  if ( v9 && v9 != 1725 )
  {
    if ( v9 > 0 )
      v6 = (unsigned __int16)v9 | 0x80070000;
    if ( v6 >= 0 )
      goto LABEL_4;
    v7 = 481;
    goto LABEL_3;
  }
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  InformationToken = NtOpenThreadToken(CurrentThread, 8u, 1u, &TokenHandle);
  if ( InformationToken < 0 )
  {
    v12 = 486;
LABEL_15:
    v6 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)v12,
           (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
           (const char *)(unsigned int)InformationToken,
           (int)ReturnLength);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    RpcRevertToSelf();
    goto LABEL_4;
  }
  v25[0] = 0;
  InformationToken = NtQueryInformationToken(TokenHandle, TokenUser, TokenInformation, 0x58u, v25);
  if ( InformationToken < 0 )
  {
    v12 = 490;
    goto LABEL_15;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  RpcRevertToSelf();
  v13 = v24;
  v14 = (_QWORD *)((char *)v24 + 1048);
  if ( *((_QWORD *)v24 + 131) || (*v14 = 0, v15 = CreateOnDemandBrokerClient(L"AudioSrv", v14), v16 = v15, v15 >= 0) )
  {
    if ( !*((_QWORD *)v13 + 132) )
    {
      v17 = (__int64 *)Microsoft::WRL::Details::Make<CBackgroundSessionCallbacks,>(&v24);
      v18 = *v17;
      *v17 = 0;
      v19 = *((_QWORD *)v13 + 132);
      *((_QWORD *)v13 + 132) = v18;
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      if ( v24 )
      {
        v24 = 0;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IBackgroundSessionCallbacks>::Release();
      }
      if ( !*((_QWORD *)v13 + 132) )
      {
        v6 = -2147024882;
        v7 = 502;
        goto LABEL_3;
      }
    }
    v23 = 0;
    ReturnLength = &v23;
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(*(_QWORD *)*v14 + 24LL))(
           *v14,
           TokenInformation[0],
           702,
           *((_QWORD *)v13 + 132));
    if ( v6 < 0 )
    {
      v7 = 509;
      goto LABEL_3;
    }
    LODWORD(ReturnLength) = v4;
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)*v14 + 56LL))(
           *v14,
           TokenInformation[0],
           0,
           v23);
    if ( v6 < 0 )
    {
      v7 = 522;
      goto LABEL_3;
    }
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EF,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
      (const char *)(unsigned int)v15,
      (int)ReturnLength);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    return v16;
  }
}

```

## disassembly

```asm
0x18002e764  push    rbp
0x18002e766  push    rbx
0x18002e767  push    rsi
0x18002e768  push    rdi
0x18002e769  push    r12
0x18002e76b  push    r13
0x18002e76d  push    r14
0x18002e76f  push    r15
0x18002e771  lea     rbp, [rsp-18h]
0x18002e776  sub     rsp, 118h
0x18002e77d  mov     rax, cs:__security_cookie
0x18002e784  xor     rax, rsp
0x18002e787  mov     [rbp+50h+var_50], rax
0x18002e78b  mov     r12, r9
0x18002e78e  mov     r15, r8
0x18002e791  mov     r14, rdx
0x18002e794  mov     rbx, rcx
0x18002e797  lea     rdx, [rsp+150h+lpCriticalSection]
0x18002e79c  call    ?Lock@CWindowsPolicyManager@@UEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; CWindowsPolicyManager::Lock(void)
0x18002e7a1  nop
0x18002e7a2  xor     r13d, r13d
0x18002e7a5  mov     [rbp+50h+var_C8], r13
0x18002e7a9  lea     r8, [rbp+50h+var_C8]; struct TSSession **
0x18002e7ad  xor     edx, edx; int
0x18002e7af  mov     ecx, [rbx+0D4h]; unsigned int
0x18002e7b5  call    ?TsSessionFromSessionId@@YAJKHPEAPEAVTSSession@@@Z; TsSessionFromSessionId(ulong,int,TSSession * *)
0x18002e7ba  mov     ebx, eax
0x18002e7bc  test    eax, eax
0x18002e7be  jns     short loc_18002E7F0
0x18002e7c0  mov     edx, 1D2h; void *
0x18002e7c5  mov     rcx, [rbp+58h]; this
0x18002e7c9  mov     r9d, ebx; char *
0x18002e7cc  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x18002e7d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e7d8  nop
0x18002e7d9  mov     rcx, [rsp+150h+lpCriticalSection]; lpCriticalSection
0x18002e7de  test    rcx, rcx
0x18002e7e1  jz      short loc_18002E7E9
0x18002e7e3  call    cs:__imp_LeaveCriticalSection
0x18002e7e9  mov     eax, ebx
0x18002e7eb  jmp     loc_18002EA2B
0x18002e7f0  mov     edi, 58h ; 'X'
0x18002e7f5  mov     r8d, edi; Size
0x18002e7f8  xor     edx, edx; Val
0x18002e7fa  lea     rcx, [rbp+50h+TokenInformation]; void *
0x18002e7fe  call    memset_0
0x18002e803  xor     ecx, ecx; BindingHandle
0x18002e805  call    cs:__imp_RpcImpersonateClient
0x18002e80b  mov     ebx, eax
0x18002e80d  test    eax, eax
0x18002e80f  jz      short loc_18002E830
0x18002e811  cmp     eax, 6BDh
0x18002e816  jz      short loc_18002E830
0x18002e818  test    eax, eax
0x18002e81a  jle     short loc_18002E825
0x18002e81c  movzx   ebx, ax
0x18002e81f  or      ebx, 80070000h
0x18002e825  test    ebx, ebx
0x18002e827  jns     short loc_18002E7D9
0x18002e829  mov     edx, 1E1h
0x18002e82e  jmp     short loc_18002E7C5
0x18002e830  mov     [rsp+150h+TokenHandle], r13
0x18002e835  xor     edx, edx
0x18002e837  lea     rcx, [rsp+150h+TokenHandle]
0x18002e83c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002e841  call    cs:__imp_GetCurrentThread
0x18002e847  lea     r9, [rsp+150h+TokenHandle]; TokenHandle
0x18002e84c  mov     r8b, 1; OpenAsSelf
0x18002e84f  mov     edx, 8; DesiredAccess
0x18002e854  mov     rcx, rax; ThreadHandle
0x18002e857  call    cs:__imp_NtOpenThreadToken
0x18002e85d  test    eax, eax
0x18002e85f  jns     short loc_18002E890
0x18002e861  mov     edx, 1E6h; void *
0x18002e866  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x18002e86d  mov     r9d, eax; char *
0x18002e870  mov     rcx, [rbp+58h]; this
0x18002e874  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002e879  mov     ebx, eax
0x18002e87b  lea     rcx, [rsp+150h+TokenHandle]
0x18002e880  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002e885  call    cs:__imp_RpcRevertToSelf
0x18002e88b  jmp     loc_18002E7D9
0x18002e890  mov     [rbp+50h+var_C0], r13d
0x18002e894  lea     rax, [rbp+50h+var_C0]
0x18002e898  mov     [rsp+150h+ReturnLength], rax; int
0x18002e89d  mov     r9d, edi; TokenInformationLength
0x18002e8a0  lea     r8, [rbp+50h+TokenInformation]; TokenInformation
0x18002e8a4  mov     edx, 1; TokenInformationClass
0x18002e8a9  mov     rcx, [rsp+150h+TokenHandle]; TokenHandle
0x18002e8ae  call    cs:__imp_NtQueryInformationToken
0x18002e8b4  test    eax, eax
0x18002e8b6  jns     short loc_18002E8BF
0x18002e8b8  mov     edx, 1EAh
0x18002e8bd  jmp     short loc_18002E866
0x18002e8bf  lea     rcx, [rsp+150h+TokenHandle]
0x18002e8c4  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002e8c9  call    cs:__imp_RpcRevertToSelf
0x18002e8cf  mov     rbx, [rbp+50h+var_C8]
0x18002e8d3  lea     rsi, [rbx+418h]
0x18002e8da  cmp     [rsi], r13
0x18002e8dd  jnz     short loc_18002E928
0x18002e8df  mov     [rsi], r13
0x18002e8e2  mov     rdx, rsi
0x18002e8e5  lea     rcx, aAudiosrv; "AudioSrv"
0x18002e8ec  call    cs:__imp_CreateOnDemandBrokerClient
0x18002e8f2  mov     edi, eax
0x18002e8f4  test    eax, eax
0x18002e8f6  jns     short loc_18002E928
0x18002e8f8  mov     rcx, [rbp+58h]; this
0x18002e8fc  mov     r9d, eax; char *
0x18002e8ff  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x18002e906  mov     edx, 1EFh; void *
0x18002e90b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e910  nop
0x18002e911  mov     rcx, [rsp+150h+lpCriticalSection]; lpCriticalSection
0x18002e916  test    rcx, rcx
0x18002e919  jz      short loc_18002E921
0x18002e91b  call    cs:__imp_LeaveCriticalSection
0x18002e921  mov     eax, edi
0x18002e923  jmp     loc_18002EA2B
0x18002e928  cmp     [rbx+420h], r13
0x18002e92f  jnz     short loc_18002E98A
0x18002e931  lea     rcx, [rbp+50h+var_C8]
0x18002e935  call    ??$Make@VCBackgroundSessionCallbacks@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCBackgroundSessionCallbacks@@@12@XZ; Microsoft::WRL::Details::Make<CBackgroundSessionCallbacks,>(void)
0x18002e93a  mov     rdx, [rax]
0x18002e93d  mov     [rax], r13
0x18002e940  mov     rcx, [rbx+420h]
0x18002e947  mov     [rbx+420h], rdx
0x18002e94e  test    rcx, rcx
0x18002e951  jz      short loc_18002E960
0x18002e953  mov     rax, [rcx]
0x18002e956  mov     rax, [rax+10h]
0x18002e95a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e95f  nop
0x18002e960  mov     rcx, [rbp+50h+var_C8]
0x18002e964  test    rcx, rcx
0x18002e967  jz      short loc_18002E972
0x18002e969  mov     [rbp+50h+var_C8], r13
0x18002e96d  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIBackgroundSessionCallbacks@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IBackgroundSessionCallbacks>::Release(void)
0x18002e972  cmp     [rbx+420h], r13
0x18002e979  jnz     short loc_18002E98A
0x18002e97b  mov     ebx, 8007000Eh
0x18002e980  mov     edx, 1F6h
0x18002e985  jmp     loc_18002E7C5
0x18002e98a  mov     [rbp+50h+var_D0], r13d
0x18002e98e  mov     rcx, [rsi]
0x18002e991  mov     rax, [rcx]
0x18002e994  lea     rdx, [rbp+50h+var_D0]
0x18002e998  mov     [rsp+150h+ReturnLength], rdx
0x18002e99d  mov     r9, [rbx+420h]
0x18002e9a4  mov     r8d, 2BEh
0x18002e9aa  mov     rdx, [rbp+50h+TokenInformation]
0x18002e9ae  mov     rax, [rax+18h]
0x18002e9b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9b7  mov     ebx, eax
0x18002e9b9  test    eax, eax
0x18002e9bb  jns     short loc_18002E9C7
0x18002e9bd  mov     edx, 1FDh
0x18002e9c2  jmp     loc_18002E7C5
0x18002e9c7  mov     rcx, [rsi]
0x18002e9ca  mov     rax, [rcx]
0x18002e9cd  mov     [rsp+150h+var_F8], r12
0x18002e9d2  mov     [rsp+150h+var_100], r13
0x18002e9d7  mov     [rsp+150h+var_108], r13
0x18002e9dc  mov     [rsp+150h+var_110], r13d
0x18002e9e1  mov     [rsp+150h+var_118], r13
0x18002e9e6  mov     [rsp+150h+var_120], r13
0x18002e9eb  mov     [rsp+150h+var_128], r15
0x18002e9f0  mov     [rsp+150h+ReturnLength], r14
0x18002e9f5  mov     r9d, [rbp+50h+var_D0]
0x18002e9f9  xor     r8d, r8d
0x18002e9fc  mov     rdx, [rbp+50h+TokenInformation]
0x18002ea00  mov     rax, [rax+38h]
0x18002ea04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea09  mov     ebx, eax
0x18002ea0b  test    eax, eax
0x18002ea0d  jns     short loc_18002EA19
0x18002ea0f  mov     edx, 20Ah
0x18002ea14  jmp     loc_18002E7C5
0x18002ea19  mov     rcx, [rsp+150h+lpCriticalSection]; lpCriticalSection
0x18002ea1e  test    rcx, rcx
0x18002ea21  jz      short loc_18002EA29
0x18002ea23  call    cs:__imp_LeaveCriticalSection
0x18002ea29  xor     eax, eax
0x18002ea2b  mov     rcx, [rbp+50h+var_50]
0x18002ea2f  xor     rcx, rsp; StackCookie
0x18002ea32  call    __security_check_cookie
0x18002ea37  add     rsp, 118h
0x18002ea3e  pop     r15
0x18002ea40  pop     r14
0x18002ea42  pop     r13
0x18002ea44  pop     r12
0x18002ea46  pop     rdi
0x18002ea47  pop     rsi
0x18002ea48  pop     rbx
0x18002ea49  pop     rbp
0x18002ea4a  retn
```
