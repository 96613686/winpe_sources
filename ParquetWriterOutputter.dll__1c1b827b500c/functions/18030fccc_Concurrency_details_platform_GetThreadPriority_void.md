# Concurrency::details::platform::__GetThreadPriority(void *)

- ea: `0x18030fccc`
- end: `0x18030fcd3`
- name: `?__GetThreadPriority@platform@details@Concurrency@@YAHPEAX@Z`
- size: `7`
- prototype: `int __stdcall(HANDLE hThread)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18031dc94`

## import_xrefs

- `KERNEL32!GetThreadPriority` at `0x18030fccc`

## pseudocode

```c
// attributes: thunk
int __stdcall Concurrency::details::platform::__GetThreadPriority(HANDLE hThread)
{
  return GetThreadPriority(hThread);
}

```

## disassembly

```asm
0x18030fccc  jmp     cs:__imp_GetThreadPriority
```
