# Windows::Security::Isolation::FileDialogBroker::HandleOk(void)

- ea: `0x14000c8f0`
- end: `0x14000c94e`
- name: `?HandleOk@FileDialogBroker@Isolation@Security@Windows@@UEAAJXZ`
- size: `94`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000c8f0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000c8f9`: `FileDialogBroker::HandleOk`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::HandleOk(
        Windows::Security::Isolation::FileDialogBroker *this)
{
  __int64 v2; // rax
  unsigned int v3; // ebx
  const char *v4; // r9
  __int64 result; // rax
  _BYTE v6[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v6, (__int64)"FileDialogBroker::HandleOk");
  try
  {
    v2 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 232LL))(v2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v6);
    result = v3;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x397,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x14000c8f0  push    rbx
0x14000c8f2  sub     rsp, 70h
0x14000c8f6  mov     rbx, rcx
0x14000c8f9  lea     rdx, aFiledialogbrok_65; "FileDialogBroker::HandleOk"
0x14000c900  lea     rcx, [rsp+78h+var_58]
0x14000c905  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000c90a  nop
0x14000c90b  lea     rcx, [rbx-10h]
0x14000c90f  mov     rax, [rcx]
0x14000c912  mov     rax, [rax+40h]
0x14000c916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c91b  mov     rdx, rax
0x14000c91e  mov     rcx, [rax]
0x14000c921  mov     rax, [rcx+0E8h]
0x14000c928  mov     rcx, rdx
0x14000c92b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c930  mov     ebx, eax
0x14000c932  lea     rcx, [rsp+78h+var_58]; this
0x14000c937  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000c93c  mov     eax, ebx
0x14000c93e  jmp     short loc_14000C947
0x14000c940  mov     eax, [rsp+78h+arg_0]
0x14000c947  add     rsp, 70h
0x14000c94b  pop     rbx
0x14000c94c  retn
```
