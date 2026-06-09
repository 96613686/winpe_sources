# Windows::Security::Isolation::FileDialogBroker::Show(HWND__ *)

- ea: `0x14000f5e0`
- end: `0x14000f64c`
- name: `?Show@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAUHWND__@@@Z`
- size: `108`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, HWND)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000f660`
- `0x14000f670`
- `0x14000f680`
- `0x14000f690`

## callees

- `0x140009194`
- `0x14000f5e0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000f5f0`: `FileDialogBroker::Show`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::Show(
        Windows::Security::Isolation::FileDialogBroker *this,
        HWND a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v8, "FileDialogBroker::Show");
  try
  {
    v4 = (*(__int64 (**)(void))(*(_QWORD *)this + 56LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, HWND))(*(_QWORD *)v4 + 24LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x345,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000f5e0  mov     [rsp+arg_8], rbx
0x14000f5e5  push    rdi
0x14000f5e6  sub     rsp, 70h
0x14000f5ea  mov     rdi, rdx
0x14000f5ed  mov     rbx, rcx
0x14000f5f0  lea     rdx, aFiledialogbrok_33; "FileDialogBroker::Show"
0x14000f5f7  lea     rcx, [rsp+78h+var_58]
0x14000f5fc  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000f601  nop
0x14000f602  mov     rax, [rbx]
0x14000f605  mov     rcx, rbx
0x14000f608  mov     rax, [rax+38h]
0x14000f60c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f611  mov     r8, rax
0x14000f614  mov     rcx, [rax]
0x14000f617  mov     rax, [rcx+18h]
0x14000f61b  mov     rdx, rdi
0x14000f61e  mov     rcx, r8
0x14000f621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f626  mov     ebx, eax
0x14000f628  lea     rcx, [rsp+78h+var_58]; this
0x14000f62d  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000f632  mov     eax, ebx
0x14000f634  jmp     short loc_14000F63D
0x14000f636  mov     eax, [rsp+78h+arg_0]
0x14000f63d  mov     rbx, [rsp+78h+arg_8]
0x14000f645  add     rsp, 70h
0x14000f649  pop     rdi
0x14000f64a  retn
```
