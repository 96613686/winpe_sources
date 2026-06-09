# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180016b38`
- end: `0x180016b9f`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800125e8`
- `0x180013aa4`

## callees

- `0x180016b38`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016b41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016b41`

## string_xrefs

- `0x180016b5d`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180016b38  push    rbx
0x180016b3a  sub     rsp, 20h
0x180016b3e  mov     rbx, rcx
0x180016b41  call    cs:__imp_GetCurrentThreadId
0x180016b47  cmp     [rbx+18h], eax
0x180016b4a  jz      short loc_180016B69
0x180016b4c  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180016b53  test    rax, rax
0x180016b56  jz      short loc_180016B69
0x180016b58  mov     rdx, [rsp+28h]
0x180016b5d  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180016b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b69  mov     rcx, [rbx]
0x180016b6c  mov     dword ptr [rbx+18h], 0
0x180016b73  jmp     short loc_180016B81
0x180016b75  cmp     rax, rbx
0x180016b78  jz      short loc_180016B8B
0x180016b7a  lea     rcx, [rax+10h]
0x180016b7e  mov     [rbx], rcx
0x180016b81  mov     rax, [rcx]
0x180016b84  test    rax, rax
0x180016b87  jnz     short loc_180016B75
0x180016b89  jmp     short loc_180016B92
0x180016b8b  mov     rax, [rbx+10h]
0x180016b8f  mov     [rcx], rax
0x180016b92  mov     qword ptr [rbx], 0
0x180016b99  add     rsp, 20h
0x180016b9d  pop     rbx
0x180016b9e  retn
```
