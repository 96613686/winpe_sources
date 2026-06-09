# j_av_sha512_update

- ea: `0x18003f050`
- end: `0x18003f055`
- name: `j_av_sha512_update`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180050480`

## pseudocode

```c
// attributes: thunk
char __fastcall j_av_sha512_update(__int64 a1, __int64 a2, unsigned __int64 a3)
{
  return av_sha512_update(a1, a2, a3);
}

```

## disassembly

```asm
0x18003f050  jmp     av_sha512_update
```
