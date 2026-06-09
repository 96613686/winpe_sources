# Windows::Security::Isolation::FileDialogBroker::EnableOpenDropDown(ulong)

- ea: `0x14000a5c0`
- end: `0x14000a62b`
- name: `?EnableOpenDropDown@FileDialogBroker@Isolation@Security@Windows@@UEAAJK@Z`
- size: `107`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000a5c0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000a5cf`: `FileDialogBroker::EnableOpenDropDown`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::EnableOpenDropDown(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v8, "FileDialogBroker::EnableOpenDropDown");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 24LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x5FD,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000a5c0  mov     [rsp+arg_8], rbx
0x14000a5c5  push    rdi
0x14000a5c6  sub     rsp, 70h
0x14000a5ca  mov     ebx, edx
0x14000a5cc  mov     rdi, rcx
0x14000a5cf  lea     rdx, aFiledialogbrok_9; "FileDialogBroker::EnableOpenDropDown"
0x14000a5d6  lea     rcx, [rsp+78h+var_58]
0x14000a5db  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000a5e0  nop
0x14000a5e1  lea     rcx, [rdi-30h]
0x14000a5e5  mov     rax, [rcx]
0x14000a5e8  mov     rax, [rax+50h]
0x14000a5ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a5f1  mov     r8, rax
0x14000a5f4  mov     rcx, [rax]
0x14000a5f7  mov     rax, [rcx+18h]
0x14000a5fb  mov     edx, ebx
0x14000a5fd  mov     rcx, r8
0x14000a600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a605  mov     ebx, eax
0x14000a607  lea     rcx, [rsp+78h+var_58]; this
0x14000a60c  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000a611  mov     eax, ebx
0x14000a613  jmp     short loc_14000A61C
0x14000a615  mov     eax, [rsp+78h+arg_0]
0x14000a61c  mov     rbx, [rsp+78h+arg_8]
0x14000a624  add     rsp, 70h
0x14000a628  pop     rdi
0x14000a629  retn
```
