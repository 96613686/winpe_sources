# Windows::Security::Isolation::FileDialogBroker::GetSavePropertyStore(IPropertyStore * *,IPropertyDescriptionList * *)

- ea: `0x14000c5c0`
- end: `0x14000c629`
- name: `?GetSavePropertyStore@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAPEAUIPropertyStore@@PEAPEAUIPropertyDescriptionList@@@Z`
- size: `105`
- prototype: `int(Windows::Security::Isolation::FileDialogBroker *__hidden this, struct IPropertyStore **, struct IPropertyDescriptionList **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000c5c0`
- `0x140014010`

## string_xrefs

- `0x14000c604`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetSavePropertyStore(
        Windows::Security::Isolation::FileDialogBroker *this,
        struct IPropertyStore **a2,
        struct IPropertyDescriptionList **a3)
{
  char *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  const char *v8; // r9
  __int64 result; // rax
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v5 = (char *)this - 24;
  try
  {
    v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 72LL))(v5);
    v7 = (*(__int64 (__fastcall **)(__int64, struct IPropertyStore **, struct IPropertyDescriptionList **))(*(_QWORD *)v6 + 96LL))(
           v6,
           a2,
           a3);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4D9,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v7,
        v10);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4DC,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000c5c0  mov     [rsp+arg_8], rbx
0x14000c5c5  push    rdi; int
0x14000c5c6  sub     rsp, 20h
0x14000c5ca  mov     rbx, r8
0x14000c5cd  mov     rdi, rdx
0x14000c5d0  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000c5d4  mov     rax, [rcx]
0x14000c5d7  mov     rax, [rax+48h]
0x14000c5db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c5e0  mov     r9, rax
0x14000c5e3  mov     rcx, [rax]
0x14000c5e6  mov     rax, [rcx+60h]
0x14000c5ea  mov     r8, rbx
0x14000c5ed  mov     rdx, rdi
0x14000c5f0  mov     rcx, r9
0x14000c5f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c5f8  mov     rcx, [rsp+28h]; this
0x14000c5fd  test    eax, eax
0x14000c5ff  jns     short loc_14000C615
0x14000c601  mov     r9d, eax; char *
0x14000c604  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000c60b  mov     edx, 4D9h; void *
0x14000c610  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000c615  xor     eax, eax
0x14000c617  jmp     short loc_14000C61D
0x14000c619  mov     eax, [rsp+28h+arg_0]
0x14000c61d  mov     rbx, [rsp+28h+arg_8]
0x14000c622  add     rsp, 20h
0x14000c626  pop     rdi
0x14000c627  retn
```
