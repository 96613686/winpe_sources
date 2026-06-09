# ConnectedStorage::BlobQuery::~BlobQuery(void)

- ea: `0x18004cf90`
- end: `0x18004d00b`
- name: `??1BlobQuery@ConnectedStorage@@UEAA@XZ`
- size: `123`
- prototype: `void __fastcall(ConnectedStorage::BlobQuery *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180013b90`

## callees

- `0x180012418`
- `0x180012424`
- `0x18001253c`
- `0x1800125ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004cfc2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004cfc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cfd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cfe7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cfd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cfe7`

## pseudocode

```c
void __fastcall ConnectedStorage::BlobQuery::~BlobQuery(ConnectedStorage::BlobQuery *this)
{
  *(_QWORD *)this = &ConnectedStorage::BlobQuery::`vftable';
  std::vector<std::function<void (void)>>::~vector<std::function<void (void)>>((char *)this + 248);
  std::vector<ConnectedStorage::BlobQueryInfoWrapper>::~vector<ConnectedStorage::BlobQueryInfoWrapper>((char *)this + 224);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  ConnectedStorage::CallerInfo::~CallerInfo((ConnectedStorage::BlobQuery *)((char *)this + 104));
  WindowsDeleteString(*((HSTRING *)this + 9));
  *((_QWORD *)this + 9) = 0;
  WindowsDeleteString(*((HSTRING *)this + 8));
  *((_QWORD *)this + 8) = 0;
  ConnectedStorage::ContextDesc::~ContextDesc((HSTRING *)this + 2);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x18004cf90  push    rbx
0x18004cf92  sub     rsp, 20h
0x18004cf96  lea     rax, ??_7BlobQuery@ConnectedStorage@@6B@; const ConnectedStorage::BlobQuery::`vftable'
0x18004cf9d  mov     rbx, rcx
0x18004cfa0  mov     [rcx], rax
0x18004cfa3  add     rcx, 0F8h
0x18004cfaa  call    ??1?$vector@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAA@XZ; std::vector<std::function<void (void)>>::~vector<std::function<void (void)>>(void)
0x18004cfaf  lea     rcx, [rbx+0E0h]
0x18004cfb6  call    ??1?$vector@VBlobQueryInfoWrapper@ConnectedStorage@@V?$allocator@VBlobQueryInfoWrapper@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::vector<ConnectedStorage::BlobQueryInfoWrapper>::~vector<ConnectedStorage::BlobQueryInfoWrapper>(void)
0x18004cfbb  lea     rcx, [rbx+0A8h]; lpCriticalSection
0x18004cfc2  call    cs:__imp_DeleteCriticalSection
0x18004cfc8  lea     rcx, [rbx+68h]; this
0x18004cfcc  call    ??1CallerInfo@ConnectedStorage@@QEAA@XZ; ConnectedStorage::CallerInfo::~CallerInfo(void)
0x18004cfd1  mov     rcx, [rbx+48h]; string
0x18004cfd5  call    cs:__imp_WindowsDeleteString
0x18004cfdb  mov     qword ptr [rbx+48h], 0
0x18004cfe3  mov     rcx, [rbx+40h]; string
0x18004cfe7  call    cs:__imp_WindowsDeleteString
0x18004cfed  lea     rcx, [rbx+10h]; this
0x18004cff1  mov     qword ptr [rbx+40h], 0
0x18004cff9  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x18004cffe  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18004d005  add     rsp, 20h
0x18004d009  pop     rbx
0x18004d00a  retn
```
