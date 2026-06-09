# wil::details::ThreadFailureCallbackHolder::suspend(void)

- ea: `0x18002349c`
- end: `0x180023529`
- name: `?suspend@ThreadFailureCallbackHolder@details@wil@@QEAA_NXZ`
- size: `141`
- prototype: `bool __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001bab8`
- `0x18001baf4`

## callees

- `0x18002349c`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800234ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800234ba`

## string_xrefs

- `0x1800234d5`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
char __fastcall wil::details::ThreadFailureCallbackHolder::suspend(wil::details::ThreadFailureCallbackHolder *this)
{
  char v2; // si
  int v3; // ebx
  wil::details::ThreadFailureCallbackHolder **v4; // rcx
  wil::details::ThreadFailureCallbackHolder *v5; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( !*((_DWORD *)this + 6) )
    return 0;
  v2 = 1;
  v3 = *((_DWORD *)this + 6);
  if ( v3 != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
    wil::details::g_pfnReportFatalUsageError(
      "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
      retaddr);
  *((_DWORD *)this + 6) = 0;
  v4 = *(wil::details::ThreadFailureCallbackHolder ***)this;
  while ( 1 )
  {
    v5 = *v4;
    if ( !*v4 )
      break;
    if ( v5 == this )
    {
      *v4 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)this + 2);
      break;
    }
    v4 = (wil::details::ThreadFailureCallbackHolder **)((char *)v5 + 16);
    *(_QWORD *)this = (char *)v5 + 16;
  }
  *(_QWORD *)this = 0;
  return v2;
}

```

## disassembly

```asm
0x18002349c  mov     [rsp+arg_0], rbx
0x1800234a1  mov     [rsp+arg_8], rsi
0x1800234a6  push    rdi
0x1800234a7  sub     rsp, 20h
0x1800234ab  mov     rdi, rcx
0x1800234ae  cmp     dword ptr [rcx+18h], 0
0x1800234b2  jz      short loc_180023513
0x1800234b4  mov     sil, 1
0x1800234b7  mov     ebx, [rcx+18h]
0x1800234ba  call    cs:__imp_GetCurrentThreadId
0x1800234c0  cmp     ebx, eax
0x1800234c2  jz      short loc_1800234E1
0x1800234c4  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800234cb  test    rax, rax
0x1800234ce  jz      short loc_1800234E1
0x1800234d0  mov     rdx, [rsp+28h]
0x1800234d5  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800234dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234e1  mov     dword ptr [rdi+18h], 0
0x1800234e8  mov     rcx, [rdi]
0x1800234eb  jmp     short loc_1800234F9
0x1800234ed  cmp     rax, rdi
0x1800234f0  jz      short loc_180023503
0x1800234f2  lea     rcx, [rax+10h]
0x1800234f6  mov     [rdi], rcx
0x1800234f9  mov     rax, [rcx]
0x1800234fc  test    rax, rax
0x1800234ff  jnz     short loc_1800234ED
0x180023501  jmp     short loc_18002350A
0x180023503  mov     rax, [rdi+10h]
0x180023507  mov     [rcx], rax
0x18002350a  mov     qword ptr [rdi], 0
0x180023511  jmp     short loc_180023516
0x180023513  xor     sil, sil
0x180023516  mov     al, sil
0x180023519  mov     rbx, [rsp+28h+arg_0]
0x18002351e  mov     rsi, [rsp+28h+arg_8]
0x180023523  add     rsp, 20h
0x180023527  pop     rdi
0x180023528  retn
```
