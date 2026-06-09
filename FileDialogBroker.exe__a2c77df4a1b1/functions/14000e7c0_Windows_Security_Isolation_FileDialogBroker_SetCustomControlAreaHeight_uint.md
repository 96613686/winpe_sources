# Windows::Security::Isolation::FileDialogBroker::SetCustomControlAreaHeight(uint)

- ea: `0x14000e7c0`
- end: `0x14000e81b`
- name: `?SetCustomControlAreaHeight@FileDialogBroker@Isolation@Security@Windows@@UEAAJI@Z`
- size: `91`
- prototype: `int(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000e7c0`
- `0x140014010`

## string_xrefs

- `0x14000e7fb`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetCustomControlAreaHeight(
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
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 144LL))(v4, a2);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x509,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v5,
        v8);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x50C,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000e7c0  push    rbx; int
0x14000e7c2  sub     rsp, 20h
0x14000e7c6  mov     ebx, edx
0x14000e7c8  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000e7cc  mov     rax, [rcx]
0x14000e7cf  mov     rax, [rax+48h]
0x14000e7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e7d8  mov     r8, rax
0x14000e7db  mov     rcx, [rax]
0x14000e7de  mov     rax, [rcx+90h]
0x14000e7e5  mov     edx, ebx
0x14000e7e7  mov     rcx, r8
0x14000e7ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e7ef  mov     rcx, [rsp+28h]; this
0x14000e7f4  test    eax, eax
0x14000e7f6  jns     short loc_14000E80C
0x14000e7f8  mov     r9d, eax; char *
0x14000e7fb  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000e802  mov     edx, 509h; void *
0x14000e807  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000e80c  xor     eax, eax
0x14000e80e  jmp     short loc_14000E814
0x14000e810  mov     eax, [rsp+28h+arg_0]
0x14000e814  add     rsp, 20h
0x14000e818  pop     rbx
0x14000e819  retn
```
