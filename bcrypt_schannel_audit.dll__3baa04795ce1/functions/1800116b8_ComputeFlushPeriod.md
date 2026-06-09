# ComputeFlushPeriod

- ea: `0x1800116b8`
- end: `0x180011754`
- name: `ComputeFlushPeriod`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800114c4`

## callees

- `0x1800116b8`

## pseudocode

```c
__int64 __fastcall ComputeFlushPeriod(unsigned __int64 a1)
{
  __int64 v1; // rax
  unsigned int v2; // r8d
  unsigned __int64 v3; // rdx
  int v4; // eax
  unsigned __int64 i; // rdx
  int v6; // eax
  __int128 v8; // [rsp+0h] [rbp-18h]
  unsigned __int64 v9; // [rsp+20h] [rbp+8h]

  v1 = *(_QWORD *)(a1 + 328);
  v2 = 0;
  v9 = a1 >> 4;
  v3 = 0;
  v8 = *(_OWORD *)(*(_QWORD *)(v1 + 8) - 16LL);
  do
  {
    v4 = *((unsigned __int8 *)&v8 + v3++);
    v2 = (1025 * (v2 + v4)) ^ ((1025 * (v2 + v4)) >> 6);
  }
  while ( v3 < 0x10 );
  for ( i = 0; i < 8; ++i )
  {
    v6 = *((unsigned __int8 *)&v9 + i);
    v2 = (1025 * (v2 + v6)) ^ ((1025 * (v2 + v6)) >> 6);
  }
  return 32769 * ((9 * v2) ^ ((9 * v2) >> 11)) % 0x927C0 + 600000;
}

```

## disassembly

```asm
0x1800116b8  sub     rsp, 18h
0x1800116bc  mov     rax, [rcx+148h]
0x1800116c3  xor     r8d, r8d
0x1800116c6  shr     rcx, 4
0x1800116ca  mov     [rsp+18h+arg_0], rcx
0x1800116cf  mov     rdx, [rax+8]
0x1800116d3  movups  xmm0, xmmword ptr [rdx-10h]
0x1800116d7  xor     edx, edx
0x1800116d9  movdqu  [rsp+18h+var_18], xmm0
0x1800116de  movzx   eax, byte ptr [rsp+rdx+18h+var_18]
0x1800116e2  inc     rdx
0x1800116e5  add     eax, r8d
0x1800116e8  imul    ecx, eax, 401h
0x1800116ee  mov     r8d, ecx
0x1800116f1  shr     r8d, 6
0x1800116f5  xor     r8d, ecx
0x1800116f8  cmp     rdx, 10h
0x1800116fc  jb      short loc_1800116DE
0x1800116fe  xor     edx, edx
0x180011700  movzx   eax, byte ptr [rsp+rdx+18h+arg_0]
0x180011705  inc     rdx
0x180011708  add     eax, r8d
0x18001170b  imul    ecx, eax, 401h
0x180011711  mov     r8d, ecx
0x180011714  shr     r8d, 6
0x180011718  xor     r8d, ecx
0x18001171b  cmp     rdx, 8
0x18001171f  jb      short loc_180011700
0x180011721  lea     eax, [r8+r8*8]
0x180011725  mov     ecx, eax
0x180011727  shr     ecx, 0Bh
0x18001172a  xor     ecx, eax
0x18001172c  mov     eax, 6FD91D85h
0x180011731  imul    r8d, ecx, 8001h
0x180011738  mul     r8d
0x18001173b  shr     edx, 12h
0x18001173e  imul    ecx, edx, 927C0h
0x180011744  sub     r8d, ecx
0x180011747  lea     eax, [r8+927C0h]
0x18001174e  add     rsp, 18h
0x180011752  retn
```
