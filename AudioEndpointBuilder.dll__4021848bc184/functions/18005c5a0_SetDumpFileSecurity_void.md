# SetDumpFileSecurity(void *)

- ea: `0x18005c5a0`
- end: `0x18005c8b8`
- name: `?SetDumpFileSecurity@@YAKPEAX@Z`
- size: `792`
- prototype: `unsigned int __fastcall(HANDLE handle)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18005c8c0`

## callees

- `0x180001734`
- `0x18001f374`
- `0x18003e920`
- `0x18003f7a4`
- `0x18005c5a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c61d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c6a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c705`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c61d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c6a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c705`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18005c87a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18005c889`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18005c898`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18005c87a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18005c889`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18005c898`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18005c613`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18005c697`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18005c6fb`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18005c613`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18005c697`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18005c6fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c86a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c86a`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18005c7b2`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18005c7b2`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18005c803`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18005c803`

## string_xrefs

- `0x18005c635`: `SetDumpFileSecurity`
- `0x18005c82a`: `SetDumpFileSecurity`

## pseudocode

```c
__int64 __fastcall SetDumpFileSecurity(HANDLE handle)
{
  DWORD LastError; // ebx
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  char *v9; // rdx
  int v11; // [rsp+60h] [rbp-A0h] BYREF
  int v12; // [rsp+64h] [rbp-9Ch] BYREF
  const char *v13; // [rsp+68h] [rbp-98h] BYREF
  PACL NewAcl; // [rsp+70h] [rbp-90h] BYREF
  PSID v15; // [rsp+78h] [rbp-88h] BYREF
  PSID pSid; // [rsp+80h] [rbp-80h] BYREF
  PSID v17; // [rsp+88h] [rbp-78h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+90h] [rbp-70h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+A0h] [rbp-60h] BYREF
  int v20; // [rsp+D0h] [rbp-30h]
  __int64 v21; // [rsp+D4h] [rbp-2Ch]
  __int64 v22; // [rsp+E0h] [rbp-20h]
  __int64 v23; // [rsp+E8h] [rbp-18h]
  int v24; // [rsp+F0h] [rbp-10h]
  PSID v25; // [rsp+F8h] [rbp-8h]
  int v26; // [rsp+100h] [rbp+0h]
  __int64 v27; // [rsp+104h] [rbp+4h]
  __int64 v28; // [rsp+110h] [rbp+10h]
  __int64 v29; // [rsp+118h] [rbp+18h]
  int v30; // [rsp+120h] [rbp+20h]
  PSID v31; // [rsp+128h] [rbp+28h]

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  NewAcl = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v15 = 0;
  pSid = 0;
  v17 = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &v15) )
    {
      if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 6u, 0, 0, 0, 0, 0, 0, 0, &v17) )
      {
        memset_0(&pListOfExplicitEntries, 0, 0x90u);
        pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
        v25 = v15;
        pListOfExplicitEntries.grfAccessPermissions = 269287424;
        v20 = 269287424;
        v26 = 269287424;
        v31 = v17;
        *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
        pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
        *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
        pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
        v21 = 2;
        v22 = 0;
        v23 = 0;
        v24 = 5;
        v27 = 2;
        v28 = 0;
        v29 = 0;
        v30 = 5;
        LastError = SetEntriesInAclW(3u, &pListOfExplicitEntries, 0, &NewAcl);
        if ( LastError )
        {
          v6 = AudioEndpointBuilderTelemetryProvider::Provider();
          if ( *(_DWORD *)v6 <= 2u )
            goto LABEL_17;
          v11 = 216;
          v9 = byte_1800785AD;
        }
        else
        {
          LastError = SetSecurityInfo(handle, SE_FILE_OBJECT, 0x80000004, 0, 0, NewAcl, 0);
          if ( !LastError )
            goto LABEL_17;
          v6 = AudioEndpointBuilderTelemetryProvider::Provider();
          if ( *(_DWORD *)v6 <= 2u )
            goto LABEL_17;
          v11 = 236;
          v9 = byte_180078581;
        }
      }
      else
      {
        LastError = GetLastError();
        v6 = AudioEndpointBuilderTelemetryProvider::Provider();
        if ( *(_DWORD *)v6 <= 2u )
          goto LABEL_17;
        v11 = 157;
        v9 = byte_1800785D9;
      }
    }
    else
    {
      LastError = GetLastError();
      v6 = AudioEndpointBuilderTelemetryProvider::Provider();
      if ( *(_DWORD *)v6 <= 2u )
        goto LABEL_17;
      v11 = 139;
      v9 = byte_18007861D;
    }
    v13 = "SetDumpFileSecurity";
    v12 = LastError;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (int)v6,
      (int)v9,
      v7,
      v8,
      (const unsigned __int16 **)&v13,
      (__int64)&v11,
      (__int64)&v12);
    goto LABEL_17;
  }
  LastError = GetLastError();
  v3 = AudioEndpointBuilderTelemetryProvider::Provider();
  if ( *(_DWORD *)v3 > 2u )
  {
    v11 = LastError;
    v13 = "SetDumpFileSecurity";
    v12 = 121;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (int)v3,
      (int)byte_180078661,
      v4,
      v5,
      (const unsigned __int16 **)&v13,
      (__int64)&v12,
      (__int64)&v11);
  }
LABEL_17:
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( v15 )
    FreeSid(v15);
  if ( pSid )
    FreeSid(pSid);
  if ( v17 )
    FreeSid(v17);
  return LastError;
}

```

## disassembly

```asm
0x18005c5a0  push    rbp
0x18005c5a2  push    rbx
0x18005c5a3  push    rsi
0x18005c5a4  push    rdi
0x18005c5a5  lea     rbp, [rsp-48h]
0x18005c5aa  sub     rsp, 148h
0x18005c5b1  mov     rax, cs:__security_cookie
0x18005c5b8  xor     rax, rsp
0x18005c5bb  mov     [rbp+60h+var_30], rax
0x18005c5bf  xor     esi, esi
0x18005c5c1  mov     word ptr [rbp+60h+pIdentifierAuthority.Value+4], 500h
0x18005c5c7  lea     rax, [rbp+60h+var_E0]
0x18005c5cb  mov     [rsp+160h+NewAcl], rsi
0x18005c5d0  mov     [rsp+160h+pSid], rax; pSid
0x18005c5d5  mov     rdi, rcx
0x18005c5d8  mov     [rsp+160h+nSubAuthority7], esi; nSubAuthority7
0x18005c5dc  lea     rcx, [rbp+60h+pIdentifierAuthority]; pIdentifierAuthority
0x18005c5e0  mov     [rsp+160h+nSubAuthority6], esi; nSubAuthority6
0x18005c5e4  lea     r8d, [rsi+20h]; nSubAuthority0
0x18005c5e8  mov     [rsp+160h+nSubAuthority5], esi; nSubAuthority5
0x18005c5ec  lea     ebx, [rsi+5]
0x18005c5ef  mov     [rsp+160h+nSubAuthority4], esi; nSubAuthority4
0x18005c5f3  mov     r9d, 220h; nSubAuthority1
0x18005c5f9  mov     [rsp+160h+nSubAuthority3], esi; nSubAuthority3
0x18005c5fd  mov     dl, 2; nSubAuthorityCount
0x18005c5ff  mov     [rsp+160h+nSubAuthority2], esi; nSubAuthority2
0x18005c603  mov     dword ptr [rbp+60h+pIdentifierAuthority.Value], esi
0x18005c606  mov     [rsp+160h+var_E8], rsi
0x18005c60b  mov     [rbp+60h+var_E0], rsi
0x18005c60f  mov     [rbp+60h+var_D8], rsi
0x18005c613  call    cs:__imp_AllocateAndInitializeSid
0x18005c619  test    eax, eax
0x18005c61b  jnz     short loc_18005C668
0x18005c61d  call    cs:__imp_GetLastError
0x18005c623  mov     ebx, eax
0x18005c625  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18005c62a  mov     ecx, [rax]
0x18005c62c  cmp     ecx, 2
0x18005c62f  jbe     loc_18005C860
0x18005c635  lea     rcx, aSetdumpfilesec; "SetDumpFileSecurity"
0x18005c63c  mov     [rsp+160h+var_100], ebx
0x18005c640  mov     [rsp+160h+var_F8], rcx
0x18005c645  lea     rdx, byte_180078661
0x18005c64c  lea     rcx, [rsp+160h+var_100]
0x18005c651  mov     [rsp+160h+var_FC], 79h ; 'y'
0x18005c659  mov     qword ptr [rsp+160h+nSubAuthority4], rcx
0x18005c65e  lea     rcx, [rsp+160h+var_FC]
0x18005c663  jmp     loc_18005C849
0x18005c668  lea     rax, [rsp+160h+var_E8]
0x18005c66d  xor     r9d, r9d; nSubAuthority1
0x18005c670  mov     [rsp+160h+pSid], rax; pSid
0x18005c675  lea     rcx, [rbp+60h+pIdentifierAuthority]; pIdentifierAuthority
0x18005c679  mov     [rsp+160h+nSubAuthority7], esi; nSubAuthority7
0x18005c67d  mov     dl, 1; nSubAuthorityCount
0x18005c67f  mov     [rsp+160h+nSubAuthority6], esi; nSubAuthority6
0x18005c683  mov     [rsp+160h+nSubAuthority5], esi; nSubAuthority5
0x18005c687  lea     r8d, [r9+12h]; nSubAuthority0
0x18005c68b  mov     [rsp+160h+nSubAuthority4], esi; nSubAuthority4
0x18005c68f  mov     [rsp+160h+nSubAuthority3], esi; nSubAuthority3
0x18005c693  mov     [rsp+160h+nSubAuthority2], esi; nSubAuthority2
0x18005c697  call    cs:__imp_AllocateAndInitializeSid
0x18005c69d  test    eax, eax
0x18005c69f  jnz     short loc_18005C6CD
0x18005c6a1  call    cs:__imp_GetLastError
0x18005c6a7  mov     ebx, eax
0x18005c6a9  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18005c6ae  mov     ecx, [rax]
0x18005c6b0  cmp     ecx, 2
0x18005c6b3  jbe     loc_18005C860
0x18005c6b9  mov     [rsp+160h+var_100], 8Bh
0x18005c6c1  lea     rdx, byte_18007861D
0x18005c6c8  jmp     loc_18005C82A
0x18005c6cd  lea     rax, [rbp+60h+var_D8]
0x18005c6d1  xor     r9d, r9d; nSubAuthority1
0x18005c6d4  mov     [rsp+160h+pSid], rax; pSid
0x18005c6d9  lea     rcx, [rbp+60h+pIdentifierAuthority]; pIdentifierAuthority
0x18005c6dd  mov     [rsp+160h+nSubAuthority7], esi; nSubAuthority7
0x18005c6e1  mov     dl, 1; nSubAuthorityCount
0x18005c6e3  mov     [rsp+160h+nSubAuthority6], esi; nSubAuthority6
0x18005c6e7  mov     [rsp+160h+nSubAuthority5], esi; nSubAuthority5
0x18005c6eb  lea     r8d, [r9+6]; nSubAuthority0
0x18005c6ef  mov     [rsp+160h+nSubAuthority4], esi; nSubAuthority4
0x18005c6f3  mov     [rsp+160h+nSubAuthority3], esi; nSubAuthority3
0x18005c6f7  mov     [rsp+160h+nSubAuthority2], esi; nSubAuthority2
0x18005c6fb  call    cs:__imp_AllocateAndInitializeSid
0x18005c701  test    eax, eax
0x18005c703  jnz     short loc_18005C731
0x18005c705  call    cs:__imp_GetLastError
0x18005c70b  mov     ebx, eax
0x18005c70d  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18005c712  mov     ecx, [rax]
0x18005c714  cmp     ecx, 2
0x18005c717  jbe     loc_18005C860
0x18005c71d  mov     [rsp+160h+var_100], 9Dh
0x18005c725  lea     rdx, byte_1800785D9
0x18005c72c  jmp     loc_18005C82A
0x18005c731  xor     edx, edx; Val
0x18005c733  lea     rcx, [rbp+60h+pListOfExplicitEntries]; void *
0x18005c737  mov     r8d, 90h; Size
0x18005c73d  call    memset_0
0x18005c742  mov     rax, [rbp+60h+var_E0]
0x18005c746  lea     r9, [rsp+160h+NewAcl]; NewAcl
0x18005c74b  mov     ecx, 100D0000h
0x18005c750  mov     [rbp+60h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18005c754  mov     rax, [rsp+160h+var_E8]
0x18005c759  lea     rdx, [rbp+60h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18005c75d  xor     r8d, r8d; OldAcl
0x18005c760  mov     [rbp+60h+var_68], rax
0x18005c764  mov     rax, [rbp+60h+var_D8]
0x18005c768  mov     [rbp+60h+pListOfExplicitEntries.grfAccessPermissions], ecx
0x18005c76b  mov     [rbp+60h+var_90], ecx
0x18005c76e  mov     [rbp+60h+var_60], ecx
0x18005c771  lea     ecx, [r8+3]; cCountOfExplicitEntries
0x18005c775  mov     [rbp+60h+var_38], rax
0x18005c779  mov     qword ptr [rbp+60h+pListOfExplicitEntries.grfAccessMode], 2
0x18005c781  mov     [rbp+60h+pListOfExplicitEntries.Trustee.pMultipleTrustee], rsi
0x18005c785  mov     qword ptr [rbp+60h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], rsi
0x18005c789  mov     [rbp+60h+pListOfExplicitEntries.Trustee.TrusteeType], ebx
0x18005c78c  mov     [rbp+60h+var_8C], 2
0x18005c794  mov     [rbp+60h+var_80], rsi
0x18005c798  mov     [rbp+60h+var_78], rsi
0x18005c79c  mov     [rbp+60h+var_70], ebx
0x18005c79f  mov     [rbp+60h+var_5C], 2
0x18005c7a7  mov     [rbp+60h+var_50], rsi
0x18005c7ab  mov     [rbp+60h+var_48], rsi
0x18005c7af  mov     [rbp+60h+var_40], ebx
0x18005c7b2  call    cs:__imp_SetEntriesInAclW
0x18005c7b8  mov     ebx, eax
0x18005c7ba  test    eax, eax
0x18005c7bc  jz      short loc_18005C7DF
0x18005c7be  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18005c7c3  mov     ecx, [rax]
0x18005c7c5  cmp     ecx, 2
0x18005c7c8  jbe     loc_18005C860
0x18005c7ce  mov     [rsp+160h+var_100], 0D8h
0x18005c7d6  lea     rdx, byte_1800785AD
0x18005c7dd  jmp     short loc_18005C82A
0x18005c7df  mov     rax, [rsp+160h+NewAcl]
0x18005c7e4  xor     r9d, r9d; psidOwner
0x18005c7e7  mov     qword ptr [rsp+160h+nSubAuthority4], rsi; pSacl
0x18005c7ec  mov     r8d, 80000004h; SecurityInfo
0x18005c7f2  mov     qword ptr [rsp+160h+nSubAuthority3], rax; pDacl
0x18005c7f7  mov     rcx, rdi; handle
0x18005c7fa  mov     qword ptr [rsp+160h+nSubAuthority2], rsi; psidGroup
0x18005c7ff  lea     edx, [r9+1]; ObjectType
0x18005c803  call    cs:__imp_SetSecurityInfo
0x18005c809  mov     ebx, eax
0x18005c80b  test    eax, eax
0x18005c80d  jz      short loc_18005C860
0x18005c80f  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18005c814  mov     ecx, [rax]
0x18005c816  cmp     ecx, 2
0x18005c819  jbe     short loc_18005C860
0x18005c81b  mov     [rsp+160h+var_100], 0ECh
0x18005c823  lea     rdx, byte_180078581
0x18005c82a  lea     rcx, aSetdumpfilesec; "SetDumpFileSecurity"
0x18005c831  mov     [rsp+160h+var_F8], rcx
0x18005c836  lea     rcx, [rsp+160h+var_FC]
0x18005c83b  mov     qword ptr [rsp+160h+nSubAuthority4], rcx
0x18005c840  lea     rcx, [rsp+160h+var_100]
0x18005c845  mov     [rsp+160h+var_FC], ebx
0x18005c849  mov     qword ptr [rsp+160h+nSubAuthority3], rcx
0x18005c84e  lea     rcx, [rsp+160h+var_F8]
0x18005c853  mov     qword ptr [rsp+160h+nSubAuthority2], rcx
0x18005c858  mov     rcx, rax
0x18005c85b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005c860  mov     rcx, [rsp+160h+NewAcl]; hMem
0x18005c865  test    rcx, rcx
0x18005c868  jz      short loc_18005C870
0x18005c86a  call    cs:__imp_LocalFree
0x18005c870  mov     rcx, [rsp+160h+var_E8]; pSid
0x18005c875  test    rcx, rcx
0x18005c878  jz      short loc_18005C880
0x18005c87a  call    cs:__imp_FreeSid
0x18005c880  mov     rcx, [rbp+60h+var_E0]; pSid
0x18005c884  test    rcx, rcx
0x18005c887  jz      short loc_18005C88F
0x18005c889  call    cs:__imp_FreeSid
0x18005c88f  mov     rcx, [rbp+60h+var_D8]; pSid
0x18005c893  test    rcx, rcx
0x18005c896  jz      short loc_18005C89E
0x18005c898  call    cs:__imp_FreeSid
0x18005c89e  mov     eax, ebx
0x18005c8a0  mov     rcx, [rbp+60h+var_30]
0x18005c8a4  xor     rcx, rsp; StackCookie
0x18005c8a7  call    __security_check_cookie
0x18005c8ac  add     rsp, 148h
0x18005c8b3  pop     rdi
0x18005c8b4  pop     rsi
0x18005c8b5  pop     rbx
0x18005c8b6  pop     rbp
0x18005c8b7  retn
```
