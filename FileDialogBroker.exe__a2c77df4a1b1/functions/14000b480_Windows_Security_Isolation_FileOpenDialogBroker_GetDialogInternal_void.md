# Windows::Security::Isolation::FileOpenDialogBroker::GetDialogInternal(void)

- ea: `0x14000b480`
- end: `0x14000b4d2`
- name: `?GetDialogInternal@FileOpenDialogBroker@Isolation@Security@Windows@@EEBAPEAUIFileDialogInternal@@XZ`
- size: `82`
- prototype: `struct IFileDialogInternal *__fastcall(Windows::Security::Isolation::FileOpenDialogBroker *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400066d0`
- `0x140007df4`
- `0x140008a8c`
- `0x14000b480`

## string_xrefs

- `0x14000b49b`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
struct IFileDialogInternal *__fastcall Windows::Security::Isolation::FileOpenDialogBroker::GetDialogInternal(
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
      (void *)0x6B,
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
0x14000b480  push    rbx; int
0x14000b482  sub     rsp, 20h
0x14000b486  mov     rax, [rsp+28h]
0x14000b48b  add     rcx, 78h ; 'x'
0x14000b48f  cmp     qword ptr [rcx], 0
0x14000b493  jnz     short loc_14000B4B0
0x14000b495  mov     r9d, 80004003h; char *
0x14000b49b  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000b4a2  mov     edx, 6Bh ; 'k'; void *
0x14000b4a7  mov     rcx, rax; this
0x14000b4aa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000b4b0  lea     rdx, [rsp+28h+arg_0]
0x14000b4b5  call    ??$query@UIFileDialogInternal@@@?$com_ptr_t@UIFileSaveDialog@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIFileDialogInternal@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IFileSaveDialog,wil::err_exception_policy>::query<IFileDialogInternal>(void)
0x14000b4ba  mov     rbx, [rsp+28h+arg_0]
0x14000b4bf  lea     rcx, [rsp+28h+arg_0]
0x14000b4c4  call    ??1?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(void)
0x14000b4c9  mov     rax, rbx
0x14000b4cc  add     rsp, 20h
0x14000b4d0  pop     rbx
0x14000b4d1  retn
```
