# ReadAllBytesInTextModeForConstraintIndex(wchar_t const *)

- ea: `0x18003c9d8`
- end: `0x18003cd27`
- name: `?ReadAllBytesInTextModeForConstraintIndex@@YA?AV?$vector@DV?$allocator@D@std@@@std@@PEB_W@Z`
- size: `847`
- prototype: ``
- caller_count: `3`
- callee_count: `20`
- tags: ``

## callers

- `0x18003ab7c`
- `0x1800a67b0`
- `0x1800a6950`

## callees

- `0x1800049e0`
- `0x18000505c`
- `0x1800050c4`
- `0x180005e44`
- `0x18000616e`
- `0x18000b264`
- `0x18000cfdc`
- `0x18000e5b4`
- `0x18000f09c`
- `0x18002ab24`
- `0x18002b0b0`
- `0x18002b184`
- `0x180039768`
- `0x180039fd4`
- `0x18003a2e0`
- `0x18003a660`
- `0x18003b2f4`
- `0x18003c9d8`
- `0x18003fd04`
- `0x180040778`

## import_xrefs

- `wincorlib!??0FailureException@Platform@@QE$AAA@PE$AAVString@1@@Z` at `0x18003cc47`
- `wincorlib!??0FailureException@Platform@@QE$AAA@PE$AAVString@1@@Z` at `0x18003cd07`
- `wincorlib!??0FailureException@Platform@@QE$AAA@PE$AAVString@1@@Z` at `0x18003cc47`
- `wincorlib!??0FailureException@Platform@@QE$AAA@PE$AAVString@1@@Z` at `0x18003cd07`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x18003cbdf`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x18003cc9f`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x18003cbdf`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x18003cc9f`

## string_xrefs

- `0x18003cc17`: `Failed to read `

## pseudocode

```c
// Hidden C++ exception states: #wind=13
_QWORD *__fastcall ReadAllBytesInTextModeForConstraintIndex(_QWORD *a1, const WCHAR *a2)
{
  int *v4; // rcx
  bool v5; // zf
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rdx
  int *v10; // rcx
  void *v11; // rbx
  __int64 v12; // rdi
  HRESULT v13; // eax
  __int64 v14; // rax
  __int64 v15; // r8
  void *Exception; // rbx
  __int64 v18; // rdi
  HRESULT v19; // eax
  __int64 v20; // rax
  __int64 v21; // r8
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING_HEADER v24; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v26[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v27[256]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v28; // [rsp+190h] [rbp+90h] BYREF
  __int64 v29; // [rsp+198h] [rbp+98h]
  void *retaddr; // [rsp+1B8h] [rbp+B8h]

  memset_0(v26, 0, 0x110u);
  std::ifstream::ifstream(v26);
  v4 = (int *)((char *)v26 + *(int *)(v26[0] + 4LL));
  v4[5] = 6;
  std::ios_base::clear((std::ios_base *)v4, v4[4], 0);
  v5 = std::filebuf::open(v27, a2, 1) == 0;
  v6 = *(int *)(v26[0] + 4LL);
  if ( v5 )
    std::ios::setstate((char *)v26 + v6, 2);
  else
    std::ios_base::clear((std::ios_base *)((char *)v26 + v6), *(_QWORD *)&v27[v6 + 56] == 0 ? 4 : 0, 0);
  std::istream::seekg(v26, v7, 2);
  std::istream::tellg(v26, &v28);
  std::istream::seekg(v26, v8, 0);
  if ( __TSS0__1__ReadAllBytesInTextModeForConstraintIndex__YA_AV__vector_DV__allocator_D_std___std__PEB_W_Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) )
  {
    Init_thread_header(&__TSS0__1__ReadAllBytesInTextModeForConstraintIndex__YA_AV__vector_DV__allocator_D_std___std__PEB_W_Z_4HA);
    if ( __TSS0__1__ReadAllBytesInTextModeForConstraintIndex__YA_AV__vector_DV__allocator_D_std___std__PEB_W_Z_4HA == -1 )
    {
      `ReadAllBytesInTextModeForConstraintIndex'::`2'::OneGigabyte = (__int128)_mm_load_si128((const __m128i *)&_xmm);
      qword_18013E488 = 0;
      Init_thread_footer(&__TSS0__1__ReadAllBytesInTextModeForConstraintIndex__YA_AV__vector_DV__allocator_D_std___std__PEB_W_Z_4HA);
    }
  }
  v9 = v28 + v29;
  if ( v28 + v29 < 0
    || v9 >= *((_QWORD *)&`ReadAllBytesInTextModeForConstraintIndex'::`2'::OneGigabyte + 1)
           + (_QWORD)`ReadAllBytesInTextModeForConstraintIndex'::`2'::OneGigabyte )
  {
    Exception = Platform::Details::Heap::AllocateException(0x68u, 0x90u);
    v18 = *(_QWORD *)(Platform::StringReference::StringReference(&v24, a2) + 24);
    string[0] = 0;
    v19 = WindowsCreateStringReference_0(L"Unexpected size for ", 0x14u, &hstringHeader, string);
    if ( v19 < 0 )
      __abi_WinRTraiseException(v19);
    string[0] = (HSTRING)Platform::String::Concat(string[0], v18);
    v20 = Platform::FailureException::FailureException(Exception, string[0]);
    wil::details::ReportFailure_CustomException<Platform::FailureException __gc *>(retaddr, 24, v21, v20, 0, v20, a1);
  }
  *(_OWORD *)a1 = 0;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  std::vector<unsigned char>::_Construct_n<>(a1, v9 + 1);
  v10 = (int *)((char *)v26 + *(int *)(v26[0] + 4LL));
  v10[5] = 4;
  std::ios_base::clear((std::ios_base *)v10, v10[4], 0);
  std::istream::read(v26, *a1, v28 + v29);
  if ( (*((_BYTE *)&v26[2] + *(int *)(v26[0] + 4LL)) & 6) != 0
    && !std::ios_base::eof((std::ios_base *)((char *)v26 + *(int *)(v26[0] + 4LL))) )
  {
    v11 = Platform::Details::Heap::AllocateException(0x68u, 0x90u);
    v12 = *(_QWORD *)(Platform::StringReference::StringReference(&v24, a2) + 24);
    string[0] = 0;
    v13 = WindowsCreateStringReference_0(L"Failed to read ", 0xFu, &hstringHeader, string);
    if ( v13 < 0 )
      __abi_WinRTraiseException(v13);
    string[0] = (HSTRING)Platform::String::Concat(string[0], v12);
    v14 = Platform::FailureException::FailureException(v11, string[0]);
    wil::details::ReportFailure_CustomException<Platform::FailureException __gc *>(retaddr, 41, v15, v14, 1, v14, a1);
  }
  std::ifstream::`vbase destructor'(v26);
  return a1;
}

```

## disassembly

```asm
0x18003c9d8  mov     [rsp-8+arg_10], rbx
0x18003c9dd  mov     [rsp-8+arg_18], rdi
0x18003c9e2  push    rbp
0x18003c9e3  lea     rbp, [rsp-0B0h]
0x18003c9eb  sub     rsp, 1B0h
0x18003c9f2  mov     rax, cs:__security_cookie
0x18003c9f9  xor     rax, rsp
0x18003c9fc  mov     [rbp+0B0h+var_8], rax
0x18003ca03  mov     rdi, rdx
0x18003ca06  mov     rbx, rcx
0x18003ca09  mov     [rsp+1B0h+var_180], rcx
0x18003ca0e  mov     [rsp+1B0h+var_190], 0
0x18003ca16  xor     edx, edx; Val
0x18003ca18  mov     r8d, 110h; Size
0x18003ca1e  lea     rcx, [rbp+0B0h+var_130]; void *
0x18003ca22  call    memset_0
0x18003ca27  lea     rcx, [rbp+0B0h+var_130]
0x18003ca2b  call    ??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@XZ; std::ifstream::ifstream(void)
0x18003ca30  nop
0x18003ca31  mov     rax, [rbp+0B0h+var_130]
0x18003ca35  movsxd  rcx, dword ptr [rax+4]
0x18003ca39  lea     rax, [rbp+0B0h+var_130]
0x18003ca3d  add     rcx, rax; this
0x18003ca40  mov     dword ptr [rcx+14h], 6
0x18003ca47  xor     r8d, r8d; bool
0x18003ca4a  mov     edx, [rcx+10h]; int
0x18003ca4d  call    ?clear@ios_base@std@@QEAAXH_N@Z; std::ios_base::clear(int,bool)
0x18003ca52  mov     r8d, 1
0x18003ca58  mov     rdx, rdi
0x18003ca5b  lea     rcx, [rbp+0B0h+var_120]
0x18003ca5f  call    ?open@?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAAPEAV12@PEB_WHH@Z; std::filebuf::open(wchar_t const *,int,int)
0x18003ca64  test    rax, rax
0x18003ca67  mov     rax, [rbp+0B0h+var_130]
0x18003ca6b  movsxd  rcx, dword ptr [rax+4]
0x18003ca6f  lea     rax, [rbp+0B0h+var_130]
0x18003ca73  jz      short loc_18003CA90
0x18003ca75  add     rcx, rax; this
0x18003ca78  mov     rax, [rcx+48h]
0x18003ca7c  neg     rax
0x18003ca7f  sbb     edx, edx
0x18003ca81  not     edx
0x18003ca83  and     edx, 4; int
0x18003ca86  xor     r8d, r8d; bool
0x18003ca89  call    ?clear@ios_base@std@@QEAAXH_N@Z; std::ios_base::clear(int,bool)
0x18003ca8e  jmp     short loc_18003CA9F
0x18003ca90  add     rcx, rax
0x18003ca93  xor     r8d, r8d
0x18003ca96  lea     edx, [r8+2]
0x18003ca9a  call    ?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::setstate(int,bool)
0x18003ca9f  mov     r8d, 2
0x18003caa5  lea     rcx, [rbp+0B0h+var_130]
0x18003caa9  call    ?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x18003caae  lea     rdx, [rbp+0B0h+var_20]
0x18003cab5  lea     rcx, [rbp+0B0h+var_130]
0x18003cab9  call    ?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ; std::istream::tellg(void)
0x18003cabe  xor     r8d, r8d
0x18003cac1  lea     rcx, [rbp+0B0h+var_130]
0x18003cac5  call    ?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x18003caca  mov     ecx, cs:_tls_index
0x18003cad0  mov     rax, gs:58h
0x18003cad9  mov     edx, 4
0x18003cade  mov     rax, [rax+rcx*8]
0x18003cae2  mov     ecx, [rdx+rax]
0x18003cae5  cmp     cs:?$TSS0@?1??ReadAllBytesInTextModeForConstraintIndex@@YA?AV?$vector@DV?$allocator@D@std@@@std@@PEB_W@Z@4HA, ecx
0x18003caeb  jle     short loc_18003CB27
0x18003caed  lea     rcx, ?$TSS0@?1??ReadAllBytesInTextModeForConstraintIndex@@YA?AV?$vector@DV?$allocator@D@std@@@std@@PEB_W@Z@4HA
0x18003caf4  call    _Init_thread_header
0x18003caf9  cmp     cs:?$TSS0@?1??ReadAllBytesInTextModeForConstraintIndex@@YA?AV?$vector@DV?$allocator@D@std@@@std@@PEB_W@Z@4HA, 0FFFFFFFFh
0x18003cb00  jnz     short loc_18003CB27
0x18003cb02  movdqa  xmm0, cs:__xmm@00000000000000000000000040000000
0x18003cb0a  movdqu  cs:?OneGigabyte@?1??ReadAllBytesInTextModeForConstraintIndex@@YA?AV?$vector@DV?$allocator@D@std@@@std@@PEB_W@Z@4V?$fpos@U_Mbstatet@@@3@B, xmm0; std::fpos<_Mbstatet> const `ReadAllBytesInTextModeForConstraintIndex(wchar_t const *)'::`2'::OneGigabyte
0x18003cb12  xor     eax, eax
0x18003cb14  mov     cs:qword_18013E488, rax
0x18003cb1b  lea     rcx, ?$TSS0@?1??ReadAllBytesInTextModeForConstraintIndex@@YA?AV?$vector@DV?$allocator@D@std@@@std@@PEB_W@Z@4HA
0x18003cb22  call    _Init_thread_footer
0x18003cb27  mov     rdx, [rbp+0B0h+var_18]
0x18003cb2e  add     rdx, [rbp+0B0h+var_20]
0x18003cb35  js      loc_18003CC97
0x18003cb3b  mov     rcx, qword ptr cs:?OneGigabyte@?1??ReadAllBytesInTextModeForConstraintIndex@@YA?AV?$vector@DV?$allocator@D@std@@@std@@PEB_W@Z@4V?$fpos@U_Mbstatet@@@3@B; std::fpos<_Mbstatet> const `ReadAllBytesInTextModeForConstraintIndex(wchar_t const *)'::`2'::OneGigabyte
0x18003cb42  add     rcx, qword ptr cs:?OneGigabyte@?1??ReadAllBytesInTextModeForConstraintIndex@@YA?AV?$vector@DV?$allocator@D@std@@@std@@PEB_W@Z@4V?$fpos@U_Mbstatet@@@3@B+8; std::fpos<_Mbstatet> const `ReadAllBytesInTextModeForConstraintIndex(wchar_t const *)'::`2'::OneGigabyte
0x18003cb49  cmp     rdx, rcx
0x18003cb4c  jge     loc_18003CC97
0x18003cb52  xorps   xmm0, xmm0
0x18003cb55  xor     eax, eax
0x18003cb57  movups  xmmword ptr [rbx], xmm0
0x18003cb5a  mov     [rbx], rax
0x18003cb5d  mov     [rbx+8], rax
0x18003cb61  mov     [rbx+10h], rax
0x18003cb65  inc     rdx
0x18003cb68  mov     rcx, rbx
0x18003cb6b  call    ??$_Construct_n@$$V@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Construct_n<>(unsigned __int64)
0x18003cb70  mov     [rsp+1B0h+var_190], 1
0x18003cb78  mov     rax, [rbp+0B0h+var_130]
0x18003cb7c  movsxd  rcx, dword ptr [rax+4]
0x18003cb80  lea     rax, [rbp+0B0h+var_130]
0x18003cb84  add     rcx, rax; this
0x18003cb87  mov     dword ptr [rcx+14h], 4
0x18003cb8e  xor     r8d, r8d; bool
0x18003cb91  mov     edx, [rcx+10h]; int
0x18003cb94  call    ?clear@ios_base@std@@QEAAXH_N@Z; std::ios_base::clear(int,bool)
0x18003cb99  mov     r8, [rbp+0B0h+var_18]
0x18003cba0  add     r8, [rbp+0B0h+var_20]
0x18003cba7  mov     rdx, [rbx]
0x18003cbaa  lea     rcx, [rbp+0B0h+var_130]
0x18003cbae  call    ?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x18003cbb3  mov     rax, [rbp+0B0h+var_130]
0x18003cbb7  movsxd  rcx, dword ptr [rax+4]
0x18003cbbb  lea     rcx, [rbp+rcx+0B0h+var_130]; this
0x18003cbc0  test    byte ptr [rcx+10h], 6
0x18003cbc4  jz      loc_18003CC67
0x18003cbca  call    ?eof@ios_base@std@@QEBA_NXZ; std::ios_base::eof(void)
0x18003cbcf  test    al, al
0x18003cbd1  jnz     loc_18003CC67
0x18003cbd7  mov     edx, 90h
0x18003cbdc  lea     ecx, [rdx-28h]
0x18003cbdf  call    cs:__imp_?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::AllocateException(unsigned __int64,unsigned __int64)
0x18003cbe5  mov     rbx, rax
0x18003cbe8  mov     [rsp+1B0h+var_188], rax
0x18003cbed  mov     rdx, rdi; sourceString
0x18003cbf0  lea     rcx, [rsp+1B0h+var_160]; hstringHeader
0x18003cbf5  call    ??0StringReference@Platform@@QEAA@PEB_W@Z; Platform::StringReference::StringReference(wchar_t const *)
0x18003cbfa  nop
0x18003cbfb  mov     rdi, [rax+18h]
0x18003cbff  mov     [rsp+1B0h+string], 0
0x18003cc08  lea     r9, [rsp+1B0h+string]; string
0x18003cc0d  lea     r8, [rsp+1B0h+hstringHeader]; hstringHeader
0x18003cc12  mov     edx, 0Fh; length
0x18003cc17  lea     rcx, aFailedToRead; "Failed to read "
0x18003cc1e  call    WindowsCreateStringReference_0
0x18003cc23  test    eax, eax
0x18003cc25  jns     short loc_18003CC2F
0x18003cc27  mov     ecx, eax; int
0x18003cc29  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x18003cc2f  mov     rdx, rdi
0x18003cc32  mov     rcx, [rsp+1B0h+string]
0x18003cc37  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x18003cc3c  mov     [rsp+1B0h+string], rax
0x18003cc41  mov     rdx, rax
0x18003cc44  mov     rcx, rbx
0x18003cc47  call    cs:__imp_??0FailureException@Platform@@QE$AAA@PE$AAVString@1@@Z; Platform::FailureException::FailureException(Platform::String *)
0x18003cc4d  mov     [rsp+1B0h+var_188], rax
0x18003cc52  mov     rcx, [rbp+0B8h]
0x18003cc59  mov     r9, rax
0x18003cc5c  mov     edx, 29h ; ')'
0x18003cc61  call    ??$ReportFailure_CustomException@PE$AAVFailureException@Platform@@@details@wil@@YAXPEAXIPEBDPE$AAVFailureException@Platform@@@Z; wil::details::ReportFailure_CustomException<Platform::FailureException *>(void *,uint,char const *,Platform::FailureException *)
0x18003cc67  lea     rcx, [rbp+0B0h+var_130]
0x18003cc6b  call    ??_D?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAAXXZ; std::ifstream::`vbase destructor'(void)
0x18003cc70  mov     rax, rbx
0x18003cc73  mov     rcx, [rbp+0B0h+var_8]
0x18003cc7a  xor     rcx, rsp; StackCookie
0x18003cc7d  call    __security_check_cookie
0x18003cc82  lea     r11, [rsp+1B0h+var_s0]
0x18003cc8a  mov     rbx, [r11+20h]
0x18003cc8e  mov     rdi, [r11+28h]
0x18003cc92  mov     rsp, r11
0x18003cc95  pop     rbp
0x18003cc96  retn
0x18003cc97  mov     edx, 90h
0x18003cc9c  lea     ecx, [rdx-28h]
0x18003cc9f  call    cs:__imp_?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::AllocateException(unsigned __int64,unsigned __int64)
0x18003cca5  mov     rbx, rax
0x18003cca8  mov     [rsp+1B0h+var_188], rax
0x18003ccad  mov     rdx, rdi; sourceString
0x18003ccb0  lea     rcx, [rsp+1B0h+var_160]; hstringHeader
0x18003ccb5  call    ??0StringReference@Platform@@QEAA@PEB_W@Z; Platform::StringReference::StringReference(wchar_t const *)
0x18003ccba  nop
0x18003ccbb  mov     rdi, [rax+18h]
0x18003ccbf  mov     [rsp+1B0h+string], 0
0x18003ccc8  lea     r9, [rsp+1B0h+string]; string
0x18003cccd  lea     r8, [rsp+1B0h+hstringHeader]; hstringHeader
0x18003ccd2  mov     edx, 14h; length
0x18003ccd7  lea     rcx, aUnexpectedSize; "Unexpected size for "
0x18003ccde  call    WindowsCreateStringReference_0
0x18003cce3  test    eax, eax
0x18003cce5  jns     short loc_18003CCEF
0x18003cce7  mov     ecx, eax; int
0x18003cce9  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x18003ccef  mov     rdx, rdi
0x18003ccf2  mov     rcx, [rsp+1B0h+string]
0x18003ccf7  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x18003ccfc  mov     [rsp+1B0h+string], rax
0x18003cd01  mov     rdx, rax
0x18003cd04  mov     rcx, rbx
0x18003cd07  call    cs:__imp_??0FailureException@Platform@@QE$AAA@PE$AAVString@1@@Z; Platform::FailureException::FailureException(Platform::String *)
0x18003cd0d  mov     [rsp+1B0h+var_188], rax
0x18003cd12  mov     rcx, [rbp+0B8h]
0x18003cd19  mov     r9, rax
0x18003cd1c  mov     edx, 18h
0x18003cd21  call    ??$ReportFailure_CustomException@PE$AAVFailureException@Platform@@@details@wil@@YAXPEAXIPEBDPE$AAVFailureException@Platform@@@Z; wil::details::ReportFailure_CustomException<Platform::FailureException *>(void *,uint,char const *,Platform::FailureException *)
```
