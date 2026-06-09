# wil::invoke_rpc_nothrow<long (&)(void *,uint),void * &,uint &>(long (&)(void *,uint),void * &,uint &)

- ea: `0x180008804`
- end: `0x18000886c`
- name: `??$invoke_rpc_nothrow@A6AJPEAXI@ZAEAPEAXAEAI@wil@@YAJA6AJPEAXI@ZAEAPEAXAEAI@Z`
- size: `104`
- prototype: `__int64()`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180009d10`
- `0x180009e40`
- `0x18000d170`
- `0x18000d8d0`
- `0x18000d930`

## callees

- `0x180006214`
- `0x18000845c`
- `0x180008804`

## string_xrefs

- `0x18000881d`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`
- `0x180008853`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 wil::invoke_rpc_nothrow<long (&)(void *,unsigned int),void * &,unsigned int &>()
{
  int v0; // eax
  unsigned int v1; // ebx
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v0 = wistd::__invoke<long (&)(void *,int),void * &,int &>();
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
0x180008804  push    rbx; int
0x180008806  sub     rsp, 20h
0x18000880a  call    ??$__invoke@A6AJPEAXH@ZAEAPEAXAEAH@wistd@@YAJA6AJPEAXH@ZAEAPEAXAEAH@Z; wistd::__invoke<long (&)(void *,int),void * &,int &>(long (&)(void *,int),void * &,int &)
0x18000880f  mov     ebx, eax
0x180008811  test    eax, eax
0x180008813  jns     short loc_180008832
0x180008815  mov     rcx, [rsp+28h]; this
0x18000881a  mov     r9d, eax; char *
0x18000881d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008824  mov     edx, 5Eh ; '^'; void *
0x180008829  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000882e  mov     eax, ebx
0x180008830  jmp     short loc_180008866
0x180008832  xor     eax, eax
0x180008834  jmp     short loc_180008866
0x180008836  mov     ebx, eax
0x180008838  test    eax, eax
0x18000883a  js      short loc_180008847
0x18000883c  jle     short loc_180008847
0x18000883e  movzx   ebx, ax
0x180008841  or      ebx, 80070000h
0x180008847  test    ebx, ebx
0x180008849  jns     short loc_180008864
0x18000884b  mov     rcx, [rsp+28h]; this
0x180008850  mov     r9d, ebx; char *
0x180008853  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000885a  mov     edx, 63h ; 'c'; void *
0x18000885f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008864  mov     eax, ebx
0x180008866  add     rsp, 20h
0x18000886a  pop     rbx
0x18000886b  retn
```
