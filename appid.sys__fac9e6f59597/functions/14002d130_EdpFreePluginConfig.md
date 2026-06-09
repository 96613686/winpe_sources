# EdpFreePluginConfig

- ea: `0x14002d130`
- end: `0x14002d167`
- name: `EdpFreePluginConfig`
- size: `55`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14002c090`
- `0x14002cc34`

## callees

- `0x14002d130`
- `0x1400328b0`

## pseudocode

```c
__int64 __fastcall EdpFreePluginConfig(__int64 a1)
{
  __int64 result; // rax

  if ( *(_BYTE *)a1 )
  {
    AiFree(*(void **)(a1 + 16));
    AiFree(*(void **)(a1 + 24));
    result = 0;
    *(_OWORD *)a1 = 0;
    *(_OWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 32) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14002d130  push    rbx
0x14002d132  sub     rsp, 20h
0x14002d136  cmp     byte ptr [rcx], 0
0x14002d139  mov     rbx, rcx
0x14002d13c  jz      short loc_14002D160
0x14002d13e  mov     rcx, [rcx+10h]
0x14002d142  call    AiFree
0x14002d147  mov     rcx, [rbx+18h]
0x14002d14b  call    AiFree
0x14002d150  xorps   xmm0, xmm0
0x14002d153  xor     eax, eax
0x14002d155  movups  xmmword ptr [rbx], xmm0
0x14002d158  movups  xmmword ptr [rbx+10h], xmm0
0x14002d15c  mov     [rbx+20h], rax
0x14002d160  add     rsp, 20h
0x14002d164  pop     rbx
0x14002d165  retn
```
