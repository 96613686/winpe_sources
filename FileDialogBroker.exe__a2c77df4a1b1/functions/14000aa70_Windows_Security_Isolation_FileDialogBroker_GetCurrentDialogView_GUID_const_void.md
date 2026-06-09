# Windows::Security::Isolation::FileDialogBroker::GetCurrentDialogView(_GUID const &,void * *)

- ea: `0x14000aa70`
- end: `0x14000aadc`
- name: `?GetCurrentDialogView@FileDialogBroker@Isolation@Security@Windows@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `108`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000aa70`
- `0x140014010`

## string_xrefs

- `0x14000aab7`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetCurrentDialogView(
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
    v7 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, void **))(*(_QWORD *)v6 + 200LL))(v6, a2, a3);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x541,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v7,
        v10);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x544,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000aa70  mov     [rsp+arg_8], rbx
0x14000aa75  push    rdi; int
0x14000aa76  sub     rsp, 20h
0x14000aa7a  mov     rbx, r8
0x14000aa7d  mov     rdi, rdx
0x14000aa80  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000aa84  mov     rax, [rcx]
0x14000aa87  mov     rax, [rax+48h]
0x14000aa8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa90  mov     r9, rax
0x14000aa93  mov     rcx, [rax]
0x14000aa96  mov     rax, [rcx+0C8h]
0x14000aa9d  mov     r8, rbx
0x14000aaa0  mov     rdx, rdi
0x14000aaa3  mov     rcx, r9
0x14000aaa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aaab  mov     rcx, [rsp+28h]; this
0x14000aab0  test    eax, eax
0x14000aab2  jns     short loc_14000AAC8
0x14000aab4  mov     r9d, eax; char *
0x14000aab7  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000aabe  mov     edx, 541h; void *
0x14000aac3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000aac8  xor     eax, eax
0x14000aaca  jmp     short loc_14000AAD0
0x14000aacc  mov     eax, [rsp+28h+arg_0]
0x14000aad0  mov     rbx, [rsp+28h+arg_8]
0x14000aad5  add     rsp, 20h
0x14000aad9  pop     rdi
0x14000aada  retn
```
