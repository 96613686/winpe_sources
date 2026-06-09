# wil::invoke_rpc_nothrow<long (&)(void *,ulong *),void * &,ulong * &>(long (&)(void *,ulong *),void * &,ulong * &)

- ea: `0x180008a44`
- end: `0x180008ab3`
- name: `??$invoke_rpc_nothrow@A6AJPEAXPEAK@ZAEAPEAXAEAPEAK@wil@@YAJA6AJPEAXPEAK@ZAEAPEAXAEAPEAK@Z`
- size: `111`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a190`

## callees

- `0x180006214`
- `0x180008504`
- `0x180008a44`

## string_xrefs

- `0x180008a64`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`
- `0x180008a9a`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 wil::invoke_rpc_nothrow<long (&)(void *,unsigned long *),void * &,unsigned long * &>()
{
  int v0; // eax
  unsigned int v1; // ebx
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v0 = wistd::__invoke<long (&)(void *,unsigned long *),void * &,unsigned long * &>(MosHostGetBrowseCacheSizeInMBytes);
  v1 = v0;
  if ( v0 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5E,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\rpc_helpers.h",
    (const char *)(unsigned int)v0,
    v3);
  return v1;
}

```

## disassembly

```asm
0x180008a44  push    rbx; int
0x180008a46  sub     rsp, 20h
0x180008a4a  lea     rcx, MosHostGetBrowseCacheSizeInMBytes
0x180008a51  call    ??$__invoke@A6AJPEAXPEAK@ZAEAPEAXAEAPEAK@wistd@@YAJA6AJPEAXPEAK@ZAEAPEAXAEAPEAK@Z; wistd::__invoke<long (&)(void *,ulong *),void * &,ulong * &>(long (&)(void *,ulong *),void * &,ulong * &)
0x180008a56  mov     ebx, eax
0x180008a58  test    eax, eax
0x180008a5a  jns     short loc_180008A79
0x180008a5c  mov     rcx, [rsp+28h]; this
0x180008a61  mov     r9d, eax; char *
0x180008a64  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008a6b  mov     edx, 5Eh ; '^'; void *
0x180008a70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a75  mov     eax, ebx
0x180008a77  jmp     short loc_180008AAD
0x180008a79  xor     eax, eax
0x180008a7b  jmp     short loc_180008AAD
0x180008a7d  mov     ebx, eax
0x180008a7f  test    eax, eax
0x180008a81  js      short loc_180008A8E
0x180008a83  jle     short loc_180008A8E
0x180008a85  movzx   ebx, ax
0x180008a88  or      ebx, 80070000h
0x180008a8e  test    ebx, ebx
0x180008a90  jns     short loc_180008AAB
0x180008a92  mov     rcx, [rsp+28h]; this
0x180008a97  mov     r9d, ebx; char *
0x180008a9a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008aa1  mov     edx, 63h ; 'c'; void *
0x180008aa6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008aab  mov     eax, ebx
0x180008aad  add     rsp, 20h
0x180008ab1  pop     rbx
0x180008ab2  retn
```
