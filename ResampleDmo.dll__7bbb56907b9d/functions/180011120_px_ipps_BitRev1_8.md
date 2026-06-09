# px_ipps_BitRev1_8

- ea: `0x180011120`
- end: `0x1800111c6`
- name: `px_ipps_BitRev1_8`
- size: `166`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d210`
- `0x18000d370`
- `0x18000d54c`
- `0x18000dd90`
- `0x18000df70`
- `0x18000e0cc`
- `0x1800155d0`
- `0x180015b08`
- `0x180015bac`

## callees

- `0x180011120`

## pseudocode

```c
void __fastcall px_ipps_BitRev1_8(__int64 a1, int a2, int *a3)
{
  int *v3; // r9
  __int64 v5; // r11
  int v6; // eax
  int i; // ecx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  int v13; // eax
  int v14; // ecx
  __int64 v15; // rdx
  __int64 v16; // rax

  v3 = a3;
  if ( a2 >= 4 )
  {
    v5 = a1 + 8 * ((__int64)a2 >> 1);
    v6 = *a3;
    for ( i = a3[1]; ; i = v3[1] )
    {
      v13 = v6 >> 1;
      v14 = i >> 1;
      if ( v13 <= 0 )
        break;
      v8 = v13;
      v3 += 2;
      v9 = *(_QWORD *)(a1 + 8LL * v13);
      *(_QWORD *)(a1 + 8 * v8) = *(_QWORD *)(a1 + 8LL * v14);
      *(_QWORD *)(a1 + 8LL * v14) = v9;
      v10 = *(_QWORD *)(a1 + 8 * v8 + 8);
      *(_QWORD *)(a1 + 8 * v8 + 8) = *(_QWORD *)(v5 + 8LL * v14);
      *(_QWORD *)(v5 + 8LL * v14) = v10;
      v11 = *(_QWORD *)(v5 + 8 * v8);
      *(_QWORD *)(v5 + 8 * v8) = *(_QWORD *)(a1 + 8LL * v14 + 8);
      *(_QWORD *)(a1 + 8LL * v14 + 8) = v11;
      v12 = *(_QWORD *)(v5 + 8 * v8 + 8);
      *(_QWORD *)(v5 + 8 * v8 + 8) = *(_QWORD *)(v5 + 8LL * v14 + 8);
      *(_QWORD *)(v5 + 8LL * v14 + 8) = v12;
      v6 = *v3;
    }
    do
    {
      v15 = v13;
      ++v3;
      v16 = *(_QWORD *)(a1 + 8LL * v13 + 8);
      *(_QWORD *)(a1 + 8 * v15 + 8) = *(_QWORD *)(v5 + 8 * v15);
      *(_QWORD *)(v5 + 8 * v15) = v16;
      v13 = *v3 >> 1;
    }
    while ( v13 > 0 );
  }
}

```

## disassembly

```asm
0x180011120  mov     r9, r8
0x180011123  mov     r10, rcx
0x180011126  cmp     edx, 4
0x180011129  jl      locret_1800111C5
0x18001112f  movsxd  rax, edx
0x180011132  sar     rax, 1
0x180011135  lea     r11, [rcx+rax*8]
0x180011139  mov     eax, [r8]
0x18001113c  mov     ecx, [r8+4]
0x180011140  jmp     short loc_18001119B
0x180011142  movsxd  rdx, ecx
0x180011145  movsxd  r8, eax
0x180011148  add     r9, 8
0x18001114c  mov     rcx, [r10+rdx*8]
0x180011150  mov     rax, [r10+r8*8]
0x180011154  mov     [r10+r8*8], rcx
0x180011158  mov     [r10+rdx*8], rax
0x18001115c  mov     rax, [r10+r8*8+8]
0x180011161  mov     rcx, [r11+rdx*8]
0x180011165  mov     [r10+r8*8+8], rcx
0x18001116a  mov     [r11+rdx*8], rax
0x18001116e  mov     rcx, [r10+rdx*8+8]
0x180011173  mov     rax, [r11+r8*8]
0x180011177  mov     [r11+r8*8], rcx
0x18001117b  mov     [r10+rdx*8+8], rax
0x180011180  mov     rcx, [r11+rdx*8+8]
0x180011185  mov     rax, [r11+r8*8+8]
0x18001118a  mov     [r11+r8*8+8], rcx
0x18001118f  mov     [r11+rdx*8+8], rax
0x180011194  mov     eax, [r9]
0x180011197  mov     ecx, [r9+4]
0x18001119b  sar     eax, 1
0x18001119d  sar     ecx, 1
0x18001119f  test    eax, eax
0x1800111a1  jg      short loc_180011142
0x1800111a3  movsxd  rdx, eax
0x1800111a6  lea     r9, [r9+4]
0x1800111aa  mov     rax, [r10+rdx*8+8]
0x1800111af  mov     rcx, [r11+rdx*8]
0x1800111b3  mov     [r10+rdx*8+8], rcx
0x1800111b8  mov     [r11+rdx*8], rax
0x1800111bc  mov     eax, [r9]
0x1800111bf  sar     eax, 1
0x1800111c1  test    eax, eax
0x1800111c3  jg      short loc_1800111A3
0x1800111c5  retn
```
