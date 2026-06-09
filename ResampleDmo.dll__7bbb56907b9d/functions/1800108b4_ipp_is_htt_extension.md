# ipp_is_htt_extension

- ea: `0x1800108b4`
- end: `0x1800108d9`
- name: `ipp_is_htt_extension`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800108b4`

## pseudocode

```c
bool ipp_is_htt_extension()
{
  _RAX = 1;
  __asm { cpuid }
  if ( (_RDX & 0x10000000) == 0 )
    BYTE2(_RBX) = 0;
  return BYTE2(_RBX) > 1u;
}

```

## disassembly

```asm
0x1800108b4  push    rbx
0x1800108b5  mov     rax, 1
0x1800108bc  cpuid
0x1800108be  xor     rax, rax
0x1800108c1  test    rdx, 10000000h
0x1800108c8  jnz     short loc_1800108CD
0x1800108ca  mov     rbx, rax
0x1800108cd  shr     rbx, 10h
0x1800108d1  cmp     bl, 1
0x1800108d4  setnbe  al
0x1800108d7  pop     rbx
0x1800108d8  retn
```
