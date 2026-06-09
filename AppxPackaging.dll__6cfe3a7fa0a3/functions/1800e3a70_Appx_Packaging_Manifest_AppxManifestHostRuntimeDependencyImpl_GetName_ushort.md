# Appx::Packaging::Manifest::AppxManifestHostRuntimeDependencyImpl::GetName(ushort * *)

- ea: `0x1800e3a70`
- end: `0x1800e3bce`
- name: `?GetName@AppxManifestHostRuntimeDependencyImpl@Manifest@Packaging@Appx@@UEAAJPEAPEAG@Z`
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
- `0x1800e3a70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3b79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3b90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3b79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3b90`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e3b34`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e3ba0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e3bb2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e3b34`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e3ba0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e3bb2`

## string_xrefs

- `0x1800e3a8e`: `onecore\printscan\appxpackaging\manifest\src\appxmanifesthostruntimedependency.cpp`
- `0x1800e3ad1`: `onecore\printscan\appxpackaging\manifest\src\appxmanifesthostruntimedependency.cpp`
- `0x1800e3b1c`: `onecore\printscan\appxpackaging\manifest\src\appxmanifesthostruntimedependency.cpp`
- `0x1800e3b61`: `onecore\printscan\appxpackaging\manifest\src\appxmanifesthostruntimedependency.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestHostRuntimeDependencyImpl::GetName(
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
    v5 = Appx::Packaging::BuildXPath(4, L"Name", &v13);
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
          (void *)0x47,
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifesthostruntimedependency.cpp",
          (const char *)(unsigned int)v7,
          0);
        CoTaskMemFree(pv);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x44,
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
        (void *)0x41,
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
    (void *)0x3E,
    (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifesthostruntimedependency.cpp",
    (const char *)0x80004003LL,
    v9);
  return v4;
}

```

## disassembly

```asm
0x1800e3a70  mov     [rsp-18h+arg_0], rbx
0x1800e3a75  push    rbp
0x1800e3a76  push    rsi
0x1800e3a77  push    rdi
0x1800e3a78  mov     rbp, rsp
0x1800e3a7b  sub     rsp, 30h
0x1800e3a7f  mov     rdi, rdx
0x1800e3a82  mov     rsi, rcx
0x1800e3a85  test    rdx, rdx
0x1800e3a88  jnz     short loc_1800E3AAA
0x1800e3a8a  mov     rcx, [rbp+18h]; this
0x1800e3a8e  lea     r8, aOnecorePrintsc_11; "onecore\\printscan\\appxpackaging\\mani"...
0x1800e3a95  mov     ebx, 80004003h
0x1800e3a9a  lea     edx, [rdi+3Eh]; void *
0x1800e3a9d  mov     r9d, ebx; char *
0x1800e3aa0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3aa5  jmp     loc_1800E3BBE
0x1800e3aaa  lea     r8, [rbp+arg_18]
0x1800e3aae  mov     [rbp+arg_18], 0
0x1800e3ab6  lea     rdx, ?Name@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Name"
0x1800e3abd  mov     ecx, 4
0x1800e3ac2  call    ?BuildXPath@Packaging@Appx@@YAJW4XPathComponentType@12@PEBGAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponentType,ushort const *,Common::AutoBStr &)
0x1800e3ac7  mov     ebx, eax
0x1800e3ac9  test    eax, eax
0x1800e3acb  jns     short loc_1800E3AEA
0x1800e3acd  mov     rcx, [rbp+18h]; this
0x1800e3ad1  lea     r8, aOnecorePrintsc_11; "onecore\\printscan\\appxpackaging\\mani"...
0x1800e3ad8  mov     r9d, eax; char *
0x1800e3adb  mov     edx, 41h ; 'A'; void *
0x1800e3ae0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3ae5  jmp     loc_1800E3BAE
0x1800e3aea  mov     rdx, [rbp+arg_18]
0x1800e3aee  lea     rcx, [rsi+18h]
0x1800e3af2  lea     r9, [rbp+bstrString]
0x1800e3af6  mov     [rbp+bstrString], 0
0x1800e3afe  mov     r8d, 8000FFFFh
0x1800e3b04  mov     qword ptr [rsp+30h+var_10], 0; int
0x1800e3b0d  call    ?GetNodeValue@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAGJPEAPEAGPEAPEAUIXMLDOMNode@@@Z; Appx::Packaging::GetNodeValue(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort *,long,ushort * *,IXMLDOMNode * *)
0x1800e3b12  mov     ebx, eax
0x1800e3b14  test    eax, eax
0x1800e3b16  jns     short loc_1800E3B42
0x1800e3b18  mov     rcx, [rbp+18h]; this
0x1800e3b1c  lea     r8, aOnecorePrintsc_11; "onecore\\printscan\\appxpackaging\\mani"...
0x1800e3b23  mov     r9d, eax; char *
0x1800e3b26  mov     edx, 44h ; 'D'; void *
0x1800e3b2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3b30  mov     rcx, [rbp+bstrString]; bstrString
0x1800e3b34  call    cs:__imp_SysFreeString
0x1800e3b3b  nop     dword ptr [rax+rax+00h]
0x1800e3b40  jmp     short loc_1800E3BAE
0x1800e3b42  mov     rdx, [rbp+bstrString]
0x1800e3b46  lea     rcx, [rbp+pv]
0x1800e3b4a  mov     [rbp+pv], 0
0x1800e3b52  call    ?CopyFromBStr@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJQEAG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromBStr(ushort * const)
0x1800e3b57  mov     ebx, eax
0x1800e3b59  test    eax, eax
0x1800e3b5b  jns     short loc_1800E3B87
0x1800e3b5d  mov     rcx, [rbp+18h]; this
0x1800e3b61  lea     r8, aOnecorePrintsc_11; "onecore\\printscan\\appxpackaging\\mani"...
0x1800e3b68  mov     r9d, eax; char *
0x1800e3b6b  mov     edx, 47h ; 'G'; void *
0x1800e3b70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3b75  mov     rcx, [rbp+pv]; pv
0x1800e3b79  call    cs:__imp_CoTaskMemFree
0x1800e3b80  nop     dword ptr [rax+rax+00h]
0x1800e3b85  jmp     short loc_1800E3B30
0x1800e3b87  mov     rax, [rbp+pv]
0x1800e3b8b  xor     ecx, ecx; pv
0x1800e3b8d  mov     [rdi], rax
0x1800e3b90  call    cs:__imp_CoTaskMemFree
0x1800e3b97  nop     dword ptr [rax+rax+00h]
0x1800e3b9c  mov     rcx, [rbp+bstrString]; bstrString
0x1800e3ba0  call    cs:__imp_SysFreeString
0x1800e3ba7  nop     dword ptr [rax+rax+00h]
0x1800e3bac  xor     ebx, ebx
0x1800e3bae  mov     rcx, [rbp+arg_18]; bstrString
0x1800e3bb2  call    cs:__imp_SysFreeString
0x1800e3bb9  nop     dword ptr [rax+rax+00h]
0x1800e3bbe  mov     eax, ebx
0x1800e3bc0  mov     rbx, [rsp+30h+arg_0]
0x1800e3bc5  add     rsp, 30h
0x1800e3bc9  pop     rdi
0x1800e3bca  pop     rsi
0x1800e3bcb  pop     rbp
0x1800e3bcc  retn
```
