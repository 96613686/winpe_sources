# BitBufferRead

- ea: `0x180007544`
- end: `0x1800075e0`
- name: `BitBufferRead`
- size: `156`
- prototype: `__int64 __fastcall(unsigned __int64 *, unsigned __int8)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007798`

## callees

- `0x180007544`

## pseudocode

```c
__int64 __fastcall BitBufferRead(unsigned __int64 *a1, unsigned __int8 a2)
{
  unsigned __int8 *v2; // r10
  int v3; // ebp
  unsigned __int64 v4; // r9
  unsigned __int8 v5; // r11
  unsigned int v6; // edi
  unsigned __int64 v7; // rsi
  int *v8; // r14
  int v9; // edx
  unsigned __int8 *v10; // r10

  v2 = (unsigned __int8 *)*a1;
  v3 = *((_DWORD *)a1 + 4);
  v4 = a1[1];
  v5 = a2;
  v6 = a2 + v3;
  v7 = *a1 + ((unsigned __int64)v6 >> 3);
  if ( v4 < v7 )
    return 0;
  if ( v4 != v7 )
  {
    v8 = (int *)(a1 + 2);
    goto LABEL_6;
  }
  if ( (v6 & 7) != 0 )
    return 0;
  v8 = (int *)(a1 + 2);
  v5 = a2;
LABEL_6:
  if ( (unsigned __int64)(v2 + 1) >= v4 )
    v9 = *v2 << 16;
  else
    v9 = (*v2 << 16) | (v2[1] << 8);
  v10 = v2 + 2;
  if ( (unsigned __int64)v10 < v4 )
    v9 |= *v10;
  *((_DWORD *)a1 + 4) = v6;
  *v8 = v6 & 7;
  *a1 = v7;
  return ((v9 << v3) & 0xFFFFFFu) >> (24 - v5);
}

```

## disassembly

```asm
0x180007544  push    rbx
0x180007546  push    rbp
0x180007547  push    rsi
0x180007548  push    rdi
0x180007549  push    r14
0x18000754b  mov     r10, [rcx]
0x18000754e  lea     rbx, [rcx+10h]
0x180007552  mov     ebp, [rbx]
0x180007554  mov     r8, rcx
0x180007557  mov     r9, [rcx+8]
0x18000755b  movzx   r11d, dl
0x18000755f  lea     edi, [r11+rbp]
0x180007563  mov     esi, edi
0x180007565  shr     rsi, 3
0x180007569  add     rsi, r10
0x18000756c  cmp     r9, rsi
0x18000756f  jb      short loc_1800075D7
0x180007571  mov     ecx, edi
0x180007573  and     ecx, 7
0x180007576  cmp     r9, rsi
0x180007579  jnz     short loc_180007589
0x18000757b  test    ecx, ecx
0x18000757d  jnz     short loc_1800075D7
0x18000757f  lea     r14, [r8+10h]
0x180007583  movzx   r11d, dl
0x180007587  jmp     short loc_18000758C
0x180007589  mov     r14, rbx
0x18000758c  movzx   eax, byte ptr [r10]
0x180007590  lea     rdx, [r10+1]
0x180007594  shl     eax, 10h
0x180007597  cmp     rdx, r9
0x18000759a  jnb     short loc_1800075A6
0x18000759c  movzx   edx, byte ptr [rdx]
0x18000759f  shl     edx, 8
0x1800075a2  or      edx, eax
0x1800075a4  jmp     short loc_1800075A8
0x1800075a6  mov     edx, eax
0x1800075a8  add     r10, 2
0x1800075ac  cmp     r10, r9
0x1800075af  jnb     short loc_1800075B7
0x1800075b1  movzx   eax, byte ptr [r10]
0x1800075b5  or      edx, eax
0x1800075b7  mov     [rbx], edi
0x1800075b9  mov     [r14], ecx
0x1800075bc  mov     ecx, ebp
0x1800075be  shl     edx, cl
0x1800075c0  mov     ecx, 18h
0x1800075c5  sub     ecx, r11d
0x1800075c8  mov     [r8], rsi
0x1800075cb  and     edx, 0FFFFFFh
0x1800075d1  shr     edx, cl
0x1800075d3  mov     eax, edx
0x1800075d5  jmp     short loc_1800075D9
0x1800075d7  xor     eax, eax
0x1800075d9  pop     r14
0x1800075db  pop     rdi
0x1800075dc  pop     rsi
0x1800075dd  pop     rbp
0x1800075de  pop     rbx
0x1800075df  retn
```
