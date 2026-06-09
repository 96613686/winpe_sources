# PathIsVolumeGUIDWorker(ushort const *)

- ea: `0x40bb42`
- end: `0x40bb6b`
- name: `?PathIsVolumeGUIDWorker@@YG_NPBG@Z`
- size: `41`
- prototype: `bool __stdcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x40b65c`
- `0x40b6d3`
- `0x40b825`

## callees

- `0x40ba88`
- `0x40bad8`
- `0x40bb42`

## pseudocode

```c

```

## disassembly

```asm
0x40bb42  mov     edi, edi
0x40bb44  push    esi; unsigned __int16 *
0x40bb45  push    0Ah; unsigned __int16 *
0x40bb47  mov     edx, offset aVolume; "\\\\?\\Volume"
0x40bb4c  mov     esi, ecx
0x40bb4e  call    ?StrIsEqualCaseInsensitive@@YG_NPBG0H@Z; StrIsEqualCaseInsensitive(ushort const *,ushort const *,int)
0x40bb53  test    al, al
0x40bb55  jz      short loc_40BB67
0x40bb57  lea     ecx, [esi+14h]
0x40bb5a  call    ?StringIsGUIDWorker@@YG_NPBG@Z; StringIsGUIDWorker(ushort const *)
0x40bb5f  test    al, al
0x40bb61  jz      short loc_40BB67
0x40bb63  mov     al, 1
0x40bb65  pop     esi
0x40bb66  retn
0x40bb67  xor     al, al
0x40bb69  pop     esi
0x40bb6a  retn
```
