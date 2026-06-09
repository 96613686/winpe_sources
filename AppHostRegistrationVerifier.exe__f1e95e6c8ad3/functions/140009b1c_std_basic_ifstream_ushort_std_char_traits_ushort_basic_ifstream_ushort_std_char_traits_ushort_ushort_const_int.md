# std::basic_ifstream<ushort,std::char_traits<ushort>>::basic_ifstream<ushort,std::char_traits<ushort>>(ushort const *,int,int)

- ea: `0x140009b1c`
- end: `0x140009c48`
- name: `??0?$basic_ifstream@GU?$char_traits@G@std@@@std@@QEAA@PEBGHH@Z`
- size: `300`
- prototype: `_QWORD *__fastcall(_QWORD *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000bc30`

## callees

- `0x14000989c`
- `0x140009b1c`
- `0x14000a4b0`
- `0x14000fa04`
- `0x14000fa54`

## import_xrefs

- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x140009c2e`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x140009c2e`
- `msvcp_win!??0?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x140009b71`
- `msvcp_win!??0?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z` at `0x140009b71`
- `msvcp_win!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x140009b52`
- `msvcp_win!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x140009b52`
- `msvcp_win!?getloc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEBA?AVlocale@2@XZ` at `0x140009bf6`
- `msvcp_win!?getloc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEBA?AVlocale@2@XZ` at `0x140009bf6`
- `msvcp_win!??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x140009b9e`
- `msvcp_win!??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x140009b9e`
- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x140009bd2`
- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x140009bd2`

## pseudocode

```c
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
0x140009b1c  mov     rax, rsp
0x140009b1f  mov     [rax+10h], rbx
0x140009b23  mov     [rax+18h], rsi
0x140009b27  mov     [rax+20h], r9d
0x140009b2b  mov     [rax+8], rcx
0x140009b2f  push    rdi
0x140009b30  sub     rsp, 30h
0x140009b34  mov     rsi, rdx
0x140009b37  mov     rbx, rcx
0x140009b3a  mov     dword ptr [rax+20h], 0
0x140009b41  lea     rax, ??_8?$basic_ifstream@GU?$char_traits@G@std@@@std@@7B@; const std::basic_ifstream<ushort>::`vbtable'
0x140009b48  mov     [rcx], rax
0x140009b4b  add     rcx, 0B0h
0x140009b52  call    cs:__imp_??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ; std::basic_ios<ushort>::basic_ios<ushort>(void)
0x140009b58  nop
0x140009b59  mov     [rsp+38h+arg_18], 1
0x140009b61  lea     rdi, [rbx+10h]
0x140009b65  xor     r9d, r9d
0x140009b68  xor     r8d, r8d
0x140009b6b  mov     rdx, rdi
0x140009b6e  mov     rcx, rbx
0x140009b71  call    cs:__imp_??0?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@_N@Z; std::basic_istream<ushort>::basic_istream<ushort>(std::basic_streambuf<ushort> *,bool)
0x140009b77  nop
0x140009b78  mov     rax, [rbx]
0x140009b7b  movsxd  rcx, dword ptr [rax+4]
0x140009b7f  lea     rax, ??_7?$basic_ifstream@GU?$char_traits@G@std@@@std@@6B@; const std::basic_ifstream<ushort>::`vftable'
0x140009b86  mov     [rcx+rbx], rax
0x140009b8a  mov     rax, [rbx]
0x140009b8d  movsxd  rcx, dword ptr [rax+4]
0x140009b91  lea     edx, [rcx-0B0h]
0x140009b97  mov     [rcx+rbx-4], edx
0x140009b9b  mov     rcx, rdi
0x140009b9e  call    cs:__imp_??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ; std::basic_streambuf<ushort>::basic_streambuf<ushort>(void)
0x140009ba4  lea     rax, ??_7?$basic_filebuf@GU?$char_traits@G@std@@@std@@6B@; const std::basic_filebuf<ushort>::`vftable'
0x140009bab  mov     [rdi], rax
0x140009bae  xor     r8d, r8d
0x140009bb1  xor     edx, edx
0x140009bb3  mov     rcx, rdi
0x140009bb6  call    ?_Init@?$basic_filebuf@GU?$char_traits@G@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@12@@Z; std::basic_filebuf<ushort>::_Init(_iobuf *,std::basic_filebuf<ushort>::_Initfl)
0x140009bbb  nop
0x140009bbc  cmp     qword ptr [rdi+80h], 0
0x140009bc4  jnz     short loc_140009C1D
0x140009bc6  mov     edx, 1
0x140009bcb  lea     r8d, [rdx+3Fh]
0x140009bcf  mov     rcx, rsi
0x140009bd2  call    cs:__imp_?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z; std::_Fiopen(ushort const *,int,int)
0x140009bd8  test    rax, rax
0x140009bdb  jz      short loc_140009C1D
0x140009bdd  mov     r8d, 1
0x140009be3  mov     rdx, rax
0x140009be6  mov     rcx, rdi
0x140009be9  call    ?_Init@?$basic_filebuf@GU?$char_traits@G@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@12@@Z; std::basic_filebuf<ushort>::_Init(_iobuf *,std::basic_filebuf<ushort>::_Initfl)
0x140009bee  lea     rdx, [rsp+38h+var_18]
0x140009bf3  mov     rcx, rdi
0x140009bf6  call    cs:__imp_?getloc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@QEBA?AVlocale@2@XZ; std::basic_streambuf<ushort>::getloc(void)
0x140009bfc  nop
0x140009bfd  mov     rcx, rax
0x140009c00  call    ??$use_facet@V?$codecvt@GDU_Mbstatet@@@std@@@std@@YAAEBV?$codecvt@GDU_Mbstatet@@@0@AEBVlocale@0@@Z; std::use_facet<std::codecvt<ushort,char,_Mbstatet>>(std::locale const &)
0x140009c05  mov     rdx, rax
0x140009c08  mov     rcx, rdi
0x140009c0b  call    ?_Initcvt@?$basic_filebuf@GU?$char_traits@G@std@@@std@@IEAAXAEBV?$codecvt@GDU_Mbstatet@@@2@@Z; std::basic_filebuf<ushort>::_Initcvt(std::codecvt<ushort,char,_Mbstatet> const &)
0x140009c10  nop
0x140009c11  lea     rcx, [rsp+38h+var_18]; this
0x140009c16  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x140009c1b  jmp     short loc_140009C35
0x140009c1d  mov     rax, [rbx]
0x140009c20  movsxd  rcx, dword ptr [rax+4]
0x140009c24  add     rcx, rbx
0x140009c27  xor     r8d, r8d
0x140009c2a  lea     edx, [r8+2]
0x140009c2e  call    cs:__imp_?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z; std::basic_ios<ushort>::setstate(int,bool)
0x140009c34  nop
0x140009c35  mov     rax, rbx
0x140009c38  mov     rbx, [rsp+38h+arg_8]
0x140009c3d  mov     rsi, [rsp+38h+arg_10]
0x140009c42  add     rsp, 30h
0x140009c46  pop     rdi
0x140009c47  retn
```
