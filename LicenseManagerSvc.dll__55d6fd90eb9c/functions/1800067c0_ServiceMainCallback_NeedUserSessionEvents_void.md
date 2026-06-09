# ServiceMainCallback::NeedUserSessionEvents(void)

- ea: `0x1800067c0`
- end: `0x1800067c3`
- name: `?NeedUserSessionEvents@ServiceMainCallback@@UEAA_NXZ`
- size: `3`
- prototype: `bool __fastcall(ServiceMainCallback *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
bool __fastcall ServiceMainCallback::NeedUserSessionEvents(ServiceMainCallback *this)
{
  return 0;
}

```

## disassembly

```asm
0x1800067c0  xor     al, al
0x1800067c2  retn
```
