# Pal::ThreadStaticImplWindows::getCurrentThreadId(void)

- ea: `0x180017460`
- end: `0x180017467`
- name: `?getCurrentThreadId@ThreadStaticImplWindows@Pal@@UEAAJXZ`
- size: `7`
- prototype: `DWORD __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017460`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall Pal::ThreadStaticImplWindows::getCurrentThreadId()
{
  return GetCurrentThreadId();
}

```

## disassembly

```asm
0x180017460  jmp     cs:__imp_GetCurrentThreadId
```
