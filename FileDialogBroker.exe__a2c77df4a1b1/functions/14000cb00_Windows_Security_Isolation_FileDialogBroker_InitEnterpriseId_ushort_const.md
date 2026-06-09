# Windows::Security::Isolation::FileDialogBroker::InitEnterpriseId(ushort const *)

- ea: `0x14000cb00`
- end: `0x14000cb5d`
- name: `?InitEnterpriseId@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEBG@Z`
- size: `93`
- prototype: `int(Windows::Security::Isolation::FileDialogBroker *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000cb00`
- `0x140014010`

## string_xrefs

- `0x14000cb3d`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::InitEnterpriseId(
        Windows::Security::Isolation::FileDialogBroker *this,
        const unsigned __int16 *a2)
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
    v5 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v4 + 232LL))(v4, a2);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x561,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v5,
        v8);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x564,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000cb00  push    rbx; int
0x14000cb02  sub     rsp, 20h
0x14000cb06  mov     rbx, rdx
0x14000cb09  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000cb0d  mov     rax, [rcx]
0x14000cb10  mov     rax, [rax+48h]
0x14000cb14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cb19  mov     r8, rax
0x14000cb1c  mov     rcx, [rax]
0x14000cb1f  mov     rax, [rcx+0E8h]
0x14000cb26  mov     rdx, rbx
0x14000cb29  mov     rcx, r8
0x14000cb2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cb31  mov     rcx, [rsp+28h]; this
0x14000cb36  test    eax, eax
0x14000cb38  jns     short loc_14000CB4E
0x14000cb3a  mov     r9d, eax; char *
0x14000cb3d  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000cb44  mov     edx, 561h; void *
0x14000cb49  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000cb4e  xor     eax, eax
0x14000cb50  jmp     short loc_14000CB56
0x14000cb52  mov     eax, [rsp+28h+arg_0]
0x14000cb56  add     rsp, 20h
0x14000cb5a  pop     rbx
0x14000cb5b  retn
```
