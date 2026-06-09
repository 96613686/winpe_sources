# wil::invoke_rpc_nothrow<long (&)(void *,uint,ulong *,__MIDL_odmlapi_0008 * *),void * &,uint &,ulong * &,__MIDL_odmlapi_0008 * * &>(long (&)(void *,uint,ulong *,__MIDL_odmlapi_0008 * *),void * &,uint &,ulong * &,__MIDL_odmlapi_0008 * * &)

- ea: `0x18000c8d4`
- end: `0x18000c94d`
- name: `??$invoke_rpc_nothrow@A6AJPEAXIPEAKPEAPEAU__MIDL_odmlapi_0008@@@ZAEAPEAXAEAIAEAPEAKAEAPEAPEAU1@@wil@@YAJA6AJPEAXIPEAKPEAPEAU__MIDL_odmlapi_0008@@@ZAEAPEAXAEAIAEAPEAKAEAPEAPEAU1@@Z`
- size: `121`
- prototype: `__int64 __fastcall(__int64, int, int, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d510`

## callees

- `0x180006214`
- `0x18000c78c`
- `0x18000c8d4`

## string_xrefs

- `0x18000c8fe`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`
- `0x18000c934`: `onecore\internal\sdk\inc\wil\opensource\wil\rpc_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::invoke_rpc_nothrow<long (&)(void *,unsigned int,unsigned long *,__MIDL_odmlapi_0008 * *),void * &,unsigned int &,unsigned long * &,__MIDL_odmlapi_0008 * * &>(
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
         (unsigned int)OdmlSvcGetAvailablePackages,
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
0x18000c8d4  push    rbx
0x18000c8d6  sub     rsp, 30h
0x18000c8da  mov     rax, qword ptr [rsp+38h+arg_20]
0x18000c8df  mov     qword ptr [rsp+38h+var_18], rax; int
0x18000c8e4  lea     rcx, OdmlSvcGetAvailablePackages
0x18000c8eb  call    ??$__invoke@A6AJPEAXKPEAIPEAPEAU__MIDL_odmlapi_0008@@@ZAEAPEAXAEAKAEAPEAIAEAPEAPEAU1@@wistd@@YAJA6AJPEAXKPEAIPEAPEAU__MIDL_odmlapi_0008@@@ZAEAPEAXAEAKAEAPEAIAEAPEAPEAU1@@Z; wistd::__invoke<long (&)(void *,ulong,uint *,__MIDL_odmlapi_0008 * *),void * &,ulong &,uint * &,__MIDL_odmlapi_0008 * * &>(long (&)(void *,ulong,uint *,__MIDL_odmlapi_0008 * *),void * &,ulong &,uint * &,__MIDL_odmlapi_0008 * * &)
0x18000c8f0  mov     ebx, eax
0x18000c8f2  test    eax, eax
0x18000c8f4  jns     short loc_18000C913
0x18000c8f6  mov     rcx, [rsp+38h]; this
0x18000c8fb  mov     r9d, eax; char *
0x18000c8fe  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c905  mov     edx, 5Eh ; '^'; void *
0x18000c90a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c90f  mov     eax, ebx
0x18000c911  jmp     short loc_18000C947
0x18000c913  xor     eax, eax
0x18000c915  jmp     short loc_18000C947
0x18000c917  mov     ebx, eax
0x18000c919  test    eax, eax
0x18000c91b  js      short loc_18000C928
0x18000c91d  jle     short loc_18000C928
0x18000c91f  movzx   ebx, ax
0x18000c922  or      ebx, 80070000h
0x18000c928  test    ebx, ebx
0x18000c92a  jns     short loc_18000C945
0x18000c92c  mov     rcx, [rsp+38h]; this
0x18000c931  mov     r9d, ebx; char *
0x18000c934  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c93b  mov     edx, 63h ; 'c'; void *
0x18000c940  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c945  mov     eax, ebx
0x18000c947  add     rsp, 30h
0x18000c94b  pop     rbx
0x18000c94c  retn
```
