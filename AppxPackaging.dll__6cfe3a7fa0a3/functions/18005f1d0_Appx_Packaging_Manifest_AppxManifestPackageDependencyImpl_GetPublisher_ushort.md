# Appx::Packaging::Manifest::AppxManifestPackageDependencyImpl::GetPublisher(ushort * *)

- ea: `0x18005f1d0`
- end: `0x18005f32f`
- name: `?GetPublisher@AppxManifestPackageDependencyImpl@Manifest@Packaging@Appx@@UEAAJPEAPEAG@Z`
- size: `351`
- prototype: `__int64 __fastcall(Appx::Packaging::Manifest::AppxManifestPackageDependencyImpl *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800e36a0`

## callees

- `0x18000f260`
- `0x180011cd0`
- `0x1800133fc`
- `0x18001711c`
- `0x18005f1d0`
- `0x180071f50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f2eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f2eb`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f24b`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f304`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f313`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f24b`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f304`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f313`

## string_xrefs

- `0x18005f1ee`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestdependencypackage.cpp`
- `0x18005f233`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestdependencypackage.cpp`
- `0x18005f28b`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestdependencypackage.cpp`
- `0x18005f2c8`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestdependencypackage.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestPackageDependencyImpl::GetPublisher(
        Appx::Packaging::Manifest::AppxManifestPackageDependencyImpl *this,
        unsigned __int16 **a2)
{
  unsigned int v4; // ebx
  int v6; // eax
  OLECHAR *v7; // rbx
  int NodeValue; // eax
  unsigned int v9; // edi
  OLECHAR *v10; // rcx
  int v11; // eax
  BSTR v12; // rcx
  int v13; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  BSTR v15; // [rsp+58h] [rbp+28h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp+30h] BYREF

  if ( !a2 )
  {
    v4 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestdependencypackage.cpp",
      (const char *)0x80004003LL,
      v13);
    return v4;
  }
  bstrString = 0;
  v6 = Appx::Packaging::BuildXPath(4, L"Publisher", &bstrString);
  v4 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestdependencypackage.cpp",
      (const char *)(unsigned int)v6,
      v13);
    SysFreeString(bstrString);
    return v4;
  }
  v7 = bstrString;
  v15 = 0;
  NodeValue = Appx::Packaging::GetNodeValue((char *)this + 48, bstrString, 0, &v15);
  v9 = NodeValue;
  if ( NodeValue >= 0 )
  {
    v10 = v15;
    if ( !v15 )
    {
      *a2 = 0;
      goto LABEL_15;
    }
    bstrString = 0;
    v11 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoCoTaskMemStringAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoCoTaskMemStringDeallocate(unsigned short *)>::CopyFromBStr(
            (LPVOID *)&bstrString,
            v15);
    v9 = v11;
    if ( v11 >= 0 )
    {
      v12 = 0;
      *a2 = bstrString;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x64,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestdependencypackage.cpp",
        (const char *)(unsigned int)v11,
        0);
      v12 = bstrString;
    }
    CoTaskMemFree(v12);
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5F,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestdependencypackage.cpp",
      (const char *)(unsigned int)NodeValue,
      0);
  }
  v10 = v15;
LABEL_15:
  SysFreeString(v10);
  SysFreeString(v7);
  return v9;
}

```

## disassembly

```asm
0x18005f1d0  mov     [rsp-18h+arg_0], rbx
0x18005f1d5  push    rbp
0x18005f1d6  push    rsi
0x18005f1d7  push    rdi
0x18005f1d8  mov     rbp, rsp
0x18005f1db  sub     rsp, 30h
0x18005f1df  mov     rsi, rdx
0x18005f1e2  mov     rdi, rcx
0x18005f1e5  test    rdx, rdx
0x18005f1e8  jnz     short loc_18005F20C
0x18005f1ea  mov     rcx, [rbp+18h]; this
0x18005f1ee  lea     r8, aOnecorePrintsc_56; "onecore\\printscan\\appxpackaging\\mani"...
0x18005f1f5  mov     ebx, 80004003h
0x18005f1fa  lea     edx, [rsi+58h]; void *
0x18005f1fd  mov     r9d, ebx; char *
0x18005f200  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f205  mov     eax, ebx
0x18005f207  jmp     loc_18005F321
0x18005f20c  lea     r8, [rbp+bstrString]
0x18005f210  mov     [rbp+bstrString], 0
0x18005f218  lea     rdx, ?Publisher@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Publisher"
0x18005f21f  mov     ecx, 4
0x18005f224  call    ?BuildXPath@Packaging@Appx@@YAJW4XPathComponentType@12@PEBGAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponentType,ushort const *,Common::AutoBStr &)
0x18005f229  mov     ebx, eax
0x18005f22b  test    eax, eax
0x18005f22d  jns     short loc_18005F259
0x18005f22f  mov     rcx, [rbp+18h]; this
0x18005f233  lea     r8, aOnecorePrintsc_56; "onecore\\printscan\\appxpackaging\\mani"...
0x18005f23a  mov     r9d, eax; char *
0x18005f23d  mov     edx, 5Ch ; '\'; void *
0x18005f242  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005f247  mov     rcx, [rbp+bstrString]; bstrString
0x18005f24b  call    cs:__imp_SysFreeString
0x18005f252  nop     dword ptr [rax+rax+00h]
0x18005f257  jmp     short loc_18005F205
0x18005f259  mov     rbx, [rbp+bstrString]
0x18005f25d  lea     rcx, [rdi+30h]
0x18005f261  mov     rdx, rbx
0x18005f264  mov     [rbp+arg_8], 0
0x18005f26c  lea     r9, [rbp+arg_8]
0x18005f270  mov     qword ptr [rsp+30h+var_10], 0; int
0x18005f279  xor     r8d, r8d
0x18005f27c  call    ?GetNodeValue@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAGJPEAPEAGPEAPEAUIXMLDOMNode@@@Z; Appx::Packaging::GetNodeValue(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort *,long,ushort * *,IXMLDOMNode * *)
0x18005f281  mov     edi, eax
0x18005f283  test    eax, eax
0x18005f285  jns     short loc_18005F2A1
0x18005f287  mov     rcx, [rbp+18h]; this
0x18005f28b  lea     r8, aOnecorePrintsc_56; "onecore\\printscan\\appxpackaging\\mani"...
0x18005f292  mov     r9d, eax; char *
0x18005f295  mov     edx, 5Fh ; '_'; void *
0x18005f29a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005f29f  jmp     short loc_18005F2F7
0x18005f2a1  mov     rcx, [rbp+arg_8]; bstrString
0x18005f2a5  test    rcx, rcx
0x18005f2a8  jz      short loc_18005F2FD
0x18005f2aa  mov     rdx, rcx
0x18005f2ad  mov     [rbp+bstrString], 0
0x18005f2b5  lea     rcx, [rbp+bstrString]
0x18005f2b9  call    ?CopyFromBStr@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJQEAG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromBStr(ushort * const)
0x18005f2be  mov     edi, eax
0x18005f2c0  test    eax, eax
0x18005f2c2  jns     short loc_18005F2E2
0x18005f2c4  mov     rcx, [rbp+18h]; this
0x18005f2c8  lea     r8, aOnecorePrintsc_56; "onecore\\printscan\\appxpackaging\\mani"...
0x18005f2cf  mov     r9d, eax; char *
0x18005f2d2  mov     edx, 64h ; 'd'; void *
0x18005f2d7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005f2dc  mov     rcx, [rbp+bstrString]
0x18005f2e0  jmp     short loc_18005F2EB
0x18005f2e2  mov     rax, [rbp+bstrString]
0x18005f2e6  xor     ecx, ecx; pv
0x18005f2e8  mov     [rsi], rax
0x18005f2eb  call    cs:__imp_CoTaskMemFree
0x18005f2f2  nop     dword ptr [rax+rax+00h]
0x18005f2f7  mov     rcx, [rbp+arg_8]
0x18005f2fb  jmp     short loc_18005F304
0x18005f2fd  mov     qword ptr [rsi], 0
0x18005f304  call    cs:__imp_SysFreeString
0x18005f30b  nop     dword ptr [rax+rax+00h]
0x18005f310  mov     rcx, rbx; bstrString
0x18005f313  call    cs:__imp_SysFreeString
0x18005f31a  nop     dword ptr [rax+rax+00h]
0x18005f31f  mov     eax, edi
0x18005f321  mov     rbx, [rsp+30h+arg_0]
0x18005f326  add     rsp, 30h
0x18005f32a  pop     rdi
0x18005f32b  pop     rsi
0x18005f32c  pop     rbp
0x18005f32d  retn
```
