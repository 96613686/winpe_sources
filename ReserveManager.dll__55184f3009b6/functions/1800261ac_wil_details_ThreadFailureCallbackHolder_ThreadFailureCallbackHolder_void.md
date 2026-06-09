# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x1800261ac`
- end: `0x180026224`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180025c68`
- `0x180025cdc`

## callees

- `0x1800261ac`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800261c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800261c2`

## string_xrefs

- `0x1800261dd`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x1800261ac  mov     [rsp+arg_0], rbx
0x1800261b1  push    rdi
0x1800261b2  sub     rsp, 20h
0x1800261b6  cmp     dword ptr [rcx+18h], 0
0x1800261ba  mov     rdi, rcx
0x1800261bd  jz      short loc_180026219
0x1800261bf  mov     ebx, [rcx+18h]
0x1800261c2  call    cs:__imp_GetCurrentThreadId
0x1800261c8  cmp     ebx, eax
0x1800261ca  jz      short loc_1800261E9
0x1800261cc  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800261d3  test    rax, rax
0x1800261d6  jz      short loc_1800261E9
0x1800261d8  mov     rdx, [rsp+28h]
0x1800261dd  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800261e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261e9  mov     rcx, [rdi]
0x1800261ec  mov     dword ptr [rdi+18h], 0
0x1800261f3  jmp     short loc_180026201
0x1800261f5  cmp     rax, rdi
0x1800261f8  jz      short loc_18002620B
0x1800261fa  lea     rcx, [rax+10h]
0x1800261fe  mov     [rdi], rcx
0x180026201  mov     rax, [rcx]
0x180026204  test    rax, rax
0x180026207  jnz     short loc_1800261F5
0x180026209  jmp     short loc_180026212
0x18002620b  mov     rax, [rdi+10h]
0x18002620f  mov     [rcx], rax
0x180026212  mov     qword ptr [rdi], 0
0x180026219  mov     rbx, [rsp+28h+arg_0]
0x18002621e  add     rsp, 20h
0x180026222  pop     rdi
0x180026223  retn
```
