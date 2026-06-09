# std::tr1::_Parser<ushort const *,ushort,std::tr1::regex_traits<ushort>>::_Disjunction(void)

- ea: `0x180019970`
- end: `0x180019a0a`
- name: `?_Disjunction@?$_Parser@PEBGGV?$regex_traits@G@tr1@std@@@tr1@std@@AEAAXXZ`
- size: `154`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x18001970c`
- `0x180019a10`
- `0x180019d84`
- `0x18001add4`

## callees

- `0x18000bb30`
- `0x18000f418`
- `0x18001877c`
- `0x180018f08`
- `0x180019970`
- `0x18001a144`
- `0x18001a8b4`

## pseudocode

```c
__int64 __fastcall std::tr1::_Parser<unsigned short const *,unsigned short,std::tr1::regex_traits<unsigned short>>::_Disjunction(
        __int64 a1)
{
  __int64 v1; // rdi
  __int64 v3; // rbp
  _DWORD *v4; // rbx
  __int64 result; // rax
  __int64 v6; // rax
  __int64 v7; // r14
  __int64 v8; // rax

  v1 = a1 + 40;
  v3 = *(_QWORD *)(a1 + 48);
  v4 = (_DWORD *)(a1 + 96);
  result = ((__int64 (*)(void))std::tr1::_Parser<unsigned short const *,unsigned short,std::tr1::regex_traits<unsigned short>>::_Alternative)();
  if ( !(_BYTE)result )
  {
    if ( *v4 != 124 )
      return result;
    v6 = std::tr1::_Builder<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_New_node(
           v1,
           8);
    std::tr1::_Builder<unsigned short const *,unsigned short,std::tr1::regex_traits<unsigned short>>::_End_group(v1, v6);
  }
  result = std::tr1::_Builder<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_Begin_if(
             v1,
             v3);
  v7 = result;
  while ( *v4 == 124 )
  {
    std::tr1::_Parser<unsigned short const *,unsigned short,std::tr1::regex_traits<unsigned short>>::_Next(a1);
    if ( !(unsigned __int8)std::tr1::_Parser<unsigned short const *,unsigned short,std::tr1::regex_traits<unsigned short>>::_Alternative(a1) )
    {
      v8 = std::tr1::_Builder<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_New_node(
             v1,
             8);
      std::tr1::_Builder<unsigned short const *,unsigned short,std::tr1::regex_traits<unsigned short>>::_End_group(
        v1,
        v8);
    }
    result = std::tr1::_Builder<unsigned short const *,unsigned short,std::tr1::regex_traits<unsigned short>>::_Else_if(
               v1,
               v3,
               v7);
  }
  return result;
}

```

## disassembly

```asm
0x180019970  push    rbx
0x180019972  push    rbp
0x180019973  push    rsi
0x180019974  push    rdi
0x180019975  push    r14
0x180019977  sub     rsp, 20h
0x18001997b  lea     rdi, [rcx+28h]
0x18001997f  mov     rsi, rcx
0x180019982  mov     rbp, [rdi+8]
0x180019986  lea     rbx, [rcx+60h]
0x18001998a  call    ?_Alternative@?$_Parser@PEBGGV?$regex_traits@G@tr1@std@@@tr1@std@@AEAA_NXZ; std::tr1::_Parser<ushort const *,ushort,std::tr1::regex_traits<ushort>>::_Alternative(void)
0x18001998f  test    al, al
0x180019991  jnz     short loc_1800199B0
0x180019993  cmp     dword ptr [rbx], 7Ch ; '|'
0x180019996  jnz     short loc_1800199FF
0x180019998  mov     edx, 8
0x18001999d  mov     rcx, rdi
0x1800199a0  call    ?_New_node@?$_Builder@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@AEAAPEAV_Node_base@23@W4_Node_type@23@@Z; std::tr1::_Builder<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_New_node(std::tr1::_Node_type)
0x1800199a5  mov     rdx, rax
0x1800199a8  mov     rcx, rdi
0x1800199ab  call    ?_End_group@?$_Builder@PEBGGV?$regex_traits@G@tr1@std@@@tr1@std@@QEAAXPEAV_Node_base@23@@Z; std::tr1::_Builder<ushort const *,ushort,std::tr1::regex_traits<ushort>>::_End_group(std::tr1::_Node_base *)
0x1800199b0  mov     rdx, rbp
0x1800199b3  mov     rcx, rdi
0x1800199b6  call    ?_Begin_if@?$_Builder@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@QEAAPEAV_Node_base@23@PEAV423@@Z; std::tr1::_Builder<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_Begin_if(std::tr1::_Node_base *)
0x1800199bb  mov     r14, rax
0x1800199be  jmp     short loc_1800199FA
0x1800199c0  mov     rcx, rsi
0x1800199c3  call    ?_Next@?$_Parser@PEBGGV?$regex_traits@G@tr1@std@@@tr1@std@@AEAAXXZ; std::tr1::_Parser<ushort const *,ushort,std::tr1::regex_traits<ushort>>::_Next(void)
0x1800199c8  mov     rcx, rsi
0x1800199cb  call    ?_Alternative@?$_Parser@PEBGGV?$regex_traits@G@tr1@std@@@tr1@std@@AEAA_NXZ; std::tr1::_Parser<ushort const *,ushort,std::tr1::regex_traits<ushort>>::_Alternative(void)
0x1800199d0  test    al, al
0x1800199d2  jnz     short loc_1800199EC
0x1800199d4  mov     edx, 8
0x1800199d9  mov     rcx, rdi
0x1800199dc  call    ?_New_node@?$_Builder@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@AEAAPEAV_Node_base@23@W4_Node_type@23@@Z; std::tr1::_Builder<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_New_node(std::tr1::_Node_type)
0x1800199e1  mov     rdx, rax
0x1800199e4  mov     rcx, rdi
0x1800199e7  call    ?_End_group@?$_Builder@PEBGGV?$regex_traits@G@tr1@std@@@tr1@std@@QEAAXPEAV_Node_base@23@@Z; std::tr1::_Builder<ushort const *,ushort,std::tr1::regex_traits<ushort>>::_End_group(std::tr1::_Node_base *)
0x1800199ec  mov     r8, r14
0x1800199ef  mov     rdx, rbp
0x1800199f2  mov     rcx, rdi
0x1800199f5  call    ?_Else_if@?$_Builder@PEBGGV?$regex_traits@G@tr1@std@@@tr1@std@@QEAAXPEAV_Node_base@23@0@Z; std::tr1::_Builder<ushort const *,ushort,std::tr1::regex_traits<ushort>>::_Else_if(std::tr1::_Node_base *,std::tr1::_Node_base *)
0x1800199fa  cmp     dword ptr [rbx], 7Ch ; '|'
0x1800199fd  jz      short loc_1800199C0
0x1800199ff  add     rsp, 20h
0x180019a03  pop     r14
0x180019a05  pop     rdi
0x180019a06  pop     rsi
0x180019a07  pop     rbp
0x180019a08  pop     rbx
0x180019a09  retn
```
