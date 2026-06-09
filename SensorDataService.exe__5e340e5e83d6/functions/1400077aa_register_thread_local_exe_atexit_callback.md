# _register_thread_local_exe_atexit_callback

- ea: `0x1400077aa`
- end: `0x1400077b0`
- name: `_register_thread_local_exe_atexit_callback`
- size: `6`
- prototype: `void __cdecl(_tls_callback_type Callback)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140006da0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_register_thread_local_exe_atexit_callback` at `0x1400077aa`

## pseudocode

```c
// attributes: thunk
void __cdecl register_thread_local_exe_atexit_callback(_tls_callback_type Callback)
{
  _register_thread_local_exe_atexit_callback(Callback);
}

```

## disassembly

```asm
0x1400077aa  jmp     cs:__imp__register_thread_local_exe_atexit_callback
```
