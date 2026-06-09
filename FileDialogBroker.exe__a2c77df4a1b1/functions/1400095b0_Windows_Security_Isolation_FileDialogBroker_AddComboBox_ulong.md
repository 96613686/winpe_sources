# Windows::Security::Isolation::FileDialogBroker::AddComboBox(ulong)

- ea: `0x1400095b0`
- end: `0x14000961b`
- name: `?AddComboBox@FileDialogBroker@Isolation@Security@Windows@@UEAAJK@Z`
- size: `107`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x1400095b0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x1400095bf`: `FileDialogBroker::AddComboBox`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::AddComboBox(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v8, "FileDialogBroker::AddComboBox");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 48LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x61B,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x1400095b0  mov     [rsp+arg_8], rbx
0x1400095b5  push    rdi
0x1400095b6  sub     rsp, 70h
0x1400095ba  mov     ebx, edx
0x1400095bc  mov     rdi, rcx
0x1400095bf  lea     rdx, aFiledialogbrok_80; "FileDialogBroker::AddComboBox"
0x1400095c6  lea     rcx, [rsp+78h+var_58]
0x1400095cb  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x1400095d0  nop
0x1400095d1  lea     rcx, [rdi-30h]
0x1400095d5  mov     rax, [rcx]
0x1400095d8  mov     rax, [rax+50h]
0x1400095dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400095e1  mov     r8, rax
0x1400095e4  mov     rcx, [rax]
0x1400095e7  mov     rax, [rcx+30h]
0x1400095eb  mov     edx, ebx
0x1400095ed  mov     rcx, r8
0x1400095f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400095f5  mov     ebx, eax
0x1400095f7  lea     rcx, [rsp+78h+var_58]; this
0x1400095fc  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x140009601  mov     eax, ebx
0x140009603  jmp     short loc_14000960C
0x140009605  mov     eax, [rsp+78h+arg_0]
0x14000960c  mov     rbx, [rsp+78h+arg_8]
0x140009614  add     rsp, 70h
0x140009618  pop     rdi
0x140009619  retn
```
