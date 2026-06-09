# Windows::Security::Isolation::FileDialogBroker::ShouldEnableDarkMode(void)

- ea: `0x14000f4b0`
- end: `0x14000f509`
- name: `?ShouldEnableDarkMode@FileDialogBroker@Isolation@Security@Windows@@UEAAHXZ`
- size: `89`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000f4b0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000f4b9`: `FileDialogBroker::ShouldEnableDarkMode)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::ShouldEnableDarkMode(
        Windows::Security::Isolation::FileDialogBroker *this)
{
  __int64 v2; // rax
  unsigned int v3; // ebx
  __int64 result; // rax
  _BYTE v5[88]; // [rsp+20h] [rbp-58h] BYREF

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v5, (__int64)"FileDialogBroker::ShouldEnableDarkMode)");
  try
  {
    v2 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 224LL))(v2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v5);
    result = v3;
  }
  catch ( ... )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000f4b0  push    rbx
0x14000f4b2  sub     rsp, 70h
0x14000f4b6  mov     rbx, rcx
0x14000f4b9  lea     rdx, aFiledialogbrok_42; "FileDialogBroker::ShouldEnableDarkMode)"
0x14000f4c0  lea     rcx, [rsp+78h+var_58]
0x14000f4c5  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000f4ca  nop
0x14000f4cb  lea     rcx, [rbx-10h]
0x14000f4cf  mov     rax, [rcx]
0x14000f4d2  mov     rax, [rax+40h]
0x14000f4d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f4db  mov     rdx, rax
0x14000f4de  mov     rcx, [rax]
0x14000f4e1  mov     rax, [rcx+0E0h]
0x14000f4e8  mov     rcx, rdx
0x14000f4eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f4f0  mov     ebx, eax
0x14000f4f2  lea     rcx, [rsp+78h+var_58]; this
0x14000f4f7  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000f4fc  mov     eax, ebx
0x14000f4fe  jmp     short loc_14000F502
0x14000f500  xor     eax, eax
0x14000f502  add     rsp, 70h
0x14000f506  pop     rbx
0x14000f507  retn
```
