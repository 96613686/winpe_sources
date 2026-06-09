# Windows::Security::Isolation::FileDialogBroker::EnableControlsForHostedPickerProviderApp(void)

- ea: `0x14000a4f0`
- end: `0x14000a541`
- name: `?EnableControlsForHostedPickerProviderApp@FileDialogBroker@Isolation@Security@Windows@@UEAAJXZ`
- size: `81`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000a4f0`
- `0x140014010`

## string_xrefs

- `0x14000a522`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::EnableControlsForHostedPickerProviderApp(
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
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 32LL))(v2);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x499,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v3,
        v6);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x49C,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x14000a4f0  sub     rsp, 28h
0x14000a4f4  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000a4f8  mov     rax, [rcx]
0x14000a4fb  mov     rax, [rax+48h]
0x14000a4ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a504  mov     rdx, rax
0x14000a507  mov     rcx, [rax]
0x14000a50a  mov     rax, [rcx+20h]
0x14000a50e  mov     rcx, rdx
0x14000a511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a516  mov     rcx, [rsp+28h]; this
0x14000a51b  test    eax, eax
0x14000a51d  jns     short loc_14000A533
0x14000a51f  mov     r9d, eax; char *
0x14000a522  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000a529  mov     edx, 499h; void *
0x14000a52e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000a533  xor     eax, eax
0x14000a535  jmp     short loc_14000A53B
0x14000a537  mov     eax, [rsp+28h+arg_0]
0x14000a53b  add     rsp, 28h
0x14000a53f  retn
```
