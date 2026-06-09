# Windows::Security::Isolation::FileDialogBroker::RemoveAllControlItems(ulong)

- ea: `0x14000dc70`
- end: `0x14000dcde`
- name: `?RemoveAllControlItems@FileDialogBroker@Isolation@Security@Windows@@UEAAJK@Z`
- size: `110`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000dc70`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000dc7f`: `FileDialogBroker::RemoveAllControlItems`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::RemoveAllControlItems(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v8, (__int64)"FileDialogBroker::RemoveAllControlItems");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 168LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x6B1,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000dc70  mov     [rsp+arg_8], rbx
0x14000dc75  push    rdi
0x14000dc76  sub     rsp, 70h
0x14000dc7a  mov     ebx, edx
0x14000dc7c  mov     rdi, rcx
0x14000dc7f  lea     rdx, aFiledialogbrok_41; "FileDialogBroker::RemoveAllControlItems"
0x14000dc86  lea     rcx, [rsp+78h+var_58]
0x14000dc8b  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000dc90  nop
0x14000dc91  lea     rcx, [rdi-30h]
0x14000dc95  mov     rax, [rcx]
0x14000dc98  mov     rax, [rax+50h]
0x14000dc9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dca1  mov     r8, rax
0x14000dca4  mov     rcx, [rax]
0x14000dca7  mov     rax, [rcx+0A8h]
0x14000dcae  mov     edx, ebx
0x14000dcb0  mov     rcx, r8
0x14000dcb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dcb8  mov     ebx, eax
0x14000dcba  lea     rcx, [rsp+78h+var_58]; this
0x14000dcbf  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000dcc4  mov     eax, ebx
0x14000dcc6  jmp     short loc_14000DCCF
0x14000dcc8  mov     eax, [rsp+78h+arg_0]
0x14000dccf  mov     rbx, [rsp+78h+arg_8]
0x14000dcd7  add     rsp, 70h
0x14000dcdb  pop     rdi
0x14000dcdc  retn
```
