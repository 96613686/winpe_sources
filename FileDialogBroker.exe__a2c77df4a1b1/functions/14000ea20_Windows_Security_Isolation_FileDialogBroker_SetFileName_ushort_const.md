# Windows::Security::Isolation::FileDialogBroker::SetFileName(ushort const *)

- ea: `0x14000ea20`
- end: `0x14000ea8d`
- name: `?SetFileName@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEBG@Z`
- size: `109`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000eaa0`
- `0x14000eab0`
- `0x14000eac0`

## callees

- `0x140009194`
- `0x14000ea20`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000ea30`: `FileDialogBroker::SetFileName`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetFileName(
        Windows::Security::Isolation::FileDialogBroker *this,
        const unsigned __int16 *a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v8, (__int64)"FileDialogBroker::SetFileName");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 1) + 56LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v4 + 120LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2F2,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000ea20  mov     [rsp+arg_8], rbx
0x14000ea25  push    rdi
0x14000ea26  sub     rsp, 70h
0x14000ea2a  mov     rbx, rdx
0x14000ea2d  mov     rdi, rcx
0x14000ea30  lea     rdx, aFiledialogbrok_46; "FileDialogBroker::SetFileName"
0x14000ea37  lea     rcx, [rsp+78h+var_58]
0x14000ea3c  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000ea41  nop
0x14000ea42  lea     rcx, [rdi-8]
0x14000ea46  mov     rax, [rcx]
0x14000ea49  mov     rax, [rax+38h]
0x14000ea4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ea52  mov     r8, rax
0x14000ea55  mov     rcx, [rax]
0x14000ea58  mov     rax, [rcx+78h]
0x14000ea5c  mov     rdx, rbx
0x14000ea5f  mov     rcx, r8
0x14000ea62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ea67  mov     ebx, eax
0x14000ea69  lea     rcx, [rsp+78h+var_58]; this
0x14000ea6e  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000ea73  mov     eax, ebx
0x14000ea75  jmp     short loc_14000EA7E
0x14000ea77  mov     eax, [rsp+78h+arg_0]
0x14000ea7e  mov     rbx, [rsp+78h+arg_8]
0x14000ea86  add     rsp, 70h
0x14000ea8a  pop     rdi
0x14000ea8b  retn
```
