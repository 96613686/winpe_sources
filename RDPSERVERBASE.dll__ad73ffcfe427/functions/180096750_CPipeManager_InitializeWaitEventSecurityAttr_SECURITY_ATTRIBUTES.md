# CPipeManager::InitializeWaitEventSecurityAttr(_SECURITY_ATTRIBUTES *)

- ea: `0x180096750`
- end: `0x180096c67`
- name: `?InitializeWaitEventSecurityAttr@CPipeManager@@IEAAJPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `1303`
- prototype: `int(CPipeManager *__hidden this, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18008fd70`

## callees

- `0x18000116c`
- `0x18007e9e0`
- `0x180096750`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800967e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800968ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009693e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800969c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096a53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096af7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096b81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800967e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800968ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009693e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800969c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096a53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096af7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096b81`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180096930`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180096adb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180096930`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180096adb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096c17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096c25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096c37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096c17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096c25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096c37`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800967d5`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800967d5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180096c08`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180096c08`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800969bb`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800969bb`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180096a49`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180096a49`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180096ace`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180096ace`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180096b77`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180096b77`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800968a4`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800968a4`

## string_xrefs

- `0x180096819`: `InitializeWaitEventSecurityAttr`
- `0x1800968e4`: `InitializeWaitEventSecurityAttr`
- `0x180096974`: `InitializeWaitEventSecurityAttr`
- `0x1800969fb`: `InitializeWaitEventSecurityAttr`
- `0x180096a89`: `InitializeWaitEventSecurityAttr`
- `0x180096ae1`: `InitializeWaitEventSecurityAttr`
- `0x180096807`: `Failed to allocate LOCAL SERVICE sid`
- `0x1800968d2`: `SetEntriesInAcl`
- `0x180096962`: `Failed to allocate security descriptor`
- `0x1800969e9`: `InitializeSecurityDescriptor`
- `0x180096a77`: `SetSecurityDescriptorDacl`

## pseudocode

```c
__int64 __fastcall CPipeManager::InitializeWaitEventSecurityAttr(CPipeManager *this, struct _SECURITY_ATTRIBUTES *a2)
{
  void *v3; // r14
  HLOCAL v4; // r15
  signed int v5; // eax
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  signed int v9; // ebx
  __int16 *v10; // rdx
  const char **v11; // rax
  signed int LastError; // eax
  HLOCAL v13; // rax
  signed int v14; // eax
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  int v18; // r8d
  int v19; // r9d
  unsigned int v20; // ecx
  signed int v21; // eax
  int *nSubAuthority3; // [rsp+28h] [rbp-81h]
  int *nSubAuthority5; // [rsp+38h] [rbp-71h]
  const char **nSubAuthority6; // [rsp+40h] [rbp-69h]
  int v26; // [rsp+60h] [rbp-49h] BYREF
  int v27; // [rsp+64h] [rbp-45h] BYREF
  const char *v28; // [rsp+68h] [rbp-41h] BYREF
  const char *v29; // [rsp+70h] [rbp-39h] BYREF
  const char *v30; // [rsp+78h] [rbp-31h] BYREF
  DWORD dwBufferLength; // [rsp+80h] [rbp-29h] BYREF
  PSID pSid; // [rsp+88h] [rbp-21h] BYREF
  PACL NewAcl; // [rsp+90h] [rbp-19h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+98h] [rbp-11h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+C8h] [rbp+1Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSid = 0;
  v3 = 0;
  NewAcl = 0;
  v4 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x13u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
    *(_QWORD *)&pListOfExplicitEntries.Trustee.TrusteeType = 1;
    pListOfExplicitEntries.grfAccessPermissions = 0x10000000;
    *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
    memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 20);
    if ( SetEntriesInAclW(1u, &pListOfExplicitEntries, 0, &NewAcl) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v27 = 2446;
        v28 = "SetEntriesInAcl";
        v30 = "InitializeWaitEventSecurityAttr";
        nSubAuthority6 = &v30;
        v10 = (__int16 *)&dword_18027ADE4;
        v26 = v9;
        nSubAuthority5 = &v27;
        nSubAuthority3 = &v26;
        v11 = &v28;
        goto LABEL_6;
      }
    }
    else
    {
      v13 = LocalAlloc(0x40u, 0x28u);
      v3 = v13;
      if ( v13 )
      {
        if ( InitializeSecurityDescriptor(v13, 1u) )
        {
          if ( SetSecurityDescriptorDacl(v3, 1, NewAcl, 0) )
          {
            dwBufferLength = GetSecurityDescriptorLength(v3);
            v4 = LocalAlloc(0x40u, dwBufferLength);
            if ( !v4 )
            {
              v17 = GetLastError();
              v20 = v17;
              if ( v17 > 0 )
                v20 = (unsigned __int16)v17 | 0x80070000;
              if ( (unsigned int)CallbackContext > 2 )
              {
                v30 = "InitializeWaitEventSecurityAttr";
                v28 = "Failed to allocate memory for self-relative SD";
                v27 = 2492;
                v29 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
                v26 = v20;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                  v20,
                  (unsigned int)&dword_18027ACCC,
                  v18,
                  v19,
                  (__int64)&v28,
                  (__int64)&v26,
                  (__int64)&v29,
                  (__int64)&v27,
                  (__int64)&v30);
              }
            }
            if ( MakeSelfRelativeSD(v3, v4, &dwBufferLength) )
            {
              a2->nLength = 24;
              a2->lpSecurityDescriptor = v4;
              a2->bInheritHandle = 0;
              v9 = 0;
            }
            else
            {
              v21 = GetLastError();
              v9 = v21;
              if ( v21 > 0 )
                v9 = (unsigned __int16)v21 | 0x80070000;
              if ( (unsigned int)CallbackContext > 2 )
              {
                v30 = "InitializeWaitEventSecurityAttr";
                v28 = "MakeSelfRelativeSD";
                v10 = &word_18027AC86;
                v27 = 2498;
                nSubAuthority6 = &v30;
                nSubAuthority5 = &v27;
                nSubAuthority3 = &v26;
                v11 = &v28;
                v26 = v9;
                goto LABEL_6;
              }
            }
          }
          else
          {
            v16 = GetLastError();
            v9 = v16;
            if ( v16 > 0 )
              v9 = (unsigned __int16)v16 | 0x80070000;
            if ( (unsigned int)CallbackContext > 2 )
            {
              v27 = 2479;
              v28 = "SetSecurityDescriptorDacl";
              v30 = "InitializeWaitEventSecurityAttr";
              nSubAuthority6 = &v30;
              v10 = word_18027AD12;
              v26 = v9;
              nSubAuthority5 = &v27;
              nSubAuthority3 = &v26;
              v11 = &v28;
              goto LABEL_6;
            }
          }
        }
        else
        {
          v15 = GetLastError();
          v9 = v15;
          if ( v15 > 0 )
            v9 = (unsigned __int16)v15 | 0x80070000;
          if ( (unsigned int)CallbackContext > 2 )
          {
            v27 = 2466;
            v28 = "InitializeSecurityDescriptor";
            v30 = "InitializeWaitEventSecurityAttr";
            nSubAuthority6 = &v30;
            v10 = (__int16 *)qword_18027AD58;
            v26 = v9;
            nSubAuthority5 = &v27;
            nSubAuthority3 = &v26;
            v11 = &v28;
            goto LABEL_6;
          }
        }
      }
      else
      {
        v14 = GetLastError();
        v9 = v14;
        if ( v14 > 0 )
          v9 = (unsigned __int16)v14 | 0x80070000;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v27 = 2458;
          v28 = "Failed to allocate security descriptor";
          v30 = "InitializeWaitEventSecurityAttr";
          nSubAuthority6 = &v30;
          v10 = &word_18027AD9E;
          v26 = v9;
          nSubAuthority5 = &v27;
          nSubAuthority3 = &v26;
          v11 = &v28;
          goto LABEL_6;
        }
      }
    }
  }
  else
  {
    v5 = GetLastError();
    v9 = v5;
    if ( v5 > 0 )
      v9 = (unsigned __int16)v5 | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v26 = 2422;
      v30 = "Failed to allocate LOCAL SERVICE sid";
      v28 = "InitializeWaitEventSecurityAttr";
      nSubAuthority6 = &v28;
      v10 = word_18027AE2A;
      v27 = v9;
      nSubAuthority5 = &v26;
      nSubAuthority3 = &v27;
      v11 = &v30;
LABEL_6:
      v29 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v6,
        (_DWORD)v10,
        v7,
        v8,
        (__int64)v11,
        (__int64)nSubAuthority3,
        (__int64)&v29,
        (__int64)nSubAuthority5,
        (__int64)nSubAuthority6);
    }
  }
  if ( pSid )
    FreeSid(pSid);
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( v3 )
    LocalFree(v3);
  if ( v9 < 0 && v4 )
    LocalFree(v4);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180096750  mov     [rsp-8+arg_0], rbx
0x180096755  mov     [rsp-8+arg_10], rsi
0x18009675a  push    rbp
0x18009675b  push    rdi
0x18009675c  push    r12
0x18009675e  push    r14
0x180096760  push    r15
0x180096762  lea     rbp, [rsp-37h]
0x180096767  sub     rsp, 0E0h
0x18009676e  mov     rax, cs:__security_cookie
0x180096775  xor     rax, rsp
0x180096778  mov     [rbp+57h+var_30], rax
0x18009677c  xor     r12d, r12d
0x18009677f  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180096785  lea     rax, [rbp+57h+var_78]
0x180096789  mov     [rbp+57h+var_78], r12
0x18009678d  mov     [rsp+100h+pSid], rax; pSid
0x180096792  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180096796  mov     [rsp+100h+nSubAuthority7], r12d; nSubAuthority7
0x18009679b  mov     rbx, rdx
0x18009679e  mov     [rsp+100h+nSubAuthority6], r12d; nSubAuthority6
0x1800967a3  lea     edi, [r12+1]
0x1800967a8  mov     [rsp+100h+nSubAuthority5], r12d; nSubAuthority5
0x1800967ad  lea     r8d, [r12+13h]; nSubAuthority0
0x1800967b2  mov     [rsp+100h+nSubAuthority4], r12d; nSubAuthority4
0x1800967b7  mov     dl, dil; nSubAuthorityCount
0x1800967ba  mov     [rsp+100h+nSubAuthority3], r12d; nSubAuthority3
0x1800967bf  xor     r9d, r9d; nSubAuthority1
0x1800967c2  mov     [rsp+100h+nSubAuthority2], r12d; nSubAuthority2
0x1800967c7  mov     r14d, r12d
0x1800967ca  mov     [rbp+57h+NewAcl], r12
0x1800967ce  mov     r15d, r12d
0x1800967d1  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r12d
0x1800967d5  call    cs:__imp_AllocateAndInitializeSid
0x1800967db  test    eax, eax
0x1800967dd  jnz     loc_180096870
0x1800967e3  call    cs:__imp_GetLastError
0x1800967e9  mov     ebx, eax
0x1800967eb  test    eax, eax
0x1800967ed  jle     short loc_1800967F8
0x1800967ef  movzx   ebx, ax
0x1800967f2  or      ebx, 80070000h
0x1800967f8  mov     eax, cs:CallbackContext
0x1800967fe  cmp     eax, 2
0x180096801  jbe     loc_180096BFF
0x180096807  lea     rax, aFailedToAlloca_11; "Failed to allocate LOCAL SERVICE sid"
0x18009680e  mov     [rbp+57h+var_A0], 976h
0x180096815  mov     [rbp+57h+var_88], rax
0x180096819  lea     rdi, aInitializewait; "InitializeWaitEventSecurityAttr"
0x180096820  lea     rax, [rbp+57h+var_98]
0x180096824  mov     [rbp+57h+var_98], rdi
0x180096828  mov     qword ptr [rsp+100h+nSubAuthority6], rax
0x18009682d  lea     rdx, word_18027AE2A
0x180096834  lea     rax, [rbp+57h+var_A0]
0x180096838  mov     [rbp+57h+var_9C], ebx
0x18009683b  mov     qword ptr [rsp+100h+nSubAuthority5], rax
0x180096840  lea     rax, [rbp+57h+var_90]
0x180096844  mov     qword ptr [rsp+100h+nSubAuthority4], rax
0x180096849  lea     rax, [rbp+57h+var_9C]
0x18009684d  mov     qword ptr [rsp+100h+nSubAuthority3], rax
0x180096852  lea     rax, [rbp+57h+var_88]
0x180096856  lea     rsi, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18009685d  mov     qword ptr [rsp+100h+nSubAuthority2], rax
0x180096862  mov     [rbp+57h+var_90], rsi
0x180096866  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18009686b  jmp     loc_180096BFF
0x180096870  mov     rax, [rbp+57h+var_78]
0x180096874  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x180096878  xorps   xmm0, xmm0
0x18009687b  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18009687f  xor     r8d, r8d; OldAcl
0x180096882  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], rdi
0x180096886  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18009688a  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x180096891  mov     ecx, edi; cCountOfExplicitEntries
0x180096893  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], 2
0x18009689b  movdqu  xmmword ptr [rbp+57h+pListOfExplicitEntries+0Ch], xmm0
0x1800968a0  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], r12d
0x1800968a4  call    cs:__imp_SetEntriesInAclW
0x1800968aa  test    eax, eax
0x1800968ac  jz      short loc_180096926
0x1800968ae  call    cs:__imp_GetLastError
0x1800968b4  mov     ebx, eax
0x1800968b6  test    eax, eax
0x1800968b8  jle     short loc_1800968C3
0x1800968ba  movzx   ebx, ax
0x1800968bd  or      ebx, 80070000h
0x1800968c3  mov     eax, cs:CallbackContext
0x1800968c9  cmp     eax, 2
0x1800968cc  jbe     loc_180096BFF
0x1800968d2  lea     rax, aSetentriesinac_0; "SetEntriesInAcl"
0x1800968d9  mov     [rbp+57h+var_9C], 98Eh
0x1800968e0  mov     [rbp+57h+var_98], rax
0x1800968e4  lea     rdi, aInitializewait; "InitializeWaitEventSecurityAttr"
0x1800968eb  lea     rax, [rbp+57h+var_88]
0x1800968ef  mov     [rbp+57h+var_88], rdi
0x1800968f3  mov     qword ptr [rsp+100h+nSubAuthority6], rax
0x1800968f8  lea     rdx, dword_18027ADE4
0x1800968ff  lea     rax, [rbp+57h+var_9C]
0x180096903  mov     [rbp+57h+var_A0], ebx
0x180096906  mov     qword ptr [rsp+100h+nSubAuthority5], rax
0x18009690b  lea     rax, [rbp+57h+var_90]
0x18009690f  mov     qword ptr [rsp+100h+nSubAuthority4], rax
0x180096914  lea     rax, [rbp+57h+var_A0]
0x180096918  mov     qword ptr [rsp+100h+nSubAuthority3], rax
0x18009691d  lea     rax, [rbp+57h+var_98]
0x180096921  jmp     loc_180096856
0x180096926  mov     edx, 28h ; '('; uBytes
0x18009692b  lea     esi, [rdx+18h]
0x18009692e  mov     ecx, esi; uFlags
0x180096930  call    cs:__imp_LocalAlloc
0x180096936  mov     r14, rax
0x180096939  test    rax, rax
0x18009693c  jnz     short loc_1800969B6
0x18009693e  call    cs:__imp_GetLastError
0x180096944  mov     ebx, eax
0x180096946  test    eax, eax
0x180096948  jle     short loc_180096953
0x18009694a  movzx   ebx, ax
0x18009694d  or      ebx, 80070000h
0x180096953  mov     eax, cs:CallbackContext
0x180096959  cmp     eax, 2
0x18009695c  jbe     loc_180096BFF
0x180096962  lea     rax, aFailedToAlloca_4; "Failed to allocate security descriptor"
0x180096969  mov     [rbp+57h+var_9C], 99Ah
0x180096970  mov     [rbp+57h+var_98], rax
0x180096974  lea     rdi, aInitializewait; "InitializeWaitEventSecurityAttr"
0x18009697b  lea     rax, [rbp+57h+var_88]
0x18009697f  mov     [rbp+57h+var_88], rdi
0x180096983  mov     qword ptr [rsp+100h+nSubAuthority6], rax
0x180096988  lea     rdx, word_18027AD9E
0x18009698f  lea     rax, [rbp+57h+var_9C]
0x180096993  mov     [rbp+57h+var_A0], ebx
0x180096996  mov     qword ptr [rsp+100h+nSubAuthority5], rax
0x18009699b  lea     rax, [rbp+57h+var_90]
0x18009699f  mov     qword ptr [rsp+100h+nSubAuthority4], rax
0x1800969a4  lea     rax, [rbp+57h+var_A0]
0x1800969a8  mov     qword ptr [rsp+100h+nSubAuthority3], rax
0x1800969ad  lea     rax, [rbp+57h+var_98]
0x1800969b1  jmp     loc_180096856
0x1800969b6  mov     edx, edi; dwRevision
0x1800969b8  mov     rcx, r14; pSecurityDescriptor
0x1800969bb  call    cs:__imp_InitializeSecurityDescriptor
0x1800969c1  test    eax, eax
0x1800969c3  jnz     short loc_180096A3D
0x1800969c5  call    cs:__imp_GetLastError
0x1800969cb  mov     ebx, eax
0x1800969cd  test    eax, eax
0x1800969cf  jle     short loc_1800969DA
0x1800969d1  movzx   ebx, ax
0x1800969d4  or      ebx, 80070000h
0x1800969da  mov     eax, cs:CallbackContext
0x1800969e0  cmp     eax, 2
0x1800969e3  jbe     loc_180096BFF
0x1800969e9  lea     rax, aInitializesecu; "InitializeSecurityDescriptor"
0x1800969f0  mov     [rbp+57h+var_9C], 9A2h
0x1800969f7  mov     [rbp+57h+var_98], rax
0x1800969fb  lea     rdi, aInitializewait; "InitializeWaitEventSecurityAttr"
0x180096a02  lea     rax, [rbp+57h+var_88]
0x180096a06  mov     [rbp+57h+var_88], rdi
0x180096a0a  mov     qword ptr [rsp+100h+nSubAuthority6], rax
0x180096a0f  lea     rdx, qword_18027AD58
0x180096a16  lea     rax, [rbp+57h+var_9C]
0x180096a1a  mov     [rbp+57h+var_A0], ebx
0x180096a1d  mov     qword ptr [rsp+100h+nSubAuthority5], rax
0x180096a22  lea     rax, [rbp+57h+var_90]
0x180096a26  mov     qword ptr [rsp+100h+nSubAuthority4], rax
0x180096a2b  lea     rax, [rbp+57h+var_A0]
0x180096a2f  mov     qword ptr [rsp+100h+nSubAuthority3], rax
0x180096a34  lea     rax, [rbp+57h+var_98]
0x180096a38  jmp     loc_180096856
0x180096a3d  mov     r8, [rbp+57h+NewAcl]; pDacl
0x180096a41  xor     r9d, r9d; bDaclDefaulted
0x180096a44  mov     edx, edi; bDaclPresent
0x180096a46  mov     rcx, r14; pSecurityDescriptor
0x180096a49  call    cs:__imp_SetSecurityDescriptorDacl
0x180096a4f  test    eax, eax
0x180096a51  jnz     short loc_180096ACB
0x180096a53  call    cs:__imp_GetLastError
0x180096a59  mov     ebx, eax
0x180096a5b  test    eax, eax
0x180096a5d  jle     short loc_180096A68
0x180096a5f  movzx   ebx, ax
0x180096a62  or      ebx, 80070000h
0x180096a68  mov     eax, cs:CallbackContext
0x180096a6e  cmp     eax, 2
0x180096a71  jbe     loc_180096BFF
0x180096a77  lea     rax, aSetsecuritydes; "SetSecurityDescriptorDacl"
0x180096a7e  mov     [rbp+57h+var_9C], 9AFh
0x180096a85  mov     [rbp+57h+var_98], rax
0x180096a89  lea     rdi, aInitializewait; "InitializeWaitEventSecurityAttr"
0x180096a90  lea     rax, [rbp+57h+var_88]
0x180096a94  mov     [rbp+57h+var_88], rdi
0x180096a98  mov     qword ptr [rsp+100h+nSubAuthority6], rax
0x180096a9d  lea     rdx, word_18027AD12
0x180096aa4  lea     rax, [rbp+57h+var_9C]
0x180096aa8  mov     [rbp+57h+var_A0], ebx
0x180096aab  mov     qword ptr [rsp+100h+nSubAuthority5], rax
0x180096ab0  lea     rax, [rbp+57h+var_90]
0x180096ab4  mov     qword ptr [rsp+100h+nSubAuthority4], rax
0x180096ab9  lea     rax, [rbp+57h+var_A0]
0x180096abd  mov     qword ptr [rsp+100h+nSubAuthority3], rax
0x180096ac2  lea     rax, [rbp+57h+var_98]
0x180096ac6  jmp     loc_180096856
0x180096acb  mov     rcx, r14; pSecurityDescriptor
0x180096ace  call    cs:__imp_GetSecurityDescriptorLength
0x180096ad4  mov     edx, eax; uBytes
0x180096ad6  mov     ecx, esi; uFlags
0x180096ad8  mov     [rbp+57h+dwBufferLength], edx
0x180096adb  call    cs:__imp_LocalAlloc
0x180096ae1  lea     rdi, aInitializewait; "InitializeWaitEventSecurityAttr"
0x180096ae8  mov     r15, rax
0x180096aeb  lea     rsi, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x180096af2  test    rax, rax
0x180096af5  jnz     short loc_180096B6D
0x180096af7  call    cs:__imp_GetLastError
0x180096afd  mov     ecx, eax
0x180096aff  test    eax, eax
0x180096b01  jle     short loc_180096B0C
0x180096b03  movzx   ecx, ax
0x180096b06  or      ecx, 80070000h
0x180096b0c  mov     eax, cs:CallbackContext
0x180096b12  cmp     eax, 2
0x180096b15  jbe     short loc_180096B6D
0x180096b17  lea     rax, aFailedToAlloca_1; "Failed to allocate memory for self-rela"...
0x180096b1e  mov     [rbp+57h+var_88], rdi
0x180096b22  mov     [rbp+57h+var_98], rax
0x180096b26  lea     rdx, dword_18027ACCC
0x180096b2d  lea     rax, [rbp+57h+var_88]
0x180096b31  mov     [rbp+57h+var_9C], 9BCh
0x180096b38  mov     qword ptr [rsp+100h+nSubAuthority6], rax
0x180096b3d  lea     rax, [rbp+57h+var_9C]
0x180096b41  mov     qword ptr [rsp+100h+nSubAuthority5], rax
0x180096b46  lea     rax, [rbp+57h+var_90]
0x180096b4a  mov     qword ptr [rsp+100h+nSubAuthority4], rax
0x180096b4f  lea     rax, [rbp+57h+var_A0]
0x180096b53  mov     qword ptr [rsp+100h+nSubAuthority3], rax
0x180096b58  lea     rax, [rbp+57h+var_98]
0x180096b5c  mov     qword ptr [rsp+100h+nSubAuthority2], rax
0x180096b61  mov     [rbp+57h+var_90], rsi
0x180096b65  mov     [rbp+57h+var_A0], ecx
0x180096b68  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180096b6d  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x180096b71  mov     rdx, r15; pSelfRelativeSecurityDescriptor
0x180096b74  mov     rcx, r14; pAbsoluteSecurityDescriptor
0x180096b77  call    cs:__imp_MakeSelfRelativeSD
0x180096b7d  test    eax, eax
0x180096b7f  jnz     short loc_180096BEE
0x180096b81  call    cs:__imp_GetLastError
0x180096b87  mov     ebx, eax
0x180096b89  test    eax, eax
0x180096b8b  jle     short loc_180096B96
0x180096b8d  movzx   ebx, ax
0x180096b90  or      ebx, 80070000h
0x180096b96  mov     eax, cs:CallbackContext
0x180096b9c  cmp     eax, 2
0x180096b9f  jbe     short loc_180096BFF
0x180096ba1  lea     rax, aMakeselfrelati; "MakeSelfRelativeSD"
0x180096ba8  mov     [rbp+57h+var_88], rdi
0x180096bac  mov     [rbp+57h+var_98], rax
0x180096bb0  lea     rdx, word_18027AC86
0x180096bb7  lea     rax, [rbp+57h+var_88]
0x180096bbb  mov     [rbp+57h+var_9C], 9C2h
0x180096bc2  mov     qword ptr [rsp+100h+nSubAuthority6], rax
0x180096bc7  lea     rax, [rbp+57h+var_9C]
0x180096bcb  mov     qword ptr [rsp+100h+nSubAuthority5], rax
0x180096bd0  lea     rax, [rbp+57h+var_90]
0x180096bd4  mov     qword ptr [rsp+100h+nSubAuthority4], rax
0x180096bd9  lea     rax, [rbp+57h+var_A0]
0x180096bdd  mov     qword ptr [rsp+100h+nSubAuthority3], rax
0x180096be2  lea     rax, [rbp+57h+var_98]
0x180096be6  mov     [rbp+57h+var_A0], ebx
0x180096be9  jmp     loc_18009685D
0x180096bee  mov     dword ptr [rbx], 18h
0x180096bf4  mov     [rbx+8], r15
0x180096bf8  mov     [rbx+10h], r12d
0x180096bfc  mov     ebx, r12d
0x180096bff  mov     rcx, [rbp+57h+var_78]; pSid
0x180096c03  test    rcx, rcx
0x180096c06  jz      short loc_180096C0E
0x180096c08  call    cs:__imp_FreeSid
0x180096c0e  mov     rcx, [rbp+57h+NewAcl]; hMem
0x180096c12  test    rcx, rcx
0x180096c15  jz      short loc_180096C1D
0x180096c17  call    cs:__imp_LocalFree
0x180096c1d  test    r14, r14
0x180096c20  jz      short loc_180096C2B
0x180096c22  mov     rcx, r14; hMem
0x180096c25  call    cs:__imp_LocalFree
0x180096c2b  test    ebx, ebx
0x180096c2d  jns     short loc_180096C3D
0x180096c2f  test    r15, r15
0x180096c32  jz      short loc_180096C3D
0x180096c34  mov     rcx, r15; hMem
0x180096c37  call    cs:__imp_LocalFree
0x180096c3d  mov     eax, ebx
0x180096c3f  mov     rcx, [rbp+57h+var_30]
0x180096c43  xor     rcx, rsp; StackCookie
0x180096c46  call    __security_check_cookie
0x180096c4b  lea     r11, [rsp+100h+var_20]
  ... truncated ...
```
