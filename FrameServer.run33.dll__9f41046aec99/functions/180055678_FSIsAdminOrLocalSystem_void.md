# FSIsAdminOrLocalSystem(void)

- ea: `0x180055678`
- end: `0x180055835`
- name: `?FSIsAdminOrLocalSystem@@YA_NXZ`
- size: `445`
- prototype: `bool(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180017170`
- `0x180017290`
- `0x180017330`

## callees

- `0x180003e20`
- `0x18000478c`
- `0x180009608`
- `0x180055678`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800557bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800557bd`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1800556d9`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1800556d9`
- `RPCRT4!RpcImpersonateClient` at `0x180055729`
- `RPCRT4!RpcImpersonateClient` at `0x180055729`
- `RPCRT4!RpcRevertToSelfEx` at `0x180055802`
- `RPCRT4!RpcRevertToSelfEx` at `0x180055802`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180055761`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18005577a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180055761`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18005577a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18005578e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800557ae`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18005578e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800557ae`

## pseudocode

```c
char FSIsAdminOrLocalSystem(void)
{
  int v0; // eax
  bool v1; // sf
  char v2; // bl
  __int64 v3; // rdx
  bool v4; // sf
  int v5; // eax
  signed int LastError; // eax
  bool v7; // sf
  WINBOOL IsMember; // [rsp+30h] [rbp-79h] BYREF
  WINBOOL v10; // [rsp+34h] [rbp-75h] BYREF
  DWORD cbSid; // [rsp+38h] [rbp-71h] BYREF
  DWORD v12; // [rsp+3Ch] [rbp-6Dh] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp-69h] BYREF
  _BYTE pSid[80]; // [rsp+50h] [rbp-59h] BYREF
  _BYTE SidToCheck[80]; // [rsp+A0h] [rbp-9h] BYREF

  memset_0(pSid, 0, 0x44u);
  cbSid = 68;
  memset_0(SidToCheck, 0, 0x44u);
  v12 = 68;
  IsMember = 0;
  v10 = 0;
  Binding = 0;
  v0 = RpcServerInqBindingHandle(&Binding);
  v1 = v0 < 0;
  if ( v0 > 0 )
  {
    v0 = (unsigned __int16)v0 | 0x80070000;
    v1 = v0 < 0;
  }
  if ( v1 )
  {
    v2 = 1;
    if ( g_wppLevels )
    {
      v3 = 105;
LABEL_6:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v3, &WPP_1f0f67a3e2e738321c6948db893abc38_Traceguids, 0, v0);
    }
  }
  else
  {
    v0 = RpcImpersonateClient(Binding);
    v4 = v0 < 0;
    if ( v0 > 0 )
    {
      v0 = (unsigned __int16)v0 | 0x80070000;
      v4 = v0 < 0;
    }
    if ( v4 )
    {
      v2 = 1;
      if ( !g_wppLevels )
        goto LABEL_26;
      v3 = 106;
      goto LABEL_6;
    }
    v2 = 1;
    if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, &cbSid)
      && CreateWellKnownSid(WinLocalSystemSid, 0, SidToCheck, &v12) )
    {
      v5 = CheckTokenMembership(0, pSid, &IsMember);
      if ( v5 )
        v5 = IsMember;
      else
        IsMember = 0;
      if ( !v5 && !CheckTokenMembership(0, SidToCheck, &v10) )
        v10 = 0;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v7 = LastError < 0;
      }
      if ( v7 && g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          107,
          &WPP_1f0f67a3e2e738321c6948db893abc38_Traceguids,
          0,
          LastError);
    }
    RpcRevertToSelfEx(Binding);
  }
LABEL_26:
  if ( !IsMember && !v10 )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x180055678  mov     [rsp-8+arg_0], rbx
0x18005567d  push    rbp
0x18005567e  lea     rbp, [rsp-57h]
0x180055683  sub     rsp, 100h
0x18005568a  mov     rax, cs:__security_cookie
0x180055691  xor     rax, rsp
0x180055694  mov     [rbp+57h+var_10], rax
0x180055698  mov     ebx, 44h ; 'D'
0x18005569d  lea     rcx, [rbp+57h+pSid]; void *
0x1800556a1  mov     r8d, ebx; Size
0x1800556a4  xor     edx, edx; Val
0x1800556a6  call    memset_0
0x1800556ab  mov     r8d, ebx; Size
0x1800556ae  mov     [rbp+57h+cbSid], ebx
0x1800556b1  xor     edx, edx; Val
0x1800556b3  lea     rcx, [rbp+57h+SidToCheck]; void *
0x1800556b7  call    memset_0
0x1800556bc  lea     rcx, [rbp+57h+Binding]; Binding
0x1800556c0  mov     [rbp+57h+var_C4], ebx
0x1800556c3  mov     [rbp+57h+IsMember], 0
0x1800556ca  mov     [rbp+57h+var_CC], 0
0x1800556d1  mov     [rbp+57h+Binding], 0
0x1800556d9  call    cs:__imp_RpcServerInqBindingHandle
0x1800556df  test    eax, eax
0x1800556e1  jle     short loc_1800556ED
0x1800556e3  movzx   eax, ax
0x1800556e6  or      eax, 80070000h
0x1800556eb  test    eax, eax
0x1800556ed  jns     short loc_180055725
0x1800556ef  mov     bl, 1
0x1800556f1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1800556f7  jb      loc_180055808
0x1800556fd  mov     edx, 69h ; 'i'
0x180055702  mov     rcx, cs:WPP_GLOBAL_Control
0x180055709  lea     r8, WPP_1f0f67a3e2e738321c6948db893abc38_Traceguids
0x180055710  xor     r9d, r9d
0x180055713  mov     [rsp+100h+var_E0], eax
0x180055717  mov     rcx, [rcx+10h]
0x18005571b  call    WPP_SF_qD
0x180055720  jmp     loc_180055808
0x180055725  mov     rcx, [rbp+57h+Binding]; BindingHandle
0x180055729  call    cs:__imp_RpcImpersonateClient
0x18005572f  test    eax, eax
0x180055731  jle     short loc_18005573D
0x180055733  movzx   eax, ax
0x180055736  or      eax, 80070000h
0x18005573b  test    eax, eax
0x18005573d  jns     short loc_180055754
0x18005573f  mov     bl, 1
0x180055741  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180055747  jb      loc_180055808
0x18005574d  mov     edx, 6Ah ; 'j'
0x180055752  jmp     short loc_180055702
0x180055754  xor     edx, edx; DomainSid
0x180055756  lea     r9, [rbp+57h+cbSid]; cbSid
0x18005575a  lea     r8, [rbp+57h+pSid]; pSid
0x18005575e  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x180055761  call    cs:__imp_CreateWellKnownSid
0x180055767  mov     bl, 1
0x180055769  test    eax, eax
0x18005576b  jz      short loc_1800557BD
0x18005576d  xor     edx, edx; DomainSid
0x18005576f  lea     r9, [rbp+57h+var_C4]; cbSid
0x180055773  lea     r8, [rbp+57h+SidToCheck]; pSid
0x180055777  lea     ecx, [rdx+16h]; WellKnownSidType
0x18005577a  call    cs:__imp_CreateWellKnownSid
0x180055780  test    eax, eax
0x180055782  jz      short loc_1800557BD
0x180055784  lea     r8, [rbp+57h+IsMember]; IsMember
0x180055788  xor     ecx, ecx; TokenHandle
0x18005578a  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x18005578e  call    cs:__imp_CheckTokenMembership
0x180055794  test    eax, eax
0x180055796  jnz     short loc_18005579D
0x180055798  mov     [rbp+57h+IsMember], eax
0x18005579b  jmp     short loc_1800557A0
0x18005579d  mov     eax, [rbp+57h+IsMember]
0x1800557a0  test    eax, eax
0x1800557a2  jnz     short loc_1800557FE
0x1800557a4  lea     r8, [rbp+57h+var_CC]; IsMember
0x1800557a8  xor     ecx, ecx; TokenHandle
0x1800557aa  lea     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x1800557ae  call    cs:__imp_CheckTokenMembership
0x1800557b4  test    eax, eax
0x1800557b6  jnz     short loc_1800557FE
0x1800557b8  mov     [rbp+57h+var_CC], eax
0x1800557bb  jmp     short loc_1800557FE
0x1800557bd  call    cs:__imp_GetLastError
0x1800557c3  test    eax, eax
0x1800557c5  jle     short loc_1800557D1
0x1800557c7  movzx   eax, ax
0x1800557ca  or      eax, 80070000h
0x1800557cf  test    eax, eax
0x1800557d1  jns     short loc_1800557FE
0x1800557d3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1800557d9  jb      short loc_1800557FE
0x1800557db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800557e2  lea     r8, WPP_1f0f67a3e2e738321c6948db893abc38_Traceguids
0x1800557e9  mov     edx, 6Bh ; 'k'
0x1800557ee  mov     [rsp+100h+var_E0], eax
0x1800557f2  xor     r9d, r9d
0x1800557f5  mov     rcx, [rcx+10h]
0x1800557f9  call    WPP_SF_qD
0x1800557fe  mov     rcx, [rbp+57h+Binding]; BindingHandle
0x180055802  call    cs:__imp_RpcRevertToSelfEx
0x180055808  cmp     [rbp+57h+IsMember], 0
0x18005580c  jnz     short loc_180055816
0x18005580e  cmp     [rbp+57h+var_CC], 0
0x180055812  jnz     short loc_180055816
0x180055814  xor     bl, bl
0x180055816  mov     al, bl
0x180055818  mov     rcx, [rbp+57h+var_10]
0x18005581c  xor     rcx, rsp; StackCookie
0x18005581f  call    __security_check_cookie
0x180055824  mov     rbx, [rsp+100h+arg_0]
0x18005582c  add     rsp, 100h
0x180055833  pop     rbp
0x180055834  retn
```
