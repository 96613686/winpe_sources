# BaseSrvGetBatRecord

- ea: `0x180006a10`
- end: `0x180006a2b`
- name: `BaseSrvGetBatRecord`
- size: `27`
- prototype: `_QWORD *__fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800069a0`
- `0x18000a960`

## callees

- `0x180006a10`

## pseudocode

```c
_QWORD *__fastcall BaseSrvGetBatRecord(__int64 a1)
{
  _QWORD *result; // rax

  result = (_QWORD *)BatRecordHead;
  if ( BatRecordHead )
  {
    do
    {
      if ( *result == a1 )
        break;
      result = (_QWORD *)result[2];
    }
    while ( result );
  }
  return result;
}

```

## disassembly

```asm
0x180006a10  mov     rax, cs:BatRecordHead
0x180006a17  test    rax, rax
0x180006a1a  jz      short locret_180006A2A
0x180006a1c  cmp     [rax], rcx
0x180006a1f  jz      short locret_180006A2A
0x180006a21  mov     rax, [rax+10h]
0x180006a25  test    rax, rax
0x180006a28  jnz     short loc_180006A1C
0x180006a2a  retn
```
