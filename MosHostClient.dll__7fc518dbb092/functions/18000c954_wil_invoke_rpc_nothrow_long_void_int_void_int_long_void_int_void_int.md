# wil::invoke_rpc_nothrow<long (&)(void *,int *),void * &,int * &>(long (&)(void *,int *),void * &,int * &)

- ea: `0x18000c954`
- end: `0x18000c9bc`
- name: `??$invoke_rpc_nothrow@A6AJPEAXPEAH@ZAEAPEAXAEAPEAH@wil@@YAJA6AJPEAXPEAH@ZAEAPEAXAEAPEAH@Z`
- size: `104`
- prototype: `__int64()`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d4b0`
- `0x18000d5e0`
- `0x18000d640`
- `0x18000d6a0`
- `0x18000ff10`

## callees

- `0x180006214`
- `0x180008504`
- `0x18000c954`

## string_xrefs

- `0x18000c96d`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`
- `0x18000c9a3`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 wil::invoke_rpc_nothrow<long (&)(void *,int *),void * &,int * &>()
{
  int v0; // eax
  unsigned int v1; // ebx
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v0 = wistd::__invoke<long (&)(void *,unsigned long *),void * &,unsigned long * &>();
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
0x18000c954  push    rbx; int
0x18000c956  sub     rsp, 20h
0x18000c95a  call    ??$__invoke@A6AJPEAXPEAK@ZAEAPEAXAEAPEAK@wistd@@YAJA6AJPEAXPEAK@ZAEAPEAXAEAPEAK@Z; wistd::__invoke<long (&)(void *,ulong *),void * &,ulong * &>(long (&)(void *,ulong *),void * &,ulong * &)
0x18000c95f  mov     ebx, eax
0x18000c961  test    eax, eax
0x18000c963  jns     short loc_18000C982
0x18000c965  mov     rcx, [rsp+28h]; this
0x18000c96a  mov     r9d, eax; char *
0x18000c96d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c974  mov     edx, 5Eh ; '^'; void *
0x18000c979  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c97e  mov     eax, ebx
0x18000c980  jmp     short loc_18000C9B6
0x18000c982  xor     eax, eax
0x18000c984  jmp     short loc_18000C9B6
0x18000c986  mov     ebx, eax
0x18000c988  test    eax, eax
0x18000c98a  js      short loc_18000C997
0x18000c98c  jle     short loc_18000C997
0x18000c98e  movzx   ebx, ax
0x18000c991  or      ebx, 80070000h
0x18000c997  test    ebx, ebx
0x18000c999  jns     short loc_18000C9B4
0x18000c99b  mov     rcx, [rsp+28h]; this
0x18000c9a0  mov     r9d, ebx; char *
0x18000c9a3  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c9aa  mov     edx, 63h ; 'c'; void *
0x18000c9af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c9b4  mov     eax, ebx
0x18000c9b6  add     rsp, 20h
0x18000c9ba  pop     rbx
0x18000c9bb  retn
```
