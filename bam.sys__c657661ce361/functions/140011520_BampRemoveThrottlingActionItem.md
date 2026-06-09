# BampRemoveThrottlingActionItem

- ea: `0x140011520`
- end: `0x14001154d`
- name: `BampRemoveThrottlingActionItem`
- size: `45`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b2f0`
- `0x14000c18c`
- `0x140013c7c`

## callees

- `0x140011520`

## pseudocode

```c
_QWORD *__fastcall BampRemoveThrottlingActionItem(_QWORD *a1)
{
  __int64 v1; // rdx
  _QWORD *result; // rax

  v1 = *a1;
  if ( *(_QWORD **)(*a1 + 8LL) != a1 || (result = (_QWORD *)a1[1], (_QWORD *)*result != a1) )
    __fastfail(3u);
  *result = v1;
  *(_QWORD *)(v1 + 8) = result;
  *(_OWORD *)a1 = 0;
  a1[2] &= ~1uLL;
  return result;
}

```

## disassembly

```asm
0x140011520  mov     rdx, [rcx]
0x140011523  cmp     [rdx+8], rcx
0x140011527  jnz     short loc_140011546
0x140011529  mov     rax, [rcx+8]
0x14001152d  cmp     [rax], rcx
0x140011530  jnz     short loc_140011546
0x140011532  mov     [rax], rdx
0x140011535  xorps   xmm0, xmm0
0x140011538  mov     [rdx+8], rax
0x14001153c  movups  xmmword ptr [rcx], xmm0
0x14001153f  and     qword ptr [rcx+10h], 0FFFFFFFFFFFFFFFEh
0x140011544  retn
0x140011546  mov     ecx, 3
0x14001154b  int     29h; Win8: RtlFailFast(ecx)
```
