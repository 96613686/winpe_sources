# Windows::Security::Isolation::FileDialogBroker::SetEditBoxText(ulong,ushort const *)

- ea: `0x14000e990`
- end: `0x14000ea0d`
- name: `?SetEditBoxText@FileDialogBroker@Isolation@Security@Windows@@UEAAJKPEBG@Z`
- size: `125`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000e990`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000e9a7`: `FileDialogBroker::SetEditBoxText`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetEditBoxText(
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

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v10, (__int64)"FileDialogBroker::SetEditBoxText");
  try
  {
    v6 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *))(*(_QWORD *)v6 + 128LL))(v6, a2, a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
    result = v7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x67F,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000e990  mov     [rsp+arg_8], rbx
0x14000e995  mov     [rsp+arg_10], rsi
0x14000e99a  push    rdi
0x14000e99b  sub     rsp, 70h
0x14000e99f  mov     rdi, r8
0x14000e9a2  mov     esi, edx
0x14000e9a4  mov     rbx, rcx
0x14000e9a7  lea     rdx, aFiledialogbrok_90; "FileDialogBroker::SetEditBoxText"
0x14000e9ae  lea     rcx, [rsp+78h+var_58]
0x14000e9b3  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000e9b8  nop
0x14000e9b9  lea     rcx, [rbx-30h]
0x14000e9bd  mov     rax, [rcx]
0x14000e9c0  mov     rax, [rax+50h]
0x14000e9c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e9c9  mov     r9, rax
0x14000e9cc  mov     rcx, [rax]
0x14000e9cf  mov     rax, [rcx+80h]
0x14000e9d6  mov     r8, rdi
0x14000e9d9  mov     edx, esi
0x14000e9db  mov     rcx, r9
0x14000e9de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e9e3  mov     ebx, eax
0x14000e9e5  lea     rcx, [rsp+78h+var_58]; this
0x14000e9ea  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000e9ef  mov     eax, ebx
0x14000e9f1  jmp     short loc_14000E9FA
0x14000e9f3  mov     eax, [rsp+78h+arg_0]
0x14000e9fa  lea     r11, [rsp+78h+var_8]
0x14000e9ff  mov     rbx, [r11+18h]
0x14000ea03  mov     rsi, [r11+20h]
0x14000ea07  mov     rsp, r11
0x14000ea0a  pop     rdi
0x14000ea0b  retn
```
