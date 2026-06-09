# wil::invoke_rpc_nothrow<long (&)(void *,__MIDL_odmlapi_0006,_GUID),void * &,__MIDL_odmlapi_0006 &,_GUID &>(long (&)(void *,__MIDL_odmlapi_0006,_GUID),void * &,__MIDL_odmlapi_0006 &,_GUID &)

- ea: `0x18000ca3c`
- end: `0x18000caab`
- name: `??$invoke_rpc_nothrow@A6AJPEAXW4__MIDL_odmlapi_0006@@U_GUID@@@ZAEAPEAXAEAW41@AEAU2@@wil@@YAJA6AJPEAXW4__MIDL_odmlapi_0006@@U_GUID@@@ZAEAPEAXAEAW41@AEAU2@@Z`
- size: `111`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000da30`

## callees

- `0x180006214`
- `0x18000c7c4`
- `0x18000ca3c`

## string_xrefs

- `0x18000ca5c`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`
- `0x18000ca92`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 wil::invoke_rpc_nothrow<long (&)(void *,enum __MIDL_odmlapi_0006,_GUID),void * &,enum __MIDL_odmlapi_0006 &,_GUID &>()
{
  int v0; // eax
  unsigned int v1; // ebx
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v0 = wistd::__invoke<long (&)(void *,enum __MIDL_odmlapi_0006,_GUID),void * &,enum __MIDL_odmlapi_0006 &,_GUID &>(OdmlSvcStartMapDataMigration);
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
0x18000ca3c  push    rbx; int
0x18000ca3e  sub     rsp, 20h
0x18000ca42  lea     rcx, OdmlSvcStartMapDataMigration
0x18000ca49  call    ??$__invoke@A6AJPEAXW4__MIDL_odmlapi_0006@@U_GUID@@@ZAEAPEAXAEAW41@AEAU2@@wistd@@YAJA6AJPEAXW4__MIDL_odmlapi_0006@@U_GUID@@@ZAEAPEAXAEAW41@AEAU2@@Z; wistd::__invoke<long (&)(void *,__MIDL_odmlapi_0006,_GUID),void * &,__MIDL_odmlapi_0006 &,_GUID &>(long (&)(void *,__MIDL_odmlapi_0006,_GUID),void * &,__MIDL_odmlapi_0006 &,_GUID &)
0x18000ca4e  mov     ebx, eax
0x18000ca50  test    eax, eax
0x18000ca52  jns     short loc_18000CA71
0x18000ca54  mov     rcx, [rsp+28h]; this
0x18000ca59  mov     r9d, eax; char *
0x18000ca5c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ca63  mov     edx, 5Eh ; '^'; void *
0x18000ca68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ca6d  mov     eax, ebx
0x18000ca6f  jmp     short loc_18000CAA5
0x18000ca71  xor     eax, eax
0x18000ca73  jmp     short loc_18000CAA5
0x18000ca75  mov     ebx, eax
0x18000ca77  test    eax, eax
0x18000ca79  js      short loc_18000CA86
0x18000ca7b  jle     short loc_18000CA86
0x18000ca7d  movzx   ebx, ax
0x18000ca80  or      ebx, 80070000h
0x18000ca86  test    ebx, ebx
0x18000ca88  jns     short loc_18000CAA3
0x18000ca8a  mov     rcx, [rsp+28h]; this
0x18000ca8f  mov     r9d, ebx; char *
0x18000ca92  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ca99  mov     edx, 63h ; 'c'; void *
0x18000ca9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000caa3  mov     eax, ebx
0x18000caa5  add     rsp, 20h
0x18000caa9  pop     rbx
0x18000caaa  retn
```
