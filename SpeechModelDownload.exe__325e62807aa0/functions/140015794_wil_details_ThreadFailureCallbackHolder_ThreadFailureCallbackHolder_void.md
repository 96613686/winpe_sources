# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x140015794`
- end: `0x14001580c`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x1400152d8`
- `0x140015588`
- `0x140016758`
- `0x1400171cc`
- `0x1400172f8`
- `0x14001747c`
- `0x1400177a0`
- `0x140018a94`
- `0x140018cdc`

## callees

- `0x140015794`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400157aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400157aa`

## string_xrefs

- `0x1400157c5`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x140015794  mov     [rsp+arg_0], rbx
0x140015799  push    rdi
0x14001579a  sub     rsp, 20h
0x14001579e  mov     rdi, rcx
0x1400157a1  cmp     dword ptr [rcx+18h], 0
0x1400157a5  jz      short loc_140015801
0x1400157a7  mov     ebx, [rcx+18h]
0x1400157aa  call    cs:__imp_GetCurrentThreadId
0x1400157b0  cmp     ebx, eax
0x1400157b2  jz      short loc_1400157D1
0x1400157b4  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1400157bb  test    rax, rax
0x1400157be  jz      short loc_1400157D1
0x1400157c0  mov     rdx, [rsp+28h]
0x1400157c5  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1400157cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400157d1  mov     dword ptr [rdi+18h], 0
0x1400157d8  mov     rcx, [rdi]
0x1400157db  jmp     short loc_1400157E9
0x1400157dd  cmp     rax, rdi
0x1400157e0  jz      short loc_1400157F3
0x1400157e2  lea     rcx, [rax+10h]
0x1400157e6  mov     [rdi], rcx
0x1400157e9  mov     rax, [rcx]
0x1400157ec  test    rax, rax
0x1400157ef  jnz     short loc_1400157DD
0x1400157f1  jmp     short loc_1400157FA
0x1400157f3  mov     rax, [rdi+10h]
0x1400157f7  mov     [rcx], rax
0x1400157fa  mov     qword ptr [rdi], 0
0x140015801  mov     rbx, [rsp+28h+arg_0]
0x140015806  add     rsp, 20h
0x14001580a  pop     rdi
0x14001580b  retn
```
