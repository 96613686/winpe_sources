# Windows::Security::Isolation::FileDialogBroker::TravelBack(void)

- ea: `0x14000f7b0`
- end: `0x14000f80e`
- name: `?TravelBack@FileDialogBroker@Isolation@Security@Windows@@UEAAJXZ`
- size: `94`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000f7b0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000f7b9`: `FileDialogBroker::TravelBack`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::TravelBack(
        Windows::Security::Isolation::FileDialogBroker *this)
{
  __int64 v2; // rax
  unsigned int v3; // ebx
  const char *v4; // r9
  __int64 result; // rax
  _BYTE v6[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v6, (__int64)"FileDialogBroker::TravelBack");
  try
  {
    v2 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 408LL))(v2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v6);
    result = v3;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x473,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x14000f7b0  push    rbx
0x14000f7b2  sub     rsp, 70h
0x14000f7b6  mov     rbx, rcx
0x14000f7b9  lea     rdx, aFiledialogbrok_38; "FileDialogBroker::TravelBack"
0x14000f7c0  lea     rcx, [rsp+78h+var_58]
0x14000f7c5  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000f7ca  nop
0x14000f7cb  lea     rcx, [rbx-10h]
0x14000f7cf  mov     rax, [rcx]
0x14000f7d2  mov     rax, [rax+40h]
0x14000f7d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f7db  mov     rdx, rax
0x14000f7de  mov     rcx, [rax]
0x14000f7e1  mov     rax, [rcx+198h]
0x14000f7e8  mov     rcx, rdx
0x14000f7eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f7f0  mov     ebx, eax
0x14000f7f2  lea     rcx, [rsp+78h+var_58]; this
0x14000f7f7  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000f7fc  mov     eax, ebx
0x14000f7fe  jmp     short loc_14000F807
0x14000f800  mov     eax, [rsp+78h+arg_0]
0x14000f807  add     rsp, 70h
0x14000f80b  pop     rbx
0x14000f80c  retn
```
