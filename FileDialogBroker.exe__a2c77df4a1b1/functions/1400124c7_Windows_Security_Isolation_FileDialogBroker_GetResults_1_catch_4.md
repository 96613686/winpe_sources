# _Windows::Security::Isolation::FileDialogBroker::GetResults_::_1_::catch$4

- ea: `0x1400124c7`
- end: `0x140012521`
- name: `_Windows::Security::Isolation::FileDialogBroker::GetResults_::_1_::catch$4`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x14000bc30`
- `0x14000bc9c`
- `0x1400124c7`

## string_xrefs

- `0x1400124fe`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetResults_::_1_::catch_4(__int64 a1, __int64 a2)
{
  struct IUnknown *IUnknown; // rax
  __int64 v4; // rdx
  int ImpersonationTokenForClientOfObject_nothrow; // eax
  int v7; // [rsp+20h] [rbp-8h]

  IUnknown = Windows::Security::Isolation::FileDialogBroker::GetIUnknown((__int64 (__fastcall ***)(Windows::Security::Isolation::FileDialogBroker *, GUID *, __int64 *))(*(_QWORD *)(a2 + 128) - 32LL));
  ImpersonationTokenForClientOfObject_nothrow = wil::GetImpersonationTokenForClientOfObject_nothrow(
                                                  (__int64)IUnknown,
                                                  v4,
                                                  (void **)(a2 + 144));
  if ( ImpersonationTokenForClientOfObject_nothrow < 0 )
    wil::details::in1diag3::Throw_Hr(
      *(wil::details::in1diag3 **)(a2 + 120),
      (void *)0x58F,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      (const char *)(unsigned int)ImpersonationTokenForClientOfObject_nothrow,
      v7);
  return 0;
}

```

## disassembly

```asm
0x1400124c7  mov     [rsp+arg_8], rdx
0x1400124cc  push    rbp; int
0x1400124cd  sub     rsp, 20h
0x1400124d1  mov     rbp, rdx
0x1400124d4  mov     rcx, [rbp+80h]
0x1400124db  add     rcx, 0FFFFFFFFFFFFFFE0h; this
0x1400124df  call    ?GetIUnknown@FileDialogBroker@Isolation@Security@Windows@@AEAAPEAUIUnknown@@XZ; Windows::Security::Isolation::FileDialogBroker::GetIUnknown(void)
0x1400124e4  lea     r8, [rbp+90h]
0x1400124eb  mov     rcx, rax
0x1400124ee  call    ?GetImpersonationTokenForClientOfObject_nothrow@wil@@YAJPEAUIUnknown@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@@Z; wil::GetImpersonationTokenForClientOfObject_nothrow(IUnknown *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x1400124f3  mov     rcx, [rbp+78h]; this
0x1400124f7  test    eax, eax
0x1400124f9  jns     short loc_140012510
0x1400124fb  mov     r9d, eax; char *
0x1400124fe  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x140012505  mov     edx, 58Fh; void *
0x14001250a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140012510  mov     rax, 0
0x14001251a  add     rsp, 20h
0x14001251e  pop     rbp
0x14001251f  retn
```
