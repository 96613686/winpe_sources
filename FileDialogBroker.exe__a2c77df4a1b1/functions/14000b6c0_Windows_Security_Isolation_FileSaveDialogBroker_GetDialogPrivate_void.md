# Windows::Security::Isolation::FileSaveDialogBroker::GetDialogPrivate(void)

- ea: `0x14000b6c0`
- end: `0x14000b712`
- name: `?GetDialogPrivate@FileSaveDialogBroker@Isolation@Security@Windows@@EEBAPEAUIFileDialogPrivate@@XZ`
- size: `82`
- prototype: `struct IFileDialogPrivate *__fastcall(Windows::Security::Isolation::FileSaveDialogBroker *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400066d0`
- `0x140007df4`
- `0x140008ae4`
- `0x14000b6c0`

## string_xrefs

- `0x14000b6db`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
struct IFileDialogPrivate *__fastcall Windows::Security::Isolation::FileSaveDialogBroker::GetDialogPrivate(
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
      (void *)0x105,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      (const char *)0x80004003LL,
      v4);
  wil::com_ptr_t<IFileSaveDialog,wil::err_exception_policy>::query<IFileDialogPrivate>(
    (__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))v1,
    &v6);
  v2 = v6;
  wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(&v6);
  return (struct IFileDialogPrivate *)v2;
}

```

## disassembly

```asm
0x14000b6c0  push    rbx; int
0x14000b6c2  sub     rsp, 20h
0x14000b6c6  mov     rax, [rsp+28h]
0x14000b6cb  add     rcx, 78h ; 'x'
0x14000b6cf  cmp     qword ptr [rcx], 0
0x14000b6d3  jnz     short loc_14000B6F0
0x14000b6d5  mov     r9d, 80004003h; char *
0x14000b6db  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000b6e2  mov     edx, 105h; void *
0x14000b6e7  mov     rcx, rax; this
0x14000b6ea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000b6f0  lea     rdx, [rsp+28h+arg_0]
0x14000b6f5  call    ??$query@UIFileDialogPrivate@@@?$com_ptr_t@UIFileSaveDialog@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIFileDialogPrivate@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IFileSaveDialog,wil::err_exception_policy>::query<IFileDialogPrivate>(void)
0x14000b6fa  mov     rbx, [rsp+28h+arg_0]
0x14000b6ff  lea     rcx, [rsp+28h+arg_0]
0x14000b704  call    ??1?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(void)
0x14000b709  mov     rax, rbx
0x14000b70c  add     rsp, 20h
0x14000b710  pop     rbx
0x14000b711  retn
```
