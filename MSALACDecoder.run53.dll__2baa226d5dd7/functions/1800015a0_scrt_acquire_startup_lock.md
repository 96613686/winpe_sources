# __scrt_acquire_startup_lock

- ea: `0x1800015a0`
- end: `0x1800015d9`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001238`
- `0x180001338`

## callees

- `0x1800015a0`
- `0x180001db4`

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
0x1800015a0  sub     rsp, 28h
0x1800015a4  call    __scrt_is_ucrt_dll_in_use
0x1800015a9  test    eax, eax
0x1800015ab  jz      short loc_1800015CE
0x1800015ad  mov     rax, gs:30h
0x1800015b6  mov     rcx, [rax+8]
0x1800015ba  jmp     short loc_1800015C1
0x1800015bc  cmp     rcx, rax
0x1800015bf  jz      short loc_1800015D5
0x1800015c1  xor     eax, eax
0x1800015c3  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x1800015cc  jnz     short loc_1800015BC
0x1800015ce  xor     al, al
0x1800015d0  add     rsp, 28h
0x1800015d4  retn
0x1800015d5  mov     al, 1
0x1800015d7  jmp     short loc_1800015D0
```
