# std::optional<std::filesystem::path>::~optional<std::filesystem::path>(void)

- ea: `0x180008f8c`
- end: `0x180008fa0`
- name: `??1?$optional@Vpath@filesystem@std@@@std@@QEAA@XZ`
- size: `20`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c2a6`
- `0x18000c3a8`
- `0x18000c3ba`

## callees

- `0x180008f20`
- `0x180008f8c`

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
0x180008f8c  sub     rsp, 28h
0x180008f90  cmp     byte ptr [rcx+20h], 0
0x180008f94  jz      short loc_180008F9B
0x180008f96  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008f9b  add     rsp, 28h
0x180008f9f  retn
```
