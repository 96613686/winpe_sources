# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x18001a948`
- end: `0x18001a9c0`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180025460`

## callees

- `0x18001a948`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a95e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a95e`

## string_xrefs

- `0x18001a979`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18001a948  mov     [rsp+arg_0], rbx
0x18001a94d  push    rdi
0x18001a94e  sub     rsp, 20h
0x18001a952  mov     rdi, rcx
0x18001a955  cmp     dword ptr [rcx+18h], 0
0x18001a959  jz      short loc_18001A9B5
0x18001a95b  mov     ebx, [rcx+18h]
0x18001a95e  call    cs:__imp_GetCurrentThreadId
0x18001a964  cmp     ebx, eax
0x18001a966  jz      short loc_18001A985
0x18001a968  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18001a96f  test    rax, rax
0x18001a972  jz      short loc_18001A985
0x18001a974  mov     rdx, [rsp+28h]
0x18001a979  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18001a980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a985  mov     dword ptr [rdi+18h], 0
0x18001a98c  mov     rcx, [rdi]
0x18001a98f  jmp     short loc_18001A99D
0x18001a991  cmp     rax, rdi
0x18001a994  jz      short loc_18001A9A7
0x18001a996  lea     rcx, [rax+10h]
0x18001a99a  mov     [rdi], rcx
0x18001a99d  mov     rax, [rcx]
0x18001a9a0  test    rax, rax
0x18001a9a3  jnz     short loc_18001A991
0x18001a9a5  jmp     short loc_18001A9AE
0x18001a9a7  mov     rax, [rdi+10h]
0x18001a9ab  mov     [rcx], rax
0x18001a9ae  mov     qword ptr [rdi], 0
0x18001a9b5  mov     rbx, [rsp+28h+arg_0]
0x18001a9ba  add     rsp, 20h
0x18001a9be  pop     rdi
0x18001a9bf  retn
```
