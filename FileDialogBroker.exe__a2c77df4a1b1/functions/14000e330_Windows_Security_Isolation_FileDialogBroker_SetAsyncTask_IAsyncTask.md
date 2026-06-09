# Windows::Security::Isolation::FileDialogBroker::SetAsyncTask(IAsyncTask *)

- ea: `0x14000e330`
- end: `0x14000e3a0`
- name: `?SetAsyncTask@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAUIAsyncTask@@@Z`
- size: `112`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, struct IAsyncTask *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x140009194`
- `0x14000e330`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000e340`: `FileDialogBroker::SetAsyncTask`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::SetAsyncTask(
        Windows::Security::Isolation::FileDialogBroker *this,
        struct IAsyncTask *a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  _BYTE v8[88]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v8, (__int64)"FileDialogBroker::SetAsyncTask");
  try
  {
    v4 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    v5 = (*(__int64 (__fastcall **)(__int64, struct IAsyncTask *))(*(_QWORD *)v4 + 360LL))(v4, a2);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x437,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x14000e330  mov     [rsp+arg_8], rbx
0x14000e335  push    rdi
0x14000e336  sub     rsp, 70h
0x14000e33a  mov     rbx, rdx
0x14000e33d  mov     rdi, rcx
0x14000e340  lea     rdx, aFiledialogbrok_76; "FileDialogBroker::SetAsyncTask"
0x14000e347  lea     rcx, [rsp+78h+var_58]
0x14000e34c  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000e351  nop
0x14000e352  lea     rcx, [rdi-10h]
0x14000e356  mov     rax, [rcx]
0x14000e359  mov     rax, [rax+40h]
0x14000e35d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e362  mov     r8, rax
0x14000e365  mov     rcx, [rax]
0x14000e368  mov     rax, [rcx+168h]
0x14000e36f  mov     rdx, rbx
0x14000e372  mov     rcx, r8
0x14000e375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e37a  mov     ebx, eax
0x14000e37c  lea     rcx, [rsp+78h+var_58]; this
0x14000e381  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000e386  mov     eax, ebx
0x14000e388  jmp     short loc_14000E391
0x14000e38a  mov     eax, [rsp+78h+arg_0]
0x14000e391  mov     rbx, [rsp+78h+arg_8]
0x14000e399  add     rsp, 70h
0x14000e39d  pop     rdi
0x14000e39e  retn
```
