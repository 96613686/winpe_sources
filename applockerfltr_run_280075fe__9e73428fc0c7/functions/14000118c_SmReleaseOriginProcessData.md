# SmReleaseOriginProcessData

- ea: `0x14000118c`
- end: `0x1400011a7`
- name: `SmReleaseOriginProcessData`
- size: `27`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140007030`
- `0x140007410`

## callees

- `0x14000118c`
- `0x140001860`

## pseudocode

```c
__int64 (*SmReleaseOriginProcessData())(void)
{
  __int64 (*result)(void); // rax

  result = qword_140004098;
  if ( qword_140004098 )
    return (__int64 (*)(void))qword_140004098();
  return result;
}

```

## disassembly

```asm
0x14000118c  sub     rsp, 28h
0x140001190  mov     rax, cs:qword_140004098
0x140001197  test    rax, rax
0x14000119a  jz      short loc_1400011A1
0x14000119c  call    _guard_dispatch_icall
0x1400011a1  add     rsp, 28h
0x1400011a5  retn
```
