# Windows::Security::Isolation::FileDialogBroker::ShouldShowFileProtectionControl(int *)

- ea: `0x14000f510`
- end: `0x14000f56d`
- name: `?ShouldShowFileProtectionControl@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAH@Z`
- size: `93`
- prototype: `int(Windows::Security::Isolation::FileDialogBroker *__hidden this, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000f510`
- `0x140014010`

## string_xrefs

- `0x14000f54d`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::ShouldShowFileProtectionControl(
        Windows::Security::Isolation::FileDialogBroker *this,
        int *a2)
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
    v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v4 + 192LL))(v4, a2);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x539,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v5,
        v8);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x53C,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000f510  push    rbx; int
0x14000f512  sub     rsp, 20h
0x14000f516  mov     rbx, rdx
0x14000f519  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14000f51d  mov     rax, [rcx]
0x14000f520  mov     rax, [rax+48h]
0x14000f524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f529  mov     r8, rax
0x14000f52c  mov     rcx, [rax]
0x14000f52f  mov     rax, [rcx+0C0h]
0x14000f536  mov     rdx, rbx
0x14000f539  mov     rcx, r8
0x14000f53c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f541  mov     rcx, [rsp+28h]; this
0x14000f546  test    eax, eax
0x14000f548  jns     short loc_14000F55E
0x14000f54a  mov     r9d, eax; char *
0x14000f54d  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000f554  mov     edx, 539h; void *
0x14000f559  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000f55e  xor     eax, eax
0x14000f560  jmp     short loc_14000F566
0x14000f562  mov     eax, [rsp+28h+arg_0]
0x14000f566  add     rsp, 20h
0x14000f56a  pop     rbx
0x14000f56b  retn
```
