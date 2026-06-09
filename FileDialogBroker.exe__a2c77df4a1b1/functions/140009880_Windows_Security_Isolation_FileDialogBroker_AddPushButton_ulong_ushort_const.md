# Windows::Security::Isolation::FileDialogBroker::AddPushButton(ulong,ushort const *)

- ea: `0x140009880`
- end: `0x1400098fa`
- name: `?AddPushButton@FileDialogBroker@Isolation@Security@Windows@@UEAAJKPEBG@Z`
- size: `122`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x140009880`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x140009897`: `FileDialogBroker::AddPushButton`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::AddPushButton(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rax
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 result; // rax
  _BYTE v10[80]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v10, "FileDialogBroker::AddPushButton");
  try
  {
    v6 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *))(*(_QWORD *)v6 + 40LL))(v6, a2, a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
    result = v7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x611,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x140009880  mov     [rsp+arg_8], rbx
0x140009885  mov     [rsp+arg_10], rsi
0x14000988a  push    rdi
0x14000988b  sub     rsp, 70h
0x14000988f  mov     rdi, r8
0x140009892  mov     esi, edx
0x140009894  mov     rbx, rcx
0x140009897  lea     rdx, aFiledialogbrok_19; "FileDialogBroker::AddPushButton"
0x14000989e  lea     rcx, [rsp+78h+var_58]
0x1400098a3  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x1400098a8  nop
0x1400098a9  lea     rcx, [rbx-30h]
0x1400098ad  mov     rax, [rcx]
0x1400098b0  mov     rax, [rax+50h]
0x1400098b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400098b9  mov     r9, rax
0x1400098bc  mov     rcx, [rax]
0x1400098bf  mov     rax, [rcx+28h]
0x1400098c3  mov     r8, rdi
0x1400098c6  mov     edx, esi
0x1400098c8  mov     rcx, r9
0x1400098cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400098d0  mov     ebx, eax
0x1400098d2  lea     rcx, [rsp+78h+var_58]; this
0x1400098d7  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1400098dc  mov     eax, ebx
0x1400098de  jmp     short loc_1400098E7
0x1400098e0  mov     eax, [rsp+78h+arg_0]
0x1400098e7  lea     r11, [rsp+78h+var_8]
0x1400098ec  mov     rbx, [r11+18h]
0x1400098f0  mov     rsi, [r11+20h]
0x1400098f4  mov     rsp, r11
0x1400098f7  pop     rdi
0x1400098f8  retn
```
