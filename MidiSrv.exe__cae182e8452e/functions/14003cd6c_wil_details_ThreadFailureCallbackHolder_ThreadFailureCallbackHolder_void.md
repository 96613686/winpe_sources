# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x14003cd6c`
- end: `0x14003cde4`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14003d0b0`
- `0x14003dae0`

## callees

- `0x14003cd6c`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003cd82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003cd82`

## string_xrefs

- `0x14003cd9d`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x14003cd6c  mov     [rsp+arg_0], rbx
0x14003cd71  push    rdi
0x14003cd72  sub     rsp, 20h
0x14003cd76  mov     rdi, rcx
0x14003cd79  cmp     dword ptr [rcx+18h], 0
0x14003cd7d  jz      short loc_14003CDD9
0x14003cd7f  mov     ebx, [rcx+18h]
0x14003cd82  call    cs:__imp_GetCurrentThreadId
0x14003cd88  cmp     ebx, eax
0x14003cd8a  jz      short loc_14003CDA9
0x14003cd8c  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x14003cd93  test    rax, rax
0x14003cd96  jz      short loc_14003CDA9
0x14003cd98  mov     rdx, [rsp+28h]
0x14003cd9d  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x14003cda4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003cda9  mov     dword ptr [rdi+18h], 0
0x14003cdb0  mov     rcx, [rdi]
0x14003cdb3  jmp     short loc_14003CDC1
0x14003cdb5  cmp     rax, rdi
0x14003cdb8  jz      short loc_14003CDCB
0x14003cdba  lea     rcx, [rax+10h]
0x14003cdbe  mov     [rdi], rcx
0x14003cdc1  mov     rax, [rcx]
0x14003cdc4  test    rax, rax
0x14003cdc7  jnz     short loc_14003CDB5
0x14003cdc9  jmp     short loc_14003CDD2
0x14003cdcb  mov     rax, [rdi+10h]
0x14003cdcf  mov     [rcx], rax
0x14003cdd2  mov     qword ptr [rdi], 0
0x14003cdd9  mov     rbx, [rsp+28h+arg_0]
0x14003cdde  add     rsp, 20h
0x14003cde2  pop     rdi
0x14003cde3  retn
```
