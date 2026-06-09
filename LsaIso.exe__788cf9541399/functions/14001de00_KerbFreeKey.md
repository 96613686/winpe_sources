# KerbFreeKey

- ea: `0x14001de00`
- end: `0x14001de45`
- name: `KerbFreeKey`
- size: `69`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1400158c0`
- `0x140016140`
- `0x1400164a0`
- `0x1400170e0`
- `0x1400175c0`
- `0x140017e00`
- `0x140019210`
- `0x140019b50`
- `0x14001ab10`
- `0x14001ea54`

## callees

- `0x140006720`
- `0x14001de00`

## pseudocode

```c
__int64 __fastcall KerbFreeKey(__int64 a1)
{
  _BYTE *v1; // rax
  __int64 i; // rcx
  __int64 result; // rax

  v1 = *(_BYTE **)(a1 + 24);
  if ( v1 )
  {
    for ( i = *(unsigned int *)(a1 + 16); i; --i )
      *v1++ = 0;
    SafeAllocaFreeToHeap(*(void **)(a1 + 24));
  }
  result = 0;
  *(_OWORD *)a1 = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  return result;
}

```

## disassembly

```asm
0x14001de00  push    rbx
0x14001de02  sub     rsp, 20h
0x14001de06  mov     rax, [rcx+18h]
0x14001de0a  mov     rbx, rcx
0x14001de0d  test    rax, rax
0x14001de10  jz      short loc_14001DE2F
0x14001de12  mov     ecx, [rcx+10h]
0x14001de15  test    rcx, rcx
0x14001de18  jz      short loc_14001DE26
0x14001de1a  mov     byte ptr [rax], 0
0x14001de1d  inc     rax
0x14001de20  sub     rcx, 1
0x14001de24  jnz     short loc_14001DE1A
0x14001de26  mov     rcx, [rbx+18h]; void *
0x14001de2a  call    SafeAllocaFreeToHeap
0x14001de2f  xorps   xmm0, xmm0
0x14001de32  xor     eax, eax
0x14001de34  movups  xmmword ptr [rbx], xmm0
0x14001de37  movups  xmmword ptr [rbx+10h], xmm0
0x14001de3b  mov     [rbx+20h], rax
0x14001de3f  add     rsp, 20h
0x14001de43  pop     rbx
0x14001de44  retn
```
