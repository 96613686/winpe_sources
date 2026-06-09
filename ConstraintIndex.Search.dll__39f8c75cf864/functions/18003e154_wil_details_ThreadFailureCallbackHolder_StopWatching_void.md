# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18003e154`
- end: `0x18003e1bb`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18003aa58`
- `0x18003bf74`
- `0x180082dc8`
- `0x1800cd444`

## callees

- `0x18003e154`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e15d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e15d`

## string_xrefs

- `0x18003e179`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18003e154  push    rbx
0x18003e156  sub     rsp, 20h
0x18003e15a  mov     rbx, rcx
0x18003e15d  call    cs:__imp_GetCurrentThreadId
0x18003e163  cmp     [rbx+18h], eax
0x18003e166  jz      short loc_18003E185
0x18003e168  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18003e16f  test    rax, rax
0x18003e172  jz      short loc_18003E185
0x18003e174  mov     rdx, [rsp+28h]
0x18003e179  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18003e180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e185  mov     rcx, [rbx]
0x18003e188  mov     dword ptr [rbx+18h], 0
0x18003e18f  jmp     short loc_18003E19D
0x18003e191  cmp     rax, rbx
0x18003e194  jz      short loc_18003E1A7
0x18003e196  lea     rcx, [rax+10h]
0x18003e19a  mov     [rbx], rcx
0x18003e19d  mov     rax, [rcx]
0x18003e1a0  test    rax, rax
0x18003e1a3  jnz     short loc_18003E191
0x18003e1a5  jmp     short loc_18003E1AE
0x18003e1a7  mov     rax, [rbx+10h]
0x18003e1ab  mov     [rcx], rax
0x18003e1ae  mov     qword ptr [rbx], 0
0x18003e1b5  add     rsp, 20h
0x18003e1b9  pop     rbx
0x18003e1ba  retn
```
