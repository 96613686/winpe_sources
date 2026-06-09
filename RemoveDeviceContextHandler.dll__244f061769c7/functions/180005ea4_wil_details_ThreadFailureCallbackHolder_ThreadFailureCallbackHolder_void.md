# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x180005ea4`
- end: `0x180005f1c`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180005adc`
- `0x180007a10`
- `0x18000b5dc`

## callees

- `0x180005ea4`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005eba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005eba`

## string_xrefs

- `0x180005ed5`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
    v3 = *(wil::details::ThreadFailureCallbackHolder ***)this;
    *((_DWORD *)this + 6) = 0;
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
0x180005ea4  mov     [rsp+arg_0], rbx
0x180005ea9  push    rdi
0x180005eaa  sub     rsp, 20h
0x180005eae  cmp     dword ptr [rcx+18h], 0
0x180005eb2  mov     rdi, rcx
0x180005eb5  jz      short loc_180005F11
0x180005eb7  mov     ebx, [rcx+18h]
0x180005eba  call    cs:__imp_GetCurrentThreadId
0x180005ec0  cmp     ebx, eax
0x180005ec2  jz      short loc_180005EE1
0x180005ec4  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180005ecb  test    rax, rax
0x180005ece  jz      short loc_180005EE1
0x180005ed0  mov     rdx, [rsp+28h]
0x180005ed5  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180005edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ee1  mov     rcx, [rdi]
0x180005ee4  mov     dword ptr [rdi+18h], 0
0x180005eeb  jmp     short loc_180005EF9
0x180005eed  cmp     rax, rdi
0x180005ef0  jz      short loc_180005F03
0x180005ef2  lea     rcx, [rax+10h]
0x180005ef6  mov     [rdi], rcx
0x180005ef9  mov     rax, [rcx]
0x180005efc  test    rax, rax
0x180005eff  jnz     short loc_180005EED
0x180005f01  jmp     short loc_180005F0A
0x180005f03  mov     rax, [rdi+10h]
0x180005f07  mov     [rcx], rax
0x180005f0a  mov     qword ptr [rdi], 0
0x180005f11  mov     rbx, [rsp+28h+arg_0]
0x180005f16  add     rsp, 20h
0x180005f1a  pop     rdi
0x180005f1b  retn
```
