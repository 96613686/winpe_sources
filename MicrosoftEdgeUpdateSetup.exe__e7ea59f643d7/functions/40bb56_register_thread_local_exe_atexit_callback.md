# __register_thread_local_exe_atexit_callback

- ea: `0x40bb56`
- end: `0x40bb7c`
- name: `__register_thread_local_exe_atexit_callback`
- size: `38`
- prototype: `void __cdecl(_tls_callback_type Callback)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x408282`

## callees

- `0x40b23d`
- `0x40c24f`

## pseudocode

```c
void __cdecl _register_thread_local_exe_atexit_callback(_tls_callback_type Callback)
{
  if ( dword_426E60 != __security_cookie )
    terminate();
  dword_426E60 = unknown_libname_3(Callback);
}

```

## disassembly

```asm
0x40bb56  mov     edi, edi
0x40bb58  push    ebp
0x40bb59  mov     ebp, esp
0x40bb5b  mov     eax, dword_426E60
0x40bb60  cmp     eax, ___security_cookie
0x40bb66  jnz     _terminate
0x40bb6c  push    [ebp+Callback]
0x40bb6f  call    unknown_libname_3; Microsoft VisualC universal runtime
0x40bb74  pop     ecx
0x40bb75  mov     dword_426E60, eax
0x40bb7a  pop     ebp
0x40bb7b  retn
```
