# wil::invoke_rpc_nothrow<long (*&)(ushort const *,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,void *,void * *),ushort const * &,__MIDL___MIDL_itf_moshostapi_0000_0000_0001 &,void *,void * *>(long (*&)(ushort const *,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,void *,void * *),ushort const * &,__MIDL___MIDL_itf_moshostapi_0000_0000_0001 &,void * &&,void * * &&)

- ea: `0x180008cb4`
- end: `0x180008d3c`
- name: `??$invoke_rpc_nothrow@AEAP6AJPEBGW4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@PEAXPEAPEAX@ZAEAPEBGAEAW41@PEAXPEAPEAX@wil@@YAJAEAP6AJPEBGW4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@PEAXPEAPEAX@ZAEAPEBGAEAW41@$$QEAPEAX$$QEAPEAPEAX@Z`
- size: `136`
- prototype: `__int64 __fastcall(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD), _QWORD *, unsigned int *, _QWORD *, _QWORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b8e8`
- `0x18000dad8`
- `0x18000f1e4`
- `0x180010038`

## callees

- `0x180006214`
- `0x180008cb4`
- `0x180012010`

## string_xrefs

- `0x180008ced`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`
- `0x180008d23`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::invoke_rpc_nothrow<long (*&)(unsigned short const *,enum __MIDL___MIDL_itf_moshostapi_0000_0000_0001,void *,void * *),unsigned short const * &,enum __MIDL___MIDL_itf_moshostapi_0000_0000_0001 &,void *,void * *>(
        __int64 (__fastcall **a1)(_QWORD, _QWORD, _QWORD, _QWORD),
        _QWORD *a2,
        unsigned int *a3,
        _QWORD *a4,
        _QWORD *a5)
{
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v5 = (*a1)(*a2, *a3, *a4, *a5);
  v6 = v5;
  if ( v5 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5E,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\rpc_helpers.h",
    (const char *)(unsigned int)v5,
    v8);
  return v6;
}

```

## disassembly

```asm
0x180008cb4  push    rbx
0x180008cb6  sub     rsp, 30h
0x180008cba  mov     rax, r9
0x180008cbd  mov     r10, r8
0x180008cc0  mov     r11, rdx
0x180008cc3  mov     rbx, rcx
0x180008cc6  mov     r9, [rsp+38h+arg_20]
0x180008ccb  mov     r9, [r9]
0x180008cce  mov     r8, [rax]
0x180008cd1  mov     edx, [r10]
0x180008cd4  mov     rcx, [r11]
0x180008cd7  mov     rax, [rbx]
0x180008cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cdf  mov     ebx, eax
0x180008ce1  test    eax, eax
0x180008ce3  jns     short loc_180008D02
0x180008ce5  mov     rcx, [rsp+38h]; this
0x180008cea  mov     r9d, eax; char *
0x180008ced  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008cf4  mov     edx, 5Eh ; '^'; void *
0x180008cf9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008cfe  mov     eax, ebx
0x180008d00  jmp     short loc_180008D36
0x180008d02  xor     eax, eax
0x180008d04  jmp     short loc_180008D36
0x180008d06  mov     ebx, eax
0x180008d08  test    eax, eax
0x180008d0a  js      short loc_180008D17
0x180008d0c  jle     short loc_180008D17
0x180008d0e  movzx   ebx, ax
0x180008d11  or      ebx, 80070000h
0x180008d17  test    ebx, ebx
0x180008d19  jns     short loc_180008D34
0x180008d1b  mov     rcx, [rsp+38h]; this
0x180008d20  mov     r9d, ebx; char *
0x180008d23  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008d2a  mov     edx, 63h ; 'c'; void *
0x180008d2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d34  mov     eax, ebx
0x180008d36  add     rsp, 30h
0x180008d3a  pop     rbx
0x180008d3b  retn
```
