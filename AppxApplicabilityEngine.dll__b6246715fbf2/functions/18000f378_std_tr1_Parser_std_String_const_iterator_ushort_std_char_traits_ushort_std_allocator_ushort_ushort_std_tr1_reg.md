# std::tr1::_Parser<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_Disjunction(void)

- ea: `0x18000f378`
- end: `0x18000f412`
- name: `?_Disjunction@?$_Parser@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@AEAAXXZ`
- size: `154`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x18000f2b8`
- `0x180019a5c`
- `0x180019dd0`
- `0x18001aec0`

## callees

- `0x18000b8d8`
- `0x18000c654`
- `0x18000f378`
- `0x18000f418`
- `0x180018980`
- `0x180018f08`
- `0x18001a144`

## pseudocode

```c
__int64 __fastcall std::tr1::_Parser<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_Disjunction(
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
  result = ((__int64 (*)(void))std::tr1::_Parser<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_Alternative)();
  if ( !(_BYTE)result )
  {
    if ( *v4 != 124 )
      return result;
    v6 = std::tr1::_Builder<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_New_node(
           v1,
           8);
    std::tr1::_Builder<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_End_group(
      v1,
      v6);
  }
  result = std::tr1::_Builder<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_Begin_if(
             v1,
             v3);
  v7 = result;
  while ( *v4 == 124 )
  {
    std::tr1::_Parser<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_Next(a1);
    if ( !(unsigned __int8)std::tr1::_Parser<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_Alternative(a1) )
    {
      v8 = std::tr1::_Builder<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_New_node(
             v1,
             8);
      std::tr1::_Builder<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short,std::tr1::regex_traits<unsigned short>>::_End_group(
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
0x18000f378  push    rbx
0x18000f37a  push    rbp
0x18000f37b  push    rsi
0x18000f37c  push    rdi
0x18000f37d  push    r14
0x18000f37f  sub     rsp, 20h
0x18000f383  lea     rdi, [rcx+28h]
0x18000f387  mov     rsi, rcx
0x18000f38a  mov     rbp, [rdi+8]
0x18000f38e  lea     rbx, [rcx+60h]
0x18000f392  call    ?_Alternative@?$_Parser@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@AEAA_NXZ; std::tr1::_Parser<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_Alternative(void)
0x18000f397  test    al, al
0x18000f399  jnz     short loc_18000F3B8
0x18000f39b  cmp     dword ptr [rbx], 7Ch ; '|'
0x18000f39e  jnz     short loc_18000F407
0x18000f3a0  mov     edx, 8
0x18000f3a5  mov     rcx, rdi
0x18000f3a8  call    ?_New_node@?$_Builder@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@AEAAPEAV_Node_base@23@W4_Node_type@23@@Z; std::tr1::_Builder<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_New_node(std::tr1::_Node_type)
0x18000f3ad  mov     rdx, rax
0x18000f3b0  mov     rcx, rdi
0x18000f3b3  call    ?_End_group@?$_Builder@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@QEAAXPEAV_Node_base@23@@Z; std::tr1::_Builder<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_End_group(std::tr1::_Node_base *)
0x18000f3b8  mov     rdx, rbp
0x18000f3bb  mov     rcx, rdi
0x18000f3be  call    ?_Begin_if@?$_Builder@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@QEAAPEAV_Node_base@23@PEAV423@@Z; std::tr1::_Builder<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_Begin_if(std::tr1::_Node_base *)
0x18000f3c3  mov     r14, rax
0x18000f3c6  jmp     short loc_18000F402
0x18000f3c8  mov     rcx, rsi
0x18000f3cb  call    ?_Next@?$_Parser@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@AEAAXXZ; std::tr1::_Parser<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_Next(void)
0x18000f3d0  mov     rcx, rsi
0x18000f3d3  call    ?_Alternative@?$_Parser@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@AEAA_NXZ; std::tr1::_Parser<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_Alternative(void)
0x18000f3d8  test    al, al
0x18000f3da  jnz     short loc_18000F3F4
0x18000f3dc  mov     edx, 8
0x18000f3e1  mov     rcx, rdi
0x18000f3e4  call    ?_New_node@?$_Builder@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@AEAAPEAV_Node_base@23@W4_Node_type@23@@Z; std::tr1::_Builder<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_New_node(std::tr1::_Node_type)
0x18000f3e9  mov     rdx, rax
0x18000f3ec  mov     rcx, rdi
0x18000f3ef  call    ?_End_group@?$_Builder@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GV?$regex_traits@G@tr1@2@@tr1@std@@QEAAXPEAV_Node_base@23@@Z; std::tr1::_Builder<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort,std::tr1::regex_traits<ushort>>::_End_group(std::tr1::_Node_base *)
0x18000f3f4  mov     r8, r14
0x18000f3f7  mov     rdx, rbp
0x18000f3fa  mov     rcx, rdi
0x18000f3fd  call    ?_Else_if@?$_Builder@PEBGGV?$regex_traits@G@tr1@std@@@tr1@std@@QEAAXPEAV_Node_base@23@0@Z; std::tr1::_Builder<ushort const *,ushort,std::tr1::regex_traits<ushort>>::_Else_if(std::tr1::_Node_base *,std::tr1::_Node_base *)
0x18000f402  cmp     dword ptr [rbx], 7Ch ; '|'
0x18000f405  jz      short loc_18000F3C8
0x18000f407  add     rsp, 20h
0x18000f40b  pop     r14
0x18000f40d  pop     rdi
0x18000f40e  pop     rsi
0x18000f40f  pop     rbp
0x18000f410  pop     rbx
0x18000f411  retn
```
