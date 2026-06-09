# FormCompleteFilePath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70> const &,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70> *)

- ea: `0x180003210`
- end: `0x180003327`
- name: `?FormCompleteFilePath@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@PEBG1PEAV12@@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180003d30`

## callees

- `0x180001098`
- `0x180003210`
- `0x18000379c`
- `0x1800038a8`
- `0x1800039e8`
- `0x1800095c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FormCompleteFilePath(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v5; // ebx
  void **v7; // rax
  _BYTE v9[8]; // [rsp+28h] [rbp-40h] BYREF
  void *Block[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v11; // [rsp+40h] [rbp-28h]
  unsigned __int64 v12; // [rsp+48h] [rbp-20h]

  v5 = 0;
  v12 = 7;
  v11 = 0;
  LOWORD(Block[0]) = 0;
  try
  {
    std::wstring::append();
    std::wstring::append(v9, L"EFI\\Microsoft\\Boot");
    if ( v11 )
    {
      v7 = Block;
      if ( v12 >= 8 )
        v7 = (void **)Block[0];
      if ( *((_WORD *)v7 + v11 - 1) != 92 )
        std::wstring::append(v9, L"\\");
    }
    std::wstring::append(v9, L"SiPolicy.p7b");
    std::wstring::assign(a4, v9, 0, -1);
  }
  catch ( ... )
  {
    v5 = -2147024882;
  }
  if ( v12 >= 8 )
    operator delete(Block[0]);
  return v5;
}

```

## disassembly

```asm
0x180003210  mov     r11, rsp
0x180003213  mov     [r11+10h], rbx
0x180003217  push    rdi
0x180003218  sub     rsp, 60h
0x18000321c  mov     rax, cs:__security_cookie
0x180003223  xor     rax, rsp
0x180003226  mov     [rsp+68h+var_18], rax
0x18000322b  mov     rdi, r9
0x18000322e  xor     ebx, ebx
0x180003230  mov     qword ptr [r11-20h], 7
0x180003238  mov     [r11-28h], rbx
0x18000323c  xor     eax, eax
0x18000323e  mov     word ptr [rsp+68h+Block], ax
0x180003243  or      r9, 0FFFFFFFFFFFFFFFFh
0x180003247  xor     r8d, r8d
0x18000324a  mov     rdx, rcx
0x18000324d  lea     rcx, [r11-40h]
0x180003251  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180003256  mov     rcx, [rsp+68h+var_28]
0x18000325b  test    rcx, rcx
0x18000325e  jz      short loc_18000328A
0x180003260  lea     rax, [rsp+68h+Block]
0x180003265  cmp     [rsp+68h+var_20], 8
0x18000326b  cmovnb  rax, [rsp+68h+Block]
0x180003271  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x180003277  jz      short loc_18000328A
0x180003279  lea     rdx, asc_18000BC18; "\\"
0x180003280  lea     rcx, [rsp+68h+var_40]
0x180003285  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18000328a  lea     rdx, aEfiMicrosoftBo; "EFI\\Microsoft\\Boot"
0x180003291  lea     rcx, [rsp+68h+var_40]
0x180003296  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18000329b  mov     rcx, [rsp+68h+var_28]
0x1800032a0  test    rcx, rcx
0x1800032a3  jz      short loc_1800032CF
0x1800032a5  lea     rax, [rsp+68h+Block]
0x1800032aa  cmp     [rsp+68h+var_20], 8
0x1800032b0  cmovnb  rax, [rsp+68h+Block]
0x1800032b6  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x1800032bc  jz      short loc_1800032CF
0x1800032be  lea     rdx, asc_18000BC18; "\\"
0x1800032c5  lea     rcx, [rsp+68h+var_40]
0x1800032ca  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x1800032cf  lea     rdx, aSipolicyP7b; "SiPolicy.p7b"
0x1800032d6  lea     rcx, [rsp+68h+var_40]
0x1800032db  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x1800032e0  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800032e4  xor     r8d, r8d
0x1800032e7  lea     rdx, [rsp+68h+var_40]
0x1800032ec  mov     rcx, rdi
0x1800032ef  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800032f4  nop
0x1800032f5  jmp     short loc_1800032FB
0x1800032f7  mov     ebx, [rsp+68h+var_48]
0x1800032fb  cmp     [rsp+68h+var_20], 8
0x180003301  jb      short loc_18000330D
0x180003303  mov     rcx, [rsp+68h+Block]; Block
0x180003308  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000330d  mov     eax, ebx
0x18000330f  mov     rcx, [rsp+68h+var_18]
0x180003314  xor     rcx, rsp; StackCookie
0x180003317  call    __security_check_cookie
0x18000331c  mov     rbx, [rsp+68h+arg_8]
0x180003321  add     rsp, 60h
0x180003325  pop     rdi
0x180003326  retn
```
