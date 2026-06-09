# Windows::Security::Isolation::FileDialogBroker::HasPlaces(void)

- ea: `0x14000c9c0`
- end: `0x14000ca11`
- name: `?HasPlaces@FileDialogBroker@Isolation@Security@Windows@@UEAAJXZ`
- size: `81`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000c9c0`
- `0x140014010`

## string_xrefs

- `0x14000c9f2`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::HasPlaces(
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
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 64LL))(v2);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4B9,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v3,
        v6);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4BC,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x14000c9c0  sub     rsp, 28h
0x14000c9c4  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000c9c8  mov     rax, [rcx]
0x14000c9cb  mov     rax, [rax+48h]
0x14000c9cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c9d4  mov     rdx, rax
0x14000c9d7  mov     rcx, [rax]
0x14000c9da  mov     rax, [rcx+40h]
0x14000c9de  mov     rcx, rdx
0x14000c9e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c9e6  mov     rcx, [rsp+28h]; this
0x14000c9eb  test    eax, eax
0x14000c9ed  jns     short loc_14000CA03
0x14000c9ef  mov     r9d, eax; char *
0x14000c9f2  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000c9f9  mov     edx, 4B9h; void *
0x14000c9fe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000ca03  xor     eax, eax
0x14000ca05  jmp     short loc_14000CA0B
0x14000ca07  mov     eax, [rsp+28h+arg_0]
0x14000ca0b  add     rsp, 28h
0x14000ca0f  retn
```
