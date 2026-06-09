# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180028d40`
- end: `0x180028dae`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `110`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180022ab4`
- `0x18002394c`
- `0x180023974`
- `0x180026558`

## callees

- `0x180028d40`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028d49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028d49`

## string_xrefs

- `0x180028d6b`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180028d40  push    rbx
0x180028d42  sub     rsp, 20h
0x180028d46  mov     rbx, rcx
0x180028d49  call    cs:__imp_GetCurrentThreadId
0x180028d50  nop     dword ptr [rax+rax+00h]
0x180028d55  cmp     [rbx+18h], eax
0x180028d58  jz      short loc_180028D77
0x180028d5a  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180028d61  test    rax, rax
0x180028d64  jz      short loc_180028D77
0x180028d66  mov     rdx, [rsp+28h]
0x180028d6b  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180028d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d77  mov     rcx, [rbx]
0x180028d7a  mov     dword ptr [rbx+18h], 0
0x180028d81  jmp     short loc_180028D8F
0x180028d83  cmp     rax, rbx
0x180028d86  jz      short loc_180028D99
0x180028d88  lea     rcx, [rax+10h]
0x180028d8c  mov     [rbx], rcx
0x180028d8f  mov     rax, [rcx]
0x180028d92  test    rax, rax
0x180028d95  jnz     short loc_180028D83
0x180028d97  jmp     short loc_180028DA0
0x180028d99  mov     rax, [rbx+10h]
0x180028d9d  mov     [rcx], rax
0x180028da0  mov     qword ptr [rbx], 0
0x180028da7  add     rsp, 20h
0x180028dab  pop     rbx
0x180028dac  retn
```
