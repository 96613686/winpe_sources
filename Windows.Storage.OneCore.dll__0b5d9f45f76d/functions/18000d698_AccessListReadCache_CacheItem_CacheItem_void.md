# AccessListReadCache::CacheItem::~CacheItem(void)

- ea: `0x18000d698`
- end: `0x18000d6b7`
- name: `??1CacheItem@AccessListReadCache@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800236f0`
- `0x180023a74`
- `0x180023a86`
- `0x180023bd1`
- `0x180023c3e`
- `0x180023f8f`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d6a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d6a4`

## pseudocode

```c
void __fastcall AccessListReadCache::CacheItem::~CacheItem(HSTRING *this)
{
  WindowsDeleteString(*this);
  *this = 0;
}

```

## disassembly

```asm
0x18000d698  push    rbx
0x18000d69a  sub     rsp, 20h
0x18000d69e  mov     rbx, rcx
0x18000d6a1  mov     rcx, [rcx]; string
0x18000d6a4  call    cs:__imp_WindowsDeleteString
0x18000d6aa  mov     qword ptr [rbx], 0
0x18000d6b1  add     rsp, 20h
0x18000d6b5  pop     rbx
0x18000d6b6  retn
```
