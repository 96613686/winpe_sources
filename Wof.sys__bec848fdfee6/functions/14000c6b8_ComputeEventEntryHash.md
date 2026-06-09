# ComputeEventEntryHash

- ea: `0x14000c6b8`
- end: `0x14000c74b`
- name: `ComputeEventEntryHash`
- size: `147`
- prototype: `__int64 __fastcall(char, unsigned __int8, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140009d88`

## callees

- `0x140009bd8`
- `0x14000c6b8`

## pseudocode

```c
__int64 __fastcall ComputeEventEntryHash(char a1, unsigned __int8 a2, __int64 a3)
{
  unsigned __int64 v5; // rcx
  unsigned int v7; // r10d
  int v8; // eax
  unsigned __int8 v9; // bl
  unsigned int v11; // [rsp+30h] [rbp+8h] BYREF

  v5 = 0;
  v7 = 0;
  do
  {
    v8 = *(unsigned __int8 *)(a3 + v5++ + 16);
    v7 = (1025 * (v7 + v8)) ^ ((1025 * (v7 + v8)) >> 6);
  }
  while ( v5 < 8 );
  v9 = a1 + 2;
  v11 = v7;
  if ( v9 < a2 )
  {
    do
    {
      RunningHash(&v11, *(_QWORD *)(a3 + 16LL * v9), *(unsigned int *)(a3 + 16LL * v9 + 8));
      ++v9;
    }
    while ( v9 < a2 );
    v7 = v11;
  }
  return 32769 * ((9 * v7) ^ ((9 * v7) >> 11));
}

```

## disassembly

```asm
0x14000c6b8  mov     [rsp+arg_8], rbx
0x14000c6bd  mov     [rsp+arg_10], rsi
0x14000c6c2  push    rdi
0x14000c6c3  sub     rsp, 20h
0x14000c6c7  mov     bl, cl
0x14000c6c9  mov     rdi, r8
0x14000c6cc  xor     ecx, ecx
0x14000c6ce  mov     sil, dl
0x14000c6d1  xor     r10d, r10d
0x14000c6d4  movzx   eax, byte ptr [r8+rcx+10h]
0x14000c6da  inc     rcx
0x14000c6dd  add     eax, r10d
0x14000c6e0  imul    r9d, eax, 401h
0x14000c6e7  mov     r10d, r9d
0x14000c6ea  shr     r10d, 6
0x14000c6ee  xor     r10d, r9d
0x14000c6f1  cmp     rcx, 8
0x14000c6f5  jb      short loc_14000C6D4
0x14000c6f7  add     bl, 2
0x14000c6fa  mov     [rsp+28h+arg_0], r10d
0x14000c6ff  cmp     bl, sil
0x14000c702  jnb     short loc_14000C729
0x14000c704  movzx   edx, bl
0x14000c707  lea     rcx, [rsp+28h+arg_0]
0x14000c70c  add     rdx, rdx
0x14000c70f  mov     r8d, [rdi+rdx*8+8]
0x14000c714  mov     rdx, [rdi+rdx*8]
0x14000c718  call    RunningHash
0x14000c71d  inc     bl
0x14000c71f  cmp     bl, sil
0x14000c722  jb      short loc_14000C704
0x14000c724  mov     r10d, [rsp+28h+arg_0]
0x14000c729  mov     rbx, [rsp+28h+arg_8]
0x14000c72e  lea     eax, [r10+r10*8]
0x14000c732  mov     rsi, [rsp+28h+arg_10]
0x14000c737  mov     ecx, eax
0x14000c739  shr     ecx, 0Bh
0x14000c73c  xor     ecx, eax
0x14000c73e  imul    eax, ecx, 8001h
0x14000c744  add     rsp, 20h
0x14000c748  pop     rdi
0x14000c749  retn
```
