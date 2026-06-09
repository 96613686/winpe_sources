# u8_ippsFFTGetBufSize_C_32fc

- ea: `0x18000d700`
- end: `0x18000d714`
- name: `u8_ippsFFTGetBufSize_C_32fc`
- size: `20`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180047f10`
- `0x180048120`
- `0x180048d70`
- `0x180048f80`
- `0x180049b00`
- `0x180049d10`
- `0x18005372c`
- `0x180055e5c`
- `0x1800589cc`

## callees

- `0x18000d700`

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
0x18000d700  mov     r8d, [rcx+18h]
0x18000d704  xor     eax, eax
0x18000d706  test    r8d, r8d
0x18000d709  jle     short loc_18000D70F
0x18000d70b  lea     eax, [r8+20h]
0x18000d70f  mov     [rdx], eax
0x18000d711  xor     eax, eax
0x18000d713  retn
```
