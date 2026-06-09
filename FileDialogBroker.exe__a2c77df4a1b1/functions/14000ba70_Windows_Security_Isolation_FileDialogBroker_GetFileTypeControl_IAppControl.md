# Windows::Security::Isolation::FileDialogBroker::GetFileTypeControl(IAppControl * *)

- ea: `0x14000ba70`
- end: `0x14000baca`
- name: `?GetFileTypeControl@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAPEAUIAppControl@@@Z`
- size: `90`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *this, struct IAppControl **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000ba70`
- `0x140014010`

## string_xrefs

- `0x14000baaa`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetFileTypeControl(
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
    v5 = (*(__int64 (__fastcall **)(__int64, struct IAppControl **))(*(_QWORD *)v4 + 112LL))(v4, a2);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4E9,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v5,
        v8);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4EC,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000ba70  push    rbx; int
0x14000ba72  sub     rsp, 20h
0x14000ba76  mov     rbx, rdx
0x14000ba79  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000ba7d  mov     rax, [rcx]
0x14000ba80  mov     rax, [rax+48h]
0x14000ba84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ba89  mov     r8, rax
0x14000ba8c  mov     rcx, [rax]
0x14000ba8f  mov     rax, [rcx+70h]
0x14000ba93  mov     rdx, rbx
0x14000ba96  mov     rcx, r8
0x14000ba99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ba9e  mov     rcx, [rsp+28h]; this
0x14000baa3  test    eax, eax
0x14000baa5  jns     short loc_14000BABB
0x14000baa7  mov     r9d, eax; char *
0x14000baaa  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000bab1  mov     edx, 4E9h; void *
0x14000bab6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000babb  xor     eax, eax
0x14000babd  jmp     short loc_14000BAC3
0x14000babf  mov     eax, [rsp+28h+arg_0]
0x14000bac3  add     rsp, 20h
0x14000bac7  pop     rbx
0x14000bac8  retn
```
