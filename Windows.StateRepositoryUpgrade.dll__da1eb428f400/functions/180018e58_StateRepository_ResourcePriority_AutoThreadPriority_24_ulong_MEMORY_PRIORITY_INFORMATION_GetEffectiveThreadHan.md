# StateRepository::ResourcePriority::AutoThreadPriority<24,ulong,_MEMORY_PRIORITY_INFORMATION>::GetEffectiveThreadHandle(void)

- ea: `0x180018e58`
- end: `0x180018e7a`
- name: `?GetEffectiveThreadHandle@?$AutoThreadPriority@$0BI@KU_MEMORY_PRIORITY_INFORMATION@@@ResourcePriority@StateRepository@@IEAAPEAXXZ`
- size: `34`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180019f90`
- `0x180019fe4`
- `0x18001a038`
- `0x180029bfc`
- `0x180029c5c`
- `0x180029cbc`

## callees

- `0x180018e58`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018e69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018e69`

## pseudocode

```c
HANDLE __fastcall StateRepository::ResourcePriority::AutoThreadPriority<24,unsigned long,_MEMORY_PRIORITY_INFORMATION>::GetEffectiveThreadHandle(
        __int64 *a1)
{
  __int64 v1; // rdx

  v1 = *a1;
  if ( (unsigned __int64)(*a1 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return GetCurrentThread();
  return (HANDLE)v1;
}

```

## disassembly

```asm
0x180018e58  sub     rsp, 28h
0x180018e5c  mov     rdx, [rcx]
0x180018e5f  lea     rax, [rdx-1]
0x180018e63  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180018e67  jbe     short loc_180018E72
0x180018e69  call    cs:__imp_GetCurrentThread
0x180018e6f  mov     rdx, rax
0x180018e72  mov     rax, rdx
0x180018e75  add     rsp, 28h
0x180018e79  retn
```
