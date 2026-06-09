# Windows::Security::Isolation::FileSaveDialogBroker::GetDialogCustomize(void)

- ea: `0x14000af00`
- end: `0x14000af52`
- name: `?GetDialogCustomize@FileSaveDialogBroker@Isolation@Security@Windows@@EEBAPEAUIFileDialogCustomize@@XZ`
- size: `82`
- prototype: `struct IFileDialogCustomize *__fastcall(Windows::Security::Isolation::FileSaveDialogBroker *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400066d0`
- `0x140007df4`
- `0x140008a34`
- `0x14000af00`

## string_xrefs

- `0x14000af1b`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
struct IFileDialogCustomize *__fastcall Windows::Security::Isolation::FileSaveDialogBroker::GetDialogCustomize(
        Windows::Security::Isolation::FileSaveDialogBroker *this)
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
      (void *)0x10E,
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
0x14000af00  push    rbx; int
0x14000af02  sub     rsp, 20h
0x14000af06  mov     rax, [rsp+28h]
0x14000af0b  add     rcx, 78h ; 'x'
0x14000af0f  cmp     qword ptr [rcx], 0
0x14000af13  jnz     short loc_14000AF30
0x14000af15  mov     r9d, 80004003h; char *
0x14000af1b  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000af22  mov     edx, 10Eh; void *
0x14000af27  mov     rcx, rax; this
0x14000af2a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000af30  lea     rdx, [rsp+28h+arg_0]
0x14000af35  call    ??$query@UIFileDialogCustomize@@@?$com_ptr_t@UIFileSaveDialog@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIFileDialogCustomize@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IFileSaveDialog,wil::err_exception_policy>::query<IFileDialogCustomize>(void)
0x14000af3a  mov     rbx, [rsp+28h+arg_0]
0x14000af3f  lea     rcx, [rsp+28h+arg_0]
0x14000af44  call    ??1?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(void)
0x14000af49  mov     rax, rbx
0x14000af4c  add     rsp, 20h
0x14000af50  pop     rbx
0x14000af51  retn
```
