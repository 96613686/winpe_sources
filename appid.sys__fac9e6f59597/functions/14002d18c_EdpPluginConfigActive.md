# EdpPluginConfigActive

- ea: `0x14002d18c`
- end: `0x14002d1b6`
- name: `EdpPluginConfigActive`
- size: `42`
- prototype: `bool __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14002c9c4`
- `0x14002cc34`
- `0x14002cd1c`

## callees

- `0x14002d170`
- `0x14002d18c`

## pseudocode

```c
bool __fastcall EdpPluginConfigActive(__int64 a1)
{
  char v1; // dl
  int v2; // r8d
  int v3; // r9d

  if ( EdpIsPluginConfigPresent(a1) )
  {
    if ( v3 )
      return 1;
    if ( !v1 )
      return v2 != 0;
  }
  return 0;
}

```

## disassembly

```asm
0x14002d18c  sub     rsp, 28h
0x14002d190  call    EdpIsPluginConfigPresent
0x14002d195  test    al, al
0x14002d197  jz      short loc_14002D1AE
0x14002d199  test    r9d, r9d
0x14002d19c  jnz     short loc_14002D1AA
0x14002d19e  test    dl, dl
0x14002d1a0  jnz     short loc_14002D1AE
0x14002d1a2  test    r8d, r8d
0x14002d1a5  setnz   al
0x14002d1a8  jmp     short loc_14002D1B0
0x14002d1aa  mov     al, 1
0x14002d1ac  jmp     short loc_14002D1B0
0x14002d1ae  xor     al, al
0x14002d1b0  add     rsp, 28h
0x14002d1b4  retn
```
