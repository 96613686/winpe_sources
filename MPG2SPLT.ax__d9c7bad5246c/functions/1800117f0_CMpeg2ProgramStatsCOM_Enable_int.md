# CMpeg2ProgramStatsCOM::Enable(int *)

- ea: `0x1800117f0`
- end: `0x180011807`
- name: `?Enable@CMpeg2ProgramStatsCOM@@UEAAJPEAH@Z`
- size: `23`
- prototype: `__int64 __fastcall(CMpeg2ProgramStatsCOM *__hidden this, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800117f0`
- `0x180018728`

## pseudocode

```c
__int64 __fastcall CMpeg2ProgramStatsCOM::Enable(CMpeg2ProgramStatsCOM *this, int *a2)
{
  if ( a2 )
    return EnableStats(L"SOFTWARE\\Microsoft\\MPEG2Demultiplexer\\Program", a2);
  else
    return 2147500035LL;
}

```

## disassembly

```asm
0x1800117f0  test    rdx, rdx
0x1800117f3  jnz     short loc_1800117FB
0x1800117f5  mov     eax, 80004003h
0x1800117fa  retn
0x1800117fb  lea     rcx, aSoftwareMicros; "SOFTWARE\\Microsoft\\MPEG2Demultiplexer"...
0x180011802  jmp     ?EnableStats@@YAJPEBGPEAH@Z; EnableStats(ushort const *,int *)
```
