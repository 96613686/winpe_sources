# EapReclaimKeyEnumBuffer

- ea: `0x18000aae8`
- end: `0x18000ab12`
- name: `EapReclaimKeyEnumBuffer`
- size: `42`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180009070`
- `0x180009370`
- `0x180009940`
- `0x180009a88`
- `0x180009d38`

## callees

- `0x180002e30`
- `0x18000aae8`

## pseudocode

```c
BOOLEAN __fastcall EapReclaimKeyEnumBuffer(__int64 a1)
{
  void *v2; // rcx
  BOOLEAN result; // al

  v2 = *(void **)a1;
  if ( v2 )
  {
    result = EaLibFree(v2);
    *(_QWORD *)a1 = 0;
    *(_DWORD *)(a1 + 8) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000aae8  push    rbx
0x18000aaea  sub     rsp, 20h
0x18000aaee  mov     rbx, rcx
0x18000aaf1  mov     rcx, [rcx]
0x18000aaf4  test    rcx, rcx
0x18000aaf7  jz      short loc_18000AB0C
0x18000aaf9  call    EaLibFree
0x18000aafe  mov     qword ptr [rbx], 0
0x18000ab05  mov     dword ptr [rbx+8], 0
0x18000ab0c  add     rsp, 20h
0x18000ab10  pop     rbx
0x18000ab11  retn
```
