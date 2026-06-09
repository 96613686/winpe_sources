# __register_thread_local_exe_atexit_callback

- ea: `0x40ed6d`
- end: `0x40ed93`
- name: `__register_thread_local_exe_atexit_callback`
- size: `38`
- prototype: `void __cdecl(_tls_callback_type Callback)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x40b702`

## callees

- `0x40e40c`
- `0x40f45f`

## pseudocode

```c
void __cdecl _register_thread_local_exe_atexit_callback(_tls_callback_type Callback)
{
  if ( dword_417FF4 != __security_cookie )
    terminate();
  dword_417FF4 = unknown_libname_4(Callback);
}

```

## disassembly

```asm
0x40ed6d  mov     edi, edi
0x40ed6f  push    ebp
0x40ed70  mov     ebp, esp
0x40ed72  mov     eax, dword_417FF4
0x40ed77  cmp     eax, ___security_cookie
0x40ed7d  jnz     _terminate
0x40ed83  push    [ebp+Callback]
0x40ed86  call    unknown_libname_4; Microsoft VisualC universal runtime
0x40ed8b  pop     ecx
0x40ed8c  mov     dword_417FF4, eax
0x40ed91  pop     ebp
0x40ed92  retn
```
