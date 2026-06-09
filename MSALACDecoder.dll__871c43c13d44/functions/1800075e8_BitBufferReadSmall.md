# BitBufferReadSmall

- ea: `0x1800075e8`
- end: `0x18000766c`
- name: `BitBufferReadSmall`
- size: `132`
- prototype: `char __fastcall(unsigned __int64 *, unsigned __int8)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800076d0`
- `0x180007798`

## callees

- `0x1800075e8`

## pseudocode

```c
char __fastcall BitBufferReadSmall(unsigned __int64 *a1, unsigned __int8 a2)
{
  unsigned __int8 *v2; // r11
  int v3; // ebp
  unsigned int v5; // ebx
  unsigned __int64 v6; // rdi
  int *v7; // rdx
  __int16 v8; // r8
  unsigned __int8 *v9; // r11

  v2 = (unsigned __int8 *)*a1;
  v3 = *((_DWORD *)a1 + 4);
  v5 = a2 + v3;
  v6 = *a1 + ((unsigned __int64)v5 >> 3);
  if ( a1[1] < v6 )
    return 0;
  if ( a1[1] != v6 )
  {
    v7 = (int *)(a1 + 2);
    goto LABEL_6;
  }
  if ( (v5 & 7) != 0 )
    return 0;
  v7 = (int *)(a1 + 2);
LABEL_6:
  v8 = *v2 << 8;
  v9 = v2 + 1;
  if ( (unsigned __int64)v9 >= a1[1] )
    v7 = (int *)(a1 + 2);
  else
    v8 |= *v9;
  *((_DWORD *)a1 + 4) = v5;
  *v7 = v5 & 7;
  *a1 = v6;
  return (unsigned __int16)(v8 << v3) >> (16 - a2);
}

```

## disassembly

```asm
0x1800075e8  push    rbx
0x1800075ea  push    rbp
0x1800075eb  push    rsi
0x1800075ec  push    rdi
0x1800075ed  mov     r11, [rcx]
0x1800075f0  lea     r10, [rcx+10h]
0x1800075f4  mov     ebp, [r10]
0x1800075f7  mov     r9, rcx
0x1800075fa  movzx   esi, dl
0x1800075fd  lea     ebx, [rsi+rbp]
0x180007600  mov     edi, ebx
0x180007602  shr     rdi, 3
0x180007606  add     rdi, r11
0x180007609  cmp     [rcx+8], rdi
0x18000760d  jb      short loc_180007665
0x18000760f  mov     ecx, ebx
0x180007611  and     ecx, 7
0x180007614  cmp     [r9+8], rdi
0x180007618  jnz     short loc_180007624
0x18000761a  test    ecx, ecx
0x18000761c  jnz     short loc_180007665
0x18000761e  lea     rdx, [r9+10h]
0x180007622  jmp     short loc_180007627
0x180007624  mov     rdx, r10
0x180007627  movzx   r8d, byte ptr [r11]
0x18000762b  shl     r8w, 8
0x180007630  inc     r11
0x180007633  cmp     r11, [r9+8]
0x180007637  jnb     short loc_180007643
0x180007639  movzx   eax, byte ptr [r11]
0x18000763d  or      r8w, ax
0x180007641  jmp     short loc_180007646
0x180007643  mov     rdx, r10
0x180007646  mov     [r10], ebx
0x180007649  mov     [rdx], ecx
0x18000764b  mov     ecx, ebp
0x18000764d  shl     r8w, cl
0x180007651  mov     ecx, 10h
0x180007656  sub     cl, sil
0x180007659  mov     [r9], rdi
0x18000765c  shr     r8w, cl
0x180007660  mov     al, r8b
0x180007663  jmp     short loc_180007667
0x180007665  xor     al, al
0x180007667  pop     rdi
0x180007668  pop     rsi
0x180007669  pop     rbp
0x18000766a  pop     rbx
0x18000766b  retn
```
