# std::tr1::_Parser<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_Wrapped_disjunction(void)

- ea: `0x18001aec0`
- end: `0x18001afa5`
- name: `?_Wrapped_disjunction@?$_Parser@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@AEAA_NXZ`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path`

## callers

- `0x180018980`

## callees

- `0x18000b8d8`
- `0x18000c654`
- `0x18000f378`
- `0x180012444`
- `0x180018ea4`
- `0x180019a5c`
- `0x180019dd0`
- `0x18001aec0`

## pseudocode

```c
char __fastcall std::tr1::_Parser<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_Wrapped_disjunction(
        _DWORD *a1)
{
  char v1; // bp
  int *v2; // rbx
  __int64 v4; // rcx
  int v5; // ebx
  __int64 v6; // rdx
  __int64 v8; // rdi

  v1 = 1;
  v2 = a1 + 24;
  ++a1[7];
  if ( (a1[25] & 0x8000000) == 0 && *v2 == 41 )
  {
    v4 = 5;
    goto LABEL_12;
  }
  if ( (a1[25] & 0x20) == 0 || *v2 != 63 )
  {
    if ( (a1[22] & 0x200) == 0 )
    {
      if ( ++a1[6] >= 0x20u )
        std::tr1::_Xbad(11);
      v8 = std::tr1::_Builder<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_Begin_capture_group(
             a1 + 10,
             (unsigned int)a1[6]);
      std::tr1::_Parser<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_Disjunction((__int64)a1);
      std::tr1::_Builder<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_End_group(
        a1 + 10,
        v8);
      a1[8] |= 1 << *(_DWORD *)(v8 + 32);
      goto LABEL_18;
    }
    goto LABEL_14;
  }
  std::tr1::_Parser<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_Next(a1);
  v5 = *v2;
  std::tr1::_Parser<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_Next(a1);
  if ( v5 == 58 )
  {
LABEL_14:
    std::tr1::_Parser<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_Do_noncapture_group(a1);
    goto LABEL_18;
  }
  if ( v5 == 33 )
  {
    LOBYTE(v6) = 1;
    std::tr1::_Parser<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_Do_assert_group(
      a1,
      v6);
    --a1[7];
    return 0;
  }
  if ( v5 != 61 )
  {
    v4 = 14;
LABEL_12:
    std::tr1::_Xbad(v4);
  }
  std::tr1::_Parser<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_Do_assert_group(
    a1,
    0);
  v1 = 0;
LABEL_18:
  --a1[7];
  return v1;
}

```

## disassembly

```asm
0x18001aec0  push    rbx
0x18001aec2  push    rbp
0x18001aec3  push    rsi
0x18001aec4  push    rdi
0x18001aec5  sub     rsp, 28h
0x18001aec9  mov     ebp, 1
0x18001aece  lea     rbx, [rcx+60h]
0x18001aed2  add     [rcx+1Ch], ebp
0x18001aed5  mov     rsi, rcx
0x18001aed8  test    dword ptr [rcx+64h], 8000000h
0x18001aedf  jnz     short loc_18001AEEB
0x18001aee1  cmp     dword ptr [rbx], 29h ; ')'
0x18001aee4  jnz     short loc_18001AEEB
0x18001aee6  lea     ecx, [rbp+4]
0x18001aee9  jmp     short loc_18001AF3A
0x18001aeeb  test    byte ptr [rcx+64h], 20h
0x18001aeef  jz      short loc_18001AF41
0x18001aef1  cmp     dword ptr [rbx], 3Fh ; '?'
0x18001aef4  jnz     short loc_18001AF41
0x18001aef6  call    ?_Next@?$_Parser@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@AEAAXXZ; std::tr1::_Parser<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_Next(void)
0x18001aefb  mov     ebx, [rbx]
0x18001aefd  mov     rcx, rsi
0x18001af00  call    ?_Next@?$_Parser@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@AEAAXXZ; std::tr1::_Parser<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_Next(void)
0x18001af05  cmp     ebx, 3Ah ; ':'
0x18001af08  jz      short loc_18001AF4A
0x18001af0a  cmp     ebx, 21h ; '!'
0x18001af0d  jnz     short loc_18001AF21
0x18001af0f  mov     dl, bpl
0x18001af12  mov     rcx, rsi
0x18001af15  call    ?_Do_assert_group@?$_Parser@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@AEAAX_N@Z; std::tr1::_Parser<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_Do_assert_group(bool)
0x18001af1a  dec     dword ptr [rsi+1Ch]
0x18001af1d  xor     al, al
0x18001af1f  jmp     short loc_18001AF9C
0x18001af21  cmp     ebx, 3Dh ; '='
0x18001af24  jnz     short loc_18001AF35
0x18001af26  xor     edx, edx
0x18001af28  mov     rcx, rsi
0x18001af2b  call    ?_Do_assert_group@?$_Parser@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@AEAAX_N@Z; std::tr1::_Parser<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_Do_assert_group(bool)
0x18001af30  xor     bpl, bpl
0x18001af33  jmp     short loc_18001AF96
0x18001af35  mov     ecx, 0Eh
0x18001af3a  call    ?_Xbad@tr1@std@@YAXW4error_type@regex_constants@12@@Z; std::tr1::_Xbad(std::tr1::regex_constants::error_type)
0x18001af3f  jmp     short loc_18001AF96
0x18001af41  test    dword ptr [rcx+58h], 200h
0x18001af48  jz      short loc_18001AF54
0x18001af4a  mov     rcx, rsi
0x18001af4d  call    ?_Do_noncapture_group@?$_Parser@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@AEAAXXZ; std::tr1::_Parser<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_Do_noncapture_group(void)
0x18001af52  jmp     short loc_18001AF96
0x18001af54  add     [rcx+18h], ebp
0x18001af57  cmp     dword ptr [rcx+18h], 20h ; ' '
0x18001af5b  jb      short loc_18001AF67
0x18001af5d  mov     ecx, 0Bh
0x18001af62  call    ?_Xbad@tr1@std@@YAXW4error_type@regex_constants@12@@Z; std::tr1::_Xbad(std::tr1::regex_constants::error_type)
0x18001af67  mov     edx, [rsi+18h]
0x18001af6a  lea     rcx, [rsi+28h]
0x18001af6e  call    ?_Begin_capture_group@?$_Builder@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@QEAAPEAV_Node_base@23@I@Z; std::tr1::_Builder<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_Begin_capture_group(uint)
0x18001af73  mov     rcx, rsi
0x18001af76  mov     rdi, rax
0x18001af79  call    ?_Disjunction@?$_Parser@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@AEAAXXZ; std::tr1::_Parser<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_Disjunction(void)
0x18001af7e  mov     rdx, rdi
0x18001af81  lea     rcx, [rsi+28h]
0x18001af85  call    ?_End_group@?$_Builder@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@QEAAXPEAV_Node_base@23@@Z; std::tr1::_Builder<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_End_group(std::tr1::_Node_base *)
0x18001af8a  mov     ecx, [rsi+20h]
0x18001af8d  mov     eax, [rdi+20h]
0x18001af90  bts     ecx, eax
0x18001af93  mov     [rsi+20h], ecx
0x18001af96  dec     dword ptr [rsi+1Ch]
0x18001af99  mov     al, bpl
0x18001af9c  add     rsp, 28h
0x18001afa0  pop     rdi
0x18001afa1  pop     rsi
0x18001afa2  pop     rbp
0x18001afa3  pop     rbx
0x18001afa4  retn
```
