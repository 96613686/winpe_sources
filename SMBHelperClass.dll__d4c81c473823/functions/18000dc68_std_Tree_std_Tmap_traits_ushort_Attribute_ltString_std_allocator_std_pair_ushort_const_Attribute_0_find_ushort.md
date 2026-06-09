# std::_Tree<std::_Tmap_traits<ushort *,Attribute,ltString,std::allocator<std::pair<ushort * const,Attribute>>,0>>::find(ushort * const &)

- ea: `0x18000dc68`
- end: `0x18000dcfd`
- name: `?find@?$_Tree@V?$_Tmap_traits@PEAGUAttribute@@UltString@@V?$allocator@U?$pair@QEAGUAttribute@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAGUAttribute@@@std@@@std@@@std@@@2@AEBQEAG@Z`
- size: `149`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d750`
- `0x18000dd04`
- `0x18000e25c`

## callees

- `0x18000dc68`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<unsigned short *,Attribute,ltString,std::allocator<std::pair<unsigned short * const,Attribute>>,0>>::find(
        __int64 *a1,
        _QWORD *a2,
        unsigned __int16 **a3)
{
  __int64 *v3; // r10
  __int64 *v6; // rax
  __int64 *v7; // rcx
  char *v8; // rdx
  signed __int64 v9; // r9
  int v10; // r11d
  int v11; // r8d
  unsigned __int16 *v12; // rax
  int v13; // r8d
  int v14; // edx
  _QWORD *result; // rax

  v3 = (__int64 *)*a1;
  v6 = *(__int64 **)(*a1 + 8);
  if ( *((_BYTE *)v6 + 25) )
    goto LABEL_15;
  v7 = (__int64 *)*a1;
  do
  {
    v8 = (char *)v6[4];
    v9 = (char *)*a3 - v8;
    do
    {
      v10 = *(unsigned __int16 *)&v8[v9];
      v11 = *(unsigned __int16 *)v8 - v10;
      if ( v11 )
        break;
      v8 += 2;
    }
    while ( v10 );
    if ( v11 >= 0 )
    {
      v7 = v6;
      v6 = (__int64 *)*v6;
    }
    else
    {
      v6 = (__int64 *)v6[2];
    }
  }
  while ( !*((_BYTE *)v6 + 25) );
  if ( v7 == v3 )
    goto LABEL_15;
  v12 = *a3;
  do
  {
    v13 = *(unsigned __int16 *)((char *)v12 + v7[4] - (_QWORD)*a3);
    v14 = *v12 - v13;
    if ( v14 )
      break;
    ++v12;
  }
  while ( v13 );
  if ( v14 < 0 )
LABEL_15:
    v7 = v3;
  result = a2;
  *a2 = v7;
  return result;
}

```

## disassembly

```asm
0x18000dc68  mov     [rsp+arg_0], rbx
0x18000dc6d  mov     [rsp+arg_8], rdi
0x18000dc72  mov     r10, [rcx]
0x18000dc75  mov     rdi, r8
0x18000dc78  mov     rbx, rdx
0x18000dc7b  mov     rax, [r10+8]
0x18000dc7f  cmp     byte ptr [rax+19h], 0
0x18000dc83  jnz     short loc_18000DCE9
0x18000dc85  mov     rcx, r10
0x18000dc88  mov     rdx, [rax+20h]
0x18000dc8c  mov     r9, [rdi]
0x18000dc8f  sub     r9, rdx
0x18000dc92  movzx   r8d, word ptr [rdx]
0x18000dc96  movzx   r11d, word ptr [rdx+r9]
0x18000dc9b  sub     r8d, r11d
0x18000dc9e  jnz     short loc_18000DCA9
0x18000dca0  add     rdx, 2
0x18000dca4  test    r11d, r11d
0x18000dca7  jnz     short loc_18000DC92
0x18000dca9  test    r8d, r8d
0x18000dcac  jns     short loc_18000DCB4
0x18000dcae  mov     rax, [rax+10h]
0x18000dcb2  jmp     short loc_18000DCBA
0x18000dcb4  mov     rcx, rax
0x18000dcb7  mov     rax, [rax]
0x18000dcba  cmp     byte ptr [rax+19h], 0
0x18000dcbe  jz      short loc_18000DC88
0x18000dcc0  cmp     rcx, r10
0x18000dcc3  jz      short loc_18000DCE9
0x18000dcc5  mov     rax, [rdi]
0x18000dcc8  mov     r9, [rcx+20h]
0x18000dccc  sub     r9, rax
0x18000dccf  movzx   edx, word ptr [rax]
0x18000dcd2  movzx   r8d, word ptr [rax+r9]
0x18000dcd7  sub     edx, r8d
0x18000dcda  jnz     short loc_18000DCE5
0x18000dcdc  add     rax, 2
0x18000dce0  test    r8d, r8d
0x18000dce3  jnz     short loc_18000DCCF
0x18000dce5  test    edx, edx
0x18000dce7  jns     short loc_18000DCEC
0x18000dce9  mov     rcx, r10
0x18000dcec  mov     rdi, [rsp+arg_8]
0x18000dcf1  mov     rax, rbx
0x18000dcf4  mov     [rbx], rcx
0x18000dcf7  mov     rbx, [rsp+arg_0]
0x18000dcfc  retn
```
