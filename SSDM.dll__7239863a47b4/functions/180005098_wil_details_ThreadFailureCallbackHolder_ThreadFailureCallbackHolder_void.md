# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x180005098`
- end: `0x180005110`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180004614`
- `0x180005ec0`
- `0x18000a588`

## callees

- `0x180005098`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800050ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800050ae`

## string_xrefs

- `0x1800050c9`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180005098  mov     [rsp+arg_0], rbx
0x18000509d  push    rdi
0x18000509e  sub     rsp, 20h
0x1800050a2  mov     rdi, rcx
0x1800050a5  cmp     dword ptr [rcx+18h], 0
0x1800050a9  jz      short loc_180005105
0x1800050ab  mov     ebx, [rcx+18h]
0x1800050ae  call    cs:__imp_GetCurrentThreadId
0x1800050b4  cmp     ebx, eax
0x1800050b6  jz      short loc_1800050D5
0x1800050b8  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800050bf  test    rax, rax
0x1800050c2  jz      short loc_1800050D5
0x1800050c4  mov     rdx, [rsp+28h]
0x1800050c9  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800050d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050d5  mov     dword ptr [rdi+18h], 0
0x1800050dc  mov     rcx, [rdi]
0x1800050df  jmp     short loc_1800050ED
0x1800050e1  cmp     rax, rdi
0x1800050e4  jz      short loc_1800050F7
0x1800050e6  lea     rcx, [rax+10h]
0x1800050ea  mov     [rdi], rcx
0x1800050ed  mov     rax, [rcx]
0x1800050f0  test    rax, rax
0x1800050f3  jnz     short loc_1800050E1
0x1800050f5  jmp     short loc_1800050FE
0x1800050f7  mov     rax, [rdi+10h]
0x1800050fb  mov     [rcx], rax
0x1800050fe  mov     qword ptr [rdi], 0
0x180005105  mov     rbx, [rsp+28h+arg_0]
0x18000510a  add     rsp, 20h
0x18000510e  pop     rdi
0x18000510f  retn
```
