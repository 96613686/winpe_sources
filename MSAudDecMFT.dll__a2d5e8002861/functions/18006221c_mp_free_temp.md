# mp_free_temp

- ea: `0x18006221c`
- end: `0x180062230`
- name: `mp_free_temp`
- size: `20`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x18005efa4`
- `0x18005f25c`
- `0x18005f670`
- `0x18005fa94`
- `0x180060418`
- `0x1800612f8`
- `0x1800622f8`
- `0x1800626cc`
- `0x180063190`
- `0x180063d00`

## callees

- `0x18006221c`
- `0x180063f98`

## pseudocode

```c
__int64 __fastcall mp_free_temp(void *a1)
{
  __int64 result; // rax

  if ( a1 )
    return bignum_free(a1);
  return result;
}

```

## disassembly

```asm
0x18006221c  sub     rsp, 28h
0x180062220  test    rcx, rcx
0x180062223  jz      short loc_18006222A
0x180062225  call    bignum_free
0x18006222a  add     rsp, 28h
0x18006222e  retn
```
