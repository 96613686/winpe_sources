# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18000eb6c`
- end: `0x18000ebd3`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d96c`
- `0x18000db78`

## callees

- `0x18000eb6c`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eb75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eb75`

## string_xrefs

- `0x18000eb91`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18000eb6c  push    rbx
0x18000eb6e  sub     rsp, 20h
0x18000eb72  mov     rbx, rcx
0x18000eb75  call    cs:__imp_GetCurrentThreadId
0x18000eb7b  cmp     [rbx+18h], eax
0x18000eb7e  jz      short loc_18000EB9D
0x18000eb80  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000eb87  test    rax, rax
0x18000eb8a  jz      short loc_18000EB9D
0x18000eb8c  mov     rdx, [rsp+28h]
0x18000eb91  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000eb98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb9d  mov     rcx, [rbx]
0x18000eba0  mov     dword ptr [rbx+18h], 0
0x18000eba7  jmp     short loc_18000EBB5
0x18000eba9  cmp     rax, rbx
0x18000ebac  jz      short loc_18000EBBF
0x18000ebae  lea     rcx, [rax+10h]
0x18000ebb2  mov     [rbx], rcx
0x18000ebb5  mov     rax, [rcx]
0x18000ebb8  test    rax, rax
0x18000ebbb  jnz     short loc_18000EBA9
0x18000ebbd  jmp     short loc_18000EBC6
0x18000ebbf  mov     rax, [rbx+10h]
0x18000ebc3  mov     [rcx], rax
0x18000ebc6  mov     qword ptr [rbx], 0
0x18000ebcd  add     rsp, 20h
0x18000ebd1  pop     rbx
0x18000ebd2  retn
```
