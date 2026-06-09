# wil::invoke_rpc_nothrow<void (&)(_RPC_ASYNC_STATE *,void *,uint),_RPC_ASYNC_STATE * &,void * &,uint &>(void (&)(_RPC_ASYNC_STATE *,void *,uint),_RPC_ASYNC_STATE * &,void * &,uint &)

- ea: `0x18000e4c8`
- end: `0x18000e514`
- name: `??$invoke_rpc_nothrow@A6AXPEAU_RPC_ASYNC_STATE@@PEAXI@ZAEAPEAU1@AEAPEAXAEAI@wil@@YAJA6AXPEAU_RPC_ASYNC_STATE@@PEAXI@ZAEAPEAU1@AEAPEAXAEAI@Z`
- size: `76`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e520`

## callees

- `0x180006214`
- `0x1800084ac`
- `0x18000e4c8`

## string_xrefs

- `0x18000e4fb`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 wil::invoke_rpc_nothrow<void (&)(_RPC_ASYNC_STATE *,void *,unsigned int),_RPC_ASYNC_STATE * &,void * &,unsigned int &>()
{
  wistd::__invoke<void (&)(_RPC_ASYNC_STATE *,void *,unsigned int),_RPC_ASYNC_STATE * &,void * &,unsigned int &>(MapsPackageSvcAddMapPackageAsync);
  return 0;
}

```

## disassembly

```asm
0x18000e4c8  push    rbx
0x18000e4ca  sub     rsp, 20h
0x18000e4ce  lea     rcx, MapsPackageSvcAddMapPackageAsync
0x18000e4d5  call    ??$__invoke@A6AXPEAU_RPC_ASYNC_STATE@@PEAXI@ZAEAPEAU1@AEAPEAXAEAI@wistd@@YAXA6AXPEAU_RPC_ASYNC_STATE@@PEAXI@ZAEAPEAU1@AEAPEAXAEAI@Z; wistd::__invoke<void (&)(_RPC_ASYNC_STATE *,void *,uint),_RPC_ASYNC_STATE * &,void * &,uint &>(void (&)(_RPC_ASYNC_STATE *,void *,uint),_RPC_ASYNC_STATE * &,void * &,uint &)
0x18000e4da  xor     eax, eax
0x18000e4dc  jmp     short loc_18000E50E
0x18000e4de  mov     ebx, eax
0x18000e4e0  test    eax, eax
0x18000e4e2  js      short loc_18000E4EF
0x18000e4e4  jle     short loc_18000E4EF
0x18000e4e6  movzx   ebx, ax
0x18000e4e9  or      ebx, 80070000h
0x18000e4ef  test    ebx, ebx
0x18000e4f1  jns     short loc_18000E50C
0x18000e4f3  mov     rcx, [rsp+28h]; this
0x18000e4f8  mov     r9d, ebx; char *
0x18000e4fb  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e502  mov     edx, 63h ; 'c'; void *
0x18000e507  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e50c  mov     eax, ebx
0x18000e50e  add     rsp, 20h
0x18000e512  pop     rbx
0x18000e513  retn
```
