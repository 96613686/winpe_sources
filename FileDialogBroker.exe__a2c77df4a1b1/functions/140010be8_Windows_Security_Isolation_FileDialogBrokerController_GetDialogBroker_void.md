# Windows::Security::Isolation::FileDialogBrokerController::GetDialogBroker(void)

- ea: `0x140010be8`
- end: `0x140010c18`
- name: `?GetDialogBroker@FileDialogBrokerController@Isolation@Security@Windows@@AEBAPEAUIFileDialog@@XZ`
- size: `48`
- prototype: `struct IFileDialog *__fastcall(Windows::Security::Isolation::FileDialogBrokerController *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140010c20`
- `0x140010ca0`
- `0x140010d20`
- `0x140010da0`
- `0x140010e30`
- `0x140010eb0`
- `0x140010f40`

## callees

- `0x140007df4`
- `0x140010be8`

## string_xrefs

- `0x140010c00`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbrokercontroller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct IFileDialog *__fastcall Windows::Security::Isolation::FileDialogBrokerController::GetDialogBroker(
        Windows::Security::Isolation::FileDialogBrokerController *this)
{
  struct IFileDialog *result; // rax
  int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  result = (struct IFileDialog *)*((_QWORD *)this + 4);
  if ( !result )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbrokercontroller.cpp",
      (const char *)0x80004003LL,
      v2);
  return result;
}

```

## disassembly

```asm
0x140010be8  sub     rsp, 28h
0x140010bec  mov     rax, [rcx+20h]
0x140010bf0  mov     r10, [rsp+28h]
0x140010bf5  test    rax, rax
0x140010bf8  jnz     short loc_140010C13
0x140010bfa  mov     r9d, 80004003h; char *
0x140010c00  lea     r8, aOnecoreuapDsSe_3; "onecoreuap\\ds\\security\\isolation\\br"...
0x140010c07  lea     edx, [rax+3Fh]; void *
0x140010c0a  mov     rcx, r10; this
0x140010c0d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140010c13  add     rsp, 28h
0x140010c17  retn
```
