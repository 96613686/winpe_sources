# Windows::Security::Isolation::FileDialogBroker::GetControlState(ulong,CDCONTROLSTATEF *)

- ea: `0x14000a9f0`
- end: `0x14000aa6a`
- name: `?GetControlState@FileDialogBroker@Isolation@Security@Windows@@UEAAJKPEAW4CDCONTROLSTATEF@@@Z`
- size: `122`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int, enum CDCONTROLSTATEF *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000a9f0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000aa07`: `FileDialogBroker::GetControlState`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetControlState(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2,
        enum CDCONTROLSTATEF *a3)
{
  __int64 v6; // rax
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 result; // rax
  _BYTE v10[80]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v10, "FileDialogBroker::GetControlState");
  try
  {
    v6 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, enum CDCONTROLSTATEF *))(*(_QWORD *)v6 + 104LL))(v6, a2, a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
    result = v7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x661,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000a9f0  mov     [rsp+arg_8], rbx
0x14000a9f5  mov     [rsp+arg_10], rsi
0x14000a9fa  push    rdi
0x14000a9fb  sub     rsp, 70h
0x14000a9ff  mov     rdi, r8
0x14000aa02  mov     esi, edx
0x14000aa04  mov     rbx, rcx
0x14000aa07  lea     rdx, aFiledialogbrok_52; "FileDialogBroker::GetControlState"
0x14000aa0e  lea     rcx, [rsp+78h+var_58]
0x14000aa13  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000aa18  nop
0x14000aa19  lea     rcx, [rbx-30h]
0x14000aa1d  mov     rax, [rcx]
0x14000aa20  mov     rax, [rax+50h]
0x14000aa24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa29  mov     r9, rax
0x14000aa2c  mov     rcx, [rax]
0x14000aa2f  mov     rax, [rcx+68h]
0x14000aa33  mov     r8, rdi
0x14000aa36  mov     edx, esi
0x14000aa38  mov     rcx, r9
0x14000aa3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa40  mov     ebx, eax
0x14000aa42  lea     rcx, [rsp+78h+var_58]; this
0x14000aa47  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000aa4c  mov     eax, ebx
0x14000aa4e  jmp     short loc_14000AA57
0x14000aa50  mov     eax, [rsp+78h+arg_0]
0x14000aa57  lea     r11, [rsp+78h+var_8]
0x14000aa5c  mov     rbx, [r11+18h]
0x14000aa60  mov     rsi, [r11+20h]
0x14000aa64  mov     rsp, r11
0x14000aa67  pop     rdi
0x14000aa68  retn
```
