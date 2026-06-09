# Windows::Security::Isolation::FileDialogBroker::MoveFocusFromBrowser(int)

- ea: `0x14000ccf0`
- end: `0x14000cd4b`
- name: `?MoveFocusFromBrowser@FileDialogBroker@Isolation@Security@Windows@@UEAAJH@Z`
- size: `91`
- prototype: `int(Windows::Security::Isolation::FileDialogBroker *__hidden this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000ccf0`
- `0x140014010`

## string_xrefs

- `0x14000cd2b`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::MoveFocusFromBrowser(
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
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 216LL))(v4, a2);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x551,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v5,
        v8);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x554,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000ccf0  push    rbx; int
0x14000ccf2  sub     rsp, 20h
0x14000ccf6  mov     ebx, edx
0x14000ccf8  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000ccfc  mov     rax, [rcx]
0x14000ccff  mov     rax, [rax+48h]
0x14000cd03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cd08  mov     r8, rax
0x14000cd0b  mov     rcx, [rax]
0x14000cd0e  mov     rax, [rcx+0D8h]
0x14000cd15  mov     edx, ebx
0x14000cd17  mov     rcx, r8
0x14000cd1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cd1f  mov     rcx, [rsp+28h]; this
0x14000cd24  test    eax, eax
0x14000cd26  jns     short loc_14000CD3C
0x14000cd28  mov     r9d, eax; char *
0x14000cd2b  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000cd32  mov     edx, 551h; void *
0x14000cd37  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000cd3c  xor     eax, eax
0x14000cd3e  jmp     short loc_14000CD44
0x14000cd40  mov     eax, [rsp+28h+arg_0]
0x14000cd44  add     rsp, 20h
0x14000cd48  pop     rbx
0x14000cd49  retn
```
