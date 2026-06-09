# j_av_sha_update

- ea: `0x18003f070`
- end: `0x18003f075`
- name: `j_av_sha_update`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18004fde0`

## pseudocode

```c
// attributes: thunk
char __fastcall j_av_sha_update(__int64 a1, __int64 a2, unsigned __int64 a3)
{
  return av_sha_update(a1, a2, a3);
}

```

## disassembly

```asm
0x18003f070  jmp     av_sha_update
```
