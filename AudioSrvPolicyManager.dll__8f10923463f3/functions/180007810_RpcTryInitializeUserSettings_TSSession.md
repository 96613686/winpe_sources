# RpcTryInitializeUserSettings(TSSession *)

- ea: `0x180007810`
- end: `0x180007b5a`
- name: `?RpcTryInitializeUserSettings@@YAJPEAVTSSession@@@Z`
- size: `842`
- prototype: `__int64 __fastcall(struct TSSession *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007f08`

## callees

- `0x180007810`
- `0x18000a384`
- `0x18000f040`
- `0x180012844`
- `0x18001d0b0`
- `0x18001d8a0`
- `0x1800232a0`
- `0x180023b20`
- `0x180027f10`
- `0x18002acfc`
- `0x180031960`
- `0x180031eb0`
- `0x180041c2c`
- `0x180041fb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000794f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000794f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800078e6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800078e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800078cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800078cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180007a3d`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180007a3d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007ac9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007ac9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007a6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007af5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007b05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007a6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007af5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007b05`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180007a10`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180007a10`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180007941`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800079bc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180007941`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800079bc`
- `RPCRT4!RpcRevertToSelf` at `0x180007a88`
- `RPCRT4!RpcRevertToSelf` at `0x180007b1f`
- `RPCRT4!RpcRevertToSelf` at `0x180007a88`
- `RPCRT4!RpcRevertToSelf` at `0x180007b1f`
- `RPCRT4!RpcImpersonateClient` at `0x18000788c`
- `RPCRT4!RpcImpersonateClient` at `0x18000788c`

## pseudocode

```c
__int64 __fastcall RpcTryInitializeUserSettings(struct TSSession *a1)
{
  const struct _tlgProvider_t *v2; // rax
  int v3; // r8d
  int v4; // r9d
  RPC_STATUS v5; // eax
  unsigned int v6; // edi
  HANDLE CurrentThread; // rax
  const char *v9; // r9
  unsigned int LastError; // ebx
  PSID *v11; // rdi
  DWORD v12; // eax
  const char *v13; // r9
  unsigned int v14; // eax
  unsigned int v15; // eax
  LSTATUS v16; // eax
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  unsigned int ReturnLengtha; // [rsp+20h] [rbp-E0h]
  DWORD TokenInformationLength; // [rsp+30h] [rbp-D0h] BYREF
  int v20[2]; // [rsp+38h] [rbp-C8h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE TokenInformation[512]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  if ( !*((_BYTE *)a1 + 1092) )
  {
    v2 = AudioSrvPolicyManagerTelemetryProvider::Provider();
    if ( *(_DWORD *)v2 > 4u && (unsigned __int8)tlgKeywordOn(v2, 0x20000, v2) )
    {
      v20[0] = *(_DWORD *)a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v3,
        (unsigned int)byte_1800585A1,
        v3,
        v4,
        (__int64)v20);
    }
    v5 = RpcImpersonateClient(0);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C0,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
        (const char *)(unsigned int)v5,
        ReturnLength);
      return v6;
    }
    TokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x2C7,
                    (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
                    v9);
LABEL_23:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      RpcRevertToSelf();
      return LastError;
    }
    TokenInformationLength = 512;
    *(_QWORD *)v20 = 0;
    v11 = (PSID *)TokenInformation;
    if ( !GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x200u, &TokenInformationLength) )
    {
      v12 = GetLastError();
      if ( v12 == 122 )
      {
        *(_QWORD *)v20 = operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
        v11 = *(PSID **)v20;
        if ( !*(_QWORD *)v20 )
        {
          LastError = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2D5,
            (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
            (const char *)0x8007000ELL,
            ReturnLengtha);
LABEL_22:
          std::unique_ptr<_TOKEN_USER>::~unique_ptr<_TOKEN_USER>(v20);
          goto LABEL_23;
        }
        if ( !GetTokenInformation(
                TokenHandle,
                TokenUser,
                *(LPVOID *)v20,
                TokenInformationLength,
                &TokenInformationLength) )
        {
          v14 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2D8,
                  (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
                  v13);
LABEL_15:
          LastError = v14;
          goto LABEL_22;
        }
      }
      else if ( v12 )
      {
        v14 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x2DC,
                (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
                (const char *)v12,
                ReturnLengtha);
        goto LABEL_15;
      }
    }
    if ( EqualSid(*v11, *((PSID *)a1 + 137)) )
    {
      phkResult = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &phkResult,
        0);
      v15 = RegOpenCurrentUser(0x20019u, &phkResult);
      if ( v15 )
      {
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x2E7,
                      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
                      (const char *)v15,
                      ReturnLengtha);
        if ( phkResult )
          RegCloseKey(phkResult);
        goto LABEL_22;
      }
      hKey[0] = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        hKey,
        0);
      v16 = RegOpenKeyExW(phkResult, L"Software\\Microsoft\\Multimedia\\Audio", 0, 1u, hKey);
      *((_BYTE *)a1 + 1092) = v16 == 0;
      if ( !v16 )
        LoadUserSettings(a1, hKey[0]);
      if ( hKey[0] )
        RegCloseKey(hKey[0]);
      if ( phkResult )
        RegCloseKey(phkResult);
    }
    std::unique_ptr<_TOKEN_USER>::~unique_ptr<_TOKEN_USER>(v20);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    RpcRevertToSelf();
  }
  return *((_BYTE *)a1 + 1092) == 0 ? 0x80070490 : 0;
}

```

## disassembly

```asm
0x180007810  mov     [rsp-8+arg_8], rbx
0x180007815  mov     [rsp-8+arg_10], rdi
0x18000781a  push    rbp
0x18000781b  lea     rbp, [rsp-170h]
0x180007823  sub     rsp, 270h
0x18000782a  mov     rax, cs:__security_cookie
0x180007831  xor     rax, rsp
0x180007834  mov     [rbp+170h+var_10], rax
0x18000783b  cmp     byte ptr [rcx+444h], 0
0x180007842  mov     rbx, rcx
0x180007845  jnz     loc_180007B25
0x18000784b  call    ?Provider@AudioSrvPolicyManagerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioSrvPolicyManagerTelemetryProvider::Provider(void)
0x180007850  mov     r8, rax
0x180007853  mov     ecx, [rax]
0x180007855  cmp     ecx, 4
0x180007858  jbe     short loc_18000788A
0x18000785a  mov     edx, 20000h
0x18000785f  mov     rcx, rax
0x180007862  call    _tlgKeywordOn
0x180007867  test    al, al
0x180007869  jz      short loc_18000788A
0x18000786b  mov     ecx, [rbx]
0x18000786d  lea     rax, [rsp+270h+var_238]
0x180007872  mov     [rsp+270h+var_238], ecx
0x180007876  lea     rdx, byte_1800585A1
0x18000787d  mov     rcx, r8
0x180007880  mov     qword ptr [rsp+270h+ReturnLength], rax; int
0x180007885  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18000788a  xor     ecx, ecx; BindingHandle
0x18000788c  call    cs:__imp_RpcImpersonateClient
0x180007892  mov     edi, eax
0x180007894  test    eax, eax
0x180007896  jns     short loc_1800078BA
0x180007898  mov     rcx, [rbp+178h]; this
0x18000789f  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x1800078a6  mov     r9d, eax; char *
0x1800078a9  mov     edx, 2C0h; void *
0x1800078ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800078b3  mov     eax, edi
0x1800078b5  jmp     loc_180007B36
0x1800078ba  xor     edx, edx
0x1800078bc  mov     [rsp+270h+TokenHandle], 0
0x1800078c5  lea     rcx, [rsp+270h+TokenHandle]
0x1800078ca  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800078cf  call    cs:__imp_GetCurrentThread
0x1800078d5  mov     edx, 8; DesiredAccess
0x1800078da  lea     r9, [rsp+270h+TokenHandle]; TokenHandle
0x1800078df  mov     rcx, rax; ThreadHandle
0x1800078e2  lea     r8d, [rdx-7]; OpenAsSelf
0x1800078e6  call    cs:__imp_OpenThreadToken
0x1800078ec  test    eax, eax
0x1800078ee  jnz     short loc_18000790F
0x1800078f0  mov     rcx, [rbp+178h]; this
0x1800078f7  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x1800078fe  mov     edx, 2C7h; void *
0x180007903  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007908  mov     ebx, eax
0x18000790a  jmp     loc_180007A7E
0x18000790f  mov     rcx, [rsp+270h+TokenHandle]; TokenHandle
0x180007914  lea     rax, [rsp+270h+TokenInformationLength]
0x180007919  mov     r9d, 200h; TokenInformationLength
0x18000791f  mov     qword ptr [rsp+270h+ReturnLength], rax; unsigned int
0x180007924  lea     r8, [rsp+270h+TokenInformation]; TokenInformation
0x180007929  mov     [rsp+270h+TokenInformationLength], r9d
0x18000792e  mov     edx, 1; TokenInformationClass
0x180007933  mov     qword ptr [rsp+270h+var_238], 0
0x18000793c  lea     rdi, [rsp+270h+TokenInformation]
0x180007941  call    cs:__imp_GetTokenInformation
0x180007947  test    eax, eax
0x180007949  jnz     loc_180007A06
0x18000794f  call    cs:__imp_GetLastError
0x180007955  cmp     eax, 7Ah ; 'z'
0x180007958  jnz     loc_1800079E5
0x18000795e  mov     ecx, [rsp+270h+TokenInformationLength]; unsigned __int64
0x180007962  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007969  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000796e  mov     qword ptr [rsp+270h+var_238], rax
0x180007973  mov     rdi, rax
0x180007976  test    rax, rax
0x180007979  jnz     short loc_1800079A0
0x18000797b  mov     rcx, [rbp+178h]; this
0x180007982  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x180007989  mov     ebx, 8007000Eh
0x18000798e  mov     edx, 2D5h; void *
0x180007993  mov     r9d, ebx; char *
0x180007996  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000799b  jmp     loc_180007A74
0x1800079a0  mov     r9d, [rsp+270h+TokenInformationLength]; TokenInformationLength
0x1800079a5  lea     rax, [rsp+270h+TokenInformationLength]
0x1800079aa  mov     rcx, [rsp+270h+TokenHandle]; TokenHandle
0x1800079af  mov     r8, rdi; TokenInformation
0x1800079b2  mov     edx, 1; TokenInformationClass
0x1800079b7  mov     qword ptr [rsp+270h+ReturnLength], rax; ReturnLength
0x1800079bc  call    cs:__imp_GetTokenInformation
0x1800079c2  test    eax, eax
0x1800079c4  jnz     short loc_180007A06
0x1800079c6  mov     rcx, [rbp+178h]; this
0x1800079cd  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x1800079d4  mov     edx, 2D8h; void *
0x1800079d9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800079de  mov     ebx, eax
0x1800079e0  jmp     loc_180007A74
0x1800079e5  test    eax, eax
0x1800079e7  jz      short loc_180007A06
0x1800079e9  mov     rcx, [rbp+178h]; this
0x1800079f0  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x1800079f7  mov     r9d, eax; char *
0x1800079fa  mov     edx, 2DCh; void *
0x1800079ff  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180007a04  jmp     short loc_1800079DE
0x180007a06  mov     rdx, [rbx+448h]; pSid2
0x180007a0d  mov     rcx, [rdi]; pSid1
0x180007a10  call    cs:__imp_EqualSid
0x180007a16  test    eax, eax
0x180007a18  jz      loc_180007B0B
0x180007a1e  xor     edx, edx
0x180007a20  mov     [rsp+270h+phkResult], 0
0x180007a29  lea     rcx, [rsp+270h+phkResult]
0x180007a2e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180007a33  lea     rdx, [rsp+270h+phkResult]; phkResult
0x180007a38  mov     ecx, 20019h; samDesired
0x180007a3d  call    cs:__imp_RegOpenCurrentUser
0x180007a43  test    eax, eax
0x180007a45  jz      short loc_180007A95
0x180007a47  mov     rcx, [rbp+178h]; this
0x180007a4e  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x180007a55  mov     r9d, eax; char *
0x180007a58  mov     edx, 2E7h; void *
0x180007a5d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180007a62  mov     rcx, [rsp+270h+phkResult]; hKey
0x180007a67  mov     ebx, eax
0x180007a69  test    rcx, rcx
0x180007a6c  jz      short loc_180007A74
0x180007a6e  call    cs:__imp_RegCloseKey
0x180007a74  lea     rcx, [rsp+270h+var_238]
0x180007a79  call    ??1?$unique_ptr@U_TOKEN_USER@@U?$default_delete@U_TOKEN_USER@@@std@@@std@@QEAA@XZ; std::unique_ptr<_TOKEN_USER>::~unique_ptr<_TOKEN_USER>(void)
0x180007a7e  lea     rcx, [rsp+270h+TokenHandle]
0x180007a83  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180007a88  call    cs:__imp_RpcRevertToSelf
0x180007a8e  mov     eax, ebx
0x180007a90  jmp     loc_180007B36
0x180007a95  xor     edx, edx
0x180007a97  mov     [rsp+270h+hKey], 0
0x180007aa0  lea     rcx, [rsp+270h+hKey]
0x180007aa5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180007aaa  mov     rcx, [rsp+270h+phkResult]; hKey
0x180007aaf  lea     rax, [rsp+270h+hKey]
0x180007ab4  mov     r9d, 1; samDesired
0x180007aba  mov     qword ptr [rsp+270h+ReturnLength], rax; phkResult
0x180007abf  xor     r8d, r8d; ulOptions
0x180007ac2  lea     rdx, SubKey; "Software\\Microsoft\\Multimedia\\Audio"
0x180007ac9  call    cs:__imp_RegOpenKeyExW
0x180007acf  test    eax, eax
0x180007ad1  setz    cl
0x180007ad4  mov     [rbx+444h], cl
0x180007ada  test    eax, eax
0x180007adc  jnz     short loc_180007AEB
0x180007ade  mov     rdx, [rsp+270h+hKey]; HKEY
0x180007ae3  mov     rcx, rbx; struct TSSession *
0x180007ae6  call    ?LoadUserSettings@@YAXPEAVTSSession@@PEAUHKEY__@@@Z; LoadUserSettings(TSSession *,HKEY__ *)
0x180007aeb  mov     rcx, [rsp+270h+hKey]; hKey
0x180007af0  test    rcx, rcx
0x180007af3  jz      short loc_180007AFB
0x180007af5  call    cs:__imp_RegCloseKey
0x180007afb  mov     rcx, [rsp+270h+phkResult]; hKey
0x180007b00  test    rcx, rcx
0x180007b03  jz      short loc_180007B0B
0x180007b05  call    cs:__imp_RegCloseKey
0x180007b0b  lea     rcx, [rsp+270h+var_238]
0x180007b10  call    ??1?$unique_ptr@U_TOKEN_USER@@U?$default_delete@U_TOKEN_USER@@@std@@@std@@QEAA@XZ; std::unique_ptr<_TOKEN_USER>::~unique_ptr<_TOKEN_USER>(void)
0x180007b15  lea     rcx, [rsp+270h+TokenHandle]
0x180007b1a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180007b1f  call    cs:__imp_RpcRevertToSelf
0x180007b25  mov     al, [rbx+444h]
0x180007b2b  neg     al
0x180007b2d  sbb     eax, eax
0x180007b2f  not     eax
0x180007b31  and     eax, 80070490h
0x180007b36  mov     rcx, [rbp+170h+var_10]
0x180007b3d  xor     rcx, rsp; StackCookie
0x180007b40  call    __security_check_cookie
0x180007b45  lea     r11, [rsp+270h+var_s0]
0x180007b4d  mov     rbx, [r11+18h]
0x180007b51  mov     rdi, [r11+20h]
0x180007b55  mov     rsp, r11
0x180007b58  pop     rbp
0x180007b59  retn
```
