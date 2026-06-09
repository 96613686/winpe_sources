# Windows::Security::Isolation::FileDialogBroker::SetSelectedControlItem(ulong,ulong)

- ea: `0x14000f290`
- end: `0x14000f30d`
- name: `?SetSelectedControlItem@FileDialogBroker@Isolation@Security@Windows@@UEAAJKK@Z`
- size: `125`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000f290`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000f2a7`: `FileDialogBroker::SetSelectedControlItem`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetSelectedControlItem(
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

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v10, (__int64)"FileDialogBroker::SetSelectedControlItem");
  try
  {
    v6 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v6 + 200LL))(v6, a2, a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
    result = v7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x6D9,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000f290  mov     [rsp+arg_8], rbx
0x14000f295  mov     [rsp+arg_10], rsi
0x14000f29a  push    rdi
0x14000f29b  sub     rsp, 70h
0x14000f29f  mov     edi, r8d
0x14000f2a2  mov     esi, edx
0x14000f2a4  mov     rbx, rcx
0x14000f2a7  lea     rdx, aFiledialogbrok_15; "FileDialogBroker::SetSelectedControlIte"...
0x14000f2ae  lea     rcx, [rsp+78h+var_58]
0x14000f2b3  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000f2b8  nop
0x14000f2b9  lea     rcx, [rbx-30h]
0x14000f2bd  mov     rax, [rcx]
0x14000f2c0  mov     rax, [rax+50h]
0x14000f2c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f2c9  mov     r9, rax
0x14000f2cc  mov     rcx, [rax]
0x14000f2cf  mov     rax, [rcx+0C8h]
0x14000f2d6  mov     r8d, edi
0x14000f2d9  mov     edx, esi
0x14000f2db  mov     rcx, r9
0x14000f2de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f2e3  mov     ebx, eax
0x14000f2e5  lea     rcx, [rsp+78h+var_58]; this
0x14000f2ea  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000f2ef  mov     eax, ebx
0x14000f2f1  jmp     short loc_14000F2FA
0x14000f2f3  mov     eax, [rsp+78h+arg_0]
0x14000f2fa  lea     r11, [rsp+78h+var_8]
0x14000f2ff  mov     rbx, [r11+18h]
0x14000f303  mov     rsi, [r11+20h]
0x14000f307  mov     rsp, r11
0x14000f30a  pop     rdi
0x14000f30b  retn
```
