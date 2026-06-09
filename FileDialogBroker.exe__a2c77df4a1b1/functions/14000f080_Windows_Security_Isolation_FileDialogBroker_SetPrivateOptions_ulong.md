# Windows::Security::Isolation::FileDialogBroker::SetPrivateOptions(ulong)

- ea: `0x14000f080`
- end: `0x14000f0d8`
- name: `?SetPrivateOptions@FileDialogBroker@Isolation@Security@Windows@@UEAAJK@Z`
- size: `88`
- prototype: `int(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000f080`
- `0x140014010`

## string_xrefs

- `0x14000f0b8`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetPrivateOptions(
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
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 48LL))(v4, a2);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4A9,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v5,
        v8);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4AC,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000f080  push    rbx; int
0x14000f082  sub     rsp, 20h
0x14000f086  mov     ebx, edx
0x14000f088  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000f08c  mov     rax, [rcx]
0x14000f08f  mov     rax, [rax+48h]
0x14000f093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f098  mov     r8, rax
0x14000f09b  mov     rcx, [rax]
0x14000f09e  mov     rax, [rcx+30h]
0x14000f0a2  mov     edx, ebx
0x14000f0a4  mov     rcx, r8
0x14000f0a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f0ac  mov     rcx, [rsp+28h]; this
0x14000f0b1  test    eax, eax
0x14000f0b3  jns     short loc_14000F0C9
0x14000f0b5  mov     r9d, eax; char *
0x14000f0b8  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000f0bf  mov     edx, 4A9h; void *
0x14000f0c4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000f0c9  xor     eax, eax
0x14000f0cb  jmp     short loc_14000F0D1
0x14000f0cd  mov     eax, [rsp+28h+arg_0]
0x14000f0d1  add     rsp, 20h
0x14000f0d5  pop     rbx
0x14000f0d6  retn
```
