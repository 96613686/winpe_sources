# Windows::Networking::UX::Internal::MBStateMachine::~MBStateMachine(void)

- ea: `0x18004d60c`
- end: `0x18004d650`
- name: `??1MBStateMachine@Internal@UX@Networking@Windows@@UEAA@XZ`
- size: `68`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::MBStateMachine *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004d830`

## callees

- `0x180002150`
- `0x1800234b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004d634`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004d634`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d61c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d61c`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::MBStateMachine::~MBStateMachine(
        Windows::Networking::UX::Internal::MBStateMachine *this)
{
  CloseHandle(*((HANDLE *)this + 33));
  *((_QWORD *)this + 33) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 72);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<enum Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::IIterable<enum Windows::Networking::UX::NetworkMediaType>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<enum Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::IIterable<enum Windows::Networking::UX::NetworkMediaType>>(this);
}

```

## disassembly

```asm
0x18004d60c  push    rbx
0x18004d60e  sub     rsp, 20h
0x18004d612  mov     rbx, rcx
0x18004d615  mov     rcx, [rcx+108h]; hObject
0x18004d61c  call    cs:__imp_CloseHandle
0x18004d622  lea     rcx, [rbx+98h]; lpCriticalSection
0x18004d629  mov     qword ptr [rbx+108h], 0
0x18004d634  call    cs:__imp_DeleteCriticalSection
0x18004d63a  lea     rcx, [rbx+48h]
0x18004d63e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d643  mov     rcx, rbx
0x18004d646  add     rsp, 20h
0x18004d64a  pop     rbx
0x18004d64b  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IVectorView@W4NetworkMediaType@UX@Networking@Windows@@@Collections@Foundation@Windows@@U?$IIterable@W4NetworkMediaType@UX@Networking@Windows@@@567@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::IIterable<Windows::Networking::UX::NetworkMediaType>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::IIterable<Windows::Networking::UX::NetworkMediaType>>(void)
```
