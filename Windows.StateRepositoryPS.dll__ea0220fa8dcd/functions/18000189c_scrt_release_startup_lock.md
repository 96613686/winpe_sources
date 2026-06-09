# __scrt_release_startup_lock

- ea: `0x18000189c`
- end: `0x1800018c0`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001168`
- `0x180001268`

## callees

- `0x18000189c`
- `0x180001c58`

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
0x18000189c  push    rbx
0x18000189e  sub     rsp, 20h
0x1800018a2  mov     bl, cl
0x1800018a4  call    __scrt_is_ucrt_dll_in_use
0x1800018a9  test    eax, eax
0x1800018ab  jz      short loc_1800018BA
0x1800018ad  test    bl, bl
0x1800018af  jnz     short loc_1800018BA
0x1800018b1  xor     eax, eax
0x1800018b3  xchg    rax, cs:__scrt_native_startup_lock
0x1800018ba  add     rsp, 20h
0x1800018be  pop     rbx
0x1800018bf  retn
```
