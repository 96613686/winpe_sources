# BaseSrvGetBatRecord

- ea: `0x180006ca0`
- end: `0x180006cbb`
- name: `BaseSrvGetBatRecord`
- size: `27`
- prototype: `_QWORD *__fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006c30`
- `0x18000abe0`

## callees

- `0x180006ca0`

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
0x180006ca0  mov     rax, cs:BatRecordHead
0x180006ca7  test    rax, rax
0x180006caa  jz      short locret_180006CBA
0x180006cac  cmp     [rax], rcx
0x180006caf  jz      short locret_180006CBA
0x180006cb1  mov     rax, [rax+10h]
0x180006cb5  test    rax, rax
0x180006cb8  jnz     short loc_180006CAC
0x180006cba  retn
```
