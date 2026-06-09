# Windows::Security::Isolation::FileDialogBroker::GetNavigationRoot(_GUID const &,void * *)

- ea: `0x14000be20`
- end: `0x14000be8c`
- name: `?GetNavigationRoot@FileDialogBroker@Isolation@Security@Windows@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `108`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000be20`
- `0x140014010`

## string_xrefs

- `0x14000be67`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetNavigationRoot(
        Windows::Security::Isolation::FileDialogBroker *this,
        const struct _GUID *a2,
        void **a3)
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
    v7 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, void **))(*(_QWORD *)v6 + 184LL))(v6, a2, a3);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x531,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v7,
        v10);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x534,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000be20  mov     [rsp+arg_8], rbx
0x14000be25  push    rdi; int
0x14000be26  sub     rsp, 20h
0x14000be2a  mov     rbx, r8
0x14000be2d  mov     rdi, rdx
0x14000be30  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000be34  mov     rax, [rcx]
0x14000be37  mov     rax, [rax+48h]
0x14000be3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000be40  mov     r9, rax
0x14000be43  mov     rcx, [rax]
0x14000be46  mov     rax, [rcx+0B8h]
0x14000be4d  mov     r8, rbx
0x14000be50  mov     rdx, rdi
0x14000be53  mov     rcx, r9
0x14000be56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000be5b  mov     rcx, [rsp+28h]; this
0x14000be60  test    eax, eax
0x14000be62  jns     short loc_14000BE78
0x14000be64  mov     r9d, eax; char *
0x14000be67  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000be6e  mov     edx, 531h; void *
0x14000be73  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000be78  xor     eax, eax
0x14000be7a  jmp     short loc_14000BE80
0x14000be7c  mov     eax, [rsp+28h+arg_0]
0x14000be80  mov     rbx, [rsp+28h+arg_8]
0x14000be85  add     rsp, 20h
0x14000be89  pop     rdi
0x14000be8a  retn
```
