# wil::invoke_rpc_nothrow<long (&)(void *,_STORAGE_DEVICE_DATA *),void * &,_STORAGE_DEVICE_DATA * &>(long (&)(void *,_STORAGE_DEVICE_DATA *),void * &,_STORAGE_DEVICE_DATA * &)

- ea: `0x18000f5bc`
- end: `0x18000f62b`
- name: `??$invoke_rpc_nothrow@A6AJPEAXPEAU_STORAGE_DEVICE_DATA@@@ZAEAPEAXAEAPEAU1@@wil@@YAJA6AJPEAXPEAU_STORAGE_DEVICE_DATA@@@ZAEAPEAXAEAPEAU1@@Z`
- size: `111`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fc00`

## callees

- `0x180006214`
- `0x180008504`
- `0x18000f5bc`

## string_xrefs

- `0x18000f5dc`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`
- `0x18000f612`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 wil::invoke_rpc_nothrow<long (&)(void *,_STORAGE_DEVICE_DATA *),void * &,_STORAGE_DEVICE_DATA * &>()
{
  int v0; // eax
  unsigned int v1; // ebx
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v0 = wistd::__invoke<long (&)(void *,unsigned long *),void * &,unsigned long * &>(MapsStorageSvcGetCurrentLocation);
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
0x18000f5bc  push    rbx; int
0x18000f5be  sub     rsp, 20h
0x18000f5c2  lea     rcx, MapsStorageSvcGetCurrentLocation
0x18000f5c9  call    ??$__invoke@A6AJPEAXPEAK@ZAEAPEAXAEAPEAK@wistd@@YAJA6AJPEAXPEAK@ZAEAPEAXAEAPEAK@Z; wistd::__invoke<long (&)(void *,ulong *),void * &,ulong * &>(long (&)(void *,ulong *),void * &,ulong * &)
0x18000f5ce  mov     ebx, eax
0x18000f5d0  test    eax, eax
0x18000f5d2  jns     short loc_18000F5F1
0x18000f5d4  mov     rcx, [rsp+28h]; this
0x18000f5d9  mov     r9d, eax; char *
0x18000f5dc  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f5e3  mov     edx, 5Eh ; '^'; void *
0x18000f5e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f5ed  mov     eax, ebx
0x18000f5ef  jmp     short loc_18000F625
0x18000f5f1  xor     eax, eax
0x18000f5f3  jmp     short loc_18000F625
0x18000f5f5  mov     ebx, eax
0x18000f5f7  test    eax, eax
0x18000f5f9  js      short loc_18000F606
0x18000f5fb  jle     short loc_18000F606
0x18000f5fd  movzx   ebx, ax
0x18000f600  or      ebx, 80070000h
0x18000f606  test    ebx, ebx
0x18000f608  jns     short loc_18000F623
0x18000f60a  mov     rcx, [rsp+28h]; this
0x18000f60f  mov     r9d, ebx; char *
0x18000f612  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f619  mov     edx, 63h ; 'c'; void *
0x18000f61e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f623  mov     eax, ebx
0x18000f625  add     rsp, 20h
0x18000f629  pop     rbx
0x18000f62a  retn
```
