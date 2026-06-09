# Windows::Security::Isolation::FileOpenDialogBroker::GetDialog(void)

- ea: `0x14000ad40`
- end: `0x14000ad70`
- name: `?GetDialog@FileOpenDialogBroker@Isolation@Security@Windows@@EEBAPEAUIFileDialog@@XZ`
- size: `48`
- prototype: `struct IFileDialog *__fastcall(Windows::Security::Isolation::FileOpenDialogBroker *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000ad40`

## string_xrefs

- `0x14000ad58`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
struct IFileDialog *__fastcall Windows::Security::Isolation::FileOpenDialogBroker::GetDialog(
        Windows::Security::Isolation::FileOpenDialogBroker *this)
{
  struct IFileDialog *result; // rax
  int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  result = (struct IFileDialog *)*((_QWORD *)this + 15);
  if ( !result )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      (const char *)0x80004003LL,
      v2);
  return result;
}

```

## disassembly

```asm
0x14000ad40  sub     rsp, 28h
0x14000ad44  mov     rax, [rcx+78h]
0x14000ad48  mov     r10, [rsp+28h]
0x14000ad4d  test    rax, rax
0x14000ad50  jnz     short loc_14000AD6B
0x14000ad52  mov     r9d, 80004003h; char *
0x14000ad58  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000ad5f  lea     edx, [rax+64h]; void *
0x14000ad62  mov     rcx, r10; this
0x14000ad65  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000ad6b  add     rsp, 28h
0x14000ad6f  retn
```
