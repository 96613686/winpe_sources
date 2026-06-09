# shfileRead

- ea: `0x180014880`
- end: `0x1800148be`
- name: `shfileRead`
- size: `62`
- prototype: `LONG __fastcall(__int64, char *, unsigned int)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x180003f50`
- `0x180005734`
- `0x1800059c0`
- `0x180006320`
- `0x18000a060`
- `0x18000b25c`
- `0x18000b368`
- `0x18000d070`
- `0x18000d24c`
- `0x180014694`

## callees

- `0x180014880`
- `0x180016a94`

## import_xrefs

- `WINMM!mmioRead` at `0x1800148b7`

## pseudocode

```c
LONG __fastcall shfileRead(__int64 a1, char *a2, unsigned int a3)
{
  CFileStream *v3; // rax
  int v4; // eax
  unsigned int v6; // [rsp+30h] [rbp+8h] BYREF

  v3 = *(CFileStream **)(a1 + 16);
  if ( !v3 )
    return mmioRead(*(HMMIO *)(a1 + 8), a2, a3);
  v6 = 0;
  v4 = CFileStream::Read(v3, (unsigned __int8 *)a2, a3, &v6);
  return v4 != 0 ? v6 : 0;
}

```

## disassembly

```asm
0x180014880  sub     rsp, 28h
0x180014884  mov     rax, [rcx+10h]
0x180014888  test    rax, rax
0x18001488b  jz      short loc_1800148AF
0x18001488d  lea     r9, [rsp+28h+arg_0]; unsigned int *
0x180014892  mov     [rsp+28h+arg_0], 0
0x18001489a  mov     rcx, rax; this
0x18001489d  call    ?Read@CFileStream@@QEAAHPEAEKPEAK@Z; CFileStream::Read(uchar *,ulong,ulong *)
0x1800148a2  neg     eax
0x1800148a4  sbb     eax, eax
0x1800148a6  and     eax, [rsp+28h+arg_0]
0x1800148aa  add     rsp, 28h
0x1800148ae  retn
0x1800148af  mov     rcx, [rcx+8]
0x1800148b3  add     rsp, 28h
0x1800148b7  jmp     cs:__imp_mmioRead
```
