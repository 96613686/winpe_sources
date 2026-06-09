# Windows::Security::Isolation::FileDialogBroker::AddSeparator(ulong)

- ea: `0x140009ad0`
- end: `0x140009b3b`
- name: `?AddSeparator@FileDialogBroker@Isolation@Security@Windows@@UEAAJK@Z`
- size: `107`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x140009ad0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x140009adf`: `FileDialogBroker::AddSeparator`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::AddSeparator(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v8, "FileDialogBroker::AddSeparator");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 80LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x643,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x140009ad0  mov     [rsp+arg_8], rbx
0x140009ad5  push    rdi
0x140009ad6  sub     rsp, 70h
0x140009ada  mov     ebx, edx
0x140009adc  mov     rdi, rcx
0x140009adf  lea     rdx, aFiledialogbrok_26; "FileDialogBroker::AddSeparator"
0x140009ae6  lea     rcx, [rsp+78h+var_58]
0x140009aeb  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x140009af0  nop
0x140009af1  lea     rcx, [rdi-30h]
0x140009af5  mov     rax, [rcx]
0x140009af8  mov     rax, [rax+50h]
0x140009afc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b01  mov     r8, rax
0x140009b04  mov     rcx, [rax]
0x140009b07  mov     rax, [rcx+50h]
0x140009b0b  mov     edx, ebx
0x140009b0d  mov     rcx, r8
0x140009b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b15  mov     ebx, eax
0x140009b17  lea     rcx, [rsp+78h+var_58]; this
0x140009b1c  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x140009b21  mov     eax, ebx
0x140009b23  jmp     short loc_140009B2C
0x140009b25  mov     eax, [rsp+78h+arg_0]
0x140009b2c  mov     rbx, [rsp+78h+arg_8]
0x140009b34  add     rsp, 70h
0x140009b38  pop     rdi
0x140009b39  retn
```
