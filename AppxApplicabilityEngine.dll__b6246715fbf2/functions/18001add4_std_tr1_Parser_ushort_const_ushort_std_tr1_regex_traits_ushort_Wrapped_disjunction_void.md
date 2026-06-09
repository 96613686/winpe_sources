# std::tr1::_Parser<ushort const *,ushort,std::tr1::regex_traits<ushort>>::_Wrapped_disjunction(void)

- ea: `0x18001add4`
- end: `0x18001aeb9`
- name: `?_Wrapped_disjunction@?$_Parser@PEBGGV?$regex_traits@G@tr1@std@@@tr1@std@@AEAA_NXZ`
- size: `229`
- prototype: `char __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path`

## callers

- `0x18001877c`

## callees

- `0x18000bb30`
- `0x180012444`
- `0x180018ea4`
- `0x180019970`
- `0x180019a10`
- `0x180019d84`
- `0x18001a8b4`
- `0x18001add4`

## pseudocode

```c
char __fastcall std::tr1::_Parser<unsigned short const *,unsigned short,std::tr1::regex_traits<unsigned short>>::_Wrapped_disjunction(
        __int64 a1)
{
  char v1; // bp
  int *v2; // rbx
  __int64 v4; // rcx
  int v5; // ebx
  __int64 v6; // rdx
  __int64 v8; // rdi

  v1 = 1;
  v2 = (int *)(a1 + 96);
  ++*(_DWORD *)(a1 + 28);
  if ( (*(_DWORD *)(a1 + 100) & 0x8000000) == 0 && *v2 == 41 )
  {
    v4 = 5;
    goto LABEL_12;
  }
  if ( (*(_BYTE *)(a1 + 100) & 0x20) == 0 || *v2 != 63 )
  {
    if ( (*(_DWORD *)(a1 + 88) & 0x200) == 0 )
    {
      if ( ++*(_DWORD *)(a1 + 24) >= 0x20u )
        std::tr1::_Xbad(11);
      v8 = std::tr1::_Builder<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_Begin_capture_group(a1 + 40);
      std::tr1::_Parser<unsigned short const *,unsigned short,std::tr1::regex_traits<unsigned short>>::_Disjunction(a1);
      std::tr1::_Builder<unsigned short const *,unsigned short,std::tr1::regex_traits<unsigned short>>::_End_group(
        a1 + 40,
        v8);
      *(_DWORD *)(a1 + 32) |= 1 << *(_DWORD *)(v8 + 32);
      goto LABEL_18;
    }
    goto LABEL_14;
  }
  std::tr1::_Parser<unsigned short const *,unsigned short,std::tr1::regex_traits<unsigned short>>::_Next((_QWORD *)a1);
  v5 = *v2;
  std::tr1::_Parser<unsigned short const *,unsigned short,std::tr1::regex_traits<unsigned short>>::_Next((_QWORD *)a1);
  if ( v5 == 58 )
  {
LABEL_14:
    std::tr1::_Parser<unsigned short const *,unsigned short,std::tr1::regex_traits<unsigned short>>::_Do_noncapture_group(a1);
    goto LABEL_18;
  }
  if ( v5 == 33 )
  {
    LOBYTE(v6) = 1;
    std::tr1::_Parser<unsigned short const *,unsigned short,std::tr1::regex_traits<unsigned short>>::_Do_assert_group(
      a1,
      v6);
    --*(_DWORD *)(a1 + 28);
    return 0;
  }
  if ( v5 != 61 )
  {
    v4 = 14;
LABEL_12:
    std::tr1::_Xbad(v4);
  }
  std::tr1::_Parser<unsigned short const *,unsigned short,std::tr1::regex_traits<unsigned short>>::_Do_assert_group(
    a1,
    0);
  v1 = 0;
LABEL_18:
  --*(_DWORD *)(a1 + 28);
  return v1;
}

```

## disassembly

```asm
0x18001add4  push    rbx
0x18001add6  push    rbp
0x18001add7  push    rsi
0x18001add8  push    rdi
0x18001add9  sub     rsp, 28h
0x18001addd  mov     ebp, 1
0x18001ade2  lea     rbx, [rcx+60h]
0x18001ade6  add     [rcx+1Ch], ebp
0x18001ade9  mov     rsi, rcx
0x18001adec  test    dword ptr [rcx+64h], 8000000h
0x18001adf3  jnz     short loc_18001ADFF
0x18001adf5  cmp     dword ptr [rbx], 29h ; ')'
0x18001adf8  jnz     short loc_18001ADFF
0x18001adfa  lea     ecx, [rbp+4]
0x18001adfd  jmp     short loc_18001AE4E
0x18001adff  test    byte ptr [rcx+64h], 20h
0x18001ae03  jz      short loc_18001AE55
0x18001ae05  cmp     dword ptr [rbx], 3Fh ; '?'
0x18001ae08  jnz     short loc_18001AE55
0x18001ae0a  call    ?_Next@?$_Parser@PEBGGV?$regex_traits@G@tr1@std@@@tr1@std@@AEAAXXZ; std::tr1::_Parser<ushort const *,ushort,std::tr1::regex_traits<ushort>>::_Next(void)
0x18001ae0f  mov     ebx, [rbx]
0x18001ae11  mov     rcx, rsi
0x18001ae14  call    ?_Next@?$_Parser@PEBGGV?$regex_traits@G@tr1@std@@@tr1@std@@AEAAXXZ; std::tr1::_Parser<ushort const *,ushort,std::tr1::regex_traits<ushort>>::_Next(void)
0x18001ae19  cmp     ebx, 3Ah ; ':'
0x18001ae1c  jz      short loc_18001AE5E
0x18001ae1e  cmp     ebx, 21h ; '!'
0x18001ae21  jnz     short loc_18001AE35
0x18001ae23  mov     dl, bpl
0x18001ae26  mov     rcx, rsi
0x18001ae29  call    ?_Do_assert_group@?$_Parser@PEBGGV?$regex_traits@G@tr1@std@@@tr1@std@@AEAAX_N@Z; std::tr1::_Parser<ushort const *,ushort,std::tr1::regex_traits<ushort>>::_Do_assert_group(bool)
0x18001ae2e  dec     dword ptr [rsi+1Ch]
0x18001ae31  xor     al, al
0x18001ae33  jmp     short loc_18001AEB0
0x18001ae35  cmp     ebx, 3Dh ; '='
0x18001ae38  jnz     short loc_18001AE49
0x18001ae3a  xor     edx, edx
0x18001ae3c  mov     rcx, rsi
0x18001ae3f  call    ?_Do_assert_group@?$_Parser@PEBGGV?$regex_traits@G@tr1@std@@@tr1@std@@AEAAX_N@Z; std::tr1::_Parser<ushort const *,ushort,std::tr1::regex_traits<ushort>>::_Do_assert_group(bool)
0x18001ae44  xor     bpl, bpl
0x18001ae47  jmp     short loc_18001AEAA
0x18001ae49  mov     ecx, 0Eh
0x18001ae4e  call    ?_Xbad@tr1@std@@YAXW4error_type@regex_constants@12@@Z; std::tr1::_Xbad(std::tr1::regex_constants::error_type)
0x18001ae53  jmp     short loc_18001AEAA
0x18001ae55  test    dword ptr [rcx+58h], 200h
0x18001ae5c  jz      short loc_18001AE68
0x18001ae5e  mov     rcx, rsi
0x18001ae61  call    ?_Do_noncapture_group@?$_Parser@PEBGGV?$regex_traits@G@tr1@std@@@tr1@std@@AEAAXXZ; std::tr1::_Parser<ushort const *,ushort,std::tr1::regex_traits<ushort>>::_Do_noncapture_group(void)
0x18001ae66  jmp     short loc_18001AEAA
0x18001ae68  add     [rcx+18h], ebp
0x18001ae6b  cmp     dword ptr [rcx+18h], 20h ; ' '
0x18001ae6f  jb      short loc_18001AE7B
0x18001ae71  mov     ecx, 0Bh
0x18001ae76  call    ?_Xbad@tr1@std@@YAXW4error_type@regex_constants@12@@Z; std::tr1::_Xbad(std::tr1::regex_constants::error_type)
0x18001ae7b  mov     edx, [rsi+18h]
0x18001ae7e  lea     rcx, [rsi+28h]
0x18001ae82  call    ?_Begin_capture_group@?$_Builder@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@QEAAPEAV_Node_base@23@I@Z; std::tr1::_Builder<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_Begin_capture_group(uint)
0x18001ae87  mov     rcx, rsi
0x18001ae8a  mov     rdi, rax
0x18001ae8d  call    ?_Disjunction@?$_Parser@PEBGGV?$regex_traits@G@tr1@std@@@tr1@std@@AEAAXXZ; std::tr1::_Parser<ushort const *,ushort,std::tr1::regex_traits<ushort>>::_Disjunction(void)
0x18001ae92  mov     rdx, rdi
0x18001ae95  lea     rcx, [rsi+28h]
0x18001ae99  call    ?_End_group@?$_Builder@PEBGGV?$regex_traits@G@tr1@std@@@tr1@std@@QEAAXPEAV_Node_base@23@@Z; std::tr1::_Builder<ushort const *,ushort,std::tr1::regex_traits<ushort>>::_End_group(std::tr1::_Node_base *)
0x18001ae9e  mov     ecx, [rsi+20h]
0x18001aea1  mov     eax, [rdi+20h]
0x18001aea4  bts     ecx, eax
0x18001aea7  mov     [rsi+20h], ecx
0x18001aeaa  dec     dword ptr [rsi+1Ch]
0x18001aead  mov     al, bpl
0x18001aeb0  add     rsp, 28h
0x18001aeb4  pop     rdi
0x18001aeb5  pop     rsi
0x18001aeb6  pop     rbp
0x18001aeb7  pop     rbx
0x18001aeb8  retn
```
