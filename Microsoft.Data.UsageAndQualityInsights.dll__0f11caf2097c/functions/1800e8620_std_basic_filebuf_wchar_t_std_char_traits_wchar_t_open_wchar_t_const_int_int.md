# std::basic_filebuf<wchar_t,std::char_traits<wchar_t>>::open(wchar_t const *,int,int)

- ea: `0x1800e8620`
- end: `0x1800e870b`
- name: `?open@?$basic_filebuf@_WU?$char_traits@_W@std@@@std@@QEAAPEAV12@PEB_WHH@Z`
- size: `235`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800e6f28`
- `0x1800e7a50`

## callees

- `0x1800e50e8`
- `0x1800e8620`
- `0x180108010`

## import_xrefs

- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEB_WHH@Z` at `0x1800e864c`
- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEB_WHH@Z` at `0x1800e864c`
- `msvcp_win!?always_noconv@codecvt_base@std@@QEBA_NXZ` at `0x1800e86a6`
- `msvcp_win!?always_noconv@codecvt_base@std@@QEBA_NXZ` at `0x1800e86a6`
- `msvcp_win!?getloc@?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@QEBA?AVlocale@2@XZ` at `0x1800e8691`
- `msvcp_win!?getloc@?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@QEBA?AVlocale@2@XZ` at `0x1800e8691`
- `msvcp_win!?_Init@?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@IEAAXXZ` at `0x1800e8669`
- `msvcp_win!?_Init@?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@IEAAXXZ` at `0x1800e86c1`
- `msvcp_win!?_Init@?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@IEAAXXZ` at `0x1800e8669`
- `msvcp_win!?_Init@?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@IEAAXXZ` at `0x1800e86c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::wfilebuf::open(__int64 a1, const wchar_t *a2, int a3)
{
  struct _iobuf *v4; // rdi
  __int64 v5; // rax
  std::codecvt_base *v6; // rdi
  void (__fastcall ***v7)(_QWORD, __int64); // rax
  _BYTE v9[8]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v10; // [rsp+28h] [rbp-10h]

  if ( *(_QWORD *)(a1 + 128) )
    return 0;
  v4 = std::_Fiopen(a2, a3, 64);
  if ( !v4 )
    return 0;
  *(_BYTE *)(a1 + 124) = 1;
  *(_BYTE *)(a1 + 114) = 0;
  std::wstreambuf::_Init(a1);
  *(_QWORD *)(a1 + 128) = v4;
  *(_QWORD *)(a1 + 116) = `std::wfilebuf::_Init'::`2'::_Stinit;
  *(_QWORD *)(a1 + 104) = 0;
  v5 = std::wstreambuf::getloc(a1, v9);
  v6 = (std::codecvt_base *)std::use_facet<std::codecvt<wchar_t,char,_Mbstatet>>(v5);
  if ( std::codecvt_base::always_noconv(v6) )
  {
    *(_QWORD *)(a1 + 104) = 0;
  }
  else
  {
    *(_QWORD *)(a1 + 104) = v6;
    std::wstreambuf::_Init(a1);
  }
  if ( v10 )
  {
    v7 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v7 )
      (**v7)(v7, 1);
  }
  return a1;
}

```

## disassembly

```asm
0x1800e8620  mov     [rsp+arg_0], rbx
0x1800e8625  push    rdi
0x1800e8626  sub     rsp, 30h
0x1800e862a  mov     eax, r8d
0x1800e862d  mov     r9, rdx
0x1800e8630  mov     rbx, rcx
0x1800e8633  cmp     qword ptr [rcx+80h], 0
0x1800e863b  jnz     loc_1800E86FE
0x1800e8641  mov     r8d, 40h ; '@'
0x1800e8647  mov     edx, eax
0x1800e8649  mov     rcx, r9
0x1800e864c  call    cs:__imp_?_Fiopen@std@@YAPEAU_iobuf@@PEB_WHH@Z; std::_Fiopen(wchar_t const *,int,int)
0x1800e8652  mov     rdi, rax
0x1800e8655  test    rax, rax
0x1800e8658  jz      loc_1800E86FE
0x1800e865e  mov     byte ptr [rbx+7Ch], 1
0x1800e8662  mov     byte ptr [rbx+72h], 0
0x1800e8666  mov     rcx, rbx
0x1800e8669  call    cs:__imp_?_Init@?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@IEAAXXZ; std::wstreambuf::_Init(void)
0x1800e866f  mov     [rbx+80h], rdi
0x1800e8676  mov     rax, cs:?_Stinit@?1??_Init@?$basic_filebuf@_WU?$char_traits@_W@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@23@@Z@4U_Mbstatet@@A; _Mbstatet `std::wfilebuf::_Init(_iobuf *,std::wfilebuf::_Initfl)'::`2'::_Stinit
0x1800e867d  mov     [rbx+74h], rax
0x1800e8681  mov     qword ptr [rbx+68h], 0
0x1800e8689  lea     rdx, [rsp+38h+var_18]
0x1800e868e  mov     rcx, rbx
0x1800e8691  call    cs:__imp_?getloc@?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@QEBA?AVlocale@2@XZ; std::wstreambuf::getloc(void)
0x1800e8697  nop
0x1800e8698  mov     rcx, rax
0x1800e869b  call    ??$use_facet@V?$codecvt@_WDU_Mbstatet@@@std@@@std@@YAAEBV?$codecvt@_WDU_Mbstatet@@@0@AEBVlocale@0@@Z; std::use_facet<std::codecvt<wchar_t,char,_Mbstatet>>(std::locale const &)
0x1800e86a0  mov     rdi, rax
0x1800e86a3  mov     rcx, rax
0x1800e86a6  call    cs:__imp_?always_noconv@codecvt_base@std@@QEBA_NXZ; std::codecvt_base::always_noconv(void)
0x1800e86ac  test    al, al
0x1800e86ae  jz      short loc_1800E86BA
0x1800e86b0  mov     qword ptr [rbx+68h], 0
0x1800e86b8  jmp     short loc_1800E86C8
0x1800e86ba  mov     [rbx+68h], rdi
0x1800e86be  mov     rcx, rbx
0x1800e86c1  call    cs:__imp_?_Init@?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@IEAAXXZ; std::wstreambuf::_Init(void)
0x1800e86c7  nop
0x1800e86c8  mov     rcx, [rsp+38h+var_10]
0x1800e86cd  test    rcx, rcx
0x1800e86d0  jz      short loc_1800E86F9
0x1800e86d2  mov     rax, [rcx]
0x1800e86d5  mov     rax, [rax+10h]
0x1800e86d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e86de  mov     r8, rax
0x1800e86e1  test    rax, rax
0x1800e86e4  jz      short loc_1800E86F9
0x1800e86e6  mov     rcx, [rax]
0x1800e86e9  mov     rax, [rcx]
0x1800e86ec  mov     edx, 1
0x1800e86f1  mov     rcx, r8
0x1800e86f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e86f9  mov     rax, rbx
0x1800e86fc  jmp     short loc_1800E8700
0x1800e86fe  xor     eax, eax
0x1800e8700  mov     rbx, [rsp+38h+arg_0]
0x1800e8705  add     rsp, 30h
0x1800e8709  pop     rdi
0x1800e870a  retn
```
