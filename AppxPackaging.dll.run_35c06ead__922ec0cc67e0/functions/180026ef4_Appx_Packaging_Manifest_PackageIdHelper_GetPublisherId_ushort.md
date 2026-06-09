# Appx::Packaging::Manifest::PackageIdHelper::GetPublisherId(ushort * *)

- ea: `0x180026ef4`
- end: `0x180027035`
- name: `?GetPublisherId@PackageIdHelper@Manifest@Packaging@Appx@@AEAAJPEAPEAG@Z`
- size: `321`
- prototype: `int(Appx::Packaging::Manifest::PackageIdHelper *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180026b54`

## callees

- `0x180011a70`
- `0x1800133fc`
- `0x180026ef4`
- `0x180027400`
- `0x180071f50`
- `0x1800ad008`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026f67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026f67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026f4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026f4a`
- `OLEAUT32!__imp_SysFreeString` at `0x180026f9b`
- `OLEAUT32!__imp_SysFreeString` at `0x180026fdf`
- `OLEAUT32!__imp_SysFreeString` at `0x180026f9b`
- `OLEAUT32!__imp_SysFreeString` at `0x180026fdf`

## string_xrefs

- `0x180026fc6`: `onecore\printscan\appxpackaging\manifest\src\packageidhelper.cpp`
- `0x180026ff4`: `onecore\printscan\appxpackaging\manifest\src\packageidhelper.cpp`
- `0x18002701a`: `onecore\printscan\appxpackaging\manifest\src\packageidhelper.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::PackageIdHelper::GetPublisherId(
        Appx::Packaging::Manifest::PackageIdHelper *this,
        unsigned __int16 **a2)
{
  int AttributeValue; // eax
  unsigned int v5; // ebx
  unsigned int *v6; // rbx
  unsigned __int16 *v7; // r9
  unsigned int v8; // eax
  unsigned int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v12; // [rsp+30h] [rbp+8h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp+18h] BYREF

  if ( *((_QWORD *)this + 1) )
    goto LABEL_8;
  bstrString = 0;
  AttributeValue = Appx::Packaging::GetAttributeValue(this, L"Publisher", 2147549183LL, &bstrString);
  v5 = AttributeValue;
  if ( AttributeValue < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x160,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\packageidhelper.cpp",
      (const char *)(unsigned int)AttributeValue,
      v10);
  }
  else
  {
    v12 = 14;
    v6 = (unsigned int *)CoTaskMemAlloc(0x1Cu);
    if ( *((unsigned int **)this + 1) == v6 )
    {
      v6 = (unsigned int *)*((_QWORD *)this + 1);
    }
    else
    {
      CoTaskMemFree(*((LPVOID *)this + 1));
      *((_QWORD *)this + 1) = v6;
    }
    if ( v6 )
    {
      v8 = ARI::Internal::PackagePublisherIdFromPublisher(
             (ARI::Internal *)bstrString,
             (const unsigned __int16 *)&v12,
             v6,
             v7);
      if ( !v8 )
      {
        SysFreeString(bstrString);
LABEL_8:
        *a2 = (unsigned __int16 *)*((_QWORD *)this + 1);
        return 0;
      }
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x169,
             (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\packageidhelper.cpp",
             (const char *)v8,
             v10);
    }
    else
    {
      v5 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x164,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\packageidhelper.cpp",
        (const char *)0x8007000ELL,
        v10);
    }
  }
  SysFreeString(bstrString);
  return v5;
}

```

## disassembly

```asm
0x180026ef4  mov     rax, rsp
0x180026ef7  mov     [rax+10h], rbx
0x180026efb  mov     [rax+20h], rsi
0x180026eff  push    rdi; int
0x180026f00  sub     rsp, 20h
0x180026f04  cmp     qword ptr [rcx+8], 0
0x180026f09  mov     rsi, rdx
0x180026f0c  mov     rdi, rcx
0x180026f0f  jnz     loc_180026FA7
0x180026f15  lea     r9, [rax+18h]
0x180026f19  mov     qword ptr [rax+18h], 0
0x180026f21  mov     r8d, 8000FFFFh
0x180026f27  lea     rdx, ?Publisher@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Publisher"
0x180026f2e  call    ?GetAttributeValue@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBGJPEAPEAG@Z; Appx::Packaging::GetAttributeValue(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *,long,ushort * *)
0x180026f33  mov     ebx, eax
0x180026f35  test    eax, eax
0x180026f37  js      loc_180026FC1
0x180026f3d  mov     ecx, 1Ch; cb
0x180026f42  mov     [rsp+28h+arg_0], 0Eh
0x180026f4a  call    cs:__imp_CoTaskMemAlloc
0x180026f51  nop     dword ptr [rax+rax+00h]
0x180026f56  mov     rbx, rax
0x180026f59  cmp     [rdi+8], rax
0x180026f5d  jz      loc_18002700C
0x180026f63  mov     rcx, [rdi+8]; pv
0x180026f67  call    cs:__imp_CoTaskMemFree
0x180026f6e  nop     dword ptr [rax+rax+00h]
0x180026f73  mov     [rdi+8], rbx
0x180026f77  test    rbx, rbx
0x180026f7a  jz      loc_180027015
0x180026f80  mov     rcx, [rsp+28h+bstrString]; this
0x180026f85  lea     rdx, [rsp+28h+arg_0]; unsigned __int16 *
0x180026f8a  mov     r8, rbx; unsigned int *
0x180026f8d  call    ?PackagePublisherIdFromPublisher@Internal@ARI@@YAJPEBGPEAIPEAG@Z; ARI::Internal::PackagePublisherIdFromPublisher(ushort const *,uint *,ushort *)
0x180026f92  test    eax, eax
0x180026f94  jnz     short loc_180026FEF
0x180026f96  mov     rcx, [rsp+28h+bstrString]; bstrString
0x180026f9b  call    cs:__imp_SysFreeString
0x180026fa2  nop     dword ptr [rax+rax+00h]
0x180026fa7  mov     rax, [rdi+8]
0x180026fab  mov     [rsi], rax
0x180026fae  xor     eax, eax
0x180026fb0  mov     rbx, [rsp+28h+arg_8]
0x180026fb5  mov     rsi, [rsp+28h+arg_18]
0x180026fba  add     rsp, 20h
0x180026fbe  pop     rdi
0x180026fbf  retn
0x180026fc1  mov     rcx, [rsp+28h]; this
0x180026fc6  lea     r8, aOnecorePrintsc_149; "onecore\\printscan\\appxpackaging\\mani"...
0x180026fcd  mov     r9d, eax; char *
0x180026fd0  mov     edx, 160h; void *
0x180026fd5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180026fda  mov     rcx, [rsp+28h+bstrString]; bstrString
0x180026fdf  call    cs:__imp_SysFreeString
0x180026fe6  nop     dword ptr [rax+rax+00h]
0x180026feb  mov     eax, ebx
0x180026fed  jmp     short loc_180026FB0
0x180026fef  mov     rcx, [rsp+28h]; this
0x180026ff4  lea     r8, aOnecorePrintsc_149; "onecore\\printscan\\appxpackaging\\mani"...
0x180026ffb  mov     r9d, eax; char *
0x180026ffe  mov     edx, 169h; void *
0x180027003  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180027008  mov     ebx, eax
0x18002700a  jmp     short loc_180026FDA
0x18002700c  mov     rbx, [rdi+8]
0x180027010  jmp     loc_180026F77
0x180027015  mov     rcx, [rsp+28h]; this
0x18002701a  lea     r8, aOnecorePrintsc_149; "onecore\\printscan\\appxpackaging\\mani"...
0x180027021  mov     ebx, 8007000Eh
0x180027026  mov     edx, 164h; void *
0x18002702b  mov     r9d, ebx; char *
0x18002702e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027033  jmp     short loc_180026FDA
```
