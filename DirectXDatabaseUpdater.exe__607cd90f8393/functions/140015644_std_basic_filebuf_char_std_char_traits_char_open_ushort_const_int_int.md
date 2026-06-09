# std::basic_filebuf<char,std::char_traits<char>>::open(ushort const *,int,int)

- ea: `0x140015644`
- end: `0x1400156be`
- name: `?open@?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAAPEAV12@PEBGHH@Z`
- size: `122`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400143a4`
- `0x140014478`

## callees

- `0x140006340`
- `0x1400142a0`
- `0x140015398`
- `0x140015448`
- `0x140015644`

## import_xrefs

- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x140015668`
- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z` at `0x140015668`
- `msvcp_win!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x14001568c`
- `msvcp_win!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x14001568c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::filebuf::open(__int64 a1, const unsigned __int16 *a2, int a3)
{
  struct _iobuf *v4; // rax
  std::locale *v5; // rax
  __int64 v6; // rax
  _BYTE v8[24]; // [rsp+20h] [rbp-18h] BYREF

  if ( *(_QWORD *)(a1 + 128) )
    return 0;
  v4 = std::_Fiopen(a2, a3, 64);
  if ( !v4 )
    return 0;
  std::filebuf::_Init(a1, v4, 1);
  v5 = (std::locale *)std::streambuf::getloc(a1, v8);
  v6 = std::use_facet<std::codecvt<char,char,_Mbstatet>>(v5);
  std::filebuf::_Initcvt(a1, v6);
  std::locale::~locale((std::locale *)v8);
  return a1;
}

```

## disassembly

```asm
0x140015644  push    rbx
0x140015646  sub     rsp, 30h
0x14001564a  mov     eax, r8d
0x14001564d  mov     r9, rdx
0x140015650  mov     rbx, rcx
0x140015653  cmp     qword ptr [rcx+80h], 0
0x14001565b  jnz     short loc_1400156B6
0x14001565d  mov     r8d, 40h ; '@'
0x140015663  mov     edx, eax
0x140015665  mov     rcx, r9
0x140015668  call    cs:__imp_?_Fiopen@std@@YAPEAU_iobuf@@PEBGHH@Z; std::_Fiopen(ushort const *,int,int)
0x14001566e  test    rax, rax
0x140015671  jz      short loc_1400156B6
0x140015673  mov     r8d, 1
0x140015679  mov     rdx, rax
0x14001567c  mov     rcx, rbx
0x14001567f  call    ?_Init@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@12@@Z; std::filebuf::_Init(_iobuf *,std::filebuf::_Initfl)
0x140015684  lea     rdx, [rsp+38h+var_18]
0x140015689  mov     rcx, rbx
0x14001568c  call    cs:__imp_?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ; std::streambuf::getloc(void)
0x140015692  nop
0x140015693  mov     rcx, rax; this
0x140015696  call    ??$use_facet@V?$codecvt@DDU_Mbstatet@@@std@@@std@@YAAEBV?$codecvt@DDU_Mbstatet@@@0@AEBVlocale@0@@Z; std::use_facet<std::codecvt<char,char,_Mbstatet>>(std::locale const &)
0x14001569b  mov     rdx, rax
0x14001569e  mov     rcx, rbx
0x1400156a1  call    ?_Initcvt@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXAEBV?$codecvt@DDU_Mbstatet@@@2@@Z; std::filebuf::_Initcvt(std::codecvt<char,char,_Mbstatet> const &)
0x1400156a6  nop
0x1400156a7  lea     rcx, [rsp+38h+var_18]; this
0x1400156ac  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x1400156b1  mov     rax, rbx
0x1400156b4  jmp     short loc_1400156B8
0x1400156b6  xor     eax, eax
0x1400156b8  add     rsp, 30h
0x1400156bc  pop     rbx
0x1400156bd  retn
```
