# Windows::Security::Isolation::FileDialogBroker::GetPrivateOptions(ulong *)

- ea: `0x14000c130`
- end: `0x14000c18a`
- name: `?GetPrivateOptions@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAK@Z`
- size: `90`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *this, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000c130`
- `0x140014010`

## string_xrefs

- `0x14000c16a`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetPrivateOptions(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int *a2)
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
    v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 40LL))(v4, a2);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4A1,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v5,
        v8);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4A4,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000c130  push    rbx; int
0x14000c132  sub     rsp, 20h
0x14000c136  mov     rbx, rdx
0x14000c139  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000c13d  mov     rax, [rcx]
0x14000c140  mov     rax, [rax+48h]
0x14000c144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c149  mov     r8, rax
0x14000c14c  mov     rcx, [rax]
0x14000c14f  mov     rax, [rcx+28h]
0x14000c153  mov     rdx, rbx
0x14000c156  mov     rcx, r8
0x14000c159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c15e  mov     rcx, [rsp+28h]; this
0x14000c163  test    eax, eax
0x14000c165  jns     short loc_14000C17B
0x14000c167  mov     r9d, eax; char *
0x14000c16a  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000c171  mov     edx, 4A1h; void *
0x14000c176  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000c17b  xor     eax, eax
0x14000c17d  jmp     short loc_14000C183
0x14000c17f  mov     eax, [rsp+28h+arg_0]
0x14000c183  add     rsp, 20h
0x14000c187  pop     rbx
0x14000c188  retn
```
