# wil::invoke_rpc_nothrow<void (&)(_RPC_ASYNC_STATE *,void *,int,int),_RPC_ASYNC_STATE * &,void * &,int &,int &>(void (&)(_RPC_ASYNC_STATE *,void *,int,int),_RPC_ASYNC_STATE * &,void * &,int &,int &)

- ea: `0x180008b2c`
- end: `0x180008b82`
- name: `??$invoke_rpc_nothrow@A6AXPEAU_RPC_ASYNC_STATE@@PEAXHH@ZAEAPEAU1@AEAPEAXAEAHAEAH@wil@@YAJA6AXPEAU_RPC_ASYNC_STATE@@PEAXHH@ZAEAPEAU1@AEAPEAXAEAH5@Z`
- size: `86`
- prototype: `__int64 __fastcall(__int64, int, int, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009670`

## callees

- `0x180006214`
- `0x180008528`
- `0x180008b2c`

## string_xrefs

- `0x180008b69`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::invoke_rpc_nothrow<void (&)(_RPC_ASYNC_STATE *,void *,int,int),_RPC_ASYNC_STATE * &,void * &,int &,int &>(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        __int64 a5)
{
  wistd::__invoke<void (&)(_RPC_ASYNC_STATE *,void *,int,int),_RPC_ASYNC_STATE * &,void * &,int &,int &>(
    (unsigned int)MosHostDeleteDataAsync,
    a2,
    a3,
    a4,
    a5);
  return 0;
}

```

## disassembly

```asm
0x180008b2c  push    rbx
0x180008b2e  sub     rsp, 30h
0x180008b32  mov     rax, [rsp+38h+arg_20]
0x180008b37  mov     [rsp+38h+var_18], rax
0x180008b3c  lea     rcx, MosHostDeleteDataAsync
0x180008b43  call    ??$__invoke@A6AXPEAU_RPC_ASYNC_STATE@@PEAXHH@ZAEAPEAU1@AEAPEAXAEAHAEAH@wistd@@YAXA6AXPEAU_RPC_ASYNC_STATE@@PEAXHH@ZAEAPEAU1@AEAPEAXAEAH5@Z; wistd::__invoke<void (&)(_RPC_ASYNC_STATE *,void *,int,int),_RPC_ASYNC_STATE * &,void * &,int &,int &>(void (&)(_RPC_ASYNC_STATE *,void *,int,int),_RPC_ASYNC_STATE * &,void * &,int &,int &)
0x180008b48  xor     eax, eax
0x180008b4a  jmp     short loc_180008B7C
0x180008b4c  mov     ebx, eax
0x180008b4e  test    eax, eax
0x180008b50  js      short loc_180008B5D
0x180008b52  jle     short loc_180008B5D
0x180008b54  movzx   ebx, ax
0x180008b57  or      ebx, 80070000h
0x180008b5d  test    ebx, ebx
0x180008b5f  jns     short loc_180008B7A
0x180008b61  mov     rcx, [rsp+38h]; this
0x180008b66  mov     r9d, ebx; char *
0x180008b69  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008b70  mov     edx, 63h ; 'c'; void *
0x180008b75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008b7a  mov     eax, ebx
0x180008b7c  add     rsp, 30h
0x180008b80  pop     rbx
0x180008b81  retn
```
