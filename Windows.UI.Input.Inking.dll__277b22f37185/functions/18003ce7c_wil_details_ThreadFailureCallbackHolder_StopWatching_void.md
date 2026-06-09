# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18003ce7c`
- end: `0x18003cee3`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180038910`
- `0x180039120`
- `0x18003913c`
- `0x18003aa80`

## callees

- `0x18003ce7c`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ce85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ce85`

## string_xrefs

- `0x18003cea1`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18003ce7c  push    rbx
0x18003ce7e  sub     rsp, 20h
0x18003ce82  mov     rbx, rcx
0x18003ce85  call    cs:__imp_GetCurrentThreadId
0x18003ce8b  cmp     [rbx+18h], eax
0x18003ce8e  jz      short loc_18003CEAD
0x18003ce90  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18003ce97  test    rax, rax
0x18003ce9a  jz      short loc_18003CEAD
0x18003ce9c  mov     rdx, [rsp+28h]
0x18003cea1  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18003cea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cead  mov     rcx, [rbx]
0x18003ceb0  mov     dword ptr [rbx+18h], 0
0x18003ceb7  jmp     short loc_18003CEC5
0x18003ceb9  cmp     rax, rbx
0x18003cebc  jz      short loc_18003CECF
0x18003cebe  lea     rcx, [rax+10h]
0x18003cec2  mov     [rbx], rcx
0x18003cec5  mov     rax, [rcx]
0x18003cec8  test    rax, rax
0x18003cecb  jnz     short loc_18003CEB9
0x18003cecd  jmp     short loc_18003CED6
0x18003cecf  mov     rax, [rbx+10h]
0x18003ced3  mov     [rcx], rax
0x18003ced6  mov     qword ptr [rbx], 0
0x18003cedd  add     rsp, 20h
0x18003cee1  pop     rbx
0x18003cee2  retn
```
