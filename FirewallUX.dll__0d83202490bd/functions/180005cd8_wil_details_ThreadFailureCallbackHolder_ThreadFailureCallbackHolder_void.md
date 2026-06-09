# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x180005cd8`
- end: `0x180005d50`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800056ec`
- `0x18000f1a4`
- `0x1800139a4`
- `0x180019ec0`
- `0x1800229a0`

## callees

- `0x180005cd8`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005cee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005cee`

## string_xrefs

- `0x180005d09`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180005cd8  mov     [rsp+arg_0], rbx
0x180005cdd  push    rdi
0x180005cde  sub     rsp, 20h
0x180005ce2  mov     rdi, rcx
0x180005ce5  cmp     dword ptr [rcx+18h], 0
0x180005ce9  jz      short loc_180005D45
0x180005ceb  mov     ebx, [rcx+18h]
0x180005cee  call    cs:__imp_GetCurrentThreadId
0x180005cf4  cmp     ebx, eax
0x180005cf6  jz      short loc_180005D15
0x180005cf8  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180005cff  test    rax, rax
0x180005d02  jz      short loc_180005D15
0x180005d04  mov     rdx, [rsp+28h]
0x180005d09  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180005d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d15  mov     dword ptr [rdi+18h], 0
0x180005d1c  mov     rcx, [rdi]
0x180005d1f  jmp     short loc_180005D2D
0x180005d21  cmp     rax, rdi
0x180005d24  jz      short loc_180005D37
0x180005d26  lea     rcx, [rax+10h]
0x180005d2a  mov     [rdi], rcx
0x180005d2d  mov     rax, [rcx]
0x180005d30  test    rax, rax
0x180005d33  jnz     short loc_180005D21
0x180005d35  jmp     short loc_180005D3E
0x180005d37  mov     rax, [rdi+10h]
0x180005d3b  mov     [rcx], rax
0x180005d3e  mov     qword ptr [rdi], 0
0x180005d45  mov     rbx, [rsp+28h+arg_0]
0x180005d4a  add     rsp, 20h
0x180005d4e  pop     rdi
0x180005d4f  retn
```
