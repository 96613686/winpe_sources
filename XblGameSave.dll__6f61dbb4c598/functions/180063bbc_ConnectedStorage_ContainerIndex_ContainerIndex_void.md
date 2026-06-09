# ConnectedStorage::ContainerIndex::~ContainerIndex(void)

- ea: `0x180063bbc`
- end: `0x180063c2a`
- name: `??1ContainerIndex@ConnectedStorage@@QEAA@XZ`
- size: `110`
- prototype: `void __fastcall(ConnectedStorage::ContainerIndex *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180032348`

## callees

- `0x180012278`
- `0x18001c090`
- `0x180029d74`
- `0x1800313e4`
- `0x18005b02c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180063c0e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180063c0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063bf0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063bf0`

## pseudocode

```c
void __fastcall ConnectedStorage::ContainerIndex::~ContainerIndex(ConnectedStorage::ContainerIndex *this)
{
  std::vector<unsigned __int64>::~vector<unsigned __int64>((char *)this + 200);
  std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>((char *)this + 184);
  std::vector<std::unique_ptr<ConnectedStorage::ContainerIndexEntry>>::~vector<std::unique_ptr<ConnectedStorage::ContainerIndexEntry>>((char *)this + 160);
  WindowsDeleteString(*((HSTRING *)this + 18));
  *((_QWORD *)this + 18) = 0;
  ConnectedStorage::ContainerIndexMetaData::~ContainerIndexMetaData((HSTRING *)this + 14);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  std::wstring::_Tidy_deallocate((char *)this + 32);
  std::wstring::_Tidy_deallocate(this);
}

```

## disassembly

```asm
0x180063bbc  push    rbx
0x180063bbe  sub     rsp, 20h
0x180063bc2  mov     rbx, rcx
0x180063bc5  add     rcx, 0C8h
0x180063bcc  call    ??1?$vector@_KV?$allocator@_K@std@@@std@@QEAA@XZ; std::vector<unsigned __int64>::~vector<unsigned __int64>(void)
0x180063bd1  lea     rcx, [rbx+0B8h]
0x180063bd8  call    ??1?$shared_ptr@V?$vector@VContainerQueryInfoWrapper@ConnectedStorage@@V?$allocator@VContainerQueryInfoWrapper@ConnectedStorage@@@std@@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>(void)
0x180063bdd  lea     rcx, [rbx+0A0h]
0x180063be4  call    ??1?$vector@V?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@std@@V?$allocator@V?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<ConnectedStorage::ContainerIndexEntry>>::~vector<std::unique_ptr<ConnectedStorage::ContainerIndexEntry>>(void)
0x180063be9  mov     rcx, [rbx+90h]; string
0x180063bf0  call    cs:__imp_WindowsDeleteString
0x180063bf6  lea     rcx, [rbx+70h]; this
0x180063bfa  mov     qword ptr [rbx+90h], 0
0x180063c05  call    ??1ContainerIndexMetaData@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContainerIndexMetaData::~ContainerIndexMetaData(void)
0x180063c0a  lea     rcx, [rbx+40h]; lpCriticalSection
0x180063c0e  call    cs:__imp_DeleteCriticalSection
0x180063c14  lea     rcx, [rbx+20h]
0x180063c18  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180063c1d  mov     rcx, rbx
0x180063c20  add     rsp, 20h
0x180063c24  pop     rbx
0x180063c25  jmp     ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
```
