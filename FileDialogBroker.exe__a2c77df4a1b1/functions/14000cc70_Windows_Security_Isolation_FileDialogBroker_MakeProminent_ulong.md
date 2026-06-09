# Windows::Security::Isolation::FileDialogBroker::MakeProminent(ulong)

- ea: `0x14000cc70`
- end: `0x14000ccde`
- name: `?MakeProminent@FileDialogBroker@Isolation@Security@Windows@@UEAAJK@Z`
- size: `110`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000cc70`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000cc7f`: `FileDialogBroker::MakeProminent`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::MakeProminent(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v8, (__int64)"FileDialogBroker::MakeProminent");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 224LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x6F7,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000cc70  mov     [rsp+arg_8], rbx
0x14000cc75  push    rdi
0x14000cc76  sub     rsp, 70h
0x14000cc7a  mov     ebx, edx
0x14000cc7c  mov     rdi, rcx
0x14000cc7f  lea     rdx, aFiledialogbrok_43; "FileDialogBroker::MakeProminent"
0x14000cc86  lea     rcx, [rsp+78h+var_58]
0x14000cc8b  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000cc90  nop
0x14000cc91  lea     rcx, [rdi-30h]
0x14000cc95  mov     rax, [rcx]
0x14000cc98  mov     rax, [rax+50h]
0x14000cc9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cca1  mov     r8, rax
0x14000cca4  mov     rcx, [rax]
0x14000cca7  mov     rax, [rcx+0E0h]
0x14000ccae  mov     edx, ebx
0x14000ccb0  mov     rcx, r8
0x14000ccb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ccb8  mov     ebx, eax
0x14000ccba  lea     rcx, [rsp+78h+var_58]; this
0x14000ccbf  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000ccc4  mov     eax, ebx
0x14000ccc6  jmp     short loc_14000CCCF
0x14000ccc8  mov     eax, [rsp+78h+arg_0]
0x14000cccf  mov     rbx, [rsp+78h+arg_8]
0x14000ccd7  add     rsp, 70h
0x14000ccdb  pop     rdi
0x14000ccdc  retn
```
