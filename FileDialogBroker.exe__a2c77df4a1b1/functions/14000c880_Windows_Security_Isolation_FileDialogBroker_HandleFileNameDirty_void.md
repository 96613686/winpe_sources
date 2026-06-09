# Windows::Security::Isolation::FileDialogBroker::HandleFileNameDirty(void)

- ea: `0x14000c880`
- end: `0x14000c8de`
- name: `?HandleFileNameDirty@FileDialogBroker@Isolation@Security@Windows@@UEAAJXZ`
- size: `94`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000c880`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000c889`: `FileDialogBroker::HandleFileNameDirty`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::HandleFileNameDirty(
        Windows::Security::Isolation::FileDialogBroker *this)
{
  __int64 v2; // rax
  unsigned int v3; // ebx
  const char *v4; // r9
  __int64 result; // rax
  _BYTE v6[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v6, (__int64)"FileDialogBroker::HandleFileNameDirty");
  try
  {
    v2 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 320LL))(v2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v6);
    result = v3;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x405,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x14000c880  push    rbx
0x14000c882  sub     rsp, 70h
0x14000c886  mov     rbx, rcx
0x14000c889  lea     rdx, aFiledialogbrok; "FileDialogBroker::HandleFileNameDirty"
0x14000c890  lea     rcx, [rsp+78h+var_58]
0x14000c895  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000c89a  nop
0x14000c89b  lea     rcx, [rbx-10h]
0x14000c89f  mov     rax, [rcx]
0x14000c8a2  mov     rax, [rax+40h]
0x14000c8a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c8ab  mov     rdx, rax
0x14000c8ae  mov     rcx, [rax]
0x14000c8b1  mov     rax, [rcx+140h]
0x14000c8b8  mov     rcx, rdx
0x14000c8bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c8c0  mov     ebx, eax
0x14000c8c2  lea     rcx, [rsp+78h+var_58]; this
0x14000c8c7  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000c8cc  mov     eax, ebx
0x14000c8ce  jmp     short loc_14000C8D7
0x14000c8d0  mov     eax, [rsp+78h+arg_0]
0x14000c8d7  add     rsp, 70h
0x14000c8db  pop     rbx
0x14000c8dc  retn
```
