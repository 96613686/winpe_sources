# TsiGetRPCClientSecurityInformation(_SCHEDULE_SID * *,_APPCONTAINER_SECURITY_INFO * *)

- ea: `0x180004db0`
- end: `0x1800052d0`
- name: `?TsiGetRPCClientSecurityInformation@@YAJPEAPEAU_SCHEDULE_SID@@PEAPEAU_APPCONTAINER_SECURITY_INFO@@@Z`
- size: `1312`
- prototype: `__int64 __fastcall(struct _SCHEDULE_SID **, struct _APPCONTAINER_SECURITY_INFO **)`
- caller_count: `4`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002f00`
- `0x180003fa0`
- `0x180006410`
- `0x180018dac`

## callees

- `0x180002c04`
- `0x180004db0`
- `0x1800052e0`
- `0x180005400`
- `0x180010094`
- `0x180010208`
- `0x180014fbc`
- `0x180015068`
- `0x18002031c`
- `0x18002041c`
- `0x180020c02`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005180`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005180`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180004f4d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180005014`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800051a8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800051d8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180005221`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800052a5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180004f4d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180005014`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800051a8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800051d8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180005221`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800052a5`
- `RPCRT4!RpcImpersonateClient` at `0x180004df3`
- `RPCRT4!RpcImpersonateClient` at `0x180004df3`
- `RPCRT4!RpcRevertToSelf` at `0x180004e2f`
- `RPCRT4!RpcRevertToSelf` at `0x1800050e1`
- `RPCRT4!RpcRevertToSelf` at `0x180004e2f`
- `RPCRT4!RpcRevertToSelf` at `0x1800050e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004eb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000505b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005130`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004eb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000505b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005130`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004f76`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004f76`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180004e21`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180004e21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180004e09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180004e09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000503c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000503c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004f0b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004f0b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004e67`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004eaa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004efa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004e67`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004eaa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004efa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000500b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000500b`
- `ntdll!RtlCopySid` at `0x180004f39`
- `ntdll!RtlCopySid` at `0x180004f39`

## pseudocode

```c
__int64 __fastcall TsiGetRPCClientSecurityInformation(
        struct _SCHEDULE_SID **a1,
        struct _APPCONTAINER_SECURITY_INFO **a2)
{
  struct _APPCONTAINER_SECURITY_INFO **v2; // r13
  struct _SCHEDULE_SID **v3; // r15
  RPC_STATUS v4; // eax
  signed int LastError; // ebx
  HANDLE CurrentThread; // rax
  RPC_STATUS v7; // eax
  void *v8; // rsi
  void *v9; // r12
  PSID *v10; // r14
  ULONG LengthSid; // r13d
  void *v12; // rax
  void *v13; // r15
  __int64 v14; // rax
  unsigned int v16; // r14d
  struct _SCHEDULE_SID *v17; // rax
  struct _SCHEDULE_SID *v18; // rbx
  const wchar_t *v19; // rax
  size_t v20; // rdx
  size_t v21; // r8
  size_t v22; // rdx
  wchar_t *v23; // rcx
  size_t *v24; // r8
  signed int v26; // eax
  struct _APPCONTAINER_SECURITY_INFO *v27; // r14
  struct _SCHEDULE_SID **v28; // r12
  struct _SCHEDULE_SID **v29; // rdx
  LPWSTR v30; // r13
  unsigned __int64 v31; // rax
  struct _SCHEDULE_SID **v32; // rax
  LPWSTR v33; // rbx
  size_t v34; // r8
  struct _SCHEDULE_SID **v35; // rcx
  unsigned int i; // r13d
  int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // rax
  struct _APPCONTAINER_SECURITY_INFO **v40; // rax
  PDWORD ReturnLength; // [rsp+20h] [rbp-60h]
  DWORD v42; // [rsp+30h] [rbp-50h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-48h] BYREF
  __int128 v44; // [rsp+40h] [rbp-40h] BYREF
  struct _SCHEDULE_SID **v45; // [rsp+A0h] [rbp+20h] BYREF
  struct _APPCONTAINER_SECURITY_INFO **v46; // [rsp+A8h] [rbp+28h]
  LPWSTR TokenInformation; // [rsp+B0h] [rbp+30h] BYREF
  LPWSTR v48; // [rsp+B8h] [rbp+38h]

  v46 = a2;
  v45 = a1;
  v2 = a2;
  v3 = a1;
  if ( __PAIR128__((unsigned __int64)a1, (unsigned __int64)a2) == 0 )
    return 2147500035LL;
  v4 = RpcImpersonateClient(0);
  LastError = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      LastError = (unsigned __int16)v4 | 0x80070000;
    goto LABEL_36;
  }
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    RpcRevertToSelf();
    if ( LastError <= 0 )
      goto LABEL_36;
    LastError = (unsigned __int16)LastError;
    goto LABEL_54;
  }
  v7 = RpcRevertToSelf();
  LastError = v7;
  if ( !v7 )
  {
    v8 = TokenHandle;
    goto LABEL_6;
  }
  if ( v7 > 0 )
  {
    LastError = (unsigned __int16)v7;
LABEL_54:
    LastError |= 0x80070000;
  }
LABEL_36:
  v8 = 0;
  if ( LastError < 0 )
    goto LABEL_37;
LABEL_6:
  v42 = 0;
  LODWORD(TokenInformation) = 0;
  LODWORD(v48) = 0;
  if ( GetTokenInformation(v8, TokenIsAppContainer, &TokenInformation, 4u, &v42) )
    LODWORD(v48) = (_DWORD)TokenInformation != 0;
  if ( v3 )
  {
    LODWORD(TokenInformation) = 0;
    v9 = 0;
    if ( GetTokenInformation(v8, TokenUser, 0, 0, (PDWORD)&TokenInformation) || GetLastError() != 122 )
    {
      v26 = GetLastError();
      LastError = v26;
      if ( v26 > 0 )
        LastError = (unsigned __int16)v26 | 0x80070000;
    }
    else
    {
      v10 = (PSID *)operator new[]((unsigned int)TokenInformation, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v10 )
      {
        LastError = -2147024882;
        goto LABEL_45;
      }
      if ( GetTokenInformation(v8, TokenUser, v10, (DWORD)TokenInformation, (PDWORD)&TokenInformation) )
      {
        LengthSid = GetLengthSid(*v10);
        v12 = operator new[](LengthSid, (const struct std::nothrow_t *)&std::nothrow);
        v13 = v12;
        if ( v12 )
        {
          LastError = 0;
          RtlCopySid(LengthSid, v12, *v10);
          v9 = v13;
        }
        else
        {
          LastError = -2147024882;
        }
        v2 = v46;
        v3 = v45;
      }
      else
      {
        LastError = -2147467259;
      }
      operator delete[](v10);
    }
    if ( LastError < 0 )
      goto LABEL_45;
    TokenInformation = 0;
    if ( !v9 )
      goto LABEL_27;
    if ( !ConvertSidToStringSidW(v9, &TokenInformation) )
    {
      GetLastError();
      goto LABEL_27;
    }
    v14 = -1;
    while ( TokenInformation[++v14] != 0 )
      ;
    v16 = 2 * v14 + 2;
    if ( 2 * (_DWORD)v14 == -2 )
      goto LABEL_27;
    v17 = (struct _SCHEDULE_SID *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
    v18 = v17;
    if ( !v17 )
      goto LABEL_27;
    *((_DWORD *)v17 + 2) = v16;
    v19 = (const wchar_t *)operator new[](v16, (const struct std::nothrow_t *)&std::nothrow);
    v20 = (unsigned __int64)*((unsigned int *)v18 + 2) >> 1;
    *(_QWORD *)v18 = v19;
    if ( StringValidateDestW(v19, v20, v21) < 0 )
    {
      if ( v22 )
        *v23 = 0;
    }
    else if ( StringCopyWorkerW(v23, v22, v24, TokenInformation, (size_t)ReturnLength) >= 0 )
    {
      *v3 = v18;
      goto LABEL_27;
    }
    TsiFreeScheduleSid(v18);
LABEL_27:
    LocalFree(TokenInformation);
    operator delete[](v9);
  }
  if ( v2 )
  {
    if ( !(_DWORD)v48 )
    {
      *v2 = 0;
      goto LABEL_29;
    }
    v45 = 0;
    TokenInformation = 0;
    LastError = TsiGetAppContainerSid(&v45, v8);
    if ( LastError >= 0 )
    {
      LastError = TsiGetCapabilities(&TokenInformation, v8);
      if ( LastError >= 0 )
      {
        v27 = (struct _APPCONTAINER_SECURITY_INFO *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
        if ( !v27 )
        {
          operator delete[](v45);
          goto LABEL_30;
        }
        v28 = v45;
        v29 = v45;
        *(_OWORD *)v27 = 0;
        *((_QWORD *)v27 + 2) = 0;
        LastError = TsiBuildStringSid(v27, v29);
        if ( LastError >= 0 )
        {
          v30 = TokenInformation;
          v31 = 16LL * *(unsigned int *)TokenInformation;
          if ( !is_mul_ok(*(unsigned int *)TokenInformation, 0x10u) )
            v31 = -1;
          v32 = (struct _SCHEDULE_SID **)operator new[](v31, (const struct std::nothrow_t *)&std::nothrow);
          v45 = v32;
          if ( !v32 )
          {
            operator delete[](v28);
            TsiFreeAppContainerSecurityInfo(v27);
            goto LABEL_30;
          }
          v33 = v30 + 4;
          v34 = 16LL * *(unsigned int *)v30;
          v48 = v30 + 4;
          memset_0(v32, 0, v34);
          v35 = v45;
          for ( i = 0; i < *(_DWORD *)TokenInformation; ++i )
          {
            v37 = *((_DWORD *)v33 + 2);
            v38 = *(_QWORD *)v33;
            v44 = 0;
            DWORD2(v44) = v37;
            LastError = TsiBuildStringSid(&v44, v38);
            if ( LastError < 0 )
            {
              operator delete[](v28);
              TsiFreeAppContainerSecurityInfo(v27);
              v2 = v46;
              goto LABEL_37;
            }
            v35 = v45;
            v33 = v48 + 8;
            v39 = 2LL * i;
            v48 += 8;
            *(_OWORD *)&v45[v39] = v44;
          }
          *((_DWORD *)v27 + 4) = *(_DWORD *)TokenInformation;
          v40 = v46;
          *((_QWORD *)v27 + 1) = v35;
          *v40 = v27;
          goto LABEL_29;
        }
        operator delete[](v28);
        TsiFreeAppContainerSecurityInfo(v27);
      }
      else
      {
        operator delete(v45);
      }
    }
LABEL_37:
    if ( !v3 )
    {
LABEL_38:
      if ( v2 && *v2 )
        TsiFreeAppContainerSecurityInfo(*v2);
      goto LABEL_30;
    }
LABEL_45:
    if ( *v3 )
      TsiFreeScheduleSid(*v3);
    goto LABEL_38;
  }
LABEL_29:
  LastError = 0;
LABEL_30:
  if ( v8 )
    CloseHandle(v8);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180004db0  mov     [rsp-18h+arg_8], rdx
0x180004db5  mov     [rsp-18h+arg_0], rcx
0x180004dba  push    rbp
0x180004dbb  push    r13
0x180004dbd  push    r15
0x180004dbf  mov     rbp, rsp
0x180004dc2  sub     rsp, 80h
0x180004dc9  mov     r13, rdx
0x180004dcc  mov     r15, rcx
0x180004dcf  test    rcx, rcx
0x180004dd2  jz      loc_1800050F0
0x180004dd8  mov     [rsp+80h+var_8], rbx
0x180004ddd  xor     ecx, ecx; BindingHandle
0x180004ddf  mov     [rsp+80h+var_10], rsi
0x180004de4  mov     [rsp+80h+var_18], rdi
0x180004de9  mov     [rsp+80h+var_20], r12
0x180004dee  mov     [rsp+80h+var_28], r14
0x180004df3  call    cs:__imp_RpcImpersonateClient
0x180004df9  mov     ebx, eax
0x180004dfb  test    eax, eax
0x180004dfd  jnz     loc_1800050D3
0x180004e03  xor     edi, edi
0x180004e05  mov     [rbp+TokenHandle], rdi
0x180004e09  call    cs:__imp_GetCurrentThread
0x180004e0f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180004e13  mov     edx, 8; DesiredAccess
0x180004e18  mov     rcx, rax; ThreadHandle
0x180004e1b  mov     r8d, 1; OpenAsSelf
0x180004e21  call    cs:__imp_OpenThreadToken
0x180004e27  test    eax, eax
0x180004e29  jz      loc_1800050D9
0x180004e2f  call    cs:__imp_RpcRevertToSelf
0x180004e35  mov     ebx, eax
0x180004e37  test    eax, eax
0x180004e39  jnz     loc_180005079
0x180004e3f  mov     rsi, [rbp+TokenHandle]
0x180004e43  lea     rax, [rbp+var_50]
0x180004e47  mov     [rbp+var_50], edi
0x180004e4a  mov     r9d, 4; TokenInformationLength
0x180004e50  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x180004e55  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180004e59  mov     dword ptr [rbp+TokenInformation], edi
0x180004e5c  mov     edx, 1Dh; TokenInformationClass
0x180004e61  mov     dword ptr [rbp+arg_18], edi
0x180004e64  mov     rcx, rsi; TokenHandle
0x180004e67  call    cs:__imp_GetTokenInformation
0x180004e6d  test    eax, eax
0x180004e6f  jz      short loc_180004E7D
0x180004e71  cmp     dword ptr [rbp+TokenInformation], 0
0x180004e75  mov     ebx, edi
0x180004e77  setnz   bl
0x180004e7a  mov     dword ptr [rbp+arg_18], ebx
0x180004e7d  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180004e84  test    r15, r15
0x180004e87  jz      loc_18000501A
0x180004e8d  lea     rax, [rbp+TokenInformation]
0x180004e91  mov     dword ptr [rbp+TokenInformation], edi
0x180004e94  xor     r9d, r9d; TokenInformationLength
0x180004e97  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x180004e9c  xor     r8d, r8d; TokenInformation
0x180004e9f  mov     edx, 1; TokenInformationClass
0x180004ea4  mov     rcx, rsi; TokenHandle
0x180004ea7  mov     r12, rdi
0x180004eaa  call    cs:__imp_GetTokenInformation
0x180004eb0  test    eax, eax
0x180004eb2  jnz     loc_18000505B
0x180004eb8  call    cs:__imp_GetLastError
0x180004ebe  cmp     eax, 7Ah ; 'z'
0x180004ec1  jnz     loc_18000505B
0x180004ec7  mov     ecx, dword ptr [rbp+TokenInformation]; unsigned __int64
0x180004eca  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004ed1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180004ed6  mov     r14, rax
0x180004ed9  test    rax, rax
0x180004edc  jz      loc_1800050BF
0x180004ee2  mov     r9d, dword ptr [rbp+TokenInformation]; TokenInformationLength
0x180004ee6  lea     rax, [rbp+TokenInformation]
0x180004eea  mov     r8, r14; TokenInformation
0x180004eed  mov     [rsp+80h+ReturnLength], rax; cchToCopy
0x180004ef2  mov     edx, 1; TokenInformationClass
0x180004ef7  mov     rcx, rsi; TokenHandle
0x180004efa  call    cs:__imp_GetTokenInformation
0x180004f00  test    eax, eax
0x180004f02  jz      loc_18000511C
0x180004f08  mov     rcx, [r14]; pSid
0x180004f0b  call    cs:__imp_GetLengthSid
0x180004f11  mov     ecx, eax; unsigned __int64
0x180004f13  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004f1a  mov     r13d, eax
0x180004f1d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180004f22  mov     r15, rax
0x180004f25  test    rax, rax
0x180004f28  jz      loc_180005126
0x180004f2e  mov     r8, [r14]; SourceSid
0x180004f31  mov     rdx, rax; DestinationSid
0x180004f34  mov     ecx, r13d; DestinationSidLength
0x180004f37  mov     ebx, edi
0x180004f39  call    cs:__imp_RtlCopySid
0x180004f3f  mov     r12, r15
0x180004f42  mov     r13, [rbp+arg_8]
0x180004f46  mov     r15, [rbp+arg_0]
0x180004f4a  mov     rcx, r14
0x180004f4d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180004f53  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180004f5a  test    ebx, ebx
0x180004f5c  js      loc_1800050C4
0x180004f62  mov     [rbp+TokenInformation], rdi
0x180004f66  test    r12, r12
0x180004f69  jz      loc_180005007
0x180004f6f  lea     rdx, [rbp+TokenInformation]; StringSid
0x180004f73  mov     rcx, r12; Sid
0x180004f76  call    cs:__imp_ConvertSidToStringSidW
0x180004f7c  test    eax, eax
0x180004f7e  jz      loc_180005130
0x180004f84  mov     rcx, [rbp+TokenInformation]
0x180004f88  mov     rax, r14
0x180004f8b  nop     dword ptr [rax+rax+00h]
0x180004f90  cmp     word ptr [rcx+rax*2+2], 0
0x180004f96  lea     rax, [rax+1]
0x180004f9a  jnz     short loc_180004F90
0x180004f9c  lea     r14d, ds:2[rax*2]
0x180004fa4  test    r14d, r14d
0x180004fa7  jz      short loc_180005007
0x180004fa9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004fb0  mov     ecx, 10h; unsigned __int64
0x180004fb5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004fba  mov     rbx, rax
0x180004fbd  test    rax, rax
0x180004fc0  jz      short loc_180005007
0x180004fc2  mov     ecx, r14d; unsigned __int64
0x180004fc5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004fcc  mov     [rax+8], r14d
0x180004fd0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180004fd5  mov     edx, [rbx+8]
0x180004fd8  mov     rcx, rax; pszDest
0x180004fdb  shr     rdx, 1; cchDest
0x180004fde  mov     [rbx], rax
0x180004fe1  call    StringValidateDestW
0x180004fe6  test    eax, eax
0x180004fe8  js      loc_18000513B
0x180004fee  mov     r9, [rbp+TokenInformation]; pszSrc
0x180004ff2  call    StringCopyWorkerW
0x180004ff7  test    eax, eax
0x180004ff9  jns     loc_1800050A4
0x180004fff  mov     rcx, rbx; struct _SCHEDULE_SID *
0x180005002  call    ?TsiFreeScheduleSid@@YAJPEAU_SCHEDULE_SID@@@Z; TsiFreeScheduleSid(_SCHEDULE_SID *)
0x180005007  mov     rcx, [rbp+TokenInformation]; hMem
0x18000500b  call    cs:__imp_LocalFree
0x180005011  mov     rcx, r12
0x180005014  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000501a  test    r13, r13
0x18000501d  jnz     loc_1800050AC
0x180005023  mov     ebx, edi
0x180005025  mov     r14, [rsp+80h+var_28]
0x18000502a  mov     r12, [rsp+80h+var_20]
0x18000502f  mov     rdi, [rsp+80h+var_18]
0x180005034  test    rsi, rsi
0x180005037  jz      short loc_180005042
0x180005039  mov     rcx, rsi; hObject
0x18000503c  call    cs:__imp_CloseHandle
0x180005042  mov     rsi, [rsp+80h+var_10]
0x180005047  mov     eax, ebx
0x180005049  mov     rbx, [rsp+80h+var_8]
0x18000504e  add     rsp, 80h
0x180005055  pop     r15
0x180005057  pop     r13
0x180005059  pop     rbp
0x18000505a  retn
0x18000505b  call    cs:__imp_GetLastError
0x180005061  mov     ebx, eax
0x180005063  test    eax, eax
0x180005065  jle     loc_180004F5A
0x18000506b  movzx   ebx, ax
0x18000506e  or      ebx, 80070000h
0x180005074  jmp     loc_180004F5A
0x180005079  jg      loc_18000510E
0x18000507f  mov     rsi, rdi
0x180005082  test    ebx, ebx
0x180005084  jns     loc_180004E43
0x18000508a  test    r15, r15
0x18000508d  jnz     short loc_1800050C4
0x18000508f  test    r13, r13
0x180005092  jz      short loc_180005025
0x180005094  mov     rcx, [r13+0]; struct _APPCONTAINER_SECURITY_INFO *
0x180005098  test    rcx, rcx
0x18000509b  jz      short loc_180005025
0x18000509d  call    ?TsiFreeAppContainerSecurityInfo@@YAJPEAU_APPCONTAINER_SECURITY_INFO@@@Z; TsiFreeAppContainerSecurityInfo(_APPCONTAINER_SECURITY_INFO *)
0x1800050a2  jmp     short loc_180005025
0x1800050a4  mov     [r15], rbx
0x1800050a7  jmp     loc_180005007
0x1800050ac  cmp     dword ptr [rbp+arg_18], 0
0x1800050b0  jnz     loc_18000514C
0x1800050b6  mov     [r13+0], rdi
0x1800050ba  jmp     loc_180005023
0x1800050bf  mov     ebx, 8007000Eh
0x1800050c4  mov     rcx, [r15]; struct _SCHEDULE_SID *
0x1800050c7  test    rcx, rcx
0x1800050ca  jz      short loc_18000508F
0x1800050cc  call    ?TsiFreeScheduleSid@@YAJPEAU_SCHEDULE_SID@@@Z; TsiFreeScheduleSid(_SCHEDULE_SID *)
0x1800050d1  jmp     short loc_18000508F
0x1800050d3  jg      short loc_180005103
0x1800050d5  xor     edi, edi
0x1800050d7  jmp     short loc_18000507F
0x1800050d9  call    cs:__imp_GetLastError
0x1800050df  mov     ebx, eax
0x1800050e1  call    cs:__imp_RpcRevertToSelf
0x1800050e7  test    ebx, ebx
0x1800050e9  jle     short loc_18000507F
0x1800050eb  movzx   ebx, bx
0x1800050ee  jmp     short loc_180005111
0x1800050f0  test    rdx, rdx
0x1800050f3  jnz     loc_180004DD8
0x1800050f9  mov     eax, 80004003h
0x1800050fe  jmp     loc_18000504E
0x180005103  movzx   ebx, ax
0x180005106  or      ebx, 80070000h
0x18000510c  jmp     short loc_1800050D5
0x18000510e  movzx   ebx, ax
0x180005111  or      ebx, 80070000h
0x180005117  jmp     loc_18000507F
0x18000511c  mov     ebx, 80004005h
0x180005121  jmp     loc_180004F4A
0x180005126  mov     ebx, 8007000Eh
0x18000512b  jmp     loc_180004F42
0x180005130  call    cs:__imp_GetLastError
0x180005136  jmp     loc_180005007
0x18000513b  test    rdx, rdx
0x18000513e  jz      loc_180004FFF
0x180005144  mov     [rcx], di
0x180005147  jmp     loc_180004FFF
0x18000514c  mov     rdx, rsi
0x18000514f  mov     [rbp+arg_0], rdi
0x180005153  lea     rcx, [rbp+arg_0]
0x180005157  mov     [rbp+TokenInformation], rdi
0x18000515b  call    TsiGetAppContainerSid
0x180005160  mov     ebx, eax
0x180005162  test    eax, eax
0x180005164  js      loc_18000508A
0x18000516a  mov     rdx, rsi
0x18000516d  lea     rcx, [rbp+TokenInformation]
0x180005171  call    TsiGetCapabilities
0x180005176  mov     ebx, eax
0x180005178  test    eax, eax
0x18000517a  jns     short loc_18000518B
0x18000517c  mov     rcx, [rbp+arg_0]
0x180005180  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005186  jmp     loc_18000508A
0x18000518b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005192  mov     ecx, 18h; unsigned __int64
0x180005197  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000519c  mov     r14, rax
0x18000519f  test    rax, rax
0x1800051a2  jnz     short loc_1800051B3
0x1800051a4  mov     rcx, [rbp+arg_0]
0x1800051a8  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800051ae  jmp     loc_180005025
0x1800051b3  mov     r12, [rbp+arg_0]
0x1800051b7  xorps   xmm0, xmm0
0x1800051ba  xor     eax, eax
0x1800051bc  mov     rdx, r12
0x1800051bf  movups  xmmword ptr [r14], xmm0
0x1800051c3  mov     rcx, r14
0x1800051c6  mov     [r14+10h], rax
0x1800051ca  call    TsiBuildStringSid
0x1800051cf  mov     ebx, eax
0x1800051d1  test    eax, eax
0x1800051d3  jns     short loc_1800051EB
0x1800051d5  mov     rcx, r12
0x1800051d8  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800051de  mov     rcx, r14; struct _APPCONTAINER_SECURITY_INFO *
0x1800051e1  call    ?TsiFreeAppContainerSecurityInfo@@YAJPEAU_APPCONTAINER_SECURITY_INFO@@@Z; TsiFreeAppContainerSecurityInfo(_APPCONTAINER_SECURITY_INFO *)
0x1800051e6  jmp     loc_18000508A
0x1800051eb  mov     r13, [rbp+TokenInformation]
0x1800051ef  mov     eax, 10h
0x1800051f4  mov     ecx, [r13+0]
0x1800051f8  mul     rcx
0x1800051fb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180005202  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005209  cmovb   rax, rcx
0x18000520d  mov     rcx, rax; unsigned __int64
0x180005210  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005215  mov     [rbp+arg_0], rax
0x180005219  test    rax, rax
0x18000521c  jnz     short loc_180005234
0x18000521e  mov     rcx, r12
0x180005221  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180005227  mov     rcx, r14; struct _APPCONTAINER_SECURITY_INFO *
0x18000522a  call    ?TsiFreeAppContainerSecurityInfo@@YAJPEAU_APPCONTAINER_SECURITY_INFO@@@Z; TsiFreeAppContainerSecurityInfo(_APPCONTAINER_SECURITY_INFO *)
0x18000522f  jmp     loc_180005025
0x180005234  mov     r8d, [r13+0]
0x180005238  lea     rbx, [r13+8]
0x18000523c  shl     r8, 4; Size
0x180005240  xor     edx, edx; Val
0x180005242  mov     rcx, rax; void *
0x180005245  mov     [rbp+arg_18], rbx
0x180005249  call    memset_0
0x18000524e  mov     rcx, [rbp+arg_0]
0x180005252  mov     r13d, edi
0x180005255  mov     rax, [rbp+TokenInformation]
0x180005259  mov     eax, [rax]
  ... truncated ...
```
