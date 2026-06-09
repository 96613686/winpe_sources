# std::basic_ifstream<char,std::char_traits<char>>::basic_ifstream<char,std::char_traits<char>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,int,int)

- ea: `0x180017ef4`
- end: `0x18001804a`
- name: `??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@HH@Z`
- size: `342`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180018a44`

## callees

- `0x180017dc4`
- `0x180017ef4`
- `0x18001819c`
- `0x180018f70`
- `0x180018ffc`

## import_xrefs

- `msvcp110_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x180017fc6`
- `msvcp110_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x180017fc6`
- `msvcp110_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x180018031`
- `msvcp110_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x180018031`
- `msvcp110_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x180017f24`
- `msvcp110_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x180017f24`
- `msvcp110_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x180017f81`
- `msvcp110_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x180017f81`
- `msvcp110_win!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x180017ff0`
- `msvcp110_win!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x180017ff0`
- `msvcp110_win!??0?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x180017f49`
- `msvcp110_win!??0?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z` at `0x180017f49`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall std::ifstream::ifstream(_QWORD *a1, const unsigned __int16 *a2)
{
  struct _iobuf *v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  _QWORD *v8; // [rsp+48h] [rbp+10h] BYREF
  int v9; // [rsp+58h] [rbp+20h]

  v9 = 0;
  *a1 = &std::ifstream::`vbtable';
  std::ios::ios(a1 + 22);
  v9 = 1;
  std::istream::istream(a1, a1 + 2, 0, 0);
  *(_QWORD *)((char *)a1 + *(int *)(*a1 + 4LL)) = &std::ifstream::`vftable';
  *(_DWORD *)((char *)a1 + *(int *)(*a1 + 4LL) - 4) = *(_DWORD *)(*a1 + 4LL) - 176;
  v8 = a1 + 2;
  std::streambuf::streambuf(a1 + 2);
  a1[2] = &std::filebuf::`vftable';
  std::filebuf::_Init(a1 + 2, 0, 0);
  if ( *((_QWORD *)a2 + 3) >= 8u )
    a2 = *(const unsigned __int16 **)a2;
  if ( a1[20]
    || (v4 = std::_Fiopen(a2, 1, 64)) == 0
    || (std::filebuf::_Init(a1 + 2, v4, 1),
        v5 = std::streambuf::getloc(a1 + 2, &v8),
        v6 = std::use_facet<std::codecvt<char,char,int>>(v5),
        std::filebuf::_Initcvt(a1 + 2, v6),
        std::locale::~locale((std::locale *)&v8),
        a1 == (_QWORD *)-16LL) )
  {
    std::ios::setstate((char *)a1 + *(int *)(*a1 + 4LL), 2);
  }
  return a1;
}

```

## disassembly

```asm
0x180017ef4  mov     [rsp+arg_18], r9d
0x180017ef9  mov     [rsp+arg_0], rcx
0x180017efe  push    rbx
0x180017eff  push    rsi
0x180017f00  push    rdi
0x180017f01  sub     rsp, 20h
0x180017f05  mov     rsi, rdx
0x180017f08  mov     rbx, rcx
0x180017f0b  mov     [rsp+38h+arg_18], 0
0x180017f13  lea     rax, ??_8?$basic_ifstream@DU?$char_traits@D@std@@@std@@7B@; const std::ifstream::`vbtable'
0x180017f1a  mov     [rcx], rax
0x180017f1d  add     rcx, 0B0h
0x180017f24  call    cs:__imp_??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::ios::ios(void)
0x180017f2b  nop     dword ptr [rax+rax+00h]
0x180017f30  nop
0x180017f31  mov     [rsp+38h+arg_18], 1
0x180017f39  lea     rdi, [rbx+10h]
0x180017f3d  xor     r9d, r9d
0x180017f40  xor     r8d, r8d
0x180017f43  mov     rdx, rdi
0x180017f46  mov     rcx, rbx
0x180017f49  call    cs:__imp_??0?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@_N@Z; std::istream::istream(std::streambuf *,bool)
0x180017f50  nop     dword ptr [rax+rax+00h]
0x180017f55  nop
0x180017f56  mov     rax, [rbx]
0x180017f59  movsxd  rcx, dword ptr [rax+4]
0x180017f5d  lea     rax, ??_7?$basic_ifstream@DU?$char_traits@D@std@@@std@@6B@; const std::ifstream::`vftable'
0x180017f64  mov     [rcx+rbx], rax
0x180017f68  mov     rax, [rbx]
0x180017f6b  movsxd  rcx, dword ptr [rax+4]
0x180017f6f  lea     edx, [rcx-0B0h]
0x180017f75  mov     [rcx+rbx-4], edx
0x180017f79  mov     [rsp+38h+arg_8], rdi
0x180017f7e  mov     rcx, rdi
0x180017f81  call    cs:__imp_??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::streambuf::streambuf(void)
0x180017f88  nop     dword ptr [rax+rax+00h]
0x180017f8d  nop
0x180017f8e  lea     rax, ??_7?$basic_filebuf@DU?$char_traits@D@std@@@std@@6B@; const std::filebuf::`vftable'
0x180017f95  mov     [rdi], rax
0x180017f98  xor     r8d, r8d
0x180017f9b  xor     edx, edx
0x180017f9d  mov     rcx, rdi
0x180017fa0  call    ?_Init@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@12@@Z; std::filebuf::_Init(_iobuf *,std::filebuf::_Initfl)
0x180017fa5  nop
0x180017fa6  cmp     qword ptr [rsi+18h], 8
0x180017fab  jb      short loc_180017FB0
0x180017fad  mov     rsi, [rsi]
0x180017fb0  cmp     qword ptr [rdi+90h], 0
0x180017fb8  jnz     short loc_180018020
0x180017fba  mov     edx, 1
0x180017fbf  lea     r8d, [rdx+3Fh]
0x180017fc3  mov     rcx, rsi
0x180017fc6  call    cs:__imp_?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z; std::_Fiopen(ushort const *,int,int)
0x180017fcd  nop     dword ptr [rax+rax+00h]
0x180017fd2  test    rax, rax
0x180017fd5  jz      short loc_180018020
0x180017fd7  mov     r8d, 1
0x180017fdd  mov     rdx, rax
0x180017fe0  mov     rcx, rdi
0x180017fe3  call    ?_Init@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@12@@Z; std::filebuf::_Init(_iobuf *,std::filebuf::_Initfl)
0x180017fe8  lea     rdx, [rsp+38h+arg_8]
0x180017fed  mov     rcx, rdi
0x180017ff0  call    cs:__imp_?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ; std::streambuf::getloc(void)
0x180017ff7  nop     dword ptr [rax+rax+00h]
0x180017ffc  nop
0x180017ffd  mov     rcx, rax
0x180018000  call    ??$use_facet@V?$codecvt@DDH@std@@@std@@YAAEBV?$codecvt@DDH@0@AEBVlocale@0@@Z; std::use_facet<std::codecvt<char,char,int>>(std::locale const &)
0x180018005  mov     rdx, rax
0x180018008  mov     rcx, rdi
0x18001800b  call    ?_Initcvt@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXPEBV?$codecvt@DDH@2@@Z; std::filebuf::_Initcvt(std::codecvt<char,char,int> const *)
0x180018010  nop
0x180018011  lea     rcx, [rsp+38h+arg_8]; this
0x180018016  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x18001801b  test    rdi, rdi
0x18001801e  jnz     short loc_18001803E
0x180018020  mov     rax, [rbx]
0x180018023  movsxd  rcx, dword ptr [rax+4]
0x180018027  add     rcx, rbx
0x18001802a  xor     r8d, r8d
0x18001802d  lea     edx, [r8+2]
0x180018031  call    cs:__imp_?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::setstate(int,bool)
0x180018038  nop     dword ptr [rax+rax+00h]
0x18001803d  nop
0x18001803e  mov     rax, rbx
0x180018041  add     rsp, 20h
0x180018045  pop     rdi
0x180018046  pop     rsi
0x180018047  pop     rbx
0x180018048  retn
```
