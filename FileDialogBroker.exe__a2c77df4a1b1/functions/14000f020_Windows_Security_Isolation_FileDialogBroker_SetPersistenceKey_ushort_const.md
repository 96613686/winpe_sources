# Windows::Security::Isolation::FileDialogBroker::SetPersistenceKey(ushort const *)

- ea: `0x14000f020`
- end: `0x14000f07a`
- name: `?SetPersistenceKey@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEBG@Z`
- size: `90`
- prototype: `int(Windows::Security::Isolation::FileDialogBroker *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000f020`
- `0x140014010`

## string_xrefs

- `0x14000f05a`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetPersistenceKey(
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
    v5 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v4 + 56LL))(v4, a2);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4B1,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v5,
        v8);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4B4,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000f020  push    rbx; int
0x14000f022  sub     rsp, 20h
0x14000f026  mov     rbx, rdx
0x14000f029  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000f02d  mov     rax, [rcx]
0x14000f030  mov     rax, [rax+48h]
0x14000f034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f039  mov     r8, rax
0x14000f03c  mov     rcx, [rax]
0x14000f03f  mov     rax, [rcx+38h]
0x14000f043  mov     rdx, rbx
0x14000f046  mov     rcx, r8
0x14000f049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f04e  mov     rcx, [rsp+28h]; this
0x14000f053  test    eax, eax
0x14000f055  jns     short loc_14000F06B
0x14000f057  mov     r9d, eax; char *
0x14000f05a  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000f061  mov     edx, 4B1h; void *
0x14000f066  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000f06b  xor     eax, eax
0x14000f06d  jmp     short loc_14000F073
0x14000f06f  mov     eax, [rsp+28h+arg_0]
0x14000f073  add     rsp, 20h
0x14000f077  pop     rbx
0x14000f078  retn
```
