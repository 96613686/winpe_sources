# Windows::Security::Isolation::FileDialogBroker::GetControlItemState(ulong,ulong,CDCONTROLSTATEF *)

- ea: `0x14000a960`
- end: `0x14000a9de`
- name: `?GetControlItemState@FileDialogBroker@Isolation@Security@Windows@@UEAAJKKPEAW4CDCONTROLSTATEF@@@Z`
- size: `126`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int, unsigned int, enum CDCONTROLSTATEF *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000a960`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000a979`: `FileDialogBroker::GetControlItemState`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetControlItemState(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2,
        unsigned int a3,
        enum CDCONTROLSTATEF *a4)
{
  __int64 v8; // rax
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 result; // rax
  _BYTE v12[120]; // [rsp+30h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v12, "FileDialogBroker::GetControlItemState");
  try
  {
    v8 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, enum CDCONTROLSTATEF *))(*(_QWORD *)v8 + 176LL))(
           v8,
           a2,
           a3,
           a4);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v12);
    result = v9;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x6BB,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x14000a960  push    rbx
0x14000a962  push    rsi
0x14000a963  push    rdi
0x14000a964  push    r14
0x14000a966  sub     rsp, 88h
0x14000a96d  mov     rdi, r9
0x14000a970  mov     esi, r8d
0x14000a973  mov     r14d, edx
0x14000a976  mov     rbx, rcx
0x14000a979  lea     rdx, aFiledialogbrok_85; "FileDialogBroker::GetControlItemState"
0x14000a980  lea     rcx, [rsp+0A8h+var_78]
0x14000a985  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000a98a  nop
0x14000a98b  lea     rcx, [rbx-30h]
0x14000a98f  mov     rax, [rcx]
0x14000a992  mov     rax, [rax+50h]
0x14000a996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a99b  mov     r10, rax
0x14000a99e  mov     rcx, [rax]
0x14000a9a1  mov     rax, [rcx+0B0h]
0x14000a9a8  mov     r9, rdi
0x14000a9ab  mov     r8d, esi
0x14000a9ae  mov     edx, r14d
0x14000a9b1  mov     rcx, r10
0x14000a9b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a9b9  mov     ebx, eax
0x14000a9bb  lea     rcx, [rsp+0A8h+var_78]; this
0x14000a9c0  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000a9c5  mov     eax, ebx
0x14000a9c7  jmp     short loc_14000A9D0
0x14000a9c9  mov     eax, [rsp+0A8h+arg_0]
0x14000a9d0  add     rsp, 88h
0x14000a9d7  pop     r14
0x14000a9d9  pop     rdi
0x14000a9da  pop     rsi
0x14000a9db  pop     rbx
0x14000a9dc  retn
```
