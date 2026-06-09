# PrintDeviceCapabilitiesOM::PrintDeviceResources::Initialize(void)

- ea: `0x18003f098`
- end: `0x18003f2b1`
- name: `?Initialize@PrintDeviceResources@PrintDeviceCapabilitiesOM@@AEAAXXZ`
- size: `537`
- prototype: `void __fastcall(PrintDeviceCapabilitiesOM::PrintDeviceResources *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800386b8`

## callees

- `0x18003b7a4`
- `0x18003cf78`
- `0x18003e0e0`
- `0x18003f098`
- `0x18003f2dc`
- `0x180040d3c`
- `0x180048010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18003f19e`
- `OLEAUT32!__imp_VariantClear` at `0x18003f1fd`
- `OLEAUT32!__imp_VariantClear` at `0x18003f19e`
- `OLEAUT32!__imp_VariantClear` at `0x18003f1fd`

## string_xrefs

- `0x18003f0ca`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x18003f151`: `XPath`
- `0x18003f1c2`: `xmlns:msdata='urn:schemas-microsoft-com:xml-msdata' xmlns:xsd='http://www.w3.org/2001/XMLSchema' xmlns:xsi='http://www.w3.org/2001/XMLSchema-instance' `

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall PrintDeviceCapabilitiesOM::PrintDeviceResources::Initialize(
        PrintDeviceCapabilitiesOM::PrintDeviceResources *this)
{
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD, __int128 *); // rbx
  __int128 *v7; // rax
  unsigned int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, LONGLONG, __int128 *); // rbx
  __int128 *v11; // rax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, char *); // rbx
  PrintCore::BStrRAII *v14; // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-49h] BYREF
  _QWORD v16[3]; // [rsp+38h] [rbp-31h] BYREF
  __int128 v17; // [rsp+50h] [rbp-19h] BYREF
  __int64 v18; // [rsp+60h] [rbp-9h]
  VARIANTARG v19; // [rsp+70h] [rbp+7h] BYREF

  v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)this + 504LL))(*(_QWORD *)this, 0);
  PrintCore::ThrowIfError(
    (PrintCore *)v2,
    "Unspecified.",
    "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
    (const char *)0x506,
    *(unsigned int *)&pvarg.vt);
  v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)this + 544LL))(*(_QWORD *)this, 0);
  PrintCore::ThrowIfError(
    (PrintCore *)v3,
    "Unspecified.",
    "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
    (const char *)0x507,
    *(unsigned int *)&pvarg.vt);
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)this + 560LL))(*(_QWORD *)this, 0);
  PrintCore::ThrowIfError(
    (PrintCore *)v4,
    "Unspecified.",
    "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
    (const char *)0x508,
    *(unsigned int *)&pvarg.vt);
  PrintCore::BStrRAII::BStrRAII((PrintCore::BStrRAII *)v16, L"SelectionLanguage");
  v5 = *(_QWORD *)this;
  v6 = *(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(**(_QWORD **)this + 640LL);
  v7 = (__int128 *)PrintCore::VariantRAII::VariantRAII((PrintCore::VariantRAII *)&pvarg, L"XPath");
  v17 = *v7;
  v18 = *((_QWORD *)v7 + 2);
  v8 = v6(v5, v16[1], &v17);
  PrintCore::ThrowIfError(
    (PrintCore *)v8,
    "Unspecified.",
    "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
    (const char *)0x50C,
    *(unsigned int *)&pvarg.vt);
  VariantClear(&pvarg);
  PrintCore::BStrRAII::BStrRAII((PrintCore::BStrRAII *)&pvarg, L"SelectionNamespaces");
  v9 = *(_QWORD *)this;
  v10 = *(__int64 (__fastcall **)(__int64, LONGLONG, __int128 *))(**(_QWORD **)this + 640LL);
  v11 = (__int128 *)PrintCore::VariantRAII::VariantRAII(
                      (PrintCore::VariantRAII *)&v19,
                      L"xmlns:msdata='urn:schemas-microsoft-com:xml-msdata' xmlns:xsd='http://www.w3.org/2001/XMLSchema' x"
                       "mlns:xsi='http://www.w3.org/2001/XMLSchema-instance' ");
  v17 = *v11;
  v18 = *((_QWORD *)v11 + 2);
  LODWORD(v10) = v10(v9, pvarg.llVal, &v17);
  VariantClear(&v19);
  if ( (_DWORD)v10 )
    PrintCore::ThrowIfError(
      (PrintCore *)0x8000FFFFLL,
      "Unspecified.",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
      (const char *)0x517,
      *(unsigned int *)&pvarg.vt);
  v12 = *(_QWORD *)this;
  v13 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(**(_QWORD **)this + 296LL);
  v14 = PrintCore::BStrRAII::BStrRAII((PrintCore::BStrRAII *)&v17, L"root");
  LODWORD(v13) = v13(v12, *((_QWORD *)v14 + 1), (char *)this + 8);
  PrintCore::ThrowIfError(
    (PrintCore *)(unsigned int)v13,
    "Unspecified.",
    "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
    (const char *)0x51E,
    *(unsigned int *)&pvarg.vt);
  *(_QWORD *)&v17 = &PrintCore::BStrRAII::`vftable';
  PrintCore::BStrRAII::Clean((PrintCore::BStrRAII *)&v17);
  if ( (_DWORD)v13 == 1 )
    Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(this);
  *(_QWORD *)&pvarg.vt = &PrintCore::BStrRAII::`vftable';
  PrintCore::BStrRAII::Clean((PrintCore::BStrRAII *)&pvarg);
  v16[0] = &PrintCore::BStrRAII::`vftable';
  PrintCore::BStrRAII::Clean((PrintCore::BStrRAII *)v16);
}

```

## disassembly

```asm
0x18003f098  push    rbp
0x18003f09a  push    rbx
0x18003f09b  push    rsi
0x18003f09c  push    rdi
0x18003f09d  push    r14
0x18003f09f  push    r15
0x18003f0a1  lea     rbp, [rsp-2Fh]
0x18003f0a6  sub     rsp, 98h
0x18003f0ad  mov     rsi, rcx
0x18003f0b0  mov     rcx, [rcx]
0x18003f0b3  mov     rax, [rcx]
0x18003f0b6  xor     edx, edx
0x18003f0b8  mov     rax, [rax+1F8h]
0x18003f0bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f0c4  mov     r9d, 506h; char *
0x18003f0ca  lea     r14, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003f0d1  mov     r8, r14; char *
0x18003f0d4  lea     r15, aUnspecified; "Unspecified."
0x18003f0db  mov     rdx, r15; char *
0x18003f0de  mov     ecx, eax; this
0x18003f0e0  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18003f0e5  mov     rcx, [rsi]
0x18003f0e8  mov     rax, [rcx]
0x18003f0eb  xor     edx, edx
0x18003f0ed  mov     rax, [rax+220h]
0x18003f0f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f0f9  mov     r9d, 507h; char *
0x18003f0ff  mov     r8, r14; char *
0x18003f102  mov     rdx, r15; char *
0x18003f105  mov     ecx, eax; this
0x18003f107  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18003f10c  mov     rcx, [rsi]
0x18003f10f  mov     rax, [rcx]
0x18003f112  xor     edx, edx
0x18003f114  mov     rax, [rax+230h]
0x18003f11b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f120  mov     r9d, 508h; char *
0x18003f126  mov     r8, r14; char *
0x18003f129  mov     rdx, r15; char *
0x18003f12c  mov     ecx, eax; this
0x18003f12e  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18003f133  lea     rdx, aSelectionlangu; "SelectionLanguage"
0x18003f13a  lea     rcx, [rbp+57h+var_88]; this
0x18003f13e  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x18003f143  nop
0x18003f144  mov     rdi, [rsi]
0x18003f147  mov     rax, [rdi]
0x18003f14a  mov     rbx, [rax+280h]
0x18003f151  lea     rdx, aXpath; "XPath"
0x18003f158  lea     rcx, [rbp+57h+pvarg]; this
0x18003f15c  call    ??0VariantRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::VariantRAII::VariantRAII(ushort const *)
0x18003f161  nop
0x18003f162  movups  xmm0, xmmword ptr [rax]
0x18003f165  movaps  [rbp+57h+var_70], xmm0
0x18003f169  movsd   xmm1, qword ptr [rax+10h]
0x18003f16e  movsd   [rbp+57h+var_60], xmm1
0x18003f173  lea     r8, [rbp+57h+var_70]
0x18003f177  mov     rdx, [rbp+57h+var_80]
0x18003f17b  mov     rcx, rdi
0x18003f17e  mov     rax, rbx
0x18003f181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f186  mov     r9d, 50Ch; char *
0x18003f18c  mov     r8, r14; char *
0x18003f18f  mov     rdx, r15; char *
0x18003f192  mov     ecx, eax; this
0x18003f194  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18003f199  nop
0x18003f19a  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18003f19e  call    cs:__imp_VariantClear
0x18003f1a4  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x18003f1ab  lea     rcx, [rbp+57h+pvarg]; this
0x18003f1af  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x18003f1b4  nop
0x18003f1b5  mov     rdi, [rsi]
0x18003f1b8  mov     rax, [rdi]
0x18003f1bb  mov     rbx, [rax+280h]
0x18003f1c2  lea     rdx, aXmlnsMsdataUrn; "xmlns:msdata='urn:schemas-microsoft-com"...
0x18003f1c9  lea     rcx, [rbp+57h+var_50]; this
0x18003f1cd  call    ??0VariantRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::VariantRAII::VariantRAII(ushort const *)
0x18003f1d2  nop
0x18003f1d3  movups  xmm0, xmmword ptr [rax]
0x18003f1d6  movaps  [rbp+57h+var_70], xmm0
0x18003f1da  movsd   xmm1, qword ptr [rax+10h]
0x18003f1df  movsd   [rbp+57h+var_60], xmm1
0x18003f1e4  lea     r8, [rbp+57h+var_70]
0x18003f1e8  mov     rdx, qword ptr [rbp+57h+pvarg+8]
0x18003f1ec  mov     rcx, rdi
0x18003f1ef  mov     rax, rbx
0x18003f1f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f1f7  mov     ebx, eax
0x18003f1f9  lea     rcx, [rbp+57h+var_50]; pvarg
0x18003f1fd  call    cs:__imp_VariantClear
0x18003f203  test    ebx, ebx
0x18003f205  jz      short loc_18003F21D
0x18003f207  mov     r9d, 517h; char *
0x18003f20d  mov     r8, r14; char *
0x18003f210  mov     rdx, r15; char *
0x18003f213  mov     ecx, 8000FFFFh; this
0x18003f218  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18003f21d  mov     rdi, [rsi]
0x18003f220  mov     rax, [rdi]
0x18003f223  mov     rbx, [rax+128h]
0x18003f22a  lea     rdx, aRoot; "root"
0x18003f231  lea     rcx, [rbp+57h+var_70]; this
0x18003f235  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x18003f23a  nop
0x18003f23b  lea     r8, [rsi+8]
0x18003f23f  mov     rdx, [rax+8]
0x18003f243  mov     rcx, rdi
0x18003f246  mov     rax, rbx
0x18003f249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f24e  mov     ebx, eax
0x18003f250  mov     r9d, 51Eh; char *
0x18003f256  mov     r8, r14; char *
0x18003f259  mov     rdx, r15; char *
0x18003f25c  mov     ecx, eax; this
0x18003f25e  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18003f263  nop
0x18003f264  lea     rdi, ??_7BStrRAII@PrintCore@@6B@; const PrintCore::BStrRAII::`vftable'
0x18003f26b  mov     qword ptr [rbp+57h+var_70], rdi
0x18003f26f  lea     rcx, [rbp+57h+var_70]; this
0x18003f273  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x18003f278  cmp     ebx, 1
0x18003f27b  jnz     short loc_18003F286
0x18003f27d  mov     rcx, rsi
0x18003f280  call    ?InternalRelease@?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(void)
0x18003f285  nop
0x18003f286  mov     qword ptr [rbp+57h+pvarg], rdi
0x18003f28a  lea     rcx, [rbp+57h+pvarg]; this
0x18003f28e  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x18003f293  nop
0x18003f294  mov     [rbp+57h+var_88], rdi
0x18003f298  lea     rcx, [rbp+57h+var_88]; this
0x18003f29c  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x18003f2a1  add     rsp, 98h
0x18003f2a8  pop     r15
0x18003f2aa  pop     r14
0x18003f2ac  pop     rdi
0x18003f2ad  pop     rsi
0x18003f2ae  pop     rbx
0x18003f2af  pop     rbp
0x18003f2b0  retn
```
