# Windows::Security::Isolation::FileDialogBroker::Close(long)

- ea: `0x14000a180`
- end: `0x14000a1ee`
- name: `?Close@FileDialogBroker@Isolation@Security@Windows@@UEAAJJ@Z`
- size: `110`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *this, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000a200`
- `0x14000a210`
- `0x14000a220`

## callees

- `0x140009194`
- `0x14000a180`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000a18f`: `FileDialogBroker::Close`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::Close(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v8, "FileDialogBroker::Close");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 1) + 56LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 184LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x363,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000a180  mov     [rsp+arg_8], rbx
0x14000a185  push    rdi
0x14000a186  sub     rsp, 70h
0x14000a18a  mov     ebx, edx
0x14000a18c  mov     rdi, rcx
0x14000a18f  lea     rdx, aFiledialogbrok_22; "FileDialogBroker::Close"
0x14000a196  lea     rcx, [rsp+78h+var_58]
0x14000a19b  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000a1a0  nop
0x14000a1a1  lea     rcx, [rdi-8]
0x14000a1a5  mov     rax, [rcx]
0x14000a1a8  mov     rax, [rax+38h]
0x14000a1ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a1b1  mov     r8, rax
0x14000a1b4  mov     rcx, [rax]
0x14000a1b7  mov     rax, [rcx+0B8h]
0x14000a1be  mov     edx, ebx
0x14000a1c0  mov     rcx, r8
0x14000a1c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a1c8  mov     ebx, eax
0x14000a1ca  lea     rcx, [rsp+78h+var_58]; this
0x14000a1cf  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000a1d4  mov     eax, ebx
0x14000a1d6  jmp     short loc_14000A1DF
0x14000a1d8  mov     eax, [rsp+78h+arg_0]
0x14000a1df  mov     rbx, [rsp+78h+arg_8]
0x14000a1e7  add     rsp, 70h
0x14000a1eb  pop     rdi
0x14000a1ec  retn
```
