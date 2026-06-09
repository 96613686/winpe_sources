# Windows::Security::Isolation::FileSaveDialogLegacyBroker::GetDialogInternal(void)

- ea: `0x14000b5a0`
- end: `0x14000b5f5`
- name: `?GetDialogInternal@FileSaveDialogLegacyBroker@Isolation@Security@Windows@@EEBAPEAUIFileDialogInternal@@XZ`
- size: `85`
- prototype: `struct IFileDialogInternal *__fastcall(Windows::Security::Isolation::FileSaveDialogLegacyBroker *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400066d0`
- `0x140007df4`
- `0x140008a8c`
- `0x14000b5a0`

## string_xrefs

- `0x14000b5be`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
struct IFileDialogInternal *__fastcall Windows::Security::Isolation::FileSaveDialogLegacyBroker::GetDialogInternal(
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
      (void *)0x223,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      (const char *)0x80004003LL,
      v4);
  wil::com_ptr_t<IFileSaveDialog,wil::err_exception_policy>::query<IFileDialogInternal>(
    (__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))v1,
    &v6);
  v2 = v6;
  wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(&v6);
  return (struct IFileDialogInternal *)v2;
}

```

## disassembly

```asm
0x14000b5a0  push    rbx; int
0x14000b5a2  sub     rsp, 20h
0x14000b5a6  mov     rax, [rsp+28h]
0x14000b5ab  add     rcx, 88h
0x14000b5b2  cmp     qword ptr [rcx], 0
0x14000b5b6  jnz     short loc_14000B5D3
0x14000b5b8  mov     r9d, 80004003h; char *
0x14000b5be  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000b5c5  mov     edx, 223h; void *
0x14000b5ca  mov     rcx, rax; this
0x14000b5cd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000b5d3  lea     rdx, [rsp+28h+arg_0]
0x14000b5d8  call    ??$query@UIFileDialogInternal@@@?$com_ptr_t@UIFileSaveDialog@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIFileDialogInternal@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IFileSaveDialog,wil::err_exception_policy>::query<IFileDialogInternal>(void)
0x14000b5dd  mov     rbx, [rsp+28h+arg_0]
0x14000b5e2  lea     rcx, [rsp+28h+arg_0]
0x14000b5e7  call    ??1?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(void)
0x14000b5ec  mov     rax, rbx
0x14000b5ef  add     rsp, 20h
0x14000b5f3  pop     rbx
0x14000b5f4  retn
```
