# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x140015328`
- end: `0x14001538f`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e260`
- `0x1400213f0`

## callees

- `0x140015328`
- `0x14004f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140015331`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140015331`

## string_xrefs

- `0x14001534d`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x140015328  push    rbx
0x14001532a  sub     rsp, 20h
0x14001532e  mov     rbx, rcx
0x140015331  call    cs:__imp_GetCurrentThreadId
0x140015337  cmp     [rbx+18h], eax
0x14001533a  jz      short loc_140015359
0x14001533c  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x140015343  test    rax, rax
0x140015346  jz      short loc_140015359
0x140015348  mov     rdx, [rsp+28h]
0x14001534d  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x140015354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015359  mov     rcx, [rbx]
0x14001535c  mov     dword ptr [rbx+18h], 0
0x140015363  jmp     short loc_140015371
0x140015365  cmp     rax, rbx
0x140015368  jz      short loc_14001537B
0x14001536a  lea     rcx, [rax+10h]
0x14001536e  mov     [rbx], rcx
0x140015371  mov     rax, [rcx]
0x140015374  test    rax, rax
0x140015377  jnz     short loc_140015365
0x140015379  jmp     short loc_140015382
0x14001537b  mov     rax, [rbx+10h]
0x14001537f  mov     [rcx], rax
0x140015382  mov     qword ptr [rbx], 0
0x140015389  add     rsp, 20h
0x14001538d  pop     rbx
0x14001538e  retn
```
