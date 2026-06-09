# Windows::Security::Isolation::FileDialogBroker::GetCurrentShellView(_GUID const &,void * *)

- ea: `0x14000acb0`
- end: `0x14000ad2f`
- name: `?GetCurrentShellView@FileDialogBroker@Isolation@Security@Windows@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `127`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000acb0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000acc8`: `FileDialogBroker::GetCurrentShellView`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetCurrentShellView(
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

  FileDialogBrokerTraceLogging::WatchCurrentThread(v10, "FileDialogBroker::GetCurrentShellView");
  try
  {
    v6 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    v7 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, void **))(*(_QWORD *)v6 + 376LL))(v6, a2, a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
    result = v7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x44B,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000acb0  mov     [rsp+arg_8], rbx
0x14000acb5  mov     [rsp+arg_10], rsi
0x14000acba  push    rdi
0x14000acbb  sub     rsp, 70h
0x14000acbf  mov     rdi, r8
0x14000acc2  mov     rsi, rdx
0x14000acc5  mov     rbx, rcx
0x14000acc8  lea     rdx, aFiledialogbrok_49; "FileDialogBroker::GetCurrentShellView"
0x14000accf  lea     rcx, [rsp+78h+var_58]
0x14000acd4  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000acd9  nop
0x14000acda  lea     rcx, [rbx-10h]
0x14000acde  mov     rax, [rcx]
0x14000ace1  mov     rax, [rax+40h]
0x14000ace5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000acea  mov     r9, rax
0x14000aced  mov     rcx, [rax]
0x14000acf0  mov     rax, [rcx+178h]
0x14000acf7  mov     r8, rdi
0x14000acfa  mov     rdx, rsi
0x14000acfd  mov     rcx, r9
0x14000ad00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ad05  mov     ebx, eax
0x14000ad07  lea     rcx, [rsp+78h+var_58]; this
0x14000ad0c  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000ad11  mov     eax, ebx
0x14000ad13  jmp     short loc_14000AD1C
0x14000ad15  mov     eax, [rsp+78h+arg_0]
0x14000ad1c  lea     r11, [rsp+78h+var_8]
0x14000ad21  mov     rbx, [r11+18h]
0x14000ad25  mov     rsi, [r11+20h]
0x14000ad29  mov     rsp, r11
0x14000ad2c  pop     rdi
0x14000ad2d  retn
```
