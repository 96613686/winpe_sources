# std::basic_ifstream<ushort,std::char_traits<ushort>>::basic_ifstream<ushort,std::char_traits<ushort>>(ushort const *,int,int)

- ea: `0x1800d9204`
- end: `0x1800d9330`
- name: `??0?$basic_ifstream@GU?$char_traits@G@std@@@std@@QEAA@PEBGHH@Z`
- size: `300`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800de91c`

## callees

- `0x1800d90b0`
- `0x1800d9204`
- `0x1800d9778`
- `0x1800dfe98`
- `0x1800dfee8`

## import_xrefs

- `msvcp_win!??0?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x1800d9259`
- `msvcp_win!??0?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x1800d9259`
- `msvcp_win!?getloc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEBA?AVlocale@2@XZ` at `0x1800d92de`
- `msvcp_win!?getloc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEBA?AVlocale@2@XZ` at `0x1800d92de`
- `msvcp_win!??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x1800d9286`
- `msvcp_win!??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x1800d9286`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x1800d9316`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x1800d9316`
- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x1800d92ba`
- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x1800d92ba`
- `msvcp_win!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x1800d923a`
- `msvcp_win!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x1800d923a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall std::basic_ifstream<unsigned short>::basic_ifstream<unsigned short>(
        _QWORD *a1,
        const unsigned __int16 *a2)
{
  struct _iobuf *v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  _BYTE v8[24]; // [rsp+20h] [rbp-18h] BYREF

  *a1 = &std::basic_ifstream<unsigned short>::`vbtable';
  std::basic_ios<unsigned short>::basic_ios<unsigned short>(a1 + 22);
  std::basic_istream<unsigned short>::basic_istream<unsigned short>(a1, a1 + 2, 0, 0);
  *(_QWORD *)((char *)a1 + *(int *)(*a1 + 4LL)) = &std::basic_ifstream<unsigned short>::`vftable';
  *(_DWORD *)((char *)a1 + *(int *)(*a1 + 4LL) - 4) = *(_DWORD *)(*a1 + 4LL) - 176;
  std::basic_streambuf<unsigned short>::basic_streambuf<unsigned short>(a1 + 2);
  a1[2] = &std::basic_filebuf<unsigned short>::`vftable';
  std::basic_filebuf<unsigned short>::_Init(a1 + 2, 0, 0);
  if ( a1[18] || (v4 = std::_Fiopen(a2, 1, 64)) == 0 )
  {
    std::basic_ios<unsigned short>::setstate((char *)a1 + *(int *)(*a1 + 4LL), 2);
  }
  else
  {
    std::basic_filebuf<unsigned short>::_Init(a1 + 2, v4, 1);
    v5 = std::basic_streambuf<unsigned short>::getloc(a1 + 2, v8);
    v6 = std::use_facet<std::codecvt<unsigned short,char,_Mbstatet>>(v5);
    std::basic_filebuf<unsigned short>::_Initcvt(a1 + 2, v6);
    std::locale::~locale((std::locale *)v8);
  }
  return a1;
}

```

## disassembly

```asm
0x1800d9204  mov     rax, rsp
0x1800d9207  mov     [rax+10h], rbx
0x1800d920b  mov     [rax+18h], rsi
0x1800d920f  mov     [rax+20h], r9d
0x1800d9213  mov     [rax+8], rcx
0x1800d9217  push    rdi
0x1800d9218  sub     rsp, 30h
0x1800d921c  mov     rsi, rdx
0x1800d921f  mov     rbx, rcx
0x1800d9222  mov     dword ptr [rax+20h], 0
0x1800d9229  lea     rax, ??_8?$basic_ifstream@GU?$char_traits@G@std@@@std@@7B@; const std::basic_ifstream<ushort>::`vbtable'
0x1800d9230  mov     [rcx], rax
0x1800d9233  add     rcx, 0B0h
0x1800d923a  call    cs:__imp_??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ; std::basic_ios<ushort>::basic_ios<ushort>(void)
0x1800d9240  nop
0x1800d9241  mov     [rsp+38h+arg_18], 1
0x1800d9249  lea     rdi, [rbx+10h]
0x1800d924d  xor     r9d, r9d
0x1800d9250  xor     r8d, r8d
0x1800d9253  mov     rdx, rdi
0x1800d9256  mov     rcx, rbx
0x1800d9259  call    cs:__imp_??0?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z; std::basic_istream<ushort>::basic_istream<ushort>(std::basic_streambuf<ushort> *,bool)
0x1800d925f  nop
0x1800d9260  mov     rax, [rbx]
0x1800d9263  movsxd  rcx, dword ptr [rax+4]
0x1800d9267  lea     rax, ??_7?$basic_ifstream@GU?$char_traits@G@std@@@std@@6B@; const std::basic_ifstream<ushort>::`vftable'
0x1800d926e  mov     [rcx+rbx], rax
0x1800d9272  mov     rax, [rbx]
0x1800d9275  movsxd  rcx, dword ptr [rax+4]
0x1800d9279  lea     edx, [rcx-0B0h]
0x1800d927f  mov     [rcx+rbx-4], edx
0x1800d9283  mov     rcx, rdi
0x1800d9286  call    cs:__imp_??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ; std::basic_streambuf<ushort>::basic_streambuf<ushort>(void)
0x1800d928c  lea     rax, ??_7?$basic_filebuf@GU?$char_traits@G@std@@@std@@6B@; const std::basic_filebuf<ushort>::`vftable'
0x1800d9293  mov     [rdi], rax
0x1800d9296  xor     r8d, r8d
0x1800d9299  xor     edx, edx
0x1800d929b  mov     rcx, rdi
0x1800d929e  call    ?_Init@?$basic_filebuf@GU?$char_traits@G@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@12@@Z; std::basic_filebuf<ushort>::_Init(_iobuf *,std::basic_filebuf<ushort>::_Initfl)
0x1800d92a3  nop
0x1800d92a4  cmp     qword ptr [rdi+80h], 0
0x1800d92ac  jnz     short loc_1800D9305
0x1800d92ae  mov     edx, 1
0x1800d92b3  lea     r8d, [rdx+3Fh]
0x1800d92b7  mov     rcx, rsi
0x1800d92ba  call    cs:__imp_?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z; std::_Fiopen(ushort const *,int,int)
0x1800d92c0  test    rax, rax
0x1800d92c3  jz      short loc_1800D9305
0x1800d92c5  mov     r8d, 1
0x1800d92cb  mov     rdx, rax
0x1800d92ce  mov     rcx, rdi
0x1800d92d1  call    ?_Init@?$basic_filebuf@GU?$char_traits@G@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@12@@Z; std::basic_filebuf<ushort>::_Init(_iobuf *,std::basic_filebuf<ushort>::_Initfl)
0x1800d92d6  lea     rdx, [rsp+38h+var_18]
0x1800d92db  mov     rcx, rdi
0x1800d92de  call    cs:__imp_?getloc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEBA?AVlocale@2@XZ; std::basic_streambuf<ushort>::getloc(void)
0x1800d92e4  nop
0x1800d92e5  mov     rcx, rax
0x1800d92e8  call    ??$use_facet@V?$codecvt@GDU_Mbstatet@@@std@@@std@@YAAEBV?$codecvt@GDU_Mbstatet@@@0@AEBVlocale@0@@Z; std::use_facet<std::codecvt<ushort,char,_Mbstatet>>(std::locale const &)
0x1800d92ed  mov     rdx, rax
0x1800d92f0  mov     rcx, rdi
0x1800d92f3  call    ?_Initcvt@?$basic_filebuf@GU?$char_traits@G@std@@@std@@IEAAXAEBV?$codecvt@GDU_Mbstatet@@@2@@Z; std::basic_filebuf<ushort>::_Initcvt(std::codecvt<ushort,char,_Mbstatet> const &)
0x1800d92f8  nop
0x1800d92f9  lea     rcx, [rsp+38h+var_18]; this
0x1800d92fe  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x1800d9303  jmp     short loc_1800D931D
0x1800d9305  mov     rax, [rbx]
0x1800d9308  movsxd  rcx, dword ptr [rax+4]
0x1800d930c  add     rcx, rbx
0x1800d930f  xor     r8d, r8d
0x1800d9312  lea     edx, [r8+2]
0x1800d9316  call    cs:__imp_?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z; std::basic_ios<ushort>::setstate(int,bool)
0x1800d931c  nop
0x1800d931d  mov     rax, rbx
0x1800d9320  mov     rbx, [rsp+38h+arg_8]
0x1800d9325  mov     rsi, [rsp+38h+arg_10]
0x1800d932a  add     rsp, 30h
0x1800d932e  pop     rdi
0x1800d932f  retn
```
