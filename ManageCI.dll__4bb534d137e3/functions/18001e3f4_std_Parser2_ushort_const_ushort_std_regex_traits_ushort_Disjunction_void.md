# std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Disjunction(void)

- ea: `0x18001e3f4`
- end: `0x18001e491`
- name: `?_Disjunction@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ`
- size: `157`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x18001e2dc`
- `0x18001e498`
- `0x18001e4e4`
- `0x18001eaf8`

## callees

- `0x18001d46c`
- `0x18001d924`
- `0x18001e3f4`
- `0x18001f0b0`
- `0x18001f14c`
- `0x18001ffd8`
- `0x180020028`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
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
0x18001e3f4  push    rbx
0x18001e3f6  push    rbp
0x18001e3f7  push    rsi
0x18001e3f8  push    rdi
0x18001e3f9  push    r14
0x18001e3fb  sub     rsp, 20h
0x18001e3ff  lea     rdi, [rcx+38h]
0x18001e403  mov     rsi, rcx
0x18001e406  mov     rbp, [rdi+8]
0x18001e40a  lea     rbx, [rcx+70h]
0x18001e40e  call    ?_Alternative@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAA_NXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Alternative(void)
0x18001e413  test    al, al
0x18001e415  jnz     short loc_18001E434
0x18001e417  cmp     dword ptr [rbx], 7Ch ; '|'
0x18001e41a  jnz     short loc_18001E486
0x18001e41c  mov     edx, 8
0x18001e421  mov     rcx, rdi
0x18001e424  call    ?_New_node@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@AEAAPEAV_Node_base@2@W4_Node_type@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_New_node(std::_Node_type)
0x18001e429  mov     rdx, rax
0x18001e42c  mov     rcx, rdi
0x18001e42f  call    ?_End_group@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEAV_Node_base@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_End_group(std::_Node_base *)
0x18001e434  cmp     dword ptr [rbx], 7Ch ; '|'
0x18001e437  jnz     short loc_18001E486
0x18001e439  mov     rdx, rbp
0x18001e43c  mov     rcx, rdi
0x18001e43f  call    ?_Begin_if@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAPEAV_Node_base@2@PEAV32@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_Begin_if(std::_Node_base *)
0x18001e444  mov     r14, rax
0x18001e447  mov     rcx, rsi
0x18001e44a  call    ?_Next@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Next(void)
0x18001e44f  mov     rcx, rsi
0x18001e452  call    ?_Alternative@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAA_NXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Alternative(void)
0x18001e457  test    al, al
0x18001e459  jnz     short loc_18001E473
0x18001e45b  mov     edx, 8
0x18001e460  mov     rcx, rdi
0x18001e463  call    ?_New_node@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@AEAAPEAV_Node_base@2@W4_Node_type@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_New_node(std::_Node_type)
0x18001e468  mov     rdx, rax
0x18001e46b  mov     rcx, rdi
0x18001e46e  call    ?_End_group@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEAV_Node_base@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_End_group(std::_Node_base *)
0x18001e473  mov     r8, r14
0x18001e476  mov     rdx, rbp
0x18001e479  mov     rcx, rdi
0x18001e47c  call    ?_Else_if@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEAV_Node_base@2@0@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_Else_if(std::_Node_base *,std::_Node_base *)
0x18001e481  cmp     dword ptr [rbx], 7Ch ; '|'
0x18001e484  jz      short loc_18001E447
0x18001e486  add     rsp, 20h
0x18001e48a  pop     r14
0x18001e48c  pop     rdi
0x18001e48d  pop     rsi
0x18001e48e  pop     rbp
0x18001e48f  pop     rbx
0x18001e490  retn
```
