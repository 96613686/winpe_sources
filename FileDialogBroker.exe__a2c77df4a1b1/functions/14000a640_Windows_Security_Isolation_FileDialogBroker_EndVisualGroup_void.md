# Windows::Security::Isolation::FileDialogBroker::EndVisualGroup(void)

- ea: `0x14000a640`
- end: `0x14000a69e`
- name: `?EndVisualGroup@FileDialogBroker@Isolation@Security@Windows@@UEAAJXZ`
- size: `94`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000a640`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000a649`: `FileDialogBroker::EndVisualGroup`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::EndVisualGroup(
        Windows::Security::Isolation::FileDialogBroker *this)
{
  __int64 v2; // rax
  unsigned int v3; // ebx
  const char *v4; // r9
  __int64 result; // rax
  _BYTE v6[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v6, "FileDialogBroker::EndVisualGroup");
  try
  {
    v2 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 216LL))(v2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v6);
    result = v3;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x6ED,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x14000a640  push    rbx
0x14000a642  sub     rsp, 70h
0x14000a646  mov     rbx, rcx
0x14000a649  lea     rdx, aFiledialogbrok_35; "FileDialogBroker::EndVisualGroup"
0x14000a650  lea     rcx, [rsp+78h+var_58]
0x14000a655  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000a65a  nop
0x14000a65b  lea     rcx, [rbx-30h]
0x14000a65f  mov     rax, [rcx]
0x14000a662  mov     rax, [rax+50h]
0x14000a666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a66b  mov     rdx, rax
0x14000a66e  mov     rcx, [rax]
0x14000a671  mov     rax, [rcx+0D8h]
0x14000a678  mov     rcx, rdx
0x14000a67b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a680  mov     ebx, eax
0x14000a682  lea     rcx, [rsp+78h+var_58]; this
0x14000a687  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000a68c  mov     eax, ebx
0x14000a68e  jmp     short loc_14000A697
0x14000a690  mov     eax, [rsp+78h+arg_0]
0x14000a697  add     rsp, 70h
0x14000a69b  pop     rbx
0x14000a69c  retn
```
