# Windows::Security::Isolation::FileDialogBroker::SetFilter(IShellItemFilter *)

- ea: `0x14000ece0`
- end: `0x14000ed50`
- name: `?SetFilter@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAUIShellItemFilter@@@Z`
- size: `112`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, struct IShellItemFilter *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000ed60`
- `0x14000ed70`
- `0x14000ed80`

## callees

- `0x140009194`
- `0x14000ece0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000ecf0`: `FileDialogBroker::SetFilter`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetFilter(
        Windows::Security::Isolation::FileDialogBroker *this,
        struct IShellItemFilter *a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v8, (__int64)"FileDialogBroker::SetFilter");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 1) + 56LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, struct IShellItemFilter *))(*(_QWORD *)v4 + 208LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x381,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000ece0  mov     [rsp+arg_8], rbx
0x14000ece5  push    rdi
0x14000ece6  sub     rsp, 70h
0x14000ecea  mov     rbx, rdx
0x14000eced  mov     rdi, rcx
0x14000ecf0  lea     rdx, aFiledialogbrok_25; "FileDialogBroker::SetFilter"
0x14000ecf7  lea     rcx, [rsp+78h+var_58]
0x14000ecfc  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000ed01  nop
0x14000ed02  lea     rcx, [rdi-8]
0x14000ed06  mov     rax, [rcx]
0x14000ed09  mov     rax, [rax+38h]
0x14000ed0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ed12  mov     r8, rax
0x14000ed15  mov     rcx, [rax]
0x14000ed18  mov     rax, [rcx+0D0h]
0x14000ed1f  mov     rdx, rbx
0x14000ed22  mov     rcx, r8
0x14000ed25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ed2a  mov     ebx, eax
0x14000ed2c  lea     rcx, [rsp+78h+var_58]; this
0x14000ed31  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000ed36  mov     eax, ebx
0x14000ed38  jmp     short loc_14000ED41
0x14000ed3a  mov     eax, [rsp+78h+arg_0]
0x14000ed41  mov     rbx, [rsp+78h+arg_8]
0x14000ed49  add     rsp, 70h
0x14000ed4d  pop     rdi
0x14000ed4e  retn
```
