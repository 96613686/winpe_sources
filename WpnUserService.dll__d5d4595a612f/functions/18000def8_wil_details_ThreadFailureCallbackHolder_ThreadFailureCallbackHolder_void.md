# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x18000def8`
- end: `0x18000df70`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dcdc`

## callees

- `0x18000def8`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000df0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000df0e`

## string_xrefs

- `0x18000df29`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18000def8  mov     [rsp+arg_0], rbx
0x18000defd  push    rdi
0x18000defe  sub     rsp, 20h
0x18000df02  mov     rdi, rcx
0x18000df05  cmp     dword ptr [rcx+18h], 0
0x18000df09  jz      short loc_18000DF65
0x18000df0b  mov     ebx, [rcx+18h]
0x18000df0e  call    cs:__imp_GetCurrentThreadId
0x18000df14  cmp     ebx, eax
0x18000df16  jz      short loc_18000DF35
0x18000df18  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000df1f  test    rax, rax
0x18000df22  jz      short loc_18000DF35
0x18000df24  mov     rdx, [rsp+28h]
0x18000df29  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000df30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df35  mov     dword ptr [rdi+18h], 0
0x18000df3c  mov     rcx, [rdi]
0x18000df3f  jmp     short loc_18000DF4D
0x18000df41  cmp     rax, rdi
0x18000df44  jz      short loc_18000DF57
0x18000df46  lea     rcx, [rax+10h]
0x18000df4a  mov     [rdi], rcx
0x18000df4d  mov     rax, [rcx]
0x18000df50  test    rax, rax
0x18000df53  jnz     short loc_18000DF41
0x18000df55  jmp     short loc_18000DF5E
0x18000df57  mov     rax, [rdi+10h]
0x18000df5b  mov     [rcx], rax
0x18000df5e  mov     qword ptr [rdi], 0
0x18000df65  mov     rbx, [rsp+28h+arg_0]
0x18000df6a  add     rsp, 20h
0x18000df6e  pop     rdi
0x18000df6f  retn
```
