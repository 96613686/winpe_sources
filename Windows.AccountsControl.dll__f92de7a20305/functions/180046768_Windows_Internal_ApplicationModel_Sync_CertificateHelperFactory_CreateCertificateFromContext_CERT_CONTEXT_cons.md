# Windows::Internal::ApplicationModel::Sync::CertificateHelperFactory::CreateCertificateFromContext(_CERT_CONTEXT const *,Windows::Security::Cryptography::Certificates::ICertificate * *)

- ea: `0x180046768`
- end: `0x1800468ab`
- name: `?CreateCertificateFromContext@CertificateHelperFactory@Sync@ApplicationModel@Internal@Windows@@CAJPEBU_CERT_CONTEXT@@PEAPEAUICertificate@Certificates@Cryptography@Security@5@@Z`
- size: `323`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *, struct Windows::Security::Cryptography::Certificates::ICertificate **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180047b8c`

## callees

- `0x180006eac`
- `0x180011ffc`
- `0x180046768`
- `0x180046c5c`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800467c7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800467c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800467ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800467ae`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800467e8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800467e8`

## string_xrefs

- `0x1800467a7`: `Windows.Security.Cryptography.Certificates.Certificate`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::ApplicationModel::Sync::CertificateHelperFactory::CreateCertificateFromContext(
        const struct _CERT_CONTEXT *a1,
        struct Windows::Security::Cryptography::Certificates::ICertificate **a2)
{
  HSTRING v4; // rbx
  int ActivationFactory; // eax
  unsigned int v6; // ebx
  int CertBufferFromCertContext; // eax
  __int64 v8; // rdx
  struct Windows::Storage::Streams::IBuffer *v10; // [rsp+20h] [rbp-40h] BYREF
  __int64 v11; // [rsp+28h] [rbp-38h] BYREF
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  *a2 = 0;
  v11 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Security.Cryptography.Certificates.Certificate",
         0x36u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v4 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_17b4221c_4baf_44a2_9608_04fb62b16942, &v11);
  v6 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v10 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
    CertBufferFromCertContext = Windows::Internal::ApplicationModel::Sync::CertificateHelperFactory::GetCertBufferFromCertContext(
                                  a1,
                                  &v10);
    v6 = CertBufferFromCertContext;
    if ( CertBufferFromCertContext >= 0 )
    {
      CertBufferFromCertContext = (*(__int64 (__fastcall **)(__int64, struct Windows::Storage::Streams::IBuffer *, struct Windows::Security::Cryptography::Certificates::ICertificate **))(*(_QWORD *)v11 + 48LL))(
                                    v11,
                                    v10,
                                    a2);
      v6 = CertBufferFromCertContext;
      if ( CertBufferFromCertContext >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
        v6 = 0;
        goto LABEL_11;
      }
      v8 = 294;
    }
    else
    {
      v8 = 293;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\certificatehelper.cpp",
      (const char *)(unsigned int)CertBufferFromCertContext,
      (int)v10);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x122,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\certificatehelper.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)v10);
  }
LABEL_11:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
  return v6;
}

```

## disassembly

```asm
0x180046768  mov     [rsp-18h+arg_10], rbx
0x18004676d  push    rbp
0x18004676e  push    rsi
0x18004676f  push    rdi
0x180046770  mov     rbp, rsp
0x180046773  sub     rsp, 60h
0x180046777  mov     rax, cs:__security_cookie
0x18004677e  xor     rax, rsp
0x180046781  mov     [rbp+var_10], rax
0x180046785  mov     rsi, rdx
0x180046788  mov     rdi, rcx
0x18004678b  mov     qword ptr [rdx], 0
0x180046792  mov     [rbp+var_38], 0
0x18004679a  lea     r9, [rbp+string]; string
0x18004679e  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800467a2  mov     edx, 36h ; '6'; length
0x1800467a7  lea     rcx, ?RuntimeClass_Windows_Security_Cryptography_Certificates_Certificate@@3QBGB; "Windows.Security.Cryptography.Certifica"...
0x1800467ae  call    cs:__imp_WindowsCreateStringReference
0x1800467b4  test    eax, eax
0x1800467b6  jns     short loc_1800467CD
0x1800467b8  xor     r9d, r9d; lpArguments
0x1800467bb  xor     r8d, r8d; nNumberOfArguments
0x1800467be  lea     edx, [r9+1]; dwExceptionFlags
0x1800467c2  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800467c7  call    cs:__imp_RaiseException
0x1800467cd  mov     rbx, [rbp+string]
0x1800467d1  lea     rcx, [rbp+var_38]
0x1800467d5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800467da  lea     r8, [rbp+var_38]
0x1800467de  lea     rdx, _GUID_17b4221c_4baf_44a2_9608_04fb62b16942
0x1800467e5  mov     rcx, rbx
0x1800467e8  call    cs:__imp_RoGetActivationFactory
0x1800467ee  mov     ebx, eax
0x1800467f0  test    eax, eax
0x1800467f2  jns     short loc_18004680E
0x1800467f4  mov     rcx, [rbp+18h]; this
0x1800467f8  mov     r9d, eax; char *
0x1800467fb  lea     r8, aOnecoreuapShel_20; "onecoreuap\\shell\\accountscontrol\\api"...
0x180046802  mov     edx, 122h; void *
0x180046807  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004680c  jmp     short loc_180046884
0x18004680e  mov     [rbp+var_40], 0
0x180046816  lea     rcx, [rbp+var_40]
0x18004681a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004681f  lea     rdx, [rbp+var_40]; struct Windows::Storage::Streams::IBuffer **
0x180046823  mov     rcx, rdi; struct _CERT_CONTEXT *
0x180046826  call    ?GetCertBufferFromCertContext@CertificateHelperFactory@Sync@ApplicationModel@Internal@Windows@@CAJPEBU_CERT_CONTEXT@@PEAPEAUIBuffer@Streams@Storage@5@@Z; Windows::Internal::ApplicationModel::Sync::CertificateHelperFactory::GetCertBufferFromCertContext(_CERT_CONTEXT const *,Windows::Storage::Streams::IBuffer * *)
0x18004682b  mov     ebx, eax
0x18004682d  test    eax, eax
0x18004682f  jns     short loc_180046855
0x180046831  mov     edx, 125h; void *
0x180046836  lea     r8, aOnecoreuapShel_20; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004683d  mov     r9d, eax; char *
0x180046840  mov     rcx, [rbp+18h]; this
0x180046844  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046849  nop
0x18004684a  lea     rcx, [rbp+var_40]
0x18004684e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046853  jmp     short loc_180046884
0x180046855  mov     rcx, [rbp+var_38]
0x180046859  mov     rax, [rcx]
0x18004685c  mov     r8, rsi
0x18004685f  mov     rdx, [rbp+var_40]
0x180046863  mov     rax, [rax+30h]
0x180046867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004686c  mov     ebx, eax
0x18004686e  test    eax, eax
0x180046870  jns     short loc_180046879
0x180046872  mov     edx, 126h
0x180046877  jmp     short loc_180046836
0x180046879  lea     rcx, [rbp+var_40]
0x18004687d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046882  xor     ebx, ebx
0x180046884  lea     rcx, [rbp+var_38]
0x180046888  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004688d  mov     eax, ebx
0x18004688f  mov     rcx, [rbp+var_10]
0x180046893  xor     rcx, rsp; StackCookie
0x180046896  call    __security_check_cookie
0x18004689b  mov     rbx, [rsp+60h+arg_10]
0x1800468a3  add     rsp, 60h
0x1800468a7  pop     rdi
0x1800468a8  pop     rsi
0x1800468a9  pop     rbp
0x1800468aa  retn
```
