# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18001af5c`
- end: `0x18001afc3`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180011bd0`
- `0x180015bf0`

## callees

- `0x18001af5c`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001af65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001af65`

## string_xrefs

- `0x18001af81`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18001af5c  push    rbx
0x18001af5e  sub     rsp, 20h
0x18001af62  mov     rbx, rcx
0x18001af65  call    cs:__imp_GetCurrentThreadId
0x18001af6b  cmp     [rbx+18h], eax
0x18001af6e  jz      short loc_18001AF8D
0x18001af70  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18001af77  test    rax, rax
0x18001af7a  jz      short loc_18001AF8D
0x18001af7c  mov     rdx, [rsp+28h]
0x18001af81  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18001af88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af8d  mov     rcx, [rbx]
0x18001af90  mov     dword ptr [rbx+18h], 0
0x18001af97  jmp     short loc_18001AFA5
0x18001af99  cmp     rax, rbx
0x18001af9c  jz      short loc_18001AFAF
0x18001af9e  lea     rcx, [rax+10h]
0x18001afa2  mov     [rbx], rcx
0x18001afa5  mov     rax, [rcx]
0x18001afa8  test    rax, rax
0x18001afab  jnz     short loc_18001AF99
0x18001afad  jmp     short loc_18001AFB6
0x18001afaf  mov     rax, [rbx+10h]
0x18001afb3  mov     [rcx], rax
0x18001afb6  mov     qword ptr [rbx], 0
0x18001afbd  add     rsp, 20h
0x18001afc1  pop     rbx
0x18001afc2  retn
```
