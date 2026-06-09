# __scrt_acquire_startup_lock

- ea: `0x1800015a4`
- end: `0x1800015dd`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: `char()`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001128`
- `0x180001228`

## callees

- `0x1800015a4`
- `0x180001c54`

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
0x1800015a4  sub     rsp, 28h
0x1800015a8  call    __scrt_is_ucrt_dll_in_use
0x1800015ad  test    eax, eax
0x1800015af  jz      short loc_1800015D2
0x1800015b1  mov     rax, gs:30h
0x1800015ba  mov     rcx, [rax+8]
0x1800015be  jmp     short loc_1800015C5
0x1800015c0  cmp     rcx, rax
0x1800015c3  jz      short loc_1800015D9
0x1800015c5  xor     eax, eax
0x1800015c7  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x1800015d0  jnz     short loc_1800015C0
0x1800015d2  xor     al, al
0x1800015d4  add     rsp, 28h
0x1800015d8  retn
0x1800015d9  mov     al, 1
0x1800015db  jmp     short loc_1800015D4
```
