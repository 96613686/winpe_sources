# CTiledConverter::RemoveDegenerateGaps(void)

- ea: `0x100452390`
- end: `0x100452505`
- name: `?RemoveDegenerateGaps@CTiledConverter@@IEAAXXZ`
- size: `373`
- prototype: `void __fastcall(CTiledConverter *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x100451ef0`

## callees

- `0x100452390`

## pseudocode

```c
void __fastcall CTiledConverter::RemoveDegenerateGaps(CTiledConverter *this)
{
  __int64 v1; // r10
  unsigned int v3; // r8d
  unsigned int v4; // ecx
  unsigned int v5; // r9d
  __int64 v6; // rdi
  __int64 v7; // rbx
  double v8; // xmm1_8
  double v9; // xmm0_8
  unsigned int v10; // eax
  unsigned int v11; // r9d
  unsigned int i; // r8d
  __int64 v13; // r11
  __int64 v14; // rcx
  unsigned int v15; // eax
  unsigned int j; // r8d
  __int64 v17; // r9
  __int64 v18; // rcx

  v1 = 0;
  v3 = 0;
  v4 = 0;
  v5 = *((_DWORD *)this + 51);
  if ( v5 )
  {
    while ( 1 )
    {
      if ( v3 >= v5 )
        goto LABEL_8;
      v6 = *((_QWORD *)this + 28);
      v7 = 5LL * v3;
      v8 = *(double *)(v6 + 40LL * v3 + 24);
      v9 = *(double *)(*((_QWORD *)this + 26) + 40LL * v4 + 24);
      if ( v8 > v9 )
        goto LABEL_6;
      ++v3;
      if ( v9 <= v8 )
        break;
LABEL_7:
      if ( v4 >= v5 )
        goto LABEL_8;
    }
    *(_BYTE *)(v6 + 8 * v7 + 32) = 1;
    *(_BYTE *)(*((_QWORD *)this + 26) + 40LL * v4 + 32) = 1;
LABEL_6:
    ++v4;
    goto LABEL_7;
  }
LABEL_8:
  v10 = *((_DWORD *)this + 51);
  v11 = 0;
  for ( i = 0; i < v10; ++i )
  {
    v13 = *((_QWORD *)this + 26);
    if ( !*(_BYTE *)(v13 + 40LL * i + 32) )
    {
      if ( v11 < i )
      {
        v14 = 5LL * v11;
        *(_OWORD *)(v13 + 8 * v14) = *(_OWORD *)(v13 + 40LL * i);
        *(_OWORD *)(v13 + 8 * v14 + 16) = *(_OWORD *)(v13 + 40LL * i + 16);
        *(_QWORD *)(v13 + 8 * v14 + 32) = *(_QWORD *)(v13 + 40LL * i + 32);
      }
      ++v11;
    }
    v10 = *((_DWORD *)this + 51);
  }
  if ( v11 < v10 )
    *((_DWORD *)this + 51) = v11;
  v15 = *((_DWORD *)this + 55);
  for ( j = 0; j < v15; ++j )
  {
    v17 = *((_QWORD *)this + 28);
    if ( !*(_BYTE *)(v17 + 40LL * j + 32) )
    {
      if ( (unsigned int)v1 < j )
      {
        v18 = 5 * v1;
        *(_OWORD *)(v17 + 8 * v18) = *(_OWORD *)(v17 + 40LL * j);
        *(_OWORD *)(v17 + 8 * v18 + 16) = *(_OWORD *)(v17 + 40LL * j + 16);
        *(_QWORD *)(v17 + 8 * v18 + 32) = *(_QWORD *)(v17 + 40LL * j + 32);
      }
      v1 = (unsigned int)(v1 + 1);
    }
    v15 = *((_DWORD *)this + 55);
  }
  if ( (unsigned int)v1 < v15 )
    *((_DWORD *)this + 55) = v1;
}

```

## disassembly

```asm
0x100452390  sub     rsp, 8
0x100452394  xor     r10d, r10d
0x100452397  mov     [rsp+8+arg_0], rbx
0x10045239c  mov     rdx, rcx
0x10045239f  mov     r8d, r10d
0x1004523a2  mov     ecx, r10d
0x1004523a5  mov     r9d, [rdx+0CCh]
0x1004523ac  test    r9d, r9d
0x1004523af  jz      short loc_10045240E
0x1004523b1  mov     [rsp+8+var_8], rdi
0x1004523b5  cmp     r8d, r9d
0x1004523b8  jnb     short loc_10045240A
0x1004523ba  mov     rdi, [rdx+0E0h]
0x1004523c1  mov     eax, ecx
0x1004523c3  lea     r11, [rax+rax*4]
0x1004523c7  mov     eax, r8d
0x1004523ca  lea     rbx, [rax+rax*4]
0x1004523ce  mov     rax, [rdx+0D0h]
0x1004523d5  movsd   xmm1, qword ptr [rdi+rbx*8+18h]
0x1004523db  movsd   xmm0, qword ptr [rax+r11*8+18h]
0x1004523e2  comisd  xmm1, xmm0
0x1004523e6  ja      short loc_100452403
0x1004523e8  inc     r8d
0x1004523eb  comisd  xmm0, xmm1
0x1004523ef  ja      short loc_100452405
0x1004523f1  mov     byte ptr [rdi+rbx*8+20h], 1
0x1004523f6  mov     rax, [rdx+0D0h]
0x1004523fd  mov     byte ptr [rax+r11*8+20h], 1
0x100452403  inc     ecx
0x100452405  cmp     ecx, r9d
0x100452408  jb      short loc_1004523B5
0x10045240a  mov     rdi, [rsp+8+var_8]
0x10045240e  mov     eax, [rdx+0CCh]
0x100452414  mov     r9d, r10d
0x100452417  mov     r8d, r10d
0x10045241a  test    eax, eax
0x10045241c  jz      short loc_100452476
0x10045241e  xchg    ax, ax
0x100452420  mov     r11, [rdx+0D0h]
0x100452427  mov     eax, r8d
0x10045242a  lea     rbx, [rax+rax*4]
0x10045242e  cmp     [r11+rbx*8+20h], r10b
0x100452433  jnz     short loc_100452468
0x100452435  cmp     r9d, r8d
0x100452438  jnb     short loc_100452465
0x10045243a  movups  xmm0, xmmword ptr [r11+rbx*8]
0x10045243f  mov     eax, r9d
0x100452442  lea     rcx, [rax+rax*4]
0x100452446  movups  xmmword ptr [r11+rcx*8], xmm0
0x10045244b  movups  xmm1, xmmword ptr [r11+rbx*8+10h]
0x100452451  movups  xmmword ptr [r11+rcx*8+10h], xmm1
0x100452457  movsd   xmm0, qword ptr [r11+rbx*8+20h]
0x10045245e  movsd   qword ptr [r11+rcx*8+20h], xmm0
0x100452465  inc     r9d
0x100452468  mov     eax, [rdx+0CCh]
0x10045246e  inc     r8d
0x100452471  cmp     r8d, eax
0x100452474  jb      short loc_100452420
0x100452476  mov     rbx, [rsp+8+arg_0]
0x10045247b  cmp     r9d, eax
0x10045247e  jnb     short loc_100452487
0x100452480  mov     [rdx+0CCh], r9d
0x100452487  mov     eax, [rdx+0DCh]
0x10045248d  mov     r8d, r10d
0x100452490  test    eax, eax
0x100452492  jz      short loc_1004524F4
0x100452494  nop     dword ptr [rax+00h]
0x100452498  nop     dword ptr [rax+rax+00000000h]
0x1004524a0  mov     r9, [rdx+0E0h]
0x1004524a7  mov     eax, r8d
0x1004524aa  lea     r11, [rax+rax*4]
0x1004524ae  cmp     byte ptr [r9+r11*8+20h], 0
0x1004524b4  jnz     short loc_1004524E6
0x1004524b6  cmp     r10d, r8d
0x1004524b9  jnb     short loc_1004524E3
0x1004524bb  movups  xmm0, xmmword ptr [r9+r11*8]
0x1004524c0  lea     rcx, [r10+r10*4]
0x1004524c4  movups  xmmword ptr [r9+rcx*8], xmm0
0x1004524c9  movups  xmm1, xmmword ptr [r9+r11*8+10h]
0x1004524cf  movups  xmmword ptr [r9+rcx*8+10h], xmm1
0x1004524d5  movsd   xmm0, qword ptr [r9+r11*8+20h]
0x1004524dc  movsd   qword ptr [r9+rcx*8+20h], xmm0
0x1004524e3  inc     r10d
0x1004524e6  mov     eax, [rdx+0DCh]
0x1004524ec  inc     r8d
0x1004524ef  cmp     r8d, eax
0x1004524f2  jb      short loc_1004524A0
0x1004524f4  cmp     r10d, eax
0x1004524f7  jnb     short loc_100452500
0x1004524f9  mov     [rdx+0DCh], r10d
0x100452500  add     rsp, 8
0x100452504  retn
```
