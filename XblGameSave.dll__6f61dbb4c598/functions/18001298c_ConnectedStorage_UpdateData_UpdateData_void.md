# ConnectedStorage::UpdateData::~UpdateData(void)

- ea: `0x18001298c`
- end: `0x1800129f6`
- name: `??1UpdateData@ConnectedStorage@@QEAA@XZ`
- size: `106`
- prototype: `void __fastcall(ConnectedStorage::UpdateData *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180019320`

## callees

- `0x18000a040`
- `0x180011e7c`
- `0x180012328`
- `0x180012498`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800129c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800129d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800129c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800129d8`

## pseudocode

```c
void __fastcall ConnectedStorage::UpdateData::~UpdateData(HSTRING *this)
{
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 28);
  std::vector<ConnectedStorage::SimpleHStringWrapper>::~vector<ConnectedStorage::SimpleHStringWrapper>(this + 25);
  std::vector<ConnectedStorage::UpdateDesc>::~vector<ConnectedStorage::UpdateDesc>(this + 22);
  WindowsDeleteString(this[21]);
  this[21] = 0;
  WindowsDeleteString(this[20]);
  this[20] = 0;
  ConnectedStorage::OperationData<IStorageOperationHandler,AsyncIStorageOperationHandler>::~OperationData<IStorageOperationHandler,AsyncIStorageOperationHandler>(this);
}

```

## disassembly

```asm
0x18001298c  push    rbx
0x18001298e  sub     rsp, 20h
0x180012992  mov     rbx, rcx
0x180012995  add     rcx, 0E0h
0x18001299c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800129a1  lea     rcx, [rbx+0C8h]
0x1800129a8  call    ??1?$vector@VSimpleHStringWrapper@ConnectedStorage@@V?$allocator@VSimpleHStringWrapper@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::vector<ConnectedStorage::SimpleHStringWrapper>::~vector<ConnectedStorage::SimpleHStringWrapper>(void)
0x1800129ad  lea     rcx, [rbx+0B0h]
0x1800129b4  call    ??1?$vector@UUpdateDesc@ConnectedStorage@@V?$allocator@UUpdateDesc@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::vector<ConnectedStorage::UpdateDesc>::~vector<ConnectedStorage::UpdateDesc>(void)
0x1800129b9  mov     rcx, [rbx+0A8h]; string
0x1800129c0  call    cs:__imp_WindowsDeleteString
0x1800129c6  mov     qword ptr [rbx+0A8h], 0
0x1800129d1  mov     rcx, [rbx+0A0h]; string
0x1800129d8  call    cs:__imp_WindowsDeleteString
0x1800129de  mov     rcx, rbx
0x1800129e1  mov     qword ptr [rbx+0A0h], 0
0x1800129ec  add     rsp, 20h
0x1800129f0  pop     rbx
0x1800129f1  jmp     ??1?$OperationData@UIStorageOperationHandler@@UAsyncIStorageOperationHandler@@@ConnectedStorage@@QEAA@XZ; ConnectedStorage::OperationData<IStorageOperationHandler,AsyncIStorageOperationHandler>::~OperationData<IStorageOperationHandler,AsyncIStorageOperationHandler>(void)
```
