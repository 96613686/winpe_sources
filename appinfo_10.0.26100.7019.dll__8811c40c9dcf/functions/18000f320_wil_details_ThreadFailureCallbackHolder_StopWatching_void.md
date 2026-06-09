# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18000f320`
- end: `0x18000f385`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `101`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001927c`
- `0x180020fe0`

## callees

- `0x18000f320`
- `0x1800213f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f329`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f329`

## string_xrefs

- `0x18000f33f`: `onecore\internal\sdk\inc\wil\opensource\wil\result.h`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StopWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  wil::details::ThreadFailureCallbackHolder *v2; // rax
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_DWORD *)this + 6) != GetCurrentThreadId() )
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x3BE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result.h",
      (const char *)0x8007029CLL,
      v3);
  *((_DWORD *)this + 6) = 0;
  while ( 1 )
  {
    v2 = **(wil::details::ThreadFailureCallbackHolder ***)this;
    if ( !v2 )
      break;
    if ( v2 == this )
    {
      **(_QWORD **)this = *((_QWORD *)this + 2);
      break;
    }
    *(_QWORD *)this = (char *)v2 + 16;
  }
  *(_QWORD *)this = 0;
}

```

## disassembly

```asm
0x18000f320  push    rbx; int
0x18000f322  sub     rsp, 20h
0x18000f326  mov     rbx, rcx
0x18000f329  call    cs:__imp_GetCurrentThreadId
0x18000f330  nop     dword ptr [rax+rax+00h]
0x18000f335  cmp     [rbx+18h], eax
0x18000f338  jz      short loc_18000F356
0x18000f33a  mov     rcx, [rsp+28h]; this
0x18000f33f  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f346  mov     r9d, 8007029Ch; char *
0x18000f34c  mov     edx, 3BEh; void *
0x18000f351  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000f356  xor     edx, edx
0x18000f358  mov     [rbx+18h], edx
0x18000f35b  mov     rcx, [rbx]
0x18000f35e  mov     rax, [rcx]
0x18000f361  test    rax, rax
0x18000f364  jz      short loc_18000F37B
0x18000f366  cmp     rax, rbx
0x18000f369  jz      short loc_18000F374
0x18000f36b  add     rax, 10h
0x18000f36f  mov     [rbx], rax
0x18000f372  jmp     short loc_18000F35B
0x18000f374  mov     rax, [rbx+10h]
0x18000f378  mov     [rcx], rax
0x18000f37b  mov     [rbx], rdx
0x18000f37e  add     rsp, 20h
0x18000f382  pop     rbx
0x18000f383  retn
```
