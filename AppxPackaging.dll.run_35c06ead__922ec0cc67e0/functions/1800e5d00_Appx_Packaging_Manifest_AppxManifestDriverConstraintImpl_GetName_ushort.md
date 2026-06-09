# Appx::Packaging::Manifest::AppxManifestDriverConstraintImpl::GetName(ushort * *)

- ea: `0x1800e5d00`
- end: `0x1800e5e5e`
- name: `?GetName@AppxManifestDriverConstraintImpl@Manifest@Packaging@Appx@@UEAAJPEAPEAG@Z`
- size: `350`
- prototype: `__int64 __fastcall(Appx::Packaging::Manifest::AppxManifestDriverConstraintImpl *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000f260`
- `0x180011cd0`
- `0x1800133fc`
- `0x18001711c`
- `0x1800e5d00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e5e09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e5e20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e5e09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e5e20`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e5dc4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e5e30`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e5e42`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e5dc4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e5e30`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e5e42`

## string_xrefs

- `0x1800e5d1e`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestdriverconstraint.cpp`
- `0x1800e5d61`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestdriverconstraint.cpp`
- `0x1800e5dac`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestdriverconstraint.cpp`
- `0x1800e5df1`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestdriverconstraint.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestDriverConstraintImpl::GetName(
        Appx::Packaging::Manifest::AppxManifestDriverConstraintImpl *this,
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
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestdriverconstraint.cpp",
          (const char *)(unsigned int)v7,
          0);
        CoTaskMemFree(pv);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x43,
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestdriverconstraint.cpp",
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
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestdriverconstraint.cpp",
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
    (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestdriverconstraint.cpp",
    (const char *)0x80004003LL,
    v9);
  return v4;
}

```

## disassembly

```asm
0x1800e5d00  mov     [rsp-18h+arg_0], rbx
0x1800e5d05  push    rbp
0x1800e5d06  push    rsi
0x1800e5d07  push    rdi
0x1800e5d08  mov     rbp, rsp
0x1800e5d0b  sub     rsp, 30h
0x1800e5d0f  mov     rdi, rdx
0x1800e5d12  mov     rsi, rcx
0x1800e5d15  test    rdx, rdx
0x1800e5d18  jnz     short loc_1800E5D3A
0x1800e5d1a  mov     rcx, [rbp+18h]; this
0x1800e5d1e  lea     r8, aOnecorePrintsc_62; "onecore\\printscan\\appxpackaging\\mani"...
0x1800e5d25  mov     ebx, 80004003h
0x1800e5d2a  lea     edx, [rdi+3Dh]; void *
0x1800e5d2d  mov     r9d, ebx; char *
0x1800e5d30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5d35  jmp     loc_1800E5E4E
0x1800e5d3a  lea     r8, [rbp+arg_18]
0x1800e5d3e  mov     [rbp+arg_18], 0
0x1800e5d46  lea     rdx, ?Name@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Name"
0x1800e5d4d  mov     ecx, 4
0x1800e5d52  call    ?BuildXPath@Packaging@Appx@@YAJW4XPathComponentType@12@PEBGAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponentType,ushort const *,Common::AutoBStr &)
0x1800e5d57  mov     ebx, eax
0x1800e5d59  test    eax, eax
0x1800e5d5b  jns     short loc_1800E5D7A
0x1800e5d5d  mov     rcx, [rbp+18h]; this
0x1800e5d61  lea     r8, aOnecorePrintsc_62; "onecore\\printscan\\appxpackaging\\mani"...
0x1800e5d68  mov     r9d, eax; char *
0x1800e5d6b  mov     edx, 40h ; '@'; void *
0x1800e5d70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5d75  jmp     loc_1800E5E3E
0x1800e5d7a  mov     rdx, [rbp+arg_18]
0x1800e5d7e  lea     rcx, [rsi+10h]
0x1800e5d82  lea     r9, [rbp+bstrString]
0x1800e5d86  mov     [rbp+bstrString], 0
0x1800e5d8e  mov     r8d, 8000FFFFh
0x1800e5d94  mov     qword ptr [rsp+30h+var_10], 0; int
0x1800e5d9d  call    ?GetNodeValue@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAGJPEAPEAGPEAPEAUIXMLDOMNode@@@Z; Appx::Packaging::GetNodeValue(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort *,long,ushort * *,IXMLDOMNode * *)
0x1800e5da2  mov     ebx, eax
0x1800e5da4  test    eax, eax
0x1800e5da6  jns     short loc_1800E5DD2
0x1800e5da8  mov     rcx, [rbp+18h]; this
0x1800e5dac  lea     r8, aOnecorePrintsc_62; "onecore\\printscan\\appxpackaging\\mani"...
0x1800e5db3  mov     r9d, eax; char *
0x1800e5db6  mov     edx, 43h ; 'C'; void *
0x1800e5dbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5dc0  mov     rcx, [rbp+bstrString]; bstrString
0x1800e5dc4  call    cs:__imp_SysFreeString
0x1800e5dcb  nop     dword ptr [rax+rax+00h]
0x1800e5dd0  jmp     short loc_1800E5E3E
0x1800e5dd2  mov     rdx, [rbp+bstrString]
0x1800e5dd6  lea     rcx, [rbp+pv]
0x1800e5dda  mov     [rbp+pv], 0
0x1800e5de2  call    ?CopyFromBStr@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJQEAG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromBStr(ushort * const)
0x1800e5de7  mov     ebx, eax
0x1800e5de9  test    eax, eax
0x1800e5deb  jns     short loc_1800E5E17
0x1800e5ded  mov     rcx, [rbp+18h]; this
0x1800e5df1  lea     r8, aOnecorePrintsc_62; "onecore\\printscan\\appxpackaging\\mani"...
0x1800e5df8  mov     r9d, eax; char *
0x1800e5dfb  mov     edx, 46h ; 'F'; void *
0x1800e5e00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5e05  mov     rcx, [rbp+pv]; pv
0x1800e5e09  call    cs:__imp_CoTaskMemFree
0x1800e5e10  nop     dword ptr [rax+rax+00h]
0x1800e5e15  jmp     short loc_1800E5DC0
0x1800e5e17  mov     rax, [rbp+pv]
0x1800e5e1b  xor     ecx, ecx; pv
0x1800e5e1d  mov     [rdi], rax
0x1800e5e20  call    cs:__imp_CoTaskMemFree
0x1800e5e27  nop     dword ptr [rax+rax+00h]
0x1800e5e2c  mov     rcx, [rbp+bstrString]; bstrString
0x1800e5e30  call    cs:__imp_SysFreeString
0x1800e5e37  nop     dword ptr [rax+rax+00h]
0x1800e5e3c  xor     ebx, ebx
0x1800e5e3e  mov     rcx, [rbp+arg_18]; bstrString
0x1800e5e42  call    cs:__imp_SysFreeString
0x1800e5e49  nop     dword ptr [rax+rax+00h]
0x1800e5e4e  mov     eax, ebx
0x1800e5e50  mov     rbx, [rsp+30h+arg_0]
0x1800e5e55  add     rsp, 30h
0x1800e5e59  pop     rdi
0x1800e5e5a  pop     rsi
0x1800e5e5b  pop     rbp
0x1800e5e5c  retn
```
