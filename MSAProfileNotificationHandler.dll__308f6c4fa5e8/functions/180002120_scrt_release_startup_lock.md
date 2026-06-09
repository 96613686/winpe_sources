# __scrt_release_startup_lock

- ea: `0x180002120`
- end: `0x180002144`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001998`
- `0x180001a98`

## callees

- `0x180002120`
- `0x180002594`

## pseudocode

```c
__int64 __fastcall _scrt_release_startup_lock(char a1)
{
  __int64 result; // rax

  result = _scrt_is_ucrt_dll_in_use();
  if ( (_DWORD)result )
  {
    if ( !a1 )
      return _InterlockedExchange64(&_scrt_native_startup_lock, 0);
  }
  return result;
}

```

## disassembly

```asm
0x180002120  push    rbx
0x180002122  sub     rsp, 20h
0x180002126  mov     bl, cl
0x180002128  call    __scrt_is_ucrt_dll_in_use
0x18000212d  test    eax, eax
0x18000212f  jz      short loc_18000213E
0x180002131  test    bl, bl
0x180002133  jnz     short loc_18000213E
0x180002135  xor     eax, eax
0x180002137  xchg    rax, cs:__scrt_native_startup_lock
0x18000213e  add     rsp, 20h
0x180002142  pop     rbx
0x180002143  retn
```
