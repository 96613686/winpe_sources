# Windows::Security::Isolation::FileDialogBroker::PopulateFileNameCombo(HWND__ *)

- ea: `0x14000d070`
- end: `0x14000d0e0`
- name: `?PopulateFileNameCombo@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAUHWND__@@@Z`
- size: `112`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000d070`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000d080`: `FileDialogBroker::PopulateFileNameCombo`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::PopulateFileNameCombo(
        Windows::Security::Isolation::FileDialogBroker *this,
        HWND a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v8, (__int64)"FileDialogBroker::PopulateFileNameCombo");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, HWND))(*(_QWORD *)v4 + 328LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x40F,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000d070  mov     [rsp+arg_8], rbx
0x14000d075  push    rdi
0x14000d076  sub     rsp, 70h
0x14000d07a  mov     rbx, rdx
0x14000d07d  mov     rdi, rcx
0x14000d080  lea     rdx, aFiledialogbrok_8; "FileDialogBroker::PopulateFileNameCombo"
0x14000d087  lea     rcx, [rsp+78h+var_58]
0x14000d08c  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000d091  nop
0x14000d092  lea     rcx, [rdi-10h]
0x14000d096  mov     rax, [rcx]
0x14000d099  mov     rax, [rax+40h]
0x14000d09d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d0a2  mov     r8, rax
0x14000d0a5  mov     rcx, [rax]
0x14000d0a8  mov     rax, [rcx+148h]
0x14000d0af  mov     rdx, rbx
0x14000d0b2  mov     rcx, r8
0x14000d0b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d0ba  mov     ebx, eax
0x14000d0bc  lea     rcx, [rsp+78h+var_58]; this
0x14000d0c1  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000d0c6  mov     eax, ebx
0x14000d0c8  jmp     short loc_14000D0D1
0x14000d0ca  mov     eax, [rsp+78h+arg_0]
0x14000d0d1  mov     rbx, [rsp+78h+arg_8]
0x14000d0d9  add     rsp, 70h
0x14000d0dd  pop     rdi
0x14000d0de  retn
```
