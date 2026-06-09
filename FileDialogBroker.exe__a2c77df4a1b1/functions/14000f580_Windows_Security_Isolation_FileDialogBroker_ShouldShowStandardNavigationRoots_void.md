# Windows::Security::Isolation::FileDialogBroker::ShouldShowStandardNavigationRoots(void)

- ea: `0x14000f580`
- end: `0x14000f5d4`
- name: `?ShouldShowStandardNavigationRoots@FileDialogBroker@Isolation@Security@Windows@@UEAAJXZ`
- size: `84`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000f580`
- `0x140014010`

## string_xrefs

- `0x14000f5b5`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::ShouldShowStandardNavigationRoots(
        Windows::Security::Isolation::FileDialogBroker *this)
{
  char *v1; // rcx
  __int64 v2; // rax
  int v3; // eax
  const char *v4; // r9
  __int64 result; // rax
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (char *)this - 24;
  try
  {
    v2 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v1 + 72LL))(v1);
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 176LL))(v2);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x529,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v3,
        v6);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x52C,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x14000f580  sub     rsp, 28h
0x14000f584  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000f588  mov     rax, [rcx]
0x14000f58b  mov     rax, [rax+48h]
0x14000f58f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f594  mov     rdx, rax
0x14000f597  mov     rcx, [rax]
0x14000f59a  mov     rax, [rcx+0B0h]
0x14000f5a1  mov     rcx, rdx
0x14000f5a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f5a9  mov     rcx, [rsp+28h]; this
0x14000f5ae  test    eax, eax
0x14000f5b0  jns     short loc_14000F5C6
0x14000f5b2  mov     r9d, eax; char *
0x14000f5b5  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000f5bc  mov     edx, 529h; void *
0x14000f5c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000f5c6  xor     eax, eax
0x14000f5c8  jmp     short loc_14000F5CE
0x14000f5ca  mov     eax, [rsp+28h+arg_0]
0x14000f5ce  add     rsp, 28h
0x14000f5d2  retn
```
