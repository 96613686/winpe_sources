# __scrt_acquire_startup_lock

- ea: `0x180001598`
- end: `0x1800015d1`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: `char()`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001148`
- `0x180001248`

## callees

- `0x180001598`
- `0x180001c44`

## pseudocode

```c
char _scrt_acquire_startup_lock()
{
  PVOID StackBase; // rcx
  signed __int64 v1; // rax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    StackBase = NtCurrentTeb()->NtTib.StackBase;
    while ( 1 )
    {
      v1 = _InterlockedCompareExchange64(&_scrt_native_startup_lock, (signed __int64)StackBase, 0);
      if ( !v1 )
        break;
      if ( StackBase == (PVOID)v1 )
        return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180001598  sub     rsp, 28h
0x18000159c  call    __scrt_is_ucrt_dll_in_use
0x1800015a1  test    eax, eax
0x1800015a3  jz      short loc_1800015C6
0x1800015a5  mov     rax, gs:30h
0x1800015ae  mov     rcx, [rax+8]
0x1800015b2  jmp     short loc_1800015B9
0x1800015b4  cmp     rcx, rax
0x1800015b7  jz      short loc_1800015CD
0x1800015b9  xor     eax, eax
0x1800015bb  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x1800015c4  jnz     short loc_1800015B4
0x1800015c6  xor     al, al
0x1800015c8  add     rsp, 28h
0x1800015cc  retn
0x1800015cd  mov     al, 1
0x1800015cf  jmp     short loc_1800015C8
```
