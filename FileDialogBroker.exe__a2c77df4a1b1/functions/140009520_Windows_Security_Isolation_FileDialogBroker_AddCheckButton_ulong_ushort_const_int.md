# Windows::Security::Isolation::FileDialogBroker::AddCheckButton(ulong,ushort const *,int)

- ea: `0x140009520`
- end: `0x14000959b`
- name: `?AddCheckButton@FileDialogBroker@Isolation@Security@Windows@@UEAAJKPEBGH@Z`
- size: `123`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *this, unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x140009520`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x140009539`: `FileDialogBroker::AddCheckButton`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::AddCheckButton(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  __int64 v8; // rax
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 result; // rax
  _BYTE v12[120]; // [rsp+30h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v12, "FileDialogBroker::AddCheckButton");
  try
  {
    v8 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, _QWORD))(*(_QWORD *)v8 + 64LL))(
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
                           (void *)0x62F,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x140009520  push    rbx
0x140009522  push    rsi
0x140009523  push    rdi
0x140009524  push    r14
0x140009526  sub     rsp, 88h
0x14000952d  mov     edi, r9d
0x140009530  mov     rsi, r8
0x140009533  mov     r14d, edx
0x140009536  mov     rbx, rcx
0x140009539  lea     rdx, aFiledialogbrok_67; "FileDialogBroker::AddCheckButton"
0x140009540  lea     rcx, [rsp+0A8h+var_78]
0x140009545  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000954a  nop
0x14000954b  lea     rcx, [rbx-30h]
0x14000954f  mov     rax, [rcx]
0x140009552  mov     rax, [rax+50h]
0x140009556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000955b  mov     r10, rax
0x14000955e  mov     rcx, [rax]
0x140009561  mov     rax, [rcx+40h]
0x140009565  mov     r9d, edi
0x140009568  mov     r8, rsi
0x14000956b  mov     edx, r14d
0x14000956e  mov     rcx, r10
0x140009571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009576  mov     ebx, eax
0x140009578  lea     rcx, [rsp+0A8h+var_78]; this
0x14000957d  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x140009582  mov     eax, ebx
0x140009584  jmp     short loc_14000958D
0x140009586  mov     eax, [rsp+0A8h+arg_0]
0x14000958d  add     rsp, 88h
0x140009594  pop     r14
0x140009596  pop     rdi
0x140009597  pop     rsi
0x140009598  pop     rbx
0x140009599  retn
```
