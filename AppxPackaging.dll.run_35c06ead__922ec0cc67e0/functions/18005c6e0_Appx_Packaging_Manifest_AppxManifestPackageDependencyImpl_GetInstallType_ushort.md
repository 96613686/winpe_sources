# Appx::Packaging::Manifest::AppxManifestPackageDependencyImpl::GetInstallType(ushort * *)

- ea: `0x18005c6e0`
- end: `0x18005c85a`
- name: `?GetInstallType@AppxManifestPackageDependencyImpl@Manifest@Packaging@Appx@@UEAAJPEAPEAG@Z`
- size: `378`
- prototype: `__int64 __fastcall(Appx::Packaging::Manifest::AppxManifestPackageDependencyImpl *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000f260`
- `0x180011cd0`
- `0x1800133fc`
- `0x18001711c`
- `0x18005c6e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005c82b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005c845`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005c82b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005c845`
- `OLEAUT32!__imp_SysFreeString` at `0x18005c764`
- `OLEAUT32!__imp_SysFreeString` at `0x18005c776`
- `OLEAUT32!__imp_SysFreeString` at `0x18005c7ae`
- `OLEAUT32!__imp_SysFreeString` at `0x18005c764`
- `OLEAUT32!__imp_SysFreeString` at `0x18005c776`
- `OLEAUT32!__imp_SysFreeString` at `0x18005c7ae`

## string_xrefs

- `0x18005c796`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestdependencypackage.cpp`
- `0x18005c7c0`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestdependencypackage.cpp`
- `0x18005c7da`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestdependencypackage.cpp`
- `0x18005c813`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestdependencypackage.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestPackageDependencyImpl::GetInstallType(
        Appx::Packaging::Manifest::AppxManifestPackageDependencyImpl *this,
        LPVOID *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  int NodeValue; // eax
  OLECHAR *v7; // rcx
  int v9; // eax
  int v10; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  BSTR bstrString; // [rsp+58h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+30h] BYREF
  BSTR v14; // [rsp+68h] [rbp+38h] BYREF

  if ( !a2 )
  {
    v5 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD8,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestdependencypackage.cpp",
      (const char *)0x80070057LL,
      v10);
    return v5;
  }
  *a2 = 0;
  v14 = 0;
  v4 = Appx::Packaging::BuildXPath(5, L"Type", &v14);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestdependencypackage.cpp",
      (const char *)(unsigned int)v4,
      v10);
    goto LABEL_6;
  }
  bstrString = 0;
  NodeValue = Appx::Packaging::GetNodeValue((char *)this + 16, v14, 0, &bstrString);
  v5 = NodeValue;
  if ( NodeValue < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDF,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestdependencypackage.cpp",
      (const char *)(unsigned int)NodeValue,
      0);
    goto LABEL_9;
  }
  v7 = bstrString;
  if ( bstrString )
  {
    pv = 0;
    v9 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoCoTaskMemStringAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoCoTaskMemStringDeallocate(unsigned short *)>::CopyFromBStr(
           &pv,
           bstrString);
    v5 = v9;
    if ( v9 >= 0 )
    {
      *a2 = pv;
      CoTaskMemFree(0);
      v7 = bstrString;
      goto LABEL_5;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE4,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestdependencypackage.cpp",
      (const char *)(unsigned int)v9,
      0);
    CoTaskMemFree(pv);
LABEL_9:
    SysFreeString(bstrString);
    goto LABEL_6;
  }
LABEL_5:
  SysFreeString(v7);
  v5 = 0;
LABEL_6:
  SysFreeString(v14);
  return v5;
}

```

## disassembly

```asm
0x18005c6e0  mov     [rsp-18h+arg_0], rbx
0x18005c6e5  push    rbp
0x18005c6e6  push    rsi
0x18005c6e7  push    rdi
0x18005c6e8  mov     rbp, rsp
0x18005c6eb  sub     rsp, 30h
0x18005c6ef  mov     rdi, rdx
0x18005c6f2  mov     rsi, rcx
0x18005c6f5  test    rdx, rdx
0x18005c6f8  jz      loc_18005C7D6
0x18005c6fe  mov     qword ptr [rdx], 0
0x18005c705  lea     r8, [rbp+arg_18]
0x18005c709  lea     rdx, ?Type@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Type"
0x18005c710  mov     [rbp+arg_18], 0
0x18005c718  mov     ecx, 5
0x18005c71d  call    ?BuildXPath@Packaging@Appx@@YAJW4XPathComponentType@12@PEBGAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponentType,ushort const *,Common::AutoBStr &)
0x18005c722  mov     ebx, eax
0x18005c724  test    eax, eax
0x18005c726  js      loc_18005C7BC
0x18005c72c  mov     rdx, [rbp+arg_18]
0x18005c730  lea     rcx, [rsi+10h]
0x18005c734  lea     r9, [rbp+bstrString]
0x18005c738  mov     [rbp+bstrString], 0
0x18005c740  xor     r8d, r8d
0x18005c743  mov     qword ptr [rsp+30h+var_10], 0; int
0x18005c74c  call    ?GetNodeValue@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAGJPEAPEAGPEAPEAUIXMLDOMNode@@@Z; Appx::Packaging::GetNodeValue(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort *,long,ushort * *,IXMLDOMNode * *)
0x18005c751  mov     ebx, eax
0x18005c753  test    eax, eax
0x18005c755  js      short loc_18005C792
0x18005c757  mov     rcx, [rbp+bstrString]; bstrString
0x18005c75b  test    rcx, rcx
0x18005c75e  jnz     loc_18005C7F5
0x18005c764  call    cs:__imp_SysFreeString
0x18005c76b  nop     dword ptr [rax+rax+00h]
0x18005c770  xor     ebx, ebx
0x18005c772  mov     rcx, [rbp+arg_18]; bstrString
0x18005c776  call    cs:__imp_SysFreeString
0x18005c77d  nop     dword ptr [rax+rax+00h]
0x18005c782  mov     eax, ebx
0x18005c784  mov     rbx, [rsp+30h+arg_0]
0x18005c789  add     rsp, 30h
0x18005c78d  pop     rdi
0x18005c78e  pop     rsi
0x18005c78f  pop     rbp
0x18005c790  retn
0x18005c792  mov     rcx, [rbp+18h]; this
0x18005c796  lea     r8, aOnecorePrintsc_56; "onecore\\printscan\\appxpackaging\\mani"...
0x18005c79d  mov     r9d, eax; char *
0x18005c7a0  mov     edx, 0DFh; void *
0x18005c7a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c7aa  mov     rcx, [rbp+bstrString]; bstrString
0x18005c7ae  call    cs:__imp_SysFreeString
0x18005c7b5  nop     dword ptr [rax+rax+00h]
0x18005c7ba  jmp     short loc_18005C772
0x18005c7bc  mov     rcx, [rbp+18h]; this
0x18005c7c0  lea     r8, aOnecorePrintsc_56; "onecore\\printscan\\appxpackaging\\mani"...
0x18005c7c7  mov     r9d, eax; char *
0x18005c7ca  mov     edx, 0DDh; void *
0x18005c7cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c7d4  jmp     short loc_18005C772
0x18005c7d6  mov     rcx, [rbp+18h]; this
0x18005c7da  lea     r8, aOnecorePrintsc_56; "onecore\\printscan\\appxpackaging\\mani"...
0x18005c7e1  mov     ebx, 80070057h
0x18005c7e6  mov     edx, 0D8h; void *
0x18005c7eb  mov     r9d, ebx; char *
0x18005c7ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c7f3  jmp     short loc_18005C782
0x18005c7f5  mov     rdx, rcx
0x18005c7f8  mov     [rbp+pv], 0
0x18005c800  lea     rcx, [rbp+pv]
0x18005c804  call    ?CopyFromBStr@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJQEAG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromBStr(ushort * const)
0x18005c809  mov     ebx, eax
0x18005c80b  test    eax, eax
0x18005c80d  jns     short loc_18005C83C
0x18005c80f  mov     rcx, [rbp+18h]; this
0x18005c813  lea     r8, aOnecorePrintsc_56; "onecore\\printscan\\appxpackaging\\mani"...
0x18005c81a  mov     r9d, eax; char *
0x18005c81d  mov     edx, 0E4h; void *
0x18005c822  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c827  mov     rcx, [rbp+pv]; pv
0x18005c82b  call    cs:__imp_CoTaskMemFree
0x18005c832  nop     dword ptr [rax+rax+00h]
0x18005c837  jmp     loc_18005C7AA
0x18005c83c  mov     rax, [rbp+pv]
0x18005c840  xor     ecx, ecx; pv
0x18005c842  mov     [rdi], rax
0x18005c845  call    cs:__imp_CoTaskMemFree
0x18005c84c  nop     dword ptr [rax+rax+00h]
0x18005c851  mov     rcx, [rbp+bstrString]
0x18005c855  jmp     loc_18005C764
```
