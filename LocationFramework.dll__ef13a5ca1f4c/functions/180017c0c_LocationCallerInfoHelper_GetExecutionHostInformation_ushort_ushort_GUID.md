# LocationCallerInfoHelper::GetExecutionHostInformation(ushort * *,ushort * *,_GUID *)

- ea: `0x180017c0c`
- end: `0x180018083`
- name: `?GetExecutionHostInformation@LocationCallerInfoHelper@@SAJPEAPEAG0PEAU_GUID@@@Z`
- size: `1143`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned __int16 **, struct _GUID *)`
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012b2c`
- `0x18005881c`
- `0x1800690f0`

## callees

- `0x180017be4`
- `0x180017c0c`
- `0x18001808c`
- `0x180018154`
- `0x180018174`
- `0x180018228`
- `0x18001e170`
- `0x18001ecbc`
- `0x18001efe0`
- `0x18001f09c`
- `0x18001f334`
- `0x18005affc`
- `0x18008f888`
- `0x1800a98c0`
- `0x1800aa5ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d7a`
- `OLEAUT32!__imp_SysFreeString` at `0x180017e50`
- `OLEAUT32!__imp_SysFreeString` at `0x180017e5c`
- `OLEAUT32!__imp_SysFreeString` at `0x180017eff`
- `OLEAUT32!__imp_SysFreeString` at `0x180017f08`
- `OLEAUT32!__imp_SysFreeString` at `0x180017f36`
- `OLEAUT32!__imp_SysFreeString` at `0x180017f3f`
- `OLEAUT32!__imp_SysFreeString` at `0x180017fca`
- `OLEAUT32!__imp_SysFreeString` at `0x180017e50`
- `OLEAUT32!__imp_SysFreeString` at `0x180017e5c`
- `OLEAUT32!__imp_SysFreeString` at `0x180017eff`
- `OLEAUT32!__imp_SysFreeString` at `0x180017f08`
- `OLEAUT32!__imp_SysFreeString` at `0x180017f36`
- `OLEAUT32!__imp_SysFreeString` at `0x180017f3f`
- `OLEAUT32!__imp_SysFreeString` at `0x180017fca`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017d65`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017d65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017e0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017e40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017eb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017ef2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017f29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017fa1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017fbd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017e0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017e40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017eb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017ef2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017f29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017fa1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017fbd`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180017c7f`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180017c7f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180017e34`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180017ea2`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180017ee6`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180017f95`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180017fec`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180018012`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180017e34`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180017ea2`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180017ee6`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180017f95`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180017fec`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180018012`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180017dd4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180017f58`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180017dd4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180017f58`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall LocationCallerInfoHelper::GetExecutionHostInformation(
        unsigned __int16 **a1,
        unsigned __int16 **a2,
        struct _GUID *a3)
{
  HRESULT v5; // eax
  signed int AppContainerSid; // edi
  bool v7; // si
  bool v8; // bl
  const unsigned __int16 *v9; // rax
  int v10; // eax
  const unsigned __int16 *v11; // rcx
  signed int LastError; // eax
  int v13; // r8d
  const unsigned __int16 *v14; // rcx
  const unsigned __int16 *v15; // rdx
  OLECHAR *v16; // rcx
  OLECHAR *v17; // rcx
  wil::details *v19; // rcx
  BSTR bstrString; // [rsp+30h] [rbp-D0h] BYREF
  BSTR v21; // [rsp+38h] [rbp-C8h] BYREF
  bool v22; // [rsp+40h] [rbp-C0h]
  HRESULT v23; // [rsp+44h] [rbp-BCh]
  void *TokenInformation; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  DWORD ReturnLength[2]; // [rsp+58h] [rbp-A8h] BYREF
  void **TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE TokenHandle_8[2]; // [rsp+68h] [rbp-98h]
  __int64 v29; // [rsp+78h] [rbp-88h]
  _BYTE v30[128]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v31[8]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE Sid[120]; // [rsp+108h] [rbp+8h] BYREF

  v21 = 0;
  bstrString = 0;
  hMem = 0;
  if ( !a1 || !a2 || !a3 )
  {
    LocalFree(0);
    hMem = 0;
    SysFreeString(0);
    SysFreeString(0);
    return 2147942487LL;
  }
  *a3 = GUID_NULL;
  v5 = CoImpersonateClient();
  AppContainerSid = v5;
  v23 = v5;
  v7 = 1;
  v8 = v5 >= 0;
  v22 = v5 >= 0;
  if ( (int)(v5 + 0x80000000) >= 0 && v5 != -2147417833 )
  {
    if ( v5 >= 0 )
      CoRevertToSelf();
LABEL_41:
    LocalFree(hMem);
    hMem = 0;
    SysFreeString(0);
    v17 = 0;
    goto LABEL_24;
  }
  TokenHandle = &ATL::CAccessToken::`vftable';
  *(_OWORD *)TokenHandle_8 = 0;
  v29 = 0;
  if ( !ATL::CAccessToken::GetEffectiveToken((ATL::CAccessToken *)&TokenHandle, 8u) )
  {
    TokenHandle = &ATL::CAccessToken::`vftable';
    ATL::CAccessToken::Clear((ATL::CAccessToken *)&TokenHandle);
    if ( v8 )
      CoRevertToSelf();
    AppContainerSid = -2147024891;
    goto LABEL_41;
  }
  memset_0(v30, 0, 0x78u);
  ATL::CSid::CSid((ATL::CSid *)v30);
  if ( !ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>((__int64)&TokenHandle, (__int64)v30) )
  {
    ATL::CSid::~CSid((ATL::CSid *)v30);
    TokenHandle = &ATL::CAccessToken::`vftable';
    ATL::CAccessToken::Clear((ATL::CAccessToken *)&TokenHandle);
    if ( v8 )
      CoRevertToSelf();
    AppContainerSid = -2147418113;
    goto LABEL_41;
  }
  v9 = ATL::CSid::Sid((ATL::CSid *)v30);
  v10 = ocslen(v9);
  AppContainerSid = ATL::CComBSTR::Append((ATL::CComBSTR *)&v21, v11, v10);
  if ( AppContainerSid < 0 )
    goto LABEL_37;
  LODWORD(TokenInformation) = 0;
  ReturnLength[0] = 0;
  if ( GetTokenInformation(TokenHandle_8[0], TokenIsAppContainer, &TokenInformation, 4u, ReturnLength) )
  {
    v7 = (_DWORD)TokenInformation != 0;
  }
  else
  {
    LastError = GetLastError();
    AppContainerSid = LastError;
    if ( LastError > 0 )
      AppContainerSid = (unsigned __int16)LastError | 0x80070000;
    if ( AppContainerSid < 0 )
      goto LABEL_37;
  }
  if ( v7 )
  {
    memset_0(v31, 0, 0x78u);
    ATL::CSid::CSid((ATL::CSid *)v31);
    AppContainerSid = LocationCallerInfoHelper::GetAppContainerSid(
                        (const struct ATL::CAccessToken *)&TokenHandle,
                        (struct ATL::CSid *)v31);
    if ( AppContainerSid >= 0 )
    {
      if ( ConvertSidToStringSidW(Sid, (LPWSTR *)&hMem) )
      {
        AppContainerSid = ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, (const unsigned __int16 *)hMem);
        if ( AppContainerSid < 0 )
        {
          ATL::CSid::~CSid((ATL::CSid *)v31);
          goto LABEL_20;
        }
        ATL::CSid::~CSid((ATL::CSid *)v31);
        goto LABEL_29;
      }
      AppContainerSid = wil::details::GetLastErrorFailHr(v19);
    }
    ATL::CSid::~CSid((ATL::CSid *)v31);
LABEL_37:
    ATL::CSid::~CSid((ATL::CSid *)v30);
    TokenHandle = &ATL::CAccessToken::`vftable';
    ATL::CAccessToken::Clear((ATL::CAccessToken *)&TokenHandle);
    if ( v8 )
      CoRevertToSelf();
    LocalFree(hMem);
    hMem = 0;
    v16 = 0;
    goto LABEL_23;
  }
  TokenInformation = 0;
  *(_QWORD *)ReturnLength = 0;
  if ( (int)LocationCallerInfoHelper::GetPackageSidFromTokenUsingPFN(TokenHandle_8[0], &TokenInformation) < 0
    || !TokenInformation )
  {
    v13 = 14;
    v15 = L"NonPackagedApp";
LABEL_18:
    AppContainerSid = ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, v15, v13);
    if ( AppContainerSid < 0 )
    {
      LocalFree(*(HLOCAL *)ReturnLength);
      *(_QWORD *)ReturnLength = 0;
LABEL_20:
      ATL::CSid::~CSid((ATL::CSid *)v30);
      TokenHandle = &ATL::CAccessToken::`vftable';
      ATL::CAccessToken::Clear((ATL::CAccessToken *)&TokenHandle);
      if ( v8 )
        CoRevertToSelf();
      LocalFree(hMem);
      hMem = 0;
      v16 = bstrString;
LABEL_23:
      SysFreeString(v16);
      v17 = v21;
LABEL_24:
      SysFreeString(v17);
      return (unsigned int)AppContainerSid;
    }
    goto LABEL_28;
  }
  if ( ConvertSidToStringSidW(TokenInformation, (LPWSTR *)ReturnLength) )
  {
    v13 = ocslen(*(const unsigned __int16 **)ReturnLength);
    v15 = v14;
    goto LABEL_18;
  }
LABEL_28:
  LocalFree(*(HLOCAL *)ReturnLength);
LABEL_29:
  *a1 = v21;
  *a2 = bstrString;
  ATL::CSid::~CSid((ATL::CSid *)v30);
  TokenHandle = &ATL::CAccessToken::`vftable';
  ATL::CAccessToken::Clear((ATL::CAccessToken *)&TokenHandle);
  if ( v8 )
    CoRevertToSelf();
  LocalFree(hMem);
  hMem = 0;
  SysFreeString(0);
  SysFreeString(0);
  return 0;
}

```

## disassembly

```asm
0x180017c0c  mov     [rsp-8+arg_18], rbx
0x180017c11  push    rbp
0x180017c12  push    rsi
0x180017c13  push    rdi
0x180017c14  push    r12
0x180017c16  push    r13
0x180017c18  push    r14
0x180017c1a  push    r15
0x180017c1c  lea     rbp, [rsp-90h]
0x180017c24  sub     rsp, 190h
0x180017c2b  mov     rax, cs:__security_cookie
0x180017c32  xor     rax, rsp
0x180017c35  mov     [rbp+0C0h+var_40], rax
0x180017c3c  mov     r14, rdx
0x180017c3f  mov     r15, rcx
0x180017c42  xor     r12d, r12d
0x180017c45  mov     [rsp+1C0h+var_188], r12
0x180017c4a  mov     [rsp+1C0h+bstrString], r12
0x180017c4f  mov     [rsp+1C0h+hMem], r12
0x180017c54  test    rcx, rcx
0x180017c57  jz      loc_180017F27
0x180017c5d  test    rdx, rdx
0x180017c60  jz      loc_180017F27
0x180017c66  test    r8, r8
0x180017c69  jz      loc_180017F27
0x180017c6f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180017c76  movdqu  xmmword ptr [r8], xmm0
0x180017c7b  movzx   ebx, r12b
0x180017c7f  call    cs:__imp_CoImpersonateClient
0x180017c85  mov     edi, eax
0x180017c87  mov     [rsp+1C0h+var_17C], eax
0x180017c8b  lea     esi, [r12+1]
0x180017c90  test    eax, eax
0x180017c92  cmovns  ebx, esi
0x180017c95  mov     [rsp+1C0h+var_180], bl
0x180017c99  mov     ecx, 80000000h
0x180017c9e  add     eax, ecx
0x180017ca0  test    ecx, eax
0x180017ca2  jz      loc_180017E8E
0x180017ca8  xorps   xmm0, xmm0
0x180017cab  movups  xmmword ptr [rsp+1C0h+TokenHandle], xmm0
0x180017cb0  movups  [rsp+1C0h+var_150], xmm0
0x180017cb5  lea     r13, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x180017cbc  mov     [rsp+1C0h+TokenHandle], r13
0x180017cc1  movdqu  xmmword ptr [rsp+1C0h+TokenHandle+8], xmm0
0x180017cc7  mov     qword ptr [rsp+1C0h+var_150+8], r12
0x180017ccc  mov     edx, 8; unsigned int
0x180017cd1  lea     rcx, [rsp+1C0h+TokenHandle]; this
0x180017cd6  call    ?GetEffectiveToken@CAccessToken@ATL@@QEAA_NK@Z; ATL::CAccessToken::GetEffectiveToken(ulong)
0x180017cdb  test    al, al
0x180017cdd  jz      loc_180017FD8
0x180017ce3  xor     edx, edx; Val
0x180017ce5  lea     r8d, [rdx+78h]; Size
0x180017ce9  lea     rcx, [rbp+0C0h+var_140]; void *
0x180017ced  call    memset_0
0x180017cf2  lea     rcx, [rbp+0C0h+var_140]; this
0x180017cf6  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x180017cfb  nop
0x180017cfc  lea     rdx, [rbp+0C0h+var_140]
0x180017d00  lea     rcx, [rsp+1C0h+TokenHandle]
0x180017d05  call    ??$GetInfoConvert@VCSid@ATL@@U_TOKEN_USER@@@CAccessToken@ATL@@IEBA_NPEAVCSid@1@W4_TOKEN_INFORMATION_CLASS@@PEAU_TOKEN_USER@@@Z; ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>(ATL::CSid *,_TOKEN_INFORMATION_CLASS,_TOKEN_USER *)
0x180017d0a  test    al, al
0x180017d0c  jz      loc_180017FF4
0x180017d12  lea     rcx, [rbp+0C0h+var_140]; this
0x180017d16  call    ?Sid@CSid@ATL@@QEBAPEBGXZ; ATL::CSid::Sid(void)
0x180017d1b  mov     rcx, rax; unsigned __int16 *
0x180017d1e  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x180017d23  mov     r8d, eax; int
0x180017d26  mov     rdx, rcx; unsigned __int16 *
0x180017d29  lea     rcx, [rsp+1C0h+var_188]; this
0x180017d2e  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180017d33  mov     edi, eax
0x180017d35  test    eax, eax
0x180017d37  js      loc_180017F77
0x180017d3d  mov     dword ptr [rsp+1C0h+TokenInformation], r12d
0x180017d42  mov     [rsp+1C0h+var_168], r12d
0x180017d47  lea     rax, [rsp+1C0h+var_168]
0x180017d4c  mov     [rsp+1C0h+ReturnLength], rax; ReturnLength
0x180017d51  mov     r9d, 4; TokenInformationLength
0x180017d57  lea     r8, [rsp+1C0h+TokenInformation]; TokenInformation
0x180017d5c  lea     edx, [r9+19h]; TokenInformationClass
0x180017d60  mov     rcx, [rsp+1C0h+TokenHandle+8]; TokenHandle
0x180017d65  call    cs:__imp_GetTokenInformation
0x180017d6b  test    eax, eax
0x180017d6d  jz      short loc_180017D7A
0x180017d6f  cmp     dword ptr [rsp+1C0h+TokenInformation], r12d
0x180017d74  setnz   sil
0x180017d78  jmp     short loc_180017D97
0x180017d7a  call    cs:__imp_GetLastError
0x180017d80  mov     edi, eax
0x180017d82  test    eax, eax
0x180017d84  jle     short loc_180017D8F
0x180017d86  movzx   edi, ax
0x180017d89  or      edi, 80070000h
0x180017d8f  test    edi, edi
0x180017d91  js      loc_180017F77
0x180017d97  test    sil, sil
0x180017d9a  jnz     loc_18001801F
0x180017da0  mov     [rsp+1C0h+TokenInformation], r12
0x180017da5  mov     qword ptr [rsp+1C0h+var_168], r12
0x180017daa  lea     rdx, [rsp+1C0h+TokenInformation]; void **
0x180017daf  mov     rcx, [rsp+1C0h+TokenHandle+8]; void *
0x180017db4  call    ?GetPackageSidFromTokenUsingPFN@LocationCallerInfoHelper@@SAJPEAXPEAPEAX@Z; LocationCallerInfoHelper::GetPackageSidFromTokenUsingPFN(void *,void * *)
0x180017db9  test    eax, eax
0x180017dbb  js      loc_180017F15
0x180017dc1  mov     rcx, [rsp+1C0h+TokenInformation]; Sid
0x180017dc6  test    rcx, rcx
0x180017dc9  jz      loc_180017F15
0x180017dcf  lea     rdx, [rsp+1C0h+var_168]; StringSid
0x180017dd4  call    cs:__imp_ConvertSidToStringSidW
0x180017dda  test    eax, eax
0x180017ddc  jz      loc_180017EAD
0x180017de2  mov     rcx, qword ptr [rsp+1C0h+var_168]; unsigned __int16 *
0x180017de7  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x180017dec  mov     r8d, eax; int
0x180017def  mov     rdx, rcx; unsigned __int16 *
0x180017df2  lea     rcx, [rsp+1C0h+bstrString]; this
0x180017df7  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180017dfc  test    eax, eax
0x180017dfe  mov     edi, eax
0x180017e00  jns     loc_180017EAD
0x180017e06  mov     rcx, qword ptr [rsp+1C0h+var_168]; hMem
0x180017e0b  call    cs:__imp_LocalFree
0x180017e11  mov     qword ptr [rsp+1C0h+var_168], r12
0x180017e16  lea     rcx, [rbp+0C0h+var_140]; this
0x180017e1a  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x180017e1f  nop
0x180017e20  mov     [rsp+1C0h+TokenHandle], r13
0x180017e25  lea     rcx, [rsp+1C0h+TokenHandle]; this
0x180017e2a  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x180017e2f  nop
0x180017e30  test    bl, bl
0x180017e32  jz      short loc_180017E3B
0x180017e34  call    cs:__imp_CoRevertToSelf
0x180017e3a  nop
0x180017e3b  mov     rcx, [rsp+1C0h+hMem]; hMem
0x180017e40  call    cs:__imp_LocalFree
0x180017e46  mov     [rsp+1C0h+hMem], r12
0x180017e4b  mov     rcx, [rsp+1C0h+bstrString]; bstrString
0x180017e50  call    cs:__imp_SysFreeString
0x180017e56  nop
0x180017e57  mov     rcx, [rsp+1C0h+var_188]; bstrString
0x180017e5c  call    cs:__imp_SysFreeString
0x180017e62  mov     eax, edi
0x180017e64  mov     rcx, [rbp+0C0h+var_40]
0x180017e6b  xor     rcx, rsp; StackCookie
0x180017e6e  call    __security_check_cookie
0x180017e73  mov     rbx, [rsp+1C0h+arg_18]
0x180017e7b  add     rsp, 190h
0x180017e82  pop     r15
0x180017e84  pop     r14
0x180017e86  pop     r13
0x180017e88  pop     r12
0x180017e8a  pop     rdi
0x180017e8b  pop     rsi
0x180017e8c  pop     rbp
0x180017e8d  retn
0x180017e8e  cmp     edi, 80010117h
0x180017e94  jz      loc_180017CA8
0x180017e9a  test    bl, bl
0x180017e9c  jz      loc_180017FB8
0x180017ea2  call    cs:__imp_CoRevertToSelf
0x180017ea8  jmp     loc_180017FB8
0x180017ead  mov     rcx, qword ptr [rsp+1C0h+var_168]; hMem
0x180017eb2  call    cs:__imp_LocalFree
0x180017eb8  mov     rax, [rsp+1C0h+var_188]
0x180017ebd  mov     [r15], rax
0x180017ec0  mov     rax, [rsp+1C0h+bstrString]
0x180017ec5  mov     [r14], rax
0x180017ec8  lea     rcx, [rbp+0C0h+var_140]; this
0x180017ecc  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x180017ed1  nop
0x180017ed2  mov     [rsp+1C0h+TokenHandle], r13
0x180017ed7  lea     rcx, [rsp+1C0h+TokenHandle]; this
0x180017edc  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x180017ee1  nop
0x180017ee2  test    bl, bl
0x180017ee4  jz      short loc_180017EED
0x180017ee6  call    cs:__imp_CoRevertToSelf
0x180017eec  nop
0x180017eed  mov     rcx, [rsp+1C0h+hMem]; hMem
0x180017ef2  call    cs:__imp_LocalFree
0x180017ef8  mov     [rsp+1C0h+hMem], r12
0x180017efd  xor     ecx, ecx; bstrString
0x180017eff  call    cs:__imp_SysFreeString
0x180017f05  nop
0x180017f06  xor     ecx, ecx; bstrString
0x180017f08  call    cs:__imp_SysFreeString
0x180017f0e  xor     eax, eax
0x180017f10  jmp     loc_180017E64
0x180017f15  mov     r8d, 0Eh
0x180017f1b  lea     rdx, aNonpackagedapp; "NonPackagedApp"
0x180017f22  jmp     loc_180017DF2
0x180017f27  xor     ecx, ecx; hMem
0x180017f29  call    cs:__imp_LocalFree
0x180017f2f  mov     [rsp+1C0h+hMem], r12
0x180017f34  xor     ecx, ecx; bstrString
0x180017f36  call    cs:__imp_SysFreeString
0x180017f3c  nop
0x180017f3d  xor     ecx, ecx; bstrString
0x180017f3f  call    cs:__imp_SysFreeString
0x180017f45  mov     eax, 80070057h
0x180017f4a  jmp     loc_180017E64
0x180017f4f  lea     rdx, [rsp+1C0h+hMem]; StringSid
0x180017f54  lea     rcx, [rbp+0C0h+Sid]; Sid
0x180017f58  call    cs:__imp_ConvertSidToStringSidW
0x180017f5e  test    eax, eax
0x180017f60  jnz     loc_180018055
0x180017f66  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180017f6b  mov     edi, eax
0x180017f6d  lea     rcx, [rbp+0C0h+var_C0]; this
0x180017f71  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x180017f76  nop
0x180017f77  lea     rcx, [rbp+0C0h+var_140]; this
0x180017f7b  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x180017f80  nop
0x180017f81  mov     [rsp+1C0h+TokenHandle], r13
0x180017f86  lea     rcx, [rsp+1C0h+TokenHandle]; this
0x180017f8b  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x180017f90  nop
0x180017f91  test    bl, bl
0x180017f93  jz      short loc_180017F9C
0x180017f95  call    cs:__imp_CoRevertToSelf
0x180017f9b  nop
0x180017f9c  mov     rcx, [rsp+1C0h+hMem]; hMem
0x180017fa1  call    cs:__imp_LocalFree
0x180017fa7  mov     [rsp+1C0h+hMem], r12
0x180017fac  xor     ecx, ecx
0x180017fae  jmp     loc_180017E50
0x180017fb3  mov     edi, 80070005h
0x180017fb8  mov     rcx, [rsp+1C0h+hMem]; hMem
0x180017fbd  call    cs:__imp_LocalFree
0x180017fc3  mov     [rsp+1C0h+hMem], r12
0x180017fc8  xor     ecx, ecx; bstrString
0x180017fca  call    cs:__imp_SysFreeString
0x180017fd0  nop
0x180017fd1  xor     ecx, ecx
0x180017fd3  jmp     loc_180017E5C
0x180017fd8  mov     [rsp+1C0h+TokenHandle], r13
0x180017fdd  lea     rcx, [rsp+1C0h+TokenHandle]; this
0x180017fe2  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x180017fe7  nop
0x180017fe8  test    bl, bl
0x180017fea  jz      short loc_180017FB3
0x180017fec  call    cs:__imp_CoRevertToSelf
0x180017ff2  jmp     short loc_180017FB3
0x180017ff4  lea     rcx, [rbp+0C0h+var_140]; this
0x180017ff8  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x180017ffd  nop
0x180017ffe  mov     [rsp+1C0h+TokenHandle], r13
0x180018003  lea     rcx, [rsp+1C0h+TokenHandle]; this
0x180018008  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x18001800d  nop
0x18001800e  test    bl, bl
0x180018010  jz      short loc_180018018
0x180018012  call    cs:__imp_CoRevertToSelf
0x180018018  mov     edi, 8000FFFFh
0x18001801d  jmp     short loc_180017FB8
0x18001801f  xor     edx, edx; Val
0x180018021  lea     r8d, [rdx+78h]; Size
0x180018025  lea     rcx, [rbp+0C0h+var_C0]; void *
0x180018029  call    memset_0
0x18001802e  lea     rcx, [rbp+0C0h+var_C0]; this
0x180018032  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x180018037  nop
0x180018038  lea     rdx, [rbp+0C0h+var_C0]; struct ATL::CSid *
0x18001803c  lea     rcx, [rsp+1C0h+TokenHandle]; struct ATL::CAccessToken *
0x180018041  call    ?GetAppContainerSid@LocationCallerInfoHelper@@SAJAEBVCAccessToken@ATL@@AEAVCSid@3@@Z; LocationCallerInfoHelper::GetAppContainerSid(ATL::CAccessToken const &,ATL::CSid &)
0x180018046  mov     edi, eax
0x180018048  test    eax, eax
0x18001804a  js      loc_180017F6D
0x180018050  jmp     loc_180017F4F
0x180018055  mov     rdx, [rsp+1C0h+hMem]; unsigned __int16 *
0x18001805a  lea     rcx, [rsp+1C0h+bstrString]; this
0x18001805f  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180018064  mov     edi, eax
0x180018066  lea     rcx, [rbp+0C0h+var_C0]; this
0x18001806a  test    eax, eax
0x18001806c  jns     short loc_180018078
0x18001806e  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x180018073  jmp     loc_180017E16
0x180018078  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18001807d  jmp     loc_180017EB8
```
