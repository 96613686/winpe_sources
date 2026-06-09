# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180031950`
- end: `0x1800319b7`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180028bac`
- `0x18002d5a0`

## callees

- `0x180031950`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031959`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031959`

## string_xrefs

- `0x180031975`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180031950  push    rbx
0x180031952  sub     rsp, 20h
0x180031956  mov     rbx, rcx
0x180031959  call    cs:__imp_GetCurrentThreadId
0x18003195f  cmp     [rbx+18h], eax
0x180031962  jz      short loc_180031981
0x180031964  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18003196b  test    rax, rax
0x18003196e  jz      short loc_180031981
0x180031970  mov     rdx, [rsp+28h]
0x180031975  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18003197c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031981  mov     rcx, [rbx]
0x180031984  mov     dword ptr [rbx+18h], 0
0x18003198b  jmp     short loc_180031999
0x18003198d  cmp     rax, rbx
0x180031990  jz      short loc_1800319A3
0x180031992  lea     rcx, [rax+10h]
0x180031996  mov     [rbx], rcx
0x180031999  mov     rax, [rcx]
0x18003199c  test    rax, rax
0x18003199f  jnz     short loc_18003198D
0x1800319a1  jmp     short loc_1800319AA
0x1800319a3  mov     rax, [rbx+10h]
0x1800319a7  mov     [rcx], rax
0x1800319aa  mov     qword ptr [rbx], 0
0x1800319b1  add     rsp, 20h
0x1800319b5  pop     rbx
0x1800319b6  retn
```
