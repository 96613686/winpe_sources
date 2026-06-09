# NgcUtils::GetUserNameAndDomain(void * const,bool,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,bool *)

- ea: `0x18008d340`
- end: `0x18008d826`
- name: `?GetUserNameAndDomain@NgcUtils@@YAJQEAX_NPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2PEA_N@Z`
- size: `1254`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18006b150`
- `0x1800779f4`
- `0x18007cbb0`

## callees

- `0x18000782c`
- `0x180010a94`
- `0x1800137c0`
- `0x180028d18`
- `0x1800294c0`
- `0x180046fd8`
- `0x18004e924`
- `0x180085f80`
- `0x180088538`
- `0x18008b554`
- `0x18008b590`
- `0x18008b770`
- `0x18008c0d8`
- `0x18008c740`
- `0x18008d340`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d5bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d670`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d69b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d5bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d670`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d69b`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18008d5af`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18008d65b`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18008d5af`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18008d65b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupSids2` at `0x18008d4e5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupSids2` at `0x18008d4e5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18008d43a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18008d43a`

## string_xrefs

- `0x18008d3bb`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall NgcUtils::GetUserNameAndDomain(void *a1, unsigned __int8 a2, __int64 a3, __int64 a4, _BYTE *a5)
{
  int v7; // r14d
  __int64 v8; // rdx
  int updated; // eax
  __int64 v11; // rdx
  NTSTATUS v12; // eax
  NTSTATUS v13; // ebx
  int v14; // ebx
  NTSTATUS v15; // ebx
  DWORD LastError; // eax
  signed int v17; // eax
  int v18; // ecx
  int ReferencedDomains; // [rsp+20h] [rbp-81h]
  DWORD v20; // [rsp+30h] [rbp-71h] BYREF
  __int64 v21; // [rsp+38h] [rbp-69h] BYREF
  __int64 v22; // [rsp+40h] [rbp-61h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-59h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+4Ch] [rbp-55h] BYREF
  void **v25; // [rsp+50h] [rbp-51h] BYREF
  PVOID PolicyHandle; // [rsp+58h] [rbp-49h] BYREF
  LPWSTR Name; // [rsp+60h] [rbp-41h] BYREF
  PLSA_REFERENCED_DOMAIN_LIST p_cchReferencedDomainName; // [rsp+68h] [rbp-39h] BYREF
  char v29; // [rsp+70h] [rbp-31h]
  LPWSTR ReferencedDomainName; // [rsp+78h] [rbp-29h] BYREF
  PLSA_TRANSLATED_NAME Names; // [rsp+80h] [rbp-21h] BYREF
  char v32; // [rsp+88h] [rbp-19h]
  PSID Sids; // [rsp+90h] [rbp-11h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]
  PSID Sid; // [rsp+100h] [rbp+5Fh] BYREF
  DWORD cchReferencedDomainName; // [rsp+108h] [rbp+67h] BYREF

  Sid = a1;
  v7 = a2;
  if ( a2 )
  {
    LOBYTE(cchReferencedDomainName) = 0;
    Name = (LPWSTR)&Sid;
    p_cchReferencedDomainName = (PLSA_REFERENCED_DOMAIN_LIST)&cchReferencedDomainName;
    lambda_e5f81c1d058d2c8ded59e4efe2ed327f_::operator()(&Name);
    if ( (_BYTE)cchReferencedDomainName )
      return NgcUtils::GetUserNameAndDomainForHybridCloudTrust(Sid, v8, a3, a4, a5);
  }
  updated = NgcUtils::Detail::CacheUpdateVersion((NgcUtils::Detail *)a1);
  if ( updated < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22A,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
      (const char *)(unsigned int)updated,
      ReferencedDomains);
  LOBYTE(v11) = v7;
  if ( (int)NgcUtils::Detail::CacheGetUserNameAndDomain(Sid, v11, a3, a4) >= 0 )
  {
    if ( a5 )
      *a5 = 1;
    return 0;
  }
  if ( a5 )
    *a5 = 0;
  v25 = &Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::`vftable';
  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v25);
  v12 = LsaOpenPolicy(0, &ObjectAttributes, 0x801u, &PolicyHandle);
  v13 = v12;
  if ( v12 < 0 )
  {
    if ( (unsigned int)dword_180122070 > 2 )
    {
      cchReferencedDomainName = v12;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)word_180107532,
        0,
        0,
        (__int64)&cchReferencedDomainName);
    }
    v14 = v13 | 0x10000000;
    goto LABEL_37;
  }
  Sids = Sid;
  v22 = 0;
  v21 = 0;
  ReferencedDomainName = (LPWSTR)&v21;
  Names = 0;
  v32 = 1;
  Name = (LPWSTR)&v22;
  p_cchReferencedDomainName = 0;
  v29 = 1;
  v15 = LsaLookupSids2(PolicyHandle, v7 << 30, 1u, &Sids, &p_cchReferencedDomainName, &Names);
  wil::details::out_param_t<std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>>::~out_param_t<std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>>(&Name);
  wil::details::out_param_t<std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>>::~out_param_t<std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>>(&ReferencedDomainName);
  if ( v15 < 0 )
  {
    if ( (unsigned int)(v15 + 1073741428) <= 1 )
    {
      if ( (unsigned int)dword_180122070 > 3 )
      {
        v20 = v15;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)word_180107502,
          0,
          0,
          (__int64)&v20);
      }
      cchName = 0;
      cchReferencedDomainName = 0;
      peUse = SidTypeInvalid;
      if ( LookupAccountSidLocalW(Sid, 0, &cchName, 0, &cchReferencedDomainName, &peUse) )
      {
        std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>::~unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>(&v21);
        std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>::~unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>(&v22);
        v14 = -2147418113;
        goto LABEL_37;
      }
      LastError = GetLastError();
      v14 = LastError;
      if ( LastError == 122 )
      {
        std::vector<unsigned short>::vector<unsigned short>(&Name, cchName);
        std::vector<unsigned short>::vector<unsigned short>(&ReferencedDomainName, cchReferencedDomainName);
        if ( LookupAccountSidLocalW(Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
        {
          std::wstring::assign(a3, Name);
          std::wstring::assign(a4, ReferencedDomainName);
          std::vector<unsigned short>::_Tidy(&ReferencedDomainName);
          std::vector<unsigned short>::_Tidy(&Name);
          std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>::~unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>(&v21);
          std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>::~unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>(&v22);
          v14 = 0;
          goto LABEL_37;
        }
        if ( (unsigned int)dword_180122070 > 2 )
        {
          v20 = GetLastError();
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_180122070,
            (unsigned __int8 *)&unk_180107480,
            0,
            0,
            (__int64)&v20);
        }
        v17 = GetLastError();
        v14 = v17;
        if ( v17 > 0 )
          v14 = (unsigned __int16)v17 | 0x80070000;
        std::vector<unsigned short>::_Tidy(&ReferencedDomainName);
        std::vector<unsigned short>::_Tidy(&Name);
      }
      else
      {
        if ( (unsigned int)dword_180122070 > 2 )
        {
          v20 = LastError;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_180122070,
            (unsigned __int8 *)&dword_1801074D4,
            0,
            0,
            (__int64)&v20);
        }
        if ( v14 > 0 )
          v14 = (unsigned __int16)v14 | 0x80070000;
      }
    }
    else
    {
      if ( (unsigned int)dword_180122070 > 2 )
      {
        cchReferencedDomainName = v15;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)&word_1801074AE,
          0,
          0,
          (__int64)&cchReferencedDomainName);
      }
      v14 = v15 | 0x10000000;
    }
    std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>::~unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>(&v21);
    std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>::~unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>(&v22);
LABEL_37:
    v25 = &Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v25);
    return (unsigned int)v14;
  }
  if ( *(_DWORD *)v21 > 8u || (v18 = 424, !_bittest(&v18, *(_DWORD *)v21)) )
  {
    std::wstring::_Assign<unsigned short>(
      a3,
      *(_QWORD *)(v21 + 16),
      (unsigned __int64)*(unsigned __int16 *)(v21 + 8) >> 1);
    std::wstring::_Assign<unsigned short>(
      a4,
      *(_QWORD *)(*(_QWORD *)(v22 + 8) + 8LL),
      (unsigned __int64)**(unsigned __int16 **)(v22 + 8) >> 1);
    std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>::~unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>(&v21);
    std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>::~unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>(&v22);
    v25 = &Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v25);
    return 0;
  }
  if ( (unsigned int)dword_180122070 > 2 )
  {
    cchReferencedDomainName = *(_DWORD *)v21;
    v20 = -2147024809;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)&dword_180122070,
      (unsigned __int8 *)byte_18010744B,
      0,
      0,
      (__int64)&v20,
      (__int64)&cchReferencedDomainName);
  }
  std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>::~unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>(&v21);
  std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>::~unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>(&v22);
  v25 = &Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v25);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18008d340  mov     [rsp-8+arg_10], rbx
0x18008d345  mov     [rsp-8+Sid], rcx
0x18008d34a  push    rbp
0x18008d34b  push    rsi
0x18008d34c  push    rdi
0x18008d34d  push    r12
0x18008d34f  push    r14
0x18008d351  lea     rbp, [rsp-2Fh]
0x18008d356  sub     rsp, 0D0h
0x18008d35d  mov     rdi, r9
0x18008d360  mov     rsi, r8
0x18008d363  movzx   r14d, dl
0x18008d367  test    dl, dl
0x18008d369  jz      short loc_18008D3AB
0x18008d36b  mov     byte ptr [rbp+4Fh+cchReferencedDomainName], 0
0x18008d36f  lea     rax, [rbp+4Fh+Sid]
0x18008d373  mov     [rbp+4Fh+Name], rax
0x18008d377  lea     rax, [rbp+4Fh+cchReferencedDomainName]
0x18008d37b  mov     [rbp+4Fh+var_88], rax
0x18008d37f  lea     rcx, [rbp+4Fh+Name]
0x18008d383  call    _lambda_e5f81c1d058d2c8ded59e4efe2ed327f___operator__
0x18008d388  cmp     byte ptr [rbp+4Fh+cchReferencedDomainName], 0
0x18008d38c  jz      short loc_18008D3AB
0x18008d38e  mov     rax, [rbp+4Fh+arg_20]
0x18008d392  mov     [rsp+0F0h+ReferencedDomains], rax; __int64
0x18008d397  mov     r9, rdi
0x18008d39a  mov     r8, rsi
0x18008d39d  mov     rcx, [rbp+4Fh+Sid]; Sid
0x18008d3a1  call    NgcUtils__GetUserNameAndDomainForHybridCloudTrust
0x18008d3a6  jmp     loc_18008D80F
0x18008d3ab  call    ?CacheUpdateVersion@Detail@NgcUtils@@YAJXZ; NgcUtils::Detail::CacheUpdateVersion(void)
0x18008d3b0  test    eax, eax
0x18008d3b2  jns     short loc_18008D3CC
0x18008d3b4  mov     rcx, [rbp+57h]; this
0x18008d3b8  mov     r9d, eax; char *
0x18008d3bb  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18008d3c2  mov     edx, 22Ah; void *
0x18008d3c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d3cc  mov     r9, rdi
0x18008d3cf  mov     r8, rsi
0x18008d3d2  mov     dl, r14b
0x18008d3d5  mov     rcx, [rbp+4Fh+Sid]
0x18008d3d9  call    ?CacheGetUserNameAndDomain@Detail@NgcUtils@@YAJQEAX_NPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z; NgcUtils::Detail::CacheGetUserNameAndDomain(void * const,bool,std::wstring *,std::wstring *)
0x18008d3de  test    eax, eax
0x18008d3e0  mov     rax, [rbp+4Fh+arg_20]
0x18008d3e4  js      short loc_18008D3F7
0x18008d3e6  test    rax, rax
0x18008d3e9  jz      loc_18008D80D
0x18008d3ef  mov     byte ptr [rax], 1
0x18008d3f2  jmp     loc_18008D80D
0x18008d3f7  test    rax, rax
0x18008d3fa  jz      short loc_18008D3FF
0x18008d3fc  mov     byte ptr [rax], 0
0x18008d3ff  lea     r12, ??_7?$HandleT@ULsaPolicyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LsaPolicyHandleTraits>::`vftable'
0x18008d406  mov     [rbp+4Fh+var_A0], r12
0x18008d40a  mov     [rbp+4Fh+PolicyHandle], 0
0x18008d412  xorps   xmm0, xmm0
0x18008d415  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x18008d419  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x18008d41d  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18008d421  lea     rcx, [rbp+4Fh+var_A0]
0x18008d425  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18008d42a  lea     r9, [rbp+4Fh+PolicyHandle]; PolicyHandle
0x18008d42e  mov     r8d, 801h; DesiredAccess
0x18008d434  lea     rdx, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18008d438  xor     ecx, ecx; SystemName
0x18008d43a  call    cs:__imp_LsaOpenPolicy
0x18008d440  mov     ebx, eax
0x18008d442  test    eax, eax
0x18008d444  jns     short loc_18008D47F
0x18008d446  mov     ecx, cs:dword_180122070
0x18008d44c  cmp     ecx, 2
0x18008d44f  jbe     short loc_18008D476
0x18008d451  mov     [rbp+4Fh+cchReferencedDomainName], eax
0x18008d454  lea     rax, [rbp+4Fh+cchReferencedDomainName]
0x18008d458  mov     [rsp+0F0h+ReferencedDomains], rax
0x18008d45d  xor     r9d, r9d
0x18008d460  xor     r8d, r8d
0x18008d463  lea     rdx, word_180107532
0x18008d46a  lea     rcx, dword_180122070
0x18008d471  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18008d476  bts     ebx, 1Ch
0x18008d47a  jmp     loc_18008D724
0x18008d47f  mov     rax, [rbp+4Fh+Sid]
0x18008d483  mov     [rbp+4Fh+Sids], rax
0x18008d487  mov     [rbp+4Fh+var_B0], 0
0x18008d48f  mov     [rbp+4Fh+var_B8], 0
0x18008d497  lea     rax, [rbp+4Fh+var_B8]
0x18008d49b  mov     [rbp+4Fh+ReferencedDomainName], rax
0x18008d49f  mov     [rbp+4Fh+var_70], 0
0x18008d4a7  mov     [rbp+4Fh+var_68], 1
0x18008d4ab  lea     rax, [rbp+4Fh+var_B0]
0x18008d4af  mov     [rbp+4Fh+Name], rax
0x18008d4b3  mov     [rbp+4Fh+var_88], 0
0x18008d4bb  mov     [rbp+4Fh+var_80], 1
0x18008d4bf  mov     edx, r14d
0x18008d4c2  shl     edx, 1Eh; LookupOptions
0x18008d4c5  lea     rax, [rbp+4Fh+var_70]
0x18008d4c9  mov     [rsp+0F0h+Names], rax; Names
0x18008d4ce  lea     rax, [rbp+4Fh+var_88]
0x18008d4d2  mov     [rsp+0F0h+ReferencedDomains], rax; ReferencedDomains
0x18008d4d7  lea     r9, [rbp+4Fh+Sids]; Sids
0x18008d4db  mov     r8d, 1; Count
0x18008d4e1  mov     rcx, [rbp+4Fh+PolicyHandle]; PolicyHandle
0x18008d4e5  call    cs:__imp_LsaLookupSids2
0x18008d4eb  mov     ebx, eax
0x18008d4ed  lea     rcx, [rbp+4Fh+Name]
0x18008d4f1  call    ??1?$out_param_t@V?$unique_ptr@U_LSA_TRANSLATED_NAME@@U?$lsamem_delete@U_LSA_TRANSLATED_NAME@@@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>>::~out_param_t<std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>>(void)
0x18008d4f6  lea     rcx, [rbp+4Fh+ReferencedDomainName]
0x18008d4fa  call    ??1?$out_param_t@V?$unique_ptr@U_LSA_TRANSLATED_NAME@@U?$lsamem_delete@U_LSA_TRANSLATED_NAME@@@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>>::~out_param_t<std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>>(void)
0x18008d4ff  test    ebx, ebx
0x18008d501  jns     loc_18008D738
0x18008d507  lea     ecx, [rbx+3FFFFE74h]
0x18008d50d  cmp     ecx, 1
0x18008d510  jbe     short loc_18008D54B
0x18008d512  mov     ecx, cs:dword_180122070
0x18008d518  cmp     ecx, 2
0x18008d51b  jbe     short loc_18008D542
0x18008d51d  mov     [rbp+4Fh+cchReferencedDomainName], ebx
0x18008d520  lea     rax, [rbp+4Fh+cchReferencedDomainName]
0x18008d524  mov     [rsp+0F0h+ReferencedDomains], rax
0x18008d529  xor     r9d, r9d
0x18008d52c  xor     r8d, r8d
0x18008d52f  lea     rdx, word_1801074AE
0x18008d536  lea     rcx, dword_180122070
0x18008d53d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18008d542  bts     ebx, 1Ch
0x18008d546  jmp     loc_18008D607
0x18008d54b  mov     eax, cs:dword_180122070
0x18008d551  cmp     eax, 3
0x18008d554  jbe     short loc_18008D57B
0x18008d556  mov     [rbp+4Fh+var_C0], ebx
0x18008d559  lea     rax, [rbp+4Fh+var_C0]
0x18008d55d  mov     [rsp+0F0h+ReferencedDomains], rax
0x18008d562  xor     r9d, r9d
0x18008d565  xor     r8d, r8d
0x18008d568  lea     rdx, word_180107502
0x18008d56f  lea     rcx, dword_180122070
0x18008d576  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18008d57b  mov     [rbp+4Fh+cchName], 0
0x18008d582  mov     [rbp+4Fh+cchReferencedDomainName], 0
0x18008d589  mov     [rbp+4Fh+peUse], 7
0x18008d590  lea     rax, [rbp+4Fh+peUse]
0x18008d594  mov     [rsp+0F0h+Names], rax; peUse
0x18008d599  lea     rax, [rbp+4Fh+cchReferencedDomainName]
0x18008d59d  mov     [rsp+0F0h+ReferencedDomains], rax; cchReferencedDomainName
0x18008d5a2  xor     r9d, r9d; ReferencedDomainName
0x18008d5a5  lea     r8, [rbp+4Fh+cchName]; cchName
0x18008d5a9  xor     edx, edx; Name
0x18008d5ab  mov     rcx, [rbp+4Fh+Sid]; Sid
0x18008d5af  call    cs:__imp_LookupAccountSidLocalW
0x18008d5b5  test    eax, eax
0x18008d5b7  jnz     loc_18008D70C
0x18008d5bd  call    cs:__imp_GetLastError
0x18008d5c3  mov     ebx, eax
0x18008d5c5  cmp     eax, 7Ah ; 'z'
0x18008d5c8  jz      short loc_18008D61F
0x18008d5ca  mov     ecx, cs:dword_180122070
0x18008d5d0  cmp     ecx, 2
0x18008d5d3  jbe     short loc_18008D5FA
0x18008d5d5  mov     [rbp+4Fh+var_C0], eax
0x18008d5d8  lea     rax, [rbp+4Fh+var_C0]
0x18008d5dc  mov     [rsp+0F0h+ReferencedDomains], rax
0x18008d5e1  xor     r9d, r9d
0x18008d5e4  xor     r8d, r8d
0x18008d5e7  lea     rdx, dword_1801074D4
0x18008d5ee  lea     rcx, dword_180122070
0x18008d5f5  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18008d5fa  test    ebx, ebx
0x18008d5fc  jle     short loc_18008D607
0x18008d5fe  movzx   ebx, bx
0x18008d601  or      ebx, 80070000h
0x18008d607  lea     rcx, [rbp+4Fh+var_B8]
0x18008d60b  call    ??1?$unique_ptr@U_LSA_TRANSLATED_NAME@@U?$lsamem_delete@U_LSA_TRANSLATED_NAME@@@@@std@@QEAA@XZ; std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>::~unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>(void)
0x18008d610  nop
0x18008d611  lea     rcx, [rbp+4Fh+var_B0]
0x18008d615  call    ??1?$unique_ptr@U_LSA_TRANSLATED_NAME@@U?$lsamem_delete@U_LSA_TRANSLATED_NAME@@@@@std@@QEAA@XZ; std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>::~unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>(void)
0x18008d61a  jmp     loc_18008D724
0x18008d61f  mov     edx, [rbp+4Fh+cchName]
0x18008d622  lea     rcx, [rbp+4Fh+Name]
0x18008d626  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18008d62b  nop
0x18008d62c  mov     edx, [rbp+4Fh+cchReferencedDomainName]
0x18008d62f  lea     rcx, [rbp+4Fh+ReferencedDomainName]
0x18008d633  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18008d638  nop
0x18008d639  lea     rax, [rbp+4Fh+peUse]
0x18008d63d  mov     [rsp+0F0h+Names], rax; peUse
0x18008d642  lea     rax, [rbp+4Fh+cchReferencedDomainName]
0x18008d646  mov     [rsp+0F0h+ReferencedDomains], rax; cchReferencedDomainName
0x18008d64b  mov     r9, [rbp+4Fh+ReferencedDomainName]; ReferencedDomainName
0x18008d64f  lea     r8, [rbp+4Fh+cchName]; cchName
0x18008d653  mov     rdx, [rbp+4Fh+Name]; Name
0x18008d657  mov     rcx, [rbp+4Fh+Sid]; Sid
0x18008d65b  call    cs:__imp_LookupAccountSidLocalW
0x18008d661  test    eax, eax
0x18008d663  jnz     short loc_18008D6C8
0x18008d665  mov     eax, cs:dword_180122070
0x18008d66b  cmp     eax, 2
0x18008d66e  jbe     short loc_18008D69B
0x18008d670  call    cs:__imp_GetLastError
0x18008d676  mov     [rbp+4Fh+var_C0], eax
0x18008d679  lea     rax, [rbp+4Fh+var_C0]
0x18008d67d  mov     [rsp+0F0h+ReferencedDomains], rax
0x18008d682  xor     r9d, r9d
0x18008d685  xor     r8d, r8d
0x18008d688  lea     rdx, unk_180107480
0x18008d68f  lea     rcx, dword_180122070
0x18008d696  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18008d69b  call    cs:__imp_GetLastError
0x18008d6a1  mov     ebx, eax
0x18008d6a3  test    eax, eax
0x18008d6a5  jle     short loc_18008D6B0
0x18008d6a7  movzx   ebx, ax
0x18008d6aa  or      ebx, 80070000h
0x18008d6b0  lea     rcx, [rbp+4Fh+ReferencedDomainName]
0x18008d6b4  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18008d6b9  nop
0x18008d6ba  lea     rcx, [rbp+4Fh+Name]
0x18008d6be  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18008d6c3  jmp     loc_18008D607
0x18008d6c8  mov     rdx, [rbp+4Fh+Name]
0x18008d6cc  mov     rcx, rsi
0x18008d6cf  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18008d6d4  mov     rdx, [rbp+4Fh+ReferencedDomainName]
0x18008d6d8  mov     rcx, rdi
0x18008d6db  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18008d6e0  nop
0x18008d6e1  lea     rcx, [rbp+4Fh+ReferencedDomainName]
0x18008d6e5  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18008d6ea  nop
0x18008d6eb  lea     rcx, [rbp+4Fh+Name]
0x18008d6ef  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18008d6f4  nop
0x18008d6f5  lea     rcx, [rbp+4Fh+var_B8]
0x18008d6f9  call    ??1?$unique_ptr@U_LSA_TRANSLATED_NAME@@U?$lsamem_delete@U_LSA_TRANSLATED_NAME@@@@@std@@QEAA@XZ; std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>::~unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>(void)
0x18008d6fe  nop
0x18008d6ff  lea     rcx, [rbp+4Fh+var_B0]
0x18008d703  call    ??1?$unique_ptr@U_LSA_TRANSLATED_NAME@@U?$lsamem_delete@U_LSA_TRANSLATED_NAME@@@@@std@@QEAA@XZ; std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>::~unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>(void)
0x18008d708  xor     ebx, ebx
0x18008d70a  jmp     short loc_18008D724
0x18008d70c  lea     rcx, [rbp+4Fh+var_B8]
0x18008d710  call    ??1?$unique_ptr@U_LSA_TRANSLATED_NAME@@U?$lsamem_delete@U_LSA_TRANSLATED_NAME@@@@@std@@QEAA@XZ; std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>::~unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>(void)
0x18008d715  nop
0x18008d716  lea     rcx, [rbp+4Fh+var_B0]
0x18008d71a  call    ??1?$unique_ptr@U_LSA_TRANSLATED_NAME@@U?$lsamem_delete@U_LSA_TRANSLATED_NAME@@@@@std@@QEAA@XZ; std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>::~unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>(void)
0x18008d71f  mov     ebx, 8000FFFFh
0x18008d724  mov     [rbp+4Fh+var_A0], r12
0x18008d728  lea     rcx, [rbp+4Fh+var_A0]
0x18008d72c  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18008d731  mov     eax, ebx
0x18008d733  jmp     loc_18008D80F
0x18008d738  mov     rdx, [rbp+4Fh+var_B8]
0x18008d73c  mov     eax, [rdx]
0x18008d73e  cmp     eax, 8
0x18008d741  ja      short loc_18008D7BC
0x18008d743  mov     ecx, 1A8h
0x18008d748  bt      ecx, eax
0x18008d74b  jnb     short loc_18008D7BC
0x18008d74d  mov     eax, cs:dword_180122070
0x18008d753  cmp     eax, 2
0x18008d756  jbe     short loc_18008D794
0x18008d758  mov     rax, [rbp+4Fh+var_B8]
0x18008d75c  mov     ecx, [rax]
0x18008d75e  mov     [rbp+4Fh+cchReferencedDomainName], ecx
0x18008d761  mov     [rbp+4Fh+var_C0], 80070057h
0x18008d768  lea     rax, [rbp+4Fh+cchReferencedDomainName]
0x18008d76c  mov     [rsp+0F0h+Names], rax
0x18008d771  lea     rax, [rbp+4Fh+var_C0]
0x18008d775  mov     [rsp+0F0h+ReferencedDomains], rax
0x18008d77a  xor     r9d, r9d
0x18008d77d  xor     r8d, r8d
0x18008d780  lea     rdx, byte_18010744B
0x18008d787  lea     rcx, dword_180122070
0x18008d78e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18008d793  nop
0x18008d794  lea     rcx, [rbp+4Fh+var_B8]
0x18008d798  call    ??1?$unique_ptr@U_LSA_TRANSLATED_NAME@@U?$lsamem_delete@U_LSA_TRANSLATED_NAME@@@@@std@@QEAA@XZ; std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>::~unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>(void)
0x18008d79d  nop
0x18008d79e  lea     rcx, [rbp+4Fh+var_B0]
0x18008d7a2  call    ??1?$unique_ptr@U_LSA_TRANSLATED_NAME@@U?$lsamem_delete@U_LSA_TRANSLATED_NAME@@@@@std@@QEAA@XZ; std::unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>::~unique_ptr<_LSA_TRANSLATED_NAME,lsamem_delete<_LSA_TRANSLATED_NAME>>(void)
0x18008d7a7  nop
0x18008d7a8  mov     [rbp+4Fh+var_A0], r12
0x18008d7ac  lea     rcx, [rbp+4Fh+var_A0]
0x18008d7b0  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18008d7b5  mov     eax, 80070057h
0x18008d7ba  jmp     short loc_18008D80F
0x18008d7bc  movzx   r8d, word ptr [rdx+8]
0x18008d7c1  shr     r8, 1
0x18008d7c4  mov     rdx, [rdx+10h]
0x18008d7c8  mov     rcx, rsi
0x18008d7cb  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18008d7d0  mov     rax, [rbp+4Fh+var_B0]
0x18008d7d4  mov     rdx, [rax+8]
0x18008d7d8  movzx   r8d, word ptr [rdx]
0x18008d7dc  shr     r8, 1
0x18008d7df  mov     rdx, [rdx+8]
0x18008d7e3  mov     rcx, rdi
0x18008d7e6  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18008d7eb  nop
  ... truncated ...
```
