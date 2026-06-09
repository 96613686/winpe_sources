# Windows::Security::Isolation::FileOpenDialogLegacyBroker::GetDialogPrivate(void)

- ea: `0x14000b660`
- end: `0x14000b6b5`
- name: `?GetDialogPrivate@FileOpenDialogLegacyBroker@Isolation@Security@Windows@@EEBAPEAUIFileDialogPrivate@@XZ`
- size: `85`
- prototype: `struct IFileDialogPrivate *__fastcall(Windows::Security::Isolation::FileOpenDialogLegacyBroker *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400066d0`
- `0x140007df4`
- `0x140008ae4`
- `0x14000b660`

## string_xrefs

- `0x14000b67e`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
struct IFileDialogPrivate *__fastcall Windows::Security::Isolation::FileOpenDialogLegacyBroker::GetDialogPrivate(
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
      (void *)0x198,
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
0x14000b660  push    rbx; int
0x14000b662  sub     rsp, 20h
0x14000b666  mov     rax, [rsp+28h]
0x14000b66b  add     rcx, 88h
0x14000b672  cmp     qword ptr [rcx], 0
0x14000b676  jnz     short loc_14000B693
0x14000b678  mov     r9d, 80004003h; char *
0x14000b67e  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000b685  mov     edx, 198h; void *
0x14000b68a  mov     rcx, rax; this
0x14000b68d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000b693  lea     rdx, [rsp+28h+arg_0]
0x14000b698  call    ??$query@UIFileDialogPrivate@@@?$com_ptr_t@UIFileSaveDialog@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIFileDialogPrivate@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IFileSaveDialog,wil::err_exception_policy>::query<IFileDialogPrivate>(void)
0x14000b69d  mov     rbx, [rsp+28h+arg_0]
0x14000b6a2  lea     rcx, [rsp+28h+arg_0]
0x14000b6a7  call    ??1?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(void)
0x14000b6ac  mov     rax, rbx
0x14000b6af  add     rsp, 20h
0x14000b6b3  pop     rbx
0x14000b6b4  retn
```
