# DiagHubCommon::DebugStringLogWriter::Write(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140009ee0`
- end: `0x140009ef4`
- name: `?Write@DebugStringLogWriter@DiagHubCommon@@UEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `20`
- prototype: `void __fastcall(__int64, const WCHAR *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140009ee0`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x140009eed`

## pseudocode

```c
void __fastcall DiagHubCommon::DebugStringLogWriter::Write(__int64 a1, const WCHAR *a2)
{
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const WCHAR **)a2;
  OutputDebugStringW(a2);
}

```

## disassembly

```asm
0x140009ee0  cmp     qword ptr [rdx+18h], 7
0x140009ee5  jbe     short loc_140009EEA
0x140009ee7  mov     rdx, [rdx]
0x140009eea  mov     rcx, rdx
0x140009eed  jmp     cs:__imp_OutputDebugStringW
```
