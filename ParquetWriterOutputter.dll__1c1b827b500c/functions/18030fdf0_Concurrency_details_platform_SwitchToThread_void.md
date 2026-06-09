# Concurrency::details::platform::__SwitchToThread(void)

- ea: `0x18030fdf0`
- end: `0x18030fdf7`
- name: `?__SwitchToThread@platform@details@Concurrency@@YAXXZ`
- size: `7`
- prototype: `BOOL __stdcall()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1803102b0`
- `0x1803190fc`
- `0x1803201e0`
- `0x180326a90`

## import_xrefs

- `KERNEL32!SwitchToThread` at `0x18030fdf0`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall Concurrency::details::platform::__SwitchToThread()
{
  return SwitchToThread();
}

```

## disassembly

```asm
0x18030fdf0  jmp     cs:__imp_SwitchToThread
```
