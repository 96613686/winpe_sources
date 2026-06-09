# __scrt_acquire_startup_lock

- ea: `0x1800015b4`
- end: `0x1800015ed`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: `char()`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001278`
- `0x180001378`

## callees

- `0x1800015b4`
- `0x180001e28`

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
0x1800015b4  sub     rsp, 28h
0x1800015b8  call    __scrt_is_ucrt_dll_in_use
0x1800015bd  test    eax, eax
0x1800015bf  jz      short loc_1800015E2
0x1800015c1  mov     rax, gs:30h
0x1800015ca  mov     rcx, [rax+8]
0x1800015ce  jmp     short loc_1800015D5
0x1800015d0  cmp     rcx, rax
0x1800015d3  jz      short loc_1800015E9
0x1800015d5  xor     eax, eax
0x1800015d7  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x1800015e0  jnz     short loc_1800015D0
0x1800015e2  xor     al, al
0x1800015e4  add     rsp, 28h
0x1800015e8  retn
0x1800015e9  mov     al, 1
0x1800015eb  jmp     short loc_1800015E4
```
