# Windows::Security::Isolation::FileDialogBroker::SetDefaultFolder(IShellItem *)

- ea: `0x14000e8e0`
- end: `0x14000e94d`
- name: `?SetDefaultFolder@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAUIShellItem@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, struct IShellItem *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000e960`
- `0x14000e970`
- `0x14000e980`

## callees

- `0x140009194`
- `0x14000e8e0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000e8f0`: `FileDialogBroker::SetDefaultFolder`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetDefaultFolder(
        Windows::Security::Isolation::FileDialogBroker *this,
        struct IShellItem *a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v8, "FileDialogBroker::SetDefaultFolder");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 1) + 56LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, struct IShellItem *))(*(_QWORD *)v4 + 88LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2CA,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000e8e0  mov     [rsp+arg_8], rbx
0x14000e8e5  push    rdi
0x14000e8e6  sub     rsp, 70h
0x14000e8ea  mov     rbx, rdx
0x14000e8ed  mov     rdi, rcx
0x14000e8f0  lea     rdx, aFiledialogbrok_1; "FileDialogBroker::SetDefaultFolder"
0x14000e8f7  lea     rcx, [rsp+78h+var_58]
0x14000e8fc  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000e901  nop
0x14000e902  lea     rcx, [rdi-8]
0x14000e906  mov     rax, [rcx]
0x14000e909  mov     rax, [rax+38h]
0x14000e90d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e912  mov     r8, rax
0x14000e915  mov     rcx, [rax]
0x14000e918  mov     rax, [rcx+58h]
0x14000e91c  mov     rdx, rbx
0x14000e91f  mov     rcx, r8
0x14000e922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e927  mov     ebx, eax
0x14000e929  lea     rcx, [rsp+78h+var_58]; this
0x14000e92e  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000e933  mov     eax, ebx
0x14000e935  jmp     short loc_14000E93E
0x14000e937  mov     eax, [rsp+78h+arg_0]
0x14000e93e  mov     rbx, [rsp+78h+arg_8]
0x14000e946  add     rsp, 70h
0x14000e94a  pop     rdi
0x14000e94b  retn
```
