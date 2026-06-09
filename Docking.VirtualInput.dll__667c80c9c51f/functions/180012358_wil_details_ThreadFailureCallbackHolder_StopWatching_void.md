# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180012358`
- end: `0x18001241d`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `197`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cc34`
- `0x18000ea88`

## callees

- `0x180012358`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012361`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012361`

## string_xrefs

- `0x180012399`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StopWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  void *retaddr; // [rsp+38h] [rbp+0h]

  if ( *((_DWORD *)this + 6) != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
    ((void (__fastcall *)(const char *, void *))wil::details::g_pfnReportFatalUsageError)(
      "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
      retaddr);
  *((_DWORD *)this + 6) = 0;
  while ( **(_QWORD **)this )
  {
    if ( **(wil::details::ThreadFailureCallbackHolder ***)this == this )
    {
      **(_QWORD **)this = *((_QWORD *)this + 2);
      break;
    }
    *(_QWORD *)this = **(_QWORD **)this + 16LL;
  }
  *(_QWORD *)this = 0;
}

```

## disassembly

```asm
0x180012358  mov     [rsp+arg_0], rcx
0x18001235d  sub     rsp, 38h
0x180012361  call    cs:__imp_GetCurrentThreadId
0x180012367  mov     rcx, [rsp+38h+arg_0]
0x18001236c  cmp     [rcx+18h], eax
0x18001236f  jz      short loc_1800123B1
0x180012371  cmp     cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA, 0
0x180012379  jz      short loc_1800123AB
0x18001237b  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180012382  mov     [rsp+38h+var_18], rax
0x180012387  mov     rax, [rsp+38h]
0x18001238c  mov     rcx, [rsp+38h+var_18]
0x180012391  mov     [rsp+38h+var_10], rcx
0x180012396  mov     rdx, rax
0x180012399  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800123a0  mov     rax, [rsp+38h+var_10]
0x1800123a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123aa  nop
0x1800123ab  xor     eax, eax
0x1800123ad  test    eax, eax
0x1800123af  jnz     short loc_180012371
0x1800123b1  mov     rax, [rsp+38h+arg_0]
0x1800123b6  mov     dword ptr [rax+18h], 0
0x1800123bd  mov     rax, [rsp+38h+arg_0]
0x1800123c2  mov     rax, [rax]
0x1800123c5  cmp     qword ptr [rax], 0
0x1800123c9  jz      short loc_18001240C
0x1800123cb  mov     rax, [rsp+38h+arg_0]
0x1800123d0  mov     rax, [rax]
0x1800123d3  mov     rcx, [rsp+38h+arg_0]
0x1800123d8  cmp     [rax], rcx
0x1800123db  jnz     short loc_1800123F3
0x1800123dd  mov     rax, [rsp+38h+arg_0]
0x1800123e2  mov     rax, [rax]
0x1800123e5  mov     rcx, [rsp+38h+arg_0]
0x1800123ea  mov     rcx, [rcx+10h]
0x1800123ee  mov     [rax], rcx
0x1800123f1  jmp     short loc_18001240C
0x1800123f3  mov     rax, [rsp+38h+arg_0]
0x1800123f8  mov     rax, [rax]
0x1800123fb  mov     rax, [rax]
0x1800123fe  add     rax, 10h
0x180012402  mov     rcx, [rsp+38h+arg_0]
0x180012407  mov     [rcx], rax
0x18001240a  jmp     short loc_1800123BD
0x18001240c  mov     rax, [rsp+38h+arg_0]
0x180012411  mov     qword ptr [rax], 0
0x180012418  add     rsp, 38h
0x18001241c  retn
```
