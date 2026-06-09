# Windows::Security::Isolation::FileDialogBroker::SetSaveDialogEditBoxTextAndFileType(int,ushort const *)

- ea: `0x14000f220`
- end: `0x14000f28a`
- name: `?SetSaveDialogEditBoxTextAndFileType@FileDialogBroker@Isolation@Security@Windows@@UEAAJHPEBG@Z`
- size: `106`
- prototype: `int(Windows::Security::Isolation::FileDialogBroker *__hidden this, int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000f220`
- `0x140014010`

## string_xrefs

- `0x14000f265`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetSaveDialogEditBoxTextAndFileType(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2,
        const unsigned __int16 *a3)
{
  char *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  const char *v8; // r9
  __int64 result; // rax
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v5 = (char *)this - 24;
  try
  {
    v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v5 + 72LL))(v5);
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *))(*(_QWORD *)v6 + 208LL))(v6, a2, a3);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x549,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v7,
        v10);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x54C,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000f220  mov     [rsp+arg_8], rbx
0x14000f225  push    rdi; int
0x14000f226  sub     rsp, 20h
0x14000f22a  mov     rbx, r8
0x14000f22d  mov     edi, edx
0x14000f22f  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000f233  mov     rax, [rcx]
0x14000f236  mov     rax, [rax+48h]
0x14000f23a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f23f  mov     r9, rax
0x14000f242  mov     rcx, [rax]
0x14000f245  mov     rax, [rcx+0D0h]
0x14000f24c  mov     r8, rbx
0x14000f24f  mov     edx, edi
0x14000f251  mov     rcx, r9
0x14000f254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f259  mov     rcx, [rsp+28h]; this
0x14000f25e  test    eax, eax
0x14000f260  jns     short loc_14000F276
0x14000f262  mov     r9d, eax; char *
0x14000f265  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000f26c  mov     edx, 549h; void *
0x14000f271  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000f276  xor     eax, eax
0x14000f278  jmp     short loc_14000F27E
0x14000f27a  mov     eax, [rsp+28h+arg_0]
0x14000f27e  mov     rbx, [rsp+28h+arg_8]
0x14000f283  add     rsp, 20h
0x14000f287  pop     rdi
0x14000f288  retn
```
