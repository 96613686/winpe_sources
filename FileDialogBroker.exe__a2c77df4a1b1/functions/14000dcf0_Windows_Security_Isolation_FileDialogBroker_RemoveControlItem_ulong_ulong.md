# Windows::Security::Isolation::FileDialogBroker::RemoveControlItem(ulong,ulong)

- ea: `0x14000dcf0`
- end: `0x14000dd6d`
- name: `?RemoveControlItem@FileDialogBroker@Isolation@Security@Windows@@UEAAJKK@Z`
- size: `125`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000dcf0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000dd07`: `FileDialogBroker::RemoveControlItem`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::RemoveControlItem(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2,
        unsigned int a3)
{
  __int64 v6; // rax
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 result; // rax
  _BYTE v10[80]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v10, (__int64)"FileDialogBroker::RemoveControlItem");
  try
  {
    v6 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v6 + 160LL))(v6, a2, a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
    result = v7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x6A7,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000dcf0  mov     [rsp+arg_8], rbx
0x14000dcf5  mov     [rsp+arg_10], rsi
0x14000dcfa  push    rdi
0x14000dcfb  sub     rsp, 70h
0x14000dcff  mov     edi, r8d
0x14000dd02  mov     esi, edx
0x14000dd04  mov     rbx, rcx
0x14000dd07  lea     rdx, aFiledialogbrok_37; "FileDialogBroker::RemoveControlItem"
0x14000dd0e  lea     rcx, [rsp+78h+var_58]
0x14000dd13  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000dd18  nop
0x14000dd19  lea     rcx, [rbx-30h]
0x14000dd1d  mov     rax, [rcx]
0x14000dd20  mov     rax, [rax+50h]
0x14000dd24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dd29  mov     r9, rax
0x14000dd2c  mov     rcx, [rax]
0x14000dd2f  mov     rax, [rcx+0A0h]
0x14000dd36  mov     r8d, edi
0x14000dd39  mov     edx, esi
0x14000dd3b  mov     rcx, r9
0x14000dd3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dd43  mov     ebx, eax
0x14000dd45  lea     rcx, [rsp+78h+var_58]; this
0x14000dd4a  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000dd4f  mov     eax, ebx
0x14000dd51  jmp     short loc_14000DD5A
0x14000dd53  mov     eax, [rsp+78h+arg_0]
0x14000dd5a  lea     r11, [rsp+78h+var_8]
0x14000dd5f  mov     rbx, [r11+18h]
0x14000dd63  mov     rsi, [r11+20h]
0x14000dd67  mov     rsp, r11
0x14000dd6a  pop     rdi
0x14000dd6b  retn
```
