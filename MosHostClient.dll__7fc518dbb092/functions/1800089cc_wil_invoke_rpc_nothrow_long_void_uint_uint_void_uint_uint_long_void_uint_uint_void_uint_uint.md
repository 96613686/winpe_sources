# wil::invoke_rpc_nothrow<long (&)(void *,uint *,uint *),void * &,uint * &,uint * &>(long (&)(void *,uint *,uint *),void * &,uint * &,uint * &)

- ea: `0x1800089cc`
- end: `0x180008a3b`
- name: `??$invoke_rpc_nothrow@A6AJPEAXPEAI1@ZAEAPEAXAEAPEAIAEAPEAI@wil@@YAJA6AJPEAXPEAI1@ZAEAPEAXAEAPEAI4@Z`
- size: `111`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009ca0`

## callees

- `0x180006214`
- `0x1800084d8`
- `0x1800089cc`

## string_xrefs

- `0x1800089ec`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`
- `0x180008a22`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::invoke_rpc_nothrow<long (&)(void *,unsigned int *,unsigned int *),void * &,unsigned int * &,unsigned int * &>(
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
         (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))MosHostCacheStateGetSizes,
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
0x1800089cc  push    rbx; int
0x1800089ce  sub     rsp, 20h
0x1800089d2  lea     rcx, MosHostCacheStateGetSizes
0x1800089d9  call    ??$__invoke@A6AJPEAXPEAKPEAPEAU_STORAGE_DEVICE_DATA@@@ZAEAPEAXAEAPEAKAEAPEAPEAU1@@wistd@@YAJA6AJPEAXPEAKPEAPEAU_STORAGE_DEVICE_DATA@@@ZAEAPEAXAEAPEAKAEAPEAPEAU1@@Z; wistd::__invoke<long (&)(void *,ulong *,_STORAGE_DEVICE_DATA * *),void * &,ulong * &,_STORAGE_DEVICE_DATA * * &>(long (&)(void *,ulong *,_STORAGE_DEVICE_DATA * *),void * &,ulong * &,_STORAGE_DEVICE_DATA * * &)
0x1800089de  mov     ebx, eax
0x1800089e0  test    eax, eax
0x1800089e2  jns     short loc_180008A01
0x1800089e4  mov     rcx, [rsp+28h]; this
0x1800089e9  mov     r9d, eax; char *
0x1800089ec  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800089f3  mov     edx, 5Eh ; '^'; void *
0x1800089f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800089fd  mov     eax, ebx
0x1800089ff  jmp     short loc_180008A35
0x180008a01  xor     eax, eax
0x180008a03  jmp     short loc_180008A35
0x180008a05  mov     ebx, eax
0x180008a07  test    eax, eax
0x180008a09  js      short loc_180008A16
0x180008a0b  jle     short loc_180008A16
0x180008a0d  movzx   ebx, ax
0x180008a10  or      ebx, 80070000h
0x180008a16  test    ebx, ebx
0x180008a18  jns     short loc_180008A33
0x180008a1a  mov     rcx, [rsp+28h]; this
0x180008a1f  mov     r9d, ebx; char *
0x180008a22  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008a29  mov     edx, 63h ; 'c'; void *
0x180008a2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a33  mov     eax, ebx
0x180008a35  add     rsp, 20h
0x180008a39  pop     rbx
0x180008a3a  retn
```
