# _register_thread_local_exe_atexit_callback

- ea: `0x140014cf4`
- end: `0x140014d32`
- name: `_register_thread_local_exe_atexit_callback`
- size: `62`
- prototype: `void __cdecl(_tls_callback_type Callback)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001bd5c`

## callees

- `0x140014cf4`
- `0x1400182b4`

## pseudocode

```c
void __cdecl register_thread_local_exe_atexit_callback(_tls_callback_type Callback)
{
  if ( qword_1400D71F0 != _security_cookie )
    terminate(Callback, Callback);
  qword_1400D71F0 = _security_cookie ^ __ROR8__(Callback, 64 - ((unsigned __int8)_security_cookie & 0x3Fu));
}

```

## disassembly

```asm
0x140014cf4  sub     rsp, 28h
0x140014cf8  mov     r8, cs:__security_cookie
0x140014cff  mov     rdx, rcx
0x140014d02  cmp     cs:qword_1400D71F0, r8
0x140014d09  jnz     short loc_140014D2C
0x140014d0b  mov     ecx, r8d
0x140014d0e  mov     eax, 40h ; '@'
0x140014d13  and     ecx, 3Fh
0x140014d16  sub     eax, ecx
0x140014d18  mov     cl, al
0x140014d1a  ror     rdx, cl
0x140014d1d  xor     rdx, r8
0x140014d20  mov     cs:qword_1400D71F0, rdx
0x140014d27  add     rsp, 28h
0x140014d2b  retn
0x140014d2c  call    terminate
```
