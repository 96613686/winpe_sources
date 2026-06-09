# SocketExpiryThreadFunc(void *)

- ea: `0x1400027e0`
- end: `0x1400027ec`
- name: `?SocketExpiryThreadFunc@@YAKPEAX@Z`
- size: `12`
- prototype: `__int64 __fastcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140002704`

## pseudocode

```c
__int64 __fastcall SocketExpiryThreadFunc(LPVOID lpThreadParameter)
{
  return StateWebServer::RunSocketExpiry(StateWebServer::s_pstweb);
}

```

## disassembly

```asm
0x1400027e0  mov     rcx, cs:?s_pstweb@StateWebServer@@0PEAV1@EA; this
0x1400027e7  jmp     ?RunSocketExpiry@StateWebServer@@QEAAJXZ; StateWebServer::RunSocketExpiry(void)
```
