# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x140015bcc`
- end: `0x140015c44`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400155e4`

## callees

- `0x140015bcc`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140015be2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140015be2`

## string_xrefs

- `0x140015bfd`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x140015bcc  mov     [rsp+arg_0], rbx
0x140015bd1  push    rdi
0x140015bd2  sub     rsp, 20h
0x140015bd6  mov     rdi, rcx
0x140015bd9  cmp     dword ptr [rcx+18h], 0
0x140015bdd  jz      short loc_140015C39
0x140015bdf  mov     ebx, [rcx+18h]
0x140015be2  call    cs:__imp_GetCurrentThreadId
0x140015be8  cmp     ebx, eax
0x140015bea  jz      short loc_140015C09
0x140015bec  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x140015bf3  test    rax, rax
0x140015bf6  jz      short loc_140015C09
0x140015bf8  mov     rdx, [rsp+28h]
0x140015bfd  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x140015c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015c09  mov     dword ptr [rdi+18h], 0
0x140015c10  mov     rcx, [rdi]
0x140015c13  jmp     short loc_140015C21
0x140015c15  cmp     rax, rdi
0x140015c18  jz      short loc_140015C2B
0x140015c1a  lea     rcx, [rax+10h]
0x140015c1e  mov     [rdi], rcx
0x140015c21  mov     rax, [rcx]
0x140015c24  test    rax, rax
0x140015c27  jnz     short loc_140015C15
0x140015c29  jmp     short loc_140015C32
0x140015c2b  mov     rax, [rdi+10h]
0x140015c2f  mov     [rcx], rax
0x140015c32  mov     qword ptr [rdi], 0
0x140015c39  mov     rbx, [rsp+28h+arg_0]
0x140015c3e  add     rsp, 20h
0x140015c42  pop     rdi
0x140015c43  retn
```
