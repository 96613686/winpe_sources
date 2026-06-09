# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180019114`
- end: `0x18001917b`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800183ac`
- `0x1800185d4`

## callees

- `0x180019114`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001911d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001911d`

## string_xrefs

- `0x180019139`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180019114  push    rbx
0x180019116  sub     rsp, 20h
0x18001911a  mov     rbx, rcx
0x18001911d  call    cs:__imp_GetCurrentThreadId
0x180019123  cmp     [rbx+18h], eax
0x180019126  jz      short loc_180019145
0x180019128  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18001912f  test    rax, rax
0x180019132  jz      short loc_180019145
0x180019134  mov     rdx, [rsp+28h]
0x180019139  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180019140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019145  mov     rcx, [rbx]
0x180019148  mov     dword ptr [rbx+18h], 0
0x18001914f  jmp     short loc_18001915D
0x180019151  cmp     rax, rbx
0x180019154  jz      short loc_180019167
0x180019156  lea     rcx, [rax+10h]
0x18001915a  mov     [rbx], rcx
0x18001915d  mov     rax, [rcx]
0x180019160  test    rax, rax
0x180019163  jnz     short loc_180019151
0x180019165  jmp     short loc_18001916E
0x180019167  mov     rax, [rbx+10h]
0x18001916b  mov     [rcx], rax
0x18001916e  mov     qword ptr [rbx], 0
0x180019175  add     rsp, 20h
0x180019179  pop     rbx
0x18001917a  retn
```
