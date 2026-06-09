# Appx::Packaging::Manifest::AppxManifestOSPackageDependencyImpl::GetName(ushort * *)

- ea: `0x1800e3f70`
- end: `0x1800e40ce`
- name: `?GetName@AppxManifestOSPackageDependencyImpl@Manifest@Packaging@Appx@@UEAAJPEAPEAG@Z`
- size: `350`
- prototype: `__int64 __fastcall(Appx::Packaging::Manifest::AppxManifestOSPackageDependencyImpl *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000f260`
- `0x180011cd0`
- `0x1800133fc`
- `0x18001711c`
- `0x1800e3f70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e4079`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e4090`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e4079`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e4090`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e4034`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e40a0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e40b2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e4034`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e40a0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e40b2`

## string_xrefs

- `0x1800e3f8e`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestospackagedependency.cpp`
- `0x1800e3fd1`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestospackagedependency.cpp`
- `0x1800e401c`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestospackagedependency.cpp`
- `0x1800e4061`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestospackagedependency.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestOSPackageDependencyImpl::GetName(
        Appx::Packaging::Manifest::AppxManifestOSPackageDependencyImpl *this,
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
    v5 = Appx::Packaging::BuildXPath(4, L"Name", &v13);
    v4 = v5;
    if ( v5 >= 0 )
    {
      bstrString = 0;
      NodeValue = Appx::Packaging::GetNodeValue((char *)this + 16, v13, 2147549183LL, &bstrString);
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
          (void *)0x46,
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestospackagedependency.cpp",
          (const char *)(unsigned int)v7,
          0);
        CoTaskMemFree(pv);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x43,
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestospackagedependency.cpp",
          (const char *)(unsigned int)NodeValue,
          0);
      }
      SysFreeString(bstrString);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestospackagedependency.cpp",
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
    (void *)0x3D,
    (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestospackagedependency.cpp",
    (const char *)0x80004003LL,
    v9);
  return v4;
}

```

## disassembly

```asm
0x1800e3f70  mov     [rsp-18h+arg_0], rbx
0x1800e3f75  push    rbp
0x1800e3f76  push    rsi
0x1800e3f77  push    rdi
0x1800e3f78  mov     rbp, rsp
0x1800e3f7b  sub     rsp, 30h
0x1800e3f7f  mov     rdi, rdx
0x1800e3f82  mov     rsi, rcx
0x1800e3f85  test    rdx, rdx
0x1800e3f88  jnz     short loc_1800E3FAA
0x1800e3f8a  mov     rcx, [rbp+18h]; this
0x1800e3f8e  lea     r8, aOnecorePrintsc_122; "onecore\\printscan\\appxpackaging\\mani"...
0x1800e3f95  mov     ebx, 80004003h
0x1800e3f9a  lea     edx, [rdi+3Dh]; void *
0x1800e3f9d  mov     r9d, ebx; char *
0x1800e3fa0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3fa5  jmp     loc_1800E40BE
0x1800e3faa  lea     r8, [rbp+arg_18]
0x1800e3fae  mov     [rbp+arg_18], 0
0x1800e3fb6  lea     rdx, ?Name@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Name"
0x1800e3fbd  mov     ecx, 4
0x1800e3fc2  call    ?BuildXPath@Packaging@Appx@@YAJW4XPathComponentType@12@PEBGAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponentType,ushort const *,Common::AutoBStr &)
0x1800e3fc7  mov     ebx, eax
0x1800e3fc9  test    eax, eax
0x1800e3fcb  jns     short loc_1800E3FEA
0x1800e3fcd  mov     rcx, [rbp+18h]; this
0x1800e3fd1  lea     r8, aOnecorePrintsc_122; "onecore\\printscan\\appxpackaging\\mani"...
0x1800e3fd8  mov     r9d, eax; char *
0x1800e3fdb  mov     edx, 40h ; '@'; void *
0x1800e3fe0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3fe5  jmp     loc_1800E40AE
0x1800e3fea  mov     rdx, [rbp+arg_18]
0x1800e3fee  lea     rcx, [rsi+10h]
0x1800e3ff2  lea     r9, [rbp+bstrString]
0x1800e3ff6  mov     [rbp+bstrString], 0
0x1800e3ffe  mov     r8d, 8000FFFFh
0x1800e4004  mov     qword ptr [rsp+30h+var_10], 0; int
0x1800e400d  call    ?GetNodeValue@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAGJPEAPEAGPEAPEAUIXMLDOMNode@@@Z; Appx::Packaging::GetNodeValue(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort *,long,ushort * *,IXMLDOMNode * *)
0x1800e4012  mov     ebx, eax
0x1800e4014  test    eax, eax
0x1800e4016  jns     short loc_1800E4042
0x1800e4018  mov     rcx, [rbp+18h]; this
0x1800e401c  lea     r8, aOnecorePrintsc_122; "onecore\\printscan\\appxpackaging\\mani"...
0x1800e4023  mov     r9d, eax; char *
0x1800e4026  mov     edx, 43h ; 'C'; void *
0x1800e402b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e4030  mov     rcx, [rbp+bstrString]; bstrString
0x1800e4034  call    cs:__imp_SysFreeString
0x1800e403b  nop     dword ptr [rax+rax+00h]
0x1800e4040  jmp     short loc_1800E40AE
0x1800e4042  mov     rdx, [rbp+bstrString]
0x1800e4046  lea     rcx, [rbp+pv]
0x1800e404a  mov     [rbp+pv], 0
0x1800e4052  call    ?CopyFromBStr@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJQEAG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromBStr(ushort * const)
0x1800e4057  mov     ebx, eax
0x1800e4059  test    eax, eax
0x1800e405b  jns     short loc_1800E4087
0x1800e405d  mov     rcx, [rbp+18h]; this
0x1800e4061  lea     r8, aOnecorePrintsc_122; "onecore\\printscan\\appxpackaging\\mani"...
0x1800e4068  mov     r9d, eax; char *
0x1800e406b  mov     edx, 46h ; 'F'; void *
0x1800e4070  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e4075  mov     rcx, [rbp+pv]; pv
0x1800e4079  call    cs:__imp_CoTaskMemFree
0x1800e4080  nop     dword ptr [rax+rax+00h]
0x1800e4085  jmp     short loc_1800E4030
0x1800e4087  mov     rax, [rbp+pv]
0x1800e408b  xor     ecx, ecx; pv
0x1800e408d  mov     [rdi], rax
0x1800e4090  call    cs:__imp_CoTaskMemFree
0x1800e4097  nop     dword ptr [rax+rax+00h]
0x1800e409c  mov     rcx, [rbp+bstrString]; bstrString
0x1800e40a0  call    cs:__imp_SysFreeString
0x1800e40a7  nop     dword ptr [rax+rax+00h]
0x1800e40ac  xor     ebx, ebx
0x1800e40ae  mov     rcx, [rbp+arg_18]; bstrString
0x1800e40b2  call    cs:__imp_SysFreeString
0x1800e40b9  nop     dword ptr [rax+rax+00h]
0x1800e40be  mov     eax, ebx
0x1800e40c0  mov     rbx, [rsp+30h+arg_0]
0x1800e40c5  add     rsp, 30h
0x1800e40c9  pop     rdi
0x1800e40ca  pop     rsi
0x1800e40cb  pop     rbp
0x1800e40cc  retn
```
