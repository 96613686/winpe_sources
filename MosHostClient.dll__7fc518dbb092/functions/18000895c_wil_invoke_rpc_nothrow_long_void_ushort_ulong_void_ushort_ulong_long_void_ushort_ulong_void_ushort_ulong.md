# wil::invoke_rpc_nothrow<long (&)(void *,ushort *,ulong),void * &,ushort * &,ulong &>(long (&)(void *,ushort *,ulong),void * &,ushort * &,ulong &)

- ea: `0x18000895c`
- end: `0x1800089c4`
- name: `??$invoke_rpc_nothrow@A6AJPEAXPEAGK@ZAEAPEAXAEAPEAGAEAK@wil@@YAJA6AJPEAXPEAGK@ZAEAPEAXAEAPEAGAEAK@Z`
- size: `104`
- prototype: `__int64()`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a660`
- `0x18000a6e0`
- `0x18000d0c0`
- `0x18000d870`
- `0x18000fc60`

## callees

- `0x180006214`
- `0x1800084ac`
- `0x18000895c`

## string_xrefs

- `0x180008975`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`
- `0x1800089ab`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 wil::invoke_rpc_nothrow<long (&)(void *,unsigned short *,unsigned long),void * &,unsigned short * &,unsigned long &>()
{
  int v0; // eax
  unsigned int v1; // ebx
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v0 = wistd::__invoke<void (&)(_RPC_ASYNC_STATE *,void *,unsigned int),_RPC_ASYNC_STATE * &,void * &,unsigned int &>();
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
0x18000895c  push    rbx; int
0x18000895e  sub     rsp, 20h
0x180008962  call    ??$__invoke@A6AXPEAU_RPC_ASYNC_STATE@@PEAXI@ZAEAPEAU1@AEAPEAXAEAI@wistd@@YAXA6AXPEAU_RPC_ASYNC_STATE@@PEAXI@ZAEAPEAU1@AEAPEAXAEAI@Z; wistd::__invoke<void (&)(_RPC_ASYNC_STATE *,void *,uint),_RPC_ASYNC_STATE * &,void * &,uint &>(void (&)(_RPC_ASYNC_STATE *,void *,uint),_RPC_ASYNC_STATE * &,void * &,uint &)
0x180008967  mov     ebx, eax
0x180008969  test    eax, eax
0x18000896b  jns     short loc_18000898A
0x18000896d  mov     rcx, [rsp+28h]; this
0x180008972  mov     r9d, eax; char *
0x180008975  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000897c  mov     edx, 5Eh ; '^'; void *
0x180008981  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008986  mov     eax, ebx
0x180008988  jmp     short loc_1800089BE
0x18000898a  xor     eax, eax
0x18000898c  jmp     short loc_1800089BE
0x18000898e  mov     ebx, eax
0x180008990  test    eax, eax
0x180008992  js      short loc_18000899F
0x180008994  jle     short loc_18000899F
0x180008996  movzx   ebx, ax
0x180008999  or      ebx, 80070000h
0x18000899f  test    ebx, ebx
0x1800089a1  jns     short loc_1800089BC
0x1800089a3  mov     rcx, [rsp+28h]; this
0x1800089a8  mov     r9d, ebx; char *
0x1800089ab  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800089b2  mov     edx, 63h ; 'c'; void *
0x1800089b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800089bc  mov     eax, ebx
0x1800089be  add     rsp, 20h
0x1800089c2  pop     rbx
0x1800089c3  retn
```
