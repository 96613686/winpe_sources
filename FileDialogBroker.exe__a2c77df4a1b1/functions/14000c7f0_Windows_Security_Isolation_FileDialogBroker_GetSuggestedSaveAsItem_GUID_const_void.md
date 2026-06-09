# Windows::Security::Isolation::FileDialogBroker::GetSuggestedSaveAsItem(_GUID const &,void * *)

- ea: `0x14000c7f0`
- end: `0x14000c86f`
- name: `?GetSuggestedSaveAsItem@FileDialogBroker@Isolation@Security@Windows@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `127`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000c7f0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000c808`: `FileDialogBroker::GetSuggestedSaveAsItem`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetSuggestedSaveAsItem(
        Windows::Security::Isolation::FileDialogBroker *this,
        const struct _GUID *a2,
        void **a3)
{
  __int64 v6; // rax
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 result; // rax
  _BYTE v10[80]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v10, (__int64)"FileDialogBroker::GetSuggestedSaveAsItem");
  try
  {
    v6 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    v7 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, void **))(*(_QWORD *)v6 + 392LL))(v6, a2, a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
    result = v7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x45F,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000c7f0  mov     [rsp+arg_8], rbx
0x14000c7f5  mov     [rsp+arg_10], rsi
0x14000c7fa  push    rdi
0x14000c7fb  sub     rsp, 70h
0x14000c7ff  mov     rdi, r8
0x14000c802  mov     rsi, rdx
0x14000c805  mov     rbx, rcx
0x14000c808  lea     rdx, aFiledialogbrok_31; "FileDialogBroker::GetSuggestedSaveAsIte"...
0x14000c80f  lea     rcx, [rsp+78h+var_58]
0x14000c814  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000c819  nop
0x14000c81a  lea     rcx, [rbx-10h]
0x14000c81e  mov     rax, [rcx]
0x14000c821  mov     rax, [rax+40h]
0x14000c825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c82a  mov     r9, rax
0x14000c82d  mov     rcx, [rax]
0x14000c830  mov     rax, [rcx+188h]
0x14000c837  mov     r8, rdi
0x14000c83a  mov     rdx, rsi
0x14000c83d  mov     rcx, r9
0x14000c840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c845  mov     ebx, eax
0x14000c847  lea     rcx, [rsp+78h+var_58]; this
0x14000c84c  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000c851  mov     eax, ebx
0x14000c853  jmp     short loc_14000C85C
0x14000c855  mov     eax, [rsp+78h+arg_0]
0x14000c85c  lea     r11, [rsp+78h+var_8]
0x14000c861  mov     rbx, [r11+18h]
0x14000c865  mov     rsi, [r11+20h]
0x14000c869  mov     rsp, r11
0x14000c86c  pop     rdi
0x14000c86d  retn
```
