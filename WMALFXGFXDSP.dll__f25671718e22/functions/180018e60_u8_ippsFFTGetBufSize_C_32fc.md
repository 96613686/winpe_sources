# u8_ippsFFTGetBufSize_C_32fc

- ea: `0x180018e60`
- end: `0x180018e74`
- name: `u8_ippsFFTGetBufSize_C_32fc`
- size: `20`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18001c9d0`
- `0x18001cbe0`
- `0x18001d830`
- `0x18001da40`
- `0x18001e5c0`
- `0x18001e7d0`
- `0x180059558`
- `0x18005bc88`
- `0x18005e7ec`

## callees

- `0x180018e60`

## pseudocode

```c
__int64 __fastcall u8_ippsFFTGetBufSize_C_32fc(__int64 a1, int *a2)
{
  int v2; // r8d
  int v3; // eax

  v2 = *(_DWORD *)(a1 + 24);
  v3 = 0;
  if ( v2 > 0 )
    v3 = v2 + 32;
  *a2 = v3;
  return 0;
}

```

## disassembly

```asm
0x180018e60  mov     r8d, [rcx+18h]
0x180018e64  xor     eax, eax
0x180018e66  test    r8d, r8d
0x180018e69  jle     short loc_180018E6F
0x180018e6b  lea     eax, [r8+20h]
0x180018e6f  mov     [rdx], eax
0x180018e71  xor     eax, eax
0x180018e73  retn
```
