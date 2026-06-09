# Windows::Security::Isolation::FileDialogBroker::GetDialogState(ulong,ulong *)

- ea: `0x14000b780`
- end: `0x14000b7ea`
- name: `?GetDialogState@FileDialogBroker@Isolation@Security@Windows@@UEAAJKPEAK@Z`
- size: `106`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *this, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000b780`
- `0x140014010`

## string_xrefs

- `0x14000b7c5`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetDialogState(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2,
        unsigned int *a3)
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
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v6 + 152LL))(v6, a2, a3);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x511,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v7,
        v10);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x514,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000b780  mov     [rsp+arg_8], rbx
0x14000b785  push    rdi; int
0x14000b786  sub     rsp, 20h
0x14000b78a  mov     rbx, r8
0x14000b78d  mov     edi, edx
0x14000b78f  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000b793  mov     rax, [rcx]
0x14000b796  mov     rax, [rax+48h]
0x14000b79a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b79f  mov     r9, rax
0x14000b7a2  mov     rcx, [rax]
0x14000b7a5  mov     rax, [rcx+98h]
0x14000b7ac  mov     r8, rbx
0x14000b7af  mov     edx, edi
0x14000b7b1  mov     rcx, r9
0x14000b7b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b7b9  mov     rcx, [rsp+28h]; this
0x14000b7be  test    eax, eax
0x14000b7c0  jns     short loc_14000B7D6
0x14000b7c2  mov     r9d, eax; char *
0x14000b7c5  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000b7cc  mov     edx, 511h; void *
0x14000b7d1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000b7d6  xor     eax, eax
0x14000b7d8  jmp     short loc_14000B7DE
0x14000b7da  mov     eax, [rsp+28h+arg_0]
0x14000b7de  mov     rbx, [rsp+28h+arg_8]
0x14000b7e3  add     rsp, 20h
0x14000b7e7  pop     rdi
0x14000b7e8  retn
```
