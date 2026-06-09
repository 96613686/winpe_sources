# Windows::Security::Isolation::FileDialogBroker::StartVisualGroup(ulong,ushort const *)

- ea: `0x14000f6a0`
- end: `0x14000f71d`
- name: `?StartVisualGroup@FileDialogBroker@Isolation@Security@Windows@@UEAAJKPEBG@Z`
- size: `125`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000f6a0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000f6b7`: `FileDialogBroker::StartVisualGroup`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::StartVisualGroup(
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

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v10, (__int64)"FileDialogBroker::StartVisualGroup");
  try
  {
    v6 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *))(*(_QWORD *)v6 + 208LL))(v6, a2, a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
    result = v7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x6E3,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000f6a0  mov     [rsp+arg_8], rbx
0x14000f6a5  mov     [rsp+arg_10], rsi
0x14000f6aa  push    rdi
0x14000f6ab  sub     rsp, 70h
0x14000f6af  mov     rdi, r8
0x14000f6b2  mov     esi, edx
0x14000f6b4  mov     rbx, rcx
0x14000f6b7  lea     rdx, aFiledialogbrok_75; "FileDialogBroker::StartVisualGroup"
0x14000f6be  lea     rcx, [rsp+78h+var_58]
0x14000f6c3  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000f6c8  nop
0x14000f6c9  lea     rcx, [rbx-30h]
0x14000f6cd  mov     rax, [rcx]
0x14000f6d0  mov     rax, [rax+50h]
0x14000f6d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f6d9  mov     r9, rax
0x14000f6dc  mov     rcx, [rax]
0x14000f6df  mov     rax, [rcx+0D0h]
0x14000f6e6  mov     r8, rdi
0x14000f6e9  mov     edx, esi
0x14000f6eb  mov     rcx, r9
0x14000f6ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f6f3  mov     ebx, eax
0x14000f6f5  lea     rcx, [rsp+78h+var_58]; this
0x14000f6fa  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000f6ff  mov     eax, ebx
0x14000f701  jmp     short loc_14000F70A
0x14000f703  mov     eax, [rsp+78h+arg_0]
0x14000f70a  lea     r11, [rsp+78h+var_8]
0x14000f70f  mov     rbx, [r11+18h]
0x14000f713  mov     rsi, [r11+20h]
0x14000f717  mov     rsp, r11
0x14000f71a  pop     rdi
0x14000f71b  retn
```
