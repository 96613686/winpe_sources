# std::optional<std::filesystem::path>::~optional<std::filesystem::path>(void)

- ea: `0x140008850`
- end: `0x140008864`
- name: `??1?$optional@Vpath@filesystem@std@@@std@@QEAA@XZ`
- size: `20`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ae98`
- `0x14000af9a`
- `0x14000afac`

## callees

- `0x1400087e4`
- `0x140008850`

## pseudocode

```c
__int64 __fastcall std::optional<std::filesystem::path>::~optional<std::filesystem::path>(__int64 a1)
{
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 32) )
    return std::wstring::~wstring((char **)a1);
  return result;
}

```

## disassembly

```asm
0x140008850  sub     rsp, 28h
0x140008854  cmp     byte ptr [rcx+20h], 0
0x140008858  jz      short loc_14000885F
0x14000885a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000885f  add     rsp, 28h
0x140008863  retn
```
