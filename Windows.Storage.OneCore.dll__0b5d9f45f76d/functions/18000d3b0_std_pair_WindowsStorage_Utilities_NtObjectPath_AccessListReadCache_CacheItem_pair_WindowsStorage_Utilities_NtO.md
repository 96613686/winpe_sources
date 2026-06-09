# std::pair<WindowsStorage::Utilities::NtObjectPath,AccessListReadCache::CacheItem>::~pair<WindowsStorage::Utilities::NtObjectPath,AccessListReadCache::CacheItem>(void)

- ea: `0x18000d3b0`
- end: `0x18000d3e1`
- name: `??1?$pair@VNtObjectPath@Utilities@WindowsStorage@@UCacheItem@AccessListReadCache@@@std@@QEAA@XZ`
- size: `49`
- prototype: `HRESULT __fastcall(HSTRING *)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000ba4c`
- `0x18000d288`
- `0x1800102cc`
- `0x180023be3`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d3bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d3ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d3bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d3ce`

## pseudocode

```c
HRESULT __fastcall std::pair<WindowsStorage::Utilities::NtObjectPath,AccessListReadCache::CacheItem>::~pair<WindowsStorage::Utilities::NtObjectPath,AccessListReadCache::CacheItem>(
        HSTRING *a1)
{
  HRESULT result; // eax

  WindowsDeleteString(a1[1]);
  a1[1] = 0;
  result = WindowsDeleteString(*a1);
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x18000d3b0  push    rbx
0x18000d3b2  sub     rsp, 20h
0x18000d3b6  mov     rbx, rcx
0x18000d3b9  mov     rcx, [rcx+8]; string
0x18000d3bd  call    cs:__imp_WindowsDeleteString
0x18000d3c3  mov     qword ptr [rbx+8], 0
0x18000d3cb  mov     rcx, [rbx]; string
0x18000d3ce  call    cs:__imp_WindowsDeleteString
0x18000d3d4  mov     qword ptr [rbx], 0
0x18000d3db  add     rsp, 20h
0x18000d3df  pop     rbx
0x18000d3e0  retn
```
