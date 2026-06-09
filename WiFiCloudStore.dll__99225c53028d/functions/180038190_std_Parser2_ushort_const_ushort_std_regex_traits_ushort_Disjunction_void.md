# std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Disjunction(void)

- ea: `0x180038190`
- end: `0x18003822d`
- name: `?_Disjunction@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ`
- size: `157`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x180037f34`
- `0x180038234`
- `0x180038388`
- `0x18003899c`

## callees

- `0x1800370e8`
- `0x1800375a0`
- `0x180038190`
- `0x180038f54`
- `0x180038ff0`
- `0x180039a90`
- `0x180039ae0`

## pseudocode

```c
__int64 __fastcall std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Disjunction(
        __int64 a1)
{
  __int64 v1; // rdi
  __int64 v3; // rbp
  _DWORD *v4; // rbx
  __int64 result; // rax
  __int64 v6; // rax
  __int64 v7; // r14
  __int64 v8; // rax

  v1 = a1 + 56;
  v3 = *(_QWORD *)(a1 + 64);
  v4 = (_DWORD *)(a1 + 112);
  result = ((__int64 (*)(void))std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Alternative)();
  if ( !(_BYTE)result )
  {
    if ( *v4 != 124 )
      return result;
    v6 = std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_New_node(v1, 8);
    result = std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_End_group(v1, v6);
  }
  if ( *v4 == 124 )
  {
    v7 = std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Begin_if(v1, v3);
    do
    {
      std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Next(a1);
      if ( !(unsigned __int8)std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Alternative(a1) )
      {
        v8 = std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_New_node(v1, 8);
        std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_End_group(v1, v8);
      }
      result = std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Else_if(
                 v1,
                 v3,
                 v7);
    }
    while ( *v4 == 124 );
  }
  return result;
}

```

## disassembly

```asm
0x180038190  push    rbx
0x180038192  push    rbp
0x180038193  push    rsi
0x180038194  push    rdi
0x180038195  push    r14
0x180038197  sub     rsp, 20h
0x18003819b  lea     rdi, [rcx+38h]
0x18003819f  mov     rsi, rcx
0x1800381a2  mov     rbp, [rdi+8]
0x1800381a6  lea     rbx, [rcx+70h]
0x1800381aa  call    ?_Alternative@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAA_NXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Alternative(void)
0x1800381af  test    al, al
0x1800381b1  jnz     short loc_1800381D0
0x1800381b3  cmp     dword ptr [rbx], 7Ch ; '|'
0x1800381b6  jnz     short loc_180038222
0x1800381b8  mov     edx, 8
0x1800381bd  mov     rcx, rdi
0x1800381c0  call    ?_New_node@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@AEAAPEAV_Node_base@2@W4_Node_type@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_New_node(std::_Node_type)
0x1800381c5  mov     rdx, rax
0x1800381c8  mov     rcx, rdi
0x1800381cb  call    ?_End_group@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEAV_Node_base@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_End_group(std::_Node_base *)
0x1800381d0  cmp     dword ptr [rbx], 7Ch ; '|'
0x1800381d3  jnz     short loc_180038222
0x1800381d5  mov     rdx, rbp
0x1800381d8  mov     rcx, rdi
0x1800381db  call    ?_Begin_if@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAPEAV_Node_base@2@PEAV32@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_Begin_if(std::_Node_base *)
0x1800381e0  mov     r14, rax
0x1800381e3  mov     rcx, rsi
0x1800381e6  call    ?_Next@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Next(void)
0x1800381eb  mov     rcx, rsi
0x1800381ee  call    ?_Alternative@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAA_NXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Alternative(void)
0x1800381f3  test    al, al
0x1800381f5  jnz     short loc_18003820F
0x1800381f7  mov     edx, 8
0x1800381fc  mov     rcx, rdi
0x1800381ff  call    ?_New_node@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@AEAAPEAV_Node_base@2@W4_Node_type@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_New_node(std::_Node_type)
0x180038204  mov     rdx, rax
0x180038207  mov     rcx, rdi
0x18003820a  call    ?_End_group@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEAV_Node_base@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_End_group(std::_Node_base *)
0x18003820f  mov     r8, r14
0x180038212  mov     rdx, rbp
0x180038215  mov     rcx, rdi
0x180038218  call    ?_Else_if@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEAV_Node_base@2@0@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_Else_if(std::_Node_base *,std::_Node_base *)
0x18003821d  cmp     dword ptr [rbx], 7Ch ; '|'
0x180038220  jz      short loc_1800381E3
0x180038222  add     rsp, 20h
0x180038226  pop     r14
0x180038228  pop     rdi
0x180038229  pop     rsi
0x18003822a  pop     rbp
0x18003822b  pop     rbx
0x18003822c  retn
```
