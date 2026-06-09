# Windows::Security::Isolation::FileDialogBroker::SetClientGuid(_GUID const &)

- ea: `0x14000e440`
- end: `0x14000e4b0`
- name: `?SetClientGuid@FileDialogBroker@Isolation@Security@Windows@@UEAAJAEBU_GUID@@@Z`
- size: `112`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, const struct _GUID *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000e4c0`
- `0x14000e4d0`
- `0x14000e4e0`

## callees

- `0x140009194`
- `0x14000e440`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000e450`: `FileDialogBroker::SetClientGuid`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetClientGuid(
        Windows::Security::Isolation::FileDialogBroker *this,
        const struct _GUID *a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v8, (__int64)"FileDialogBroker::SetClientGuid");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 1) + 56LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *))(*(_QWORD *)v4 + 192LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x36D,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000e440  mov     [rsp+arg_8], rbx
0x14000e445  push    rdi
0x14000e446  sub     rsp, 70h
0x14000e44a  mov     rbx, rdx
0x14000e44d  mov     rdi, rcx
0x14000e450  lea     rdx, aFiledialogbrok_66; "FileDialogBroker::SetClientGuid"
0x14000e457  lea     rcx, [rsp+78h+var_58]
0x14000e45c  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000e461  nop
0x14000e462  lea     rcx, [rdi-8]
0x14000e466  mov     rax, [rcx]
0x14000e469  mov     rax, [rax+38h]
0x14000e46d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e472  mov     r8, rax
0x14000e475  mov     rcx, [rax]
0x14000e478  mov     rax, [rcx+0C0h]
0x14000e47f  mov     rdx, rbx
0x14000e482  mov     rcx, r8
0x14000e485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e48a  mov     ebx, eax
0x14000e48c  lea     rcx, [rsp+78h+var_58]; this
0x14000e491  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000e496  mov     eax, ebx
0x14000e498  jmp     short loc_14000E4A1
0x14000e49a  mov     eax, [rsp+78h+arg_0]
0x14000e4a1  mov     rbx, [rsp+78h+arg_8]
0x14000e4a9  add     rsp, 70h
0x14000e4ad  pop     rdi
0x14000e4ae  retn
```
