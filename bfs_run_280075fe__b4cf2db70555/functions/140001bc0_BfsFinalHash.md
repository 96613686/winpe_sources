# BfsFinalHash

- ea: `0x140001bc0`
- end: `0x140001bd9`
- name: `BfsFinalHash`
- size: `25`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x140006c24`
- `0x140006d20`
- `0x140007044`
- `0x140007250`
- `0x140008e84`
- `0x140009114`
- `0x14000a4bc`
- `0x14000b338`
- `0x14000b4c4`
- `0x14000bf64`
- `0x14000c8cc`
- `0x14000d848`

## callees

- `0x140001bc0`

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
0x140001bc0  mov     rax, [rcx]
0x140001bc3  test    rax, rax
0x140001bc6  jz      short loc_140001BCA
0x140001bc8  retn
0x140001bca  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x140001bd1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140001bd8  retn
```
