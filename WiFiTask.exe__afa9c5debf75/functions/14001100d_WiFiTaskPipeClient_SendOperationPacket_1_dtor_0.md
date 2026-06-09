# _WiFiTaskPipeClient::SendOperationPacket_::_1_::dtor$0

- ea: `0x14001100d`
- end: `0x14001102a`
- name: `_WiFiTaskPipeClient::SendOperationPacket_::_1_::dtor$0`
- size: `29`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task`

## callees

- `0x1400016c4`

## pseudocode

```c
void __fastcall WiFiTaskPipeClient::SendOperationPacket_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 80));
}

```

## disassembly

```asm
0x14001100d  push    rbp
0x14001100f  sub     rsp, 20h
0x140011013  mov     rbp, rdx
0x140011016  mov     edx, 18h
0x14001101b  mov     rcx, [rbp+50h]; Block
0x14001101f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140011024  add     rsp, 20h
0x140011028  pop     rbp
0x140011029  retn
```
