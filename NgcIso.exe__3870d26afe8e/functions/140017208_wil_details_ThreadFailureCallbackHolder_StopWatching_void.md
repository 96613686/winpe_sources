# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x140017208`
- end: `0x14001726f`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140016278`
- `0x14001648c`

## callees

- `0x140017208`
- `0x140071010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140017211`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140017211`

## string_xrefs

- `0x14001722d`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x140017208  push    rbx
0x14001720a  sub     rsp, 20h
0x14001720e  mov     rbx, rcx
0x140017211  call    cs:__imp_GetCurrentThreadId
0x140017217  cmp     [rbx+18h], eax
0x14001721a  jz      short loc_140017239
0x14001721c  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x140017223  test    rax, rax
0x140017226  jz      short loc_140017239
0x140017228  mov     rdx, [rsp+28h]
0x14001722d  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x140017234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017239  mov     rcx, [rbx]
0x14001723c  mov     dword ptr [rbx+18h], 0
0x140017243  jmp     short loc_140017251
0x140017245  cmp     rax, rbx
0x140017248  jz      short loc_14001725B
0x14001724a  lea     rcx, [rax+10h]
0x14001724e  mov     [rbx], rcx
0x140017251  mov     rax, [rcx]
0x140017254  test    rax, rax
0x140017257  jnz     short loc_140017245
0x140017259  jmp     short loc_140017262
0x14001725b  mov     rax, [rbx+10h]
0x14001725f  mov     [rcx], rax
0x140017262  mov     qword ptr [rbx], 0
0x140017269  add     rsp, 20h
0x14001726d  pop     rbx
0x14001726e  retn
```
