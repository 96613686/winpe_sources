# __security_check_cookie(x)

- ea: `0x408c05`
- end: `0x408c13`
- name: `@__security_check_cookie@4`
- size: `14`
- prototype: `void __fastcall(uintptr_t StackCookie)`
- caller_count: `78`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4015dc`
- `0x401684`
- `0x401786`
- `0x40187b`
- `0x401938`
- `0x401a73`
- `0x401d96`
- `0x401e78`
- `0x401f55`
- `0x401ff9`
- `0x40207e`
- `0x40231f`
- `0x4024fb`
- `0x4025d9`
- `0x4026c9`
- `0x4027a1`
- `0x402829`
- `0x4028da`
- `0x4029d6`
- `0x402b8e`
- `0x402de7`
- `0x402eb5`
- `0x402f53`
- `0x403062`
- `0x403116`
- `0x403e11`
- `0x403e90`
- `0x403fc4`
- `0x4040f0`
- `0x404212`
- `0x404418`
- `0x40465a`
- `0x404873`
- `0x40498a`
- `0x404bd8`
- `0x404c5f`
- `0x404d09`
- `0x4050c0`
- `0x4052f1`
- `0x405452`
- `0x405a90`
- `0x405d21`
- `0x405df6`
- `0x405ecb`
- `0x405ff0`
- `0x4061f3`
- `0x4062cf`
- `0x4063fc`
- `0x407f09`
- `0x408d40`

## callees

- `0x408c05`
- `0x408c3b`

## pseudocode

```c
void __fastcall __security_check_cookie(uintptr_t StackCookie)
{
  if ( StackCookie != __security_cookie )
    __report_gsfailure();
}

```

## disassembly

```asm
0x408c05  cmp     ecx, ___security_cookie
0x408c0b  jnz     short loc_408C0E
0x408c0d  retn
0x408c0e  jmp     ___report_gsfailure
```
