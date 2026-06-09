# _register_thread_local_exe_atexit_callback

- ea: `0x140012d3c`
- end: `0x140012d78`
- name: `_register_thread_local_exe_atexit_callback`
- size: `60`
- prototype: `void __cdecl(_tls_callback_type Callback)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140005a6c`

## callees

- `0x140012d3c`
- `0x140013628`

## pseudocode

```c
void __cdecl register_thread_local_exe_atexit_callback(_tls_callback_type Callback)
{
  if ( qword_14003CAE8 != _security_cookie )
    terminate(Callback, Callback);
  qword_14003CAE8 = _security_cookie ^ __ROR8__(Callback, 64 - ((unsigned __int8)_security_cookie & 0x3Fu));
}

```

## disassembly

```asm
0x140012d3c  sub     rsp, 28h
0x140012d40  mov     r8, cs:__security_cookie
0x140012d47  mov     rdx, rcx
0x140012d4a  cmp     cs:qword_14003CAE8, r8
0x140012d51  jnz     short loc_140012D72
0x140012d53  mov     eax, r8d
0x140012d56  mov     ecx, 40h ; '@'
0x140012d5b  and     eax, 3Fh
0x140012d5e  sub     ecx, eax
0x140012d60  ror     rdx, cl
0x140012d63  xor     rdx, r8
0x140012d66  mov     cs:qword_14003CAE8, rdx
0x140012d6d  add     rsp, 28h
0x140012d71  retn
0x140012d72  call    terminate
```
