# __scrt_acquire_startup_lock

- ea: `0x1800015ac`
- end: `0x1800015e5`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001168`
- `0x180001268`

## callees

- `0x1800015ac`
- `0x180001c58`

## pseudocode

```c
char _scrt_acquire_startup_lock()
{
  PVOID StackBase; // rcx
  signed __int64 v1; // rax

  if ( _scrt_is_ucrt_dll_in_use() )
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
0x1800015ac  sub     rsp, 28h
0x1800015b0  call    __scrt_is_ucrt_dll_in_use
0x1800015b5  test    eax, eax
0x1800015b7  jz      short loc_1800015DA
0x1800015b9  mov     rax, gs:30h
0x1800015c2  mov     rcx, [rax+8]
0x1800015c6  jmp     short loc_1800015CD
0x1800015c8  cmp     rcx, rax
0x1800015cb  jz      short loc_1800015E1
0x1800015cd  xor     eax, eax
0x1800015cf  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x1800015d8  jnz     short loc_1800015C8
0x1800015da  xor     al, al
0x1800015dc  add     rsp, 28h
0x1800015e0  retn
0x1800015e1  mov     al, 1
0x1800015e3  jmp     short loc_1800015DC
```
