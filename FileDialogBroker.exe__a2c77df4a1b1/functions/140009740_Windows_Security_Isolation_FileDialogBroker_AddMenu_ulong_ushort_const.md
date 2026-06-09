# Windows::Security::Isolation::FileDialogBroker::AddMenu(ulong,ushort const *)

- ea: `0x140009740`
- end: `0x1400097ba`
- name: `?AddMenu@FileDialogBroker@Isolation@Security@Windows@@UEAAJKPEBG@Z`
- size: `122`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x140009740`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x140009757`: `FileDialogBroker::AddMenu`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::AddMenu(
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

  FileDialogBrokerTraceLogging::WatchCurrentThread(v10, "FileDialogBroker::AddMenu");
  try
  {
    v6 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *))(*(_QWORD *)v6 + 32LL))(v6, a2, a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
    result = v7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x607,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x140009740  mov     [rsp+arg_8], rbx
0x140009745  mov     [rsp+arg_10], rsi
0x14000974a  push    rdi
0x14000974b  sub     rsp, 70h
0x14000974f  mov     rdi, r8
0x140009752  mov     esi, edx
0x140009754  mov     rbx, rcx
0x140009757  lea     rdx, aFiledialogbrok_55; "FileDialogBroker::AddMenu"
0x14000975e  lea     rcx, [rsp+78h+var_58]
0x140009763  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x140009768  nop
0x140009769  lea     rcx, [rbx-30h]
0x14000976d  mov     rax, [rcx]
0x140009770  mov     rax, [rax+50h]
0x140009774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009779  mov     r9, rax
0x14000977c  mov     rcx, [rax]
0x14000977f  mov     rax, [rcx+20h]
0x140009783  mov     r8, rdi
0x140009786  mov     edx, esi
0x140009788  mov     rcx, r9
0x14000978b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009790  mov     ebx, eax
0x140009792  lea     rcx, [rsp+78h+var_58]; this
0x140009797  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000979c  mov     eax, ebx
0x14000979e  jmp     short loc_1400097A7
0x1400097a0  mov     eax, [rsp+78h+arg_0]
0x1400097a7  lea     r11, [rsp+78h+var_8]
0x1400097ac  mov     rbx, [r11+18h]
0x1400097b0  mov     rsi, [r11+20h]
0x1400097b4  mov     rsp, r11
0x1400097b7  pop     rdi
0x1400097b8  retn
```
