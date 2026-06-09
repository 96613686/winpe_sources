# Windows::Security::Isolation::FileDialogBroker::EnumControls(IEnumAppControl * *)

- ea: `0x14000a6b0`
- end: `0x14000a70a`
- name: `?EnumControls@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAPEAUIEnumAppControl@@@Z`
- size: `90`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *this, struct IEnumAppControl **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000a6b0`
- `0x140014010`

## string_xrefs

- `0x14000a6ea`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::EnumControls(
        Windows::Security::Isolation::FileDialogBroker *this,
        struct IEnumAppControl **a2)
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
    v5 = (*(__int64 (__fastcall **)(__int64, struct IEnumAppControl **))(*(_QWORD *)v4 + 80LL))(v4, a2);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4C9,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v5,
        v8);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4CC,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000a6b0  push    rbx; int
0x14000a6b2  sub     rsp, 20h
0x14000a6b6  mov     rbx, rdx
0x14000a6b9  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000a6bd  mov     rax, [rcx]
0x14000a6c0  mov     rax, [rax+48h]
0x14000a6c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a6c9  mov     r8, rax
0x14000a6cc  mov     rcx, [rax]
0x14000a6cf  mov     rax, [rcx+50h]
0x14000a6d3  mov     rdx, rbx
0x14000a6d6  mov     rcx, r8
0x14000a6d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a6de  mov     rcx, [rsp+28h]; this
0x14000a6e3  test    eax, eax
0x14000a6e5  jns     short loc_14000A6FB
0x14000a6e7  mov     r9d, eax; char *
0x14000a6ea  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000a6f1  mov     edx, 4C9h; void *
0x14000a6f6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000a6fb  xor     eax, eax
0x14000a6fd  jmp     short loc_14000A703
0x14000a6ff  mov     eax, [rsp+28h+arg_0]
0x14000a703  add     rsp, 20h
0x14000a707  pop     rbx
0x14000a708  retn
```
