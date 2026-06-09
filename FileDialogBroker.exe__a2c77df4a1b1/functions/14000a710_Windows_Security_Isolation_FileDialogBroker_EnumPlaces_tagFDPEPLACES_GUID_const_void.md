# Windows::Security::Isolation::FileDialogBroker::EnumPlaces(tagFDPEPLACES,_GUID const &,void * *)

- ea: `0x14000a710`
- end: `0x14000a787`
- name: `?EnumPlaces@FileDialogBroker@Isolation@Security@Windows@@UEAAJW4tagFDPEPLACES@@AEBU_GUID@@PEAPEAX@Z`
- size: `119`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000a710`
- `0x140014010`

## string_xrefs

- `0x14000a75d`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::EnumPlaces(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  const char *v10; // r9
  __int64 result; // rax
  int v12; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v7 = a1 - 24;
  try
  {
    v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 72LL))(v7);
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v8 + 72LL))(v8, a2, a3, a4);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4C1,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v9,
        v12);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4C4,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x14000a710  mov     [rsp+arg_8], rbx
0x14000a715  mov     [rsp+arg_10], rsi
0x14000a71a  push    rdi
0x14000a71b  sub     rsp, 30h
0x14000a71f  mov     rbx, r9
0x14000a722  mov     rdi, r8
0x14000a725  mov     esi, edx
0x14000a727  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000a72b  mov     rax, [rcx]
0x14000a72e  mov     rax, [rax+48h]
0x14000a732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a737  mov     r10, rax
0x14000a73a  mov     rcx, [rax]
0x14000a73d  mov     rax, [rcx+48h]
0x14000a741  mov     r9, rbx
0x14000a744  mov     r8, rdi
0x14000a747  mov     edx, esi
0x14000a749  mov     rcx, r10
0x14000a74c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a751  mov     rcx, [rsp+38h]; this
0x14000a756  test    eax, eax
0x14000a758  jns     short loc_14000A76E
0x14000a75a  mov     r9d, eax; char *
0x14000a75d  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000a764  mov     edx, 4C1h; void *
0x14000a769  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000a76e  xor     eax, eax
0x14000a770  jmp     short loc_14000A776
0x14000a772  mov     eax, [rsp+38h+arg_0]
0x14000a776  mov     rbx, [rsp+38h+arg_8]
0x14000a77b  mov     rsi, [rsp+38h+arg_10]
0x14000a780  add     rsp, 30h
0x14000a784  pop     rdi
0x14000a785  retn
```
