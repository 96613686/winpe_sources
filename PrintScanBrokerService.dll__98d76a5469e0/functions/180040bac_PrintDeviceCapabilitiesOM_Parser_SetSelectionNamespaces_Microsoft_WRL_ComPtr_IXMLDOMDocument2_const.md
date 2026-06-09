# PrintDeviceCapabilitiesOM::Parser::SetSelectionNamespaces(Microsoft::WRL::ComPtr<IXMLDOMDocument2> const &)

- ea: `0x180040bac`
- end: `0x180040c66`
- name: `?SetSelectionNamespaces@Parser@PrintDeviceCapabilitiesOM@@YAXAEBV?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@@Z`
- size: `186`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003c620`

## callees

- `0x18003b7a4`
- `0x18003cf78`
- `0x18003e0e0`
- `0x180040bac`
- `0x180040d3c`
- `0x180048010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180040c19`
- `OLEAUT32!__imp_VariantClear` at `0x180040c19`

## string_xrefs

- `0x180040c29`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x180040bd8`: `xmlns:psf='http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework' xmlns:psf2='http://schemas.microsoft.com/windows/2013/12/printing/printschemaframework2' xmlns:psk='http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords' xmlns:psk11='http://schemas.microsoft.com/windows/2013/05/printing/printschemakeywordsv11' xmlns:psk12='http://schemas.microsoft.com/windows/2013/12/printing/printschemakeywordsv12' xmlns:ns0000='http://schemas.microsoft.com/windows/2018/`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall PrintDeviceCapabilitiesOM::Parser::SetSelectionNamespaces(__int64 *a1)
{
  __int64 v2; // rdi
  __int64 (__fastcall *v3)(__int64, _QWORD, __int128 *); // rbx
  __int128 *v4; // rax
  _QWORD v5[2]; // [rsp+20h] [rbp-58h] BYREF
  __int128 v6; // [rsp+30h] [rbp-48h] BYREF
  __int64 v7; // [rsp+40h] [rbp-38h]
  VARIANTARG pvarg; // [rsp+50h] [rbp-28h] BYREF

  PrintCore::BStrRAII::BStrRAII((PrintCore::BStrRAII *)v5, L"SelectionNamespaces");
  v2 = *a1;
  v3 = *(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)*a1 + 640LL);
  v4 = (__int128 *)PrintCore::VariantRAII::VariantRAII(
                     (PrintCore::VariantRAII *)&pvarg,
                     L"xmlns:psf='http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework' xmlns:psf2='"
                      "http://schemas.microsoft.com/windows/2013/12/printing/printschemaframework2' xmlns:psk='http://sch"
                      "emas.microsoft.com/windows/2003/08/printing/printschemakeywords' xmlns:psk11='http://schemas.micro"
                      "soft.com/windows/2013/05/printing/printschemakeywordsv11' xmlns:psk12='http://schemas.microsoft.co"
                      "m/windows/2013/12/printing/printschemakeywordsv12' xmlns:ns0000='http://schemas.microsoft.com/wind"
                      "ows/2018/04/printing/printschemakeywords/Ipp' xmlns:xsd='http://www.w3.org/2001/XMLSchema' xmlns:x"
                      "si='http://www.w3.org/2001/XMLSchema-instance' ");
  v6 = *v4;
  v7 = *((_QWORD *)v4 + 2);
  LODWORD(v3) = v3(v2, v5[1], &v6);
  VariantClear(&pvarg);
  if ( (_DWORD)v3 )
    PrintCore::ThrowIfError(
      (PrintCore *)0x8000FFFFLL,
      "Unspecified.",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
      (const char *)0x21C,
      v5[0]);
  v5[0] = &PrintCore::BStrRAII::`vftable';
  PrintCore::BStrRAII::Clean((PrintCore::BStrRAII *)v5);
}

```

## disassembly

```asm
0x180040bac  mov     [rsp+arg_0], rbx
0x180040bb1  push    rdi
0x180040bb2  sub     rsp, 70h
0x180040bb6  mov     rbx, rcx
0x180040bb9  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x180040bc0  lea     rcx, [rsp+78h+var_58]; this
0x180040bc5  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x180040bca  nop
0x180040bcb  mov     rdi, [rbx]
0x180040bce  mov     rax, [rdi]
0x180040bd1  mov     rbx, [rax+280h]
0x180040bd8  lea     rdx, aXmlnsPsfHttpSc; "xmlns:psf='http://schemas.microsoft.com"...
0x180040bdf  lea     rcx, [rsp+78h+pvarg]; this
0x180040be4  call    ??0VariantRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::VariantRAII::VariantRAII(ushort const *)
0x180040be9  nop
0x180040bea  movups  xmm0, xmmword ptr [rax]
0x180040bed  movaps  [rsp+78h+var_48], xmm0
0x180040bf2  movsd   xmm1, qword ptr [rax+10h]
0x180040bf7  movsd   [rsp+78h+var_38], xmm1
0x180040bfd  lea     r8, [rsp+78h+var_48]
0x180040c02  mov     rdx, [rsp+78h+var_50]
0x180040c07  mov     rcx, rdi
0x180040c0a  mov     rax, rbx
0x180040c0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c12  mov     ebx, eax
0x180040c14  lea     rcx, [rsp+78h+pvarg]; pvarg
0x180040c19  call    cs:__imp_VariantClear
0x180040c1f  test    ebx, ebx
0x180040c21  jz      short loc_180040C42
0x180040c23  mov     r9d, 21Ch; char *
0x180040c29  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180040c30  lea     rdx, aUnspecified; "Unspecified."
0x180040c37  mov     ecx, 8000FFFFh; this
0x180040c3c  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x180040c41  nop
0x180040c42  lea     rax, ??_7BStrRAII@PrintCore@@6B@; const PrintCore::BStrRAII::`vftable'
0x180040c49  mov     [rsp+78h+var_58], rax
0x180040c4e  lea     rcx, [rsp+78h+var_58]; this
0x180040c53  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x180040c58  mov     rbx, [rsp+78h+arg_0]
0x180040c60  add     rsp, 70h
0x180040c64  pop     rdi
0x180040c65  retn
```
