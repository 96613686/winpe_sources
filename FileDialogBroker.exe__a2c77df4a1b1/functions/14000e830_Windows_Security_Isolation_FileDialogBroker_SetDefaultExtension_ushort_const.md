# Windows::Security::Isolation::FileDialogBroker::SetDefaultExtension(ushort const *)

- ea: `0x14000e830`
- end: `0x14000e8a0`
- name: `?SetDefaultExtension@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEBG@Z`
- size: `112`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000e8b0`
- `0x14000e8c0`
- `0x14000e8d0`

## callees

- `0x140009194`
- `0x14000e830`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000e840`: `FileDialogBroker::SetDefaultExtension`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetDefaultExtension(
        Windows::Security::Isolation::FileDialogBroker *this,
        const unsigned __int16 *a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v8, (__int64)"FileDialogBroker::SetDefaultExtension");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 1) + 56LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v4 + 176LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x359,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000e830  mov     [rsp+arg_8], rbx
0x14000e835  push    rdi
0x14000e836  sub     rsp, 70h
0x14000e83a  mov     rbx, rdx
0x14000e83d  mov     rdi, rcx
0x14000e840  lea     rdx, aFiledialogbrok_89; "FileDialogBroker::SetDefaultExtension"
0x14000e847  lea     rcx, [rsp+78h+var_58]
0x14000e84c  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000e851  nop
0x14000e852  lea     rcx, [rdi-8]
0x14000e856  mov     rax, [rcx]
0x14000e859  mov     rax, [rax+38h]
0x14000e85d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e862  mov     r8, rax
0x14000e865  mov     rcx, [rax]
0x14000e868  mov     rax, [rcx+0B0h]
0x14000e86f  mov     rdx, rbx
0x14000e872  mov     rcx, r8
0x14000e875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e87a  mov     ebx, eax
0x14000e87c  lea     rcx, [rsp+78h+var_58]; this
0x14000e881  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000e886  mov     eax, ebx
0x14000e888  jmp     short loc_14000E891
0x14000e88a  mov     eax, [rsp+78h+arg_0]
0x14000e891  mov     rbx, [rsp+78h+arg_8]
0x14000e899  add     rsp, 70h
0x14000e89d  pop     rdi
0x14000e89e  retn
```
