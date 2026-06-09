# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x140003eb0`
- end: `0x140003f26`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `118`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x140003f30`
- `0x1400045a0`
- `0x140004c10`
- `0x140005280`
- `0x14000b580`
- `0x14000b678`
- `0x14000b80c`
- `0x14000b88c`
- `0x14000b984`
- `0x14000ba7c`
- `0x14000bb74`
- `0x140013728`
- `0x1400139fc`

## callees

- `0x140003eb0`
- `0x140085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003eb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003eb9`

## string_xrefs

- `0x140003edb`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StopWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  wil::details::ThreadFailureCallbackHolder **v2; // rcx
  wil::details::ThreadFailureCallbackHolder *v3; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_DWORD *)this + 6) != GetCurrentThreadId() )
  {
    if ( wil::details::g_pfnReportFatalUsageError )
      wil::details::g_pfnReportFatalUsageError(
        "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
        retaddr);
  }
  v2 = *(wil::details::ThreadFailureCallbackHolder ***)this;
  *((_DWORD *)this + 6) = 0;
  v3 = *v2;
  if ( *v2 )
  {
    while ( v3 != this )
    {
      v2 = (wil::details::ThreadFailureCallbackHolder **)((char *)v3 + 16);
      *(_QWORD *)this = (char *)v3 + 16;
      v3 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v3 + 2);
      if ( !v3 )
      {
        *(_QWORD *)this = 0;
        return;
      }
    }
    *v2 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)this + 2);
  }
  *(_QWORD *)this = 0;
}

```

## disassembly

```asm
0x140003eb0  push    rbx
0x140003eb2  sub     rsp, 20h
0x140003eb6  mov     rbx, rcx
0x140003eb9  call    cs:__imp_GetCurrentThreadId
0x140003ec0  nop     dword ptr [rax+rax+00h]
0x140003ec5  cmp     [rbx+18h], eax
0x140003ec8  jz      short loc_140003EE7
0x140003eca  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x140003ed1  test    rax, rax
0x140003ed4  jz      short loc_140003EE7
0x140003ed6  mov     rdx, [rsp+28h]
0x140003edb  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x140003ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ee7  mov     rcx, [rbx]
0x140003eea  xor     edx, edx
0x140003eec  mov     [rbx+18h], edx
0x140003eef  mov     rax, [rcx]
0x140003ef2  test    rax, rax
0x140003ef5  jz      short loc_140003F1C
0x140003ef7  cmp     rax, rbx
0x140003efa  jz      short loc_140003F15
0x140003efc  lea     rcx, [rax+10h]
0x140003f00  mov     [rbx], rcx
0x140003f03  mov     rax, [rcx]
0x140003f06  test    rax, rax
0x140003f09  jnz     short loc_140003EF7
0x140003f0b  mov     [rbx], rdx
0x140003f0e  add     rsp, 20h
0x140003f12  pop     rbx
0x140003f13  retn
0x140003f15  mov     rax, [rbx+10h]
0x140003f19  mov     [rcx], rax
0x140003f1c  mov     [rbx], rdx
0x140003f1f  add     rsp, 20h
0x140003f23  pop     rbx
0x140003f24  retn
```
