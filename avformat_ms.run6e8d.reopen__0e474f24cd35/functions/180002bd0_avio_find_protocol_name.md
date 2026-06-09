# avio_find_protocol_name

- ea: `0x180002bd0`
- end: `0x180002beb`
- name: `avio_find_protocol_name`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002bd0`
- `0x180003c8c`

## pseudocode

```c
__int64 __fastcall avio_find_protocol_name(char *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = sub_180003C8C(a1);
  result = 0;
  if ( v1 )
    return *(_QWORD *)v1;
  return result;
}

```

## disassembly

```asm
0x180002bd0  sub     rsp, 28h
0x180002bd4  call    sub_180003C8C
0x180002bd9  mov     rcx, rax
0x180002bdc  xor     eax, eax
0x180002bde  test    rcx, rcx
0x180002be1  jz      short loc_180002BE6
0x180002be3  mov     rax, [rcx]
0x180002be6  add     rsp, 28h
0x180002bea  retn
```
