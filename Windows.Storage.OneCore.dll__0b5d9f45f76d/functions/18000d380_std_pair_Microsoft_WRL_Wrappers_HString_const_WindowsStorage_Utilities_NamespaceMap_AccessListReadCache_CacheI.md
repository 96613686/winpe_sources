# std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>>::~pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>>(void)

- ea: `0x18000d380`
- end: `0x18000d3a8`
- name: `??1?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@QEAA@XZ`
- size: `40`
- prototype: `HRESULT __fastcall(HSTRING *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ba20`
- `0x18000d258`

## callees

- `0x18000d114`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d395`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d395`

## pseudocode

```c
HRESULT __fastcall std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>>::~pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>>(
        HSTRING *a1)
{
  HRESULT result; // eax

  WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>::~NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>((__int64)(a1 + 1));
  result = WindowsDeleteString(*a1);
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x18000d380  push    rbx
0x18000d382  sub     rsp, 20h
0x18000d386  mov     rbx, rcx
0x18000d389  add     rcx, 8
0x18000d38d  call    ??1?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>::~NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>(void)
0x18000d392  mov     rcx, [rbx]; string
0x18000d395  call    cs:__imp_WindowsDeleteString
0x18000d39b  mov     qword ptr [rbx], 0
0x18000d3a2  add     rsp, 20h
0x18000d3a6  pop     rbx
0x18000d3a7  retn
```
