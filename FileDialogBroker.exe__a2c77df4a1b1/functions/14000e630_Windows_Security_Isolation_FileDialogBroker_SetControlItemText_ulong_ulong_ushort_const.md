# Windows::Security::Isolation::FileDialogBroker::SetControlItemText(ulong,ulong,ushort const *)

- ea: `0x14000e630`
- end: `0x14000e6ae`
- name: `?SetControlItemText@FileDialogBroker@Isolation@Security@Windows@@UEAAJKKPEBG@Z`
- size: `126`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000e630`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000e649`: `FileDialogBroker::SetControlItemText`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetControlItemText(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2,
        unsigned int a3,
        const unsigned __int16 *a4)
{
  __int64 v8; // rax
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 result; // rax
  _BYTE v12[120]; // [rsp+30h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v12, (__int64)"FileDialogBroker::SetControlItemText");
  try
  {
    v8 = (*(__int64 (**)(void))(*((_QWORD *)this - 6) + 80LL))();
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, const unsigned __int16 *))(*(_QWORD *)v8 + 232LL))(
           v8,
           a2,
           a3,
           a4);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v12);
    result = v9;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x701,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x14000e630  push    rbx
0x14000e632  push    rsi
0x14000e633  push    rdi
0x14000e634  push    r14
0x14000e636  sub     rsp, 88h
0x14000e63d  mov     rdi, r9
0x14000e640  mov     esi, r8d
0x14000e643  mov     r14d, edx
0x14000e646  mov     rbx, rcx
0x14000e649  lea     rdx, aFiledialogbrok_79; "FileDialogBroker::SetControlItemText"
0x14000e650  lea     rcx, [rsp+0A8h+var_78]
0x14000e655  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000e65a  nop
0x14000e65b  lea     rcx, [rbx-30h]
0x14000e65f  mov     rax, [rcx]
0x14000e662  mov     rax, [rax+50h]
0x14000e666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e66b  mov     r10, rax
0x14000e66e  mov     rcx, [rax]
0x14000e671  mov     rax, [rcx+0E8h]
0x14000e678  mov     r9, rdi
0x14000e67b  mov     r8d, esi
0x14000e67e  mov     edx, r14d
0x14000e681  mov     rcx, r10
0x14000e684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e689  mov     ebx, eax
0x14000e68b  lea     rcx, [rsp+0A8h+var_78]; this
0x14000e690  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000e695  mov     eax, ebx
0x14000e697  jmp     short loc_14000E6A0
0x14000e699  mov     eax, [rsp+0A8h+arg_0]
0x14000e6a0  add     rsp, 88h
0x14000e6a7  pop     r14
0x14000e6a9  pop     rdi
0x14000e6aa  pop     rsi
0x14000e6ab  pop     rbx
0x14000e6ac  retn
```
