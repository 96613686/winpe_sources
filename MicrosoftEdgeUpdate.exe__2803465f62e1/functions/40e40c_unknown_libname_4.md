# unknown_libname_4

- ea: `0x40e40c`
- end: `0x40e42b`
- name: `unknown_libname_4`
- size: `31`
- prototype: `uintptr_t __cdecl(int)`
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x40e492`
- `0x40ed6d`
- `0x40eff6`
- `0x411ca5`

## pseudocode

```c
// Microsoft VisualC universal runtime
uintptr_t __cdecl unknown_libname_4(int a1)
{
  return __security_cookie ^ __ROR4__(a1, 32 - (__security_cookie & 0x1F));
}

```

## disassembly

```asm
0x40e40c  mov     edi, edi
0x40e40e  push    ebp
0x40e40f  mov     ebp, esp
0x40e411  mov     eax, ___security_cookie
0x40e416  and     eax, 1Fh
0x40e419  push    20h ; ' '
0x40e41b  pop     ecx
0x40e41c  sub     ecx, eax
0x40e41e  mov     eax, [ebp+arg_0]
0x40e421  ror     eax, cl
0x40e423  xor     eax, ___security_cookie
0x40e429  pop     ebp
0x40e42a  retn
```
