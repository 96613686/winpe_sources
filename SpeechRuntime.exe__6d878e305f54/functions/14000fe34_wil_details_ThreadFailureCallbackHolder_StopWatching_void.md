# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x14000fe34`
- end: `0x14000fe9b`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400072a8`
- `0x1400081e8`
- `0x140008268`
- `0x14000c224`

## callees

- `0x14000fe34`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000fe3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000fe3d`

## string_xrefs

- `0x14000fe59`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x14000fe34  push    rbx
0x14000fe36  sub     rsp, 20h
0x14000fe3a  mov     rbx, rcx
0x14000fe3d  call    cs:__imp_GetCurrentThreadId
0x14000fe43  cmp     [rbx+18h], eax
0x14000fe46  jz      short loc_14000FE65
0x14000fe48  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x14000fe4f  test    rax, rax
0x14000fe52  jz      short loc_14000FE65
0x14000fe54  mov     rdx, [rsp+28h]
0x14000fe59  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x14000fe60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fe65  mov     rcx, [rbx]
0x14000fe68  mov     dword ptr [rbx+18h], 0
0x14000fe6f  jmp     short loc_14000FE7D
0x14000fe71  cmp     rax, rbx
0x14000fe74  jz      short loc_14000FE87
0x14000fe76  lea     rcx, [rax+10h]
0x14000fe7a  mov     [rbx], rcx
0x14000fe7d  mov     rax, [rcx]
0x14000fe80  test    rax, rax
0x14000fe83  jnz     short loc_14000FE71
0x14000fe85  jmp     short loc_14000FE8E
0x14000fe87  mov     rax, [rbx+10h]
0x14000fe8b  mov     [rcx], rax
0x14000fe8e  mov     qword ptr [rbx], 0
0x14000fe95  add     rsp, 20h
0x14000fe99  pop     rbx
0x14000fe9a  retn
```
