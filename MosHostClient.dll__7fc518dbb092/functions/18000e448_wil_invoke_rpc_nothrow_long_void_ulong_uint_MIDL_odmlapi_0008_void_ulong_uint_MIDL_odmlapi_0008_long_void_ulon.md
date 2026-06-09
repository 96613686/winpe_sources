# wil::invoke_rpc_nothrow<long (&)(void *,ulong,uint *,__MIDL_odmlapi_0008 * *),void * &,ulong &,uint * &,__MIDL_odmlapi_0008 * * &>(long (&)(void *,ulong,uint *,__MIDL_odmlapi_0008 * *),void * &,ulong &,uint * &,__MIDL_odmlapi_0008 * * &)

- ea: `0x18000e448`
- end: `0x18000e4c1`
- name: `??$invoke_rpc_nothrow@A6AJPEAXKPEAIPEAPEAU__MIDL_odmlapi_0008@@@ZAEAPEAXAEAKAEAPEAIAEAPEAPEAU1@@wil@@YAJA6AJPEAXKPEAIPEAPEAU__MIDL_odmlapi_0008@@@ZAEAPEAXAEAKAEAPEAIAEAPEAPEAU1@@Z`
- size: `121`
- prototype: `__int64 __fastcall(__int64, int, int, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f050`

## callees

- `0x180006214`
- `0x18000c78c`
- `0x18000e448`

## string_xrefs

- `0x18000e472`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`
- `0x18000e4a8`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::invoke_rpc_nothrow<long (&)(void *,unsigned long,unsigned int *,__MIDL_odmlapi_0008 * *),void * &,unsigned long &,unsigned int * &,__MIDL_odmlapi_0008 * * &>(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        __int64 a5)
{
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v5 = wistd::__invoke<long (&)(void *,unsigned long,unsigned int *,__MIDL_odmlapi_0008 * *),void * &,unsigned long &,unsigned int * &,__MIDL_odmlapi_0008 * * &>(
         (unsigned int)MapsPackageSvcGetPackages,
         a2,
         a3,
         a4,
         a5);
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
0x18000e448  push    rbx
0x18000e44a  sub     rsp, 30h
0x18000e44e  mov     rax, qword ptr [rsp+38h+arg_20]
0x18000e453  mov     qword ptr [rsp+38h+var_18], rax; int
0x18000e458  lea     rcx, MapsPackageSvcGetPackages
0x18000e45f  call    ??$__invoke@A6AJPEAXKPEAIPEAPEAU__MIDL_odmlapi_0008@@@ZAEAPEAXAEAKAEAPEAIAEAPEAPEAU1@@wistd@@YAJA6AJPEAXKPEAIPEAPEAU__MIDL_odmlapi_0008@@@ZAEAPEAXAEAKAEAPEAIAEAPEAPEAU1@@Z; wistd::__invoke<long (&)(void *,ulong,uint *,__MIDL_odmlapi_0008 * *),void * &,ulong &,uint * &,__MIDL_odmlapi_0008 * * &>(long (&)(void *,ulong,uint *,__MIDL_odmlapi_0008 * *),void * &,ulong &,uint * &,__MIDL_odmlapi_0008 * * &)
0x18000e464  mov     ebx, eax
0x18000e466  test    eax, eax
0x18000e468  jns     short loc_18000E487
0x18000e46a  mov     rcx, [rsp+38h]; this
0x18000e46f  mov     r9d, eax; char *
0x18000e472  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e479  mov     edx, 5Eh ; '^'; void *
0x18000e47e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e483  mov     eax, ebx
0x18000e485  jmp     short loc_18000E4BB
0x18000e487  xor     eax, eax
0x18000e489  jmp     short loc_18000E4BB
0x18000e48b  mov     ebx, eax
0x18000e48d  test    eax, eax
0x18000e48f  js      short loc_18000E49C
0x18000e491  jle     short loc_18000E49C
0x18000e493  movzx   ebx, ax
0x18000e496  or      ebx, 80070000h
0x18000e49c  test    ebx, ebx
0x18000e49e  jns     short loc_18000E4B9
0x18000e4a0  mov     rcx, [rsp+38h]; this
0x18000e4a5  mov     r9d, ebx; char *
0x18000e4a8  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e4af  mov     edx, 63h ; 'c'; void *
0x18000e4b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e4b9  mov     eax, ebx
0x18000e4bb  add     rsp, 30h
0x18000e4bf  pop     rbx
0x18000e4c0  retn
```
