# wil::invoke_rpc_nothrow<void (&)(_RPC_ASYNC_STATE *,void *,_GUID,_STORAGE_DEVICE_VALIDATION_RESULT *),_RPC_ASYNC_STATE * &,void * &,_GUID &,_STORAGE_DEVICE_VALIDATION_RESULT *>(void (&)(_RPC_ASYNC_STATE *,void *,_GUID,_STORAGE_DEVICE_VALIDATION_RESULT *),_RPC_ASYNC_STATE * &,void * &,_GUID &,_STORAGE_DEVICE_VALIDATION_RESULT * &&)

- ea: `0x18000f634`
- end: `0x18000f68a`
- name: `??$invoke_rpc_nothrow@A6AXPEAU_RPC_ASYNC_STATE@@PEAXU_GUID@@PEAU_STORAGE_DEVICE_VALIDATION_RESULT@@@ZAEAPEAU1@AEAPEAXAEAU2@PEAU3@@wil@@YAJA6AXPEAU_RPC_ASYNC_STATE@@PEAXU_GUID@@PEAU_STORAGE_DEVICE_VALIDATION_RESULT@@@ZAEAPEAU1@AEAPEAXAEAU2@$$QEAPEAU3@@Z`
- size: `86`
- prototype: `__int64 __fastcall(__int64, int, int, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f690`

## callees

- `0x180006214`
- `0x18000f48c`
- `0x18000f634`

## string_xrefs

- `0x18000f671`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::invoke_rpc_nothrow<void (&)(_RPC_ASYNC_STATE *,void *,_GUID,_STORAGE_DEVICE_VALIDATION_RESULT *),_RPC_ASYNC_STATE * &,void * &,_GUID &,_STORAGE_DEVICE_VALIDATION_RESULT *>(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        __int64 a5)
{
  wistd::__invoke<void (&)(_RPC_ASYNC_STATE *,void *,_GUID,_STORAGE_DEVICE_VALIDATION_RESULT *),_RPC_ASYNC_STATE * &,void * &,_GUID &,_STORAGE_DEVICE_VALIDATION_RESULT *>(
    (unsigned int)MapsStorageSvcValidateLocationAsync,
    a2,
    a3,
    a4,
    a5);
  return 0;
}

```

## disassembly

```asm
0x18000f634  push    rbx
0x18000f636  sub     rsp, 30h
0x18000f63a  mov     rax, [rsp+38h+arg_20]
0x18000f63f  mov     [rsp+38h+var_18], rax
0x18000f644  lea     rcx, MapsStorageSvcValidateLocationAsync
0x18000f64b  call    ??$__invoke@A6AXPEAU_RPC_ASYNC_STATE@@PEAXU_GUID@@PEAU_STORAGE_DEVICE_VALIDATION_RESULT@@@ZAEAPEAU1@AEAPEAXAEAU2@PEAU3@@wistd@@YAXA6AXPEAU_RPC_ASYNC_STATE@@PEAXU_GUID@@PEAU_STORAGE_DEVICE_VALIDATION_RESULT@@@ZAEAPEAU1@AEAPEAXAEAU2@$$QEAPEAU3@@Z; wistd::__invoke<void (&)(_RPC_ASYNC_STATE *,void *,_GUID,_STORAGE_DEVICE_VALIDATION_RESULT *),_RPC_ASYNC_STATE * &,void * &,_GUID &,_STORAGE_DEVICE_VALIDATION_RESULT *>(void (&)(_RPC_ASYNC_STATE *,void *,_GUID,_STORAGE_DEVICE_VALIDATION_RESULT *),_RPC_ASYNC_STATE * &,void * &,_GUID &,_STORAGE_DEVICE_VALIDATION_RESULT * &&)
0x18000f650  xor     eax, eax
0x18000f652  jmp     short loc_18000F684
0x18000f654  mov     ebx, eax
0x18000f656  test    eax, eax
0x18000f658  js      short loc_18000F665
0x18000f65a  jle     short loc_18000F665
0x18000f65c  movzx   ebx, ax
0x18000f65f  or      ebx, 80070000h
0x18000f665  test    ebx, ebx
0x18000f667  jns     short loc_18000F682
0x18000f669  mov     rcx, [rsp+38h]; this
0x18000f66e  mov     r9d, ebx; char *
0x18000f671  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f678  mov     edx, 63h ; 'c'; void *
0x18000f67d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f682  mov     eax, ebx
0x18000f684  add     rsp, 30h
0x18000f688  pop     rbx
0x18000f689  retn
```
