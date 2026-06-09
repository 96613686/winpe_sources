# Appx::Packaging::Manifest::AppxManifestHostRuntimeDependencyImpl::GetPublisher(ushort * *)

- ea: `0x1800e3be0`
- end: `0x1800e3d3e`
- name: `?GetPublisher@AppxManifestHostRuntimeDependencyImpl@Manifest@Packaging@Appx@@UEAAJPEAPEAG@Z`
- size: `350`
- prototype: `__int64 __fastcall(Appx::Packaging::Manifest::AppxManifestHostRuntimeDependencyImpl *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000f260`
- `0x180011cd0`
- `0x1800133fc`
- `0x18001711c`
- `0x1800e3be0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3ce9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3d00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3ce9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3d00`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e3ca4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e3d10`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e3d22`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e3ca4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e3d10`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e3d22`

## string_xrefs

- `0x1800e3bfe`: `onecore\printscan\appxpackaging\manifest\src\appxmanifesthostruntimedependency.cpp`
- `0x1800e3c41`: `onecore\printscan\appxpackaging\manifest\src\appxmanifesthostruntimedependency.cpp`
- `0x1800e3c8c`: `onecore\printscan\appxpackaging\manifest\src\appxmanifesthostruntimedependency.cpp`
- `0x1800e3cd1`: `onecore\printscan\appxpackaging\manifest\src\appxmanifesthostruntimedependency.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestHostRuntimeDependencyImpl::GetPublisher(
        Appx::Packaging::Manifest::AppxManifestHostRuntimeDependencyImpl *this,
        LPVOID *a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  int NodeValue; // eax
  int v7; // eax
  int v9; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  BSTR bstrString; // [rsp+58h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+30h] BYREF
  BSTR v13; // [rsp+68h] [rbp+38h] BYREF

  if ( a2 )
  {
    v13 = 0;
    v5 = Appx::Packaging::BuildXPath(4, L"Publisher", &v13);
    v4 = v5;
    if ( v5 >= 0 )
    {
      bstrString = 0;
      NodeValue = Appx::Packaging::GetNodeValue((char *)this + 24, v13, 2147549183LL, &bstrString);
      v4 = NodeValue;
      if ( NodeValue >= 0 )
      {
        pv = 0;
        v7 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoCoTaskMemStringAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoCoTaskMemStringDeallocate(unsigned short *)>::CopyFromBStr(
               &pv,
               bstrString);
        v4 = v7;
        if ( v7 >= 0 )
        {
          *a2 = pv;
          CoTaskMemFree(0);
          SysFreeString(bstrString);
          v4 = 0;
          goto LABEL_11;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5C,
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifesthostruntimedependency.cpp",
          (const char *)(unsigned int)v7,
          0);
        CoTaskMemFree(pv);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x59,
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifesthostruntimedependency.cpp",
          (const char *)(unsigned int)NodeValue,
          0);
      }
      SysFreeString(bstrString);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifesthostruntimedependency.cpp",
        (const char *)(unsigned int)v5,
        v9);
    }
LABEL_11:
    SysFreeString(v13);
    return v4;
  }
  v4 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x53,
    (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifesthostruntimedependency.cpp",
    (const char *)0x80004003LL,
    v9);
  return v4;
}

```

## disassembly

```asm
0x1800e3be0  mov     [rsp-18h+arg_0], rbx
0x1800e3be5  push    rbp
0x1800e3be6  push    rsi
0x1800e3be7  push    rdi
0x1800e3be8  mov     rbp, rsp
0x1800e3beb  sub     rsp, 30h
0x1800e3bef  mov     rdi, rdx
0x1800e3bf2  mov     rsi, rcx
0x1800e3bf5  test    rdx, rdx
0x1800e3bf8  jnz     short loc_1800E3C1A
0x1800e3bfa  mov     rcx, [rbp+18h]; this
0x1800e3bfe  lea     r8, aOnecorePrintsc_11; "onecore\\printscan\\appxpackaging\\mani"...
0x1800e3c05  mov     ebx, 80004003h
0x1800e3c0a  lea     edx, [rdi+53h]; void *
0x1800e3c0d  mov     r9d, ebx; char *
0x1800e3c10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3c15  jmp     loc_1800E3D2E
0x1800e3c1a  lea     r8, [rbp+arg_18]
0x1800e3c1e  mov     [rbp+arg_18], 0
0x1800e3c26  lea     rdx, ?Publisher@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Publisher"
0x1800e3c2d  mov     ecx, 4
0x1800e3c32  call    ?BuildXPath@Packaging@Appx@@YAJW4XPathComponentType@12@PEBGAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponentType,ushort const *,Common::AutoBStr &)
0x1800e3c37  mov     ebx, eax
0x1800e3c39  test    eax, eax
0x1800e3c3b  jns     short loc_1800E3C5A
0x1800e3c3d  mov     rcx, [rbp+18h]; this
0x1800e3c41  lea     r8, aOnecorePrintsc_11; "onecore\\printscan\\appxpackaging\\mani"...
0x1800e3c48  mov     r9d, eax; char *
0x1800e3c4b  mov     edx, 56h ; 'V'; void *
0x1800e3c50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3c55  jmp     loc_1800E3D1E
0x1800e3c5a  mov     rdx, [rbp+arg_18]
0x1800e3c5e  lea     rcx, [rsi+18h]
0x1800e3c62  lea     r9, [rbp+bstrString]
0x1800e3c66  mov     [rbp+bstrString], 0
0x1800e3c6e  mov     r8d, 8000FFFFh
0x1800e3c74  mov     qword ptr [rsp+30h+var_10], 0; int
0x1800e3c7d  call    ?GetNodeValue@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAGJPEAPEAGPEAPEAUIXMLDOMNode@@@Z; Appx::Packaging::GetNodeValue(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort *,long,ushort * *,IXMLDOMNode * *)
0x1800e3c82  mov     ebx, eax
0x1800e3c84  test    eax, eax
0x1800e3c86  jns     short loc_1800E3CB2
0x1800e3c88  mov     rcx, [rbp+18h]; this
0x1800e3c8c  lea     r8, aOnecorePrintsc_11; "onecore\\printscan\\appxpackaging\\mani"...
0x1800e3c93  mov     r9d, eax; char *
0x1800e3c96  mov     edx, 59h ; 'Y'; void *
0x1800e3c9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3ca0  mov     rcx, [rbp+bstrString]; bstrString
0x1800e3ca4  call    cs:__imp_SysFreeString
0x1800e3cab  nop     dword ptr [rax+rax+00h]
0x1800e3cb0  jmp     short loc_1800E3D1E
0x1800e3cb2  mov     rdx, [rbp+bstrString]
0x1800e3cb6  lea     rcx, [rbp+pv]
0x1800e3cba  mov     [rbp+pv], 0
0x1800e3cc2  call    ?CopyFromBStr@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJQEAG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromBStr(ushort * const)
0x1800e3cc7  mov     ebx, eax
0x1800e3cc9  test    eax, eax
0x1800e3ccb  jns     short loc_1800E3CF7
0x1800e3ccd  mov     rcx, [rbp+18h]; this
0x1800e3cd1  lea     r8, aOnecorePrintsc_11; "onecore\\printscan\\appxpackaging\\mani"...
0x1800e3cd8  mov     r9d, eax; char *
0x1800e3cdb  mov     edx, 5Ch ; '\'; void *
0x1800e3ce0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3ce5  mov     rcx, [rbp+pv]; pv
0x1800e3ce9  call    cs:__imp_CoTaskMemFree
0x1800e3cf0  nop     dword ptr [rax+rax+00h]
0x1800e3cf5  jmp     short loc_1800E3CA0
0x1800e3cf7  mov     rax, [rbp+pv]
0x1800e3cfb  xor     ecx, ecx; pv
0x1800e3cfd  mov     [rdi], rax
0x1800e3d00  call    cs:__imp_CoTaskMemFree
0x1800e3d07  nop     dword ptr [rax+rax+00h]
0x1800e3d0c  mov     rcx, [rbp+bstrString]; bstrString
0x1800e3d10  call    cs:__imp_SysFreeString
0x1800e3d17  nop     dword ptr [rax+rax+00h]
0x1800e3d1c  xor     ebx, ebx
0x1800e3d1e  mov     rcx, [rbp+arg_18]; bstrString
0x1800e3d22  call    cs:__imp_SysFreeString
0x1800e3d29  nop     dword ptr [rax+rax+00h]
0x1800e3d2e  mov     eax, ebx
0x1800e3d30  mov     rbx, [rsp+30h+arg_0]
0x1800e3d35  add     rsp, 30h
0x1800e3d39  pop     rdi
0x1800e3d3a  pop     rsi
0x1800e3d3b  pop     rbp
0x1800e3d3c  retn
```
