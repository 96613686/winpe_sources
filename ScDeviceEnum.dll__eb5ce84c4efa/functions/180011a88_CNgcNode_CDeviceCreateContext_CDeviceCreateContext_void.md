# CNgcNode::CDeviceCreateContext::~CDeviceCreateContext(void)

- ea: `0x180011a88`
- end: `0x180011ab6`
- name: `??1CDeviceCreateContext@CNgcNode@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(CNgcNode::CDeviceCreateContext *this, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012304`
- `0x18001f28b`

## callees

- `0x180008bbc`
- `0x180009840`

## pseudocode

```c
void __fastcall CNgcNode::CDeviceCreateContext::~CDeviceCreateContext(CNgcNode::CDeviceCreateContext *this, __int64 a2)
{
  LOBYTE(a2) = 1;
  std::wstring::_Tidy((char *)this + 24, a2, 0);
  *(_QWORD *)this = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::Close(this);
}

```

## disassembly

```asm
0x180011a88  push    rbx
0x180011a8a  sub     rsp, 20h
0x180011a8e  mov     rbx, rcx
0x180011a91  xor     r8d, r8d
0x180011a94  add     rcx, 18h
0x180011a98  mov     dl, 1
0x180011a9a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180011a9f  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180011aa6  mov     rcx, rbx
0x180011aa9  mov     [rbx], rax
0x180011aac  add     rsp, 20h
0x180011ab0  pop     rbx
0x180011ab1  jmp     ?Close@?$HandleT@USwDeviceHandleTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::Close(void)
```
