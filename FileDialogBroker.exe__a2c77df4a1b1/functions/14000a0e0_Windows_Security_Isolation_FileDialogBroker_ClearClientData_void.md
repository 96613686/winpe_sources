# Windows::Security::Isolation::FileDialogBroker::ClearClientData(void)

- ea: `0x14000a0e0`
- end: `0x14000a13e`
- name: `?ClearClientData@FileDialogBroker@Isolation@Security@Windows@@UEAAJXZ`
- size: `94`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000a150`
- `0x14000a160`
- `0x14000a170`

## callees

- `0x140009194`
- `0x14000a0e0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000a0e9`: `FileDialogBroker::ClearClientData`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::ClearClientData(
        Windows::Security::Isolation::FileDialogBroker *this)
{
  __int64 v2; // rax
  unsigned int v3; // ebx
  const char *v4; // r9
  __int64 result; // rax
  _BYTE v6[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v6, "FileDialogBroker::ClearClientData");
  try
  {
    v2 = (*(__int64 (**)(void))(*((_QWORD *)this - 1) + 56LL))();
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 200LL))(v2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v6);
    result = v3;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x377,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x14000a0e0  push    rbx
0x14000a0e2  sub     rsp, 70h
0x14000a0e6  mov     rbx, rcx
0x14000a0e9  lea     rdx, aFiledialogbrok_39; "FileDialogBroker::ClearClientData"
0x14000a0f0  lea     rcx, [rsp+78h+var_58]
0x14000a0f5  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000a0fa  nop
0x14000a0fb  lea     rcx, [rbx-8]
0x14000a0ff  mov     rax, [rcx]
0x14000a102  mov     rax, [rax+38h]
0x14000a106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a10b  mov     rdx, rax
0x14000a10e  mov     rcx, [rax]
0x14000a111  mov     rax, [rcx+0C8h]
0x14000a118  mov     rcx, rdx
0x14000a11b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a120  mov     ebx, eax
0x14000a122  lea     rcx, [rsp+78h+var_58]; this
0x14000a127  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000a12c  mov     eax, ebx
0x14000a12e  jmp     short loc_14000A137
0x14000a130  mov     eax, [rsp+78h+arg_0]
0x14000a137  add     rsp, 70h
0x14000a13b  pop     rbx
0x14000a13c  retn
```
