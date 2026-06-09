# DiagnosticRunner::~DiagnosticRunner(void)

- ea: `0x18001e294`
- end: `0x18001e2e2`
- name: `??1DiagnosticRunner@@MEAA@XZ`
- size: `78`
- prototype: `void __fastcall(DiagnosticRunner *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001eb00`

## callees

- `0x180009c68`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e2c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e2c4`

## pseudocode

```c
void __fastcall DiagnosticRunner::~DiagnosticRunner(DiagnosticRunner *this)
{
  *(_QWORD *)this = &DiagnosticRunner::`vftable';
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<IDiagnosticRunner,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &Microsoft::WRL::RuntimeClass<IDiagnosticRunner,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  WindowsDeleteString(*((HSTRING *)this + 41));
  *((_QWORD *)this + 41) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,IRunManager,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,IRunManager,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x18001e294  push    rbx
0x18001e296  sub     rsp, 20h
0x18001e29a  lea     rax, ??_7DiagnosticRunner@@6B@; const DiagnosticRunner::`vftable'
0x18001e2a1  mov     rbx, rcx
0x18001e2a4  mov     [rcx], rax
0x18001e2a7  lea     rax, ??_7?$RuntimeClass@UIDiagnosticRunner@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<IDiagnosticRunner,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'}
0x18001e2ae  mov     [rcx+8], rax
0x18001e2b2  lea     rax, ??_7?$RuntimeClass@UIDiagnosticRunner@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<IDiagnosticRunner,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001e2b9  mov     [rcx+10h], rax
0x18001e2bd  mov     rcx, [rcx+148h]; string
0x18001e2c4  call    cs:__imp_WindowsDeleteString
0x18001e2ca  mov     rcx, rbx
0x18001e2cd  mov     qword ptr [rbx+148h], 0
0x18001e2d8  add     rsp, 20h
0x18001e2dc  pop     rbx
0x18001e2dd  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRunManager@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,IRunManager,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,IRunManager,Microsoft::WRL::FtmBase>(void)
```
