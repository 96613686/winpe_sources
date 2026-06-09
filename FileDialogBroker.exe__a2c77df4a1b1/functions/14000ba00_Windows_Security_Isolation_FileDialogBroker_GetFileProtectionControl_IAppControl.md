# Windows::Security::Isolation::FileDialogBroker::GetFileProtectionControl(IAppControl * *)

- ea: `0x14000ba00`
- end: `0x14000ba5d`
- name: `?GetFileProtectionControl@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAPEAUIAppControl@@@Z`
- size: `93`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *this, struct IAppControl **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000ba00`
- `0x140014010`

## string_xrefs

- `0x14000ba3d`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetFileProtectionControl(
        Windows::Security::Isolation::FileDialogBroker *this,
        struct IAppControl **a2)
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
    v5 = (*(__int64 (__fastcall **)(__int64, struct IAppControl **))(*(_QWORD *)v4 + 128LL))(v4, a2);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4F9,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v5,
        v8);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4FC,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000ba00  push    rbx; int
0x14000ba02  sub     rsp, 20h
0x14000ba06  mov     rbx, rdx
0x14000ba09  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000ba0d  mov     rax, [rcx]
0x14000ba10  mov     rax, [rax+48h]
0x14000ba14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ba19  mov     r8, rax
0x14000ba1c  mov     rcx, [rax]
0x14000ba1f  mov     rax, [rcx+80h]
0x14000ba26  mov     rdx, rbx
0x14000ba29  mov     rcx, r8
0x14000ba2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ba31  mov     rcx, [rsp+28h]; this
0x14000ba36  test    eax, eax
0x14000ba38  jns     short loc_14000BA4E
0x14000ba3a  mov     r9d, eax; char *
0x14000ba3d  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000ba44  mov     edx, 4F9h; void *
0x14000ba49  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000ba4e  xor     eax, eax
0x14000ba50  jmp     short loc_14000BA56
0x14000ba52  mov     eax, [rsp+28h+arg_0]
0x14000ba56  add     rsp, 20h
0x14000ba5a  pop     rbx
0x14000ba5b  retn
```
