# Windows::Security::Isolation::FileSaveDialogBroker::GetSaveDialog(void)

- ea: `0x14000c4c0`
- end: `0x14000c4f2`
- name: `?GetSaveDialog@FileSaveDialogBroker@Isolation@Security@Windows@@EEBAPEAUIFileSaveDialog@@XZ`
- size: `50`
- prototype: `struct IFileSaveDialog *__fastcall(Windows::Security::Isolation::FileSaveDialogBroker *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000c4c0`

## string_xrefs

- `0x14000c4d8`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
struct IFileSaveDialog *__fastcall Windows::Security::Isolation::FileSaveDialogBroker::GetSaveDialog(
        Windows::Security::Isolation::FileSaveDialogBroker *this)
{
  struct IFileSaveDialog *result; // rax
  int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  result = (struct IFileSaveDialog *)*((_QWORD *)this + 15);
  if ( !result )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEE,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      (const char *)0x80004003LL,
      v2);
  return result;
}

```

## disassembly

```asm
0x14000c4c0  sub     rsp, 28h
0x14000c4c4  mov     rax, [rcx+78h]
0x14000c4c8  mov     r10, [rsp+28h]
0x14000c4cd  test    rax, rax
0x14000c4d0  jnz     short loc_14000C4ED
0x14000c4d2  mov     r9d, 80004003h; char *
0x14000c4d8  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000c4df  mov     edx, 0EEh; void *
0x14000c4e4  mov     rcx, r10; this
0x14000c4e7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000c4ed  add     rsp, 28h
0x14000c4f1  retn
```
