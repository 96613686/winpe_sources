# Windows::Security::Isolation::FileDialogBroker::GetOptions(ulong *)

- ea: `0x14000c020`
- end: `0x14000c08d`
- name: `?GetOptions@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAK@Z`
- size: `109`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000c0a0`
- `0x14000c0b0`
- `0x14000c0c0`

## callees

- `0x140009194`
- `0x14000c020`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000c030`: `FileDialogBroker::GetOptions`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetOptions(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int *a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v8, "FileDialogBroker::GetOptions");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 1) + 56LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 80LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2C0,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000c020  mov     [rsp+arg_8], rbx
0x14000c025  push    rdi
0x14000c026  sub     rsp, 70h
0x14000c02a  mov     rbx, rdx
0x14000c02d  mov     rdi, rcx
0x14000c030  lea     rdx, aFiledialogbrok_78; "FileDialogBroker::GetOptions"
0x14000c037  lea     rcx, [rsp+78h+var_58]
0x14000c03c  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000c041  nop
0x14000c042  lea     rcx, [rdi-8]
0x14000c046  mov     rax, [rcx]
0x14000c049  mov     rax, [rax+38h]
0x14000c04d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c052  mov     r8, rax
0x14000c055  mov     rcx, [rax]
0x14000c058  mov     rax, [rcx+50h]
0x14000c05c  mov     rdx, rbx
0x14000c05f  mov     rcx, r8
0x14000c062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c067  mov     ebx, eax
0x14000c069  lea     rcx, [rsp+78h+var_58]; this
0x14000c06e  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000c073  mov     eax, ebx
0x14000c075  jmp     short loc_14000C07E
0x14000c077  mov     eax, [rsp+78h+arg_0]
0x14000c07e  mov     rbx, [rsp+78h+arg_8]
0x14000c086  add     rsp, 70h
0x14000c08a  pop     rdi
0x14000c08b  retn
```
