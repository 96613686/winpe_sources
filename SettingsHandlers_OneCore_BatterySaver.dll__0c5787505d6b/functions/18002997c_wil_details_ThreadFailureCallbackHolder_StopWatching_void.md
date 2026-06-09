# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18002997c`
- end: `0x1800299e3`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ae5c`
- `0x180022e60`

## callees

- `0x18002997c`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029985`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029985`

## string_xrefs

- `0x1800299a1`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18002997c  push    rbx
0x18002997e  sub     rsp, 20h
0x180029982  mov     rbx, rcx
0x180029985  call    cs:__imp_GetCurrentThreadId
0x18002998b  cmp     [rbx+18h], eax
0x18002998e  jz      short loc_1800299AD
0x180029990  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180029997  test    rax, rax
0x18002999a  jz      short loc_1800299AD
0x18002999c  mov     rdx, [rsp+28h]
0x1800299a1  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800299a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299ad  mov     rcx, [rbx]
0x1800299b0  mov     dword ptr [rbx+18h], 0
0x1800299b7  jmp     short loc_1800299C5
0x1800299b9  cmp     rax, rbx
0x1800299bc  jz      short loc_1800299CF
0x1800299be  lea     rcx, [rax+10h]
0x1800299c2  mov     [rbx], rcx
0x1800299c5  mov     rax, [rcx]
0x1800299c8  test    rax, rax
0x1800299cb  jnz     short loc_1800299B9
0x1800299cd  jmp     short loc_1800299D6
0x1800299cf  mov     rax, [rbx+10h]
0x1800299d3  mov     [rcx], rax
0x1800299d6  mov     qword ptr [rbx], 0
0x1800299dd  add     rsp, 20h
0x1800299e1  pop     rbx
0x1800299e2  retn
```
