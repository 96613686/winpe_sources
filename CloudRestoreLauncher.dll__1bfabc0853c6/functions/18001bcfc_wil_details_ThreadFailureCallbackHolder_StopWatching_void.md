# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18001bcfc`
- end: `0x18001bd63`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180016b14`
- `0x180018674`
- `0x18001f7d4`
- `0x18002010c`
- `0x18010e11c`
- `0x18010f210`

## callees

- `0x18001bcfc`
- `0x18012d010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001bd05`
- `KERNEL32!GetCurrentThreadId` at `0x18001bd05`

## string_xrefs

- `0x18001bd21`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18001bcfc  push    rbx
0x18001bcfe  sub     rsp, 20h
0x18001bd02  mov     rbx, rcx
0x18001bd05  call    cs:__imp_GetCurrentThreadId
0x18001bd0b  cmp     [rbx+18h], eax
0x18001bd0e  jz      short loc_18001BD2D
0x18001bd10  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18001bd17  test    rax, rax
0x18001bd1a  jz      short loc_18001BD2D
0x18001bd1c  mov     rdx, [rsp+28h]
0x18001bd21  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18001bd28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd2d  mov     rcx, [rbx]
0x18001bd30  mov     dword ptr [rbx+18h], 0
0x18001bd37  jmp     short loc_18001BD45
0x18001bd39  cmp     rax, rbx
0x18001bd3c  jz      short loc_18001BD4F
0x18001bd3e  lea     rcx, [rax+10h]
0x18001bd42  mov     [rbx], rcx
0x18001bd45  mov     rax, [rcx]
0x18001bd48  test    rax, rax
0x18001bd4b  jnz     short loc_18001BD39
0x18001bd4d  jmp     short loc_18001BD56
0x18001bd4f  mov     rax, [rbx+10h]
0x18001bd53  mov     [rcx], rax
0x18001bd56  mov     qword ptr [rbx], 0
0x18001bd5d  add     rsp, 20h
0x18001bd61  pop     rbx
0x18001bd62  retn
```
