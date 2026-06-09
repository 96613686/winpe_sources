# Windows::Security::Isolation::FileDialogBroker::HandleTab(void)

- ea: `0x14000c960`
- end: `0x14000c9b4`
- name: `?HandleTab@FileDialogBroker@Isolation@Security@Windows@@UEAAJXZ`
- size: `84`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000c960`
- `0x140014010`

## string_xrefs

- `0x14000c995`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::HandleTab(
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
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 248LL))(v2);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x571,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v3,
        v6);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x574,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x14000c960  sub     rsp, 28h
0x14000c964  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000c968  mov     rax, [rcx]
0x14000c96b  mov     rax, [rax+48h]
0x14000c96f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c974  mov     rdx, rax
0x14000c977  mov     rcx, [rax]
0x14000c97a  mov     rax, [rcx+0F8h]
0x14000c981  mov     rcx, rdx
0x14000c984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c989  mov     rcx, [rsp+28h]; this
0x14000c98e  test    eax, eax
0x14000c990  jns     short loc_14000C9A6
0x14000c992  mov     r9d, eax; char *
0x14000c995  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000c99c  mov     edx, 571h; void *
0x14000c9a1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000c9a6  xor     eax, eax
0x14000c9a8  jmp     short loc_14000C9AE
0x14000c9aa  mov     eax, [rsp+28h+arg_0]
0x14000c9ae  add     rsp, 28h
0x14000c9b2  retn
```
