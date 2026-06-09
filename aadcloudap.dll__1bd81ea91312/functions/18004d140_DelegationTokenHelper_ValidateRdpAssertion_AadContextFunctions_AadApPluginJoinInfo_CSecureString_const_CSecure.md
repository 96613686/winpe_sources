# DelegationTokenHelper::ValidateRdpAssertion(AadContextFunctions *,_AadApPluginJoinInfo *,CSecureString const &,CSecureString &,CSecureString &,CSecureString &)

- ea: `0x18004d140`
- end: `0x18004d6f3`
- name: `?ValidateRdpAssertion@DelegationTokenHelper@@CAJPEAVAadContextFunctions@@PEAU_AadApPluginJoinInfo@@AEBVCSecureString@@AEAV4@33@Z`
- size: `1459`
- prototype: `__int64 __fastcall(struct AadContextFunctions *this, struct _AadApPluginJoinInfo *, const struct CSecureString *, struct CSecureString *, struct CSecureString *, struct CSecureString *)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004c88c`

## callees

- `0x1800063f4`
- `0x1800067f4`
- `0x1800069c0`
- `0x180006ac4`
- `0x180007bec`
- `0x1800090d0`
- `0x18000a300`
- `0x18003ad60`
- `0x18004b5a4`
- `0x18004b898`
- `0x18004b8c0`
- `0x18004c174`
- `0x18004cde4`
- `0x18004d140`
- `0x18004db1c`
- `0x180071e14`
- `0x180076758`
- `0x180076f14`
- `0x180077b34`
- `0x18007cdac`

## import_xrefs

- `ncrypt!NCryptVerifySignature` at `0x18004d5b9`
- `ncrypt!NCryptVerifySignature` at `0x18004d5b9`
- `ncrypt!NCryptFreeObject` at `0x18004d663`
- `ncrypt!NCryptFreeObject` at `0x18004d673`
- `ncrypt!NCryptFreeObject` at `0x18004d663`
- `ncrypt!NCryptFreeObject` at `0x18004d673`
- `ncrypt!NCryptOpenStorageProvider` at `0x18004d503`
- `ncrypt!NCryptOpenStorageProvider` at `0x18004d503`

## string_xrefs

- `0x18004d1e8`: `DelegationTokenHelper::ValidateRdpAssertion`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall DelegationTokenHelper::ValidateRdpAssertion(
        struct AadContextFunctions *this,
        struct _AadApPluginJoinInfo *a2,
        const struct CSecureString *a3,
        struct CSecureString *a4,
        struct CSecureString *a5,
        struct CSecureString *a6)
{
  SECURITY_STATUS v10; // ecx
  struct CSecureString *v11; // rsi
  int v12; // esi
  int v13; // eax
  int v14; // r14d
  __int64 *v15; // rax
  __int64 *v16; // rax
  __int64 *v17; // rax
  __int64 v18; // r9
  unsigned int v19; // ebx
  PBYTE pbSignature; // [rsp+20h] [rbp-B9h]
  DWORD dwFlags[2]; // [rsp+30h] [rbp-A9h]
  const WCHAR *pPaddingInfo; // [rsp+50h] [rbp-89h] BYREF
  NCRYPT_KEY_HANDLE hKey; // [rsp+58h] [rbp-81h] BYREF
  char v25[8]; // [rsp+60h] [rbp-79h] BYREF
  char v26[8]; // [rsp+68h] [rbp-71h] BYREF
  char v27[8]; // [rsp+70h] [rbp-69h] BYREF
  char v28[8]; // [rsp+78h] [rbp-61h] BYREF
  char v29[8]; // [rsp+80h] [rbp-59h] BYREF
  __int64 v30; // [rsp+88h] [rbp-51h] BYREF
  __int64 v31; // [rsp+90h] [rbp-49h] BYREF
  char v32[8]; // [rsp+98h] [rbp-41h] BYREF
  PBYTE pbHashValue[2]; // [rsp+A0h] [rbp-39h] BYREF
  PBYTE cbSignature[2]; // [rsp+B0h] [rbp-29h] BYREF
  __int128 v35; // [rsp+C0h] [rbp-19h] BYREF
  const char *v36[6]; // [rsp+D0h] [rbp-9h] BYREF
  SECURITY_STATUS v37; // [rsp+130h] [rbp+57h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+140h] [rbp+67h] BYREF

  v37 = 0;
  phProvider = 0;
  hKey = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v31);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v30);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v29);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v28);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v27);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v32);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v26);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v25);
  *(_OWORD *)pbHashValue = 0;
  *(_OWORD *)cbSignature = 0;
  v35 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v36,
    (int)"delegationtokenhelper.cpp",
    (int)"DelegationTokenHelper::ValidateRdpAssertion",
    (int)&v37);
  if ( !*(_DWORD *)(*(_QWORD *)a3 - 16LL) )
  {
    v10 = -2147024809;
    dwFlags[0] = 689;
LABEL_27:
    v37 = v10;
    goto LABEL_28;
  }
  v11 = a6;
  v10 = DelegationTokenHelper::ParseRdpAssertion(
          this,
          a3,
          (struct CSecureString *)v27,
          (struct CSecureString *)v32,
          a4,
          (struct CSecureString *)v26,
          (struct CSecureString *)v25,
          a5,
          a6);
  v37 = v10;
  if ( v10 >= 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EntraAdditionalRdpAssertionValidation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EntraAdditionalRdpAssertionValidation>::GetImpl'::`2'::impl)
      && !*(_DWORD *)(*(_QWORD *)v11 - 16LL) )
    {
      v10 = -2147187366;
      dwFlags[0] = 698;
      goto LABEL_27;
    }
    v10 = DelegationTokenHelper::ValidateNonce(this, a2, (const struct CSecureString *)v27);
    v37 = v10;
    if ( v10 >= 0 )
    {
      v12 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Find(
              a3,
              46,
              0);
      v13 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Find(
              a3,
              46,
              (unsigned int)(v12 + 1));
      v14 = v13;
      if ( v12 < 0 || v13 < 0 )
      {
        v10 = -2147187374;
        dwFlags[0] = 709;
        goto LABEL_27;
      }
      v15 = (__int64 *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
                         a3,
                         &pPaddingInfo,
                         0,
                         (unsigned int)v12);
      CSecureString::operator=((__int64)&v31, *v15);
      ATL::CStringData::Release((ATL::CStringData *)(pPaddingInfo - 12));
      v16 = (__int64 *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
                         a3,
                         &pPaddingInfo,
                         (unsigned int)(v12 + 1),
                         (unsigned int)(v14 - v12 - 1));
      CSecureString::operator=((__int64)&v30, *v16);
      ATL::CStringData::Release((ATL::CStringData *)(pPaddingInfo - 12));
      v17 = (__int64 *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
                         a3,
                         &pPaddingInfo,
                         (unsigned int)(v14 + 1));
      CSecureString::operator=((__int64)v29, *v17);
      ATL::CStringData::Release((ATL::CStringData *)(pPaddingInfo - 12));
      v10 = StringUtility::StringFormat(v28, L"%s.%s", v31, v30);
      if ( v10 >= 0 )
      {
        LOBYTE(pbSignature) = 1;
        v10 = StringUtility::EncodeString(this, v28, &v35, 65001, (_DWORD)pbSignature);
        v37 = v10;
        if ( v10 >= 0 )
        {
          v10 = CryptoHelper::ComputeSha256Hash(this, (struct _AP_BLOB *)&v35, (struct _AP_BLOB *)pbHashValue);
          v37 = v10;
          if ( v10 >= 0 )
          {
            LOBYTE(v18) = 1;
            v10 = StringUtility::Base64UrlDecode(this, v29, cbSignature, v18);
            v37 = v10;
            if ( v10 >= 0 )
            {
              v10 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Software Key Storage Provider", 0);
              v37 = v10;
              if ( v10 >= 0 )
              {
                v10 = DelegationTokenHelper::ImportPublicKey(
                        this,
                        phProvider,
                        (const struct CSecureString *)v26,
                        (const struct CSecureString *)v25,
                        &hKey);
                v37 = v10;
                if ( v10 >= 0 )
                {
                  pPaddingInfo = L"SHA256";
                  v10 = NCryptVerifySignature(
                          hKey,
                          &pPaddingInfo,
                          pbHashValue[1],
                          (DWORD)pbHashValue[0],
                          cbSignature[1],
                          (DWORD)cbSignature[0],
                          0x42u);
                  v37 = v10;
                  if ( v10 >= 0 )
                    goto LABEL_29;
                  dwFlags[0] = 740;
                }
                else
                {
                  dwFlags[0] = 727;
                }
              }
              else
              {
                dwFlags[0] = 725;
              }
            }
            else
            {
              dwFlags[0] = 723;
            }
          }
          else
          {
            dwFlags[0] = 721;
          }
        }
        else
        {
          dwFlags[0] = 719;
        }
      }
      else
      {
        dwFlags[0] = 717;
      }
    }
    else
    {
      dwFlags[0] = 702;
    }
  }
  else
  {
    dwFlags[0] = 692;
  }
LABEL_28:
  LODWORD(pbSignature) = v10;
  WPPTraceLogA(
    2,
    0,
    "%x 0x%08x %s:%u : %s:%ws",
    2,
    pbSignature,
    "delegationtokenhelper.cpp",
    *(_QWORD *)dwFlags,
    "HRESULT",
    &base);
LABEL_29:
  if ( this )
  {
    AadContextFunctions::LsaFreeApBlob(this, (struct _AP_BLOB *)pbHashValue);
    AadContextFunctions::LsaFreeApBlob(this, (struct _AP_BLOB *)cbSignature);
    AadContextFunctions::LsaFreeApBlob(this, (struct _AP_BLOB *)&v35);
  }
  if ( phProvider )
    NCryptFreeObject(phProvider);
  if ( hKey )
    NCryptFreeObject(hKey);
  v19 = v37;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v36);
  CSecureString::~CSecureString((CSecureString *)v25);
  CSecureString::~CSecureString((CSecureString *)v26);
  CSecureString::~CSecureString((CSecureString *)v32);
  CSecureString::~CSecureString((CSecureString *)v27);
  CSecureString::~CSecureString((CSecureString *)v28);
  CSecureString::~CSecureString((CSecureString *)v29);
  CSecureString::~CSecureString((CSecureString *)&v30);
  CSecureString::~CSecureString((CSecureString *)&v31);
  return v19;
}

```

## disassembly

```asm
0x18004d140  mov     [rsp-8+arg_8], rbx
0x18004d145  mov     [rsp-8+arg_18], rsi
0x18004d14a  push    rbp
0x18004d14b  push    rdi
0x18004d14c  push    r13
0x18004d14e  push    r14
0x18004d150  push    r15
0x18004d152  lea     rbp, [rsp-27h]
0x18004d157  sub     rsp, 100h
0x18004d15e  mov     r15, r9
0x18004d161  mov     rdi, r8
0x18004d164  mov     r14, rdx
0x18004d167  mov     rbx, rcx
0x18004d16a  mov     [rbp+47h+arg_0], 0
0x18004d171  mov     [rbp+47h+phProvider], 0
0x18004d179  mov     [rsp+120h+hKey], 0
0x18004d182  lea     rcx, [rbp+47h+var_90]; void *
0x18004d186  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004d18b  nop
0x18004d18c  lea     rcx, [rbp+47h+var_98]; void *
0x18004d190  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004d195  nop
0x18004d196  lea     rcx, [rbp+47h+var_A0]; void *
0x18004d19a  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004d19f  nop
0x18004d1a0  lea     rcx, [rbp+47h+var_A8]; void *
0x18004d1a4  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004d1a9  nop
0x18004d1aa  lea     rcx, [rbp+47h+var_B0]; void *
0x18004d1ae  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004d1b3  nop
0x18004d1b4  lea     rcx, [rbp+47h+var_88]; void *
0x18004d1b8  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004d1bd  nop
0x18004d1be  lea     rcx, [rbp+47h+var_B8]; void *
0x18004d1c2  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004d1c7  nop
0x18004d1c8  lea     rcx, [rbp+47h+var_C0]; void *
0x18004d1cc  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004d1d1  nop
0x18004d1d2  xorps   xmm0, xmm0
0x18004d1d5  movups  xmmword ptr [rbp+47h+pbHashValue], xmm0
0x18004d1d9  xorps   xmm1, xmm1
0x18004d1dc  movups  xmmword ptr [rbp+47h+var_70], xmm1
0x18004d1e0  movups  [rbp+47h+var_60], xmm0
0x18004d1e4  lea     r9, [rbp+47h+arg_0]
0x18004d1e8  lea     r8, aDelegationtoke_10; "DelegationTokenHelper::ValidateRdpAsser"...
0x18004d1ef  lea     r13, aOnecoreuapDsEx_26+21h; "delegationtokenhelper.cpp"
0x18004d1f6  mov     rdx, r13
0x18004d1f9  lea     rcx, [rbp+47h+var_50]
0x18004d1fd  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18004d202  nop
0x18004d203  mov     rax, [rdi]
0x18004d206  cmp     dword ptr [rax-10h], 0
0x18004d20a  jnz     short loc_18004D236
0x18004d20c  mov     ecx, 80070057h
0x18004d211  lea     rax, base
0x18004d218  mov     [rsp+120h+var_E0], rax
0x18004d21d  lea     rax, aHresult; "HRESULT"
0x18004d224  mov     [rsp+120h+var_E8], rax
0x18004d229  mov     [rsp+120h+dwFlags], 2B1h
0x18004d231  jmp     loc_18004D60F
0x18004d236  mov     rsi, [rbp+47h+arg_28]
0x18004d23a  mov     [rsp+120h+var_E0], rsi; struct CSecureString *
0x18004d23f  mov     rax, [rbp+47h+arg_20]
0x18004d243  mov     [rsp+120h+var_E8], rax; struct CSecureString *
0x18004d248  lea     rax, [rbp+47h+var_C0]
0x18004d24c  mov     qword ptr [rsp+120h+dwFlags], rax; struct CSecureString *
0x18004d251  lea     rax, [rbp+47h+var_B8]
0x18004d255  mov     qword ptr [rsp+120h+cbSignature], rax; struct CSecureString *
0x18004d25a  mov     [rsp+120h+pbSignature], r15; struct CSecureString *
0x18004d25f  lea     r9, [rbp+47h+var_88]; struct CSecureString *
0x18004d263  lea     r8, [rbp+47h+var_B0]; struct CSecureString *
0x18004d267  mov     rdx, rdi; struct CSecureString *
0x18004d26a  mov     rcx, rbx; this
0x18004d26d  call    ?ParseRdpAssertion@DelegationTokenHelper@@SAJPEAVAadContextFunctions@@AEBVCSecureString@@AEAV3@222222@Z; DelegationTokenHelper::ParseRdpAssertion(AadContextFunctions *,CSecureString const &,CSecureString &,CSecureString &,CSecureString &,CSecureString &,CSecureString &,CSecureString &,CSecureString &)
0x18004d272  mov     ecx, eax
0x18004d274  mov     [rbp+47h+arg_0], eax
0x18004d277  test    eax, eax
0x18004d279  jns     short loc_18004D2A0
0x18004d27b  lea     rax, base
0x18004d282  mov     [rsp+120h+var_E0], rax
0x18004d287  lea     rax, aHresult; "HRESULT"
0x18004d28e  mov     [rsp+120h+var_E8], rax
0x18004d293  mov     [rsp+120h+dwFlags], 2B4h
0x18004d29b  jmp     loc_18004D612
0x18004d2a0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EntraAdditionalRdpAssertionValidation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EntraAdditionalRdpAssertionValidation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EntraAdditionalRdpAssertionValidation> `wil::Feature<__WilFeatureTraits_Feature_EntraAdditionalRdpAssertionValidation>::GetImpl(void)'::`2'::impl
0x18004d2a7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EntraAdditionalRdpAssertionValidation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EntraAdditionalRdpAssertionValidation>::__private_IsEnabled(void)
0x18004d2ac  test    al, al
0x18004d2ae  jz      short loc_18004D2E3
0x18004d2b0  mov     rax, [rsi]
0x18004d2b3  cmp     dword ptr [rax-10h], 0
0x18004d2b7  jnz     short loc_18004D2E3
0x18004d2b9  mov     ecx, 8004855Ah
0x18004d2be  lea     rax, base
0x18004d2c5  mov     [rsp+120h+var_E0], rax
0x18004d2ca  lea     rax, aHresult; "HRESULT"
0x18004d2d1  mov     [rsp+120h+var_E8], rax
0x18004d2d6  mov     [rsp+120h+dwFlags], 2BAh
0x18004d2de  jmp     loc_18004D60F
0x18004d2e3  lea     r8, [rbp+47h+var_B0]; struct CSecureString *
0x18004d2e7  mov     rdx, r14; struct _AadApPluginJoinInfo *
0x18004d2ea  mov     rcx, rbx; this
0x18004d2ed  call    ?ValidateNonce@DelegationTokenHelper@@SAJPEAVAadContextFunctions@@PEAU_AadApPluginJoinInfo@@AEBVCSecureString@@@Z; DelegationTokenHelper::ValidateNonce(AadContextFunctions *,_AadApPluginJoinInfo *,CSecureString const &)
0x18004d2f2  mov     ecx, eax
0x18004d2f4  mov     [rbp+47h+arg_0], eax
0x18004d2f7  test    eax, eax
0x18004d2f9  jns     short loc_18004D320
0x18004d2fb  lea     rax, base
0x18004d302  mov     [rsp+120h+var_E0], rax
0x18004d307  lea     rax, aHresult; "HRESULT"
0x18004d30e  mov     [rsp+120h+var_E8], rax
0x18004d313  mov     [rsp+120h+dwFlags], 2BEh
0x18004d31b  jmp     loc_18004D612
0x18004d320  mov     r14d, 2Eh ; '.'
0x18004d326  mov     edx, r14d
0x18004d329  xor     r8d, r8d
0x18004d32c  mov     rcx, rdi
0x18004d32f  call    ?Find@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Find(ushort,int)
0x18004d334  mov     esi, eax
0x18004d336  mov     edx, r14d
0x18004d339  lea     r8d, [rax+1]
0x18004d33d  mov     rcx, rdi
0x18004d340  call    ?Find@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Find(ushort,int)
0x18004d345  mov     r14d, eax
0x18004d348  test    esi, esi
0x18004d34a  js      loc_18004D5EA
0x18004d350  test    eax, eax
0x18004d352  js      loc_18004D5EA
0x18004d358  mov     r9d, esi
0x18004d35b  xor     r8d, r8d
0x18004d35e  lea     rdx, [rsp+120h+pPaddingInfo]
0x18004d363  mov     rcx, rdi
0x18004d366  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x18004d36b  nop
0x18004d36c  mov     rdx, [rax]
0x18004d36f  lea     rcx, [rbp+47h+var_90]
0x18004d373  call    ??4CSecureString@@QEAAAEAV0@PEBG@Z; CSecureString::operator=(ushort const *)
0x18004d378  nop
0x18004d379  mov     rcx, [rsp+120h+pPaddingInfo]
0x18004d37e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004d382  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004d387  mov     r9d, r14d
0x18004d38a  sub     r9d, esi
0x18004d38d  dec     r9d
0x18004d390  lea     r8d, [rsi+1]
0x18004d394  lea     rdx, [rsp+120h+pPaddingInfo]
0x18004d399  mov     rcx, rdi
0x18004d39c  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x18004d3a1  nop
0x18004d3a2  mov     rdx, [rax]
0x18004d3a5  lea     rcx, [rbp+47h+var_98]
0x18004d3a9  call    ??4CSecureString@@QEAAAEAV0@PEBG@Z; CSecureString::operator=(ushort const *)
0x18004d3ae  nop
0x18004d3af  mov     rcx, [rsp+120h+pPaddingInfo]
0x18004d3b4  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004d3b8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004d3bd  lea     r8d, [r14+1]
0x18004d3c1  lea     rdx, [rsp+120h+pPaddingInfo]
0x18004d3c6  mov     rcx, rdi
0x18004d3c9  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int)
0x18004d3ce  nop
0x18004d3cf  mov     rdx, [rax]
0x18004d3d2  lea     rcx, [rbp+47h+var_A0]
0x18004d3d6  call    ??4CSecureString@@QEAAAEAV0@PEBG@Z; CSecureString::operator=(ushort const *)
0x18004d3db  nop
0x18004d3dc  mov     rcx, [rsp+120h+pPaddingInfo]
0x18004d3e1  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004d3e5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004d3ea  mov     r9, [rbp+47h+var_98]
0x18004d3ee  mov     r8, [rbp+47h+var_90]
0x18004d3f2  lea     rdx, aSS; "%s.%s"
0x18004d3f9  lea     rcx, [rbp+47h+var_A8]
0x18004d3fd  call    ?StringFormat@StringUtility@@SAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGZZ; StringUtility::StringFormat(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,...)
0x18004d402  mov     ecx, eax
0x18004d404  test    eax, eax
0x18004d406  jns     short loc_18004D42D
0x18004d408  lea     rax, base
0x18004d40f  mov     [rsp+120h+var_E0], rax
0x18004d414  lea     rax, aHresult; "HRESULT"
0x18004d41b  mov     [rsp+120h+var_E8], rax
0x18004d420  mov     [rsp+120h+dwFlags], 2CDh
0x18004d428  jmp     loc_18004D612
0x18004d42d  mov     byte ptr [rsp+120h+pbSignature], 1
0x18004d432  mov     r9d, 0FDE9h
0x18004d438  lea     r8, [rbp+47h+var_60]
0x18004d43c  lea     rdx, [rbp+47h+var_A8]
0x18004d440  mov     rcx, rbx
0x18004d443  call    ?EncodeString@StringUtility@@SAJPEAVAadContextFunctions@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAU_AP_BLOB@@I_N@Z; StringUtility::EncodeString(AadContextFunctions *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_AP_BLOB *,uint,bool)
0x18004d448  mov     ecx, eax
0x18004d44a  mov     [rbp+47h+arg_0], eax
0x18004d44d  test    eax, eax
0x18004d44f  jns     short loc_18004D476
0x18004d451  lea     rax, base
0x18004d458  mov     [rsp+120h+var_E0], rax
0x18004d45d  lea     rax, aHresult; "HRESULT"
0x18004d464  mov     [rsp+120h+var_E8], rax
0x18004d469  mov     [rsp+120h+dwFlags], 2CFh
0x18004d471  jmp     loc_18004D612
0x18004d476  lea     r8, [rbp+47h+pbHashValue]; struct _AP_BLOB *
0x18004d47a  lea     rdx, [rbp+47h+var_60]; struct _AP_BLOB *
0x18004d47e  mov     rcx, rbx; this
0x18004d481  call    ?ComputeSha256Hash@CryptoHelper@@SAJPEAVAadContextFunctions@@PEAU_AP_BLOB@@1@Z; CryptoHelper::ComputeSha256Hash(AadContextFunctions *,_AP_BLOB *,_AP_BLOB *)
0x18004d486  mov     ecx, eax
0x18004d488  mov     [rbp+47h+arg_0], eax
0x18004d48b  test    eax, eax
0x18004d48d  jns     short loc_18004D4B4
0x18004d48f  lea     rax, base
0x18004d496  mov     [rsp+120h+var_E0], rax
0x18004d49b  lea     rax, aHresult; "HRESULT"
0x18004d4a2  mov     [rsp+120h+var_E8], rax
0x18004d4a7  mov     [rsp+120h+dwFlags], 2D1h
0x18004d4af  jmp     loc_18004D612
0x18004d4b4  mov     r9b, 1
0x18004d4b7  lea     r8, [rbp+47h+var_70]
0x18004d4bb  lea     rdx, [rbp+47h+var_A0]
0x18004d4bf  mov     rcx, rbx
0x18004d4c2  call    ?Base64UrlDecode@StringUtility@@SAJPEAVAadContextFunctions@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAU_AP_BLOB@@_N@Z; StringUtility::Base64UrlDecode(AadContextFunctions *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_AP_BLOB *,bool)
0x18004d4c7  mov     ecx, eax
0x18004d4c9  mov     [rbp+47h+arg_0], eax
0x18004d4cc  test    eax, eax
0x18004d4ce  jns     short loc_18004D4F5
0x18004d4d0  lea     rax, base
0x18004d4d7  mov     [rsp+120h+var_E0], rax
0x18004d4dc  lea     rax, aHresult; "HRESULT"
0x18004d4e3  mov     [rsp+120h+var_E8], rax
0x18004d4e8  mov     [rsp+120h+dwFlags], 2D3h
0x18004d4f0  jmp     loc_18004D612
0x18004d4f5  xor     r8d, r8d; dwFlags
0x18004d4f8  lea     rdx, aMicrosoftSoftw; "Microsoft Software Key Storage Provider"
0x18004d4ff  lea     rcx, [rbp+47h+phProvider]; phProvider
0x18004d503  call    cs:__imp_NCryptOpenStorageProvider
0x18004d509  mov     ecx, eax
0x18004d50b  mov     [rbp+47h+arg_0], eax
0x18004d50e  test    eax, eax
0x18004d510  jns     short loc_18004D537
0x18004d512  lea     rax, base
0x18004d519  mov     [rsp+120h+var_E0], rax
0x18004d51e  lea     rax, aHresult; "HRESULT"
0x18004d525  mov     [rsp+120h+var_E8], rax
0x18004d52a  mov     [rsp+120h+dwFlags], 2D5h
0x18004d532  jmp     loc_18004D612
0x18004d537  lea     rax, [rsp+120h+hKey]
0x18004d53c  mov     [rsp+120h+pbSignature], rax; unsigned __int64 *
0x18004d541  lea     r9, [rbp+47h+var_C0]; struct CSecureString *
0x18004d545  lea     r8, [rbp+47h+var_B8]; struct CSecureString *
0x18004d549  mov     rdx, [rbp+47h+phProvider]; hProvider
0x18004d54d  mov     rcx, rbx; this
0x18004d550  call    ?ImportPublicKey@DelegationTokenHelper@@CAJPEAVAadContextFunctions@@_KAEBVCSecureString@@2PEA_K@Z; DelegationTokenHelper::ImportPublicKey(AadContextFunctions *,unsigned __int64,CSecureString const &,CSecureString const &,unsigned __int64 *)
0x18004d555  mov     ecx, eax
0x18004d557  mov     [rbp+47h+arg_0], eax
0x18004d55a  test    eax, eax
0x18004d55c  jns     short loc_18004D583
0x18004d55e  lea     rax, base
0x18004d565  mov     [rsp+120h+var_E0], rax
0x18004d56a  lea     rax, aHresult; "HRESULT"
0x18004d571  mov     [rsp+120h+var_E8], rax
0x18004d576  mov     [rsp+120h+dwFlags], 2D7h
0x18004d57e  jmp     loc_18004D612
0x18004d583  lea     rax, aSha256; "SHA256"
0x18004d58a  mov     [rsp+120h+pPaddingInfo], rax
0x18004d58f  mov     [rsp+120h+dwFlags], 42h ; 'B'; dwFlags
0x18004d597  mov     eax, dword ptr [rbp+47h+var_70]
0x18004d59a  mov     [rsp+120h+cbSignature], eax; cbSignature
0x18004d59e  mov     rax, [rbp+47h+var_70+8]
0x18004d5a2  mov     [rsp+120h+pbSignature], rax; pbSignature
0x18004d5a7  mov     r9d, dword ptr [rbp+47h+pbHashValue]; cbHashValue
0x18004d5ab  mov     r8, [rbp+47h+pbHashValue+8]; pbHashValue
0x18004d5af  lea     rdx, [rsp+120h+pPaddingInfo]; pPaddingInfo
0x18004d5b4  mov     rcx, [rsp+120h+hKey]; hKey
0x18004d5b9  call    cs:__imp_NCryptVerifySignature
0x18004d5bf  mov     ecx, eax
0x18004d5c1  mov     [rbp+47h+arg_0], eax
0x18004d5c4  test    eax, eax
0x18004d5c6  jns     short loc_18004D631
0x18004d5c8  lea     rax, base
0x18004d5cf  mov     [rsp+120h+var_E0], rax
0x18004d5d4  lea     rax, aHresult; "HRESULT"
0x18004d5db  mov     [rsp+120h+var_E8], rax
0x18004d5e0  mov     [rsp+120h+dwFlags], 2E4h
0x18004d5e8  jmp     short loc_18004D612
0x18004d5ea  mov     ecx, 80048552h
0x18004d5ef  lea     rax, base
0x18004d5f6  mov     [rsp+120h+var_E0], rax
0x18004d5fb  lea     rax, aHresult; "HRESULT"
0x18004d602  mov     [rsp+120h+var_E8], rax
0x18004d607  mov     [rsp+120h+dwFlags], 2C5h
0x18004d60f  mov     [rbp+47h+arg_0], ecx
0x18004d612  mov     qword ptr [rsp+120h+cbSignature], r13
0x18004d617  mov     dword ptr [rsp+120h+pbSignature], ecx
0x18004d61b  mov     ecx, 2
0x18004d620  mov     r9d, ecx
0x18004d623  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18004d62a  xor     edx, edx
0x18004d62c  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004d631  test    rbx, rbx
0x18004d634  jz      short loc_18004D65A
0x18004d636  lea     rdx, [rbp+47h+pbHashValue]; struct _AP_BLOB *
0x18004d63a  mov     rcx, rbx; this
0x18004d63d  call    ?LsaFreeApBlob@AadContextFunctions@@QEAAXPEAU_AP_BLOB@@@Z; AadContextFunctions::LsaFreeApBlob(_AP_BLOB *)
  ... truncated ...
```
