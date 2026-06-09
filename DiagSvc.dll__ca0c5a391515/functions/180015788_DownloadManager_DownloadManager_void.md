# DownloadManager::~DownloadManager(void)

- ea: `0x180015788`
- end: `0x180015818`
- name: `??1DownloadManager@@MEAA@XZ`
- size: `144`
- prototype: `void __fastcall(DownloadManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016570`

## callees

- `0x180009c68`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800157b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800157c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800157d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800157eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800157fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800157b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800157c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800157d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800157eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800157fd`

## pseudocode

```c
void __fastcall DownloadManager::~DownloadManager(DownloadManager *this)
{
  *(_QWORD *)this = &DownloadManager::`vftable';
  *((_QWORD *)this + 1) = &DownloadManager::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &Microsoft::WRL::RuntimeClass<IDownloadManager,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = 0;
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
0x180015788  push    rbx
0x18001578a  sub     rsp, 20h
0x18001578e  lea     rax, ??_7DownloadManager@@6B@; const DownloadManager::`vftable'
0x180015795  mov     rbx, rcx
0x180015798  mov     [rcx], rax
0x18001579b  lea     rax, ??_7DownloadManager@@6BIWeakReferenceSource@@@; const DownloadManager::`vftable'{for `IWeakReferenceSource'}
0x1800157a2  mov     [rcx+8], rax
0x1800157a6  lea     rax, ??_7?$RuntimeClass@UIDownloadManager@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<IDownloadManager,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800157ad  mov     [rcx+10h], rax
0x1800157b1  mov     rcx, [rcx+60h]; string
0x1800157b5  call    cs:__imp_WindowsDeleteString
0x1800157bb  mov     qword ptr [rbx+60h], 0
0x1800157c3  mov     rcx, [rbx+58h]; string
0x1800157c7  call    cs:__imp_WindowsDeleteString
0x1800157cd  mov     qword ptr [rbx+58h], 0
0x1800157d5  mov     rcx, [rbx+50h]; string
0x1800157d9  call    cs:__imp_WindowsDeleteString
0x1800157df  mov     qword ptr [rbx+50h], 0
0x1800157e7  mov     rcx, [rbx+48h]; string
0x1800157eb  call    cs:__imp_WindowsDeleteString
0x1800157f1  mov     qword ptr [rbx+48h], 0
0x1800157f9  mov     rcx, [rbx+40h]; string
0x1800157fd  call    cs:__imp_WindowsDeleteString
0x180015803  mov     rcx, rbx
0x180015806  mov     qword ptr [rbx+40h], 0
0x18001580e  add     rsp, 20h
0x180015812  pop     rbx
0x180015813  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRunManager@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,IRunManager,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,IRunManager,Microsoft::WRL::FtmBase>(void)
```
