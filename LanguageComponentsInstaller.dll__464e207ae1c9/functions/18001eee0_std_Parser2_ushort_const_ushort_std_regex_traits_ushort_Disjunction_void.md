# std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Disjunction(void)

- ea: `0x18001eee0`
- end: `0x18001effc`
- name: `?_Disjunction@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ`
- size: `284`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x180011038`
- `0x18001f004`
- `0x18001f6c4`
- `0x180021988`

## callees

- `0x180003544`
- `0x18001dc38`
- `0x18001e1c0`
- `0x18001eee0`
- `0x18001fcfc`
- `0x180020fc0`
- `0x180021010`

## pseudocode

```c
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
0x18001eee0  push    rbx
0x18001eee2  push    rbp
0x18001eee3  push    rsi
0x18001eee4  push    rdi
0x18001eee5  push    r13
0x18001eee7  push    r14
0x18001eee9  push    r15
0x18001eeeb  sub     rsp, 20h
0x18001eeef  mov     r13, [rcx+40h]
0x18001eef3  lea     rdi, [rcx+70h]
0x18001eef7  mov     rbx, rcx
0x18001eefa  call    ?_Alternative@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAA_NXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Alternative(void)
0x18001eeff  test    al, al
0x18001ef01  jnz     short loc_18001EF2A
0x18001ef03  cmp     dword ptr [rdi], 7Ch ; '|'
0x18001ef06  jnz     loc_18001EFED
0x18001ef0c  lea     rbp, [rbx+38h]
0x18001ef10  mov     edx, 8
0x18001ef15  mov     rcx, rbp
0x18001ef18  call    ?_New_node@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@AEAAPEAV_Node_base@2@W4_Node_type@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_New_node(std::_Node_type)
0x18001ef1d  mov     rdx, rax
0x18001ef20  mov     rcx, rbp
0x18001ef23  call    ?_End_group@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEAV_Node_base@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_End_group(std::_Node_base *)
0x18001ef28  jmp     short loc_18001EF2E
0x18001ef2a  lea     rbp, [rbx+38h]
0x18001ef2e  cmp     dword ptr [rdi], 7Ch ; '|'
0x18001ef31  jnz     loc_18001EFED
0x18001ef37  mov     rdx, r13
0x18001ef3a  mov     rcx, rbp
0x18001ef3d  call    ?_Begin_if@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAPEAV_Node_base@2@PEAV32@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_Begin_if(std::_Node_base *)
0x18001ef42  mov     r14, rax
0x18001ef45  mov     rcx, rbx
0x18001ef48  call    ?_Next@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Next(void)
0x18001ef4d  mov     rcx, rbx
0x18001ef50  call    ?_Alternative@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAA_NXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Alternative(void)
0x18001ef55  test    al, al
0x18001ef57  jnz     short loc_18001EF73
0x18001ef59  lea     rcx, [rbx+38h]
0x18001ef5d  mov     edx, 8
0x18001ef62  call    ?_New_node@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@AEAAPEAV_Node_base@2@W4_Node_type@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_New_node(std::_Node_type)
0x18001ef67  lea     rcx, [rbx+38h]
0x18001ef6b  mov     rdx, rax
0x18001ef6e  call    ?_End_group@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEAV_Node_base@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_End_group(std::_Node_base *)
0x18001ef73  mov     rsi, [r13+10h]
0x18001ef77  mov     r15, [r14+10h]
0x18001ef7b  mov     qword ptr [r14+10h], 0
0x18001ef83  mov     rax, [rbp+8]
0x18001ef87  mov     [rbp+8], r14
0x18001ef8b  mov     qword ptr [r14+10h], 0
0x18001ef93  mov     [rax+10h], r14
0x18001ef97  jmp     short loc_18001EF9D
0x18001ef99  mov     rsi, [rsi+28h]
0x18001ef9d  cmp     qword ptr [rsi+28h], 0
0x18001efa2  jnz     short loc_18001EF99
0x18001efa4  mov     ecx, 30h ; '0'; Size
0x18001efa9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001efae  lea     rcx, ??_7_Node_if@std@@6B@; const std::_Node_if::`vftable'
0x18001efb5  mov     qword ptr [rax+8], 10h
0x18001efbd  mov     qword ptr [rax+18h], 0
0x18001efc5  mov     [rax], rcx
0x18001efc8  mov     [rax+20h], r14
0x18001efcc  mov     qword ptr [rax+28h], 0
0x18001efd4  mov     [rsi+28h], rax
0x18001efd8  mov     [rax+10h], r15
0x18001efdc  mov     rax, [rsi+28h]
0x18001efe0  mov     [r15+18h], rax
0x18001efe4  cmp     dword ptr [rdi], 7Ch ; '|'
0x18001efe7  jz      loc_18001EF45
0x18001efed  add     rsp, 20h
0x18001eff1  pop     r15
0x18001eff3  pop     r14
0x18001eff5  pop     r13
0x18001eff7  pop     rdi
0x18001eff8  pop     rsi
0x18001eff9  pop     rbp
0x18001effa  pop     rbx
0x18001effb  retn
```
