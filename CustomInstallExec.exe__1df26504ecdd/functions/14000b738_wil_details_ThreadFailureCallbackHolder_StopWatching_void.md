# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x14000b738`
- end: `0x14000b79f`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400085bc`
- `0x140009730`

## callees

- `0x14000b738`
- `0x14000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b741`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b741`

## string_xrefs

- `0x14000b75d`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x14000b738  push    rbx
0x14000b73a  sub     rsp, 20h
0x14000b73e  mov     rbx, rcx
0x14000b741  call    cs:__imp_GetCurrentThreadId
0x14000b747  cmp     [rbx+18h], eax
0x14000b74a  jz      short loc_14000B769
0x14000b74c  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x14000b753  test    rax, rax
0x14000b756  jz      short loc_14000B769
0x14000b758  mov     rdx, [rsp+28h]
0x14000b75d  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x14000b764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b769  mov     rcx, [rbx]
0x14000b76c  mov     dword ptr [rbx+18h], 0
0x14000b773  jmp     short loc_14000B781
0x14000b775  cmp     rax, rbx
0x14000b778  jz      short loc_14000B78B
0x14000b77a  lea     rcx, [rax+10h]
0x14000b77e  mov     [rbx], rcx
0x14000b781  mov     rax, [rcx]
0x14000b784  test    rax, rax
0x14000b787  jnz     short loc_14000B775
0x14000b789  jmp     short loc_14000B792
0x14000b78b  mov     rax, [rbx+10h]
0x14000b78f  mov     [rcx], rax
0x14000b792  mov     qword ptr [rbx], 0
0x14000b799  add     rsp, 20h
0x14000b79d  pop     rbx
0x14000b79e  retn
```
