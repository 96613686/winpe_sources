# Windows::Security::Isolation::FileDialogBroker::SetControlLabel(ulong,ushort const *)

- ea: `0x14000e6c0`
- end: `0x14000e73a`
- name: `?SetControlLabel@FileDialogBroker@Isolation@Security@Windows@@UEAAJKPEBG@Z`
- size: `122`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000e6c0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000e6d7`: `FileDialogBroker::SetControlLabel`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetControlLabel(
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

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v10, (__int64)"FileDialogBroker::SetControlLabel");
  try
  {
    v6 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *))(*(_QWORD *)v6 + 96LL))(v6, a2, a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
    result = v7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x657,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000e6c0  mov     [rsp+arg_8], rbx
0x14000e6c5  mov     [rsp+arg_10], rsi
0x14000e6ca  push    rdi
0x14000e6cb  sub     rsp, 70h
0x14000e6cf  mov     rdi, r8
0x14000e6d2  mov     esi, edx
0x14000e6d4  mov     rbx, rcx
0x14000e6d7  lea     rdx, aFiledialogbrok_21; "FileDialogBroker::SetControlLabel"
0x14000e6de  lea     rcx, [rsp+78h+var_58]
0x14000e6e3  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000e6e8  nop
0x14000e6e9  lea     rcx, [rbx-30h]
0x14000e6ed  mov     rax, [rcx]
0x14000e6f0  mov     rax, [rax+50h]
0x14000e6f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e6f9  mov     r9, rax
0x14000e6fc  mov     rcx, [rax]
0x14000e6ff  mov     rax, [rcx+60h]
0x14000e703  mov     r8, rdi
0x14000e706  mov     edx, esi
0x14000e708  mov     rcx, r9
0x14000e70b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e710  mov     ebx, eax
0x14000e712  lea     rcx, [rsp+78h+var_58]; this
0x14000e717  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000e71c  mov     eax, ebx
0x14000e71e  jmp     short loc_14000E727
0x14000e720  mov     eax, [rsp+78h+arg_0]
0x14000e727  lea     r11, [rsp+78h+var_8]
0x14000e72c  mov     rbx, [r11+18h]
0x14000e730  mov     rsi, [r11+20h]
0x14000e734  mov     rsp, r11
0x14000e737  pop     rdi
0x14000e738  retn
```
