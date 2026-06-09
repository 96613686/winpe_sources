# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18001838c`
- end: `0x1800183f3`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800124e0`
- `0x18001256c`
- `0x180015540`

## callees

- `0x18001838c`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018395`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018395`

## string_xrefs

- `0x1800183b1`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18001838c  push    rbx
0x18001838e  sub     rsp, 20h
0x180018392  mov     rbx, rcx
0x180018395  call    cs:__imp_GetCurrentThreadId
0x18001839b  cmp     [rbx+18h], eax
0x18001839e  jz      short loc_1800183BD
0x1800183a0  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800183a7  test    rax, rax
0x1800183aa  jz      short loc_1800183BD
0x1800183ac  mov     rdx, [rsp+28h]
0x1800183b1  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800183b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183bd  mov     rcx, [rbx]
0x1800183c0  mov     dword ptr [rbx+18h], 0
0x1800183c7  jmp     short loc_1800183D5
0x1800183c9  cmp     rax, rbx
0x1800183cc  jz      short loc_1800183DF
0x1800183ce  lea     rcx, [rax+10h]
0x1800183d2  mov     [rbx], rcx
0x1800183d5  mov     rax, [rcx]
0x1800183d8  test    rax, rax
0x1800183db  jnz     short loc_1800183C9
0x1800183dd  jmp     short loc_1800183E6
0x1800183df  mov     rax, [rbx+10h]
0x1800183e3  mov     [rcx], rax
0x1800183e6  mov     qword ptr [rbx], 0
0x1800183ed  add     rsp, 20h
0x1800183f1  pop     rbx
0x1800183f2  retn
```
