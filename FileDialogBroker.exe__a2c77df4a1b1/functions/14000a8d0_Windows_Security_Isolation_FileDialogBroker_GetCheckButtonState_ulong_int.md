# Windows::Security::Isolation::FileDialogBroker::GetCheckButtonState(ulong,int *)

- ea: `0x14000a8d0`
- end: `0x14000a94d`
- name: `?GetCheckButtonState@FileDialogBroker@Isolation@Security@Windows@@UEAAJKPEAH@Z`
- size: `125`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000a8d0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000a8e7`: `FileDialogBroker::GetCheckButtonState`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetCheckButtonState(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2,
        int *a3)
{
  __int64 v6; // rax
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 result; // rax
  _BYTE v10[80]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v10, "FileDialogBroker::GetCheckButtonState");
  try
  {
    v6 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v6 + 136LL))(v6, a2, a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
    result = v7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x689,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000a8d0  mov     [rsp+arg_8], rbx
0x14000a8d5  mov     [rsp+arg_10], rsi
0x14000a8da  push    rdi
0x14000a8db  sub     rsp, 70h
0x14000a8df  mov     rdi, r8
0x14000a8e2  mov     esi, edx
0x14000a8e4  mov     rbx, rcx
0x14000a8e7  lea     rdx, aFiledialogbrok_2; "FileDialogBroker::GetCheckButtonState"
0x14000a8ee  lea     rcx, [rsp+78h+var_58]
0x14000a8f3  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000a8f8  nop
0x14000a8f9  lea     rcx, [rbx-30h]
0x14000a8fd  mov     rax, [rcx]
0x14000a900  mov     rax, [rax+50h]
0x14000a904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a909  mov     r9, rax
0x14000a90c  mov     rcx, [rax]
0x14000a90f  mov     rax, [rcx+88h]
0x14000a916  mov     r8, rdi
0x14000a919  mov     edx, esi
0x14000a91b  mov     rcx, r9
0x14000a91e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a923  mov     ebx, eax
0x14000a925  lea     rcx, [rsp+78h+var_58]; this
0x14000a92a  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000a92f  mov     eax, ebx
0x14000a931  jmp     short loc_14000A93A
0x14000a933  mov     eax, [rsp+78h+arg_0]
0x14000a93a  lea     r11, [rsp+78h+var_8]
0x14000a93f  mov     rbx, [r11+18h]
0x14000a943  mov     rsi, [r11+20h]
0x14000a947  mov     rsp, r11
0x14000a94a  pop     rdi
0x14000a94b  retn
```
