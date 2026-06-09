# BaseSetProcessCreateNotify

- ea: `0x180006ed0`
- end: `0x180006ed8`
- name: `BaseSetProcessCreateNotify`
- size: `8`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall BaseSetProcessCreateNotify(__int64 a1)
{
  UserNotifyProcessCreate = a1;
}

```

## disassembly

```asm
0x180006ed0  mov     cs:UserNotifyProcessCreate, rcx
0x180006ed7  retn
```
