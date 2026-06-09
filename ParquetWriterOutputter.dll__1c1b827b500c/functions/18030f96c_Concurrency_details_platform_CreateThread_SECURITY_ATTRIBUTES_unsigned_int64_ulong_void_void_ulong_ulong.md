# Concurrency::details::platform::__CreateThread(_SECURITY_ATTRIBUTES *,unsigned __int64,ulong (*)(void *),void *,ulong,ulong *)

- ea: `0x18030f96c`
- end: `0x18030f973`
- name: `?__CreateThread@platform@details@Concurrency@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@_KP6AKPEAX@Z2KPEAK@Z`
- size: `7`
- prototype: `HANDLE __stdcall(LPSECURITY_ATTRIBUTES lpThreadAttributes, SIZE_T dwStackSize, LPTHREAD_START_ROUTINE lpStartAddress, LPVOID lpParameter, DWORD dwCreationFlags, LPDWORD lpThreadId)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18030ffb8`

## import_xrefs

- `KERNEL32!CreateThread` at `0x18030f96c`

## pseudocode

```c
// attributes: thunk
HANDLE __stdcall Concurrency::details::platform::__CreateThread(
        LPSECURITY_ATTRIBUTES lpThreadAttributes,
        SIZE_T dwStackSize,
        LPTHREAD_START_ROUTINE lpStartAddress,
        LPVOID lpParameter,
        DWORD dwCreationFlags,
        LPDWORD lpThreadId)
{
  return CreateThread(lpThreadAttributes, dwStackSize, lpStartAddress, lpParameter, dwCreationFlags, lpThreadId);
}

```

## disassembly

```asm
0x18030f96c  jmp     cs:__imp_CreateThread
```
