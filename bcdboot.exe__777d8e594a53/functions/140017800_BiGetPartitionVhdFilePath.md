# BiGetPartitionVhdFilePath

- ea: `0x140017800`
- end: `0x140017829`
- name: `BiGetPartitionVhdFilePath`
- size: `41`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140015cd8`
- `0x140016784`
- `0x140017320`
- `0x1400211b0`

## callees

- `0x140017830`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140017814`
- `ntdll!RtlInitUnicodeString` at `0x140017814`

## pseudocode

```c
__int64 __fastcall BiGetPartitionVhdFilePath(PCWSTR SourceString)
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  return BiGetPartitionVhdFilePathFromUnicodeString(&DestinationString);
}

```

## disassembly

```asm
0x140017800  sub     rsp, 38h
0x140017804  xorps   xmm0, xmm0
0x140017807  mov     rdx, rcx; SourceString
0x14001780a  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x14001780f  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x140017814  call    cs:__imp_RtlInitUnicodeString
0x14001781a  lea     rcx, [rsp+38h+DestinationString]
0x14001781f  call    BiGetPartitionVhdFilePathFromUnicodeString
0x140017824  add     rsp, 38h
0x140017828  retn
```
