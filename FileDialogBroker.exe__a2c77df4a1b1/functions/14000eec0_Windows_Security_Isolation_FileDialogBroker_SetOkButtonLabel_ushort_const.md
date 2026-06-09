# Windows::Security::Isolation::FileDialogBroker::SetOkButtonLabel(ushort const *)

- ea: `0x14000eec0`
- end: `0x14000ef30`
- name: `?SetOkButtonLabel@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEBG@Z`
- size: `112`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000ef40`
- `0x14000ef50`
- `0x14000ef60`

## callees

- `0x140009194`
- `0x14000eec0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000eed0`: `FileDialogBroker::SetOkButtonLabel`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetOkButtonLabel(
        Windows::Security::Isolation::FileDialogBroker *this,
        const unsigned __int16 *a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v8, (__int64)"FileDialogBroker::SetOkButtonLabel");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 1) + 56LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v4 + 144LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x310,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000eec0  mov     [rsp+arg_8], rbx
0x14000eec5  push    rdi
0x14000eec6  sub     rsp, 70h
0x14000eeca  mov     rbx, rdx
0x14000eecd  mov     rdi, rcx
0x14000eed0  lea     rdx, aFiledialogbrok_69; "FileDialogBroker::SetOkButtonLabel"
0x14000eed7  lea     rcx, [rsp+78h+var_58]
0x14000eedc  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000eee1  nop
0x14000eee2  lea     rcx, [rdi-8]
0x14000eee6  mov     rax, [rcx]
0x14000eee9  mov     rax, [rax+38h]
0x14000eeed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eef2  mov     r8, rax
0x14000eef5  mov     rcx, [rax]
0x14000eef8  mov     rax, [rcx+90h]
0x14000eeff  mov     rdx, rbx
0x14000ef02  mov     rcx, r8
0x14000ef05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ef0a  mov     ebx, eax
0x14000ef0c  lea     rcx, [rsp+78h+var_58]; this
0x14000ef11  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000ef16  mov     eax, ebx
0x14000ef18  jmp     short loc_14000EF21
0x14000ef1a  mov     eax, [rsp+78h+arg_0]
0x14000ef21  mov     rbx, [rsp+78h+arg_8]
0x14000ef29  add     rsp, 70h
0x14000ef2d  pop     rdi
0x14000ef2e  retn
```
