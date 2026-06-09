# wil::invoke_rpc_nothrow<long (&)(void *,uint,uint),void * &,uint &,uint &>(long (&)(void *,uint,uint),void * &,uint &,uint &)

- ea: `0x1800088ec`
- end: `0x180008954`
- name: `??$invoke_rpc_nothrow@A6AJPEAXII@ZAEAPEAXAEAIAEAI@wil@@YAJA6AJPEAXII@ZAEAPEAXAEAI3@Z`
- size: `104`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a9d0`
- `0x18000aa50`

## callees

- `0x180006214`
- `0x180008480`
- `0x1800088ec`

## string_xrefs

- `0x180008905`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`
- `0x18000893b`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::invoke_rpc_nothrow<long (&)(void *,unsigned int,unsigned int),void * &,unsigned int &,unsigned int &>(
        __int64 a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = wistd::__invoke<long (&)(void *,int,unsigned int),void * &,int &,unsigned int &>(a1);
  v2 = v1;
  if ( v1 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5E,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\rpc_helpers.h",
    (const char *)(unsigned int)v1,
    v4);
  return v2;
}

```

## disassembly

```asm
0x1800088ec  push    rbx; int
0x1800088ee  sub     rsp, 20h
0x1800088f2  call    ??$__invoke@A6AJPEAXHI@ZAEAPEAXAEAHAEAI@wistd@@YAJA6AJPEAXHI@ZAEAPEAXAEAHAEAI@Z; wistd::__invoke<long (&)(void *,int,uint),void * &,int &,uint &>(long (&)(void *,int,uint),void * &,int &,uint &)
0x1800088f7  mov     ebx, eax
0x1800088f9  test    eax, eax
0x1800088fb  jns     short loc_18000891A
0x1800088fd  mov     rcx, [rsp+28h]; this
0x180008902  mov     r9d, eax; char *
0x180008905  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000890c  mov     edx, 5Eh ; '^'; void *
0x180008911  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008916  mov     eax, ebx
0x180008918  jmp     short loc_18000894E
0x18000891a  xor     eax, eax
0x18000891c  jmp     short loc_18000894E
0x18000891e  mov     ebx, eax
0x180008920  test    eax, eax
0x180008922  js      short loc_18000892F
0x180008924  jle     short loc_18000892F
0x180008926  movzx   ebx, ax
0x180008929  or      ebx, 80070000h
0x18000892f  test    ebx, ebx
0x180008931  jns     short loc_18000894C
0x180008933  mov     rcx, [rsp+28h]; this
0x180008938  mov     r9d, ebx; char *
0x18000893b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008942  mov     edx, 63h ; 'c'; void *
0x180008947  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000894c  mov     eax, ebx
0x18000894e  add     rsp, 20h
0x180008952  pop     rbx
0x180008953  retn
```
