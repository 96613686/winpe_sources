# Windows::Security::Isolation::FileDialogBroker::NeedLayout(void)

- ea: `0x14000cd60`
- end: `0x14000cdbe`
- name: `?NeedLayout@FileDialogBroker@Isolation@Security@Windows@@UEAAJXZ`
- size: `94`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000cd60`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000cd69`: `FileDialogBroker::NeedLayout`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::NeedLayout(
        Windows::Security::Isolation::FileDialogBroker *this)
{
  __int64 v2; // rax
  unsigned int v3; // ebx
  const char *v4; // r9
  __int64 result; // rax
  _BYTE v6[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v6, (__int64)"FileDialogBroker::NeedLayout");
  try
  {
    v2 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 288LL))(v2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v6);
    result = v3;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3DD,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x14000cd60  push    rbx
0x14000cd62  sub     rsp, 70h
0x14000cd66  mov     rbx, rcx
0x14000cd69  lea     rdx, aFiledialogbrok_50; "FileDialogBroker::NeedLayout"
0x14000cd70  lea     rcx, [rsp+78h+var_58]
0x14000cd75  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000cd7a  nop
0x14000cd7b  lea     rcx, [rbx-10h]
0x14000cd7f  mov     rax, [rcx]
0x14000cd82  mov     rax, [rax+40h]
0x14000cd86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cd8b  mov     rdx, rax
0x14000cd8e  mov     rcx, [rax]
0x14000cd91  mov     rax, [rcx+120h]
0x14000cd98  mov     rcx, rdx
0x14000cd9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cda0  mov     ebx, eax
0x14000cda2  lea     rcx, [rsp+78h+var_58]; this
0x14000cda7  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000cdac  mov     eax, ebx
0x14000cdae  jmp     short loc_14000CDB7
0x14000cdb0  mov     eax, [rsp+78h+arg_0]
0x14000cdb7  add     rsp, 70h
0x14000cdbb  pop     rbx
0x14000cdbc  retn
```
