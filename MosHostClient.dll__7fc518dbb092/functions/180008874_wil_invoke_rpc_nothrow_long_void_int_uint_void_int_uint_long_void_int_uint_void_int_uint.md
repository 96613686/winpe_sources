# wil::invoke_rpc_nothrow<long (&)(void *,int,uint),void * &,int &,uint &>(long (&)(void *,int,uint),void * &,int &,uint &)

- ea: `0x180008874`
- end: `0x1800088e3`
- name: `??$invoke_rpc_nothrow@A6AJPEAXHI@ZAEAPEAXAEAHAEAI@wil@@YAJA6AJPEAXHI@ZAEAPEAXAEAHAEAI@Z`
- size: `111`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009d70`

## callees

- `0x180006214`
- `0x180008480`
- `0x180008874`

## string_xrefs

- `0x180008894`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`
- `0x1800088ca`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 wil::invoke_rpc_nothrow<long (&)(void *,int,unsigned int),void * &,int &,unsigned int &>()
{
  int v0; // eax
  unsigned int v1; // ebx
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v0 = wistd::__invoke<long (&)(void *,int,unsigned int),void * &,int &,unsigned int &>(MosHostCacheStateSetSlotSize);
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
0x180008874  push    rbx; int
0x180008876  sub     rsp, 20h
0x18000887a  lea     rcx, MosHostCacheStateSetSlotSize
0x180008881  call    ??$__invoke@A6AJPEAXHI@ZAEAPEAXAEAHAEAI@wistd@@YAJA6AJPEAXHI@ZAEAPEAXAEAHAEAI@Z; wistd::__invoke<long (&)(void *,int,uint),void * &,int &,uint &>(long (&)(void *,int,uint),void * &,int &,uint &)
0x180008886  mov     ebx, eax
0x180008888  test    eax, eax
0x18000888a  jns     short loc_1800088A9
0x18000888c  mov     rcx, [rsp+28h]; this
0x180008891  mov     r9d, eax; char *
0x180008894  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000889b  mov     edx, 5Eh ; '^'; void *
0x1800088a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800088a5  mov     eax, ebx
0x1800088a7  jmp     short loc_1800088DD
0x1800088a9  xor     eax, eax
0x1800088ab  jmp     short loc_1800088DD
0x1800088ad  mov     ebx, eax
0x1800088af  test    eax, eax
0x1800088b1  js      short loc_1800088BE
0x1800088b3  jle     short loc_1800088BE
0x1800088b5  movzx   ebx, ax
0x1800088b8  or      ebx, 80070000h
0x1800088be  test    ebx, ebx
0x1800088c0  jns     short loc_1800088DB
0x1800088c2  mov     rcx, [rsp+28h]; this
0x1800088c7  mov     r9d, ebx; char *
0x1800088ca  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800088d1  mov     edx, 63h ; 'c'; void *
0x1800088d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800088db  mov     eax, ebx
0x1800088dd  add     rsp, 20h
0x1800088e1  pop     rbx
0x1800088e2  retn
```
