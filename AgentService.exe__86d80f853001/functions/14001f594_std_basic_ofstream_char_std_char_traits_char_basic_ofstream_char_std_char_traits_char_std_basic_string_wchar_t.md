# std::basic_ofstream<char,std::char_traits<char>>::basic_ofstream<char,std::char_traits<char>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,int,int)

- ea: `0x14001f594`
- end: `0x14001f741`
- name: `??0?$basic_ofstream@DU?$char_traits@D@std@@@std@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@HH@Z`
- size: `429`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001f748`

## callees

- `0x14001f464`
- `0x14001f594`
- `0x140020bd0`
- `0x14009b010`

## import_xrefs

- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x14001f5d3`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x14001f5d3`
- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEB_WHH@Z` at `0x14001f66a`
- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEB_WHH@Z` at `0x14001f66a`
- `msvcp_win!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x14001f692`
- `msvcp_win!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x14001f692`
- `msvcp_win!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x14001f63a`
- `msvcp_win!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x14001f6c2`
- `msvcp_win!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x14001f63a`
- `msvcp_win!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x14001f6c2`
- `msvcp_win!??0?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x14001f5f2`
- `msvcp_win!??0?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x14001f5f2`
- `msvcp_win!?always_noconv@codecvt_base@std@@QEBA_NXZ` at `0x14001f6a7`
- `msvcp_win!?always_noconv@codecvt_base@std@@QEBA_NXZ` at `0x14001f6a7`
- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x14001f70d`
- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x14001f70d`
- `msvcp_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x14001f61f`
- `msvcp_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x14001f61f`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall std::ofstream::ofstream(__int64 a1, __int64 a2)
{
  const wchar_t *v2; // rsi
  struct _iobuf *v4; // rax
  __int64 v5; // rax
  std::codecvt_base *v6; // rsi
  void (__fastcall ***v7)(_QWORD, __int64); // rax
  _BYTE v9[8]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v10; // [rsp+28h] [rbp-20h]

  v2 = (const wchar_t *)a2;
  if ( *(_QWORD *)(a2 + 24) > 7u )
    v2 = *(const wchar_t **)a2;
  *(_QWORD *)a1 = &std::ofstream::`vbtable';
  std::ios::ios(a1 + 168);
  std::ostream::ostream(a1, a1 + 8, 0, 0);
  *(_QWORD *)(*(int *)(*(_QWORD *)a1 + 4LL) + a1) = &std::ofstream::`vftable';
  *(_DWORD *)(*(int *)(*(_QWORD *)a1 + 4LL) + a1 - 4) = *(_DWORD *)(*(_QWORD *)a1 + 4LL) - 168;
  std::streambuf::streambuf(a1 + 8);
  *(_QWORD *)(a1 + 8) = &std::filebuf::`vftable';
  *(_BYTE *)(a1 + 132) = 0;
  *(_BYTE *)(a1 + 121) = 0;
  std::streambuf::_Init(a1 + 8);
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 124) = `std::filebuf::_Init'::`2'::_Stinit;
  *(_QWORD *)(a1 + 112) = 0;
  v4 = std::_Fiopen(v2, 10, 64);
  if ( v4 )
  {
    std::filebuf::_Init(a1 + 8, v4, 1);
    v5 = std::streambuf::getloc(a1 + 8, v9);
    v6 = (std::codecvt_base *)std::use_facet<std::codecvt<char,char,_Mbstatet>>(v5);
    if ( std::codecvt_base::always_noconv(v6) )
    {
      *(_QWORD *)(a1 + 112) = 0;
    }
    else
    {
      *(_QWORD *)(a1 + 112) = v6;
      std::streambuf::_Init(a1 + 8);
    }
    if ( v10 )
    {
      v7 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      if ( v7 )
        (**v7)(v7, 1);
    }
  }
  else
  {
    std::ios::setstate(a1 + *(int *)(*(_QWORD *)a1 + 4LL), 2);
  }
  *(_QWORD *)(*(int *)(*(_QWORD *)a1 + 4LL) + a1) = &std::ofstream::`vftable';
  *(_DWORD *)(*(int *)(*(_QWORD *)a1 + 4LL) + a1 - 4) = *(_DWORD *)(*(_QWORD *)a1 + 4LL) - 168;
  return a1;
}

```

## disassembly

```asm
0x14001f594  mov     rax, rsp
0x14001f597  mov     [rax+18h], rbx
0x14001f59b  mov     [rax+20h], r9d
0x14001f59f  mov     [rax+8], rcx
0x14001f5a3  push    rsi
0x14001f5a4  push    rdi
0x14001f5a5  push    r15
0x14001f5a7  sub     rsp, 30h
0x14001f5ab  mov     rsi, rdx
0x14001f5ae  mov     rbx, rcx
0x14001f5b1  mov     dword ptr [rax+20h], 0
0x14001f5b8  cmp     qword ptr [rdx+18h], 7
0x14001f5bd  jbe     short loc_14001F5C2
0x14001f5bf  mov     rsi, [rdx]
0x14001f5c2  lea     rax, ??_8?$basic_ofstream@DU?$char_traits@D@std@@@std@@7B@; const std::ofstream::`vbtable'
0x14001f5c9  mov     [rcx], rax
0x14001f5cc  add     rcx, 0A8h
0x14001f5d3  call    cs:__imp_??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::ios::ios(void)
0x14001f5d9  nop
0x14001f5da  mov     [rsp+48h+arg_18], 1
0x14001f5e2  lea     rdi, [rbx+8]
0x14001f5e6  xor     r9d, r9d
0x14001f5e9  xor     r8d, r8d
0x14001f5ec  mov     rdx, rdi
0x14001f5ef  mov     rcx, rbx
0x14001f5f2  call    cs:__imp_??0?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z; std::ostream::ostream(std::streambuf *,bool)
0x14001f5f8  nop
0x14001f5f9  mov     rax, [rbx]
0x14001f5fc  movsxd  rcx, dword ptr [rax+4]
0x14001f600  lea     r15, ??_7?$basic_ofstream@DU?$char_traits@D@std@@@std@@6B@; const std::ofstream::`vftable'
0x14001f607  mov     [rcx+rbx], r15
0x14001f60b  mov     rax, [rbx]
0x14001f60e  movsxd  rcx, dword ptr [rax+4]
0x14001f612  lea     edx, [rcx-0A8h]
0x14001f618  mov     [rcx+rbx-4], edx
0x14001f61c  mov     rcx, rdi
0x14001f61f  call    cs:__imp_??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::streambuf::streambuf(void)
0x14001f625  lea     rax, ??_7?$basic_filebuf@DU?$char_traits@D@std@@@std@@6B@; const std::filebuf::`vftable'
0x14001f62c  mov     [rdi], rax
0x14001f62f  mov     byte ptr [rdi+7Ch], 0
0x14001f633  mov     byte ptr [rdi+71h], 0
0x14001f637  mov     rcx, rdi
0x14001f63a  call    cs:__imp_?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ; std::streambuf::_Init(void)
0x14001f640  mov     qword ptr [rdi+80h], 0
0x14001f64b  mov     rax, cs:?_Stinit@?1??_Init@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@23@@Z@4U_Mbstatet@@A; _Mbstatet `std::filebuf::_Init(_iobuf *,std::filebuf::_Initfl)'::`2'::_Stinit
0x14001f652  mov     [rdi+74h], rax
0x14001f656  mov     qword ptr [rdi+68h], 0
0x14001f65e  mov     edx, 0Ah
0x14001f663  lea     r8d, [rdx+36h]
0x14001f667  mov     rcx, rsi
0x14001f66a  call    cs:__imp_?_Fiopen@std@@YAPEAU_iobuf@@PEB_WHH@Z; std::_Fiopen(wchar_t const *,int,int)
0x14001f670  test    rax, rax
0x14001f673  jz      loc_14001F6FC
0x14001f679  mov     r8d, 1
0x14001f67f  mov     rdx, rax
0x14001f682  mov     rcx, rdi
0x14001f685  call    ?_Init@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@12@@Z; std::filebuf::_Init(_iobuf *,std::filebuf::_Initfl)
0x14001f68a  lea     rdx, [rsp+48h+var_28]
0x14001f68f  mov     rcx, rdi
0x14001f692  call    cs:__imp_?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ; std::streambuf::getloc(void)
0x14001f698  nop
0x14001f699  mov     rcx, rax
0x14001f69c  call    ??$use_facet@V?$codecvt@DDU_Mbstatet@@@std@@@std@@YAAEBV?$codecvt@DDU_Mbstatet@@@0@AEBVlocale@0@@Z; std::use_facet<std::codecvt<char,char,_Mbstatet>>(std::locale const &)
0x14001f6a1  mov     rsi, rax
0x14001f6a4  mov     rcx, rax
0x14001f6a7  call    cs:__imp_?always_noconv@codecvt_base@std@@QEBA_NXZ; std::codecvt_base::always_noconv(void)
0x14001f6ad  test    al, al
0x14001f6af  jz      short loc_14001F6BB
0x14001f6b1  mov     qword ptr [rdi+68h], 0
0x14001f6b9  jmp     short loc_14001F6C9
0x14001f6bb  mov     [rdi+68h], rsi
0x14001f6bf  mov     rcx, rdi
0x14001f6c2  call    cs:__imp_?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ; std::streambuf::_Init(void)
0x14001f6c8  nop
0x14001f6c9  mov     rcx, [rsp+48h+var_20]
0x14001f6ce  test    rcx, rcx
0x14001f6d1  jz      short loc_14001F714
0x14001f6d3  mov     rax, [rcx]
0x14001f6d6  mov     rax, [rax+10h]
0x14001f6da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f6df  mov     r8, rax
0x14001f6e2  test    rax, rax
0x14001f6e5  jz      short loc_14001F714
0x14001f6e7  mov     rcx, [rax]
0x14001f6ea  mov     rax, [rcx]
0x14001f6ed  mov     edx, 1
0x14001f6f2  mov     rcx, r8
0x14001f6f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f6fa  jmp     short loc_14001F714
0x14001f6fc  mov     rax, [rbx]
0x14001f6ff  movsxd  rcx, dword ptr [rax+4]
0x14001f703  add     rcx, rbx
0x14001f706  xor     r8d, r8d
0x14001f709  lea     edx, [r8+2]
0x14001f70d  call    cs:__imp_?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::setstate(int,bool)
0x14001f713  nop
0x14001f714  mov     rax, [rbx]
0x14001f717  movsxd  rcx, dword ptr [rax+4]
0x14001f71b  mov     [rcx+rbx], r15
0x14001f71f  mov     rax, [rbx]
0x14001f722  movsxd  rcx, dword ptr [rax+4]
0x14001f726  lea     edx, [rcx-0A8h]
0x14001f72c  mov     [rcx+rbx-4], edx
0x14001f730  mov     rax, rbx
0x14001f733  mov     rbx, [rsp+48h+arg_10]
0x14001f738  add     rsp, 30h
0x14001f73c  pop     r15
0x14001f73e  pop     rdi
0x14001f73f  pop     rsi
0x14001f740  retn
```
