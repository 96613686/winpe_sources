# std::basic_ifstream<char,std::char_traits<char>>::basic_ifstream<char,std::char_traits<char>>(char const *,int,int)

- ea: `0x18002a604`
- end: `0x18002a730`
- name: `??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@PEBDHH@Z`
- size: `300`
- prototype: `_QWORD *__fastcall(_QWORD *, const char *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002a5b8`

## callees

- `0x18000eaa8`
- `0x18002a444`
- `0x18002a604`
- `0x1800305a8`
- `0x180030658`

## import_xrefs

- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x18002a63b`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x18002a63b`
- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x18002a719`
- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x18002a719`
- `msvcp_win!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x18002a6e1`
- `msvcp_win!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x18002a6e1`
- `msvcp_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x18002a687`
- `msvcp_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x18002a687`
- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBDHH@Z` at `0x18002a6bd`
- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBDHH@Z` at `0x18002a6bd`
- `msvcp_win!??0?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x18002a65a`
- `msvcp_win!??0?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x18002a65a`

## pseudocode

```c
_QWORD *__fastcall std::ifstream::ifstream(_QWORD *a1, const char *a2, int a3)
{
  struct _iobuf *v6; // rax
  std::locale *v7; // rax
  __int64 v8; // rax
  _BYTE v10[40]; // [rsp+20h] [rbp-28h] BYREF

  *a1 = &std::ifstream::`vbtable';
  std::ios::ios(a1 + 22);
  std::istream::istream(a1, a1 + 2, 0, 0);
  *(_QWORD *)((char *)a1 + *(int *)(*a1 + 4LL)) = &std::ifstream::`vftable';
  *(_DWORD *)((char *)a1 + *(int *)(*a1 + 4LL) - 4) = *(_DWORD *)(*a1 + 4LL) - 176;
  std::streambuf::streambuf(a1 + 2);
  a1[2] = &std::filebuf::`vftable';
  std::filebuf::_Init(a1 + 2, 0, 0);
  if ( a1[18] || (v6 = std::_Fiopen(a2, a3 | 1u, 64)) == 0 )
  {
    std::ios::setstate((char *)a1 + *(int *)(*a1 + 4LL), 2);
  }
  else
  {
    std::filebuf::_Init(a1 + 2, v6, 1);
    v7 = (std::locale *)std::streambuf::getloc(a1 + 2, v10);
    v8 = std::use_facet<std::codecvt<char,char,_Mbstatet>>(v7);
    std::filebuf::_Initcvt(a1 + 2, v8);
    std::locale::~locale((std::locale *)v10);
  }
  return a1;
}

```

## disassembly

```asm
0x18002a604  mov     rax, rsp
0x18002a607  mov     [rax+10h], rbx
0x18002a60b  mov     [rax+20h], r9d
0x18002a60f  mov     [rax+8], rcx
0x18002a613  push    rbp
0x18002a614  push    rsi
0x18002a615  push    rdi
0x18002a616  sub     rsp, 30h
0x18002a61a  mov     esi, r8d
0x18002a61d  mov     rbp, rdx
0x18002a620  mov     rbx, rcx
0x18002a623  mov     dword ptr [rax+20h], 0
0x18002a62a  lea     rax, ??_8?$basic_ifstream@DU?$char_traits@D@std@@@std@@7B@; const std::ifstream::`vbtable'
0x18002a631  mov     [rcx], rax
0x18002a634  add     rcx, 0B0h
0x18002a63b  call    cs:__imp_??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::ios::ios(void)
0x18002a641  nop
0x18002a642  mov     [rsp+48h+arg_18], 1
0x18002a64a  lea     rdi, [rbx+10h]
0x18002a64e  xor     r9d, r9d
0x18002a651  xor     r8d, r8d
0x18002a654  mov     rdx, rdi
0x18002a657  mov     rcx, rbx
0x18002a65a  call    cs:__imp_??0?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z; std::istream::istream(std::streambuf *,bool)
0x18002a660  nop
0x18002a661  mov     rax, [rbx]
0x18002a664  movsxd  rcx, dword ptr [rax+4]
0x18002a668  lea     rax, ??_7?$basic_ifstream@DU?$char_traits@D@std@@@std@@6B@; const std::ifstream::`vftable'
0x18002a66f  mov     [rcx+rbx], rax
0x18002a673  mov     rax, [rbx]
0x18002a676  movsxd  rcx, dword ptr [rax+4]
0x18002a67a  lea     edx, [rcx-0B0h]
0x18002a680  mov     [rcx+rbx-4], edx
0x18002a684  mov     rcx, rdi
0x18002a687  call    cs:__imp_??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::streambuf::streambuf(void)
0x18002a68d  lea     rax, ??_7?$basic_filebuf@DU?$char_traits@D@std@@@std@@6B@; const std::filebuf::`vftable'
0x18002a694  mov     [rdi], rax
0x18002a697  xor     r8d, r8d
0x18002a69a  xor     edx, edx
0x18002a69c  mov     rcx, rdi
0x18002a69f  call    ?_Init@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@12@@Z; std::filebuf::_Init(_iobuf *,std::filebuf::_Initfl)
0x18002a6a4  nop
0x18002a6a5  cmp     qword ptr [rdi+80h], 0
0x18002a6ad  jnz     short loc_18002A708
0x18002a6af  or      esi, 1
0x18002a6b2  mov     r8d, 40h ; '@'
0x18002a6b8  mov     edx, esi
0x18002a6ba  mov     rcx, rbp
0x18002a6bd  call    cs:__imp_?_Fiopen@std@@YAPEAU_iobuf@@PEBDHH@Z; std::_Fiopen(char const *,int,int)
0x18002a6c3  test    rax, rax
0x18002a6c6  jz      short loc_18002A708
0x18002a6c8  mov     r8d, 1
0x18002a6ce  mov     rdx, rax
0x18002a6d1  mov     rcx, rdi
0x18002a6d4  call    ?_Init@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@12@@Z; std::filebuf::_Init(_iobuf *,std::filebuf::_Initfl)
0x18002a6d9  lea     rdx, [rsp+48h+var_28]
0x18002a6de  mov     rcx, rdi
0x18002a6e1  call    cs:__imp_?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ; std::streambuf::getloc(void)
0x18002a6e7  nop
0x18002a6e8  mov     rcx, rax; this
0x18002a6eb  call    ??$use_facet@V?$codecvt@DDU_Mbstatet@@@std@@@std@@YAAEBV?$codecvt@DDU_Mbstatet@@@0@AEBVlocale@0@@Z; std::use_facet<std::codecvt<char,char,_Mbstatet>>(std::locale const &)
0x18002a6f0  mov     rdx, rax
0x18002a6f3  mov     rcx, rdi
0x18002a6f6  call    ?_Initcvt@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXAEBV?$codecvt@DDU_Mbstatet@@@2@@Z; std::filebuf::_Initcvt(std::codecvt<char,char,_Mbstatet> const &)
0x18002a6fb  nop
0x18002a6fc  lea     rcx, [rsp+48h+var_28]; this
0x18002a701  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x18002a706  jmp     short loc_18002A720
0x18002a708  mov     rax, [rbx]
0x18002a70b  movsxd  rcx, dword ptr [rax+4]
0x18002a70f  add     rcx, rbx
0x18002a712  xor     r8d, r8d
0x18002a715  lea     edx, [r8+2]
0x18002a719  call    cs:__imp_?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::setstate(int,bool)
0x18002a71f  nop
0x18002a720  mov     rax, rbx
0x18002a723  mov     rbx, [rsp+48h+arg_8]
0x18002a728  add     rsp, 30h
0x18002a72c  pop     rdi
0x18002a72d  pop     rsi
0x18002a72e  pop     rbp
0x18002a72f  retn
```
