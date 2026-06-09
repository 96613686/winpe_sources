# _dynamic_atexit_destructor_for__Updater__

- ea: `0x180011790`
- end: `0x18001179c`
- name: `_dynamic_atexit_destructor_for__Updater__`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007a30`

## pseudocode

```c
__int64 dynamic_atexit_destructor_for__Updater__()
{
  return Microsoft::WRL::ComPtr<TimeUpdate>::InternalRelease((__int64 *)&qword_18001C2F0);
}

```

## disassembly

```asm
0x180011790  lea     rcx, qword_18001C2F0
0x180011797  jmp     ?InternalRelease@?$ComPtr@VTimeUpdate@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<TimeUpdate>::InternalRelease(void)
```
