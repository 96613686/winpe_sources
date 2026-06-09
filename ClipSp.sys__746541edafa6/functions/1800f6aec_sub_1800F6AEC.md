# sub_1800F6AEC

- ea: `0x1800f6aec`
- end: `0x1800f6afe`
- name: `sub_1800F6AEC`
- size: `18`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800edc00`
- `0x1800edf50`
- `0x1800ee1c0`
- `0x1800ee3e0`
- `0x1800efb80`
- `0x1800efea0`
- `0x1800f0340`

## callees

- `0x1800f6b4c`

## pseudocode

```c
void __fastcall sub_1800F6AEC()
{
  char v0; // zf
  char v1; // sf
  char v2; // of

  if ( !(v1 ^ v2 | v0) )
    JUMPOUT(0x1800F6AF8LL);
  JUMPOUT(0x1800F6B4FLL);
}

```

## disassembly

```asm
0x1800f6aec  xchg    eax, esp
0x1800f6aed  xchg    eax, ecx
0x1800f6aee  cmp     [rcx], eax
0x1800f6af0  jle     short near ptr byte_1800F6B4F
0x1800f6af2  xor     al, 0FEh
0x1800f6af4  fdiv    qword ptr [rsi-4Dh]
0x1800f6af7  lodsd
```
