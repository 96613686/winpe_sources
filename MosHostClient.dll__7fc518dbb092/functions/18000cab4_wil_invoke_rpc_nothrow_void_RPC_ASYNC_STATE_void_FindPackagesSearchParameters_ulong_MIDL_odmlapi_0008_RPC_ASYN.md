# wil::invoke_rpc_nothrow<void (&)(_RPC_ASYNC_STATE *,void *,FindPackagesSearchParameters,ulong *,__MIDL_odmlapi_0008 * *),_RPC_ASYNC_STATE * &,void * &,FindPackagesSearchParameters &,ulong *,__MIDL_odmlapi_0008 * *>(void (&)(_RPC_ASYNC_STATE *,void *,FindPackagesSearchParameters,ulong *,__MIDL_odmlapi_0008 * *),_RPC_ASYNC_STATE * &,void * &,FindPackagesSearchParameters &,ulong * &&,__MIDL_odmlapi_0008 * * &&)

- ea: `0x18000cab4`
- end: `0x18000cb0d`
- name: `??$invoke_rpc_nothrow@A6AXPEAU_RPC_ASYNC_STATE@@PEAXUFindPackagesSearchParameters@@PEAKPEAPEAU__MIDL_odmlapi_0008@@@ZAEAPEAU1@AEAPEAXAEAU2@PEAKPEAPEAU3@@wil@@YAJA6AXPEAU_RPC_ASYNC_STATE@@PEAXUFindPackagesSearchParameters@@PEAKPEAPEAU__MIDL_odmlapi_0008@@@ZAEAPEAU1@AEAPEAXAEAU2@$$QEAPEAK$$QEAPEAPEAU3@@Z`
- size: `89`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cd20`
- `0x18000e580`

## callees

- `0x180006214`
- `0x18000c7fc`
- `0x18000cab4`

## string_xrefs

- `0x18000caf4`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::invoke_rpc_nothrow<void (&)(_RPC_ASYNC_STATE *,void *,FindPackagesSearchParameters,unsigned long *,__MIDL_odmlapi_0008 * *),_RPC_ASYNC_STATE * &,void * &,FindPackagesSearchParameters &,unsigned long *,__MIDL_odmlapi_0008 * *>(
        int a1,
        int a2,
        int a3,
        int a4,
        __int64 a5,
        __int64 a6)
{
  wistd::__invoke<void (&)(_RPC_ASYNC_STATE *,void *,FindPackagesSearchParameters,unsigned long *,__MIDL_odmlapi_0008 * *),_RPC_ASYNC_STATE * &,void * &,FindPackagesSearchParameters &,unsigned long *,__MIDL_odmlapi_0008 * *>(
    a1,
    a2,
    a3,
    a4,
    a5,
    a6);
  return 0;
}

```

## disassembly

```asm
0x18000cab4  push    rbx
0x18000cab6  sub     rsp, 30h
0x18000caba  mov     rax, [rsp+38h+arg_28]
0x18000cabf  mov     [rsp+38h+var_10], rax
0x18000cac4  mov     rax, [rsp+38h+arg_20]
0x18000cac9  mov     [rsp+38h+var_18], rax
0x18000cace  call    ??$__invoke@A6AXPEAU_RPC_ASYNC_STATE@@PEAXUFindPackagesSearchParameters@@PEAKPEAPEAU__MIDL_odmlapi_0008@@@ZAEAPEAU1@AEAPEAXAEAU2@PEAKPEAPEAU3@@wistd@@YAXA6AXPEAU_RPC_ASYNC_STATE@@PEAXUFindPackagesSearchParameters@@PEAKPEAPEAU__MIDL_odmlapi_0008@@@ZAEAPEAU1@AEAPEAXAEAU2@$$QEAPEAK$$QEAPEAPEAU3@@Z; wistd::__invoke<void (&)(_RPC_ASYNC_STATE *,void *,FindPackagesSearchParameters,ulong *,__MIDL_odmlapi_0008 * *),_RPC_ASYNC_STATE * &,void * &,FindPackagesSearchParameters &,ulong *,__MIDL_odmlapi_0008 * *>(void (&)(_RPC_ASYNC_STATE *,void *,FindPackagesSearchParameters,ulong *,__MIDL_odmlapi_0008 * *),_RPC_ASYNC_STATE * &,void * &,FindPackagesSearchParameters &,ulong * &&,__MIDL_odmlapi_0008 * * &&)
0x18000cad3  xor     eax, eax
0x18000cad5  jmp     short loc_18000CB07
0x18000cad7  mov     ebx, eax
0x18000cad9  test    eax, eax
0x18000cadb  js      short loc_18000CAE8
0x18000cadd  jle     short loc_18000CAE8
0x18000cadf  movzx   ebx, ax
0x18000cae2  or      ebx, 80070000h
0x18000cae8  test    ebx, ebx
0x18000caea  jns     short loc_18000CB05
0x18000caec  mov     rcx, [rsp+38h]; this
0x18000caf1  mov     r9d, ebx; char *
0x18000caf4  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000cafb  mov     edx, 63h ; 'c'; void *
0x18000cb00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cb05  mov     eax, ebx
0x18000cb07  add     rsp, 30h
0x18000cb0b  pop     rbx
0x18000cb0c  retn
```
