# AccountSystemOnlyInfo::ApplyToWriter(Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter &)

- ea: `0x18010df64`
- end: `0x18010e624`
- name: `?ApplyToWriter@AccountSystemOnlyInfo@@QEAAJAEAVJsonObjectWriter@TokenBroker@Authentication@Security@Internal@Windows@@@Z`
- size: `1728`
- prototype: `int(AccountSystemOnlyInfo *__hidden this, struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter *)`
- caller_count: `2`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180074e0c`
- `0x18010de6c`

## callees

- `0x18000bd40`
- `0x1800372d0`
- `0x18003acd0`
- `0x1800425b0`
- `0x180045820`
- `0x180048628`
- `0x18004be18`
- `0x18004cc00`
- `0x18004ce78`
- `0x18004d358`
- `0x18004d844`
- `0x18004e4dc`
- `0x1800511fc`
- `0x1800513a4`
- `0x1800518b0`
- `0x180052f30`
- `0x180053718`
- `0x180079548`
- `0x18008e690`
- `0x18010df64`
- `0x18010ed10`
- `0x18010ee68`
- `0x180112f00`
- `0x1801133dc`
- `0x18011358c`
- `0x180113810`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010e0cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010e142`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010e1a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010e5da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010e5e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010e0cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010e142`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010e1a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010e5da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010e5e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18010e37c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18010e3f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18010e509`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18010e37c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18010e3f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18010e509`

## string_xrefs

- `0x18010dff6`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18010e0ac`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18010e126`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18010e184`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18010e1fe`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18010e5b6`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18010e403`: `AccountUserSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall AccountSystemOnlyInfo::ApplyToWriter(
        AccountSystemOnlyInfo *this,
        struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter *a2)
{
  HSTRING *v4; // rax
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  HSTRING *v8; // rax
  int v9; // eax
  __int64 v10; // rdx
  HSTRING *v11; // rax
  HSTRING v12; // rbx
  int v13; // edi
  __int64 v14; // rdx
  __int64 v15; // rdx
  HSTRING *v16; // rax
  HSTRING v17; // rdi
  int v18; // esi
  __int64 v19; // rdx
  HSTRING *v20; // rax
  HSTRING *v21; // rax
  HSTRING *v22; // rax
  HSTRING *v23; // rax
  HSTRING *v24; // rax
  __int64 v25; // rdx
  HSTRING v26; // r14
  HSTRING *v27; // rax
  HSTRING *v28; // rax
  __int64 v29; // rdx
  int v31; // [rsp+20h] [rbp-59h]
  int v32; // [rsp+30h] [rbp-49h] BYREF
  char v33; // [rsp+34h] [rbp-45h]
  __int128 v34; // [rsp+38h] [rbp-41h]
  HSTRING string; // [rsp+48h] [rbp-31h] BYREF
  HSTRING v36; // [rsp+50h] [rbp-29h] BYREF
  __int64 i; // [rsp+58h] [rbp-21h] BYREF
  HSTRING v38; // [rsp+60h] [rbp-19h] BYREF
  std::_Ref_count_base *v39; // [rsp+68h] [rbp-11h]
  HSTRING v40[4]; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v32 = 5;
  v33 = 0;
  v34 = 0;
  v4 = Windows::Internal::StringReference::StringReference(&v38, L"Id");
  LOBYTE(v31) = 0;
  v5 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::Initialize(&v32, 0, *v4, 0);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 670;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v5,
      v31);
    goto LABEL_97;
  }
  v5 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::SetSingleStringValue(
         (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v32,
         *(HSTRING *)this);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 671;
    goto LABEL_5;
  }
  v5 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter::AddSystemDefinedProperty(
         a2,
         (const struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v32);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 672;
    goto LABEL_5;
  }
  v8 = Windows::Internal::StringReference::StringReference(&v38, L"ProviderPfn");
  LOBYTE(v31) = 0;
  v5 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::Initialize(&v32, 0, *v8, 0);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 679;
    goto LABEL_5;
  }
  v5 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::SetSingleStringValue(
         (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v32,
         *((HSTRING *)this + 5));
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 680;
    goto LABEL_5;
  }
  v5 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter::AddSystemDefinedProperty(
         a2,
         (const struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v32);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 681;
    goto LABEL_5;
  }
  string = 0;
  v9 = ConvertScopeToStringScope(*((unsigned int *)this + 12), &string);
  v6 = v9;
  if ( v9 < 0 )
  {
    v10 = 685;
    goto LABEL_16;
  }
  v11 = Windows::Internal::StringReference::StringReference(&v38, L"Scope");
  LOBYTE(v31) = 0;
  v9 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::Initialize(&v32, 0, *v11, 0);
  v6 = v9;
  if ( v9 < 0 )
  {
    v10 = 690;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v9,
      v31);
    if ( string )
      WindowsDeleteString(string);
    goto LABEL_97;
  }
  v12 = string;
  v13 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::SetSingleStringValue(
          (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v32,
          string);
  if ( v13 < 0 )
  {
    v14 = 691;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v13,
      v31);
LABEL_23:
    if ( v12 )
      WindowsDeleteString(v12);
    v6 = v13;
    goto LABEL_97;
  }
  v13 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter::AddSystemDefinedProperty(
          a2,
          (const struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v32);
  if ( v13 < 0 )
  {
    v14 = 692;
    goto LABEL_22;
  }
  v36 = 0;
  v13 = ConvertEnumerableStateToStringEnumerableState(*((unsigned int *)this + 13), &v36);
  if ( v13 < 0 )
  {
    v15 = 696;
    goto LABEL_30;
  }
  v16 = Windows::Internal::StringReference::StringReference(&v38, L"EnumerableState");
  LOBYTE(v31) = 0;
  v13 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::Initialize(&v32, 0, *v16, 0);
  if ( v13 < 0 )
  {
    v15 = 701;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v13,
      v31);
    if ( v36 )
      WindowsDeleteString(v36);
    goto LABEL_23;
  }
  v17 = v36;
  v18 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::SetSingleStringValue(
          (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v32,
          v36);
  if ( v18 < 0 )
  {
    v19 = 702;
    goto LABEL_36;
  }
  v18 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter::AddSystemDefinedProperty(
          a2,
          (const struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v32);
  if ( v18 < 0 )
  {
    v19 = 703;
    goto LABEL_36;
  }
  v20 = Windows::Internal::StringReference::StringReference(&v38, L"IdSalt");
  LOBYTE(v31) = 0;
  v18 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::Initialize(&v32, 2, *v20, 0);
  if ( v18 < 0 )
  {
    v19 = 710;
    goto LABEL_36;
  }
  v18 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::SetInlineBytesValue(
          (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v32,
          *((BYTE **)this + 1),
          *((_DWORD *)this + 4));
  if ( v18 < 0 )
  {
    v19 = 712;
    goto LABEL_36;
  }
  v18 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter::AddSystemDefinedProperty(
          a2,
          (const struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v32);
  if ( v18 < 0 )
  {
    v19 = 713;
    goto LABEL_36;
  }
  v21 = Windows::Internal::StringReference::StringReference(&v38, L"AccountRevisionNumber");
  LOBYTE(v31) = 0;
  v18 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::Initialize(&v32, 0, *v21, 0);
  if ( v18 < 0 )
  {
    v19 = 720;
    goto LABEL_36;
  }
  v18 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::SetSingleStringValue(
          (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v32,
          *((HSTRING *)this + 7));
  if ( v18 < 0 )
  {
    v19 = 721;
    goto LABEL_36;
  }
  v18 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter::AddSystemDefinedProperty(
          a2,
          (const struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v32);
  if ( v18 < 0 )
  {
    v19 = 722;
    goto LABEL_36;
  }
  v22 = Windows::Internal::StringReference::StringReference(&v38, L"AccountPictureRevisionNumber");
  LOBYTE(v31) = 0;
  v18 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::Initialize(&v32, 0, *v22, 0);
  if ( v18 < 0 )
  {
    v19 = 729;
    goto LABEL_36;
  }
  v18 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::SetSingleStringValue(
          (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v32,
          *((HSTRING *)this + 8));
  if ( v18 < 0 )
  {
    v19 = 730;
    goto LABEL_36;
  }
  v18 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter::AddSystemDefinedProperty(
          a2,
          (const struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v32);
  if ( v18 < 0 )
  {
    v19 = 731;
    goto LABEL_36;
  }
  if ( !WindowsIsStringEmpty(*((HSTRING *)this + 9)) )
  {
    v23 = Windows::Internal::StringReference::StringReference(&v38, L"PerUserAccountId");
    LOBYTE(v31) = 0;
    v18 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::Initialize(&v32, 0, *v23, 0);
    if ( v18 < 0 )
    {
      v19 = 740;
      goto LABEL_36;
    }
    v18 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::SetSingleStringValue(
            (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v32,
            *((HSTRING *)this + 9));
    if ( v18 < 0 )
    {
      v19 = 741;
      goto LABEL_36;
    }
    v18 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter::AddSystemDefinedProperty(
            a2,
            (const struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v32);
    if ( v18 < 0 )
    {
      v19 = 742;
      goto LABEL_36;
    }
  }
  if ( WindowsIsStringEmpty(*((HSTRING *)this + 10)) )
    goto LABEL_71;
  v24 = Windows::Internal::StringReference::StringReference(&v38, L"AccountUserSid");
  LOBYTE(v31) = 0;
  v18 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::Initialize(&v32, 0, *v24, 0);
  if ( v18 < 0 )
  {
    v19 = 752;
    goto LABEL_36;
  }
  v18 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::SetSingleStringValue(
          (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v32,
          *((HSTRING *)this + 10));
  if ( v18 < 0 )
  {
    v19 = 753;
    goto LABEL_36;
  }
  v18 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter::AddSystemDefinedProperty(
          a2,
          (const struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v32);
  if ( v18 >= 0 )
  {
LABEL_71:
    v25 = **((_QWORD **)this + 3);
    for ( i = v25; ; v25 = i )
    {
      if ( *(_BYTE *)(v25 + 25) )
        goto LABEL_92;
      std::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>(
        &v38,
        v25 + 64);
      v26 = v38;
      if ( *((_DWORD *)v38 + 2) != 2 )
      {
        v27 = Windows::Internal::StringReference::StringReference(v40, L"HasPropertiesView");
        LOBYTE(v31) = 0;
        v18 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::Initialize(&v32, 4, *v27, 0);
        if ( v18 < 0 )
        {
          v29 = 771;
          goto LABEL_90;
        }
        v18 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::SetBooleanValue(
                (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v32,
                *((_DWORD *)v26 + 2) == 0);
        if ( v18 < 0 )
        {
          v29 = 774;
          goto LABEL_90;
        }
        v18 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter::AddPerAppProperty(
                a2,
                *(HSTRING *)v26,
                (const struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v32);
        if ( v18 < 0 )
        {
          v29 = 777;
          goto LABEL_90;
        }
      }
      if ( !WindowsIsStringEmpty(*((HSTRING *)v26 + 2)) )
      {
        v28 = Windows::Internal::StringReference::StringReference(v40, L"PerAppId");
        LOBYTE(v31) = 0;
        v18 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::Initialize(&v32, 0, *v28, 0);
        if ( v18 < 0 )
        {
          v29 = 787;
LABEL_90:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v29,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
            (const char *)(unsigned int)v18,
            v31);
          if ( v39 )
            std::_Ref_count_base::_Decref(v39);
          goto LABEL_92;
        }
        v18 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::SetSingleStringValue(
                (Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v32,
                *((HSTRING *)v26 + 2));
        if ( v18 < 0 )
        {
          v29 = 790;
          goto LABEL_90;
        }
        v18 = Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter::AddPerAppProperty(
                a2,
                *(HSTRING *)v26,
                (const struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v32);
        if ( v18 < 0 )
        {
          v29 = 793;
          goto LABEL_90;
        }
      }
      if ( v39 )
        std::_Ref_count_base::_Decref(v39);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<PerAppAccountData>>>>,std::_Iterator_base0>::operator++(&i);
    }
  }
  v19 = 754;
LABEL_36:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v19,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
    (const char *)(unsigned int)v18,
    v31);
LABEL_92:
  if ( v17 )
    WindowsDeleteString(v17);
  if ( v12 )
    WindowsDeleteString(v12);
  v6 = v18;
LABEL_97:
  Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::~JsonObjectProperty((Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *)&v32);
  return v6;
}

```

## disassembly

```asm
0x18010df64  mov     [rsp-8+arg_10], rbx
0x18010df69  mov     [rsp-8+arg_18], rsi
0x18010df6e  push    rbp
0x18010df6f  push    rdi
0x18010df70  push    r12
0x18010df72  push    r14
0x18010df74  push    r15
0x18010df76  lea     rbp, [rsp-37h]
0x18010df7b  sub     rsp, 0B0h
0x18010df82  mov     rax, cs:__security_cookie
0x18010df89  xor     rax, rsp
0x18010df8c  mov     [rbp+57h+var_30], rax
0x18010df90  mov     r15, rdx
0x18010df93  mov     r14, rcx
0x18010df96  mov     [rbp+57h+var_A0], 5
0x18010df9d  xor     r12d, r12d
0x18010dfa0  mov     [rbp+57h+var_9C], r12b
0x18010dfa4  xorps   xmm0, xmm0
0x18010dfa7  movdqu  [rbp+57h+var_98], xmm0
0x18010dfac  lea     rdx, aId; "Id"
0x18010dfb3  lea     rcx, [rbp+57h+var_70]; string
0x18010dfb7  call    ??$?0$02@StringReference@Internal@Windows@@QEAA@AEAY02$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[3])
0x18010dfbc  mov     byte ptr [rsp+0D0h+var_B0], r12b; int
0x18010dfc1  xor     r9d, r9d
0x18010dfc4  mov     r8, [rax]
0x18010dfc7  xor     edx, edx
0x18010dfc9  lea     rcx, [rbp+57h+var_A0]
0x18010dfcd  call    ?Initialize@JsonObjectProperty@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJW4SerializedPropertyType@23456@PEAUHSTRING__@@_N2@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::Initialize(Windows::Internal::Security::Authentication::TokenBroker::SerializedPropertyType,HSTRING__ *,bool,bool)
0x18010dfd2  mov     ebx, eax
0x18010dfd4  test    eax, eax
0x18010dfd6  jns     short loc_18010DFDF
0x18010dfd8  mov     edx, 29Eh
0x18010dfdd  jmp     short loc_18010DFF6
0x18010dfdf  mov     rdx, [r14]; HSTRING
0x18010dfe2  lea     rcx, [rbp+57h+var_A0]; this
0x18010dfe6  call    ?SetSingleStringValue@JsonObjectProperty@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::SetSingleStringValue(HSTRING__ *)
0x18010dfeb  mov     ebx, eax
0x18010dfed  test    eax, eax
0x18010dfef  jns     short loc_18010E00E
0x18010dff1  mov     edx, 29Fh; void *
0x18010dff6  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010dffd  mov     r9d, eax; char *
0x18010e000  mov     rcx, [rbp+5Fh]; this
0x18010e004  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010e009  jmp     loc_18010E5F1
0x18010e00e  lea     rdx, [rbp+57h+var_A0]; struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *
0x18010e012  mov     rcx, r15; this
0x18010e015  call    ?AddSystemDefinedProperty@JsonObjectWriter@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJAEBVJsonObjectProperty@23456@@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter::AddSystemDefinedProperty(Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty const &)
0x18010e01a  mov     ebx, eax
0x18010e01c  test    eax, eax
0x18010e01e  jns     short loc_18010E027
0x18010e020  mov     edx, 2A0h
0x18010e025  jmp     short loc_18010DFF6
0x18010e027  lea     rdx, aProviderpfn; "ProviderPfn"
0x18010e02e  lea     rcx, [rbp+57h+var_70]; string
0x18010e032  call    ??$?0$0M@@StringReference@Internal@Windows@@QEAA@AEAY0M@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[12])
0x18010e037  mov     byte ptr [rsp+0D0h+var_B0], r12b; int
0x18010e03c  xor     r9d, r9d
0x18010e03f  mov     r8, [rax]
0x18010e042  xor     edx, edx
0x18010e044  lea     rcx, [rbp+57h+var_A0]
0x18010e048  call    ?Initialize@JsonObjectProperty@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJW4SerializedPropertyType@23456@PEAUHSTRING__@@_N2@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::Initialize(Windows::Internal::Security::Authentication::TokenBroker::SerializedPropertyType,HSTRING__ *,bool,bool)
0x18010e04d  mov     ebx, eax
0x18010e04f  test    eax, eax
0x18010e051  jns     short loc_18010E05A
0x18010e053  mov     edx, 2A7h
0x18010e058  jmp     short loc_18010DFF6
0x18010e05a  mov     rdx, [r14+28h]; HSTRING
0x18010e05e  lea     rcx, [rbp+57h+var_A0]; this
0x18010e062  call    ?SetSingleStringValue@JsonObjectProperty@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::SetSingleStringValue(HSTRING__ *)
0x18010e067  mov     ebx, eax
0x18010e069  test    eax, eax
0x18010e06b  jns     short loc_18010E074
0x18010e06d  mov     edx, 2A8h
0x18010e072  jmp     short loc_18010DFF6
0x18010e074  lea     rdx, [rbp+57h+var_A0]; struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *
0x18010e078  mov     rcx, r15; this
0x18010e07b  call    ?AddSystemDefinedProperty@JsonObjectWriter@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJAEBVJsonObjectProperty@23456@@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter::AddSystemDefinedProperty(Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty const &)
0x18010e080  mov     ebx, eax
0x18010e082  test    eax, eax
0x18010e084  jns     short loc_18010E090
0x18010e086  mov     edx, 2A9h
0x18010e08b  jmp     loc_18010DFF6
0x18010e090  mov     [rbp+57h+string], r12
0x18010e094  lea     rdx, [rbp+57h+string]
0x18010e098  mov     ecx, [r14+30h]
0x18010e09c  call    ?ConvertScopeToStringScope@@YAJW4WebAccountScope@Provider@Web@Authentication@Security@Windows@@AEAVString@Internal@6@@Z; ConvertScopeToStringScope(Windows::Security::Authentication::Web::Provider::WebAccountScope,Windows::Internal::String &)
0x18010e0a1  mov     ebx, eax
0x18010e0a3  test    eax, eax
0x18010e0a5  jns     short loc_18010E0D8
0x18010e0a7  mov     edx, 2ADh; void *
0x18010e0ac  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010e0b3  mov     r9d, eax; char *
0x18010e0b6  mov     rcx, [rbp+5Fh]; this
0x18010e0ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010e0bf  nop
0x18010e0c0  mov     rcx, [rbp+57h+string]; string
0x18010e0c4  test    rcx, rcx
0x18010e0c7  jz      loc_18010E5F1
0x18010e0cd  call    cs:__imp_WindowsDeleteString
0x18010e0d3  jmp     loc_18010E5F1
0x18010e0d8  lea     rdx, aScope; "Scope"
0x18010e0df  lea     rcx, [rbp+57h+var_70]; string
0x18010e0e3  call    ??$?0$05@StringReference@Internal@Windows@@QEAA@AEAY05$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[6])
0x18010e0e8  mov     byte ptr [rsp+0D0h+var_B0], r12b; int
0x18010e0ed  xor     r9d, r9d
0x18010e0f0  mov     r8, [rax]
0x18010e0f3  xor     edx, edx
0x18010e0f5  lea     rcx, [rbp+57h+var_A0]
0x18010e0f9  call    ?Initialize@JsonObjectProperty@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJW4SerializedPropertyType@23456@PEAUHSTRING__@@_N2@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::Initialize(Windows::Internal::Security::Authentication::TokenBroker::SerializedPropertyType,HSTRING__ *,bool,bool)
0x18010e0fe  mov     ebx, eax
0x18010e100  test    eax, eax
0x18010e102  jns     short loc_18010E10B
0x18010e104  mov     edx, 2B2h
0x18010e109  jmp     short loc_18010E0AC
0x18010e10b  mov     rbx, [rbp+57h+string]
0x18010e10f  mov     rdx, rbx; HSTRING
0x18010e112  lea     rcx, [rbp+57h+var_A0]; this
0x18010e116  call    ?SetSingleStringValue@JsonObjectProperty@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::SetSingleStringValue(HSTRING__ *)
0x18010e11b  mov     edi, eax
0x18010e11d  test    eax, eax
0x18010e11f  jns     short loc_18010E14F
0x18010e121  mov     edx, 2B3h; void *
0x18010e126  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010e12d  mov     r9d, edi; char *
0x18010e130  mov     rcx, [rbp+5Fh]; this
0x18010e134  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010e139  nop
0x18010e13a  test    rbx, rbx
0x18010e13d  jz      short loc_18010E148
0x18010e13f  mov     rcx, rbx; string
0x18010e142  call    cs:__imp_WindowsDeleteString
0x18010e148  mov     ebx, edi
0x18010e14a  jmp     loc_18010E5F1
0x18010e14f  lea     rdx, [rbp+57h+var_A0]; struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *
0x18010e153  mov     rcx, r15; this
0x18010e156  call    ?AddSystemDefinedProperty@JsonObjectWriter@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJAEBVJsonObjectProperty@23456@@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter::AddSystemDefinedProperty(Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty const &)
0x18010e15b  mov     edi, eax
0x18010e15d  test    eax, eax
0x18010e15f  jns     short loc_18010E168
0x18010e161  mov     edx, 2B4h
0x18010e166  jmp     short loc_18010E126
0x18010e168  mov     [rbp+57h+var_80], r12
0x18010e16c  lea     rdx, [rbp+57h+var_80]
0x18010e170  mov     ecx, [r14+34h]
0x18010e174  call    ?ConvertEnumerableStateToStringEnumerableState@@YAJW4WebAccountEnumerableState@Credentials@Security@Internal@Windows@@AEAVString@45@@Z; ConvertEnumerableStateToStringEnumerableState(Windows::Internal::Security::Credentials::WebAccountEnumerableState,Windows::Internal::String &)
0x18010e179  mov     edi, eax
0x18010e17b  test    eax, eax
0x18010e17d  jns     short loc_18010E1A9
0x18010e17f  mov     edx, 2B8h; void *
0x18010e184  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010e18b  mov     r9d, edi; char *
0x18010e18e  mov     rcx, [rbp+5Fh]; this
0x18010e192  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010e197  nop
0x18010e198  mov     rcx, [rbp+57h+var_80]; string
0x18010e19c  test    rcx, rcx
0x18010e19f  jz      short loc_18010E13A
0x18010e1a1  call    cs:__imp_WindowsDeleteString
0x18010e1a7  jmp     short loc_18010E13A
0x18010e1a9  lea     rdx, aEnumerablestat_4; "EnumerableState"
0x18010e1b0  lea     rcx, [rbp+57h+var_70]; string
0x18010e1b4  call    ??$?0$0BA@@StringReference@Internal@Windows@@QEAA@AEAY0BA@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[16])
0x18010e1b9  mov     byte ptr [rsp+0D0h+var_B0], r12b; int
0x18010e1be  xor     r9d, r9d
0x18010e1c1  mov     r8, [rax]
0x18010e1c4  xor     edx, edx
0x18010e1c6  lea     rcx, [rbp+57h+var_A0]
0x18010e1ca  call    ?Initialize@JsonObjectProperty@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJW4SerializedPropertyType@23456@PEAUHSTRING__@@_N2@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::Initialize(Windows::Internal::Security::Authentication::TokenBroker::SerializedPropertyType,HSTRING__ *,bool,bool)
0x18010e1cf  mov     edi, eax
0x18010e1d1  test    eax, eax
0x18010e1d3  jns     short loc_18010E1DC
0x18010e1d5  mov     edx, 2BDh
0x18010e1da  jmp     short loc_18010E184
0x18010e1dc  mov     rdi, [rbp+57h+var_80]
0x18010e1e0  mov     rdx, rdi; HSTRING
0x18010e1e3  lea     rcx, [rbp+57h+var_A0]; this
0x18010e1e7  call    ?SetSingleStringValue@JsonObjectProperty@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::SetSingleStringValue(HSTRING__ *)
0x18010e1ec  mov     esi, eax
0x18010e1ee  test    eax, eax
0x18010e1f0  jns     short loc_18010E20F
0x18010e1f2  mov     edx, 2BEh; void *
0x18010e1f7  mov     rcx, [rbp+5Fh]; this
0x18010e1fb  mov     r9d, esi; char *
0x18010e1fe  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010e205  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010e20a  jmp     loc_18010E5D2
0x18010e20f  lea     rdx, [rbp+57h+var_A0]; struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *
0x18010e213  mov     rcx, r15; this
0x18010e216  call    ?AddSystemDefinedProperty@JsonObjectWriter@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJAEBVJsonObjectProperty@23456@@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter::AddSystemDefinedProperty(Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty const &)
0x18010e21b  mov     esi, eax
0x18010e21d  test    eax, eax
0x18010e21f  jns     short loc_18010E228
0x18010e221  mov     edx, 2BFh
0x18010e226  jmp     short loc_18010E1F7
0x18010e228  lea     rdx, aIdsalt; "IdSalt"
0x18010e22f  lea     rcx, [rbp+57h+var_70]; string
0x18010e233  call    ??$?0$06@StringReference@Internal@Windows@@QEAA@AEAY06$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[7])
0x18010e238  mov     byte ptr [rsp+0D0h+var_B0], r12b
0x18010e23d  xor     r9d, r9d
0x18010e240  mov     r8, [rax]
0x18010e243  lea     edx, [r9+2]
0x18010e247  lea     rcx, [rbp+57h+var_A0]
0x18010e24b  call    ?Initialize@JsonObjectProperty@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJW4SerializedPropertyType@23456@PEAUHSTRING__@@_N2@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::Initialize(Windows::Internal::Security::Authentication::TokenBroker::SerializedPropertyType,HSTRING__ *,bool,bool)
0x18010e250  mov     esi, eax
0x18010e252  test    eax, eax
0x18010e254  jns     short loc_18010E25D
0x18010e256  mov     edx, 2C6h
0x18010e25b  jmp     short loc_18010E1F7
0x18010e25d  mov     r8d, [r14+10h]; cbBinary
0x18010e261  mov     rdx, [r14+8]; pbBinary
0x18010e265  lea     rcx, [rbp+57h+var_A0]; this
0x18010e269  call    ?SetInlineBytesValue@JsonObjectProperty@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEAEK@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::SetInlineBytesValue(uchar *,ulong)
0x18010e26e  mov     esi, eax
0x18010e270  test    eax, eax
0x18010e272  jns     short loc_18010E27E
0x18010e274  mov     edx, 2C8h
0x18010e279  jmp     loc_18010E1F7
0x18010e27e  lea     rdx, [rbp+57h+var_A0]; struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *
0x18010e282  mov     rcx, r15; this
0x18010e285  call    ?AddSystemDefinedProperty@JsonObjectWriter@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJAEBVJsonObjectProperty@23456@@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter::AddSystemDefinedProperty(Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty const &)
0x18010e28a  mov     esi, eax
0x18010e28c  test    eax, eax
0x18010e28e  jns     short loc_18010E29A
0x18010e290  mov     edx, 2C9h
0x18010e295  jmp     loc_18010E1F7
0x18010e29a  lea     rdx, aAccountrevisio; "AccountRevisionNumber"
0x18010e2a1  lea     rcx, [rbp+57h+var_70]; string
0x18010e2a5  call    ??$?0$0BG@@StringReference@Internal@Windows@@QEAA@AEAY0BG@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[22])
0x18010e2aa  mov     byte ptr [rsp+0D0h+var_B0], r12b
0x18010e2af  xor     r9d, r9d
0x18010e2b2  mov     r8, [rax]
0x18010e2b5  xor     edx, edx
0x18010e2b7  lea     rcx, [rbp+57h+var_A0]
0x18010e2bb  call    ?Initialize@JsonObjectProperty@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJW4SerializedPropertyType@23456@PEAUHSTRING__@@_N2@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::Initialize(Windows::Internal::Security::Authentication::TokenBroker::SerializedPropertyType,HSTRING__ *,bool,bool)
0x18010e2c0  mov     esi, eax
0x18010e2c2  test    eax, eax
0x18010e2c4  jns     short loc_18010E2D0
0x18010e2c6  mov     edx, 2D0h
0x18010e2cb  jmp     loc_18010E1F7
0x18010e2d0  mov     rdx, [r14+38h]; HSTRING
0x18010e2d4  lea     rcx, [rbp+57h+var_A0]; this
0x18010e2d8  call    ?SetSingleStringValue@JsonObjectProperty@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::SetSingleStringValue(HSTRING__ *)
0x18010e2dd  mov     esi, eax
0x18010e2df  test    eax, eax
0x18010e2e1  jns     short loc_18010E2ED
0x18010e2e3  mov     edx, 2D1h
0x18010e2e8  jmp     loc_18010E1F7
0x18010e2ed  lea     rdx, [rbp+57h+var_A0]; struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *
0x18010e2f1  mov     rcx, r15; this
0x18010e2f4  call    ?AddSystemDefinedProperty@JsonObjectWriter@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJAEBVJsonObjectProperty@23456@@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter::AddSystemDefinedProperty(Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty const &)
0x18010e2f9  mov     esi, eax
0x18010e2fb  test    eax, eax
0x18010e2fd  jns     short loc_18010E309
0x18010e2ff  mov     edx, 2D2h
0x18010e304  jmp     loc_18010E1F7
0x18010e309  lea     rdx, aAccountpicture_0; "AccountPictureRevisionNumber"
0x18010e310  lea     rcx, [rbp+57h+var_70]; string
0x18010e314  call    ??$?0$0BN@@StringReference@Internal@Windows@@QEAA@AEAY0BN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[29])
0x18010e319  mov     byte ptr [rsp+0D0h+var_B0], r12b
0x18010e31e  xor     r9d, r9d
0x18010e321  mov     r8, [rax]
0x18010e324  xor     edx, edx
0x18010e326  lea     rcx, [rbp+57h+var_A0]
0x18010e32a  call    ?Initialize@JsonObjectProperty@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJW4SerializedPropertyType@23456@PEAUHSTRING__@@_N2@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::Initialize(Windows::Internal::Security::Authentication::TokenBroker::SerializedPropertyType,HSTRING__ *,bool,bool)
0x18010e32f  mov     esi, eax
0x18010e331  test    eax, eax
0x18010e333  jns     short loc_18010E33F
0x18010e335  mov     edx, 2D9h
0x18010e33a  jmp     loc_18010E1F7
0x18010e33f  mov     rdx, [r14+40h]; HSTRING
0x18010e343  lea     rcx, [rbp+57h+var_A0]; this
0x18010e347  call    ?SetSingleStringValue@JsonObjectProperty@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::SetSingleStringValue(HSTRING__ *)
0x18010e34c  mov     esi, eax
0x18010e34e  test    eax, eax
0x18010e350  jns     short loc_18010E35C
0x18010e352  mov     edx, 2DAh
0x18010e357  jmp     loc_18010E1F7
0x18010e35c  lea     rdx, [rbp+57h+var_A0]; struct Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *
0x18010e360  mov     rcx, r15; this
0x18010e363  call    ?AddSystemDefinedProperty@JsonObjectWriter@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJAEBVJsonObjectProperty@23456@@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectWriter::AddSystemDefinedProperty(Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty const &)
0x18010e368  mov     esi, eax
0x18010e36a  test    eax, eax
0x18010e36c  jns     short loc_18010E378
0x18010e36e  mov     edx, 2DBh
0x18010e373  jmp     loc_18010E1F7
0x18010e378  mov     rcx, [r14+48h]; string
0x18010e37c  call    cs:__imp_WindowsIsStringEmpty
0x18010e382  test    eax, eax
0x18010e384  jnz     short loc_18010E3F5
0x18010e386  lea     rdx, aPeruseraccount; "PerUserAccountId"
0x18010e38d  lea     rcx, [rbp+57h+var_70]; string
0x18010e391  call    ??$?0$0BB@@StringReference@Internal@Windows@@QEAA@AEAY0BB@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[17])
0x18010e396  mov     byte ptr [rsp+0D0h+var_B0], r12b
0x18010e39b  xor     r9d, r9d
0x18010e39e  mov     r8, [rax]
0x18010e3a1  xor     edx, edx
0x18010e3a3  lea     rcx, [rbp+57h+var_A0]
0x18010e3a7  call    ?Initialize@JsonObjectProperty@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJW4SerializedPropertyType@23456@PEAUHSTRING__@@_N2@Z; Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::Initialize(Windows::Internal::Security::Authentication::TokenBroker::SerializedPropertyType,HSTRING__ *,bool,bool)
0x18010e3ac  mov     esi, eax
  ... truncated ...
```
