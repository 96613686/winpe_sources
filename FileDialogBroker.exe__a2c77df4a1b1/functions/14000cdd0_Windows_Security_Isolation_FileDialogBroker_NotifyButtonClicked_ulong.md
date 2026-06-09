# Windows::Security::Isolation::FileDialogBroker::NotifyButtonClicked(ulong)

- ea: `0x14000cdd0`
- end: `0x14000ce3e`
- name: `?NotifyButtonClicked@FileDialogBroker@Isolation@Security@Windows@@UEAAJK@Z`
- size: `110`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000cdd0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000cddf`: `FileDialogBroker::NotifyButtonClicked`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::NotifyButtonClicked(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v8, (__int64)"FileDialogBroker::NotifyButtonClicked");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 264LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3BF,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000cdd0  mov     [rsp+arg_8], rbx
0x14000cdd5  push    rdi
0x14000cdd6  sub     rsp, 70h
0x14000cdda  mov     ebx, edx
0x14000cddc  mov     rdi, rcx
0x14000cddf  lea     rdx, aFiledialogbrok_27; "FileDialogBroker::NotifyButtonClicked"
0x14000cde6  lea     rcx, [rsp+78h+var_58]
0x14000cdeb  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000cdf0  nop
0x14000cdf1  lea     rcx, [rdi-10h]
0x14000cdf5  mov     rax, [rcx]
0x14000cdf8  mov     rax, [rax+40h]
0x14000cdfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ce01  mov     r8, rax
0x14000ce04  mov     rcx, [rax]
0x14000ce07  mov     rax, [rcx+108h]
0x14000ce0e  mov     edx, ebx
0x14000ce10  mov     rcx, r8
0x14000ce13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ce18  mov     ebx, eax
0x14000ce1a  lea     rcx, [rsp+78h+var_58]; this
0x14000ce1f  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000ce24  mov     eax, ebx
0x14000ce26  jmp     short loc_14000CE2F
0x14000ce28  mov     eax, [rsp+78h+arg_0]
0x14000ce2f  mov     rbx, [rsp+78h+arg_8]
0x14000ce37  add     rsp, 70h
0x14000ce3b  pop     rdi
0x14000ce3c  retn
```
