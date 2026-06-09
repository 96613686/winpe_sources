# Windows::Security::Isolation::FileSaveDialogBroker::GetDialog(void)

- ea: `0x14000adc0`
- end: `0x14000adf2`
- name: `?GetDialog@FileSaveDialogBroker@Isolation@Security@Windows@@EEBAPEAUIFileDialog@@XZ`
- size: `50`
- prototype: `struct IFileDialog *__fastcall(Windows::Security::Isolation::FileSaveDialogBroker *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000adc0`

## string_xrefs

- `0x14000add8`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
struct IFileDialog *__fastcall Windows::Security::Isolation::FileSaveDialogBroker::GetDialog(
        Windows::Security::Isolation::FileSaveDialogBroker *this)
{
  struct IFileDialog *result; // rax
  int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  result = (struct IFileDialog *)*((_QWORD *)this + 15);
  if ( !result )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF5,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      (const char *)0x80004003LL,
      v2);
  return result;
}

```

## disassembly

```asm
0x14000adc0  sub     rsp, 28h
0x14000adc4  mov     rax, [rcx+78h]
0x14000adc8  mov     r10, [rsp+28h]
0x14000adcd  test    rax, rax
0x14000add0  jnz     short loc_14000ADED
0x14000add2  mov     r9d, 80004003h; char *
0x14000add8  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000addf  mov     edx, 0F5h; void *
0x14000ade4  mov     rcx, r10; this
0x14000ade7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000aded  add     rsp, 28h
0x14000adf1  retn
```
