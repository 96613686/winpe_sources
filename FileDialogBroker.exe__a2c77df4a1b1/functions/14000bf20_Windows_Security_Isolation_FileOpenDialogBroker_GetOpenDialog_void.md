# Windows::Security::Isolation::FileOpenDialogBroker::GetOpenDialog(void)

- ea: `0x14000bf20`
- end: `0x14000bf50`
- name: `?GetOpenDialog@FileOpenDialogBroker@Isolation@Security@Windows@@EEBAPEAUIFileOpenDialog@@XZ`
- size: `48`
- prototype: `struct IFileOpenDialog *__fastcall(Windows::Security::Isolation::FileOpenDialogBroker *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000bf20`

## string_xrefs

- `0x14000bf38`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
struct IFileOpenDialog *__fastcall Windows::Security::Isolation::FileOpenDialogBroker::GetOpenDialog(
        Windows::Security::Isolation::FileOpenDialogBroker *this)
{
  struct IFileOpenDialog *result; // rax
  int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  result = (struct IFileOpenDialog *)*((_QWORD *)this + 15);
  if ( !result )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      (const char *)0x80004003LL,
      v2);
  return result;
}

```

## disassembly

```asm
0x14000bf20  sub     rsp, 28h
0x14000bf24  mov     rax, [rcx+78h]
0x14000bf28  mov     r10, [rsp+28h]
0x14000bf2d  test    rax, rax
0x14000bf30  jnz     short loc_14000BF4B
0x14000bf32  mov     r9d, 80004003h; char *
0x14000bf38  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000bf3f  lea     edx, [rax+56h]; void *
0x14000bf42  mov     rcx, r10; this
0x14000bf45  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000bf4b  add     rsp, 28h
0x14000bf4f  retn
```
