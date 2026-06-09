# Windows::Security::Isolation::FileDialogBroker::GetCurrentSelection(IShellItem * *)

- ea: `0x14000ab70`
- end: `0x14000abdd`
- name: `?GetCurrentSelection@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAPEAUIShellItem@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, struct IShellItem **)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000abf0`
- `0x14000ac00`
- `0x14000ac10`

## callees

- `0x140009194`
- `0x14000ab70`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000ab80`: `FileDialogBroker::GetCurrentSelection`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetCurrentSelection(
        Windows::Security::Isolation::FileDialogBroker *this,
        struct IShellItem **a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v8, "FileDialogBroker::GetCurrentSelection");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 1) + 56LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, struct IShellItem **))(*(_QWORD *)v4 + 112LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2E8,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000ab70  mov     [rsp+arg_8], rbx
0x14000ab75  push    rdi
0x14000ab76  sub     rsp, 70h
0x14000ab7a  mov     rbx, rdx
0x14000ab7d  mov     rdi, rcx
0x14000ab80  lea     rdx, aFiledialogbrok_24; "FileDialogBroker::GetCurrentSelection"
0x14000ab87  lea     rcx, [rsp+78h+var_58]
0x14000ab8c  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000ab91  nop
0x14000ab92  lea     rcx, [rdi-8]
0x14000ab96  mov     rax, [rcx]
0x14000ab99  mov     rax, [rax+38h]
0x14000ab9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aba2  mov     r8, rax
0x14000aba5  mov     rcx, [rax]
0x14000aba8  mov     rax, [rcx+70h]
0x14000abac  mov     rdx, rbx
0x14000abaf  mov     rcx, r8
0x14000abb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000abb7  mov     ebx, eax
0x14000abb9  lea     rcx, [rsp+78h+var_58]; this
0x14000abbe  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000abc3  mov     eax, ebx
0x14000abc5  jmp     short loc_14000ABCE
0x14000abc7  mov     eax, [rsp+78h+arg_0]
0x14000abce  mov     rbx, [rsp+78h+arg_8]
0x14000abd6  add     rsp, 70h
0x14000abda  pop     rdi
0x14000abdb  retn
```
