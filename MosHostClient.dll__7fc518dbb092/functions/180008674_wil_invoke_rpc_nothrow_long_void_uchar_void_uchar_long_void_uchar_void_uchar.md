# wil::invoke_rpc_nothrow<long (&)(void *,uchar),void * &,uchar &>(long (&)(void *,uchar),void * &,uchar &)

- ea: `0x180008674`
- end: `0x1800086e3`
- name: `??$invoke_rpc_nothrow@A6AJPEAXE@ZAEAPEAXAEAE@wil@@YAJA6AJPEAXE@ZAEAPEAXAEAE@Z`
- size: `111`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009de0`

## callees

- `0x180006214`
- `0x180008394`
- `0x180008674`

## string_xrefs

- `0x180008694`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`
- `0x1800086ca`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 wil::invoke_rpc_nothrow<long (&)(void *,unsigned char),void * &,unsigned char &>()
{
  int v0; // eax
  unsigned int v1; // ebx
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v0 = wistd::__invoke<long (&)(void *,unsigned char),void * &,unsigned char &>(MosHostCacheStateSnapshot);
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
0x180008674  push    rbx; int
0x180008676  sub     rsp, 20h
0x18000867a  lea     rcx, MosHostCacheStateSnapshot
0x180008681  call    ??$__invoke@A6AJPEAXE@ZAEAPEAXAEAE@wistd@@YAJA6AJPEAXE@ZAEAPEAXAEAE@Z; wistd::__invoke<long (&)(void *,uchar),void * &,uchar &>(long (&)(void *,uchar),void * &,uchar &)
0x180008686  mov     ebx, eax
0x180008688  test    eax, eax
0x18000868a  jns     short loc_1800086A9
0x18000868c  mov     rcx, [rsp+28h]; this
0x180008691  mov     r9d, eax; char *
0x180008694  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000869b  mov     edx, 5Eh ; '^'; void *
0x1800086a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800086a5  mov     eax, ebx
0x1800086a7  jmp     short loc_1800086DD
0x1800086a9  xor     eax, eax
0x1800086ab  jmp     short loc_1800086DD
0x1800086ad  mov     ebx, eax
0x1800086af  test    eax, eax
0x1800086b1  js      short loc_1800086BE
0x1800086b3  jle     short loc_1800086BE
0x1800086b5  movzx   ebx, ax
0x1800086b8  or      ebx, 80070000h
0x1800086be  test    ebx, ebx
0x1800086c0  jns     short loc_1800086DB
0x1800086c2  mov     rcx, [rsp+28h]; this
0x1800086c7  mov     r9d, ebx; char *
0x1800086ca  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800086d1  mov     edx, 63h ; 'c'; void *
0x1800086d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800086db  mov     eax, ebx
0x1800086dd  add     rsp, 20h
0x1800086e1  pop     rbx
0x1800086e2  retn
```
