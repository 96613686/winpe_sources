# Windows::Security::Isolation::FileDialogBroker::GetSaveExtension(ushort * *)

- ea: `0x14000c560`
- end: `0x14000c5ba`
- name: `?GetSaveExtension@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAPEAG@Z`
- size: `90`
- prototype: `int(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140007df4`
- `0x14000c560`
- `0x140014010`

## string_xrefs

- `0x14000c59a`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetSaveExtension(
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
    v5 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v4 + 104LL))(v4, a2);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4E1,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v5,
        v8);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4E4,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000c560  push    rbx; int
0x14000c562  sub     rsp, 20h
0x14000c566  mov     rbx, rdx
0x14000c569  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000c56d  mov     rax, [rcx]
0x14000c570  mov     rax, [rax+48h]
0x14000c574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c579  mov     r8, rax
0x14000c57c  mov     rcx, [rax]
0x14000c57f  mov     rax, [rcx+68h]
0x14000c583  mov     rdx, rbx
0x14000c586  mov     rcx, r8
0x14000c589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c58e  mov     rcx, [rsp+28h]; this
0x14000c593  test    eax, eax
0x14000c595  jns     short loc_14000C5AB
0x14000c597  mov     r9d, eax; char *
0x14000c59a  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000c5a1  mov     edx, 4E1h; void *
0x14000c5a6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000c5ab  xor     eax, eax
0x14000c5ad  jmp     short loc_14000C5B3
0x14000c5af  mov     eax, [rsp+28h+arg_0]
0x14000c5b3  add     rsp, 20h
0x14000c5b7  pop     rbx
0x14000c5b8  retn
```
