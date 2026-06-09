# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x1400298d8`
- end: `0x14002993f`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000fed8`
- `0x14001e974`

## callees

- `0x1400298d8`
- `0x140070010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400298e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400298e1`

## string_xrefs

- `0x1400298fd`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x1400298d8  push    rbx
0x1400298da  sub     rsp, 20h
0x1400298de  mov     rbx, rcx
0x1400298e1  call    cs:__imp_GetCurrentThreadId
0x1400298e7  cmp     [rbx+18h], eax
0x1400298ea  jz      short loc_140029909
0x1400298ec  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1400298f3  test    rax, rax
0x1400298f6  jz      short loc_140029909
0x1400298f8  mov     rdx, [rsp+28h]
0x1400298fd  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x140029904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029909  mov     rcx, [rbx]
0x14002990c  mov     dword ptr [rbx+18h], 0
0x140029913  jmp     short loc_140029921
0x140029915  cmp     rax, rbx
0x140029918  jz      short loc_14002992B
0x14002991a  lea     rcx, [rax+10h]
0x14002991e  mov     [rbx], rcx
0x140029921  mov     rax, [rcx]
0x140029924  test    rax, rax
0x140029927  jnz     short loc_140029915
0x140029929  jmp     short loc_140029932
0x14002992b  mov     rax, [rbx+10h]
0x14002992f  mov     [rcx], rax
0x140029932  mov     qword ptr [rbx], 0
0x140029939  add     rsp, 20h
0x14002993d  pop     rbx
0x14002993e  retn
```
