# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x40ebc0`
- end: `0x40ebca`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `10`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x40bfd7`

## pseudocode

```c
void __cdecl wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__()
{
  wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(wil::details::g_threadFailureCallbacks);
}

```

## disassembly

```asm
0x40ebc0  mov     ecx, offset ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x40ebc5  jmp     ??1?$ThreadLocalStorage@PAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QAE@XZ; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)
```
