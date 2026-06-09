# WorkspaceManager::~WorkspaceManager(void)

- ea: `0x18001a7b0`
- end: `0x18001a833`
- name: `??1WorkspaceManager@@MEAA@XZ`
- size: `131`
- prototype: `void __fastcall(WorkspaceManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001a840`

## callees

- `0x180009c68`
- `0x18001a880`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a7e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a7f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a806`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a818`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a7e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a7f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a806`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a818`

## pseudocode

```c
void __fastcall WorkspaceManager::~WorkspaceManager(WorkspaceManager *this)
{
  *(_QWORD *)this = &WorkspaceManager::`vftable';
  *((_QWORD *)this + 1) = &WorkspaceManager::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &WorkspaceManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  WorkspaceManager::DeleteWorkspace(this);
  WindowsDeleteString(*((HSTRING *)this + 11));
  *((_QWORD *)this + 11) = 0;
  WindowsDeleteString(*((HSTRING *)this + 10));
  *((_QWORD *)this + 10) = 0;
  WindowsDeleteString(*((HSTRING *)this + 9));
  *((_QWORD *)this + 9) = 0;
  WindowsDeleteString(*((HSTRING *)this + 8));
  *((_QWORD *)this + 8) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,IRunManager,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,IRunManager,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x18001a7b0  push    rbx
0x18001a7b2  sub     rsp, 20h
0x18001a7b6  lea     rax, ??_7WorkspaceManager@@6B@; const WorkspaceManager::`vftable'
0x18001a7bd  mov     rbx, rcx
0x18001a7c0  mov     [rcx], rax
0x18001a7c3  lea     rax, ??_7WorkspaceManager@@6BIWeakReferenceSource@@@; const WorkspaceManager::`vftable'{for `IWeakReferenceSource'}
0x18001a7ca  mov     [rcx+8], rax
0x18001a7ce  lea     rax, ??_7WorkspaceManager@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const WorkspaceManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001a7d5  mov     [rcx+10h], rax
0x18001a7d9  call    ?DeleteWorkspace@WorkspaceManager@@UEAAJXZ; WorkspaceManager::DeleteWorkspace(void)
0x18001a7de  mov     rcx, [rbx+58h]; string
0x18001a7e2  call    cs:__imp_WindowsDeleteString
0x18001a7e8  mov     qword ptr [rbx+58h], 0
0x18001a7f0  mov     rcx, [rbx+50h]; string
0x18001a7f4  call    cs:__imp_WindowsDeleteString
0x18001a7fa  mov     qword ptr [rbx+50h], 0
0x18001a802  mov     rcx, [rbx+48h]; string
0x18001a806  call    cs:__imp_WindowsDeleteString
0x18001a80c  mov     qword ptr [rbx+48h], 0
0x18001a814  mov     rcx, [rbx+40h]; string
0x18001a818  call    cs:__imp_WindowsDeleteString
0x18001a81e  mov     rcx, rbx
0x18001a821  mov     qword ptr [rbx+40h], 0
0x18001a829  add     rsp, 20h
0x18001a82d  pop     rbx
0x18001a82e  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRunManager@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,IRunManager,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,IRunManager,Microsoft::WRL::FtmBase>(void)
```
