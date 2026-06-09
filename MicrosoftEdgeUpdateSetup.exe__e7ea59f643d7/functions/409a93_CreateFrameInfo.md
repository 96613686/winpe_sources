# __CreateFrameInfo

- ea: `0x409a93`
- end: `0x409ab7`
- name: `__CreateFrameInfo`
- size: `36`
- prototype: `_DWORD *__cdecl(_DWORD *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x40ab0d`

## callees

- `0x40943c`

## pseudocode

```c
_DWORD *__cdecl _CreateFrameInfo(_DWORD *a1, int a2)
{
  *a1 = a2;
  a1[1] = *(_DWORD *)(__vcrt_getptd() + 36);
  *(_DWORD *)(__vcrt_getptd() + 36) = a1;
  return a1;
}

```

## disassembly

```asm
0x409a93  push    ebp
0x409a94  mov     ebp, esp
0x409a96  mov     ecx, [ebp+arg_4]
0x409a99  push    esi
0x409a9a  mov     esi, [ebp+arg_0]
0x409a9d  mov     [esi], ecx
0x409a9f  call    ___vcrt_getptd
0x409aa4  mov     ecx, [eax+24h]
0x409aa7  mov     [esi+4], ecx
0x409aaa  call    ___vcrt_getptd
0x409aaf  mov     [eax+24h], esi
0x409ab2  mov     eax, esi
0x409ab4  pop     esi
0x409ab5  pop     ebp
0x409ab6  retn
```
