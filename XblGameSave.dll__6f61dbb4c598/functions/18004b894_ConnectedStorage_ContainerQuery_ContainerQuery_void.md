# ConnectedStorage::ContainerQuery::~ContainerQuery(void)

- ea: `0x18004b894`
- end: `0x18004b8fd`
- name: `??1ContainerQuery@ConnectedStorage@@UEAA@XZ`
- size: `105`
- prototype: `void __fastcall(ConnectedStorage::ContainerQuery *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180013bd0`

## callees

- `0x180012418`
- `0x180012430`
- `0x18001253c`
- `0x1800125ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004b8c6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004b8c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b8d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b8d9`

## pseudocode

```c
void __fastcall ConnectedStorage::ContainerQuery::~ContainerQuery(ConnectedStorage::ContainerQuery *this)
{
  *(_QWORD *)this = &ConnectedStorage::ContainerQuery::`vftable';
  std::vector<std::function<void (void)>>::~vector<std::function<void (void)>>((char *)this + 240);
  std::vector<ConnectedStorage::ContainerQueryInfoWrapper>::~vector<ConnectedStorage::ContainerQueryInfoWrapper>((char *)this + 216);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 4);
  ConnectedStorage::CallerInfo::~CallerInfo((HSTRING *)this + 12);
  WindowsDeleteString(*((HSTRING *)this + 8));
  *((_QWORD *)this + 8) = 0;
  ConnectedStorage::ContextDesc::~ContextDesc((HSTRING *)this + 2);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x18004b894  push    rbx
0x18004b896  sub     rsp, 20h
0x18004b89a  lea     rax, ??_7ContainerQuery@ConnectedStorage@@6B@; const ConnectedStorage::ContainerQuery::`vftable'
0x18004b8a1  mov     rbx, rcx
0x18004b8a4  mov     [rcx], rax
0x18004b8a7  add     rcx, 0F0h
0x18004b8ae  call    ??1?$vector@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAA@XZ; std::vector<std::function<void (void)>>::~vector<std::function<void (void)>>(void)
0x18004b8b3  lea     rcx, [rbx+0D8h]
0x18004b8ba  call    ??1?$vector@VContainerQueryInfoWrapper@ConnectedStorage@@V?$allocator@VContainerQueryInfoWrapper@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::vector<ConnectedStorage::ContainerQueryInfoWrapper>::~vector<ConnectedStorage::ContainerQueryInfoWrapper>(void)
0x18004b8bf  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x18004b8c6  call    cs:__imp_DeleteCriticalSection
0x18004b8cc  lea     rcx, [rbx+60h]; this
0x18004b8d0  call    ??1CallerInfo@ConnectedStorage@@QEAA@XZ; ConnectedStorage::CallerInfo::~CallerInfo(void)
0x18004b8d5  mov     rcx, [rbx+40h]; string
0x18004b8d9  call    cs:__imp_WindowsDeleteString
0x18004b8df  lea     rcx, [rbx+10h]; this
0x18004b8e3  mov     qword ptr [rbx+40h], 0
0x18004b8eb  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x18004b8f0  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18004b8f7  add     rsp, 20h
0x18004b8fb  pop     rbx
0x18004b8fc  retn
```
