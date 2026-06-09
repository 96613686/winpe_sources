# CMpeg2TransportStatsCOM::Enable(int *)

- ea: `0x180011810`
- end: `0x180011827`
- name: `?Enable@CMpeg2TransportStatsCOM@@UEAAJPEAH@Z`
- size: `23`
- prototype: `__int64 __fastcall(CMpeg2TransportStatsCOM *__hidden this, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180011810`
- `0x180018728`

## pseudocode

```c
__int64 __fastcall CMpeg2TransportStatsCOM::Enable(CMpeg2TransportStatsCOM *this, int *a2)
{
  if ( a2 )
    return EnableStats(L"SOFTWARE\\Microsoft\\MPEG2Demultiplexer\\Transport", a2);
  else
    return 2147500035LL;
}

```

## disassembly

```asm
0x180011810  test    rdx, rdx
0x180011813  jnz     short loc_18001181B
0x180011815  mov     eax, 80004003h
0x18001181a  retn
0x18001181b  lea     rcx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\MPEG2Demultiplexer"...
0x180011822  jmp     ?EnableStats@@YAJPEBGPEAH@Z; EnableStats(ushort const *,int *)
```
