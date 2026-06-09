# Windows::Security::Isolation::FileDialogBrokerController::OnSelectionChange(IFileDialog *)

- ea: `0x140010e30`
- end: `0x140010ea6`
- name: `?OnSelectionChange@FileDialogBrokerController@Isolation@Security@Windows@@UEAAJPEAUIFileDialog@@@Z`
- size: `118`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBrokerController *__hidden this, struct IFileDialog *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000f8d0`
- `0x140010bb0`
- `0x140010be8`
- `0x140010e30`
- `0x140014010`

## string_xrefs

- `0x140010e42`: `FileDialogBrokerController::OnSelectionChange`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBrokerController::OnSelectionChange(
        Windows::Security::Isolation::FileDialogBrokerController *this,
        struct IFileDialog *a2)
{
  struct IFileDialogEvents *ClientDialogEvents; // rdi
  HRESULT (__stdcall *OnSelectionChange)(IFileDialogEvents *, IFileDialog *); // rsi
  struct IFileDialog *DialogBroker; // rax
  unsigned int v6; // ebx
  const char *v7; // r9
  __int64 result; // rax
  _BYTE v9[80]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(
    (__int64)v9,
    (__int64)"FileDialogBrokerController::OnSelectionChange");
  try
  {
    ClientDialogEvents = Windows::Security::Isolation::FileDialogBrokerController::GetClientDialogEvents(this);
    OnSelectionChange = ClientDialogEvents->lpVtbl->OnSelectionChange;
    DialogBroker = Windows::Security::Isolation::FileDialogBrokerController::GetDialogBroker(this);
    v6 = ((__int64 (__fastcall *)(struct IFileDialogEvents *, struct IFileDialog *))OnSelectionChange)(
           ClientDialogEvents,
           DialogBroker);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v9);
    result = v6;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x82,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbrokercontroller.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x140010e30  mov     [rsp+arg_0], rbx
0x140010e35  mov     [rsp+arg_8], rsi
0x140010e3a  push    rdi
0x140010e3b  sub     rsp, 70h
0x140010e3f  mov     rbx, rcx
0x140010e42  lea     rdx, aFiledialogbrok_72; "FileDialogBrokerController::OnSelection"...
0x140010e49  lea     rcx, [rsp+78h+var_58]
0x140010e4e  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x140010e53  nop
0x140010e54  mov     rcx, rbx; this
0x140010e57  call    ?GetClientDialogEvents@FileDialogBrokerController@Isolation@Security@Windows@@AEBAPEAUIFileDialogEvents@@XZ; Windows::Security::Isolation::FileDialogBrokerController::GetClientDialogEvents(void)
0x140010e5c  mov     rdi, rax
0x140010e5f  mov     rcx, [rax]
0x140010e62  mov     rsi, [rcx+30h]
0x140010e66  mov     rcx, rbx; this
0x140010e69  call    ?GetDialogBroker@FileDialogBrokerController@Isolation@Security@Windows@@AEBAPEAUIFileDialog@@XZ; Windows::Security::Isolation::FileDialogBrokerController::GetDialogBroker(void)
0x140010e6e  mov     rdx, rax
0x140010e71  mov     rcx, rdi
0x140010e74  mov     rax, rsi
0x140010e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010e7c  mov     ebx, eax
0x140010e7e  lea     rcx, [rsp+78h+var_58]; this
0x140010e83  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x140010e88  mov     eax, ebx
0x140010e8a  jmp     short loc_140010E93
0x140010e8c  mov     eax, [rsp+78h+arg_10]
0x140010e93  lea     r11, [rsp+78h+var_8]
0x140010e98  mov     rbx, [r11+10h]
0x140010e9c  mov     rsi, [r11+18h]
0x140010ea0  mov     rsp, r11
0x140010ea3  pop     rdi
0x140010ea4  retn
```
