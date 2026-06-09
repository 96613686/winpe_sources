# std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Disjunction(void)

- ea: `0x18001e4dc`
- end: `0x18001e5f8`
- name: `?_Disjunction@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ`
- size: `284`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x18001ae64`
- `0x18001e600`
- `0x18001ea58`
- `0x18001f3e8`

## callees

- `0x1800032c4`
- `0x18001d798`
- `0x18001dbe8`
- `0x18001e4dc`
- `0x18001eaa4`
- `0x18001f08c`
- `0x18001f0dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Disjunction(
        __int64 a1)
{
  __int64 v1; // r13
  _DWORD *v2; // rdi
  __int64 result; // rax
  __int64 v5; // rbp
  __int64 v6; // rax
  __int64 v7; // r14
  __int64 v8; // rax
  __int64 v9; // rsi
  __int64 v10; // r15
  __int64 v11; // rax
  _QWORD *v12; // rax

  v1 = *(_QWORD *)(a1 + 64);
  v2 = (_DWORD *)(a1 + 112);
  result = ((__int64 (*)(void))std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Alternative)();
  if ( (_BYTE)result )
  {
    v5 = a1 + 56;
  }
  else
  {
    if ( *v2 != 124 )
      return result;
    v5 = a1 + 56;
    v6 = std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_New_node(a1 + 56, 8);
    result = std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_End_group(
               a1 + 56,
               v6);
  }
  if ( *v2 == 124 )
  {
    v7 = std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Begin_if(v5, v1);
    do
    {
      std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Next(a1);
      if ( !(unsigned __int8)std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Alternative(a1) )
      {
        v8 = std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_New_node(
               a1 + 56,
               8);
        std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_End_group(a1 + 56, v8);
      }
      v9 = *(_QWORD *)(v1 + 16);
      v10 = *(_QWORD *)(v7 + 16);
      *(_QWORD *)(v7 + 16) = 0;
      v11 = *(_QWORD *)(v5 + 8);
      *(_QWORD *)(v5 + 8) = v7;
      *(_QWORD *)(v7 + 16) = 0;
      *(_QWORD *)(v11 + 16) = v7;
      while ( *(_QWORD *)(v9 + 40) )
        v9 = *(_QWORD *)(v9 + 40);
      v12 = operator new(0x30u);
      v12[1] = 16;
      v12[3] = 0;
      *v12 = &std::_Node_if::`vftable';
      v12[4] = v7;
      v12[5] = 0;
      *(_QWORD *)(v9 + 40) = v12;
      v12[2] = v10;
      result = *(_QWORD *)(v9 + 40);
      *(_QWORD *)(v10 + 24) = result;
    }
    while ( *v2 == 124 );
  }
  return result;
}

```

## disassembly

```asm
0x18001e4dc  push    rbx
0x18001e4de  push    rbp
0x18001e4df  push    rsi
0x18001e4e0  push    rdi
0x18001e4e1  push    r13
0x18001e4e3  push    r14
0x18001e4e5  push    r15
0x18001e4e7  sub     rsp, 20h
0x18001e4eb  mov     r13, [rcx+40h]
0x18001e4ef  lea     rdi, [rcx+70h]
0x18001e4f3  mov     rbx, rcx
0x18001e4f6  call    ?_Alternative@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAA_NXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Alternative(void)
0x18001e4fb  test    al, al
0x18001e4fd  jnz     short loc_18001E526
0x18001e4ff  cmp     dword ptr [rdi], 7Ch ; '|'
0x18001e502  jnz     loc_18001E5E9
0x18001e508  lea     rbp, [rbx+38h]
0x18001e50c  mov     edx, 8
0x18001e511  mov     rcx, rbp
0x18001e514  call    ?_New_node@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@AEAAPEAV_Node_base@2@W4_Node_type@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_New_node(std::_Node_type)
0x18001e519  mov     rdx, rax
0x18001e51c  mov     rcx, rbp
0x18001e51f  call    ?_End_group@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEAV_Node_base@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_End_group(std::_Node_base *)
0x18001e524  jmp     short loc_18001E52A
0x18001e526  lea     rbp, [rbx+38h]
0x18001e52a  cmp     dword ptr [rdi], 7Ch ; '|'
0x18001e52d  jnz     loc_18001E5E9
0x18001e533  mov     rdx, r13
0x18001e536  mov     rcx, rbp
0x18001e539  call    ?_Begin_if@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAPEAV_Node_base@2@PEAV32@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_Begin_if(std::_Node_base *)
0x18001e53e  mov     r14, rax
0x18001e541  mov     rcx, rbx
0x18001e544  call    ?_Next@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Next(void)
0x18001e549  mov     rcx, rbx
0x18001e54c  call    ?_Alternative@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAA_NXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Alternative(void)
0x18001e551  test    al, al
0x18001e553  jnz     short loc_18001E56F
0x18001e555  lea     rcx, [rbx+38h]
0x18001e559  mov     edx, 8
0x18001e55e  call    ?_New_node@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@AEAAPEAV_Node_base@2@W4_Node_type@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_New_node(std::_Node_type)
0x18001e563  lea     rcx, [rbx+38h]
0x18001e567  mov     rdx, rax
0x18001e56a  call    ?_End_group@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEAV_Node_base@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_End_group(std::_Node_base *)
0x18001e56f  mov     rsi, [r13+10h]
0x18001e573  mov     r15, [r14+10h]
0x18001e577  mov     qword ptr [r14+10h], 0
0x18001e57f  mov     rax, [rbp+8]
0x18001e583  mov     [rbp+8], r14
0x18001e587  mov     qword ptr [r14+10h], 0
0x18001e58f  mov     [rax+10h], r14
0x18001e593  jmp     short loc_18001E599
0x18001e595  mov     rsi, [rsi+28h]
0x18001e599  cmp     qword ptr [rsi+28h], 0
0x18001e59e  jnz     short loc_18001E595
0x18001e5a0  mov     ecx, 30h ; '0'; Size
0x18001e5a5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e5aa  lea     rcx, ??_7_Node_if@std@@6B@; const std::_Node_if::`vftable'
0x18001e5b1  mov     qword ptr [rax+8], 10h
0x18001e5b9  mov     qword ptr [rax+18h], 0
0x18001e5c1  mov     [rax], rcx
0x18001e5c4  mov     [rax+20h], r14
0x18001e5c8  mov     qword ptr [rax+28h], 0
0x18001e5d0  mov     [rsi+28h], rax
0x18001e5d4  mov     [rax+10h], r15
0x18001e5d8  mov     rax, [rsi+28h]
0x18001e5dc  mov     [r15+18h], rax
0x18001e5e0  cmp     dword ptr [rdi], 7Ch ; '|'
0x18001e5e3  jz      loc_18001E541
0x18001e5e9  add     rsp, 20h
0x18001e5ed  pop     r15
0x18001e5ef  pop     r14
0x18001e5f1  pop     r13
0x18001e5f3  pop     rdi
0x18001e5f4  pop     rsi
0x18001e5f5  pop     rbp
0x18001e5f6  pop     rbx
0x18001e5f7  retn
```
