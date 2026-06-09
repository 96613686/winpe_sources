# Windows::Security::Isolation::FileDialogBroker::GetPersistRegkey(ushort * *)

- ea: `0x14000c0d0`
- end: `0x14000c12a`
- name: `?GetPersistRegkey@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAPEAG@Z`
- size: `90`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000c0d0`
- `0x140014010`

## string_xrefs

- `0x14000c10a`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetPersistRegkey(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned __int16 **a2)
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
    v5 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v4 + 88LL))(v4, a2);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4D1,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v5,
        v8);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4D4,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000c0d0  push    rbx; int
0x14000c0d2  sub     rsp, 20h
0x14000c0d6  mov     rbx, rdx
0x14000c0d9  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000c0dd  mov     rax, [rcx]
0x14000c0e0  mov     rax, [rax+48h]
0x14000c0e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c0e9  mov     r8, rax
0x14000c0ec  mov     rcx, [rax]
0x14000c0ef  mov     rax, [rcx+58h]
0x14000c0f3  mov     rdx, rbx
0x14000c0f6  mov     rcx, r8
0x14000c0f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c0fe  mov     rcx, [rsp+28h]; this
0x14000c103  test    eax, eax
0x14000c105  jns     short loc_14000C11B
0x14000c107  mov     r9d, eax; char *
0x14000c10a  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000c111  mov     edx, 4D1h; void *
0x14000c116  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000c11b  xor     eax, eax
0x14000c11d  jmp     short loc_14000C123
0x14000c11f  mov     eax, [rsp+28h+arg_0]
0x14000c123  add     rsp, 20h
0x14000c127  pop     rbx
0x14000c128  retn
```
