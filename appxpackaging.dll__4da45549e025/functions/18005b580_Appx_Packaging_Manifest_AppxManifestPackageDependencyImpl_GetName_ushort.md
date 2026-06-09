# Appx::Packaging::Manifest::AppxManifestPackageDependencyImpl::GetName(ushort * *)

- ea: `0x18005b580`
- end: `0x18005b6e6`
- name: `?GetName@AppxManifestPackageDependencyImpl@Manifest@Packaging@Appx@@UEAAJPEAPEAG@Z`
- size: `358`
- prototype: `__int64 __fastcall(Appx::Packaging::Manifest::AppxManifestPackageDependencyImpl *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800e3690`

## callees

- `0x18000f260`
- `0x180011cd0`
- `0x1800133fc`
- `0x18001711c`
- `0x18005b580`
- `0x180071f50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b622`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b622`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b632`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b641`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b69a`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b632`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b641`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b69a`

## string_xrefs

- `0x18005b661`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestdependencypackage.cpp`
- `0x18005b682`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestdependencypackage.cpp`
- `0x18005b6ac`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestdependencypackage.cpp`
- `0x18005b6c9`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestdependencypackage.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestPackageDependencyImpl::GetName(
        Appx::Packaging::Manifest::AppxManifestPackageDependencyImpl *this,
        unsigned __int16 **a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  OLECHAR *v6; // rbx
  int NodeValue; // eax
  unsigned int v8; // edi
  int v9; // eax
  BSTR v10; // rcx
  int v12; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  BSTR bstrString; // [rsp+58h] [rbp+28h] BYREF
  BSTR v15; // [rsp+60h] [rbp+30h] BYREF

  if ( !a2 )
  {
    v5 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestdependencypackage.cpp",
      (const char *)0x80004003LL,
      v12);
    return v5;
  }
  v15 = 0;
  v4 = Appx::Packaging::BuildXPath(4, L"Name", &v15);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestdependencypackage.cpp",
      (const char *)(unsigned int)v4,
      v12);
    SysFreeString(v15);
    return v5;
  }
  v6 = v15;
  bstrString = 0;
  NodeValue = Appx::Packaging::GetNodeValue((char *)this + 48, v15, 2147549183LL, &bstrString);
  v8 = NodeValue;
  if ( NodeValue < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestdependencypackage.cpp",
      (const char *)(unsigned int)NodeValue,
      0);
  }
  else
  {
    v15 = 0;
    v9 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoCoTaskMemStringAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoCoTaskMemStringDeallocate(unsigned short *)>::CopyFromBStr(
           (LPVOID *)&v15,
           bstrString);
    v8 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x49,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestdependencypackage.cpp",
        (const char *)(unsigned int)v9,
        0);
      v10 = v15;
    }
    else
    {
      v10 = 0;
      *a2 = v15;
    }
    CoTaskMemFree(v10);
  }
  SysFreeString(bstrString);
  SysFreeString(v6);
  return v8;
}

```

## disassembly

```asm
0x18005b580  mov     [rsp-18h+arg_0], rbx
0x18005b585  push    rbp
0x18005b586  push    rsi
0x18005b587  push    rdi
0x18005b588  mov     rbp, rsp
0x18005b58b  sub     rsp, 30h
0x18005b58f  mov     rsi, rdx
0x18005b592  mov     rdi, rcx
0x18005b595  test    rdx, rdx
0x18005b598  jz      loc_18005B65D
0x18005b59e  lea     r8, [rbp+arg_10]
0x18005b5a2  mov     [rbp+arg_10], 0
0x18005b5aa  lea     rdx, ?Name@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Name"
0x18005b5b1  mov     ecx, 4
0x18005b5b6  call    ?BuildXPath@Packaging@Appx@@YAJW4XPathComponentType@12@PEBGAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponentType,ushort const *,Common::AutoBStr &)
0x18005b5bb  mov     ebx, eax
0x18005b5bd  test    eax, eax
0x18005b5bf  js      loc_18005B67E
0x18005b5c5  mov     rbx, [rbp+arg_10]
0x18005b5c9  lea     rcx, [rdi+30h]
0x18005b5cd  mov     rdx, rbx
0x18005b5d0  mov     [rbp+bstrString], 0
0x18005b5d8  lea     r9, [rbp+bstrString]
0x18005b5dc  mov     qword ptr [rsp+30h+var_10], 0; int
0x18005b5e5  mov     r8d, 8000FFFFh
0x18005b5eb  call    ?GetNodeValue@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAGJPEAPEAGPEAPEAUIXMLDOMNode@@@Z; Appx::Packaging::GetNodeValue(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort *,long,ushort * *,IXMLDOMNode * *)
0x18005b5f0  mov     edi, eax
0x18005b5f2  test    eax, eax
0x18005b5f4  js      loc_18005B6A8
0x18005b5fa  mov     rdx, [rbp+bstrString]
0x18005b5fe  lea     rcx, [rbp+arg_10]
0x18005b602  mov     [rbp+arg_10], 0
0x18005b60a  call    ?CopyFromBStr@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJQEAG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromBStr(ushort * const)
0x18005b60f  mov     edi, eax
0x18005b611  test    eax, eax
0x18005b613  js      loc_18005B6C5
0x18005b619  mov     rax, [rbp+arg_10]
0x18005b61d  xor     ecx, ecx; pv
0x18005b61f  mov     [rsi], rax
0x18005b622  call    cs:__imp_CoTaskMemFree
0x18005b629  nop     dword ptr [rax+rax+00h]
0x18005b62e  mov     rcx, [rbp+bstrString]; bstrString
0x18005b632  call    cs:__imp_SysFreeString
0x18005b639  nop     dword ptr [rax+rax+00h]
0x18005b63e  mov     rcx, rbx; bstrString
0x18005b641  call    cs:__imp_SysFreeString
0x18005b648  nop     dword ptr [rax+rax+00h]
0x18005b64d  mov     eax, edi
0x18005b64f  mov     rbx, [rsp+30h+arg_0]
0x18005b654  add     rsp, 30h
0x18005b658  pop     rdi
0x18005b659  pop     rsi
0x18005b65a  pop     rbp
0x18005b65b  retn
0x18005b65d  mov     rcx, [rbp+18h]; this
0x18005b661  lea     r8, aOnecorePrintsc_56; "onecore\\printscan\\appxpackaging\\mani"...
0x18005b668  mov     ebx, 80004003h
0x18005b66d  mov     edx, 3Fh ; '?'; void *
0x18005b672  mov     r9d, ebx; char *
0x18005b675  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b67a  mov     eax, ebx
0x18005b67c  jmp     short loc_18005B64F
0x18005b67e  mov     rcx, [rbp+18h]; this
0x18005b682  lea     r8, aOnecorePrintsc_56; "onecore\\printscan\\appxpackaging\\mani"...
0x18005b689  mov     r9d, ebx; char *
0x18005b68c  mov     edx, 43h ; 'C'; void *
0x18005b691  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005b696  mov     rcx, [rbp+arg_10]; bstrString
0x18005b69a  call    cs:__imp_SysFreeString
0x18005b6a1  nop     dword ptr [rax+rax+00h]
0x18005b6a6  jmp     short loc_18005B67A
0x18005b6a8  mov     rcx, [rbp+18h]; this
0x18005b6ac  lea     r8, aOnecorePrintsc_56; "onecore\\printscan\\appxpackaging\\mani"...
0x18005b6b3  mov     r9d, edi; char *
0x18005b6b6  mov     edx, 46h ; 'F'; void *
0x18005b6bb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005b6c0  jmp     loc_18005B62E
0x18005b6c5  mov     rcx, [rbp+18h]; this
0x18005b6c9  lea     r8, aOnecorePrintsc_56; "onecore\\printscan\\appxpackaging\\mani"...
0x18005b6d0  mov     r9d, edi; char *
0x18005b6d3  mov     edx, 49h ; 'I'; void *
0x18005b6d8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005b6dd  mov     rcx, [rbp+arg_10]
0x18005b6e1  jmp     loc_18005B622
```
