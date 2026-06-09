# Windows::Security::Isolation::FileDialogBroker::SetFileTypeIndex(uint)

- ea: `0x14000eb80`
- end: `0x14000ebeb`
- name: `?SetFileTypeIndex@FileDialogBroker@Isolation@Security@Windows@@UEAAJI@Z`
- size: `107`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000ec00`
- `0x14000ec10`
- `0x14000ec20`

## callees

- `0x140009194`
- `0x14000eb80`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000eb8f`: `FileDialogBroker::SetFileTypeIndex`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetFileTypeIndex(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v8, (__int64)"FileDialogBroker::SetFileTypeIndex");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 1) + 56LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 40LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x27D,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000eb80  mov     [rsp+arg_8], rbx
0x14000eb85  push    rdi
0x14000eb86  sub     rsp, 70h
0x14000eb8a  mov     ebx, edx
0x14000eb8c  mov     rdi, rcx
0x14000eb8f  lea     rdx, aFiledialogbrok_57; "FileDialogBroker::SetFileTypeIndex"
0x14000eb96  lea     rcx, [rsp+78h+var_58]
0x14000eb9b  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000eba0  nop
0x14000eba1  lea     rcx, [rdi-8]
0x14000eba5  mov     rax, [rcx]
0x14000eba8  mov     rax, [rax+38h]
0x14000ebac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ebb1  mov     r8, rax
0x14000ebb4  mov     rcx, [rax]
0x14000ebb7  mov     rax, [rcx+28h]
0x14000ebbb  mov     edx, ebx
0x14000ebbd  mov     rcx, r8
0x14000ebc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ebc5  mov     ebx, eax
0x14000ebc7  lea     rcx, [rsp+78h+var_58]; this
0x14000ebcc  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000ebd1  mov     eax, ebx
0x14000ebd3  jmp     short loc_14000EBDC
0x14000ebd5  mov     eax, [rsp+78h+arg_0]
0x14000ebdc  mov     rbx, [rsp+78h+arg_8]
0x14000ebe4  add     rsp, 70h
0x14000ebe8  pop     rdi
0x14000ebe9  retn
```
