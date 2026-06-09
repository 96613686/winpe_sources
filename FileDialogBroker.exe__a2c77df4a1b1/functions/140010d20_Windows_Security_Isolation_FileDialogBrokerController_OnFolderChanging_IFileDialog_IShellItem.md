# Windows::Security::Isolation::FileDialogBrokerController::OnFolderChanging(IFileDialog *,IShellItem *)

- ea: `0x140010d20`
- end: `0x140010d8f`
- name: `?OnFolderChanging@FileDialogBrokerController@Isolation@Security@Windows@@UEAAJPEAUIFileDialog@@PEAUIShellItem@@@Z`
- size: `111`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBrokerController *__hidden this, struct IFileDialog *, struct IShellItem *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000f8d0`
- `0x140010bb0`
- `0x140010be8`
- `0x140010d20`
- `0x140014010`

## string_xrefs

- `0x140010d30`: `FileDialogBrokerController::OnFolderChanging`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBrokerController::OnFolderChanging(
        Windows::Security::Isolation::FileDialogBrokerController *this,
        struct IFileDialog *a2,
        struct IShellItem *a3)
{
  struct IFileDialogEvents *ClientDialogEvents; // rdi
  HRESULT (__stdcall *OnFolderChanging)(IFileDialogEvents *, IFileDialog *, IShellItem *); // r14
  struct IFileDialog *DialogBroker; // rax
  unsigned int v8; // ebx
  const char *v9; // r9
  __int64 result; // rax
  _BYTE v11[120]; // [rsp+20h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(
    (__int64)v11,
    (__int64)"FileDialogBrokerController::OnFolderChanging");
  try
  {
    ClientDialogEvents = Windows::Security::Isolation::FileDialogBrokerController::GetClientDialogEvents(this);
    OnFolderChanging = ClientDialogEvents->lpVtbl->OnFolderChanging;
    DialogBroker = Windows::Security::Isolation::FileDialogBrokerController::GetDialogBroker(this);
    v8 = ((__int64 (__fastcall *)(struct IFileDialogEvents *, struct IFileDialog *, struct IShellItem *))OnFolderChanging)(
           ClientDialogEvents,
           DialogBroker,
           a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v11);
    result = v8;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x66,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbrokercontroller.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x140010d20  push    rbx
0x140010d22  push    rsi
0x140010d23  push    rdi
0x140010d24  push    r14
0x140010d26  sub     rsp, 78h
0x140010d2a  mov     rsi, r8
0x140010d2d  mov     rbx, rcx
0x140010d30  lea     rdx, aFiledialogbrok_28; "FileDialogBrokerController::OnFolderCha"...
0x140010d37  lea     rcx, [rsp+98h+var_78]
0x140010d3c  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x140010d41  nop
0x140010d42  mov     rcx, rbx; this
0x140010d45  call    ?GetClientDialogEvents@FileDialogBrokerController@Isolation@Security@Windows@@AEBAPEAUIFileDialogEvents@@XZ; Windows::Security::Isolation::FileDialogBrokerController::GetClientDialogEvents(void)
0x140010d4a  mov     rdi, rax
0x140010d4d  mov     rcx, [rax]
0x140010d50  mov     r14, [rcx+20h]
0x140010d54  mov     rcx, rbx; this
0x140010d57  call    ?GetDialogBroker@FileDialogBrokerController@Isolation@Security@Windows@@AEBAPEAUIFileDialog@@XZ; Windows::Security::Isolation::FileDialogBrokerController::GetDialogBroker(void)
0x140010d5c  mov     r8, rsi
0x140010d5f  mov     rdx, rax
0x140010d62  mov     rcx, rdi
0x140010d65  mov     rax, r14
0x140010d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010d6d  mov     ebx, eax
0x140010d6f  lea     rcx, [rsp+98h+var_78]; this
0x140010d74  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x140010d79  mov     eax, ebx
0x140010d7b  jmp     short loc_140010D84
0x140010d7d  mov     eax, [rsp+98h+arg_18]
0x140010d84  add     rsp, 78h
0x140010d88  pop     r14
0x140010d8a  pop     rdi
0x140010d8b  pop     rsi
0x140010d8c  pop     rbx
0x140010d8d  retn
```
