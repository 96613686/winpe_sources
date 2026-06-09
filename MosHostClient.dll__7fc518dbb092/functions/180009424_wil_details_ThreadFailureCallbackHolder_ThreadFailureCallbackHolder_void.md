# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x180009424`
- end: `0x18000949c`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008ebc`

## callees

- `0x180009424`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000943a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000943a`

## string_xrefs

- `0x180009455`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(
        wil::details::ThreadFailureCallbackHolder *this)
{
  int v2; // ebx
  wil::details::ThreadFailureCallbackHolder **v3; // rcx
  wil::details::ThreadFailureCallbackHolder *v4; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_DWORD *)this + 6) )
  {
    v2 = *((_DWORD *)this + 6);
    if ( v2 != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *((_DWORD *)this + 6) = 0;
    v3 = *(wil::details::ThreadFailureCallbackHolder ***)this;
    while ( 1 )
    {
      v4 = *v3;
      if ( !*v3 )
        break;
      if ( v4 == this )
      {
        *v3 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)this + 2);
        break;
      }
      v3 = (wil::details::ThreadFailureCallbackHolder **)((char *)v4 + 16);
      *(_QWORD *)this = (char *)v4 + 16;
    }
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180009424  mov     [rsp+arg_0], rbx
0x180009429  push    rdi
0x18000942a  sub     rsp, 20h
0x18000942e  mov     rdi, rcx
0x180009431  cmp     dword ptr [rcx+18h], 0
0x180009435  jz      short loc_180009491
0x180009437  mov     ebx, [rcx+18h]
0x18000943a  call    cs:__imp_GetCurrentThreadId
0x180009440  cmp     ebx, eax
0x180009442  jz      short loc_180009461
0x180009444  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000944b  test    rax, rax
0x18000944e  jz      short loc_180009461
0x180009450  mov     rdx, [rsp+28h]
0x180009455  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000945c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009461  mov     dword ptr [rdi+18h], 0
0x180009468  mov     rcx, [rdi]
0x18000946b  jmp     short loc_180009479
0x18000946d  cmp     rax, rdi
0x180009470  jz      short loc_180009483
0x180009472  lea     rcx, [rax+10h]
0x180009476  mov     [rdi], rcx
0x180009479  mov     rax, [rcx]
0x18000947c  test    rax, rax
0x18000947f  jnz     short loc_18000946D
0x180009481  jmp     short loc_18000948A
0x180009483  mov     rax, [rdi+10h]
0x180009487  mov     [rcx], rax
0x18000948a  mov     qword ptr [rdi], 0
0x180009491  mov     rbx, [rsp+28h+arg_0]
0x180009496  add     rsp, 20h
0x18000949a  pop     rdi
0x18000949b  retn
```
