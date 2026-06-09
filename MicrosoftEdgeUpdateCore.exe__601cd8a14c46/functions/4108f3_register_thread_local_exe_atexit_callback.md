# __register_thread_local_exe_atexit_callback

- ea: `0x4108f3`
- end: `0x410919`
- name: `__register_thread_local_exe_atexit_callback`
- size: `38`
- prototype: `void __cdecl(_tls_callback_type Callback)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x40d5c2`

## callees

- `0x410668`
- `0x411615`

## pseudocode

```c
void __cdecl _register_thread_local_exe_atexit_callback(_tls_callback_type Callback)
{
  if ( dword_43E0D0 != __security_cookie )
    terminate();
  dword_43E0D0 = unknown_libname_6(Callback);
}

```

## disassembly

```asm
0x4108f3  mov     edi, edi
0x4108f5  push    ebp
0x4108f6  mov     ebp, esp
0x4108f8  mov     eax, dword_43E0D0
0x4108fd  cmp     eax, ___security_cookie
0x410903  jnz     _terminate
0x410909  push    [ebp+Callback]
0x41090c  call    unknown_libname_6; Microsoft VisualC universal runtime
0x410911  pop     ecx
0x410912  mov     dword_43E0D0, eax
0x410917  pop     ebp
0x410918  retn
```
