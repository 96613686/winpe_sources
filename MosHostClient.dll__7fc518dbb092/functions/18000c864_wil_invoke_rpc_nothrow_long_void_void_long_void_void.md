# wil::invoke_rpc_nothrow<long (&)(void *),void * &>(long (&)(void *),void * &)

- ea: `0x18000c864`
- end: `0x18000c8cc`
- name: `??$invoke_rpc_nothrow@A6AJPEAX@ZAEAPEAX@wil@@YAJA6AJPEAX@ZAEAPEAX@Z`
- size: `104`
- prototype: `__int64()`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d120`
- `0x18000d3b0`
- `0x18000d990`
- `0x18000d9e0`
- `0x18000fec0`

## callees

- `0x180006214`
- `0x18000c770`
- `0x18000c864`

## string_xrefs

- `0x18000c87d`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`
- `0x18000c8b3`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 wil::invoke_rpc_nothrow<long (&)(void *),void * &>()
{
  int v0; // eax
  unsigned int v1; // ebx
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v0 = wistd::__invoke<long (&)(void *),void * &>();
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
0x18000c864  push    rbx; int
0x18000c866  sub     rsp, 20h
0x18000c86a  call    ??$__invoke@A6AJPEAX@ZAEAPEAX@wistd@@YAJA6AJPEAX@ZAEAPEAX@Z; wistd::__invoke<long (&)(void *),void * &>(long (&)(void *),void * &)
0x18000c86f  mov     ebx, eax
0x18000c871  test    eax, eax
0x18000c873  jns     short loc_18000C892
0x18000c875  mov     rcx, [rsp+28h]; this
0x18000c87a  mov     r9d, eax; char *
0x18000c87d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c884  mov     edx, 5Eh ; '^'; void *
0x18000c889  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c88e  mov     eax, ebx
0x18000c890  jmp     short loc_18000C8C6
0x18000c892  xor     eax, eax
0x18000c894  jmp     short loc_18000C8C6
0x18000c896  mov     ebx, eax
0x18000c898  test    eax, eax
0x18000c89a  js      short loc_18000C8A7
0x18000c89c  jle     short loc_18000C8A7
0x18000c89e  movzx   ebx, ax
0x18000c8a1  or      ebx, 80070000h
0x18000c8a7  test    ebx, ebx
0x18000c8a9  jns     short loc_18000C8C4
0x18000c8ab  mov     rcx, [rsp+28h]; this
0x18000c8b0  mov     r9d, ebx; char *
0x18000c8b3  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c8ba  mov     edx, 63h ; 'c'; void *
0x18000c8bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c8c4  mov     eax, ebx
0x18000c8c6  add     rsp, 20h
0x18000c8ca  pop     rbx
0x18000c8cb  retn
```
