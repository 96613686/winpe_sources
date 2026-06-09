# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180026af8`
- end: `0x180026b66`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `110`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180024834`
- `0x180026ad4`

## callees

- `0x180026af8`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026b01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026b01`

## string_xrefs

- `0x180026b23`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180026af8  push    rbx
0x180026afa  sub     rsp, 20h
0x180026afe  mov     rbx, rcx
0x180026b01  call    cs:__imp_GetCurrentThreadId
0x180026b08  nop     dword ptr [rax+rax+00h]
0x180026b0d  cmp     [rbx+18h], eax
0x180026b10  jz      short loc_180026B2F
0x180026b12  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180026b19  test    rax, rax
0x180026b1c  jz      short loc_180026B2F
0x180026b1e  mov     rdx, [rsp+28h]
0x180026b23  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180026b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b2f  mov     rcx, [rbx]
0x180026b32  mov     dword ptr [rbx+18h], 0
0x180026b39  jmp     short loc_180026B47
0x180026b3b  cmp     rax, rbx
0x180026b3e  jz      short loc_180026B51
0x180026b40  lea     rcx, [rax+10h]
0x180026b44  mov     [rbx], rcx
0x180026b47  mov     rax, [rcx]
0x180026b4a  test    rax, rax
0x180026b4d  jnz     short loc_180026B3B
0x180026b4f  jmp     short loc_180026B58
0x180026b51  mov     rax, [rbx+10h]
0x180026b55  mov     [rcx], rax
0x180026b58  mov     qword ptr [rbx], 0
0x180026b5f  add     rsp, 20h
0x180026b63  pop     rbx
0x180026b64  retn
```
