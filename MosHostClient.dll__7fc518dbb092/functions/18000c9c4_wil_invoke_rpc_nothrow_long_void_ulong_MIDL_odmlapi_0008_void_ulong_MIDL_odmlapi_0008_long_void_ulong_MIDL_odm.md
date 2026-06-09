# wil::invoke_rpc_nothrow<long (&)(void *,ulong *,__MIDL_odmlapi_0008 * *),void * &,ulong * &,__MIDL_odmlapi_0008 * * &>(long (&)(void *,ulong *,__MIDL_odmlapi_0008 * *),void * &,ulong * &,__MIDL_odmlapi_0008 * * &)

- ea: `0x18000c9c4`
- end: `0x18000ca33`
- name: `??$invoke_rpc_nothrow@A6AJPEAXPEAKPEAPEAU__MIDL_odmlapi_0008@@@ZAEAPEAXAEAPEAKAEAPEAPEAU1@@wil@@YAJA6AJPEAXPEAKPEAPEAU__MIDL_odmlapi_0008@@@ZAEAPEAXAEAPEAKAEAPEAPEAU1@@Z`
- size: `111`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d700`

## callees

- `0x180006214`
- `0x1800084d8`
- `0x18000c9c4`

## string_xrefs

- `0x18000c9e4`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`
- `0x18000ca1a`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::invoke_rpc_nothrow<long (&)(void *,unsigned long *,__MIDL_odmlapi_0008 * *),void * &,unsigned long * &,__MIDL_odmlapi_0008 * * &>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = wistd::__invoke<long (&)(void *,unsigned long *,_STORAGE_DEVICE_DATA * *),void * &,unsigned long * &,_STORAGE_DEVICE_DATA * * &>(
         (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))OdmlSvcGetUserPackages,
         a2,
         a3,
         a4);
  v5 = v4;
  if ( v4 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5E,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\rpc_helpers.h",
    (const char *)(unsigned int)v4,
    v7);
  return v5;
}

```

## disassembly

```asm
0x18000c9c4  push    rbx; int
0x18000c9c6  sub     rsp, 20h
0x18000c9ca  lea     rcx, OdmlSvcGetUserPackages
0x18000c9d1  call    ??$__invoke@A6AJPEAXPEAKPEAPEAU_STORAGE_DEVICE_DATA@@@ZAEAPEAXAEAPEAKAEAPEAPEAU1@@wistd@@YAJA6AJPEAXPEAKPEAPEAU_STORAGE_DEVICE_DATA@@@ZAEAPEAXAEAPEAKAEAPEAPEAU1@@Z; wistd::__invoke<long (&)(void *,ulong *,_STORAGE_DEVICE_DATA * *),void * &,ulong * &,_STORAGE_DEVICE_DATA * * &>(long (&)(void *,ulong *,_STORAGE_DEVICE_DATA * *),void * &,ulong * &,_STORAGE_DEVICE_DATA * * &)
0x18000c9d6  mov     ebx, eax
0x18000c9d8  test    eax, eax
0x18000c9da  jns     short loc_18000C9F9
0x18000c9dc  mov     rcx, [rsp+28h]; this
0x18000c9e1  mov     r9d, eax; char *
0x18000c9e4  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c9eb  mov     edx, 5Eh ; '^'; void *
0x18000c9f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c9f5  mov     eax, ebx
0x18000c9f7  jmp     short loc_18000CA2D
0x18000c9f9  xor     eax, eax
0x18000c9fb  jmp     short loc_18000CA2D
0x18000c9fd  mov     ebx, eax
0x18000c9ff  test    eax, eax
0x18000ca01  js      short loc_18000CA0E
0x18000ca03  jle     short loc_18000CA0E
0x18000ca05  movzx   ebx, ax
0x18000ca08  or      ebx, 80070000h
0x18000ca0e  test    ebx, ebx
0x18000ca10  jns     short loc_18000CA2B
0x18000ca12  mov     rcx, [rsp+28h]; this
0x18000ca17  mov     r9d, ebx; char *
0x18000ca1a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ca21  mov     edx, 63h ; 'c'; void *
0x18000ca26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ca2b  mov     eax, ebx
0x18000ca2d  add     rsp, 20h
0x18000ca31  pop     rbx
0x18000ca32  retn
```
