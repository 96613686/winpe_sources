# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180006c74`
- end: `0x180006cdb`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008ddc`
- `0x18000a1b4`

## callees

- `0x180006c74`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006c7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006c7d`

## string_xrefs

- `0x180006c99`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180006c74  push    rbx
0x180006c76  sub     rsp, 20h
0x180006c7a  mov     rbx, rcx
0x180006c7d  call    cs:__imp_GetCurrentThreadId
0x180006c83  cmp     [rbx+18h], eax
0x180006c86  jz      short loc_180006CA5
0x180006c88  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180006c8f  test    rax, rax
0x180006c92  jz      short loc_180006CA5
0x180006c94  mov     rdx, [rsp+28h]
0x180006c99  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180006ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ca5  mov     rcx, [rbx]
0x180006ca8  mov     dword ptr [rbx+18h], 0
0x180006caf  jmp     short loc_180006CBD
0x180006cb1  cmp     rax, rbx
0x180006cb4  jz      short loc_180006CC7
0x180006cb6  lea     rcx, [rax+10h]
0x180006cba  mov     [rbx], rcx
0x180006cbd  mov     rax, [rcx]
0x180006cc0  test    rax, rax
0x180006cc3  jnz     short loc_180006CB1
0x180006cc5  jmp     short loc_180006CCE
0x180006cc7  mov     rax, [rbx+10h]
0x180006ccb  mov     [rcx], rax
0x180006cce  mov     qword ptr [rbx], 0
0x180006cd5  add     rsp, 20h
0x180006cd9  pop     rbx
0x180006cda  retn
```
