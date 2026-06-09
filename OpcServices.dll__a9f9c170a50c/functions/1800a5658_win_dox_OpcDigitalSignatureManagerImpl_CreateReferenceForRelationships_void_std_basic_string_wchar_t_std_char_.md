# win_dox::OpcDigitalSignatureManagerImpl::CreateReferenceForRelationships(void *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> const &,_CRYPT_XML_ALGORITHM const &,_CRYPT_XML_ALGORITHM *,win_dox::OpcSignatureRelationshipReference const &)

- ea: `0x1800a5658`
- end: `0x1800a5774`
- name: `?CreateReferenceForRelationships@OpcDigitalSignatureManagerImpl@win_dox@@AEAAPEAXPEAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBU_CRYPT_XML_ALGORITHM@@PEAU5@AEBVOpcSignatureRelationshipReference@2@@Z`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800a4ae0`

## callees

- `0x180017dd0`
- `0x180018c2c`
- `0x180060af0`
- `0x1800a5658`
- `0x1800a577c`
- `0x1800a5a40`
- `0x180117740`

## import_xrefs

- `CRYPTXML!CryptXmlCreateReference` at `0x1800a5724`
- `CRYPTXML!CryptXmlCreateReference` at `0x1800a5724`

## string_xrefs

- `0x1800a56b1`: `http://schemas.openxmlformats.org/package/2006/RelationshipTransform`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HCRYPTXML __fastcall win_dox::OpcDigitalSignatureManagerImpl::CreateReferenceForRelationships(
        __int64 a1,
        void *a2,
        __int64 a3,
        const CRYPT_XML_ALGORITHM *a4,
        CRYPT_XML_ALGORITHM *rgTransform,
        __int64 a6)
{
  BYTE *v9; // rax
  const WCHAR *v10; // r9
  HRESULT Reference; // eax
  __int64 v12; // rdx
  const char *v13; // r8
  unsigned int v14; // r9d
  HCRYPTXML v15; // rbx
  __int64 v16; // rdx
  HCRYPTXML phReference[2]; // [rsp+50h] [rbp-49h] BYREF
  char v19[8]; // [rsp+60h] [rbp-39h] BYREF
  BYTE *v20; // [rsp+68h] [rbp-31h] BYREF
  ULONG v21; // [rsp+78h] [rbp-21h]
  unsigned __int64 v22; // [rsp+80h] [rbp-19h]
  char v23[8]; // [rsp+88h] [rbp-11h] BYREF
  __int16 v24; // [rsp+90h] [rbp-9h]
  __int64 v25; // [rsp+A0h] [rbp+7h]
  __int64 v26; // [rsp+A8h] [rbp+Fh]

  phReference[1] = (HCRYPTXML)-2LL;
  v26 = 7;
  v25 = 0;
  v24 = 0;
  win_dox::OpcSignatureRelationshipReferenceWriter::Write(a6, v23);
  rgTransform->wszAlgorithm = L"http://schemas.openxmlformats.org/package/2006/RelationshipTransform";
  win_musl::UnicodeWideToUnicode8(v19, v23);
  rgTransform->Encoded.cbData = v21;
  v9 = (BYTE *)&v20;
  if ( v22 >= 0x10 )
    v9 = v20;
  rgTransform->Encoded.pbData = v9;
  phReference[0] = 0;
  v10 = (const WCHAR *)(a3 + 8);
  if ( *(_QWORD *)(a3 + 32) >= 8u )
    v10 = *(const WCHAR **)v10;
  Reference = CryptXmlCreateReference(a2, 0, 0, v10, 0, a4, 2u, rgTransform, phReference);
  if ( Reference < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)Reference, v12, v13, v14);
  v15 = phReference[0];
  LOBYTE(v12) = 1;
  std::string::_Tidy(v19, v12, 0);
  LOBYTE(v16) = 1;
  std::wstring::_Tidy(v23, v16, 0);
  return v15;
}

```

## disassembly

```asm
0x1800a5658  push    rbp
0x1800a565a  push    rbx
0x1800a565b  push    rsi
0x1800a565c  push    rdi
0x1800a565d  push    r14
0x1800a565f  lea     rbp, [rsp-27h]
0x1800a5664  sub     rsp, 0C0h
0x1800a566b  mov     [rbp+47h+var_88], 0FFFFFFFFFFFFFFFEh
0x1800a5673  mov     rax, cs:__security_cookie
0x1800a567a  xor     rax, rsp
0x1800a567d  mov     [rbp+47h+var_30], rax
0x1800a5681  mov     r14, r9
0x1800a5684  mov     rbx, r8
0x1800a5687  mov     rsi, rdx
0x1800a568a  mov     rdi, [rbp+47h+arg_20]
0x1800a568e  mov     rcx, [rbp+47h+arg_28]
0x1800a5692  mov     [rbp+47h+var_38], 7
0x1800a569a  mov     [rbp+47h+var_40], 0
0x1800a56a2  xor     eax, eax
0x1800a56a4  mov     [rbp+47h+var_50], ax
0x1800a56a8  lea     rdx, [rbp+47h+var_58]
0x1800a56ac  call    ?Write@OpcSignatureRelationshipReferenceWriter@win_dox@@SAXAEBVOpcSignatureRelationshipReference@2@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_dox::OpcSignatureRelationshipReferenceWriter::Write(win_dox::OpcSignatureRelationshipReference const &,std::wstring *)
0x1800a56b1  lea     rax, ?gc_RelationshipTransform@Value@DigitalSignatures@win_musl@@3QB_WB; "http://schemas.openxmlformats.org/packa"...
0x1800a56b8  mov     [rdi+8], rax
0x1800a56bc  lea     rdx, [rbp+47h+var_58]
0x1800a56c0  lea     rcx, [rbp+47h+var_80]
0x1800a56c4  call    ?UnicodeWideToUnicode8@win_musl@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@3@@Z; win_musl::UnicodeWideToUnicode8(std::wstring const &)
0x1800a56c9  nop
0x1800a56ca  mov     eax, [rbp+47h+var_68]
0x1800a56cd  mov     [rdi+14h], eax
0x1800a56d0  lea     rax, [rbp+47h+var_78]
0x1800a56d4  cmp     [rbp+47h+var_60], 10h
0x1800a56d9  cmovnb  rax, [rbp+47h+var_78]
0x1800a56de  mov     [rdi+18h], rax
0x1800a56e2  mov     [rbp+47h+var_90], 0
0x1800a56ea  lea     r9, [rbx+8]
0x1800a56ee  cmp     qword ptr [rbx+20h], 8
0x1800a56f3  jb      short loc_1800A56F8
0x1800a56f5  mov     r9, [r9]; wszURI
0x1800a56f8  lea     rax, [rbp+47h+var_90]
0x1800a56fc  mov     [rsp+0E0h+phReference], rax; phReference
0x1800a5701  mov     [rsp+0E0h+rgTransform], rdi; rgTransform
0x1800a5706  mov     [rsp+0E0h+cTransform], 2; cTransform
0x1800a570e  mov     [rsp+0E0h+pDigestMethod], r14; pDigestMethod
0x1800a5713  mov     [rsp+0E0h+wszType], 0; wszType
0x1800a571c  xor     r8d, r8d; wszId
0x1800a571f  xor     edx, edx; dwFlags
0x1800a5721  mov     rcx, rsi; hCryptXml
0x1800a5724  call    cs:__imp_CryptXmlCreateReference
0x1800a572a  test    eax, eax
0x1800a572c  jns     short loc_1800A5736
0x1800a572e  mov     ecx, eax; this
0x1800a5730  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800a5736  mov     rbx, [rbp+47h+var_90]
0x1800a573a  xor     r8d, r8d
0x1800a573d  mov     dl, 1
0x1800a573f  lea     rcx, [rbp+47h+var_80]
0x1800a5743  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x1800a5748  nop
0x1800a5749  xor     r8d, r8d
0x1800a574c  mov     dl, 1
0x1800a574e  lea     rcx, [rbp+47h+var_58]
0x1800a5752  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800a5757  mov     rax, rbx
0x1800a575a  mov     rcx, [rbp+47h+var_30]
0x1800a575e  xor     rcx, rsp; StackCookie
0x1800a5761  call    __security_check_cookie
0x1800a5766  add     rsp, 0C0h
0x1800a576d  pop     r14
0x1800a576f  pop     rdi
0x1800a5770  pop     rsi
0x1800a5771  pop     rbx
0x1800a5772  pop     rbp
0x1800a5773  retn
```
