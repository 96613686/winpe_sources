# Rpc_DnsRegistryAccessCheck

- ea: `0x18000f1cc`
- end: `0x18000f3b9`
- name: `Rpc_DnsRegistryAccessCheck`
- size: `493`
- prototype: `__int64 __fastcall(DWORD DesiredAccess)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800023d0`
- `0x180002550`
- `0x180002650`
- `0x180002740`

## callees

- `0x1800014b0`
- `0x18000f1cc`
- `0x180015008`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18000f257`
- `RPCRT4!RpcImpersonateClient` at `0x18000f257`
- `RPCRT4!RpcRevertToSelf` at `0x18000f2c9`
- `RPCRT4!RpcRevertToSelf` at `0x18000f36f`
- `RPCRT4!RpcRevertToSelf` at `0x18000f2c9`
- `RPCRT4!RpcRevertToSelf` at `0x18000f36f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f318`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f318`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000f2a2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000f2a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f28a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f28a`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000f30e`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000f30e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f365`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f365`

## pseudocode

```c
__int64 __fastcall Rpc_DnsRegistryAccessCheck(DWORD DesiredAccess)
{
  DWORD LastError; // eax
  unsigned int v3; // ebx
  int v4; // edi
  __int64 v5; // rdx
  HANDLE CurrentThread; // rax
  void *TokenHandle; // [rsp+40h] [rbp-9h] BYREF
  WINBOOL AccessStatus; // [rsp+48h] [rbp-1h] BYREF
  DWORD PrivilegeSetLength; // [rsp+4Ch] [rbp+3h] BYREF
  DWORD GrantedAccess; // [rsp+50h] [rbp+7h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+58h] [rbp+Fh] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+68h] [rbp+1Fh] BYREF

  AccessStatus = 0;
  GrantedAccess = 0;
  PrivilegeSetLength = 0;
  GenericMapping.GenericRead = 131097;
  GenericMapping.GenericExecute = 131097;
  TokenHandle = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  GenericMapping.GenericWrite = 131078;
  GenericMapping.GenericAll = 983103;
  if ( (xmmword_18001F260 & 0x80u) != 0LL )
    WPP_SF_d(1031, 41, WPP_40375b7da6503ec0d2901a6efbf6c2e2_Traceguids, DesiredAccess);
  LastError = RpcImpersonateClient(0);
  v3 = LastError;
  if ( LastError )
  {
    v4 = 0;
    if ( (BYTE1(xmmword_18001F260) & 8) == 0 )
      goto LABEL_16;
    v5 = 42;
    goto LABEL_6;
  }
  CurrentThread = GetCurrentThread();
  v4 = 1;
  AccessStatus = OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle);
  if ( AccessStatus )
  {
    RpcRevertToSelf();
    PrivilegeSetLength = 20;
    v4 = 0;
    if ( AccessCheck(
           (PSECURITY_DESCRIPTOR)&g_rgbZtdnsSecurityDescriptor,
           TokenHandle,
           DesiredAccess,
           &GenericMapping,
           &PrivilegeSet,
           &PrivilegeSetLength,
           &GrantedAccess,
           &AccessStatus) )
    {
      if ( (xmmword_18001F260 & 0x80u) != 0LL )
        WPP_SF_d(1031, 45, WPP_40375b7da6503ec0d2901a6efbf6c2e2_Traceguids, (unsigned int)AccessStatus);
      v3 = AccessStatus == 0 ? 5 : 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
      {
        v5 = 44;
        goto LABEL_6;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    {
      v5 = 43;
LABEL_6:
      WPP_SF_d(1035, v5, WPP_40375b7da6503ec0d2901a6efbf6c2e2_Traceguids, LastError);
    }
  }
LABEL_16:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v4 )
    RpcRevertToSelf();
  if ( (xmmword_18001F260 & 0x80u) != 0LL )
    WPP_SF_d(1031, 46, WPP_40375b7da6503ec0d2901a6efbf6c2e2_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18000f1cc  mov     [rsp-8+arg_8], rbx
0x18000f1d1  mov     [rsp-8+arg_10], rsi
0x18000f1d6  push    rbp
0x18000f1d7  push    rdi
0x18000f1d8  push    r15
0x18000f1da  lea     rbp, [rsp-47h]
0x18000f1df  sub     rsp, 90h
0x18000f1e6  mov     rax, cs:__security_cookie
0x18000f1ed  xor     rax, rsp
0x18000f1f0  mov     [rbp+57h+var_20], rax
0x18000f1f4  xor     eax, eax
0x18000f1f6  mov     [rbp+57h+var_58], 0
0x18000f1fd  mov     [rbp+57h+var_38.Privilege.Attributes], eax
0x18000f200  xorps   xmm0, xmm0
0x18000f203  mov     [rbp+57h+var_50], eax
0x18000f206  mov     esi, ecx
0x18000f208  mov     [rbp+57h+var_54], eax
0x18000f20b  mov     eax, 20019h
0x18000f210  mov     [rbp+57h+GenericMapping.GenericRead], eax
0x18000f213  mov     [rbp+57h+GenericMapping.GenericExecute], eax
0x18000f216  mov     [rbp+57h+TokenHandle], 0
0x18000f21e  movups  xmmword ptr [rbp+57h+var_38.PrivilegeCount], xmm0
0x18000f222  mov     [rbp+57h+GenericMapping.GenericWrite], 20006h
0x18000f229  mov     [rbp+57h+GenericMapping.GenericAll], 0F003Fh
0x18000f230  cmp     byte ptr cs:xmmword_18001F260, 0
0x18000f237  lea     r15, WPP_40375b7da6503ec0d2901a6efbf6c2e2_Traceguids
0x18000f23e  jge     short loc_18000F255
0x18000f240  mov     edx, 29h ; ')'
0x18000f245  mov     ecx, 407h
0x18000f24a  mov     r9d, esi
0x18000f24d  mov     r8, r15
0x18000f250  call    WPP_SF_d
0x18000f255  xor     ecx, ecx; BindingHandle
0x18000f257  call    cs:__imp_RpcImpersonateClient
0x18000f25d  mov     ebx, eax
0x18000f25f  test    eax, eax
0x18000f261  jz      short loc_18000F28A
0x18000f263  xor     edi, edi
0x18000f265  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000f26c  jz      loc_18000F35C
0x18000f272  lea     edx, [rdi+2Ah]
0x18000f275  mov     ecx, 40Bh
0x18000f27a  mov     r9d, eax
0x18000f27d  mov     r8, r15
0x18000f280  call    WPP_SF_d
0x18000f285  jmp     loc_18000F35C
0x18000f28a  call    cs:__imp_GetCurrentThread
0x18000f290  mov     edi, 1
0x18000f295  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18000f299  mov     rcx, rax; ThreadHandle
0x18000f29c  mov     r8d, edi; OpenAsSelf
0x18000f29f  lea     edx, [rdi+7]; DesiredAccess
0x18000f2a2  call    cs:__imp_OpenThreadToken
0x18000f2a8  mov     [rbp+57h+var_58], eax
0x18000f2ab  test    eax, eax
0x18000f2ad  jnz     short loc_18000F2C9
0x18000f2af  call    cs:__imp_GetLastError
0x18000f2b5  mov     ebx, eax
0x18000f2b7  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000f2be  jz      loc_18000F35C
0x18000f2c4  lea     edx, [rdi+2Ah]
0x18000f2c7  jmp     short loc_18000F275
0x18000f2c9  call    cs:__imp_RpcRevertToSelf
0x18000f2cf  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x18000f2d3  lea     rax, [rbp+57h+var_58]
0x18000f2d7  mov     [rsp+0A0h+AccessStatus], rax; AccessStatus
0x18000f2dc  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18000f2e0  lea     rax, [rbp+57h+var_50]
0x18000f2e4  mov     [rbp+57h+var_54], 14h
0x18000f2eb  mov     [rsp+0A0h+GrantedAccess], rax; GrantedAccess
0x18000f2f0  lea     rcx, ?g_rgbZtdnsSecurityDescriptor@@3QBEB; pSecurityDescriptor
0x18000f2f7  lea     rax, [rbp+57h+var_54]
0x18000f2fb  mov     r8d, esi; DesiredAccess
0x18000f2fe  mov     [rsp+0A0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18000f303  xor     edi, edi
0x18000f305  lea     rax, [rbp+57h+var_38]
0x18000f309  mov     [rsp+0A0h+PrivilegeSet], rax; PrivilegeSet
0x18000f30e  call    cs:__imp_AccessCheck
0x18000f314  test    eax, eax
0x18000f316  jnz     short loc_18000F331
0x18000f318  call    cs:__imp_GetLastError
0x18000f31e  mov     ebx, eax
0x18000f320  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000f327  jz      short loc_18000F35C
0x18000f329  lea     edx, [rdi+2Ch]
0x18000f32c  jmp     loc_18000F275
0x18000f331  cmp     byte ptr cs:xmmword_18001F260, dil
0x18000f338  jge     short loc_18000F350
0x18000f33a  mov     r9d, [rbp+57h+var_58]
0x18000f33e  mov     edx, 2Dh ; '-'
0x18000f343  mov     ecx, 407h
0x18000f348  mov     r8, r15
0x18000f34b  call    WPP_SF_d
0x18000f350  mov     eax, [rbp+57h+var_58]
0x18000f353  neg     eax
0x18000f355  sbb     ebx, ebx
0x18000f357  not     ebx
0x18000f359  and     ebx, 5
0x18000f35c  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18000f360  test    rcx, rcx
0x18000f363  jz      short loc_18000F36B
0x18000f365  call    cs:__imp_CloseHandle
0x18000f36b  test    edi, edi
0x18000f36d  jz      short loc_18000F375
0x18000f36f  call    cs:__imp_RpcRevertToSelf
0x18000f375  cmp     byte ptr cs:xmmword_18001F260, 0
0x18000f37c  jge     short loc_18000F393
0x18000f37e  mov     edx, 2Eh ; '.'
0x18000f383  mov     ecx, 407h
0x18000f388  mov     r9d, ebx
0x18000f38b  mov     r8, r15
0x18000f38e  call    WPP_SF_d
0x18000f393  mov     eax, ebx
0x18000f395  mov     rcx, [rbp+57h+var_20]
0x18000f399  xor     rcx, rsp; StackCookie
0x18000f39c  call    __security_check_cookie
0x18000f3a1  lea     r11, [rsp+0A0h+var_10]
0x18000f3a9  mov     rbx, [r11+28h]
0x18000f3ad  mov     rsi, [r11+30h]
0x18000f3b1  mov     rsp, r11
0x18000f3b4  pop     r15
0x18000f3b6  pop     rdi
0x18000f3b7  pop     rbp
0x18000f3b8  retn
```
