# Windows::Security::Isolation::FileOpenDialogLegacyBroker::GetDialogCustomize(void)

- ea: `0x14000aea0`
- end: `0x14000aef5`
- name: `?GetDialogCustomize@FileOpenDialogLegacyBroker@Isolation@Security@Windows@@EEBAPEAUIFileDialogCustomize@@XZ`
- size: `85`
- prototype: `struct IFileDialogCustomize *__fastcall(Windows::Security::Isolation::FileOpenDialogLegacyBroker *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400066d0`
- `0x140007df4`
- `0x140008a34`
- `0x14000aea0`

## string_xrefs

- `0x14000aebe`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
struct IFileDialogCustomize *__fastcall Windows::Security::Isolation::FileOpenDialogLegacyBroker::GetDialogCustomize(
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
      (void *)0x1A1,
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
0x14000aea0  push    rbx; int
0x14000aea2  sub     rsp, 20h
0x14000aea6  mov     rax, [rsp+28h]
0x14000aeab  add     rcx, 88h
0x14000aeb2  cmp     qword ptr [rcx], 0
0x14000aeb6  jnz     short loc_14000AED3
0x14000aeb8  mov     r9d, 80004003h; char *
0x14000aebe  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000aec5  mov     edx, 1A1h; void *
0x14000aeca  mov     rcx, rax; this
0x14000aecd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000aed3  lea     rdx, [rsp+28h+arg_0]
0x14000aed8  call    ??$query@UIFileDialogCustomize@@@?$com_ptr_t@UIFileSaveDialog@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIFileDialogCustomize@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IFileSaveDialog,wil::err_exception_policy>::query<IFileDialogCustomize>(void)
0x14000aedd  mov     rbx, [rsp+28h+arg_0]
0x14000aee2  lea     rcx, [rsp+28h+arg_0]
0x14000aee7  call    ??1?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(void)
0x14000aeec  mov     rax, rbx
0x14000aeef  add     rsp, 20h
0x14000aef3  pop     rbx
0x14000aef4  retn
```
