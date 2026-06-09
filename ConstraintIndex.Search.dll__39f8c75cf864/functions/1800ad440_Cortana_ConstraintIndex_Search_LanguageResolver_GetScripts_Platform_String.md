# Cortana::ConstraintIndex::Search::LanguageResolver::GetScripts(Platform::String *)

- ea: `0x1800ad440`
- end: `0x1800ad62a`
- name: `?GetScripts@LanguageResolver@Search@ConstraintIndex@Cortana@@AE$AAAPE$AAU?$IVectorView@PE$AAVString@Platform@@@Collections@Foundation@Windows@@PE$AAVString@Platform@@@Z`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1800ace18`

## callees

- `0x1800049e0`
- `0x180005e44`
- `0x18000617a`
- `0x18000619e`
- `0x180009fa0`
- `0x18000c860`
- `0x18000cdf0`
- `0x180011728`
- `0x1800395d0`
- `0x18003a5f4`
- `0x18003e940`
- `0x18003feb4`
- `0x18003fee0`
- `0x180092490`
- `0x18009ca1c`
- `0x1800ab9b4`
- `0x1800abc90`
- `0x1800ac240`
- `0x1800ac3b8`
- `0x1800ad440`
- `0x1800ad6a0`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-normalization-l1-1-0!GetStringScripts` at `0x1800ad49a`
- `api-ms-win-core-normalization-l1-1-0!GetStringScripts` at `0x1800ad49a`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x1800ad4ff`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x1800ad4ff`

## string_xrefs

- `0x1800ad4ab`: `shellcommon\shell\cortana\constraintindex\src\Search\LanguageResolver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Cortana::ConstraintIndex::Search::LanguageResolver::GetScripts(__int64 a1, HSTRING a2)
{
  const WCHAR *StringRawBuffer_0; // rax
  __int64 v3; // r8
  const char *v4; // r9
  void *v5; // rax
  __int64 v6; // rbx
  __int64 v7; // rdi
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rsi
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rbx
  HSTRING v17; // [rsp+38h] [rbp-C8h]
  __int64 View__Q__IVector_PE_AAVString_Platform___Collections_Foundation_Windows____Vector_PE_AAVString_Platform__U__equal_to_PE_AAVString_Platform___std___00_2Platform__UE_AAAPE_AAU__IVectorView_PE_AAVString_Platform___234_XZ; // [rsp+38h] [rbp-C8h]
  _BYTE v19[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v20[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v21[240]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Scripts[264]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+2A8h]

  StringRawBuffer_0 = WindowsGetStringRawBuffer_0(a2, 0);
  v3 = -1;
  do
    ++v3;
  while ( StringRawBuffer_0[v3] );
  if ( !GetStringScripts(0, StringRawBuffer_0, v3, Scripts, 260) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xAA,
      (unsigned int)"shellcommon\\shell\\cortana\\constraintindex\\src\\Search\\LanguageResolver.cpp",
      v4);
  std::wstring::wstring(v20, Scripts);
  memset_0(v21, 0, sizeof(v21));
  std::wistringstream::wistringstream(v21, v20);
  std::wstring::wstring(v19);
  v5 = Platform::Details::Heap::Allocate(0x88u, 0xB0u);
  v6 = Platform::Collections::Vector<Platform::String __gc *,std::equal_to<Platform::String __gc *>,1>::Vector<Platform::String __gc *,std::equal_to<Platform::String __gc *>,1>(v5);
  v7 = __abi_winrt_ptr_ctor(v6);
  __abi_winrt_ptr_dtor(v6);
  while ( 1 )
  {
    v8 = std::getline<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v21, v19);
    if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v8 + 4LL) + v8 + 16) & 6) != 0 )
      break;
    v9 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v19);
    v17 = (HSTRING)Platform::String::String(v10, v9);
    _Append__Q__IVector_PE_AAVString_Platform___Collections_Foundation_Windows____Vector_PE_AAVString_Platform__U__equal_to_PE_AAVString_Platform___std___00_2Platform__UE_AAAXPE_AAVString_6__Z(
      v7,
      v17);
    WindowsDeleteString_0(v17);
  }
  View__Q__IVector_PE_AAVString_Platform___Collections_Foundation_Windows____Vector_PE_AAVString_Platform__U__equal_to_PE_AAVString_Platform___std___00_2Platform__UE_AAAPE_AAU__IVectorView_PE_AAVString_Platform___234_XZ = _GetView__Q__IVector_PE_AAVString_Platform___Collections_Foundation_Windows____Vector_PE_AAVString_Platform__U__equal_to_PE_AAVString_Platform___std___00_2Platform__UE_AAAPE_AAU__IVectorView_PE_AAVString_Platform___234_XZ(v7);
  v11 = __abi_winrt_ptr_ctor(View__Q__IVector_PE_AAVString_Platform___Collections_Foundation_Windows____Vector_PE_AAVString_Platform__U__equal_to_PE_AAVString_Platform___std___00_2Platform__UE_AAAPE_AAU__IVectorView_PE_AAVString_Platform___234_XZ);
  __abi_winrt_ptr_dtor(View__Q__IVector_PE_AAVString_Platform___Collections_Foundation_Windows____Vector_PE_AAVString_Platform__U__equal_to_PE_AAVString_Platform___std___00_2Platform__UE_AAAPE_AAU__IVectorView_PE_AAVString_Platform___234_XZ);
  LOBYTE(v12) = 1;
  v13 = __abi_winrt_cast_to(v12, v7, &_uuidof__AUIDisposable_Platform__);
  v15 = v13;
  if ( v13 )
  {
    Platform::IDisposable::_Dispose_(v13, v14);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  __abi_winrt_ptr_dtor(v7);
  std::wstring::_Tidy_deallocate(v19);
  std::wistringstream::`vbase destructor'(v21);
  std::wstring::_Tidy_deallocate(v20);
  return v11;
}

```

## disassembly

```asm
0x1800ad440  mov     [rsp-8+arg_0], rbx
0x1800ad445  mov     [rsp-8+arg_10], rsi
0x1800ad44a  push    rbp
0x1800ad44b  push    rdi
0x1800ad44c  push    r14
0x1800ad44e  lea     rbp, [rsp-290h]
0x1800ad456  sub     rsp, 390h
0x1800ad45d  mov     rax, cs:__security_cookie
0x1800ad464  xor     rax, rsp
0x1800ad467  mov     [rbp+2A0h+var_20], rax
0x1800ad46e  mov     rcx, rdx; string
0x1800ad471  xor     edx, edx; length
0x1800ad473  call    WindowsGetStringRawBuffer_0
0x1800ad478  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800ad47c  xor     r14d, r14d
0x1800ad47f  inc     r8; cchString
0x1800ad482  cmp     [rax+r8*2], r14w
0x1800ad487  jnz     short loc_1800AD47F
0x1800ad489  mov     [rsp+3A0h+cchScripts], 104h; cchScripts
0x1800ad491  lea     r9, [rbp+2A0h+Scripts]; lpScripts
0x1800ad495  mov     rdx, rax; lpString
0x1800ad498  xor     ecx, ecx; dwFlags
0x1800ad49a  call    cs:__imp_GetStringScripts
0x1800ad4a0  test    eax, eax
0x1800ad4a2  jnz     short loc_1800AD4BD
0x1800ad4a4  mov     rcx, [rbp+2A8h]; this
0x1800ad4ab  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\cortana\\constraint"...
0x1800ad4b2  mov     edx, 0AAh; void *
0x1800ad4b7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800ad4bd  lea     rdx, [rbp+2A0h+Scripts]
0x1800ad4c1  lea     rcx, [rsp+3A0h+var_340]
0x1800ad4c6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800ad4cb  nop
0x1800ad4cc  xor     edx, edx; Val
0x1800ad4ce  mov     r8d, 0F0h; Size
0x1800ad4d4  lea     rcx, [rbp+2A0h+var_320]; void *
0x1800ad4d8  call    memset_0
0x1800ad4dd  lea     rdx, [rsp+3A0h+var_340]
0x1800ad4e2  lea     rcx, [rbp+2A0h+var_320]
0x1800ad4e6  call    ??0?$basic_istringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::wistringstream::wistringstream(std::wstring const &,int)
0x1800ad4eb  nop
0x1800ad4ec  lea     rcx, [rsp+3A0h+var_360]
0x1800ad4f1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800ad4f6  nop
0x1800ad4f7  mov     edx, 0B0h
0x1800ad4fc  lea     ecx, [rdx-28h]
0x1800ad4ff  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x1800ad505  mov     [rsp+3A0h+var_370], rax
0x1800ad50a  mov     rcx, rax
0x1800ad50d  call    ??0?$Vector@PE$AAVString@Platform@@U?$equal_to@PE$AAVString@Platform@@@std@@$00@Collections@Platform@@QE$AAA@XZ; Platform::Collections::Vector<Platform::String *,std::equal_to<Platform::String *>,1>::Vector<Platform::String *,std::equal_to<Platform::String *>,1>(void)
0x1800ad512  mov     rbx, rax
0x1800ad515  mov     [rsp+3A0h+var_370], rax
0x1800ad51a  mov     rcx, rax
0x1800ad51d  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800ad522  mov     rdi, rax
0x1800ad525  mov     [rsp+3A0h+var_370], rax
0x1800ad52a  mov     rcx, rbx
0x1800ad52d  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800ad532  nop
0x1800ad533  lea     rdx, [rsp+3A0h+var_360]
0x1800ad538  lea     rcx, [rbp+2A0h+var_320]
0x1800ad53c  call    ??$getline@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@YAAEAV?$basic_istream@_WU?$char_traits@_W@std@@@0@$$QEAV10@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@_W@Z; std::getline<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(std::wistream &&,std::wstring &,wchar_t)
0x1800ad541  mov     rcx, [rax]
0x1800ad544  movsxd  rdx, dword ptr [rcx+4]
0x1800ad548  test    byte ptr [rdx+rax+10h], 6
0x1800ad54d  jnz     short loc_1800AD584
0x1800ad54f  mov     [rsp+3A0h+var_368], r14
0x1800ad554  lea     rcx, [rsp+3A0h+var_360]
0x1800ad559  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800ad55e  mov     rdx, rax
0x1800ad561  call    ??0String@Platform@@QE$AAA@PEB_W@Z; Platform::String::String(wchar_t const *)
0x1800ad566  mov     rbx, rax
0x1800ad569  mov     [rsp+3A0h+var_368], rax
0x1800ad56e  mov     rdx, rax
0x1800ad571  mov     rcx, rdi
0x1800ad574  call    ?Append@?Q?$IVector@PE$AAVString@Platform@@@Collections@Foundation@Windows@@?$Vector@PE$AAVString@Platform@@U?$equal_to@PE$AAVString@Platform@@@std@@$00@2Platform@@UE$AAAXPE$AAVString@6@@Z
0x1800ad579  nop
0x1800ad57a  mov     rcx, rbx; string
0x1800ad57d  call    WindowsDeleteString_0
0x1800ad582  jmp     short loc_1800AD533
0x1800ad584  mov     rcx, rdi
0x1800ad587  call    ?GetView@?Q?$IVector@PE$AAVString@Platform@@@Collections@Foundation@Windows@@?$Vector@PE$AAVString@Platform@@U?$equal_to@PE$AAVString@Platform@@@std@@$00@2Platform@@UE$AAAPE$AAU?$IVectorView@PE$AAVString@Platform@@@234@XZ
0x1800ad58c  mov     rbx, rax
0x1800ad58f  mov     [rsp+3A0h+var_368], rax
0x1800ad594  mov     rcx, rax
0x1800ad597  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800ad59c  mov     rsi, rax
0x1800ad59f  mov     rcx, rbx
0x1800ad5a2  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800ad5a7  nop
0x1800ad5a8  lea     r8, __uuidof_?AUIDisposable@Platform@@
0x1800ad5af  mov     rdx, rdi
0x1800ad5b2  mov     cl, 1
0x1800ad5b4  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x1800ad5b9  mov     rbx, rax
0x1800ad5bc  test    rax, rax
0x1800ad5bf  jz      short loc_1800AD5D8
0x1800ad5c1  mov     rcx, rax
0x1800ad5c4  call    ?_Dispose_@IDisposable@Platform@@UE$AAAXXZ; Platform::IDisposable::_Dispose_(void)
0x1800ad5c9  mov     rcx, [rbx]
0x1800ad5cc  mov     rax, [rcx+10h]
0x1800ad5d0  mov     rcx, rbx
0x1800ad5d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad5d8  mov     rcx, rdi
0x1800ad5db  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800ad5e0  nop
0x1800ad5e1  lea     rcx, [rsp+3A0h+var_360]
0x1800ad5e6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ad5eb  nop
0x1800ad5ec  lea     rcx, [rbp+2A0h+var_320]
0x1800ad5f0  call    ??_D?$basic_istringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAXXZ; std::wistringstream::`vbase destructor'(void)
0x1800ad5f5  nop
0x1800ad5f6  lea     rcx, [rsp+3A0h+var_340]
0x1800ad5fb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ad600  mov     rax, rsi
0x1800ad603  mov     rcx, [rbp+2A0h+var_20]
0x1800ad60a  xor     rcx, rsp; StackCookie
0x1800ad60d  call    __security_check_cookie
0x1800ad612  lea     r11, [rsp+3A0h+var_10]
0x1800ad61a  mov     rbx, [r11+20h]
0x1800ad61e  mov     rsi, [r11+30h]
0x1800ad622  mov     rsp, r11
0x1800ad625  pop     r14
0x1800ad627  pop     rdi
0x1800ad628  pop     rbp
0x1800ad629  retn
```
