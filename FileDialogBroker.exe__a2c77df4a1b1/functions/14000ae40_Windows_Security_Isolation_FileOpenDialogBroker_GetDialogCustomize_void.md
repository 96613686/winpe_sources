# Windows::Security::Isolation::FileOpenDialogBroker::GetDialogCustomize(void)

- ea: `0x14000ae40`
- end: `0x14000ae92`
- name: `?GetDialogCustomize@FileOpenDialogBroker@Isolation@Security@Windows@@EEBAPEAUIFileDialogCustomize@@XZ`
- size: `82`
- prototype: `struct IFileDialogCustomize *__fastcall(Windows::Security::Isolation::FileOpenDialogBroker *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400066d0`
- `0x140007df4`
- `0x140008a34`
- `0x14000ae40`

## string_xrefs

- `0x14000ae5b`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
struct IFileDialogCustomize *__fastcall Windows::Security::Isolation::FileOpenDialogBroker::GetDialogCustomize(
        Windows::Security::Isolation::FileOpenDialogBroker *this)
{
  char *v1; // rcx
  __int64 v2; // rbx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  v1 = (char *)this + 120;
  if ( !*(_QWORD *)v1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      (const char *)0x80004003LL,
      v4);
  wil::com_ptr_t<IFileSaveDialog,wil::err_exception_policy>::query<IFileDialogCustomize>(
    (__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))v1,
    &v6);
  v2 = v6;
  wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(&v6);
  return (struct IFileDialogCustomize *)v2;
}

```

## disassembly

```asm
0x14000ae40  push    rbx; int
0x14000ae42  sub     rsp, 20h
0x14000ae46  mov     rax, [rsp+28h]
0x14000ae4b  add     rcx, 78h ; 'x'
0x14000ae4f  cmp     qword ptr [rcx], 0
0x14000ae53  jnz     short loc_14000AE70
0x14000ae55  mov     r9d, 80004003h; char *
0x14000ae5b  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000ae62  mov     edx, 7Dh ; '}'; void *
0x14000ae67  mov     rcx, rax; this
0x14000ae6a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000ae70  lea     rdx, [rsp+28h+arg_0]
0x14000ae75  call    ??$query@UIFileDialogCustomize@@@?$com_ptr_t@UIFileSaveDialog@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIFileDialogCustomize@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IFileSaveDialog,wil::err_exception_policy>::query<IFileDialogCustomize>(void)
0x14000ae7a  mov     rbx, [rsp+28h+arg_0]
0x14000ae7f  lea     rcx, [rsp+28h+arg_0]
0x14000ae84  call    ??1?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(void)
0x14000ae89  mov     rax, rbx
0x14000ae8c  add     rsp, 20h
0x14000ae90  pop     rbx
0x14000ae91  retn
```
