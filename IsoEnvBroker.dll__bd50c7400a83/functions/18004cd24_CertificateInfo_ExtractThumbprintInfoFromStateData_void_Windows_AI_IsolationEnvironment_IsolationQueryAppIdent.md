# CertificateInfo::ExtractThumbprintInfoFromStateData(void *,Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus &,CertificateInfo &)

- ea: `0x18004cd24`
- end: `0x18004cefe`
- name: `?ExtractThumbprintInfoFromStateData@CertificateInfo@@CAJPEAXAEAW4IsolationQueryAppIdentityStatus@IsolationEnvironment@AI@Windows@@AEAV1@@Z`
- size: `474`
- prototype: `__int64 __fastcall(HANDLE hStateData, enum Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus *, struct CertificateInfo *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18004d9fc`

## callees

- `0x180002520`
- `0x18001045c`
- `0x180011e18`
- `0x180013230`
- `0x1800214c4`
- `0x1800366b4`
- `0x18004c958`
- `0x18004cb8c`
- `0x18004cc34`
- `0x18004cd24`

## import_xrefs

- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x18004cd88`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x18004cd88`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x18004cda9`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x18004cda9`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x18004cd61`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x18004cd61`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18004cdde`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18004ce2f`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18004cdde`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18004ce2f`

## string_xrefs

- `0x18004cdf7`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\certificateinfo.cpp`
- `0x18004ce48`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\certificateinfo.cpp`
- `0x18004ced0`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\certificateinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CertificateInfo::ExtractThumbprintInfoFromStateData(
        HANDLE hStateData,
        enum Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus *a2,
        struct CertificateInfo *a3)
{
  CRYPT_PROVIDER_DATA *v6; // rax
  const char *v7; // rax
  __int64 v8; // rdx
  CRYPT_PROVIDER_SGNR *ProvSignerFromChain; // rax
  CRYPT_PROVIDER_CERT *ProvCertFromChain; // rax
  CRYPT_PROVIDER_CERT *v11; // rbx
  unsigned int LastErrorMsg; // ebx
  __int64 v14; // rax
  _QWORD *v15; // rbx
  const char *v16; // [rsp+20h] [rbp-78h]
  const char *v17; // [rsp+28h] [rbp-70h]
  DWORD pcbData; // [rsp+30h] [rbp-68h] BYREF
  void *pvData[3]; // [rsp+38h] [rbp-60h] BYREF
  char *v20[4]; // [rsp+50h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  Log(
    4u,
    L"[QueryAppIdentity] Checking if the certificate is Windows signed and getting the thumbprint from the state data.");
  *(_DWORD *)a2 = 5;
  v6 = WTHelperProvDataFromStateData(hStateData);
  if ( !v6 )
  {
    v7 = "[QueryAppIdentity] Failed to get provider data from state data.";
    v8 = 357;
LABEL_16:
    LastErrorMsg = -2147467259;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\certificateinfo.cpp",
      (const char *)0x80004005LL,
      (int)v7,
      v17);
    return LastErrorMsg;
  }
  ProvSignerFromChain = WTHelperGetProvSignerFromChain(v6, 0, 0, 0);
  if ( !ProvSignerFromChain )
  {
    v7 = "[QueryAppIdentity] Failed to get signer info from provider data.";
    v8 = 363;
    goto LABEL_16;
  }
  ProvCertFromChain = WTHelperGetProvCertFromChain(ProvSignerFromChain, 0);
  v11 = ProvCertFromChain;
  if ( !ProvCertFromChain || !ProvCertFromChain->pCert )
  {
    v7 = "[QueryAppIdentity] Failed to get certificate info from signer info.";
    v8 = 369;
    goto LABEL_16;
  }
  pcbData = 0;
  if ( !CertGetCertificateContextProperty(ProvCertFromChain->pCert, 3u, 0, &pcbData) )
    return wil::details::in1diag3::Return_GetLastErrorMsg(
             retaddr,
             (void *)0x178,
             (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\certificateinfo.cpp",
             "[QueryAppIdentity] Failed call to CertGetCertificateContextProperty to query thumbprint size.",
             v16);
  std::vector<unsigned char>::vector<unsigned char>(pvData, pcbData);
  if ( CertGetCertificateContextProperty(v11->pCert, 3u, pvData[0], &pcbData) )
  {
    v14 = BytesToHexString(v20, pvData);
    v15 = (_QWORD *)((char *)a3 + 8);
    std::wstring::operator=((char *)a3 + 8, v14);
    std::wstring::~wstring(v20);
    if ( *((_QWORD *)a3 + 4) > 7u )
      v15 = (_QWORD *)*v15;
    Log(4u, L"[QueryAppIdentity] Certificate thumbprint: %s", v15);
    *(_DWORD *)a2 = 0;
    LastErrorMsg = 0;
  }
  else
  {
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0x17F,
                     (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\certificateinfo.cpp",
                     "[QueryAppIdentity] Failed call to CertGetCertificateContextProperty to query thumbprint size.",
                     v16);
  }
  std::vector<unsigned char>::~vector<unsigned char>(pvData);
  return LastErrorMsg;
}

```

## disassembly

```asm
0x18004cd24  push    rbx
0x18004cd26  push    rsi
0x18004cd27  push    rdi
0x18004cd28  sub     rsp, 80h
0x18004cd2f  mov     rax, cs:__security_cookie
0x18004cd36  xor     rax, rsp
0x18004cd39  mov     [rsp+98h+var_28], rax
0x18004cd3e  mov     rsi, r8
0x18004cd41  mov     rdi, rdx
0x18004cd44  mov     rbx, rcx
0x18004cd47  lea     rdx, aQueryappidenti_11; "[QueryAppIdentity] Checking if the cert"...
0x18004cd4e  mov     ecx, 4; unsigned __int8
0x18004cd53  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18004cd58  mov     dword ptr [rdi], 5
0x18004cd5e  mov     rcx, rbx; hStateData
0x18004cd61  call    cs:__imp_WTHelperProvDataFromStateData
0x18004cd67  test    rax, rax
0x18004cd6a  jnz     short loc_18004CD7D
0x18004cd6c  lea     rax, aQueryappidenti_3; "[QueryAppIdentity] Failed to get provid"...
0x18004cd73  mov     edx, 165h
0x18004cd78  jmp     loc_18004CEC3
0x18004cd7d  xor     r9d, r9d; idxCounterSigner
0x18004cd80  xor     r8d, r8d; fCounterSigner
0x18004cd83  xor     edx, edx; idxSigner
0x18004cd85  mov     rcx, rax; pProvData
0x18004cd88  call    cs:__imp_WTHelperGetProvSignerFromChain
0x18004cd8e  test    rax, rax
0x18004cd91  jnz     short loc_18004CDA4
0x18004cd93  lea     rax, aQueryappidenti_12; "[QueryAppIdentity] Failed to get signer"...
0x18004cd9a  mov     edx, 16Bh
0x18004cd9f  jmp     loc_18004CEC3
0x18004cda4  xor     edx, edx; idxCert
0x18004cda6  mov     rcx, rax; pSgnr
0x18004cda9  call    cs:__imp_WTHelperGetProvCertFromChain
0x18004cdaf  mov     rbx, rax
0x18004cdb2  test    rax, rax
0x18004cdb5  jz      loc_18004CEB7
0x18004cdbb  cmp     qword ptr [rax+8], 0
0x18004cdc0  jz      loc_18004CEB7
0x18004cdc6  mov     [rsp+98h+pcbData], 0
0x18004cdce  lea     r9, [rsp+98h+pcbData]; pcbData
0x18004cdd3  xor     r8d, r8d; pvData
0x18004cdd6  lea     edx, [r8+3]; dwPropId
0x18004cdda  mov     rcx, [rax+8]; pCertContext
0x18004cdde  call    cs:__imp_CertGetCertificateContextProperty
0x18004cde4  test    eax, eax
0x18004cde6  jnz     short loc_18004CE0D
0x18004cde8  mov     rcx, [rsp+98h]; this
0x18004cdf0  lea     r9, aQueryappidenti_18; "[QueryAppIdentity] Failed call to CertG"...
0x18004cdf7  lea     r8, aOnecoreuapWind_16; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004cdfe  mov     edx, 178h; void *
0x18004ce03  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18004ce08  jmp     loc_18004CEE6
0x18004ce0d  mov     edx, [rsp+98h+pcbData]
0x18004ce11  lea     rcx, [rsp+98h+pvData]
0x18004ce16  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18004ce1b  nop
0x18004ce1c  lea     r9, [rsp+98h+pcbData]; pcbData
0x18004ce21  mov     r8, [rsp+98h+pvData]; pvData
0x18004ce26  mov     edx, 3; dwPropId
0x18004ce2b  mov     rcx, [rbx+8]; pCertContext
0x18004ce2f  call    cs:__imp_CertGetCertificateContextProperty
0x18004ce35  test    eax, eax
0x18004ce37  jnz     short loc_18004CE5D
0x18004ce39  mov     rcx, [rsp+98h]; this
0x18004ce41  lea     r9, aQueryappidenti_18; "[QueryAppIdentity] Failed call to CertG"...
0x18004ce48  lea     r8, aOnecoreuapWind_16; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004ce4f  mov     edx, 17Fh; void *
0x18004ce54  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18004ce59  mov     ebx, eax
0x18004ce5b  jmp     short loc_18004CEAB
0x18004ce5d  lea     rdx, [rsp+98h+pvData]
0x18004ce62  lea     rcx, [rsp+98h+var_48]
0x18004ce67  call    ?BytesToHexString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@EV?$allocator@E@std@@@2@@Z; BytesToHexString(std::vector<uchar> const &)
0x18004ce6c  lea     rbx, [rsi+8]
0x18004ce70  mov     rdx, rax
0x18004ce73  mov     rcx, rbx
0x18004ce76  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004ce7b  lea     rcx, [rsp+98h+var_48]
0x18004ce80  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004ce85  cmp     qword ptr [rbx+18h], 7
0x18004ce8a  jbe     short loc_18004CE8F
0x18004ce8c  mov     rbx, [rbx]
0x18004ce8f  mov     r8, rbx
0x18004ce92  lea     rdx, aQueryappidenti_16; "[QueryAppIdentity] Certificate thumbpri"...
0x18004ce99  mov     ecx, 4; unsigned __int8
0x18004ce9e  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18004cea3  mov     dword ptr [rdi], 0
0x18004cea9  xor     ebx, ebx
0x18004ceab  lea     rcx, [rsp+98h+pvData]
0x18004ceb0  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18004ceb5  jmp     short loc_18004CEE4
0x18004ceb7  lea     rax, aQueryappidenti_8; "[QueryAppIdentity] Failed to get certif"...
0x18004cebe  mov     edx, 171h; void *
0x18004cec3  mov     ebx, 80004005h
0x18004cec8  mov     qword ptr [rsp+98h+var_78], rax; int
0x18004cecd  mov     r9d, ebx; char *
0x18004ced0  lea     r8, aOnecoreuapWind_16; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004ced7  mov     rcx, [rsp+98h]; this
0x18004cedf  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004cee4  mov     eax, ebx
0x18004cee6  mov     rcx, [rsp+98h+var_28]
0x18004ceeb  xor     rcx, rsp; StackCookie
0x18004ceee  call    __security_check_cookie
0x18004cef3  add     rsp, 80h
0x18004cefa  pop     rdi
0x18004cefb  pop     rsi
0x18004cefc  pop     rbx
0x18004cefd  retn
```
