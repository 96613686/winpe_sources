# ComputeEventEntryHash

- ea: `0x1800113c4`
- end: `0x18001145c`
- name: `ComputeEventEntryHash`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011104`

## callees

- `0x1800113c4`

## pseudocode

```c
__int64 __fastcall ComputeEventEntryHash(char a1, unsigned __int8 a2, __int64 a3)
{
  unsigned int v3; // r10d
  unsigned __int64 i; // rcx
  int v7; // eax
  unsigned __int8 j; // r11
  unsigned __int64 k; // rdx
  int v10; // eax

  v3 = 0;
  for ( i = 0; i < 8; ++i )
  {
    v7 = *(unsigned __int8 *)(a3 + i + 16);
    v3 = (1025 * (v3 + v7)) ^ ((1025 * (v3 + v7)) >> 6);
  }
  for ( j = a1 + 2; j < a2; ++j )
  {
    for ( k = 0; k < *(unsigned int *)(a3 + 16LL * j + 8); v3 = (1025 * (v3 + v10)) ^ ((1025 * (v3 + v10)) >> 6) )
      v10 = *(unsigned __int8 *)(*(_QWORD *)(a3 + 16LL * j) + k++);
  }
  return 32769 * ((9 * v3) ^ ((9 * v3) >> 11));
}

```

## disassembly

```asm
0x1800113c4  mov     [rsp+arg_0], rbx
0x1800113c9  mov     [rsp+arg_8], rdi
0x1800113ce  xor     r10d, r10d
0x1800113d1  mov     r11b, cl
0x1800113d4  xor     ecx, ecx
0x1800113d6  mov     bl, dl
0x1800113d8  movzx   eax, byte ptr [r8+rcx+10h]
0x1800113de  inc     rcx
0x1800113e1  add     eax, r10d
0x1800113e4  imul    r9d, eax, 401h
0x1800113eb  mov     r10d, r9d
0x1800113ee  shr     r10d, 6
0x1800113f2  xor     r10d, r9d
0x1800113f5  cmp     rcx, 8
0x1800113f9  jb      short loc_1800113D8
0x1800113fb  add     r11b, 2
0x1800113ff  jmp     short loc_18001143A
0x180011401  movzx   eax, r11b
0x180011405  xor     edx, edx
0x180011407  add     rax, rax
0x18001140a  mov     r9d, [r8+rax*8+8]
0x18001140f  mov     rdi, [r8+rax*8]
0x180011413  test    r9, r9
0x180011416  jz      short loc_180011437
0x180011418  movzx   eax, byte ptr [rdi+rdx]
0x18001141c  inc     rdx
0x18001141f  add     eax, r10d
0x180011422  imul    ecx, eax, 401h
0x180011428  mov     r10d, ecx
0x18001142b  shr     r10d, 6
0x18001142f  xor     r10d, ecx
0x180011432  cmp     rdx, r9
0x180011435  jb      short loc_180011418
0x180011437  inc     r11b
0x18001143a  cmp     r11b, bl
0x18001143d  jb      short loc_180011401
0x18001143f  mov     rbx, [rsp+arg_0]
0x180011444  lea     eax, [r10+r10*8]
0x180011448  mov     rdi, [rsp+arg_8]
0x18001144d  mov     ecx, eax
0x18001144f  shr     ecx, 0Bh
0x180011452  xor     ecx, eax
0x180011454  imul    eax, ecx, 8001h
0x18001145a  retn
```
