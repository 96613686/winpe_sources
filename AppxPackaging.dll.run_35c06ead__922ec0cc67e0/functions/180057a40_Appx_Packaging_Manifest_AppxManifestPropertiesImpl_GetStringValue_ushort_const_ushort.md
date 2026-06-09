# Appx::Packaging::Manifest::AppxManifestPropertiesImpl::GetStringValue(ushort const *,ushort * *)

- ea: `0x180057a40`
- end: `0x180057c08`
- name: `?GetStringValue@AppxManifestPropertiesImpl@Manifest@Packaging@Appx@@UEAAJPEBGPEAPEAG@Z`
- size: `456`
- prototype: `__int64 __fastcall(Appx::Packaging::Manifest::AppxManifestPropertiesImpl *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000f260`
- `0x180011cd0`
- `0x1800133fc`
- `0x18001711c`
- `0x180057a40`
- `0x180071f50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180057a7e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180057a7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057b4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057b4c`
- `OLEAUT32!__imp_SysFreeString` at `0x180057b5c`
- `OLEAUT32!__imp_SysFreeString` at `0x180057b6b`
- `OLEAUT32!__imp_SysFreeString` at `0x180057b9a`
- `OLEAUT32!__imp_SysFreeString` at `0x180057b5c`
- `OLEAUT32!__imp_SysFreeString` at `0x180057b6b`
- `OLEAUT32!__imp_SysFreeString` at `0x180057b9a`

## string_xrefs

- `0x180057aa3`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestproperties.cpp`
- `0x180057b82`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestproperties.cpp`
- `0x180057baf`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestproperties.cpp`
- `0x180057bcd`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestproperties.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestPropertiesImpl::GetStringValue(
        Appx::Packaging::Manifest::AppxManifestPropertiesImpl *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  __int64 v6; // rbx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  const unsigned __int16 * near *v10; // rdx
  int v11; // eax
  OLECHAR *v12; // rbx
  int NodeValue; // eax
  unsigned int v14; // edi
  OLECHAR *v15; // rcx
  int v16; // eax
  BSTR v17; // rcx
  int v18; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  BSTR bstrString; // [rsp+68h] [rbp+38h] BYREF
  BSTR v21; // [rsp+78h] [rbp+48h] BYREF

  if ( !a2 )
  {
    v8 = 94;
    goto LABEL_21;
  }
  if ( !a3 )
  {
    v8 = 95;
LABEL_21:
    v7 = -2147467261;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestproperties.cpp",
      (const char *)v7,
      v18);
    return v7;
  }
  v6 = 0;
  while ( (unsigned int)_o__wcsicmp((&Appx::Packaging::Manifest::Element::PropertiesStringValues)[v6], a2) )
  {
    v6 = (unsigned int)(v6 + 1);
    if ( (unsigned int)v6 >= 4 )
    {
      v7 = -2147024809;
      v8 = 113;
      goto LABEL_7;
    }
  }
  v10 = (&Appx::Packaging::Manifest::Element::PropertiesStringValues)[v6];
  v21 = 0;
  v11 = Appx::Packaging::BuildXPath(3, v10, &v21);
  v7 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestproperties.cpp",
      (const char *)(unsigned int)v11,
      v18);
    SysFreeString(v21);
    return v7;
  }
  v12 = v21;
  bstrString = 0;
  NodeValue = Appx::Packaging::GetNodeValue((char *)this + 16, v21, 0, &bstrString);
  v14 = NodeValue;
  if ( NodeValue < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestproperties.cpp",
      (const char *)(unsigned int)NodeValue,
      0);
  }
  else
  {
    v15 = bstrString;
    if ( !bstrString )
    {
      *a3 = 0;
      goto LABEL_16;
    }
    v21 = 0;
    v16 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoCoTaskMemStringAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoCoTaskMemStringDeallocate(unsigned short *)>::CopyFromBStr(
            (LPVOID *)&v21,
            bstrString);
    v14 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x7B,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestproperties.cpp",
        (const char *)(unsigned int)v16,
        0);
      v17 = v21;
    }
    else
    {
      v17 = 0;
      *a3 = v21;
    }
    CoTaskMemFree(v17);
  }
  v15 = bstrString;
LABEL_16:
  SysFreeString(v15);
  SysFreeString(v12);
  return v14;
}

```

## disassembly

```asm
0x180057a40  mov     [rsp-28h+arg_0], rbx
0x180057a45  push    rbp
0x180057a46  push    rsi
0x180057a47  push    rdi
0x180057a48  push    r12
0x180057a4a  push    r14
0x180057a4c  mov     rbp, rsp
0x180057a4f  sub     rsp, 30h
0x180057a53  mov     rsi, r8
0x180057a56  mov     rdi, rdx
0x180057a59  mov     r14, rcx
0x180057a5c  test    rdx, rdx
0x180057a5f  jz      loc_180057BE6
0x180057a65  test    r8, r8
0x180057a68  jz      loc_180057BF5
0x180057a6e  xor     ebx, ebx
0x180057a70  lea     r12, ?PropertiesStringValues@Element@Manifest@Packaging@Appx@@3PAPEBGA; ushort const * near * Appx::Packaging::Manifest::Element::PropertiesStringValues
0x180057a77  mov     rcx, [r12+rbx*8]
0x180057a7b  mov     rdx, rdi
0x180057a7e  call    cs:__imp__o__wcsicmp
0x180057a85  nop     dword ptr [rax+rax+00h]
0x180057a8a  test    eax, eax
0x180057a8c  jz      short loc_180057AC6
0x180057a8e  inc     ebx
0x180057a90  cmp     ebx, 4
0x180057a93  jb      short loc_180057A77
0x180057a95  mov     ebx, 80070057h
0x180057a9a  mov     edx, 71h ; 'q'; void *
0x180057a9f  mov     rcx, [rbp+28h]; this
0x180057aa3  lea     r8, aOnecorePrintsc_22; "onecore\\printscan\\appxpackaging\\mani"...
0x180057aaa  mov     r9d, ebx; char *
0x180057aad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057ab2  mov     eax, ebx
0x180057ab4  mov     rbx, [rsp+30h+arg_0]
0x180057ab9  add     rsp, 30h
0x180057abd  pop     r14
0x180057abf  pop     r12
0x180057ac1  pop     rdi
0x180057ac2  pop     rsi
0x180057ac3  pop     rbp
0x180057ac4  retn
0x180057ac6  mov     rdx, [r12+rbx*8]
0x180057aca  lea     r8, [rbp+arg_18]
0x180057ace  mov     ecx, 3
0x180057ad3  mov     [rbp+arg_18], 0
0x180057adb  call    ?BuildXPath@Packaging@Appx@@YAJW4XPathComponentType@12@PEBGAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponentType,ushort const *,Common::AutoBStr &)
0x180057ae0  mov     ebx, eax
0x180057ae2  test    eax, eax
0x180057ae4  js      loc_180057B7E
0x180057aea  mov     rbx, [rbp+arg_18]
0x180057aee  lea     rcx, [r14+10h]
0x180057af2  mov     rdx, rbx
0x180057af5  mov     [rbp+bstrString], 0
0x180057afd  lea     r9, [rbp+bstrString]
0x180057b01  mov     qword ptr [rsp+30h+var_10], 0; int
0x180057b0a  xor     r8d, r8d
0x180057b0d  call    ?GetNodeValue@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAGJPEAPEAGPEAPEAUIXMLDOMNode@@@Z; Appx::Packaging::GetNodeValue(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort *,long,ushort * *,IXMLDOMNode * *)
0x180057b12  mov     edi, eax
0x180057b14  test    eax, eax
0x180057b16  js      loc_180057BC9
0x180057b1c  mov     rcx, [rbp+bstrString]
0x180057b20  test    rcx, rcx
0x180057b23  jz      loc_180057BFC
0x180057b29  mov     rdx, rcx
0x180057b2c  mov     [rbp+arg_18], 0
0x180057b34  lea     rcx, [rbp+arg_18]
0x180057b38  call    ?CopyFromBStr@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJQEAG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromBStr(ushort * const)
0x180057b3d  mov     edi, eax
0x180057b3f  test    eax, eax
0x180057b41  js      short loc_180057BAB
0x180057b43  mov     rax, [rbp+arg_18]
0x180057b47  xor     ecx, ecx; pv
0x180057b49  mov     [rsi], rax
0x180057b4c  call    cs:__imp_CoTaskMemFree
0x180057b53  nop     dword ptr [rax+rax+00h]
0x180057b58  mov     rcx, [rbp+bstrString]; bstrString
0x180057b5c  call    cs:__imp_SysFreeString
0x180057b63  nop     dword ptr [rax+rax+00h]
0x180057b68  mov     rcx, rbx; bstrString
0x180057b6b  call    cs:__imp_SysFreeString
0x180057b72  nop     dword ptr [rax+rax+00h]
0x180057b77  mov     eax, edi
0x180057b79  jmp     loc_180057AB4
0x180057b7e  mov     rcx, [rbp+28h]; this
0x180057b82  lea     r8, aOnecorePrintsc_22; "onecore\\printscan\\appxpackaging\\mani"...
0x180057b89  mov     r9d, ebx; char *
0x180057b8c  mov     edx, 74h ; 't'; void *
0x180057b91  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180057b96  mov     rcx, [rbp+arg_18]; bstrString
0x180057b9a  call    cs:__imp_SysFreeString
0x180057ba1  nop     dword ptr [rax+rax+00h]
0x180057ba6  jmp     loc_180057AB2
0x180057bab  mov     rcx, [rbp+28h]; this
0x180057baf  lea     r8, aOnecorePrintsc_22; "onecore\\printscan\\appxpackaging\\mani"...
0x180057bb6  mov     r9d, edi; char *
0x180057bb9  mov     edx, 7Bh ; '{'; void *
0x180057bbe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180057bc3  mov     rcx, [rbp+arg_18]
0x180057bc7  jmp     short loc_180057B4C
0x180057bc9  mov     rcx, [rbp+28h]; this
0x180057bcd  lea     r8, aOnecorePrintsc_22; "onecore\\printscan\\appxpackaging\\mani"...
0x180057bd4  mov     r9d, edi; char *
0x180057bd7  mov     edx, 76h ; 'v'; void *
0x180057bdc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180057be1  jmp     loc_180057B58
0x180057be6  mov     edx, 5Eh ; '^'
0x180057beb  mov     ebx, 80004003h
0x180057bf0  jmp     loc_180057A9F
0x180057bf5  mov     edx, 5Fh ; '_'
0x180057bfa  jmp     short loc_180057BEB
0x180057bfc  mov     qword ptr [rsi], 0
0x180057c03  jmp     loc_180057B5C
```
