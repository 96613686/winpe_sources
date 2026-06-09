# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18000f524`
- end: `0x18000f58b`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c6b4`
- `0x18000d73c`
- `0x18000e2d8`
- `0x18001c7a0`

## callees

- `0x18000f524`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f52d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f52d`

## string_xrefs

- `0x18000f549`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StopWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  wil::details::ThreadFailureCallbackHolder **v2; // rcx
  wil::details::ThreadFailureCallbackHolder *v3; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_DWORD *)this + 6) != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
    wil::details::g_pfnReportFatalUsageError(
      "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
      retaddr);
  v2 = *(wil::details::ThreadFailureCallbackHolder ***)this;
  *((_DWORD *)this + 6) = 0;
  while ( 1 )
  {
    v3 = *v2;
    if ( !*v2 )
      break;
    if ( v3 == this )
    {
      *v2 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)this + 2);
      break;
    }
    v2 = (wil::details::ThreadFailureCallbackHolder **)((char *)v3 + 16);
    *(_QWORD *)this = (char *)v3 + 16;
  }
  *(_QWORD *)this = 0;
}

```

## disassembly

```asm
0x18000f524  push    rbx
0x18000f526  sub     rsp, 20h
0x18000f52a  mov     rbx, rcx
0x18000f52d  call    cs:__imp_GetCurrentThreadId
0x18000f533  cmp     [rbx+18h], eax
0x18000f536  jz      short loc_18000F555
0x18000f538  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000f53f  test    rax, rax
0x18000f542  jz      short loc_18000F555
0x18000f544  mov     rdx, [rsp+28h]
0x18000f549  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000f550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f555  mov     rcx, [rbx]
0x18000f558  mov     dword ptr [rbx+18h], 0
0x18000f55f  jmp     short loc_18000F56D
0x18000f561  cmp     rax, rbx
0x18000f564  jz      short loc_18000F577
0x18000f566  lea     rcx, [rax+10h]
0x18000f56a  mov     [rbx], rcx
0x18000f56d  mov     rax, [rcx]
0x18000f570  test    rax, rax
0x18000f573  jnz     short loc_18000F561
0x18000f575  jmp     short loc_18000F57E
0x18000f577  mov     rax, [rbx+10h]
0x18000f57b  mov     [rcx], rax
0x18000f57e  mov     qword ptr [rbx], 0
0x18000f585  add     rsp, 20h
0x18000f589  pop     rbx
0x18000f58a  retn
```
