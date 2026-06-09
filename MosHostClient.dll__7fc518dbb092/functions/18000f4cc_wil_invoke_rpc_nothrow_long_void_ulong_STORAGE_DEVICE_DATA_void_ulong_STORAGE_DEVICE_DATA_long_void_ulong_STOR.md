# wil::invoke_rpc_nothrow<long (&)(void *,ulong *,_STORAGE_DEVICE_DATA * *),void * &,ulong * &,_STORAGE_DEVICE_DATA * * &>(long (&)(void *,ulong *,_STORAGE_DEVICE_DATA * *),void * &,ulong * &,_STORAGE_DEVICE_DATA * * &)

- ea: `0x18000f4cc`
- end: `0x18000f53b`
- name: `??$invoke_rpc_nothrow@A6AJPEAXPEAKPEAPEAU_STORAGE_DEVICE_DATA@@@ZAEAPEAXAEAPEAKAEAPEAPEAU1@@wil@@YAJA6AJPEAXPEAKPEAPEAU_STORAGE_DEVICE_DATA@@@ZAEAPEAXAEAPEAKAEAPEAPEAU1@@Z`
- size: `111`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fce0`

## callees

- `0x180006214`
- `0x1800084d8`
- `0x18000f4cc`

## string_xrefs

- `0x18000f4ec`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`
- `0x18000f522`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::invoke_rpc_nothrow<long (&)(void *,unsigned long *,_STORAGE_DEVICE_DATA * *),void * &,unsigned long * &,_STORAGE_DEVICE_DATA * * &>(
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
         (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))MapsStorageSvcGetLocations,
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
0x18000f4cc  push    rbx; int
0x18000f4ce  sub     rsp, 20h
0x18000f4d2  lea     rcx, MapsStorageSvcGetLocations
0x18000f4d9  call    ??$__invoke@A6AJPEAXPEAKPEAPEAU_STORAGE_DEVICE_DATA@@@ZAEAPEAXAEAPEAKAEAPEAPEAU1@@wistd@@YAJA6AJPEAXPEAKPEAPEAU_STORAGE_DEVICE_DATA@@@ZAEAPEAXAEAPEAKAEAPEAPEAU1@@Z; wistd::__invoke<long (&)(void *,ulong *,_STORAGE_DEVICE_DATA * *),void * &,ulong * &,_STORAGE_DEVICE_DATA * * &>(long (&)(void *,ulong *,_STORAGE_DEVICE_DATA * *),void * &,ulong * &,_STORAGE_DEVICE_DATA * * &)
0x18000f4de  mov     ebx, eax
0x18000f4e0  test    eax, eax
0x18000f4e2  jns     short loc_18000F501
0x18000f4e4  mov     rcx, [rsp+28h]; this
0x18000f4e9  mov     r9d, eax; char *
0x18000f4ec  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f4f3  mov     edx, 5Eh ; '^'; void *
0x18000f4f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f4fd  mov     eax, ebx
0x18000f4ff  jmp     short loc_18000F535
0x18000f501  xor     eax, eax
0x18000f503  jmp     short loc_18000F535
0x18000f505  mov     ebx, eax
0x18000f507  test    eax, eax
0x18000f509  js      short loc_18000F516
0x18000f50b  jle     short loc_18000F516
0x18000f50d  movzx   ebx, ax
0x18000f510  or      ebx, 80070000h
0x18000f516  test    ebx, ebx
0x18000f518  jns     short loc_18000F533
0x18000f51a  mov     rcx, [rsp+28h]; this
0x18000f51f  mov     r9d, ebx; char *
0x18000f522  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f529  mov     edx, 63h ; 'c'; void *
0x18000f52e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f533  mov     eax, ebx
0x18000f535  add     rsp, 20h
0x18000f539  pop     rbx
0x18000f53a  retn
```
