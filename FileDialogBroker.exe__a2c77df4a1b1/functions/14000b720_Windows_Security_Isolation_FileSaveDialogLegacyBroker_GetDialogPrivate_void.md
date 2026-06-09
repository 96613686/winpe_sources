# Windows::Security::Isolation::FileSaveDialogLegacyBroker::GetDialogPrivate(void)

- ea: `0x14000b720`
- end: `0x14000b775`
- name: `?GetDialogPrivate@FileSaveDialogLegacyBroker@Isolation@Security@Windows@@EEBAPEAUIFileDialogPrivate@@XZ`
- size: `85`
- prototype: `struct IFileDialogPrivate *__fastcall(Windows::Security::Isolation::FileSaveDialogLegacyBroker *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400066d0`
- `0x140007df4`
- `0x140008ae4`
- `0x14000b720`

## string_xrefs

- `0x14000b73e`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
struct IFileDialogPrivate *__fastcall Windows::Security::Isolation::FileSaveDialogLegacyBroker::GetDialogPrivate(
        Windows::Security::Isolation::FileSaveDialogLegacyBroker *this)
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
      (void *)0x22C,
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
0x14000b720  push    rbx; int
0x14000b722  sub     rsp, 20h
0x14000b726  mov     rax, [rsp+28h]
0x14000b72b  add     rcx, 88h
0x14000b732  cmp     qword ptr [rcx], 0
0x14000b736  jnz     short loc_14000B753
0x14000b738  mov     r9d, 80004003h; char *
0x14000b73e  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000b745  mov     edx, 22Ch; void *
0x14000b74a  mov     rcx, rax; this
0x14000b74d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000b753  lea     rdx, [rsp+28h+arg_0]
0x14000b758  call    ??$query@UIFileDialogPrivate@@@?$com_ptr_t@UIFileSaveDialog@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIFileDialogPrivate@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IFileSaveDialog,wil::err_exception_policy>::query<IFileDialogPrivate>(void)
0x14000b75d  mov     rbx, [rsp+28h+arg_0]
0x14000b762  lea     rcx, [rsp+28h+arg_0]
0x14000b767  call    ??1?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(void)
0x14000b76c  mov     rax, rbx
0x14000b76f  add     rsp, 20h
0x14000b773  pop     rbx
0x14000b774  retn
```
