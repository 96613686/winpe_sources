# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x140007ca8`
- end: `0x140007d2a`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140007a38`

## callees

- `0x140007ca8`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007cc8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007cc8`

## string_xrefs

- `0x140007ce3`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(
        wil::details::ThreadFailureCallbackHolder *this)
{
  int v2; // ebx
  wil::details::ThreadFailureCallbackHolder **v3; // rcx
  wil::details::ThreadFailureCallbackHolder *v4; // rax
  void *retaddr; // [rsp+38h] [rbp+0h]

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
0x140007ca8  push    rdi
0x140007caa  sub     rsp, 30h
0x140007cae  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x140007cb7  mov     [rsp+38h+arg_0], rbx
0x140007cbc  mov     rdi, rcx
0x140007cbf  cmp     dword ptr [rcx+18h], 0
0x140007cc3  jz      short loc_140007D1F
0x140007cc5  mov     ebx, [rcx+18h]
0x140007cc8  call    cs:__imp_GetCurrentThreadId
0x140007cce  cmp     ebx, eax
0x140007cd0  jz      short loc_140007CEF
0x140007cd2  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x140007cd9  test    rax, rax
0x140007cdc  jz      short loc_140007CEF
0x140007cde  mov     rdx, [rsp+38h]
0x140007ce3  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x140007cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007cef  mov     dword ptr [rdi+18h], 0
0x140007cf6  mov     rcx, [rdi]
0x140007cf9  jmp     short loc_140007D07
0x140007cfb  cmp     rax, rdi
0x140007cfe  jz      short loc_140007D11
0x140007d00  lea     rcx, [rax+10h]
0x140007d04  mov     [rdi], rcx
0x140007d07  mov     rax, [rcx]
0x140007d0a  test    rax, rax
0x140007d0d  jnz     short loc_140007CFB
0x140007d0f  jmp     short loc_140007D18
0x140007d11  mov     rax, [rdi+10h]
0x140007d15  mov     [rcx], rax
0x140007d18  mov     qword ptr [rdi], 0
0x140007d1f  mov     rbx, [rsp+38h+arg_0]
0x140007d24  add     rsp, 30h
0x140007d28  pop     rdi
0x140007d29  retn
```
