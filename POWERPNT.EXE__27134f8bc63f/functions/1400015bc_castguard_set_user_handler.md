# __castguard_set_user_handler

- ea: `0x1400015bc`
- end: `0x1400015c7`
- name: `__castguard_set_user_handler`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1400015b0`

## pseudocode

```c
__int64 __fastcall _castguard_set_user_handler(__int64 a1)
{
  return _InterlockedExchange64(&_castguard_check_failure_user_handled_fptr, a1);
}

```

## disassembly

```asm
0x1400015bc  xchg    rcx, cs:__castguard_check_failure_user_handled_fptr
0x1400015c3  mov     rax, rcx
0x1400015c6  retn
```
