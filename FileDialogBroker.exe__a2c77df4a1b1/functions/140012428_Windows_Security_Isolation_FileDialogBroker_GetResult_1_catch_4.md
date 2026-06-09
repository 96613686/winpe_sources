# _Windows::Security::Isolation::FileDialogBroker::GetResult_::_1_::catch$4

- ea: `0x140012428`
- end: `0x140012482`
- name: `_Windows::Security::Isolation::FileDialogBroker::GetResult_::_1_::catch$4`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000bc30`
- `0x14000bc9c`
- `0x140012428`

## string_xrefs

- `0x14001245f`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetResult_::_1_::catch_4(__int64 a1, __int64 a2)
{
  struct IUnknown *IUnknown; // rax
  __int64 v4; // rdx
  int ImpersonationTokenForClientOfObject_nothrow; // eax
  int v7; // [rsp+20h] [rbp-8h]

  IUnknown = Windows::Security::Isolation::FileDialogBroker::GetIUnknown((__int64 (__fastcall ***)(Windows::Security::Isolation::FileDialogBroker *, GUID *, __int64 *))(*(_QWORD *)(a2 + 128) - 8LL));
  ImpersonationTokenForClientOfObject_nothrow = wil::GetImpersonationTokenForClientOfObject_nothrow(
                                                  (__int64)IUnknown,
                                                  v4,
                                                  (void **)(a2 + 144));
  if ( ImpersonationTokenForClientOfObject_nothrow < 0 )
    wil::details::in1diag3::Throw_Hr(
      *(wil::details::in1diag3 **)(a2 + 120),
      (void *)0x333,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      (const char *)(unsigned int)ImpersonationTokenForClientOfObject_nothrow,
      v7);
  return 0;
}

```

## disassembly

```asm
0x140012428  mov     [rsp+arg_8], rdx
0x14001242d  push    rbp; int
0x14001242e  sub     rsp, 20h
0x140012432  mov     rbp, rdx
0x140012435  mov     rcx, [rbp+80h]
0x14001243c  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x140012440  call    ?GetIUnknown@FileDialogBroker@Isolation@Security@Windows@@AEAAPEAUIUnknown@@XZ; Windows::Security::Isolation::FileDialogBroker::GetIUnknown(void)
0x140012445  lea     r8, [rbp+90h]
0x14001244c  mov     rcx, rax
0x14001244f  call    ?GetImpersonationTokenForClientOfObject_nothrow@wil@@YAJPEAUIUnknown@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@@Z; wil::GetImpersonationTokenForClientOfObject_nothrow(IUnknown *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x140012454  mov     rcx, [rbp+78h]; this
0x140012458  test    eax, eax
0x14001245a  jns     short loc_140012471
0x14001245c  mov     r9d, eax; char *
0x14001245f  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x140012466  mov     edx, 333h; void *
0x14001246b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140012471  mov     rax, 0
0x14001247b  add     rsp, 20h
0x14001247f  pop     rbp
0x140012480  retn
```
