# Windows::Security::Isolation::FileDialogBroker::GetCurrentSelectionInternal(IShellItem * *,int)

- ea: `0x14000ac20`
- end: `0x14000ac9f`
- name: `?GetCurrentSelectionInternal@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAPEAUIShellItem@@H@Z`
- size: `127`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *this, struct IShellItem **, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000ac20`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000ac38`: `FileDialogBroker::GetCurrentSelectionInternal`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetCurrentSelectionInternal(
        Windows::Security::Isolation::FileDialogBroker *this,
        struct IShellItem **a2,
        unsigned int a3)
{
  __int64 v6; // rax
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 result; // rax
  _BYTE v10[80]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v10, "FileDialogBroker::GetCurrentSelectionInternal");
  try
  {
    v6 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    v7 = (*(__int64 (__fastcall **)(__int64, struct IShellItem **, _QWORD))(*(_QWORD *)v6 + 344LL))(v6, a2, a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
    result = v7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x423,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000ac20  mov     [rsp+arg_8], rbx
0x14000ac25  mov     [rsp+arg_10], rsi
0x14000ac2a  push    rdi
0x14000ac2b  sub     rsp, 70h
0x14000ac2f  mov     edi, r8d
0x14000ac32  mov     rsi, rdx
0x14000ac35  mov     rbx, rcx
0x14000ac38  lea     rdx, aFiledialogbrok_29; "FileDialogBroker::GetCurrentSelectionIn"...
0x14000ac3f  lea     rcx, [rsp+78h+var_58]
0x14000ac44  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000ac49  nop
0x14000ac4a  lea     rcx, [rbx-10h]
0x14000ac4e  mov     rax, [rcx]
0x14000ac51  mov     rax, [rax+40h]
0x14000ac55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ac5a  mov     r9, rax
0x14000ac5d  mov     rcx, [rax]
0x14000ac60  mov     rax, [rcx+158h]
0x14000ac67  mov     r8d, edi
0x14000ac6a  mov     rdx, rsi
0x14000ac6d  mov     rcx, r9
0x14000ac70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ac75  mov     ebx, eax
0x14000ac77  lea     rcx, [rsp+78h+var_58]; this
0x14000ac7c  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000ac81  mov     eax, ebx
0x14000ac83  jmp     short loc_14000AC8C
0x14000ac85  mov     eax, [rsp+78h+arg_0]
0x14000ac8c  lea     r11, [rsp+78h+var_8]
0x14000ac91  mov     rbx, [r11+18h]
0x14000ac95  mov     rsi, [r11+20h]
0x14000ac99  mov     rsp, r11
0x14000ac9c  pop     rdi
0x14000ac9d  retn
```
