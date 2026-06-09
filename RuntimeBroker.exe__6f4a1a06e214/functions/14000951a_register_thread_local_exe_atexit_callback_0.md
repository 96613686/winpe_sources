# _register_thread_local_exe_atexit_callback_0

- ea: `0x14000951a`
- end: `0x140009520`
- name: `_register_thread_local_exe_atexit_callback_0`
- size: `6`
- prototype: `void __cdecl(_tls_callback_type Callback)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140008ad0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_register_thread_local_exe_atexit_callback` at `0x14000951a`

## pseudocode

```c
// attributes: thunk
void __cdecl register_thread_local_exe_atexit_callback_0(_tls_callback_type Callback)
{
  _register_thread_local_exe_atexit_callback(Callback);
}

```

## disassembly

```asm
0x14000951a  jmp     cs:__imp__register_thread_local_exe_atexit_callback
```
