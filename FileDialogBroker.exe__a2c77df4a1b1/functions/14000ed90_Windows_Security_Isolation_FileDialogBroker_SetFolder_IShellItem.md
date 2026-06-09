# Windows::Security::Isolation::FileDialogBroker::SetFolder(IShellItem *)

- ea: `0x14000ed90`
- end: `0x14000edfd`
- name: `?SetFolder@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAUIShellItem@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, struct IShellItem *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000ee10`
- `0x14000ee20`
- `0x14000ee30`

## callees

- `0x140009194`
- `0x14000ed90`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000eda0`: `FileDialogBroker::SetFolder`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetFolder(
        Windows::Security::Isolation::FileDialogBroker *this,
        struct IShellItem *a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v8, "FileDialogBroker::SetFolder");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 1) + 56LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, struct IShellItem *))(*(_QWORD *)v4 + 96LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2D4,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000ed90  mov     [rsp+arg_8], rbx
0x14000ed95  push    rdi
0x14000ed96  sub     rsp, 70h
0x14000ed9a  mov     rbx, rdx
0x14000ed9d  mov     rdi, rcx
0x14000eda0  lea     rdx, aFiledialogbrok_11; "FileDialogBroker::SetFolder"
0x14000eda7  lea     rcx, [rsp+78h+var_58]
0x14000edac  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000edb1  nop
0x14000edb2  lea     rcx, [rdi-8]
0x14000edb6  mov     rax, [rcx]
0x14000edb9  mov     rax, [rax+38h]
0x14000edbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000edc2  mov     r8, rax
0x14000edc5  mov     rcx, [rax]
0x14000edc8  mov     rax, [rcx+60h]
0x14000edcc  mov     rdx, rbx
0x14000edcf  mov     rcx, r8
0x14000edd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000edd7  mov     ebx, eax
0x14000edd9  lea     rcx, [rsp+78h+var_58]; this
0x14000edde  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000ede3  mov     eax, ebx
0x14000ede5  jmp     short loc_14000EDEE
0x14000ede7  mov     eax, [rsp+78h+arg_0]
0x14000edee  mov     rbx, [rsp+78h+arg_8]
0x14000edf6  add     rsp, 70h
0x14000edfa  pop     rdi
0x14000edfb  retn
```
