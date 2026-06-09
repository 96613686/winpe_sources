# Windows::Security::Isolation::FileDialogBroker::Unadvise(ulong)

- ea: `0x14000f820`
- end: `0x14000f88b`
- name: `?Unadvise@FileDialogBroker@Isolation@Security@Windows@@UEAAJK@Z`
- size: `107`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000f8a0`
- `0x14000f8b0`
- `0x14000f8c0`

## callees

- `0x140009194`
- `0x14000f820`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000f82f`: `FileDialogBroker::Unadvise`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::Unadvise(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v8, (__int64)"FileDialogBroker::Unadvise");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 1) + 56LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 64LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2AC,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000f820  mov     [rsp+arg_8], rbx
0x14000f825  push    rdi
0x14000f826  sub     rsp, 70h
0x14000f82a  mov     ebx, edx
0x14000f82c  mov     rdi, rcx
0x14000f82f  lea     rdx, aFiledialogbrok_58; "FileDialogBroker::Unadvise"
0x14000f836  lea     rcx, [rsp+78h+var_58]
0x14000f83b  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000f840  nop
0x14000f841  lea     rcx, [rdi-8]
0x14000f845  mov     rax, [rcx]
0x14000f848  mov     rax, [rax+38h]
0x14000f84c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f851  mov     r8, rax
0x14000f854  mov     rcx, [rax]
0x14000f857  mov     rax, [rcx+40h]
0x14000f85b  mov     edx, ebx
0x14000f85d  mov     rcx, r8
0x14000f860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f865  mov     ebx, eax
0x14000f867  lea     rcx, [rsp+78h+var_58]; this
0x14000f86c  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000f871  mov     eax, ebx
0x14000f873  jmp     short loc_14000F87C
0x14000f875  mov     eax, [rsp+78h+arg_0]
0x14000f87c  mov     rbx, [rsp+78h+arg_8]
0x14000f884  add     rsp, 70h
0x14000f888  pop     rdi
0x14000f889  retn
```
