# Windows::Security::Isolation::FileDialogBroker::EnableOkButton(int)

- ea: `0x14000a550`
- end: `0x14000a5ab`
- name: `?EnableOkButton@FileDialogBroker@Isolation@Security@Windows@@UEAAJH@Z`
- size: `91`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000a550`
- `0x140014010`

## string_xrefs

- `0x14000a58b`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::EnableOkButton(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2)
{
  char *v3; // rcx
  __int64 v4; // rax
  int v5; // eax
  const char *v6; // r9
  __int64 result; // rax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = (char *)this - 24;
  try
  {
    v4 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 72LL))(v3);
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 224LL))(v4, a2);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x559,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v5,
        v8);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x55C,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000a550  push    rbx; int
0x14000a552  sub     rsp, 20h
0x14000a556  mov     ebx, edx
0x14000a558  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000a55c  mov     rax, [rcx]
0x14000a55f  mov     rax, [rax+48h]
0x14000a563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a568  mov     r8, rax
0x14000a56b  mov     rcx, [rax]
0x14000a56e  mov     rax, [rcx+0E0h]
0x14000a575  mov     edx, ebx
0x14000a577  mov     rcx, r8
0x14000a57a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a57f  mov     rcx, [rsp+28h]; this
0x14000a584  test    eax, eax
0x14000a586  jns     short loc_14000A59C
0x14000a588  mov     r9d, eax; char *
0x14000a58b  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000a592  mov     edx, 559h; void *
0x14000a597  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000a59c  xor     eax, eax
0x14000a59e  jmp     short loc_14000A5A4
0x14000a5a0  mov     eax, [rsp+28h+arg_0]
0x14000a5a4  add     rsp, 20h
0x14000a5a8  pop     rbx
0x14000a5a9  retn
```
