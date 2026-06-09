# Windows::Security::Isolation::FileSaveDialogLegacyBroker::GetSaveDialog(void)

- ea: `0x14000c500`
- end: `0x14000c555`
- name: `?GetSaveDialog@FileSaveDialogLegacyBroker@Isolation@Security@Windows@@EEBAPEAUIFileSaveDialog@@XZ`
- size: `85`
- prototype: `struct IFileSaveDialog *(Windows::Security::Isolation::FileSaveDialogLegacyBroker *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400066d0`
- `0x140007df4`
- `0x140008b94`
- `0x14000c500`

## string_xrefs

- `0x14000c51e`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
struct IFileSaveDialog *__fastcall Windows::Security::Isolation::FileSaveDialogLegacyBroker::GetSaveDialog(
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
      (void *)0x213,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      (const char *)0x80004003LL,
      v4);
  wil::com_ptr_t<IFileDialog,wil::err_exception_policy>::query<IFileSaveDialog>(
    (__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))v1,
    &v6);
  v2 = v6;
  wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(&v6);
  return (struct IFileSaveDialog *)v2;
}

```

## disassembly

```asm
0x14000c500  push    rbx; int
0x14000c502  sub     rsp, 20h
0x14000c506  mov     rax, [rsp+28h]
0x14000c50b  add     rcx, 88h
0x14000c512  cmp     qword ptr [rcx], 0
0x14000c516  jnz     short loc_14000C533
0x14000c518  mov     r9d, 80004003h; char *
0x14000c51e  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000c525  mov     edx, 213h; void *
0x14000c52a  mov     rcx, rax; this
0x14000c52d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000c533  lea     rdx, [rsp+28h+arg_0]
0x14000c538  call    ??$query@UIFileSaveDialog@@@?$com_ptr_t@UIFileDialog@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIFileSaveDialog@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IFileDialog,wil::err_exception_policy>::query<IFileSaveDialog>(void)
0x14000c53d  mov     rbx, [rsp+28h+arg_0]
0x14000c542  lea     rcx, [rsp+28h+arg_0]
0x14000c547  call    ??1?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(void)
0x14000c54c  mov     rax, rbx
0x14000c54f  add     rsp, 20h
0x14000c553  pop     rbx
0x14000c554  retn
```
