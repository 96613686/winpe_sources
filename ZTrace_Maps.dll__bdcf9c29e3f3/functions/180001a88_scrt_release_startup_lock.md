# __scrt_release_startup_lock

- ea: `0x180001a88`
- end: `0x180001aac`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001408`
- `0x180001508`

## callees

- `0x180001a88`
- `0x180002190`

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
0x180001a88  push    rbx
0x180001a8a  sub     rsp, 20h
0x180001a8e  mov     bl, cl
0x180001a90  call    __scrt_is_ucrt_dll_in_use
0x180001a95  test    eax, eax
0x180001a97  jz      short loc_180001AA6
0x180001a99  test    bl, bl
0x180001a9b  jnz     short loc_180001AA6
0x180001a9d  xor     eax, eax
0x180001a9f  xchg    rax, cs:__scrt_native_startup_lock
0x180001aa6  add     rsp, 20h
0x180001aaa  pop     rbx
0x180001aab  retn
```
