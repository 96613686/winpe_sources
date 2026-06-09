# BfsFinalHash

- ea: `0x1400017b0`
- end: `0x1400017c9`
- name: `BfsFinalHash`
- size: `25`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x140006db4`
- `0x140006eb0`
- `0x1400071d4`
- `0x1400073e0`
- `0x140009014`
- `0x1400092a4`
- `0x14000a64c`
- `0x14000b4c8`
- `0x14000b654`
- `0x14000c0f4`
- `0x14000ca5c`
- `0x14000d9dc`

## callees

- `0x1400017b0`

## pseudocode

```c
__int64 __fastcall BfsFinalHash(__int64 *a1)
{
  __int64 result; // rax

  result = *a1;
  if ( !*a1 )
  {
    *a1 = -1;
    return -1;
  }
  return result;
}

```

## disassembly

```asm
0x1400017b0  mov     rax, [rcx]
0x1400017b3  test    rax, rax
0x1400017b6  jz      short loc_1400017BA
0x1400017b8  retn
0x1400017ba  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x1400017c1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400017c8  retn
```
