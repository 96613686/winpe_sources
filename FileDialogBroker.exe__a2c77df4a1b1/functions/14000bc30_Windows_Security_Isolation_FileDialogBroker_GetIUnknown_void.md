# Windows::Security::Isolation::FileDialogBroker::GetIUnknown(void)

- ea: `0x14000bc30`
- end: `0x14000bc95`
- name: `?GetIUnknown@FileDialogBroker@Isolation@Security@Windows@@AEAAPEAUIUnknown@@XZ`
- size: `101`
- prototype: `struct IUnknown *__fastcall(__int64 (__fastcall ***this)(Windows::Security::Isolation::FileDialogBroker *, GUID *, __int64 *))`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140009bd0`
- `0x140012428`
- `0x1400124c7`

## callees

- `0x1400066d0`
- `0x140007df4`
- `0x14000bc30`
- `0x140014010`

## string_xrefs

- `0x14000bc62`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct IUnknown *__fastcall Windows::Security::Isolation::FileDialogBroker::GetIUnknown(
        __int64 (__fastcall ***this)(Windows::Security::Isolation::FileDialogBroker *, GUID *, __int64 *))
{
  __int64 (__fastcall **v1)(Windows::Security::Isolation::FileDialogBroker *, GUID *, __int64 *); // rax
  int v2; // eax
  __int64 v3; // rbx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  v1 = *this;
  v7 = 0;
  v2 = (*v1)((Windows::Security::Isolation::FileDialogBroker *)this, &GUID_00000000_0000_0000_c000_000000000046, &v7);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x264,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      (const char *)(unsigned int)v2,
      v5);
  v3 = v7;
  v7 = 0;
  wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(&v7);
  return (struct IUnknown *)v3;
}

```

## disassembly

```asm
0x14000bc30  push    rbx; int
0x14000bc32  sub     rsp, 20h
0x14000bc36  mov     rax, [rcx]
0x14000bc39  mov     [rsp+28h+arg_0], 0
0x14000bc42  lea     r8, [rsp+28h+arg_0]
0x14000bc47  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x14000bc4e  mov     rax, [rax]
0x14000bc51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bc56  mov     rcx, [rsp+28h]; this
0x14000bc5b  test    eax, eax
0x14000bc5d  jns     short loc_14000BC74
0x14000bc5f  mov     r9d, eax; char *
0x14000bc62  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000bc69  mov     edx, 264h; void *
0x14000bc6e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000bc74  mov     rbx, [rsp+28h+arg_0]
0x14000bc79  mov     [rsp+28h+arg_0], 0
0x14000bc82  lea     rcx, [rsp+28h+arg_0]
0x14000bc87  call    ??1?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(void)
0x14000bc8c  mov     rax, rbx
0x14000bc8f  add     rsp, 20h
0x14000bc93  pop     rbx
0x14000bc94  retn
```
