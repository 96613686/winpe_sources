# __scrt_acquire_startup_lock

- ea: `0x180003b64`
- end: `0x180003b9d`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003fd0`
- `0x1800040fc`

## callees

- `0x180003b64`
- `0x180004670`

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
0x180003b64  sub     rsp, 28h
0x180003b68  call    __scrt_is_ucrt_dll_in_use
0x180003b6d  test    eax, eax
0x180003b6f  jz      short loc_180003B92
0x180003b71  mov     rax, gs:30h
0x180003b7a  mov     rcx, [rax+8]
0x180003b7e  jmp     short loc_180003B85
0x180003b80  cmp     rcx, rax
0x180003b83  jz      short loc_180003B99
0x180003b85  xor     eax, eax
0x180003b87  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x180003b90  jnz     short loc_180003B80
0x180003b92  xor     al, al
0x180003b94  add     rsp, 28h
0x180003b98  retn
0x180003b99  mov     al, 1
0x180003b9b  jmp     short loc_180003B94
```
