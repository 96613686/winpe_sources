# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180035080`
- end: `0x1800350e7`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x180005828`
- `0x18000f594`
- `0x1800101d0`
- `0x180010478`
- `0x180025e78`
- `0x180026580`
- `0x180027e08`
- `0x180027ee0`
- `0x180033cbc`
- `0x18003505c`
- `0x180038728`
- `0x18004e118`
- `0x18004eca0`
- `0x18004ed90`

## callees

- `0x180035080`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035089`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035089`

## string_xrefs

- `0x1800350a5`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180035080  push    rbx
0x180035082  sub     rsp, 20h
0x180035086  mov     rbx, rcx
0x180035089  call    cs:__imp_GetCurrentThreadId
0x18003508f  cmp     [rbx+18h], eax
0x180035092  jz      short loc_1800350B1
0x180035094  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18003509b  test    rax, rax
0x18003509e  jz      short loc_1800350B1
0x1800350a0  mov     rdx, [rsp+28h]
0x1800350a5  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800350ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800350b1  mov     rcx, [rbx]
0x1800350b4  mov     dword ptr [rbx+18h], 0
0x1800350bb  jmp     short loc_1800350C9
0x1800350bd  cmp     rax, rbx
0x1800350c0  jz      short loc_1800350D3
0x1800350c2  lea     rcx, [rax+10h]
0x1800350c6  mov     [rbx], rcx
0x1800350c9  mov     rax, [rcx]
0x1800350cc  test    rax, rax
0x1800350cf  jnz     short loc_1800350BD
0x1800350d1  jmp     short loc_1800350DA
0x1800350d3  mov     rax, [rbx+10h]
0x1800350d7  mov     [rcx], rax
0x1800350da  mov     qword ptr [rbx], 0
0x1800350e1  add     rsp, 20h
0x1800350e5  pop     rbx
0x1800350e6  retn
```
