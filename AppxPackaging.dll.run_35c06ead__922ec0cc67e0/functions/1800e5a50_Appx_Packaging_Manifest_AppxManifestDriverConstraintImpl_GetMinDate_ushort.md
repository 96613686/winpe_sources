# Appx::Packaging::Manifest::AppxManifestDriverConstraintImpl::GetMinDate(ushort * *)

- ea: `0x1800e5a50`
- end: `0x1800e5bbc`
- name: `?GetMinDate@AppxManifestDriverConstraintImpl@Manifest@Packaging@Appx@@UEAAJPEAPEAG@Z`
- size: `364`
- prototype: `__int64 __fastcall(Appx::Packaging::Manifest::AppxManifestDriverConstraintImpl *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000f260`
- `0x180011cd0`
- `0x1800133fc`
- `0x18001711c`
- `0x1800e5a50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e5b5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e5b75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e5b5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e5b75`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e5b11`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e5b8e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e5ba0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e5b11`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e5b8e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e5ba0`

## string_xrefs

- `0x1800e5a6e`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestdriverconstraint.cpp`
- `0x1800e5ab1`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestdriverconstraint.cpp`
- `0x1800e5af9`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestdriverconstraint.cpp`
- `0x1800e5b46`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestdriverconstraint.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestDriverConstraintImpl::GetMinDate(
        Appx::Packaging::Manifest::AppxManifestDriverConstraintImpl *this,
        LPVOID *a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  int NodeValue; // eax
  OLECHAR *v7; // rcx
  int v8; // eax
  int v10; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  BSTR bstrString; // [rsp+58h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+30h] BYREF
  BSTR v14; // [rsp+68h] [rbp+38h] BYREF

  if ( a2 )
  {
    v14 = 0;
    v5 = Appx::Packaging::BuildXPath(4, L"MinDate", &v14);
    v4 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x55,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestdriverconstraint.cpp",
        (const char *)(unsigned int)v5,
        v10);
LABEL_14:
      SysFreeString(v14);
      return v4;
    }
    bstrString = 0;
    NodeValue = Appx::Packaging::GetNodeValue((char *)this + 16, v14, 0, &bstrString);
    v4 = NodeValue;
    if ( NodeValue < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x58,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestdriverconstraint.cpp",
        (const char *)(unsigned int)NodeValue,
        0);
LABEL_7:
      SysFreeString(bstrString);
      goto LABEL_14;
    }
    v7 = bstrString;
    if ( bstrString )
    {
      pv = 0;
      v8 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoCoTaskMemStringAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoCoTaskMemStringDeallocate(unsigned short *)>::CopyFromBStr(
             &pv,
             bstrString);
      v4 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5D,
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestdriverconstraint.cpp",
          (const char *)(unsigned int)v8,
          0);
        CoTaskMemFree(pv);
        goto LABEL_7;
      }
      *a2 = pv;
      CoTaskMemFree(0);
      v7 = bstrString;
    }
    else
    {
      *a2 = 0;
    }
    SysFreeString(v7);
    v4 = 0;
    goto LABEL_14;
  }
  v4 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x52,
    (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestdriverconstraint.cpp",
    (const char *)0x80004003LL,
    v10);
  return v4;
}

```

## disassembly

```asm
0x1800e5a50  mov     [rsp-18h+arg_0], rbx
0x1800e5a55  push    rbp
0x1800e5a56  push    rsi
0x1800e5a57  push    rdi
0x1800e5a58  mov     rbp, rsp
0x1800e5a5b  sub     rsp, 30h
0x1800e5a5f  mov     rdi, rdx
0x1800e5a62  mov     rsi, rcx
0x1800e5a65  test    rdx, rdx
0x1800e5a68  jnz     short loc_1800E5A8A
0x1800e5a6a  mov     rcx, [rbp+18h]; this
0x1800e5a6e  lea     r8, aOnecorePrintsc_62; "onecore\\printscan\\appxpackaging\\mani"...
0x1800e5a75  mov     ebx, 80004003h
0x1800e5a7a  lea     edx, [rdi+52h]; void *
0x1800e5a7d  mov     r9d, ebx; char *
0x1800e5a80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5a85  jmp     loc_1800E5BAC
0x1800e5a8a  lea     r8, [rbp+arg_18]
0x1800e5a8e  mov     [rbp+arg_18], 0
0x1800e5a96  lea     rdx, ?MinDate@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "MinDate"
0x1800e5a9d  mov     ecx, 4
0x1800e5aa2  call    ?BuildXPath@Packaging@Appx@@YAJW4XPathComponentType@12@PEBGAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponentType,ushort const *,Common::AutoBStr &)
0x1800e5aa7  mov     ebx, eax
0x1800e5aa9  test    eax, eax
0x1800e5aab  jns     short loc_1800E5ACA
0x1800e5aad  mov     rcx, [rbp+18h]; this
0x1800e5ab1  lea     r8, aOnecorePrintsc_62; "onecore\\printscan\\appxpackaging\\mani"...
0x1800e5ab8  mov     r9d, eax; char *
0x1800e5abb  mov     edx, 55h ; 'U'; void *
0x1800e5ac0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5ac5  jmp     loc_1800E5B9C
0x1800e5aca  mov     rdx, [rbp+arg_18]
0x1800e5ace  lea     rcx, [rsi+10h]
0x1800e5ad2  lea     r9, [rbp+bstrString]
0x1800e5ad6  mov     [rbp+bstrString], 0
0x1800e5ade  xor     r8d, r8d
0x1800e5ae1  mov     qword ptr [rsp+30h+var_10], 0; int
0x1800e5aea  call    ?GetNodeValue@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAGJPEAPEAGPEAPEAUIXMLDOMNode@@@Z; Appx::Packaging::GetNodeValue(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort *,long,ushort * *,IXMLDOMNode * *)
0x1800e5aef  mov     ebx, eax
0x1800e5af1  test    eax, eax
0x1800e5af3  jns     short loc_1800E5B1F
0x1800e5af5  mov     rcx, [rbp+18h]; this
0x1800e5af9  lea     r8, aOnecorePrintsc_62; "onecore\\printscan\\appxpackaging\\mani"...
0x1800e5b00  mov     r9d, eax; char *
0x1800e5b03  mov     edx, 58h ; 'X'; void *
0x1800e5b08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5b0d  mov     rcx, [rbp+bstrString]; bstrString
0x1800e5b11  call    cs:__imp_SysFreeString
0x1800e5b18  nop     dword ptr [rax+rax+00h]
0x1800e5b1d  jmp     short loc_1800E5B9C
0x1800e5b1f  mov     rcx, [rbp+bstrString]; bstrString
0x1800e5b23  test    rcx, rcx
0x1800e5b26  jz      short loc_1800E5B87
0x1800e5b28  mov     rdx, rcx
0x1800e5b2b  mov     [rbp+pv], 0
0x1800e5b33  lea     rcx, [rbp+pv]
0x1800e5b37  call    ?CopyFromBStr@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJQEAG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromBStr(ushort * const)
0x1800e5b3c  mov     ebx, eax
0x1800e5b3e  test    eax, eax
0x1800e5b40  jns     short loc_1800E5B6C
0x1800e5b42  mov     rcx, [rbp+18h]; this
0x1800e5b46  lea     r8, aOnecorePrintsc_62; "onecore\\printscan\\appxpackaging\\mani"...
0x1800e5b4d  mov     r9d, eax; char *
0x1800e5b50  mov     edx, 5Dh ; ']'; void *
0x1800e5b55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5b5a  mov     rcx, [rbp+pv]; pv
0x1800e5b5e  call    cs:__imp_CoTaskMemFree
0x1800e5b65  nop     dword ptr [rax+rax+00h]
0x1800e5b6a  jmp     short loc_1800E5B0D
0x1800e5b6c  mov     rax, [rbp+pv]
0x1800e5b70  xor     ecx, ecx; pv
0x1800e5b72  mov     [rdi], rax
0x1800e5b75  call    cs:__imp_CoTaskMemFree
0x1800e5b7c  nop     dword ptr [rax+rax+00h]
0x1800e5b81  mov     rcx, [rbp+bstrString]
0x1800e5b85  jmp     short loc_1800E5B8E
0x1800e5b87  mov     qword ptr [rdi], 0
0x1800e5b8e  call    cs:__imp_SysFreeString
0x1800e5b95  nop     dword ptr [rax+rax+00h]
0x1800e5b9a  xor     ebx, ebx
0x1800e5b9c  mov     rcx, [rbp+arg_18]; bstrString
0x1800e5ba0  call    cs:__imp_SysFreeString
0x1800e5ba7  nop     dword ptr [rax+rax+00h]
0x1800e5bac  mov     eax, ebx
0x1800e5bae  mov     rbx, [rsp+30h+arg_0]
0x1800e5bb3  add     rsp, 30h
0x1800e5bb7  pop     rdi
0x1800e5bb8  pop     rsi
0x1800e5bb9  pop     rbp
0x1800e5bba  retn
```
