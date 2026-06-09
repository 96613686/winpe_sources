# PrintCore::RestHelpers::CanonicalizeUrl(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18001309c`
- end: `0x1800132df`
- name: `?CanonicalizeUrl@RestHelpers@PrintCore@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V34@@Z`
- size: `579`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180017464`

## callees

- `0x180003a60`
- `0x18000e164`
- `0x18000e208`
- `0x180011358`
- `0x180011de0`
- `0x18001309c`
- `0x18001ba58`
- `0x18001c4a8`
- `0x18001de18`
- `0x18001df80`
- `0x18002b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800131a8`

## string_xrefs

- `0x18001315c`: `URL '%ws' missing path`

## pseudocode

```c
__int64 __fastcall PrintCore::RestHelpers::CanonicalizeUrl(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  const char *v5; // rax
  __int64 v6; // rbx
  const char *v7; // rax
  unsigned __int16 *v8; // r14
  __int64 v9; // rbp
  __int64 v10; // rdx
  _WORD *v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdx
  _BYTE v16[32]; // [rsp+50h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v4 = std::wstring::find(a2, L"://", 0);
  v5 = (const char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x29,
    (unsigned int)"onecoreuap\\internal\\printscan\\inc\\RestHelpers.h",
    (const char *)0x80070057LL,
    v4 == -1,
    (bool)"URL '%ws' missing scheme://",
    v5);
  v6 = std::wstring::find(a2, L"/", v4 + 3);
  v7 = (const char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x2C,
    (unsigned int)"onecoreuap\\internal\\printscan\\inc\\RestHelpers.h",
    (const char *)0x80070057LL,
    v6 == -1,
    (bool)"URL '%ws' missing path",
    v7);
  v8 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr() + 2 * v6;
  v11 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  while ( v8 != (unsigned __int16 *)v9 )
    *v11++ = ((__int64 (__fastcall *)(_QWORD))_o_towlower)(*v8++);
  if ( (unsigned int)std::wstring::compare(a2, v10, 7, L"ipps://") )
  {
    if ( !(unsigned int)std::wstring::compare(a2, v12, 6, L"ipp://") )
    {
      std::wstring::wstring((__int64)v16, (__int64)L"ipp://");
      PrintCore::RestHelpers::_AddDefaultIppPort(v16, a2);
      std::wstring::_Tidy_deallocate((__int64)v16);
      std::wstring::_Replace<unsigned short>(a2, v14, 6u, (char *)L"http://", 7u);
    }
  }
  else
  {
    std::wstring::wstring((__int64)v16, (__int64)L"ipps://");
    PrintCore::RestHelpers::_AddDefaultIppPort(v16, a2);
    std::wstring::_Tidy_deallocate((__int64)v16);
    std::wstring::_Replace<unsigned short>(a2, v13, 7u, (char *)L"https://", 8u);
  }
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_OWORD *)a1 = *(_OWORD *)a2;
  *(_OWORD *)(a1 + 16) = *(_OWORD *)(a2 + 16);
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 7;
  *(_WORD *)a2 = 0;
  std::wstring::_Tidy_deallocate(a2);
  return a1;
}

```

## disassembly

```asm
0x18001309c  mov     [rsp+arg_10], rbx
0x1800130a1  mov     [rsp+arg_18], rbp
0x1800130a6  push    rsi
0x1800130a7  push    rdi
0x1800130a8  push    r14
0x1800130aa  sub     rsp, 80h
0x1800130b1  mov     rax, cs:__security_cookie
0x1800130b8  xor     rax, rsp
0x1800130bb  mov     [rsp+98h+var_28], rax
0x1800130c0  mov     rdi, rdx
0x1800130c3  mov     rsi, rcx
0x1800130c6  mov     [rsp+98h+var_50], rcx
0x1800130cb  mov     [rsp+98h+var_50], rdx
0x1800130d0  xor     r8d, r8d
0x1800130d3  lea     rdx, asc_18002F168; "://"
0x1800130da  mov     rcx, rdi
0x1800130dd  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x1800130e2  mov     rbx, rax
0x1800130e5  mov     rcx, rdi
0x1800130e8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800130ed  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800130f1  setz    dl
0x1800130f4  mov     rcx, [rsp+98h]; this
0x1800130fc  mov     [rsp+98h+var_68], rax; char *
0x180013101  lea     rax, aUrlWsMissingSc; "URL '%ws' missing scheme://"
0x180013108  mov     qword ptr [rsp+98h+var_70], rax; bool
0x18001310d  mov     [rsp+98h+var_78], dl; char
0x180013111  mov     ebp, 80070057h
0x180013116  mov     r9d, ebp; char *
0x180013119  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\printscan\\inc\\R"...
0x180013120  mov     edx, 29h ; ')'; void *
0x180013125  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001312a  lea     r8, [rbx+3]
0x18001312e  lea     rdx, S; "/"
0x180013135  mov     rcx, rdi
0x180013138  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x18001313d  mov     rbx, rax
0x180013140  mov     rcx, rdi
0x180013143  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013148  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001314c  setz    dl
0x18001314f  mov     rcx, [rsp+98h]; this
0x180013157  mov     [rsp+98h+var_68], rax; char *
0x18001315c  lea     rax, aUrlWsMissingPa; "URL '%ws' missing path"
0x180013163  mov     qword ptr [rsp+98h+var_70], rax; bool
0x180013168  mov     [rsp+98h+var_78], dl; char
0x18001316c  mov     r9d, ebp; char *
0x18001316f  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\printscan\\inc\\R"...
0x180013176  mov     edx, 2Ch ; ','; void *
0x18001317b  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180013180  mov     rcx, rdi
0x180013183  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013188  mov     r14, rax
0x18001318b  mov     rcx, rdi
0x18001318e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013193  lea     rbp, [rax+rbx*2]
0x180013197  mov     rcx, rdi
0x18001319a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001319f  mov     rbx, rax
0x1800131a2  jmp     short loc_1800131BF
0x1800131a4  movzx   ecx, word ptr [r14]
0x1800131a8  mov     rax, cs:__imp__o_towlower
0x1800131af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131b4  mov     [rbx], ax
0x1800131b7  lea     rbx, [rbx+2]
0x1800131bb  add     r14, 2
0x1800131bf  cmp     r14, rbp
0x1800131c2  jnz     short loc_1800131A4
0x1800131c4  lea     r9, aIpps; "ipps://"
0x1800131cb  mov     ebx, 7
0x1800131d0  mov     r8d, ebx
0x1800131d3  mov     rcx, rdi
0x1800131d6  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAH_K0QEBG@Z; std::wstring::compare(unsigned __int64,unsigned __int64,ushort const * const)
0x1800131db  test    eax, eax
0x1800131dd  jnz     short loc_18001321E
0x1800131df  lea     rdx, aIpps; "ipps://"
0x1800131e6  lea     rcx, [rsp+98h+var_48]
0x1800131eb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800131f0  nop
0x1800131f1  mov     rdx, rdi
0x1800131f4  lea     rcx, [rsp+98h+var_48]
0x1800131f9  call    ?_AddDefaultIppPort@RestHelpers@PrintCore@@CAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@@Z; PrintCore::RestHelpers::_AddDefaultIppPort(std::wstring const &,std::wstring &)
0x1800131fe  nop
0x1800131ff  lea     rcx, [rsp+98h+var_48]
0x180013204  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013209  mov     qword ptr [rsp+98h+var_78], 8
0x180013212  lea     r9, aHttps; "https://"
0x180013219  mov     r8d, ebx
0x18001321c  jmp     short loc_180013272
0x18001321e  lea     r9, aIpp; "ipp://"
0x180013225  mov     ebp, 6
0x18001322a  mov     r8d, ebp
0x18001322d  mov     rcx, rdi
0x180013230  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAH_K0QEBG@Z; std::wstring::compare(unsigned __int64,unsigned __int64,ushort const * const)
0x180013235  test    eax, eax
0x180013237  jnz     short loc_18001327A
0x180013239  lea     rdx, aIpp; "ipp://"
0x180013240  lea     rcx, [rsp+98h+var_48]
0x180013245  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001324a  nop
0x18001324b  mov     rdx, rdi
0x18001324e  lea     rcx, [rsp+98h+var_48]
0x180013253  call    ?_AddDefaultIppPort@RestHelpers@PrintCore@@CAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@@Z; PrintCore::RestHelpers::_AddDefaultIppPort(std::wstring const &,std::wstring &)
0x180013258  nop
0x180013259  lea     rcx, [rsp+98h+var_48]
0x18001325e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013263  mov     qword ptr [rsp+98h+var_78], rbx; __int64
0x180013268  lea     r9, aHttp_0; "http://"
0x18001326f  mov     r8d, ebp
0x180013272  mov     rcx, rdi; int
0x180013275  call    ??$_Replace@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_K_KQEBG0@Z; std::wstring::_Replace<ushort>(unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x18001327a  xorps   xmm0, xmm0
0x18001327d  movups  xmmword ptr [rsi], xmm0
0x180013280  mov     qword ptr [rsi+10h], 0
0x180013288  mov     qword ptr [rsi+18h], 0
0x180013290  movups  xmm0, xmmword ptr [rdi]
0x180013293  movups  xmmword ptr [rsi], xmm0
0x180013296  movups  xmm1, xmmword ptr [rdi+10h]
0x18001329a  movups  xmmword ptr [rsi+10h], xmm1
0x18001329e  mov     qword ptr [rdi+10h], 0
0x1800132a6  mov     [rdi+18h], rbx
0x1800132aa  xor     edx, edx
0x1800132ac  mov     [rdi], dx
0x1800132af  mov     rcx, rdi
0x1800132b2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800132b7  mov     rax, rsi
0x1800132ba  mov     rcx, [rsp+98h+var_28]
0x1800132bf  xor     rcx, rsp; StackCookie
0x1800132c2  call    __security_check_cookie
0x1800132c7  lea     r11, [rsp+98h+var_18]
0x1800132cf  mov     rbx, [r11+30h]
0x1800132d3  mov     rbp, [r11+38h]
0x1800132d7  mov     rsp, r11
0x1800132da  pop     r14
0x1800132dc  pop     rdi
0x1800132dd  pop     rsi
0x1800132de  retn
```
