# shfileWrite

- ea: `0x180014960`
- end: `0x18001499e`
- name: `shfileWrite`
- size: `62`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1800065c0`
- `0x1800067a0`
- `0x18000b87c`
- `0x18000c410`
- `0x18000ca4c`
- `0x180014468`
- `0x180014600`
- `0x1800149a4`

## callees

- `0x180014960`
- `0x180017170`

## import_xrefs

- `WINMM!mmioWrite` at `0x180014997`

## pseudocode

```c
LONG __fastcall shfileWrite(__int64 a1, char *a2, unsigned int a3)
{
  CFileStream *v3; // rax
  int v4; // eax
  unsigned int v6; // [rsp+30h] [rbp+8h] BYREF

  v3 = *(CFileStream **)(a1 + 16);
  if ( !v3 )
    return mmioWrite(*(HMMIO *)(a1 + 8), a2, a3);
  v6 = 0;
  v4 = CFileStream::Write(v3, (unsigned __int8 *)a2, a3, &v6);
  return v4 != 0 ? v6 : 0;
}

```

## disassembly

```asm
0x180014960  sub     rsp, 28h
0x180014964  mov     rax, [rcx+10h]
0x180014968  test    rax, rax
0x18001496b  jz      short loc_18001498F
0x18001496d  lea     r9, [rsp+28h+arg_0]; unsigned int *
0x180014972  mov     [rsp+28h+arg_0], 0
0x18001497a  mov     rcx, rax; this
0x18001497d  call    ?Write@CFileStream@@QEAAHPEAEKPEAK@Z; CFileStream::Write(uchar *,ulong,ulong *)
0x180014982  neg     eax
0x180014984  sbb     eax, eax
0x180014986  and     eax, [rsp+28h+arg_0]
0x18001498a  add     rsp, 28h
0x18001498e  retn
0x18001498f  mov     rcx, [rcx+8]
0x180014993  add     rsp, 28h
0x180014997  jmp     cs:__imp_mmioWrite
```
