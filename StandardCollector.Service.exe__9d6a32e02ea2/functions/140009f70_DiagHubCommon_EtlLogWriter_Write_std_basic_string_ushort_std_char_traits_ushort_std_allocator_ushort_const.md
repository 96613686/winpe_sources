# DiagHubCommon::EtlLogWriter::Write(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140009f70`
- end: `0x140009f8d`
- name: `?Write@EtlLogWriter@DiagHubCommon@@UEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `29`
- prototype: `ULONG __fastcall(__int64, const WCHAR *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140009f70`

## import_xrefs

- `ADVAPI32!EventWriteString` at `0x140009f86`

## pseudocode

```c
ULONG __fastcall DiagHubCommon::EtlLogWriter::Write(__int64 a1, const WCHAR *a2)
{
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const WCHAR **)a2;
  return EventWriteString(*(_QWORD *)(a1 + 8), 0, 0, a2);
}

```

## disassembly

```asm
0x140009f70  cmp     qword ptr [rdx+18h], 7
0x140009f75  jbe     short loc_140009F7A
0x140009f77  mov     rdx, [rdx]
0x140009f7a  mov     rcx, [rcx+8]
0x140009f7e  mov     r9, rdx
0x140009f81  xor     edx, edx
0x140009f83  xor     r8d, r8d
0x140009f86  jmp     cs:__imp_EventWriteString
```
