# Windows::Security::Isolation::FileDialogBroker::SetCheckButtonState(ulong,int)

- ea: `0x14000e3b0`
- end: `0x14000e42d`
- name: `?SetCheckButtonState@FileDialogBroker@Isolation@Security@Windows@@UEAAJKH@Z`
- size: `125`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000e3b0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000e3c7`: `FileDialogBroker::SetCheckButtonState`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetCheckButtonState(
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

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v10, (__int64)"FileDialogBroker::SetCheckButtonState");
  try
  {
    v6 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v6 + 144LL))(v6, a2, a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
    result = v7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x693,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000e3b0  mov     [rsp+arg_8], rbx
0x14000e3b5  mov     [rsp+arg_10], rsi
0x14000e3ba  push    rdi
0x14000e3bb  sub     rsp, 70h
0x14000e3bf  mov     edi, r8d
0x14000e3c2  mov     esi, edx
0x14000e3c4  mov     rbx, rcx
0x14000e3c7  lea     rdx, aFiledialogbrok_68; "FileDialogBroker::SetCheckButtonState"
0x14000e3ce  lea     rcx, [rsp+78h+var_58]
0x14000e3d3  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000e3d8  nop
0x14000e3d9  lea     rcx, [rbx-30h]
0x14000e3dd  mov     rax, [rcx]
0x14000e3e0  mov     rax, [rax+50h]
0x14000e3e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e3e9  mov     r9, rax
0x14000e3ec  mov     rcx, [rax]
0x14000e3ef  mov     rax, [rcx+90h]
0x14000e3f6  mov     r8d, edi
0x14000e3f9  mov     edx, esi
0x14000e3fb  mov     rcx, r9
0x14000e3fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e403  mov     ebx, eax
0x14000e405  lea     rcx, [rsp+78h+var_58]; this
0x14000e40a  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000e40f  mov     eax, ebx
0x14000e411  jmp     short loc_14000E41A
0x14000e413  mov     eax, [rsp+78h+arg_0]
0x14000e41a  lea     r11, [rsp+78h+var_8]
0x14000e41f  mov     rbx, [r11+18h]
0x14000e423  mov     rsi, [r11+20h]
0x14000e427  mov     rsp, r11
0x14000e42a  pop     rdi
0x14000e42b  retn
```
