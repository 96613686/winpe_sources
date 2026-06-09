# BaseSetProcessCreateNotify

- ea: `0x180007160`
- end: `0x180007168`
- name: `BaseSetProcessCreateNotify`
- size: `8`
- prototype: ``
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
0x180007160  mov     cs:UserNotifyProcessCreate, rcx
0x180007167  retn
```
