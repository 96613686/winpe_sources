# Windows::Security::Isolation::FileDialogBroker::NotifyControlActivating(ulong)

- ea: `0x14000cee0`
- end: `0x14000cf4e`
- name: `?NotifyControlActivating@FileDialogBroker@Isolation@Security@Windows@@UEAAJK@Z`
- size: `110`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000cee0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000ceef`: `FileDialogBroker::NotifyControlActivating`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::NotifyControlActivating(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v8, (__int64)"FileDialogBroker::NotifyControlActivating");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 280LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3D3,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000cee0  mov     [rsp+arg_8], rbx
0x14000cee5  push    rdi
0x14000cee6  sub     rsp, 70h
0x14000ceea  mov     ebx, edx
0x14000ceec  mov     rdi, rcx
0x14000ceef  lea     rdx, aFiledialogbrok_87; "FileDialogBroker::NotifyControlActivati"...
0x14000cef6  lea     rcx, [rsp+78h+var_58]
0x14000cefb  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000cf00  nop
0x14000cf01  lea     rcx, [rdi-10h]
0x14000cf05  mov     rax, [rcx]
0x14000cf08  mov     rax, [rax+40h]
0x14000cf0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cf11  mov     r8, rax
0x14000cf14  mov     rcx, [rax]
0x14000cf17  mov     rax, [rcx+118h]
0x14000cf1e  mov     edx, ebx
0x14000cf20  mov     rcx, r8
0x14000cf23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cf28  mov     ebx, eax
0x14000cf2a  lea     rcx, [rsp+78h+var_58]; this
0x14000cf2f  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000cf34  mov     eax, ebx
0x14000cf36  jmp     short loc_14000CF3F
0x14000cf38  mov     eax, [rsp+78h+arg_0]
0x14000cf3f  mov     rbx, [rsp+78h+arg_8]
0x14000cf47  add     rsp, 70h
0x14000cf4b  pop     rdi
0x14000cf4c  retn
```
