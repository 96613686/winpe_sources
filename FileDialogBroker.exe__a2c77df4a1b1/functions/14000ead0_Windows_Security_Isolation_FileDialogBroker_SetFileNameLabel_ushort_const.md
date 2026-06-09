# Windows::Security::Isolation::FileDialogBroker::SetFileNameLabel(ushort const *)

- ea: `0x14000ead0`
- end: `0x14000eb40`
- name: `?SetFileNameLabel@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEBG@Z`
- size: `112`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000eb50`
- `0x14000eb60`
- `0x14000eb70`

## callees

- `0x140009194`
- `0x14000ead0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000eae0`: `FileDialogBroker::SetFileNameLabel`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetFileNameLabel(
        Windows::Security::Isolation::FileDialogBroker *this,
        const unsigned __int16 *a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v8, (__int64)"FileDialogBroker::SetFileNameLabel");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 1) + 56LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v4 + 152LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x31A,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000ead0  mov     [rsp+arg_8], rbx
0x14000ead5  push    rdi
0x14000ead6  sub     rsp, 70h
0x14000eada  mov     rbx, rdx
0x14000eadd  mov     rdi, rcx
0x14000eae0  lea     rdx, aFiledialogbrok_34; "FileDialogBroker::SetFileNameLabel"
0x14000eae7  lea     rcx, [rsp+78h+var_58]
0x14000eaec  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000eaf1  nop
0x14000eaf2  lea     rcx, [rdi-8]
0x14000eaf6  mov     rax, [rcx]
0x14000eaf9  mov     rax, [rax+38h]
0x14000eafd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eb02  mov     r8, rax
0x14000eb05  mov     rcx, [rax]
0x14000eb08  mov     rax, [rcx+98h]
0x14000eb0f  mov     rdx, rbx
0x14000eb12  mov     rcx, r8
0x14000eb15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eb1a  mov     ebx, eax
0x14000eb1c  lea     rcx, [rsp+78h+var_58]; this
0x14000eb21  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000eb26  mov     eax, ebx
0x14000eb28  jmp     short loc_14000EB31
0x14000eb2a  mov     eax, [rsp+78h+arg_0]
0x14000eb31  mov     rbx, [rsp+78h+arg_8]
0x14000eb39  add     rsp, 70h
0x14000eb3d  pop     rdi
0x14000eb3e  retn
```
