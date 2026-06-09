# Windows::Security::Isolation::FileOpenDialogLegacyBroker::GetOpenDialog(void)

- ea: `0x14000bf60`
- end: `0x14000bfb5`
- name: `?GetOpenDialog@FileOpenDialogLegacyBroker@Isolation@Security@Windows@@EEBAPEAUIFileOpenDialog@@XZ`
- size: `85`
- prototype: `struct IFileOpenDialog *__fastcall(Windows::Security::Isolation::FileOpenDialogLegacyBroker *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400066d0`
- `0x140007df4`
- `0x140008b3c`
- `0x14000bf60`

## string_xrefs

- `0x14000bf7e`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
struct IFileOpenDialog *__fastcall Windows::Security::Isolation::FileOpenDialogLegacyBroker::GetOpenDialog(
        Windows::Security::Isolation::FileOpenDialogLegacyBroker *this)
{
  char *v1; // rcx
  __int64 v2; // rbx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  v1 = (char *)this + 136;
  if ( !*(_QWORD *)v1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x178,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      (const char *)0x80004003LL,
      v4);
  wil::com_ptr_t<IFileDialog,wil::err_exception_policy>::query<IFileOpenDialog>(
    (__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))v1,
    &v6);
  v2 = v6;
  wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(&v6);
  return (struct IFileOpenDialog *)v2;
}

```

## disassembly

```asm
0x14000bf60  push    rbx; int
0x14000bf62  sub     rsp, 20h
0x14000bf66  mov     rax, [rsp+28h]
0x14000bf6b  add     rcx, 88h
0x14000bf72  cmp     qword ptr [rcx], 0
0x14000bf76  jnz     short loc_14000BF93
0x14000bf78  mov     r9d, 80004003h; char *
0x14000bf7e  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000bf85  mov     edx, 178h; void *
0x14000bf8a  mov     rcx, rax; this
0x14000bf8d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000bf93  lea     rdx, [rsp+28h+arg_0]
0x14000bf98  call    ??$query@UIFileOpenDialog@@@?$com_ptr_t@UIFileDialog@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIFileOpenDialog@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IFileDialog,wil::err_exception_policy>::query<IFileOpenDialog>(void)
0x14000bf9d  mov     rbx, [rsp+28h+arg_0]
0x14000bfa2  lea     rcx, [rsp+28h+arg_0]
0x14000bfa7  call    ??1?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(void)
0x14000bfac  mov     rax, rbx
0x14000bfaf  add     rsp, 20h
0x14000bfb3  pop     rbx
0x14000bfb4  retn
```
