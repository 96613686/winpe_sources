# Comms::SecureRpcClient::SecureRpcClient(void)

- ea: `0x1800031a0`
- end: `0x1800031b6`
- name: `??0SecureRpcClient@Comms@@QEAA@XZ`
- size: `22`
- prototype: `Comms::SecureRpcClient *__fastcall(Comms::SecureRpcClient *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
Comms::SecureRpcClient *__fastcall Comms::SecureRpcClient::SecureRpcClient(Comms::SecureRpcClient *this)
{
  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = &Comms::SecureRpcClient::`vftable';
  return this;
}

```

## disassembly

```asm
0x1800031a0  lea     rax, ??_7SecureRpcClient@Comms@@6B@
0x1800031a7  mov     qword ptr [rcx+8], 0
0x1800031af  mov     [rcx], rax
0x1800031b2  mov     rax, rcx
0x1800031b5  retn
```
