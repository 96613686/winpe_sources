# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18001a730`
- end: `0x18001a791`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `97`
- prototype: `void(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800193d0`
- `0x180052c90`
- `0x180053610`
- `0x1800583b0`
- `0x18005bc90`

## callees

- `0x18001a6f0`
- `0x18001a730`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001a739`
- `KERNEL32!GetCurrentThreadId` at `0x18001a739`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StopWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  void *v2; // rdx
  unsigned int v3; // r8d
  wil::details::ThreadFailureCallbackHolder **v4; // rcx
  wil::details::ThreadFailureCallbackHolder *v5; // rax
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_DWORD *)this + 6) != GetCurrentThreadId() )
    wil::details::in1diag3::Log_Hr(retaddr, v2, v3, (const char *)0x8007029CLL, v6);
  v4 = *(wil::details::ThreadFailureCallbackHolder ***)this;
  *((_DWORD *)this + 6) = 0;
  v5 = *v4;
  if ( *v4 )
  {
    while ( v5 != this )
    {
      v4 = (wil::details::ThreadFailureCallbackHolder **)((char *)v5 + 16);
      *(_QWORD *)this = (char *)v5 + 16;
      v5 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v5 + 2);
      if ( !v5 )
      {
        *(_QWORD *)this = 0;
        return;
      }
    }
    *v4 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)this + 2);
  }
  *(_QWORD *)this = 0;
}

```

## disassembly

```asm
0x18001a730  push    rbx; int
0x18001a732  sub     rsp, 20h
0x18001a736  mov     rbx, rcx
0x18001a739  call    cs:__imp_GetCurrentThreadId
0x18001a73f  cmp     [rbx+18h], eax
0x18001a742  jz      short loc_18001A754
0x18001a744  mov     rcx, [rsp+28h]; this
0x18001a749  mov     r9d, 8007029Ch; char *
0x18001a74f  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001a754  mov     rcx, [rbx]
0x18001a757  xor     edx, edx
0x18001a759  mov     [rbx+18h], edx
0x18001a75c  mov     rax, [rcx]
0x18001a75f  test    rax, rax
0x18001a762  jz      short loc_18001A788
0x18001a764  cmp     rax, rbx
0x18001a767  jz      short loc_18001A781
0x18001a769  lea     rcx, [rax+10h]
0x18001a76d  mov     [rbx], rcx
0x18001a770  mov     rax, [rcx]
0x18001a773  test    rax, rax
0x18001a776  jnz     short loc_18001A764
0x18001a778  mov     [rbx], rdx
0x18001a77b  add     rsp, 20h
0x18001a77f  pop     rbx
0x18001a780  retn
0x18001a781  mov     rax, [rbx+10h]
0x18001a785  mov     [rcx], rax
0x18001a788  mov     [rbx], rdx
0x18001a78b  add     rsp, 20h
0x18001a78f  pop     rbx
0x18001a790  retn
```
