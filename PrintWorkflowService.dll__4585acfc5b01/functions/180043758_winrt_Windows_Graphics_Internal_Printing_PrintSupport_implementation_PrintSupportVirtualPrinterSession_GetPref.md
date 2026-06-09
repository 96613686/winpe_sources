# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::GetPreferredPdlTempFileName(winrt::hstring const &)

- ea: `0x180043758`
- end: `0x180043905`
- name: `?GetPreferredPdlTempFileName@PrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAA?AUhstring@8@AEBU98@@Z`
- size: `429`
- prototype: `winrt::hstring *__fastcall(__int64, winrt::hstring *, winrt::hstring *)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180042dc8`

## callees

- `0x180003ca0`
- `0x18000495c`
- `0x180009718`
- `0x18000a724`
- `0x1800127a4`
- `0x1800129dc`
- `0x180012b10`
- `0x180036004`
- `0x1800421f4`
- `0x180043758`
- `0x180045c8c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800437a1`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800437a1`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180043888`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180043888`

## string_xrefs

- `0x1800438de`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportvirtualprintersession.cpp`
- `0x1800438f3`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportvirtualprintersession.cpp`
- `0x18004381d`: `.temp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
winrt::hstring *__fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::GetPreferredPdlTempFileName(
        __int64 a1,
        winrt::hstring *a2,
        winrt::hstring *a3)
{
  HRESULT v6; // eax
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // r8
  __int64 v11; // r9
  const WCHAR *v12; // rax
  PCWSTR v13; // r8
  HRESULT v14; // eax
  int v16[4]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v17[8]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v18[2]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v19[8]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v20[16]; // [rsp+50h] [rbp-B0h] BYREF
  GUID pguid; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v18[0] = a2;
  pguid = 0;
  v6 = CoCreateGuid(&pguid);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x208,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportvirtualprintersession.cpp",
      (const char *)(unsigned int)v6,
      v16[0]);
  *(GUID *)v16 = pguid;
  v7 = winrt::to_hstring(v18, v16);
  v8 = winrt::operator+(v19, a1 + 184, L"_PreferredPdl_");
  winrt::hstring::operator std::basic_string_view<unsigned short>(v7, v16, v9, v8);
  winrt::hstring::operator std::basic_string_view<unsigned short>(v11, v20, v10, v11);
  winrt::impl::concat_hstring(v17, v20, v16);
  winrt::operator+(v16, v17, L".temp");
  winrt::handle_type<winrt::impl::hstring_traits>::close(v17);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v19);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v18);
  memset_0(pszPathOut, 0, 0x208u);
  winrt::hstring::c_str(a3);
  v12 = winrt::hstring::c_str((winrt::hstring *)v16);
  v14 = PathCchCombine(pszPathOut, 0x104u, v13, v12);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x20B,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportvirtualprintersession.cpp",
      (const char *)(unsigned int)v14,
      v16[0]);
  winrt::hstring::hstring(a2, pszPathOut);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v16);
  return a2;
}

```

## disassembly

```asm
0x180043758  mov     [rsp-8+arg_0], rbx
0x18004375d  mov     [rsp-8+arg_18], rsi
0x180043762  push    rbp
0x180043763  push    rdi
0x180043764  push    r14
0x180043766  lea     rbp, [rsp-190h]
0x18004376e  sub     rsp, 290h
0x180043775  mov     rax, cs:__security_cookie
0x18004377c  xor     rax, rsp
0x18004377f  mov     [rbp+1A0h+var_20], rax
0x180043786  mov     r14, r8
0x180043789  mov     rdi, rdx
0x18004378c  mov     rsi, rcx
0x18004378f  mov     [rsp+2A0h+var_268], rdx
0x180043794  xorps   xmm0, xmm0
0x180043797  movups  xmmword ptr [rsp+2A0h+pguid.Data1], xmm0
0x18004379c  lea     rcx, [rsp+2A0h+pguid]; pguid
0x1800437a1  call    cs:__imp_CoCreateGuid
0x1800437a7  mov     rcx, [rbp+1A8h]; this
0x1800437ae  test    eax, eax
0x1800437b0  js      loc_1800438F0
0x1800437b6  movaps  xmm0, xmmword ptr [rsp+2A0h+pguid.Data1]
0x1800437bb  movdqa  xmmword ptr [rsp+2A0h+var_280], xmm0; int
0x1800437c1  lea     rdx, [rsp+2A0h+var_280]
0x1800437c6  lea     rcx, [rsp+2A0h+var_268]
0x1800437cb  call    ?to_hstring@winrt@@YA?AUhstring@1@AEBUguid@1@@Z; winrt::to_hstring(winrt::guid const &)
0x1800437d0  mov     rbx, rax
0x1800437d3  lea     rdx, [rsi+0B8h]
0x1800437da  lea     r8, aPreferredpdl; "_PreferredPdl_"
0x1800437e1  lea     rcx, [rsp+2A0h+var_258]
0x1800437e6  call    ??Hwinrt@@YA?AUhstring@0@AEBU10@PEBG@Z; winrt::operator+(winrt::hstring const &,ushort const *)
0x1800437eb  mov     r9, rax
0x1800437ee  lea     rdx, [rsp+2A0h+var_280]
0x1800437f3  mov     rcx, rbx
0x1800437f6  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x1800437fb  lea     rdx, [rsp+2A0h+var_250]
0x180043800  mov     rcx, r9
0x180043803  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x180043808  lea     r8, [rsp+2A0h+var_280]
0x18004380d  lea     rdx, [rsp+2A0h+var_250]
0x180043812  lea     rcx, [rsp+2A0h+var_270]
0x180043817  call    ?concat_hstring@impl@winrt@@YA?AUhstring@2@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@0@Z; winrt::impl::concat_hstring(std::basic_string_view<ushort> const &,std::basic_string_view<ushort> const &)
0x18004381c  nop
0x18004381d  lea     r8, aTemp; ".temp"
0x180043824  lea     rdx, [rsp+2A0h+var_270]
0x180043829  lea     rcx, [rsp+2A0h+var_280]
0x18004382e  call    ??Hwinrt@@YA?AUhstring@0@AEBU10@PEBG@Z; winrt::operator+(winrt::hstring const &,ushort const *)
0x180043833  nop
0x180043834  lea     rcx, [rsp+2A0h+var_270]
0x180043839  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18004383e  nop
0x18004383f  lea     rcx, [rsp+2A0h+var_258]
0x180043844  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180043849  nop
0x18004384a  lea     rcx, [rsp+2A0h+var_268]
0x18004384f  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180043854  xor     edx, edx; Val
0x180043856  mov     r8d, 208h; Size
0x18004385c  lea     rcx, [rsp+2A0h+pszPathOut]; void *
0x180043861  call    memset_0
0x180043866  mov     rcx, r14; this
0x180043869  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18004386e  mov     r8, rax
0x180043871  lea     rcx, [rsp+2A0h+var_280]; this
0x180043876  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18004387b  mov     r9, rax; pszMore
0x18004387e  mov     edx, 104h; cchPathOut
0x180043883  lea     rcx, [rsp+2A0h+pszPathOut]; pszPathOut
0x180043888  call    cs:__imp_PathCchCombine
0x18004388e  mov     rcx, [rbp+1A8h]; this
0x180043895  test    eax, eax
0x180043897  js      short loc_1800438DB
0x180043899  lea     rdx, [rsp+2A0h+pszPathOut]; unsigned __int16 *
0x18004389e  mov     rcx, rdi; this
0x1800438a1  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800438a6  nop
0x1800438a7  lea     rcx, [rsp+2A0h+var_280]
0x1800438ac  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800438b1  mov     rax, rdi
0x1800438b4  mov     rcx, [rbp+1A0h+var_20]
0x1800438bb  xor     rcx, rsp; StackCookie
0x1800438be  call    __security_check_cookie
0x1800438c3  lea     r11, [rsp+2A0h+var_10]
0x1800438cb  mov     rbx, [r11+20h]
0x1800438cf  mov     rsi, [r11+38h]
0x1800438d3  mov     rsp, r11
0x1800438d6  pop     r14
0x1800438d8  pop     rdi
0x1800438d9  pop     rbp
0x1800438da  retn
0x1800438db  mov     r9d, eax; char *
0x1800438de  lea     r8, aOnecoreuapPrin_20; "onecoreuap\\printscan\\print\\workflow"...
0x1800438e5  mov     edx, 20Bh; void *
0x1800438ea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800438f0  mov     r9d, eax; char *
0x1800438f3  lea     r8, aOnecoreuapPrin_20; "onecoreuap\\printscan\\print\\workflow"...
0x1800438fa  mov     edx, 208h; void *
0x1800438ff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
