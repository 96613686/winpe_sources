# wil::invoke_rpc_nothrow<long (&)(void *,ushort * *,int *),void * &,ushort * * &,int * &>(long (&)(void *,ushort * *,int *),void * &,ushort * * &,int * &)

- ea: `0x180008abc`
- end: `0x180008b24`
- name: `??$invoke_rpc_nothrow@A6AJPEAXPEAPEAGPEAH@ZAEAPEAXAEAPEAPEAGAEAPEAH@wil@@YAJA6AJPEAXPEAPEAGPEAH@ZAEAPEAXAEAPEAPEAGAEAPEAH@Z`
- size: `104`
- prototype: `__int64 __fastcall(__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD), _QWORD *, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a200`
- `0x18000d580`

## callees

- `0x180006214`
- `0x1800084d8`
- `0x180008abc`

## string_xrefs

- `0x180008ad5`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`
- `0x180008b0b`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::invoke_rpc_nothrow<long (&)(void *,unsigned short * *,int *),void * &,unsigned short * * &,int * &>(
        __int64 (__fastcall *a1)(_QWORD, _QWORD, _QWORD),
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = wistd::__invoke<long (&)(void *,unsigned long *,_STORAGE_DEVICE_DATA * *),void * &,unsigned long * &,_STORAGE_DEVICE_DATA * * &>(
         a1,
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
0x180008abc  push    rbx; int
0x180008abe  sub     rsp, 20h
0x180008ac2  call    ??$__invoke@A6AJPEAXPEAKPEAPEAU_STORAGE_DEVICE_DATA@@@ZAEAPEAXAEAPEAKAEAPEAPEAU1@@wistd@@YAJA6AJPEAXPEAKPEAPEAU_STORAGE_DEVICE_DATA@@@ZAEAPEAXAEAPEAKAEAPEAPEAU1@@Z; wistd::__invoke<long (&)(void *,ulong *,_STORAGE_DEVICE_DATA * *),void * &,ulong * &,_STORAGE_DEVICE_DATA * * &>(long (&)(void *,ulong *,_STORAGE_DEVICE_DATA * *),void * &,ulong * &,_STORAGE_DEVICE_DATA * * &)
0x180008ac7  mov     ebx, eax
0x180008ac9  test    eax, eax
0x180008acb  jns     short loc_180008AEA
0x180008acd  mov     rcx, [rsp+28h]; this
0x180008ad2  mov     r9d, eax; char *
0x180008ad5  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008adc  mov     edx, 5Eh ; '^'; void *
0x180008ae1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008ae6  mov     eax, ebx
0x180008ae8  jmp     short loc_180008B1E
0x180008aea  xor     eax, eax
0x180008aec  jmp     short loc_180008B1E
0x180008aee  mov     ebx, eax
0x180008af0  test    eax, eax
0x180008af2  js      short loc_180008AFF
0x180008af4  jle     short loc_180008AFF
0x180008af6  movzx   ebx, ax
0x180008af9  or      ebx, 80070000h
0x180008aff  test    ebx, ebx
0x180008b01  jns     short loc_180008B1C
0x180008b03  mov     rcx, [rsp+28h]; this
0x180008b08  mov     r9d, ebx; char *
0x180008b0b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008b12  mov     edx, 63h ; 'c'; void *
0x180008b17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008b1c  mov     eax, ebx
0x180008b1e  add     rsp, 20h
0x180008b22  pop     rbx
0x180008b23  retn
```
