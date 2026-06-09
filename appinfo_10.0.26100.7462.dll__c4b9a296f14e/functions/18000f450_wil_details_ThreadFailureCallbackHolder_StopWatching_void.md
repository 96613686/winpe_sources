# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18000f450`
- end: `0x18000f4b5`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `101`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001964c`
- `0x18001fd6c`

## callees

- `0x18000f450`
- `0x18002017c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f459`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f459`

## string_xrefs

- `0x18000f46f`: `onecore\internal\sdk\inc\wil\opensource\wil\result.h`

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
0x18000f450  push    rbx; int
0x18000f452  sub     rsp, 20h
0x18000f456  mov     rbx, rcx
0x18000f459  call    cs:__imp_GetCurrentThreadId
0x18000f460  nop     dword ptr [rax+rax+00h]
0x18000f465  cmp     [rbx+18h], eax
0x18000f468  jz      short loc_18000F486
0x18000f46a  mov     rcx, [rsp+28h]; this
0x18000f46f  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f476  mov     r9d, 8007029Ch; char *
0x18000f47c  mov     edx, 3BEh; void *
0x18000f481  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000f486  xor     edx, edx
0x18000f488  mov     [rbx+18h], edx
0x18000f48b  mov     rcx, [rbx]
0x18000f48e  mov     rax, [rcx]
0x18000f491  test    rax, rax
0x18000f494  jz      short loc_18000F4AB
0x18000f496  cmp     rax, rbx
0x18000f499  jz      short loc_18000F4A4
0x18000f49b  add     rax, 10h
0x18000f49f  mov     [rbx], rax
0x18000f4a2  jmp     short loc_18000F48B
0x18000f4a4  mov     rax, [rbx+10h]
0x18000f4a8  mov     [rcx], rax
0x18000f4ab  mov     [rbx], rdx
0x18000f4ae  add     rsp, 20h
0x18000f4b2  pop     rbx
0x18000f4b3  retn
```
