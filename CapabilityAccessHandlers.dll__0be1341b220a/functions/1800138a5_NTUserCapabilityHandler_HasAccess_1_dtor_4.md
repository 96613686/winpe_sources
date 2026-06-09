# _NTUserCapabilityHandler::HasAccess_::_1_::dtor$4

- ea: `0x1800138a5`
- end: `0x1800138ce`
- name: `_NTUserCapabilityHandler::HasAccess_::_1_::dtor$4`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001031c`
- `0x1800138a5`

## pseudocode

```c
void __fastcall NTUserCapabilityHandler::HasAccess_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 88) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 88) &= ~1u;
    Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 144));
  }
}

```

## disassembly

```asm
0x1800138a5  push    rbp
0x1800138a7  sub     rsp, 20h
0x1800138ab  mov     rbp, rdx
0x1800138ae  mov     eax, [rbp+58h]
0x1800138b1  and     eax, 1
0x1800138b4  test    eax, eax
0x1800138b6  jz      short loc_1800138C8
0x1800138b8  and     dword ptr [rbp+58h], 0FFFFFFFEh
0x1800138bc  lea     rcx, [rbp+90h]; this
0x1800138c3  call    ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
0x1800138c8  add     rsp, 20h
0x1800138cc  pop     rbp
0x1800138cd  retn
```
