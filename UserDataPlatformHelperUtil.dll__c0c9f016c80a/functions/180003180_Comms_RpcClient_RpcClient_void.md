# Comms::RpcClient::RpcClient(void)

- ea: `0x180003180`
- end: `0x180003193`
- name: `??0RpcClient@Comms@@QEAA@XZ`
- size: `19`
- prototype: `Comms::RpcClient *__fastcall(Comms::RpcClient *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
Comms::RpcClient *__fastcall Comms::RpcClient::RpcClient(Comms::RpcClient *this)
{
  *(_QWORD *)this = -1;
  *((_QWORD *)this + 1) = -1;
  *((_QWORD *)this + 2) = -1;
  return this;
}

```

## disassembly

```asm
0x180003180  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003184  mov     [rcx], rax
0x180003187  mov     [rcx+8], rax
0x18000318b  mov     [rcx+10h], rax
0x18000318f  mov     rax, rcx
0x180003192  retn
```
