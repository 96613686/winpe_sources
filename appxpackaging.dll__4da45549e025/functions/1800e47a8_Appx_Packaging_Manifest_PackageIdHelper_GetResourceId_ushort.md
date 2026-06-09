# Appx::Packaging::Manifest::PackageIdHelper::GetResourceId(ushort * *)

- ea: `0x1800e47a8`
- end: `0x1800e48f0`
- name: `?GetResourceId@PackageIdHelper@Manifest@Packaging@Appx@@QEAAJPEAPEAG@Z`
- size: `328`
- prototype: `int(Appx::Packaging::Manifest::PackageIdHelper *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800e3040`

## callees

- `0x180011a70`
- `0x1800133fc`
- `0x18001711c`
- `0x18001bb60`
- `0x180071f50`
- `0x1800e47a8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e487d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e48d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e487d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e48d1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e488d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e488d`

## string_xrefs

- `0x1800e47c6`: `onecore\printscan\appxpackaging\manifest\src\packageidhelper.cpp`
- `0x1800e481d`: `onecore\printscan\appxpackaging\manifest\src\packageidhelper.cpp`
- `0x1800e485a`: `onecore\printscan\appxpackaging\manifest\src\packageidhelper.cpp`
- `0x1800e48ae`: `onecore\printscan\appxpackaging\manifest\src\packageidhelper.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::PackageIdHelper::GetResourceId(
        Appx::Packaging::Manifest::PackageIdHelper *this,
        unsigned __int16 **a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rdx
  int AttributeValue; // eax
  OLECHAR *v6; // rcx
  int v7; // eax
  unsigned __int16 *v8; // rcx
  int v9; // eax
  BSTR v10; // rcx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+8h]
  BSTR bstrString; // [rsp+38h] [rbp+18h] BYREF
  unsigned __int16 *v15; // [rsp+40h] [rbp+20h] BYREF

  if ( !a2 )
  {
    v3 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA3,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\packageidhelper.cpp",
      (const char *)0x80004003LL,
      savedregs);
    return v3;
  }
  *a2 = 0;
  v4 = *((_QWORD *)this + 3);
  bstrString = 0;
  if ( !v4 )
  {
    AttributeValue = Appx::Packaging::GetAttributeValue(this, L"ResourceId", 0, &bstrString);
    v3 = AttributeValue;
    if ( AttributeValue >= 0 )
    {
      v6 = bstrString;
      if ( !bstrString )
      {
LABEL_12:
        SysFreeString(v6);
        return v3;
      }
      v15 = 0;
      v7 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoCoTaskMemStringAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoCoTaskMemStringDeallocate(unsigned short *)>::CopyFromBStr(
             &v15,
             bstrString);
      v3 = v7;
      if ( v7 >= 0 )
      {
        v8 = 0;
        *a2 = v15;
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xAF,
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\packageidhelper.cpp",
          (const char *)(unsigned int)v7,
          savedregs);
        v8 = v15;
      }
      CoTaskMemFree(v8);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xAA,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\packageidhelper.cpp",
        (const char *)(unsigned int)AttributeValue,
        savedregs);
    }
    v6 = bstrString;
    goto LABEL_12;
  }
  v9 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoCoTaskMemStringAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoCoTaskMemStringDeallocate(unsigned short *)>::CopyFromString(
         &bstrString,
         v4);
  v3 = v9;
  if ( v9 >= 0 )
  {
    v10 = 0;
    *a2 = bstrString;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\packageidhelper.cpp",
      (const char *)(unsigned int)v9,
      savedregs);
    v10 = bstrString;
  }
  CoTaskMemFree(v10);
  return v3;
}

```

## disassembly

```asm
0x1800e47a8  mov     [rsp-8+arg_0], rbx
0x1800e47ad  mov     [rsp-8+arg_18], rdi
0x1800e47b2  push    rbp; int
0x1800e47b3  mov     rbp, rsp
0x1800e47b6  sub     rsp, 20h
0x1800e47ba  mov     rdi, rdx
0x1800e47bd  test    rdx, rdx
0x1800e47c0  jnz     short loc_1800E47E4
0x1800e47c2  mov     rcx, [rbp+8]; this
0x1800e47c6  lea     r8, aOnecorePrintsc_149; "onecore\\printscan\\appxpackaging\\mani"...
0x1800e47cd  mov     ebx, 80004003h
0x1800e47d2  mov     edx, 0A3h; void *
0x1800e47d7  mov     r9d, ebx; char *
0x1800e47da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e47df  jmp     loc_1800E48DD
0x1800e47e4  mov     qword ptr [rdx], 0
0x1800e47eb  mov     rdx, [rcx+18h]
0x1800e47ef  mov     [rbp+bstrString], 0
0x1800e47f7  test    rdx, rdx
0x1800e47fa  jnz     loc_1800E489B
0x1800e4800  lea     r9, [rbp+bstrString]
0x1800e4804  xor     r8d, r8d
0x1800e4807  lea     rdx, ?ResourceId@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "ResourceId"
0x1800e480e  call    ?GetAttributeValue@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBGJPEAPEAG@Z; Appx::Packaging::GetAttributeValue(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *,long,ushort * *)
0x1800e4813  mov     ebx, eax
0x1800e4815  test    eax, eax
0x1800e4817  jns     short loc_1800E4833
0x1800e4819  mov     rcx, [rbp+8]; this
0x1800e481d  lea     r8, aOnecorePrintsc_149; "onecore\\printscan\\appxpackaging\\mani"...
0x1800e4824  mov     r9d, eax; char *
0x1800e4827  mov     edx, 0AAh; void *
0x1800e482c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e4831  jmp     short loc_1800E4889
0x1800e4833  mov     rcx, [rbp+bstrString]
0x1800e4837  test    rcx, rcx
0x1800e483a  jz      short loc_1800E488D
0x1800e483c  mov     rdx, rcx
0x1800e483f  mov     [rbp+arg_10], 0
0x1800e4847  lea     rcx, [rbp+arg_10]
0x1800e484b  call    ?CopyFromBStr@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJQEAG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromBStr(ushort * const)
0x1800e4850  mov     ebx, eax
0x1800e4852  test    eax, eax
0x1800e4854  jns     short loc_1800E4874
0x1800e4856  mov     rcx, [rbp+8]; this
0x1800e485a  lea     r8, aOnecorePrintsc_149; "onecore\\printscan\\appxpackaging\\mani"...
0x1800e4861  mov     r9d, eax; char *
0x1800e4864  mov     edx, 0AFh; void *
0x1800e4869  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e486e  mov     rcx, [rbp+arg_10]
0x1800e4872  jmp     short loc_1800E487D
0x1800e4874  mov     rax, [rbp+arg_10]
0x1800e4878  xor     ecx, ecx; pv
0x1800e487a  mov     [rdi], rax
0x1800e487d  call    cs:__imp_CoTaskMemFree
0x1800e4884  nop     dword ptr [rax+rax+00h]
0x1800e4889  mov     rcx, [rbp+bstrString]; bstrString
0x1800e488d  call    cs:__imp_SysFreeString
0x1800e4894  nop     dword ptr [rax+rax+00h]
0x1800e4899  jmp     short loc_1800E48DD
0x1800e489b  lea     rcx, [rbp+bstrString]
0x1800e489f  call    ?CopyFromString@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJPEBG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromString(ushort const *)
0x1800e48a4  mov     ebx, eax
0x1800e48a6  test    eax, eax
0x1800e48a8  jns     short loc_1800E48C8
0x1800e48aa  mov     rcx, [rbp+8]; this
0x1800e48ae  lea     r8, aOnecorePrintsc_149; "onecore\\printscan\\appxpackaging\\mani"...
0x1800e48b5  mov     r9d, eax; char *
0x1800e48b8  mov     edx, 0B6h; void *
0x1800e48bd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e48c2  mov     rcx, [rbp+bstrString]
0x1800e48c6  jmp     short loc_1800E48D1
0x1800e48c8  mov     rax, [rbp+bstrString]
0x1800e48cc  xor     ecx, ecx; pv
0x1800e48ce  mov     [rdi], rax
0x1800e48d1  call    cs:__imp_CoTaskMemFree
0x1800e48d8  nop     dword ptr [rax+rax+00h]
0x1800e48dd  mov     rdi, [rsp+20h+arg_18]
0x1800e48e2  mov     eax, ebx
0x1800e48e4  mov     rbx, [rsp+20h+arg_0]
0x1800e48e9  add     rsp, 20h
0x1800e48ed  pop     rbp
0x1800e48ee  retn
```
