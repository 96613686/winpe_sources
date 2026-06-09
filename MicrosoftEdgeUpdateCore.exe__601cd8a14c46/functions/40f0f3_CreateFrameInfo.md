# __CreateFrameInfo

- ea: `0x40f0f3`
- end: `0x40f117`
- name: `__CreateFrameInfo`
- size: `36`
- prototype: `_DWORD *__cdecl(_DWORD *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x40fbed`

## callees

- `0x40e8fc`

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
0x40f0f3  push    ebp
0x40f0f4  mov     ebp, esp
0x40f0f6  mov     ecx, [ebp+arg_4]
0x40f0f9  push    esi
0x40f0fa  mov     esi, [ebp+arg_0]
0x40f0fd  mov     [esi], ecx
0x40f0ff  call    ___vcrt_getptd
0x40f104  mov     ecx, [eax+24h]
0x40f107  mov     [esi+4], ecx
0x40f10a  call    ___vcrt_getptd
0x40f10f  mov     [eax+24h], esi
0x40f112  mov     eax, esi
0x40f114  pop     esi
0x40f115  pop     ebp
0x40f116  retn
```
