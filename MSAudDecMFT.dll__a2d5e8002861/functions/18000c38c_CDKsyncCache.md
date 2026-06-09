# CDKsyncCache

- ea: `0x18000c38c`
- end: `0x18000c4ff`
- name: `CDKsyncCache`
- size: `371`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a810`
- `0x18000c510`
- `0x18000eb68`
- `0x180013dac`
- `0x180013ef4`
- `0x180013f68`
- `0x180018730`
- `0x18004019c`
- `0x180047994`
- `0x18004b258`

## callees

- `0x18000c38c`

## pseudocode

```c
void __fastcall CDKsyncCache(int *a1)
{
  __int64 v2; // rbp
  int v3; // edx
  int v4; // eax
  int v5; // edx
  int v6; // r15d
  unsigned int v7; // r12d
  int v8; // ecx
  char v9; // si
  __int64 v10; // rbx
  int v11; // r13d
  int v12; // edx
  int v13; // r13d
  __int64 v14; // r12
  int v15; // esi
  __int64 v16; // rdi
  __int64 v17; // r11
  __int64 v18; // r10
  int v19; // r9d

  v2 = (unsigned int)a1[1];
  if ( a1[10] )
  {
    if ( (_DWORD)v2 )
    {
      v6 = *a1;
      v7 = a1[5];
      v8 = a1[9];
      v9 = v7;
      a1[2] += v2;
      v10 = *((_QWORD *)a1 + 3);
      v11 = a1[8];
      v12 = BitMask[v2];
      a1[5] = (v7 + v2) & (v8 - 1);
      v13 = v11 - 1;
      v14 = v7 >> 3;
      v15 = v9 & 7;
      v16 = v13 & (unsigned int)(v14 + 1);
      v17 = v13 & (unsigned int)(v14 + 2);
      v18 = v13 & (unsigned int)(v14 + 3);
      v19 = ((unsigned int)(v6 << (32 - v2)) >> v15)
          | ~((unsigned int)(v12 << (32 - v2)) >> v15)
          & (*(unsigned __int8 *)(v10 + v18)
           | ((*(unsigned __int8 *)(v10 + v17)
             | (((*(unsigned __int8 *)(v14 + v10) << 8) | *(unsigned __int8 *)(v10 + v16)) << 8)) << 8));
      *(_BYTE *)(v14 + v10) = HIBYTE(v19);
      *(_BYTE *)(v16 + *((_QWORD *)a1 + 3)) = BYTE2(v19);
      *(_BYTE *)(v17 + *((_QWORD *)a1 + 3)) = BYTE1(v19);
      *(_BYTE *)(v18 + *((_QWORD *)a1 + 3)) = v19;
      if ( (unsigned int)(v15 + v2) > 0x20 )
        *(_BYTE *)((v13 & (unsigned int)(v14 + 4)) + *((_QWORD *)a1 + 3)) = ((_BYTE)v6 << (8 - ((v15 + v2) & 7)))
                                                                          | *(_BYTE *)((v13 & (unsigned int)(v14 + 4))
                                                                                     + *((_QWORD *)a1 + 3))
                                                                          & ~(LOBYTE(BitMask[((_BYTE)v15 + (_BYTE)v2)
                                                                                           & 7]) << (8 - ((v15 + v2) & 7)));
    }
  }
  else
  {
    v3 = a1[2];
    v4 = v2 + v3;
    v5 = v3 - v2;
    if ( *((_BYTE *)a1 + 40) )
      v4 = v5;
    a1[2] = v4;
    a1[5] = (a1[9] - 1) & (a1[5] - v2);
  }
  *(_QWORD *)a1 = 0;
}

```

## disassembly

```asm
0x18000c38c  push    rbx
0x18000c38e  push    rbp
0x18000c38f  push    rsi
0x18000c390  push    rdi
0x18000c391  push    r12
0x18000c393  push    r13
0x18000c395  push    r14
0x18000c397  push    r15
0x18000c399  cmp     dword ptr [rcx+28h], 0
0x18000c39d  mov     r14, rcx
0x18000c3a0  mov     ebp, [rcx+4]
0x18000c3a3  jnz     short loc_18000C3DE
0x18000c3a5  mov     eax, [rcx+8]
0x18000c3a8  mov     edx, eax
0x18000c3aa  add     eax, ebp
0x18000c3ac  sub     edx, ebp
0x18000c3ae  cmp     byte ptr [rcx+28h], 0
0x18000c3b2  cmovnz  eax, edx
0x18000c3b5  mov     [rcx+8], eax
0x18000c3b8  mov     ecx, [rcx+14h]
0x18000c3bb  mov     eax, [r14+24h]
0x18000c3bf  sub     ecx, ebp
0x18000c3c1  dec     eax
0x18000c3c3  and     ecx, eax
0x18000c3c5  mov     [r14+14h], ecx
0x18000c3c9  mov     qword ptr [r14], 0
0x18000c3d0  pop     r15
0x18000c3d2  pop     r14
0x18000c3d4  pop     r13
0x18000c3d6  pop     r12
0x18000c3d8  pop     rdi
0x18000c3d9  pop     rsi
0x18000c3da  pop     rbp
0x18000c3db  pop     rbx
0x18000c3dc  retn
0x18000c3de  test    ebp, ebp
0x18000c3e0  jz      short loc_18000C3C9
0x18000c3e2  mov     edx, [rcx+14h]
0x18000c3e5  mov     r8d, 20h ; ' '
0x18000c3eb  mov     r15d, [rcx]
0x18000c3ee  mov     r12d, edx
0x18000c3f1  mov     ecx, [rcx+24h]
0x18000c3f4  mov     esi, edx
0x18000c3f6  add     [r14+8], ebp
0x18000c3fa  dec     ecx
0x18000c3fc  mov     rbx, [r14+18h]
0x18000c400  lea     eax, [rdx+rbp]
0x18000c403  mov     r13d, [r14+20h]
0x18000c407  lea     rdx, BitMask
0x18000c40e  mov     edx, [rdx+rbp*4]
0x18000c411  and     ecx, eax
0x18000c413  mov     [r14+14h], ecx
0x18000c417  dec     r13d
0x18000c41a  shr     r12d, 3
0x18000c41e  and     esi, 7
0x18000c421  sub     r8d, ebp
0x18000c424  mov     eax, r13d
0x18000c427  mov     ecx, r8d
0x18000c42a  shl     edx, cl
0x18000c42c  mov     ecx, esi
0x18000c42e  shr     edx, cl
0x18000c430  lea     edi, [r12+1]
0x18000c435  and     rdi, rax
0x18000c438  lea     r11d, [r12+2]
0x18000c43d  mov     eax, r13d
0x18000c440  lea     r10d, [r12+3]
0x18000c445  and     r11, rax
0x18000c448  mov     ecx, r8d
0x18000c44b  mov     eax, r13d
0x18000c44e  not     edx
0x18000c450  movzx   r9d, byte ptr [rbx+rdi]
0x18000c455  and     r10, rax
0x18000c458  movzx   eax, byte ptr [r12+rbx]
0x18000c45d  shl     eax, 8
0x18000c460  or      r9d, eax
0x18000c463  movzx   eax, byte ptr [rbx+r11]
0x18000c468  shl     r9d, 8
0x18000c46c  or      r9d, eax
0x18000c46f  movzx   eax, byte ptr [rbx+r10]
0x18000c474  shl     r9d, 8
0x18000c478  or      r9d, eax
0x18000c47b  mov     eax, r15d
0x18000c47e  shl     eax, cl
0x18000c480  and     r9d, edx
0x18000c483  mov     ecx, esi
0x18000c485  shr     eax, cl
0x18000c487  or      r9d, eax
0x18000c48a  mov     eax, r9d
0x18000c48d  mov     ecx, r9d
0x18000c490  shr     eax, 18h
0x18000c493  mov     [r12+rbx], al
0x18000c497  mov     rax, [r14+18h]
0x18000c49b  shr     ecx, 10h
0x18000c49e  mov     [rdi+rax], cl
0x18000c4a1  mov     ecx, r9d
0x18000c4a4  mov     rax, [r14+18h]
0x18000c4a8  shr     ecx, 8
0x18000c4ab  mov     [r11+rax], cl
0x18000c4af  mov     rax, [r14+18h]
0x18000c4b3  mov     [r10+rax], r9b
0x18000c4b7  lea     eax, [rsi+rbp]
0x18000c4ba  cmp     eax, 20h ; ' '
0x18000c4bd  jbe     loc_18000C3C9
0x18000c4c3  mov     r8, [r14+18h]
0x18000c4c7  lea     r9d, [r12+4]
0x18000c4cc  and     eax, 7
0x18000c4cf  mov     ecx, 8
0x18000c4d4  sub     ecx, eax
0x18000c4d6  mov     edx, eax
0x18000c4d8  mov     eax, r13d
0x18000c4db  and     r9, rax
0x18000c4de  shl     r15b, cl
0x18000c4e1  lea     rax, BitMask
0x18000c4e8  mov     al, [rax+rdx*4]
0x18000c4eb  shl     al, cl
0x18000c4ed  not     al
0x18000c4ef  and     al, [r9+r8]
0x18000c4f3  or      al, r15b
0x18000c4f6  mov     [r9+r8], al
0x18000c4fa  jmp     loc_18000C3C9
```
