# Windows::Security::Isolation::FileDialogBroker::SetAppControlsModule(IAppControlsModule *)

- ea: `0x14000e2c0`
- end: `0x14000e31d`
- name: `?SetAppControlsModule@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAUIAppControlsModule@@@Z`
- size: `93`
- prototype: `int(Windows::Security::Isolation::FileDialogBroker *__hidden this, struct IAppControlsModule *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000e2c0`
- `0x140014010`

## string_xrefs

- `0x14000e2fd`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetAppControlsModule(
        Windows::Security::Isolation::FileDialogBroker *this,
        struct IAppControlsModule *a2)
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
    v5 = (*(__int64 (__fastcall **)(__int64, struct IAppControlsModule *))(*(_QWORD *)v4 + 160LL))(v4, a2);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x519,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v5,
        v8);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x51C,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000e2c0  push    rbx; int
0x14000e2c2  sub     rsp, 20h
0x14000e2c6  mov     rbx, rdx
0x14000e2c9  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000e2cd  mov     rax, [rcx]
0x14000e2d0  mov     rax, [rax+48h]
0x14000e2d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e2d9  mov     r8, rax
0x14000e2dc  mov     rcx, [rax]
0x14000e2df  mov     rax, [rcx+0A0h]
0x14000e2e6  mov     rdx, rbx
0x14000e2e9  mov     rcx, r8
0x14000e2ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e2f1  mov     rcx, [rsp+28h]; this
0x14000e2f6  test    eax, eax
0x14000e2f8  jns     short loc_14000E30E
0x14000e2fa  mov     r9d, eax; char *
0x14000e2fd  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000e304  mov     edx, 519h; void *
0x14000e309  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000e30e  xor     eax, eax
0x14000e310  jmp     short loc_14000E316
0x14000e312  mov     eax, [rsp+28h+arg_0]
0x14000e316  add     rsp, 20h
0x14000e31a  pop     rbx
0x14000e31b  retn
```
