# _CtapSrvIsAllowedRpcCaller

- ea: `0x18000d640`
- end: `0x18000d9ec`
- name: `_CtapSrvIsAllowedRpcCaller`
- size: `940`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800dd350`

## callees

- `0x18000d640`
- `0x18002bbf4`
- `0x180094b44`
- `0x1800dbee8`
- `0x1800dc260`
- `0x1800dc3e4`
- `0x1800dc648`
- `0x1800dc6c8`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d71e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d71e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d70a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d736`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d70a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d736`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000d6c0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000d702`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000d6c0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000d702`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000d6a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000d6ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000d6a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000d6ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d95a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d95a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d917`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d925`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d933`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d917`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d925`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d933`
- `ntdll!RtlIsMultiSessionSku` at `0x18000d79d`
- `ntdll!RtlIsMultiSessionSku` at `0x18000d79d`
- `RPCRT4!RpcImpersonateClient` at `0x18000d68c`
- `RPCRT4!RpcImpersonateClient` at `0x18000d68c`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000d96b`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000d96b`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000d84b`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000d84b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d712`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d712`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000d777`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000d777`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18000d6e0`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18000d6e0`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000d818`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000d818`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000d7c3`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000d7c3`

## string_xrefs

- `0x18000d698`: `Impersonate`
- `0x18000d73e`: `GetToken`
- `0x18000d861`: `_CtapSrvCheckWellKnownSidMembership`

## pseudocode

```c
__int64 __fastcall CtapSrvIsAllowedRpcCaller(RPC_BINDING_HANDLE BindingHandle, int a2)
{
  __int64 result; // rax
  int v5; // ecx
  unsigned int v6; // ebx
  const char *v7; // r15
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  DWORD v10; // ecx
  HANDLE v11; // rax
  BOOL v12; // ebx
  DWORD v13; // esi
  void *v14; // rbx
  DWORD NonzeroLastError; // esi
  unsigned int i; // r12d
  WINBOOL v17; // eax
  void *v18; // r14
  void *v19; // r12
  void *v20; // r13
  const char *v21; // r9
  _BYTE v22[4]; // [rsp+38h] [rbp-59h] BYREF
  int TokenInformation; // [rsp+3Ch] [rbp-55h] BYREF
  WINBOOL IsMember[2]; // [rsp+40h] [rbp-51h] BYREF
  DWORD cbSid[2]; // [rsp+48h] [rbp-49h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp-41h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-39h] BYREF
  void *v28; // [rsp+60h] [rbp-31h]
  _BYTE pSid[80]; // [rsp+68h] [rbp-29h] BYREF

  TokenInformation = 0;
  ReturnLength = 0;
  result = 0;
  if ( BindingHandle != (RPC_BINDING_HANDLE)1 )
  {
    v6 = RpcImpersonateClient(BindingHandle);
    if ( v6 )
    {
      v7 = "Impersonate";
      goto LABEL_59;
    }
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      if ( LastError != 1008 )
      {
        v10 = LastError;
LABEL_10:
        SetLastError(v10);
        goto LABEL_11;
      }
      if ( !ImpersonateSelf(SecurityImpersonation) )
      {
LABEL_11:
        v14 = 0;
        TokenHandle = 0;
LABEL_13:
        if ( !v14 )
        {
          NonzeroLastError = GetLastError();
          v7 = "GetToken";
          if ( !NonzeroLastError )
            NonzeroLastError = -2147418113;
          goto LABEL_56;
        }
        if ( !GetTokenInformation(v14, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) || ReturnLength != 4 )
        {
          NonzeroLastError = _GetNonzeroLastError();
          v7 = "IsAppContainer";
          goto LABEL_55;
        }
        v7 = 0;
        if ( TokenInformation )
        {
          NonzeroLastError = 4252;
          if ( !(unsigned __int8)RtlIsMultiSessionSku() || a2 == 4 )
          {
            v22[0] = 0;
            if ( !(unsigned int)CapabilityCheck(v14, L"userSigninSupport", v22) )
            {
              if ( v22[0] )
              {
                NonzeroLastError = 0;
                if ( a2 == 4 )
                {
LABEL_38:
                  if ( !TokenInformation )
                    goto LABEL_53;
                  *(_QWORD *)IsMember = 0;
                  *(_QWORD *)cbSid = 0;
                  v18 = 0;
                  v28 = 0;
                  v19 = 0;
                  NonzeroLastError = -2146893807;
                  CtapSrvQueryTokenSecurityAttributes(v14);
                  v20 = *(void **)IsMember;
                  if ( *(_QWORD *)IsMember
                    && (CtapSrvExtractTokenSecurityPublisher(*(_QWORD *)IsMember, cbSid), (v18 = *(void **)cbSid) != 0)
                    || (CtapSrvGetCallerProcessImageName(BindingHandle), (v19 = v28) != 0)
                    && (CtapSrvGetPublisherFromImageName(BindingHandle), (v18 = *(void **)cbSid) != 0) )
                  {
                    if ( (unsigned int)CtapSrvIsMicrosoftPublisher(v18) )
                      NonzeroLastError = 0;
                    else
                      v7 = "NotMicrosoft";
                  }
                  else
                  {
                    v7 = "NoPublisher";
                  }
                  if ( v19 )
                    LocalFree(v19);
                  if ( v18 )
                    LocalFree(v18);
                  if ( v20 )
                    LocalFree(v20);
                }
              }
            }
          }
LABEL_55:
          CloseHandle(v14);
LABEL_56:
          v6 = RpcRevertToSelfEx(BindingHandle);
          if ( v6 )
          {
            v7 = "Revert";
          }
          else
          {
            v6 = NonzeroLastError;
            if ( !NonzeroLastError )
              return v6;
          }
LABEL_59:
          if ( (byte_1801AEA01 & 0x20) != 0 )
          {
            v21 = qword_18016F750;
            if ( v7 )
              LODWORD(v21) = (_DWORD)v7;
            McTemplateU0ssdd_EventWriteTransfer(
              v5,
              (unsigned int)EVENT_CTAP_FUNCTION_WARNING,
              (unsigned int)"_CtapSrvIsAllowedRpcCaller",
              (_DWORD)v21,
              v6,
              v6);
          }
          return v6;
        }
        for ( i = 0; ; ++i )
        {
          if ( i >= 2 )
          {
            if ( a2 == 4 )
              goto LABEL_38;
LABEL_53:
            v7 = "NoMatch";
            NonzeroLastError = -2147417829;
            goto LABEL_55;
          }
          IsMember[0] = 0;
          cbSid[0] = 68;
          if ( !CreateWellKnownSid(*((WELL_KNOWN_SID_TYPE *)&qword_18014F620 + i), 0, pSid, cbSid) )
            break;
          NonzeroLastError = 0;
          if ( CheckTokenMembership(v14, pSid, IsMember) )
            goto LABEL_30;
          NonzeroLastError = _GetNonzeroLastError();
          v17 = 0;
LABEL_31:
          if ( NonzeroLastError )
          {
            v7 = "_CtapSrvCheckWellKnownSidMembership";
            goto LABEL_55;
          }
          if ( v17 )
            goto LABEL_55;
        }
        NonzeroLastError = _GetNonzeroLastError();
LABEL_30:
        v17 = IsMember[0];
        goto LABEL_31;
      }
      v11 = GetCurrentThread();
      v12 = OpenThreadToken(v11, 8u, 1, &TokenHandle);
      v13 = GetLastError();
      RevertToSelf();
      if ( !v12 )
      {
        v10 = v13;
        goto LABEL_10;
      }
    }
    v14 = TokenHandle;
    goto LABEL_13;
  }
  return result;
}

```

## disassembly

```asm
0x18000d640  mov     r11, rsp
0x18000d643  push    rbp
0x18000d644  push    rdi
0x18000d645  push    r13
0x18000d647  push    r14
0x18000d649  lea     rbp, [r11-5Fh]
0x18000d64d  sub     rsp, 0C8h
0x18000d654  mov     rax, cs:__security_cookie
0x18000d65b  xor     rax, rsp
0x18000d65e  mov     [rbp+57h+var_30], rax
0x18000d662  xor     r13d, r13d
0x18000d665  mov     r14d, edx
0x18000d668  mov     [rbp+57h+TokenInformation], r13d
0x18000d66c  mov     rdi, rcx
0x18000d66f  mov     [rbp+57h+var_98], r13d
0x18000d673  mov     eax, r13d
0x18000d676  cmp     rcx, 1
0x18000d67a  jz      loc_18000D9D2
0x18000d680  mov     [r11+10h], rbx
0x18000d684  mov     [r11+18h], rsi
0x18000d688  mov     [r11-28h], r15
0x18000d68c  call    cs:__imp_RpcImpersonateClient
0x18000d692  mov     ebx, eax
0x18000d694  test    eax, eax
0x18000d696  jz      short loc_18000D6A4
0x18000d698  lea     r15, aImpersonate; "Impersonate"
0x18000d69f  jmp     loc_18000D986
0x18000d6a4  mov     [rbp+57h+TokenHandle], r13
0x18000d6a8  call    cs:__imp_GetCurrentThread
0x18000d6ae  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18000d6b2  mov     edx, 8; DesiredAccess
0x18000d6b7  mov     rcx, rax; ThreadHandle
0x18000d6ba  mov     r8d, 1; OpenAsSelf
0x18000d6c0  call    cs:__imp_OpenThreadToken
0x18000d6c6  test    eax, eax
0x18000d6c8  jnz     short loc_18000D72D
0x18000d6ca  call    cs:__imp_GetLastError
0x18000d6d0  cmp     eax, 3F0h
0x18000d6d5  jz      short loc_18000D6DB
0x18000d6d7  mov     ecx, eax
0x18000d6d9  jmp     short loc_18000D71E
0x18000d6db  mov     ecx, 2; ImpersonationLevel
0x18000d6e0  call    cs:__imp_ImpersonateSelf
0x18000d6e6  test    eax, eax
0x18000d6e8  jz      short loc_18000D724
0x18000d6ea  call    cs:__imp_GetCurrentThread
0x18000d6f0  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18000d6f4  mov     edx, 8; DesiredAccess
0x18000d6f9  mov     rcx, rax; ThreadHandle
0x18000d6fc  mov     r8d, 1; OpenAsSelf
0x18000d702  call    cs:__imp_OpenThreadToken
0x18000d708  mov     ebx, eax
0x18000d70a  call    cs:__imp_GetLastError
0x18000d710  mov     esi, eax
0x18000d712  call    cs:__imp_RevertToSelf
0x18000d718  test    ebx, ebx
0x18000d71a  jnz     short loc_18000D72D
0x18000d71c  mov     ecx, esi; dwErrCode
0x18000d71e  call    cs:__imp_SetLastError
0x18000d724  mov     rbx, r13
0x18000d727  mov     [rbp+57h+TokenHandle], rbx
0x18000d72b  jmp     short loc_18000D731
0x18000d72d  mov     rbx, [rbp+57h+TokenHandle]
0x18000d731  test    rbx, rbx
0x18000d734  jnz     short loc_18000D754
0x18000d736  call    cs:__imp_GetLastError
0x18000d73c  mov     esi, eax
0x18000d73e  lea     r15, aGettoken; "GetToken"
0x18000d745  test    esi, esi
0x18000d747  mov     eax, 8000FFFFh
0x18000d74c  cmovz   esi, eax
0x18000d74f  jmp     loc_18000D968
0x18000d754  lea     rax, [rbp+57h+var_98]
0x18000d758  mov     [rsp+0E0h+arg_18], r12
0x18000d760  mov     r9d, 4; TokenInformationLength
0x18000d766  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x18000d76b  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18000d76f  mov     edx, 1Dh; TokenInformationClass
0x18000d774  mov     rcx, rbx; TokenHandle
0x18000d777  call    cs:__imp_GetTokenInformation
0x18000d77d  test    eax, eax
0x18000d77f  jz      loc_18000D949
0x18000d785  cmp     [rbp+57h+var_98], 4
0x18000d789  jnz     loc_18000D949
0x18000d78f  mov     r15, r13
0x18000d792  cmp     [rbp+57h+TokenInformation], r13d
0x18000d796  jz      short loc_18000D7ED
0x18000d798  mov     esi, 109Ch
0x18000d79d  call    cs:__imp_RtlIsMultiSessionSku
0x18000d7a3  test    al, al
0x18000d7a5  jz      short loc_18000D7B1
0x18000d7a7  cmp     r14d, 4
0x18000d7ab  jnz     loc_18000D957
0x18000d7b1  lea     r8, [rbp+57h+var_B0]
0x18000d7b5  mov     [rbp+57h+var_B0], r13b
0x18000d7b9  lea     rdx, aUsersigninsupp; "userSigninSupport"
0x18000d7c0  mov     rcx, rbx
0x18000d7c3  call    cs:__imp_CapabilityCheck
0x18000d7c9  test    eax, eax
0x18000d7cb  jnz     loc_18000D957
0x18000d7d1  cmp     [rbp+57h+var_B0], r13b
0x18000d7d5  jz      loc_18000D957
0x18000d7db  mov     esi, r13d
0x18000d7de  cmp     r14d, 4
0x18000d7e2  jnz     loc_18000D957
0x18000d7e8  jmp     loc_18000D877
0x18000d7ed  mov     r12d, r13d
0x18000d7f0  lea     rax, qword_18014F620
0x18000d7f7  cmp     r12d, 2
0x18000d7fb  jnb     short loc_18000D86D
0x18000d7fd  mov     ecx, r12d
0x18000d800  lea     r9, [rbp+57h+cbSid]; cbSid
0x18000d804  lea     r8, [rbp+57h+pSid]; pSid
0x18000d808  mov     [rbp+57h+IsMember], r13d
0x18000d80c  xor     edx, edx; DomainSid
0x18000d80e  mov     [rbp+57h+cbSid], 44h ; 'D'
0x18000d815  mov     ecx, [rax+rcx*4]; WellKnownSidType
0x18000d818  call    cs:__imp_CreateWellKnownSid
0x18000d81e  test    eax, eax
0x18000d820  jnz     short loc_18000D83D
0x18000d822  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x18000d827  mov     esi, eax
0x18000d829  mov     eax, [rbp+57h+IsMember]
0x18000d82c  test    esi, esi
0x18000d82e  jnz     short loc_18000D861
0x18000d830  test    eax, eax
0x18000d832  jnz     loc_18000D957
0x18000d838  inc     r12d
0x18000d83b  jmp     short loc_18000D7F0
0x18000d83d  lea     r8, [rbp+57h+IsMember]; IsMember
0x18000d841  mov     rcx, rbx; TokenHandle
0x18000d844  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x18000d848  mov     esi, r13d
0x18000d84b  call    cs:__imp_CheckTokenMembership
0x18000d851  test    eax, eax
0x18000d853  jnz     short loc_18000D829
0x18000d855  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x18000d85a  mov     esi, eax
0x18000d85c  mov     eax, r13d
0x18000d85f  jmp     short loc_18000D82C
0x18000d861  lea     r15, aCtapsrvcheckwe; "_CtapSrvCheckWellKnownSidMembership"
0x18000d868  jmp     loc_18000D957
0x18000d86d  cmp     r14d, 4
0x18000d871  jnz     loc_18000D93B
0x18000d877  cmp     [rbp+57h+TokenInformation], r13d
0x18000d87b  jz      loc_18000D93B
0x18000d881  lea     rdx, [rbp+57h+IsMember]
0x18000d885  mov     qword ptr [rbp+57h+IsMember], r13
0x18000d889  mov     rcx, rbx; TokenHandle
0x18000d88c  mov     qword ptr [rbp+57h+cbSid], r13
0x18000d890  mov     r14, r13
0x18000d893  mov     [rbp+57h+var_88], r13
0x18000d897  mov     r12, r13
0x18000d89a  mov     esi, 80090011h
0x18000d89f  call    _CtapSrvQueryTokenSecurityAttributes
0x18000d8a4  mov     r13, qword ptr [rbp+57h+IsMember]
0x18000d8a8  test    r13, r13
0x18000d8ab  jz      short loc_18000D8C2
0x18000d8ad  lea     rdx, [rbp+57h+cbSid]
0x18000d8b1  mov     rcx, r13
0x18000d8b4  call    _CtapSrvExtractTokenSecurityPublisher
0x18000d8b9  mov     r14, qword ptr [rbp+57h+cbSid]
0x18000d8bd  test    r14, r14
0x18000d8c0  jnz     short loc_18000D8EF
0x18000d8c2  lea     rdx, [rbp+57h+var_88]
0x18000d8c6  mov     rcx, rdi; BindingHandle
0x18000d8c9  call    _CtapSrvGetCallerProcessImageName
0x18000d8ce  mov     r12, [rbp+57h+var_88]
0x18000d8d2  test    r12, r12
0x18000d8d5  jz      short loc_18000D908
0x18000d8d7  lea     r8, [rbp+57h+cbSid]
0x18000d8db  mov     rdx, r12
0x18000d8de  mov     rcx, rdi; BindingHandle
0x18000d8e1  call    _CtapSrvGetPublisherFromImageName
0x18000d8e6  mov     r14, qword ptr [rbp+57h+cbSid]
0x18000d8ea  test    r14, r14
0x18000d8ed  jz      short loc_18000D908
0x18000d8ef  mov     rcx, r14
0x18000d8f2  call    _CtapSrvIsMicrosoftPublisher
0x18000d8f7  test    eax, eax
0x18000d8f9  jnz     short loc_18000D904
0x18000d8fb  lea     r15, aNotmicrosoft; "NotMicrosoft"
0x18000d902  jmp     short loc_18000D90F
0x18000d904  xor     esi, esi
0x18000d906  jmp     short loc_18000D90F
0x18000d908  lea     r15, aNopublisher; "NoPublisher"
0x18000d90f  test    r12, r12
0x18000d912  jz      short loc_18000D91D
0x18000d914  mov     rcx, r12; hMem
0x18000d917  call    cs:__imp_LocalFree
0x18000d91d  test    r14, r14
0x18000d920  jz      short loc_18000D92B
0x18000d922  mov     rcx, r14; hMem
0x18000d925  call    cs:__imp_LocalFree
0x18000d92b  test    r13, r13
0x18000d92e  jz      short loc_18000D957
0x18000d930  mov     rcx, r13; hMem
0x18000d933  call    cs:__imp_LocalFree
0x18000d939  jmp     short loc_18000D957
0x18000d93b  lea     r15, aNomatch; "NoMatch"
0x18000d942  mov     esi, 8001011Bh
0x18000d947  jmp     short loc_18000D957
0x18000d949  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x18000d94e  mov     esi, eax
0x18000d950  lea     r15, aIsappcontainer; "IsAppContainer"
0x18000d957  mov     rcx, rbx; hObject
0x18000d95a  call    cs:__imp_CloseHandle
0x18000d960  mov     r12, [rsp+0E0h+arg_18]
0x18000d968  mov     rcx, rdi; BindingHandle
0x18000d96b  call    cs:__imp_RpcRevertToSelfEx
0x18000d971  mov     ebx, eax
0x18000d973  test    eax, eax
0x18000d975  jz      short loc_18000D980
0x18000d977  lea     r15, aRevert; "Revert"
0x18000d97e  jmp     short loc_18000D986
0x18000d980  mov     ebx, esi
0x18000d982  test    esi, esi
0x18000d984  jz      short loc_18000D9B8
0x18000d986  test    cs:byte_1801AEA01, 20h
0x18000d98d  jz      short loc_18000D9B8
0x18000d98f  test    r15, r15
0x18000d992  mov     [rsp+28h], ebx
0x18000d996  lea     r9, qword_18016F750
0x18000d99d  mov     dword ptr [rsp+0E0h+ReturnLength], ebx
0x18000d9a1  cmovnz  r9, r15
0x18000d9a5  lea     r8, aCtapsrvisallow; "_CtapSrvIsAllowedRpcCaller"
0x18000d9ac  lea     rdx, EVENT_CTAP_FUNCTION_WARNING
0x18000d9b3  call    McTemplateU0ssdd_EventWriteTransfer
0x18000d9b8  mov     rsi, [rsp+0E0h+arg_10]
0x18000d9c0  mov     eax, ebx
0x18000d9c2  mov     rbx, [rsp+0E0h+arg_8]
0x18000d9ca  mov     r15, [rsp+0C0h]
0x18000d9d2  mov     rcx, [rbp+57h+var_30]
0x18000d9d6  xor     rcx, rsp; StackCookie
0x18000d9d9  call    __security_check_cookie
0x18000d9de  add     rsp, 0C8h
0x18000d9e5  pop     r14
0x18000d9e7  pop     r13
0x18000d9e9  pop     rdi
0x18000d9ea  pop     rbp
0x18000d9eb  retn
```
