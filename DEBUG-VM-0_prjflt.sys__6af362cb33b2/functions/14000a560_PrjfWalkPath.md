# PrjfWalkPath

- ea: `0x14000a560`
- end: `0x14000a694`
- name: `PrjfWalkPath`
- size: `308`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140044cec`
- `0x1400453bc`

## callees

- `0x14000a560`

## pseudocode

```c
char __fastcall PrjfWalkPath(unsigned __int16 *a1, __int64 a2, __int64 a3)
{
  unsigned __int16 v4; // cx
  char v5; // r9
  _WORD *v6; // rcx
  bool v7; // al
  unsigned __int16 v8; // dx
  __int64 v9; // r11
  unsigned __int16 v10; // cx
  unsigned __int16 v11; // r9
  unsigned __int16 i; // dx
  unsigned __int16 v13; // cx
  unsigned __int16 v14; // cx
  __int64 v15; // rbx
  __int16 v16; // ax
  unsigned __int16 v17; // ax
  unsigned __int16 v18; // r8

  v4 = *a1;
  if ( !v4 )
  {
LABEL_2:
    v5 = 0;
    *(_DWORD *)a3 = 0;
    *(_QWORD *)(a3 + 8) = 0;
    return v5;
  }
  if ( *(_WORD *)a3 )
  {
    v9 = *((_QWORD *)a1 + 1);
    v10 = v4 >> 1;
    v11 = v10;
    for ( i = (*(_QWORD *)(a3 + 8) - v9) >> 1; i < v10; ++i )
    {
      if ( *(_WORD *)(v9 + 2LL * i) == 92 )
        break;
    }
    if ( i == v10 )
      goto LABEL_2;
    while ( 1 )
    {
      v13 = i + 1;
      if ( (unsigned __int16)(i + 1) >= v11 || *(_WORD *)(v9 + 2LL * v13) != 92 )
        break;
      ++i;
    }
    if ( v13 == v11 )
      goto LABEL_2;
    v8 = i + 1;
  }
  else
  {
    v6 = (_WORD *)*((_QWORD *)a1 + 1);
    v7 = *v6 == 92;
    v8 = v7;
    *(_QWORD *)(a3 + 8) = &v6[v7];
  }
  v5 = 0;
  v14 = *a1 >> 1;
  v15 = v8;
  if ( v8 < v14 )
  {
    while ( *(_WORD *)(*((_QWORD *)a1 + 1) + 2LL * v8) != 92 )
    {
      if ( ++v8 >= v14 )
        goto LABEL_20;
    }
    v5 = 1;
  }
LABEL_20:
  *(_QWORD *)(a3 + 8) = *((_QWORD *)a1 + 1) + 2 * v15;
  v16 = 2 * (v8 - v15);
  *(_WORD *)(a3 + 2) = v16;
  *(_WORD *)a3 = v16;
  v17 = v8 + 1;
  v18 = *a1 >> 1;
  if ( (unsigned __int16)(v8 + 1) >= v18 )
  {
LABEL_23:
    if ( v17 == v18 )
      return 0;
  }
  else
  {
    while ( *(_WORD *)(*((_QWORD *)a1 + 1) + 2LL * v17) == 92 )
    {
      v17 = ++v8 + 1;
      if ( (unsigned __int16)(v8 + 1) >= v18 )
        goto LABEL_23;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x14000a560  mov     [rsp+arg_0], rbx
0x14000a565  mov     [rsp+arg_8], rdi
0x14000a56a  mov     r10, rcx
0x14000a56d  xor     edi, edi
0x14000a56f  movzx   ecx, word ptr [rcx]
0x14000a572  test    cx, cx
0x14000a575  jnz     short loc_14000A586
0x14000a577  mov     r9b, dil
0x14000a57a  mov     [r8], edi
0x14000a57d  mov     [r8+8], rdi
0x14000a581  jmp     loc_14000A685
0x14000a586  cmp     [r8], di
0x14000a58a  jnz     short loc_14000A5A6
0x14000a58c  mov     rcx, [r10+8]
0x14000a590  mov     eax, edi
0x14000a592  cmp     word ptr [rcx], 5Ch ; '\'
0x14000a596  setz    al
0x14000a599  movzx   edx, ax
0x14000a59c  lea     rax, [rcx+rdx*2]
0x14000a5a0  mov     [r8+8], rax
0x14000a5a4  jmp     short loc_14000A602
0x14000a5a6  mov     r11, [r10+8]
0x14000a5aa  mov     rax, [r8+8]
0x14000a5ae  sub     rax, r11
0x14000a5b1  shr     cx, 1
0x14000a5b4  sar     rax, 1
0x14000a5b7  movzx   r9d, cx
0x14000a5bb  movzx   edx, ax
0x14000a5be  cmp     ax, cx
0x14000a5c1  jnb     short loc_14000A5D6
0x14000a5c3  movzx   eax, dx
0x14000a5c6  cmp     word ptr [r11+rax*2], 5Ch ; '\'
0x14000a5cc  jz      short loc_14000A5D6
0x14000a5ce  inc     dx
0x14000a5d1  cmp     dx, cx
0x14000a5d4  jb      short loc_14000A5C3
0x14000a5d6  cmp     dx, r9w
0x14000a5da  jnz     short loc_14000A5EC
0x14000a5dc  jmp     short loc_14000A577
0x14000a5de  movzx   eax, cx
0x14000a5e1  cmp     word ptr [r11+rax*2], 5Ch ; '\'
0x14000a5e7  jnz     short loc_14000A5F5
0x14000a5e9  inc     dx
0x14000a5ec  lea     ecx, [rdx+1]
0x14000a5ef  cmp     cx, r9w
0x14000a5f3  jb      short loc_14000A5DE
0x14000a5f5  cmp     cx, r9w
0x14000a5f9  jz      loc_14000A577
0x14000a5ff  inc     dx
0x14000a602  movzx   ecx, word ptr [r10]
0x14000a606  mov     r9b, dil
0x14000a609  shr     cx, 1
0x14000a60c  movzx   ebx, dx
0x14000a60f  cmp     dx, cx
0x14000a612  jnb     short loc_14000A630
0x14000a614  mov     r11, [r10+8]
0x14000a618  movzx   eax, dx
0x14000a61b  cmp     word ptr [r11+rax*2], 5Ch ; '\'
0x14000a621  jz      short loc_14000A62D
0x14000a623  inc     dx
0x14000a626  cmp     dx, cx
0x14000a629  jb      short loc_14000A618
0x14000a62b  jmp     short loc_14000A630
0x14000a62d  mov     r9b, 1
0x14000a630  mov     rax, [r10+8]
0x14000a634  lea     rcx, [rax+rbx*2]
0x14000a638  movzx   eax, dx
0x14000a63b  sub     ax, bx
0x14000a63e  mov     [r8+8], rcx
0x14000a642  add     ax, ax
0x14000a645  mov     [r8+2], ax
0x14000a64a  mov     [r8], ax
0x14000a64e  lea     eax, [rdx+1]
0x14000a651  movzx   r8d, word ptr [r10]
0x14000a655  shr     r8w, 1
0x14000a659  cmp     ax, r8w
0x14000a65d  jnb     short loc_14000A679
0x14000a65f  mov     rcx, [r10+8]
0x14000a663  movzx   eax, ax
0x14000a666  cmp     word ptr [rcx+rax*2], 5Ch ; '\'
0x14000a66b  jnz     short loc_14000A685
0x14000a66d  inc     dx
0x14000a670  lea     eax, [rdx+1]
0x14000a673  cmp     ax, r8w
0x14000a677  jb      short loc_14000A663
0x14000a679  cmp     ax, r8w
0x14000a67d  movzx   r9d, r9b
0x14000a681  cmovz   r9d, edi
0x14000a685  mov     rbx, [rsp+arg_0]
0x14000a68a  mov     al, r9b
0x14000a68d  mov     rdi, [rsp+arg_8]
0x14000a692  retn
```
