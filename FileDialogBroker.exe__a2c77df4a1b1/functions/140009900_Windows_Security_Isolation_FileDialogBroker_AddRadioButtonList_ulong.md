# Windows::Security::Isolation::FileDialogBroker::AddRadioButtonList(ulong)

- ea: `0x140009900`
- end: `0x14000996b`
- name: `?AddRadioButtonList@FileDialogBroker@Isolation@Security@Windows@@UEAAJK@Z`
- size: `107`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x140009900`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000990f`: `FileDialogBroker::AddRadioButtonList`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::AddRadioButtonList(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v8, "FileDialogBroker::AddRadioButtonList");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 56LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x625,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x140009900  mov     [rsp+arg_8], rbx
0x140009905  push    rdi
0x140009906  sub     rsp, 70h
0x14000990a  mov     ebx, edx
0x14000990c  mov     rdi, rcx
0x14000990f  lea     rdx, aFiledialogbrok_83; "FileDialogBroker::AddRadioButtonList"
0x140009916  lea     rcx, [rsp+78h+var_58]
0x14000991b  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x140009920  nop
0x140009921  lea     rcx, [rdi-30h]
0x140009925  mov     rax, [rcx]
0x140009928  mov     rax, [rax+50h]
0x14000992c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009931  mov     r8, rax
0x140009934  mov     rcx, [rax]
0x140009937  mov     rax, [rcx+38h]
0x14000993b  mov     edx, ebx
0x14000993d  mov     rcx, r8
0x140009940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009945  mov     ebx, eax
0x140009947  lea     rcx, [rsp+78h+var_58]; this
0x14000994c  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x140009951  mov     eax, ebx
0x140009953  jmp     short loc_14000995C
0x140009955  mov     eax, [rsp+78h+arg_0]
0x14000995c  mov     rbx, [rsp+78h+arg_8]
0x140009964  add     rsp, 70h
0x140009968  pop     rdi
0x140009969  retn
```
