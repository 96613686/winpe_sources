# UsageAndQualityInsights::Facts::FactKey::GetTimeBin(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1800fda60`
- end: `0x1800fdc02`
- name: `?GetTimeBin@FactKey@Facts@UsageAndQualityInsights@@AEBA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@6@@Z`
- size: `418`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x1800fd5bc`
- `0x1800fd7b0`

## callees

- `0x18001a9b0`
- `0x180020650`
- `0x18002b470`
- `0x180041d6c`
- `0x18004350c`
- `0x1800fa348`
- `0x1800fb74c`
- `0x1800fda60`

## import_xrefs

- `msvcp_win!??1?$basic_istream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x1800fdbe3`
- `msvcp_win!??1?$basic_istream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x1800fdbe3`
- `msvcp_win!?setstate@?$basic_ios@_WU?$char_traits@_W@std@@@std@@QEAAXH_N@Z` at `0x1800fdb4a`
- `msvcp_win!?setstate@?$basic_ios@_WU?$char_traits@_W@std@@@std@@QEAAXH_N@Z` at `0x1800fdb4a`
- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x1800fdb08`
- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x1800fdb08`
- `msvcp_win!??1?$basic_ios@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x1800fdbed`
- `msvcp_win!??1?$basic_ios@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x1800fdbed`
- `msvcp_win!?fail@ios_base@std@@QEBA_NXZ` at `0x1800fdb77`
- `msvcp_win!?fail@ios_base@std@@QEBA_NXZ` at `0x1800fdb77`

## string_xrefs

- `0x1800fdab4`: `onecore\base\usageandqualityinsights\service\lib\factstore\factkey.cpp`
- `0x1800fdb9a`: `onecore\base\usageandqualityinsights\service\lib\factstore\factkey.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall UsageAndQualityInsights::Facts::FactKey::GetTimeBin(__int64 a1, _QWORD *a2, __int64 a3)
{
  _QWORD *v4; // rdi
  __int64 v5; // rbx
  int v7; // [rsp+20h] [rbp-E0h]
  int v8; // [rsp+20h] [rbp-E0h]
  bool v9[8]; // [rsp+28h] [rbp-D8h]
  const char *v10[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v11[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v12[120]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v13[96]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v14[96]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v15[128]; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]
  __int64 v17; // [rsp+210h] [rbp+110h] BYREF

  v4 = (_QWORD *)(a1 + 8);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
    a1 + 8,
    &v17,
    a3);
  v5 = v17;
  LOBYTE(v7) = v17 == *v4;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xC0,
    (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\factstore\\factkey.cpp",
    (const char *)0x80070057LL,
    v7,
    (bool)"Day time bin key not found in dimensions",
    v10[0]);
  *a2 = 0;
  std::wistringstream::wistringstream(v10, v5 + 64);
  std::chrono::_Time_parse_fields::_Time_parse_fields((std::chrono::_Time_parse_fields *)v14, 0, *(__int64 *)v9);
  if ( (unsigned __int8)std::ios_base::operator bool((char *)v10 + *((int *)v10[0] + 1))
    && (unsigned __int8)std::chrono::_Time_parse_fields::_Make_time_point<std::chrono::duration<__int64,std::ratio<1,10000000>>>((std::chrono::_Time_parse_fields *)v14) )
  {
    *a2 = v17;
  }
  else
  {
    std::wios::setstate((char *)v10 + *((int *)v10[0] + 1), 2);
  }
  if ( v15[32] )
    std::string::~string(v15);
  LOBYTE(v8) = std::ios_base::fail((std::ios_base *)((char *)v10 + *((int *)v10[0] + 1)));
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xC7,
    (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\factstore\\factkey.cpp",
    (const char *)0x80070057LL,
    v8,
    (bool)"Failed to parse time bin string",
    v10[0]);
  *(const char **)((char *)v10 + *((int *)v10[0] + 1)) = (const char *)&std::wistringstream::`vftable';
  *(_DWORD *)&v9[*((int *)v10[0] + 1) + 4] = *((_DWORD *)v10[0] + 1) - 144;
  std::wstringbuf::~wstringbuf(v11);
  std::wistream::~wistream<wchar_t,std::char_traits<wchar_t>>(v12);
  std::wios::~wios<wchar_t,std::char_traits<wchar_t>>(v13);
  return a2;
}

```

## disassembly

```asm
0x1800fda60  push    rbp
0x1800fda62  push    rbx
0x1800fda63  push    rsi
0x1800fda64  push    rdi
0x1800fda65  lea     rbp, [rsp-0E8h]
0x1800fda6d  sub     rsp, 1E8h
0x1800fda74  mov     rsi, rdx
0x1800fda77  lea     rdi, [rcx+8]
0x1800fda7b  lea     rdx, [rbp+100h+arg_0]
0x1800fda82  mov     rcx, rdi
0x1800fda85  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x1800fda8a  mov     rbx, [rbp+100h+arg_0]
0x1800fda91  cmp     rbx, [rdi]
0x1800fda94  setz    al
0x1800fda97  mov     rcx, [rbp+108h]; this
0x1800fda9e  lea     rdx, aDayTimeBinKeyN; "Day time bin key not found in dimension"...
0x1800fdaa5  mov     qword ptr [rsp+200h+var_1D8], rdx; bool
0x1800fdaaa  mov     byte ptr [rsp+200h+var_1E0], al; int
0x1800fdaae  mov     r9d, 80070057h; char *
0x1800fdab4  lea     r8, aOnecoreBaseUsa_11; "onecore\\base\\usageandqualityinsights"...
0x1800fdabb  mov     edx, 0C0h; void *
0x1800fdac0  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800fdac5  xor     edi, edi
0x1800fdac7  mov     [rsi], rdi
0x1800fdaca  lea     rdx, [rbx+40h]
0x1800fdace  lea     rcx, [rsp+200h+var_1D0]
0x1800fdad3  call    ??0?$basic_istringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::wistringstream::wistringstream(std::wstring const &,int)
0x1800fdad8  nop
0x1800fdad9  mov     qword ptr [rsp+200h+var_1E0], rdi
0x1800fdade  xor     r9d, r9d
0x1800fdae1  lea     r8, aFtTz; "%FT%TZ"
0x1800fdae8  lea     rdx, [rsp+200h+var_1D0]
0x1800fdaed  lea     rcx, [rbp+100h+var_E0]
0x1800fdaf1  call    ??$?0_WU?$char_traits@_W@std@@V?$allocator@_W@1@@_Time_parse_fields@chrono@std@@QEAA@AEAV?$basic_istream@_WU?$char_traits@_W@std@@@2@PEB_WPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@PEAV?$duration@HU?$ratio@$0DM@$00@std@@@12@I@Z; std::chrono::_Time_parse_fields::_Time_parse_fields(std::wistream &,wchar_t const *,std::wstring *,std::chrono::duration<int,std::ratio<60,1>> *,uint)
0x1800fdaf6  nop
0x1800fdaf7  mov     rax, [rsp+200h+var_1D0]
0x1800fdafc  movsxd  rcx, dword ptr [rax+4]
0x1800fdb00  lea     rax, [rsp+200h+var_1D0]
0x1800fdb05  add     rcx, rax
0x1800fdb08  call    cs:__imp_??Bios_base@std@@QEBA_NXZ; std::ios_base::operator bool(void)
0x1800fdb0e  test    al, al
0x1800fdb10  jz      short loc_1800FDB32
0x1800fdb12  lea     rdx, [rbp+100h+arg_0]
0x1800fdb19  lea     rcx, [rbp+100h+var_E0]; this
0x1800fdb1d  call    ??$_Make_time_point@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@_Time_parse_fields@chrono@std@@QEAA_NAEAV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@12@W4_Leap_second_rep@012@@Z; std::chrono::_Time_parse_fields::_Make_time_point<std::chrono::duration<__int64,std::ratio<1,10000000>>>(std::chrono::duration<__int64,std::ratio<1,10000000>> &,std::chrono::_Time_parse_fields::_Leap_second_rep)
0x1800fdb22  test    al, al
0x1800fdb24  jz      short loc_1800FDB32
0x1800fdb26  mov     rax, [rbp+100h+arg_0]
0x1800fdb2d  mov     [rsi], rax
0x1800fdb30  jmp     short loc_1800FDB51
0x1800fdb32  mov     rax, [rsp+200h+var_1D0]
0x1800fdb37  movsxd  rcx, dword ptr [rax+4]
0x1800fdb3b  lea     rax, [rsp+200h+var_1D0]
0x1800fdb40  add     rcx, rax
0x1800fdb43  xor     r8d, r8d
0x1800fdb46  lea     edx, [r8+2]
0x1800fdb4a  call    cs:__imp_?setstate@?$basic_ios@_WU?$char_traits@_W@std@@@std@@QEAAXH_N@Z; std::wios::setstate(int,bool)
0x1800fdb50  nop
0x1800fdb51  cmp     [rbp+100h+var_60], dil
0x1800fdb58  jz      short loc_1800FDB66
0x1800fdb5a  lea     rcx, [rbp+100h+var_80]; void *
0x1800fdb61  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800fdb66  mov     rax, [rsp+200h+var_1D0]
0x1800fdb6b  movsxd  rcx, dword ptr [rax+4]
0x1800fdb6f  lea     rax, [rsp+200h+var_1D0]
0x1800fdb74  add     rcx, rax
0x1800fdb77  call    cs:__imp_?fail@ios_base@std@@QEBA_NXZ; std::ios_base::fail(void)
0x1800fdb7d  mov     rcx, [rbp+108h]; this
0x1800fdb84  lea     rdx, aFailedToParseT; "Failed to parse time bin string"
0x1800fdb8b  mov     qword ptr [rsp+200h+var_1D8], rdx; bool
0x1800fdb90  mov     byte ptr [rsp+200h+var_1E0], al; int
0x1800fdb94  mov     r9d, 80070057h; char *
0x1800fdb9a  lea     r8, aOnecoreBaseUsa_11; "onecore\\base\\usageandqualityinsights"...
0x1800fdba1  mov     edx, 0C7h; void *
0x1800fdba6  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800fdbab  nop
0x1800fdbac  mov     rax, [rsp+200h+var_1D0]
0x1800fdbb1  movsxd  rcx, dword ptr [rax+4]
0x1800fdbb5  lea     rax, ??_7?$basic_istringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@6B@; const std::wistringstream::`vftable'
0x1800fdbbc  mov     [rsp+rcx+200h+var_1D0], rax
0x1800fdbc1  mov     rax, [rsp+200h+var_1D0]
0x1800fdbc6  movsxd  rcx, dword ptr [rax+4]
0x1800fdbca  lea     edx, [rcx-90h]
0x1800fdbd0  mov     dword ptr [rsp+rcx+200h+var_1D8+4], edx
0x1800fdbd4  lea     rcx, [rsp+200h+var_1C0]
0x1800fdbd9  call    ??1?$basic_stringbuf@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UEAA@XZ; std::wstringbuf::~wstringbuf(void)
0x1800fdbde  lea     rcx, [rsp+200h+var_1B8]
0x1800fdbe3  call    cs:__imp_??1?$basic_istream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ; std::wistream::~wistream<wchar_t,std::char_traits<wchar_t>>(void)
0x1800fdbe9  lea     rcx, [rbp+100h+var_140]
0x1800fdbed  call    cs:__imp_??1?$basic_ios@_WU?$char_traits@_W@std@@@std@@UEAA@XZ; std::wios::~wios<wchar_t,std::char_traits<wchar_t>>(void)
0x1800fdbf3  mov     rax, rsi
0x1800fdbf6  add     rsp, 1E8h
0x1800fdbfd  pop     rdi
0x1800fdbfe  pop     rsi
0x1800fdbff  pop     rbx
0x1800fdc00  pop     rbp
0x1800fdc01  retn
```
