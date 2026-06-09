# LookUpTableFlushPartial

- ea: `0x18001b3f4`
- end: `0x18001b47e`
- name: `LookUpTableFlushPartial`
- size: `138`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ac90`
- `0x18001b4f0`

## callees

- `0x18001ab60`
- `0x18001b3f4`

## pseudocode

```c
void __fastcall LookUpTableFlushPartial(__int64 a1)
{
  unsigned int v2; // ebp
  unsigned int v3; // edi
  unsigned int v4; // esi
  _QWORD *v5; // rax

  if ( *(_DWORD *)(a1 + 256) )
  {
    v2 = *(_DWORD *)(a1 + 260);
    v3 = 0;
    v4 = v2;
    do
    {
      if ( *(_QWORD *)(a1 + 8LL * v4) )
        v3 += FlushLookUpTableBucket(a1, v4);
      v4 = ((_BYTE)v4 + 1) & 0x1F;
    }
    while ( v4 != v2 && v3 < 0x10 );
    *(_DWORD *)(a1 + 260) = v4;
    if ( v3 )
    {
      v5 = (_QWORD *)(a1 + 280);
      if ( *(_DWORD *)(a1 + 296) > v3 || !*v5 )
        *(_DWORD *)(a1 + 296) = v3;
      if ( *(_DWORD *)(a1 + 292) < v3 )
        *(_DWORD *)(a1 + 292) = v3;
      ++*v5;
      *(_QWORD *)(a1 + 272) += v3;
    }
  }
}

```

## disassembly

```asm
0x18001b3f4  push    rbx
0x18001b3f6  push    rbp
0x18001b3f7  push    rsi
0x18001b3f8  push    rdi
0x18001b3f9  sub     rsp, 28h
0x18001b3fd  cmp     dword ptr [rcx+100h], 0
0x18001b404  mov     rbx, rcx
0x18001b407  jz      short loc_18001B475
0x18001b409  mov     ebp, [rcx+104h]
0x18001b40f  xor     edi, edi
0x18001b411  mov     esi, ebp
0x18001b413  mov     eax, esi
0x18001b415  cmp     qword ptr [rbx+rax*8], 0
0x18001b41a  jz      short loc_18001B428
0x18001b41c  mov     edx, esi
0x18001b41e  mov     rcx, rbx
0x18001b421  call    FlushLookUpTableBucket
0x18001b426  add     edi, eax
0x18001b428  inc     esi
0x18001b42a  and     esi, 1Fh
0x18001b42d  cmp     esi, ebp
0x18001b42f  jz      short loc_18001B436
0x18001b431  cmp     edi, 10h
0x18001b434  jb      short loc_18001B413
0x18001b436  mov     [rbx+104h], esi
0x18001b43c  test    edi, edi
0x18001b43e  jz      short loc_18001B475
0x18001b440  lea     rax, [rbx+118h]
0x18001b447  cmp     [rbx+128h], edi
0x18001b44d  ja      short loc_18001B455
0x18001b44f  cmp     qword ptr [rax], 0
0x18001b453  jnz     short loc_18001B45B
0x18001b455  mov     [rbx+128h], edi
0x18001b45b  cmp     [rbx+124h], edi
0x18001b461  jnb     short loc_18001B469
0x18001b463  mov     [rbx+124h], edi
0x18001b469  inc     qword ptr [rax]
0x18001b46c  mov     eax, edi
0x18001b46e  add     [rbx+110h], rax
0x18001b475  add     rsp, 28h
0x18001b479  pop     rdi
0x18001b47a  pop     rsi
0x18001b47b  pop     rbp
0x18001b47c  pop     rbx
0x18001b47d  retn
```
