# Windows::Security::Isolation::FileDialogBrokerController::OnFileOk(IFileDialog *)

- ea: `0x140010c20`
- end: `0x140010c96`
- name: `?OnFileOk@FileDialogBrokerController@Isolation@Security@Windows@@UEAAJPEAUIFileDialog@@@Z`
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
- `0x140010c20`
- `0x140014010`

## string_xrefs

- `0x140010c32`: `FileDialogBrokerController::OnFileOk`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBrokerController::OnFileOk(
        Windows::Security::Isolation::FileDialogBrokerController *this,
        struct IFileDialog *a2)
{
  struct IFileDialogEvents *ClientDialogEvents; // rdi
  HRESULT (__stdcall *OnFileOk)(IFileDialogEvents *, IFileDialog *); // rsi
  struct IFileDialog *DialogBroker; // rax
  unsigned int v6; // ebx
  const char *v7; // r9
  __int64 result; // rax
  _BYTE v9[80]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v9, "FileDialogBrokerController::OnFileOk");
  try
  {
    ClientDialogEvents = Windows::Security::Isolation::FileDialogBrokerController::GetClientDialogEvents(this);
    OnFileOk = ClientDialogEvents->lpVtbl->OnFileOk;
    DialogBroker = Windows::Security::Isolation::FileDialogBrokerController::GetDialogBroker(this);
    v6 = ((__int64 (__fastcall *)(struct IFileDialogEvents *, struct IFileDialog *))OnFileOk)(
           ClientDialogEvents,
           DialogBroker);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v9);
    result = v6;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x58,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbrokercontroller.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x140010c20  mov     [rsp+arg_0], rbx
0x140010c25  mov     [rsp+arg_8], rsi
0x140010c2a  push    rdi
0x140010c2b  sub     rsp, 70h
0x140010c2f  mov     rbx, rcx
0x140010c32  lea     rdx, aFiledialogbrok_6; "FileDialogBrokerController::OnFileOk"
0x140010c39  lea     rcx, [rsp+78h+var_58]
0x140010c3e  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x140010c43  nop
0x140010c44  mov     rcx, rbx; this
0x140010c47  call    ?GetClientDialogEvents@FileDialogBrokerController@Isolation@Security@Windows@@AEBAPEAUIFileDialogEvents@@XZ; Windows::Security::Isolation::FileDialogBrokerController::GetClientDialogEvents(void)
0x140010c4c  mov     rdi, rax
0x140010c4f  mov     rcx, [rax]
0x140010c52  mov     rsi, [rcx+18h]
0x140010c56  mov     rcx, rbx; this
0x140010c59  call    ?GetDialogBroker@FileDialogBrokerController@Isolation@Security@Windows@@AEBAPEAUIFileDialog@@XZ; Windows::Security::Isolation::FileDialogBrokerController::GetDialogBroker(void)
0x140010c5e  mov     rdx, rax
0x140010c61  mov     rcx, rdi
0x140010c64  mov     rax, rsi
0x140010c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010c6c  mov     ebx, eax
0x140010c6e  lea     rcx, [rsp+78h+var_58]; this
0x140010c73  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x140010c78  mov     eax, ebx
0x140010c7a  jmp     short loc_140010C83
0x140010c7c  mov     eax, [rsp+78h+arg_10]
0x140010c83  lea     r11, [rsp+78h+var_8]
0x140010c88  mov     rbx, [r11+10h]
0x140010c8c  mov     rsi, [r11+18h]
0x140010c90  mov     rsp, r11
0x140010c93  pop     rdi
0x140010c94  retn
```
