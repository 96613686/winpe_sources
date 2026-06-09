# FH4::UWMap4::ReadEntry(uchar * *)

- ea: `0x14000f3a8`
- end: `0x14000f446`
- name: `?ReadEntry@UWMap4@FH4@@AEAAXPEAPEAE@Z`
- size: `158`
- prototype: `void __fastcall(FH4::UWMap4 *__hidden this, unsigned __int8 **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ee90`
- `0x14000f464`
- `0x14000f534`

## callees

- `0x14000f3a8`

## pseudocode

```c
void __fastcall FH4::UWMap4::ReadEntry(FH4::UWMap4 *this, unsigned __int8 **a2)
{
  __int64 v4; // rcx
  unsigned __int8 *v5; // r8
  unsigned int v6; // eax
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int *v10; // rdx
  __int64 v11; // rcx
  unsigned __int8 *v12; // rdx
  int v13; // eax

  v4 = **a2 & 0xF;
  v5 = &(*a2)[-*((char *)qword_14002D5E0 + v4)];
  v6 = *((_DWORD *)v5 - 1) >> *((_BYTE *)&qword_14002D5E0[2] + v4);
  *a2 = v5;
  v7 = v6 & 3;
  *((_DWORD *)this + 5) = v7;
  *((_DWORD *)this + 4) = v6 >> 2;
  if ( v7 == 1 || v7 == 2 )
  {
    v9 = *(_DWORD *)*a2;
    *a2 += 4;
    *((_DWORD *)this + 6) = v9;
    v10 = (int *)*a2;
    v11 = *(_BYTE *)v10 & 0xF;
    v12 = (unsigned __int8 *)v10 - *((char *)qword_14002D5E0 + v11);
    v13 = *((_DWORD *)v12 - 1) >> *((_BYTE *)&qword_14002D5E0[2] + v11);
    *a2 = v12;
    *((_DWORD *)this + 7) = v13;
  }
  else if ( v7 == 3 )
  {
    v8 = *(_DWORD *)*a2;
    *a2 += 4;
    *((_DWORD *)this + 6) = v8;
  }
}

```

## disassembly

```asm
0x14000f3a8  mov     r8, [rdx]
0x14000f3ab  lea     r11, cs:140000000h
0x14000f3b2  mov     r10, rcx
0x14000f3b5  mov     r9, rdx
0x14000f3b8  movzx   ecx, byte ptr [r8]
0x14000f3bc  and     ecx, 0Fh
0x14000f3bf  movsx   rax, byte ptr [rcx+r11+2D5E0h]
0x14000f3c8  mov     cl, [rcx+r11+2D5F0h]
0x14000f3d0  sub     r8, rax
0x14000f3d3  mov     eax, [r8-4]
0x14000f3d7  shr     eax, cl
0x14000f3d9  mov     ecx, eax
0x14000f3db  mov     [rdx], r8
0x14000f3de  and     ecx, 3
0x14000f3e1  shr     eax, 2
0x14000f3e4  mov     [r10+14h], ecx
0x14000f3e8  mov     [r10+10h], eax
0x14000f3ec  cmp     ecx, 1
0x14000f3ef  jz      short loc_14000F40C
0x14000f3f1  cmp     ecx, 2
0x14000f3f4  jz      short loc_14000F40C
0x14000f3f6  cmp     ecx, 3
0x14000f3f9  jnz     short locret_14000F445
0x14000f3fb  mov     rax, [rdx]
0x14000f3fe  mov     ecx, [rax]
0x14000f400  add     rax, 4
0x14000f404  mov     [rdx], rax
0x14000f407  mov     [r10+18h], ecx
0x14000f40b  retn
0x14000f40c  mov     rax, [rdx]
0x14000f40f  mov     ecx, [rax]
0x14000f411  add     rax, 4
0x14000f415  mov     [rdx], rax
0x14000f418  mov     [r10+18h], ecx
0x14000f41c  mov     rdx, [rdx]
0x14000f41f  movzx   ecx, byte ptr [rdx]
0x14000f422  and     ecx, 0Fh
0x14000f425  movsx   rax, byte ptr [rcx+r11+2D5E0h]
0x14000f42e  mov     cl, [rcx+r11+2D5F0h]
0x14000f436  sub     rdx, rax
0x14000f439  mov     eax, [rdx-4]
0x14000f43c  shr     eax, cl
0x14000f43e  mov     [r9], rdx
0x14000f441  mov     [r10+1Ch], eax
0x14000f445  retn
```
