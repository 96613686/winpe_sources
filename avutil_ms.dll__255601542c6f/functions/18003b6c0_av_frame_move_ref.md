# av_frame_move_ref

- ea: `0x18003b6c0`
- end: `0x18003b744`
- name: `av_frame_move_ref`
- size: `132`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180033ab0`
- `0x18003fb48`

## callees

- `0x18003b6c0`
- `0x18003c4e8`

## pseudocode

```c
__int64 __fastcall av_frame_move_ref(__int64 a1, __int64 a2)
{
  __int64 v2; // r9
  _OWORD *v3; // rax
  _OWORD *v4; // r8
  __int128 v5; // xmm1

  v2 = 3;
  v3 = (_OWORD *)a1;
  v4 = (_OWORD *)a2;
  do
  {
    *v3 = *v4;
    v3[1] = v4[1];
    v3[2] = v4[2];
    v3[3] = v4[3];
    v3[4] = v4[4];
    v3[5] = v4[5];
    v3[6] = v4[6];
    v3 += 8;
    v5 = v4[7];
    v4 += 8;
    *(v3 - 1) = v5;
    --v2;
  }
  while ( v2 );
  *v3 = *v4;
  v3[1] = v4[1];
  if ( *(_QWORD *)(a2 + 96) == a2 )
    *(_QWORD *)(a1 + 96) = a1;
  return sub_18003C4E8(a2);
}

```

## disassembly

```asm
0x18003b6c0  mov     r9d, 3
0x18003b6c6  mov     rax, rcx
0x18003b6c9  mov     r8, rdx
0x18003b6cc  lea     r10d, [r9+7Dh]
0x18003b6d0  movups  xmm0, xmmword ptr [r8]
0x18003b6d4  movups  xmmword ptr [rax], xmm0
0x18003b6d7  movups  xmm1, xmmword ptr [r8+10h]
0x18003b6dc  movups  xmmword ptr [rax+10h], xmm1
0x18003b6e0  movups  xmm0, xmmword ptr [r8+20h]
0x18003b6e5  movups  xmmword ptr [rax+20h], xmm0
0x18003b6e9  movups  xmm1, xmmword ptr [r8+30h]
0x18003b6ee  movups  xmmword ptr [rax+30h], xmm1
0x18003b6f2  movups  xmm0, xmmword ptr [r8+40h]
0x18003b6f7  movups  xmmword ptr [rax+40h], xmm0
0x18003b6fb  movups  xmm1, xmmword ptr [r8+50h]
0x18003b700  movups  xmmword ptr [rax+50h], xmm1
0x18003b704  movups  xmm0, xmmword ptr [r8+60h]
0x18003b709  movups  xmmword ptr [rax+60h], xmm0
0x18003b70d  add     rax, r10
0x18003b710  movups  xmm1, xmmword ptr [r8+70h]
0x18003b715  add     r8, r10
0x18003b718  movups  xmmword ptr [rax-10h], xmm1
0x18003b71c  sub     r9, 1
0x18003b720  jnz     short loc_18003B6D0
0x18003b722  movups  xmm0, xmmword ptr [r8]
0x18003b726  movups  xmmword ptr [rax], xmm0
0x18003b729  movups  xmm1, xmmword ptr [r8+10h]
0x18003b72e  movups  xmmword ptr [rax+10h], xmm1
0x18003b732  cmp     [rdx+60h], rdx
0x18003b736  jnz     short loc_18003B73C
0x18003b738  mov     [rcx+60h], rcx
0x18003b73c  mov     rcx, rdx
0x18003b73f  jmp     sub_18003C4E8
```
