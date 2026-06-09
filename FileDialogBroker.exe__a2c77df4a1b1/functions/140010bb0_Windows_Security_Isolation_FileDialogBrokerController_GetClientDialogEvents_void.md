# Windows::Security::Isolation::FileDialogBrokerController::GetClientDialogEvents(void)

- ea: `0x140010bb0`
- end: `0x140010be0`
- name: `?GetClientDialogEvents@FileDialogBrokerController@Isolation@Security@Windows@@AEBAPEAUIFileDialogEvents@@XZ`
- size: `48`
- prototype: `struct IFileDialogEvents *__fastcall(Windows::Security::Isolation::FileDialogBrokerController *__hidden this)`
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
- `0x140010bb0`

## string_xrefs

- `0x140010bc8`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbrokercontroller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct IFileDialogEvents *__fastcall Windows::Security::Isolation::FileDialogBrokerController::GetClientDialogEvents(
        Windows::Security::Isolation::FileDialogBrokerController *this)
{
  struct IFileDialogEvents *result; // rax
  int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  result = (struct IFileDialogEvents *)*((_QWORD *)this + 5);
  if ( !result )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbrokercontroller.cpp",
      (const char *)0x80004003LL,
      v2);
  return result;
}

```

## disassembly

```asm
0x140010bb0  sub     rsp, 28h
0x140010bb4  mov     rax, [rcx+28h]
0x140010bb8  mov     r10, [rsp+28h]
0x140010bbd  test    rax, rax
0x140010bc0  jnz     short loc_140010BDB
0x140010bc2  mov     r9d, 80004003h; char *
0x140010bc8  lea     r8, aOnecoreuapDsSe_3; "onecoreuap\\ds\\security\\isolation\\br"...
0x140010bcf  lea     edx, [rax+46h]; void *
0x140010bd2  mov     rcx, r10; this
0x140010bd5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140010bdb  add     rsp, 28h
0x140010bdf  retn
```
