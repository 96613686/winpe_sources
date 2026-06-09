# Windows::Security::Isolation::FileOpenDialogLegacyBroker::GetDialog(void)

- ea: `0x14000ad80`
- end: `0x14000adb5`
- name: `?GetDialog@FileOpenDialogLegacyBroker@Isolation@Security@Windows@@EEBAPEAUIFileDialog@@XZ`
- size: `53`
- prototype: `struct IFileDialog *__fastcall(Windows::Security::Isolation::FileOpenDialogLegacyBroker *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000ad80`

## string_xrefs

- `0x14000ad9b`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
struct IFileDialog *__fastcall Windows::Security::Isolation::FileOpenDialogLegacyBroker::GetDialog(
        Windows::Security::Isolation::FileOpenDialogLegacyBroker *this)
{
  struct IFileDialog *result; // rax
  int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  result = (struct IFileDialog *)*((_QWORD *)this + 17);
  if ( !result )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x188,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      (const char *)0x80004003LL,
      v2);
  return result;
}

```

## disassembly

```asm
0x14000ad80  sub     rsp, 28h
0x14000ad84  mov     rax, [rcx+88h]
0x14000ad8b  mov     r10, [rsp+28h]
0x14000ad90  test    rax, rax
0x14000ad93  jnz     short loc_14000ADB0
0x14000ad95  mov     r9d, 80004003h; char *
0x14000ad9b  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000ada2  mov     edx, 188h; void *
0x14000ada7  mov     rcx, r10; this
0x14000adaa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000adb0  add     rsp, 28h
0x14000adb4  retn
```
