# Windows::Security::Isolation::FileDialogBroker::SetControlItemState(ulong,ulong,CDCONTROLSTATEF)

- ea: `0x14000e5a0`
- end: `0x14000e61e`
- name: `?SetControlItemState@FileDialogBroker@Isolation@Security@Windows@@UEAAJKKW4CDCONTROLSTATEF@@@Z`
- size: `126`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int, unsigned int, enum CDCONTROLSTATEF)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000e5a0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000e5b9`: `FileDialogBroker::SetControlItemState`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetControlItemState(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  __int64 v8; // rax
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 result; // rax
  _BYTE v12[120]; // [rsp+30h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v12, (__int64)"FileDialogBroker::SetControlItemState");
  try
  {
    v8 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v8 + 184LL))(v8, a2, a3, a4);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v12);
    result = v9;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x6C5,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x14000e5a0  push    rbx
0x14000e5a2  push    rsi
0x14000e5a3  push    rdi
0x14000e5a4  push    r14
0x14000e5a6  sub     rsp, 88h
0x14000e5ad  mov     edi, r9d
0x14000e5b0  mov     esi, r8d
0x14000e5b3  mov     r14d, edx
0x14000e5b6  mov     rbx, rcx
0x14000e5b9  lea     rdx, aFiledialogbrok_54; "FileDialogBroker::SetControlItemState"
0x14000e5c0  lea     rcx, [rsp+0A8h+var_78]
0x14000e5c5  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000e5ca  nop
0x14000e5cb  lea     rcx, [rbx-30h]
0x14000e5cf  mov     rax, [rcx]
0x14000e5d2  mov     rax, [rax+50h]
0x14000e5d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e5db  mov     r10, rax
0x14000e5de  mov     rcx, [rax]
0x14000e5e1  mov     rax, [rcx+0B8h]
0x14000e5e8  mov     r9d, edi
0x14000e5eb  mov     r8d, esi
0x14000e5ee  mov     edx, r14d
0x14000e5f1  mov     rcx, r10
0x14000e5f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e5f9  mov     ebx, eax
0x14000e5fb  lea     rcx, [rsp+0A8h+var_78]; this
0x14000e600  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000e605  mov     eax, ebx
0x14000e607  jmp     short loc_14000E610
0x14000e609  mov     eax, [rsp+0A8h+arg_0]
0x14000e610  add     rsp, 88h
0x14000e617  pop     r14
0x14000e619  pop     rdi
0x14000e61a  pop     rsi
0x14000e61b  pop     rbx
0x14000e61c  retn
```
