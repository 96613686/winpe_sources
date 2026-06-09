# Windows::Security::Isolation::FileDialogBroker::SetControlState(ulong,CDCONTROLSTATEF)

- ea: `0x14000e740`
- end: `0x14000e7ba`
- name: `?SetControlState@FileDialogBroker@Isolation@Security@Windows@@UEAAJKW4CDCONTROLSTATEF@@@Z`
- size: `122`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int, enum CDCONTROLSTATEF)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000e740`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000e757`: `FileDialogBroker::SetControlState`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetControlState(
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

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v10, (__int64)"FileDialogBroker::SetControlState");
  try
  {
    v6 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v6 + 112LL))(v6, a2, a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
    result = v7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x66B,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000e740  mov     [rsp+arg_8], rbx
0x14000e745  mov     [rsp+arg_10], rsi
0x14000e74a  push    rdi
0x14000e74b  sub     rsp, 70h
0x14000e74f  mov     edi, r8d
0x14000e752  mov     esi, edx
0x14000e754  mov     rbx, rcx
0x14000e757  lea     rdx, aFiledialogbrok_3; "FileDialogBroker::SetControlState"
0x14000e75e  lea     rcx, [rsp+78h+var_58]
0x14000e763  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000e768  nop
0x14000e769  lea     rcx, [rbx-30h]
0x14000e76d  mov     rax, [rcx]
0x14000e770  mov     rax, [rax+50h]
0x14000e774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e779  mov     r9, rax
0x14000e77c  mov     rcx, [rax]
0x14000e77f  mov     rax, [rcx+70h]
0x14000e783  mov     r8d, edi
0x14000e786  mov     edx, esi
0x14000e788  mov     rcx, r9
0x14000e78b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e790  mov     ebx, eax
0x14000e792  lea     rcx, [rsp+78h+var_58]; this
0x14000e797  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000e79c  mov     eax, ebx
0x14000e79e  jmp     short loc_14000E7A7
0x14000e7a0  mov     eax, [rsp+78h+arg_0]
0x14000e7a7  lea     r11, [rsp+78h+var_8]
0x14000e7ac  mov     rbx, [r11+18h]
0x14000e7b0  mov     rsi, [r11+20h]
0x14000e7b4  mov     rsp, r11
0x14000e7b7  pop     rdi
0x14000e7b8  retn
```
