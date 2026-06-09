# Windows::Security::Isolation::FileDialogBroker::SetOptions(ulong)

- ea: `0x14000ef70`
- end: `0x14000efdb`
- name: `?SetOptions@FileDialogBroker@Isolation@Security@Windows@@UEAAJK@Z`
- size: `107`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000eff0`
- `0x14000f000`
- `0x14000f010`

## callees

- `0x140009194`
- `0x14000ef70`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000ef7f`: `FileDialogBroker::SetOptions`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetOptions(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v8, (__int64)"FileDialogBroker::SetOptions");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 1) + 56LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 72LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2B6,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000ef70  mov     [rsp+arg_8], rbx
0x14000ef75  push    rdi
0x14000ef76  sub     rsp, 70h
0x14000ef7a  mov     ebx, edx
0x14000ef7c  mov     rdi, rcx
0x14000ef7f  lea     rdx, aFiledialogbrok_30; "FileDialogBroker::SetOptions"
0x14000ef86  lea     rcx, [rsp+78h+var_58]
0x14000ef8b  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000ef90  nop
0x14000ef91  lea     rcx, [rdi-8]
0x14000ef95  mov     rax, [rcx]
0x14000ef98  mov     rax, [rax+38h]
0x14000ef9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000efa1  mov     r8, rax
0x14000efa4  mov     rcx, [rax]
0x14000efa7  mov     rax, [rcx+48h]
0x14000efab  mov     edx, ebx
0x14000efad  mov     rcx, r8
0x14000efb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000efb5  mov     ebx, eax
0x14000efb7  lea     rcx, [rsp+78h+var_58]; this
0x14000efbc  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000efc1  mov     eax, ebx
0x14000efc3  jmp     short loc_14000EFCC
0x14000efc5  mov     eax, [rsp+78h+arg_0]
0x14000efcc  mov     rbx, [rsp+78h+arg_8]
0x14000efd4  add     rsp, 70h
0x14000efd8  pop     rdi
0x14000efd9  retn
```
