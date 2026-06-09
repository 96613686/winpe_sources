# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180017bd0`
- end: `0x180017c37`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ab30`
- `0x18000ac9c`
- `0x18000c570`
- `0x18000c798`
- `0x18000c84c`
- `0x180011e60`
- `0x180016ee4`

## callees

- `0x180017bd0`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017bd9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017bd9`

## string_xrefs

- `0x180017bf5`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180017bd0  push    rbx
0x180017bd2  sub     rsp, 20h
0x180017bd6  mov     rbx, rcx
0x180017bd9  call    cs:__imp_GetCurrentThreadId
0x180017bdf  cmp     [rbx+18h], eax
0x180017be2  jz      short loc_180017C01
0x180017be4  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180017beb  test    rax, rax
0x180017bee  jz      short loc_180017C01
0x180017bf0  mov     rdx, [rsp+28h]
0x180017bf5  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180017bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c01  mov     rcx, [rbx]
0x180017c04  mov     dword ptr [rbx+18h], 0
0x180017c0b  jmp     short loc_180017C19
0x180017c0d  cmp     rax, rbx
0x180017c10  jz      short loc_180017C23
0x180017c12  lea     rcx, [rax+10h]
0x180017c16  mov     [rbx], rcx
0x180017c19  mov     rax, [rcx]
0x180017c1c  test    rax, rax
0x180017c1f  jnz     short loc_180017C0D
0x180017c21  jmp     short loc_180017C2A
0x180017c23  mov     rax, [rbx+10h]
0x180017c27  mov     [rcx], rax
0x180017c2a  mov     qword ptr [rbx], 0
0x180017c31  add     rsp, 20h
0x180017c35  pop     rbx
0x180017c36  retn
```
