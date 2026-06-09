# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18001065c`
- end: `0x1800106c3`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e884`

## callees

- `0x18001065c`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010665`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010665`

## string_xrefs

- `0x180010681`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StopWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  wil::details::ThreadFailureCallbackHolder **v2; // rcx
  wil::details::ThreadFailureCallbackHolder *v3; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_DWORD *)this + 6) != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
    wil::details::g_pfnReportFatalUsageError(
      "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
      retaddr);
  v2 = *(wil::details::ThreadFailureCallbackHolder ***)this;
  *((_DWORD *)this + 6) = 0;
  while ( 1 )
  {
    v3 = *v2;
    if ( !*v2 )
      break;
    if ( v3 == this )
    {
      *v2 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)this + 2);
      break;
    }
    v2 = (wil::details::ThreadFailureCallbackHolder **)((char *)v3 + 16);
    *(_QWORD *)this = (char *)v3 + 16;
  }
  *(_QWORD *)this = 0;
}

```

## disassembly

```asm
0x18001065c  push    rbx
0x18001065e  sub     rsp, 20h
0x180010662  mov     rbx, rcx
0x180010665  call    cs:__imp_GetCurrentThreadId
0x18001066b  cmp     [rbx+18h], eax
0x18001066e  jz      short loc_18001068D
0x180010670  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180010677  test    rax, rax
0x18001067a  jz      short loc_18001068D
0x18001067c  mov     rdx, [rsp+28h]
0x180010681  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180010688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001068d  mov     rcx, [rbx]
0x180010690  mov     dword ptr [rbx+18h], 0
0x180010697  jmp     short loc_1800106A5
0x180010699  cmp     rax, rbx
0x18001069c  jz      short loc_1800106AF
0x18001069e  lea     rcx, [rax+10h]
0x1800106a2  mov     [rbx], rcx
0x1800106a5  mov     rax, [rcx]
0x1800106a8  test    rax, rax
0x1800106ab  jnz     short loc_180010699
0x1800106ad  jmp     short loc_1800106B6
0x1800106af  mov     rax, [rbx+10h]
0x1800106b3  mov     [rcx], rax
0x1800106b6  mov     qword ptr [rbx], 0
0x1800106bd  add     rsp, 20h
0x1800106c1  pop     rbx
0x1800106c2  retn
```
