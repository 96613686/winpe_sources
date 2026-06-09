# Windows::Security::Isolation::FileDialogBrokerController::OnFolderChange(IFileDialog *)

- ea: `0x140010ca0`
- end: `0x140010d16`
- name: `?OnFolderChange@FileDialogBrokerController@Isolation@Security@Windows@@UEAAJPEAUIFileDialog@@@Z`
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
- `0x140010ca0`
- `0x140014010`

## string_xrefs

- `0x140010cb2`: `FileDialogBrokerController::OnFolderChange`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBrokerController::OnFolderChange(
        Windows::Security::Isolation::FileDialogBrokerController *this,
        struct IFileDialog *a2)
{
  struct IFileDialogEvents *ClientDialogEvents; // rdi
  HRESULT (__stdcall *OnFolderChange)(IFileDialogEvents *, IFileDialog *); // rsi
  struct IFileDialog *DialogBroker; // rax
  unsigned int v6; // ebx
  const char *v7; // r9
  __int64 result; // rax
  _BYTE v9[80]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v9, (__int64)"FileDialogBrokerController::OnFolderChange");
  try
  {
    ClientDialogEvents = Windows::Security::Isolation::FileDialogBrokerController::GetClientDialogEvents(this);
    OnFolderChange = ClientDialogEvents->lpVtbl->OnFolderChange;
    DialogBroker = Windows::Security::Isolation::FileDialogBrokerController::GetDialogBroker(this);
    v6 = ((__int64 (__fastcall *)(struct IFileDialogEvents *, struct IFileDialog *))OnFolderChange)(
           ClientDialogEvents,
           DialogBroker);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v9);
    result = v6;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x74,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbrokercontroller.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x140010ca0  mov     [rsp+arg_0], rbx
0x140010ca5  mov     [rsp+arg_8], rsi
0x140010caa  push    rdi
0x140010cab  sub     rsp, 70h
0x140010caf  mov     rbx, rcx
0x140010cb2  lea     rdx, aFiledialogbrok_82; "FileDialogBrokerController::OnFolderCha"...
0x140010cb9  lea     rcx, [rsp+78h+var_58]
0x140010cbe  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x140010cc3  nop
0x140010cc4  mov     rcx, rbx; this
0x140010cc7  call    ?GetClientDialogEvents@FileDialogBrokerController@Isolation@Security@Windows@@AEBAPEAUIFileDialogEvents@@XZ; Windows::Security::Isolation::FileDialogBrokerController::GetClientDialogEvents(void)
0x140010ccc  mov     rdi, rax
0x140010ccf  mov     rcx, [rax]
0x140010cd2  mov     rsi, [rcx+28h]
0x140010cd6  mov     rcx, rbx; this
0x140010cd9  call    ?GetDialogBroker@FileDialogBrokerController@Isolation@Security@Windows@@AEBAPEAUIFileDialog@@XZ; Windows::Security::Isolation::FileDialogBrokerController::GetDialogBroker(void)
0x140010cde  mov     rdx, rax
0x140010ce1  mov     rcx, rdi
0x140010ce4  mov     rax, rsi
0x140010ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010cec  mov     ebx, eax
0x140010cee  lea     rcx, [rsp+78h+var_58]; this
0x140010cf3  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x140010cf8  mov     eax, ebx
0x140010cfa  jmp     short loc_140010D03
0x140010cfc  mov     eax, [rsp+78h+arg_10]
0x140010d03  lea     r11, [rsp+78h+var_8]
0x140010d08  mov     rbx, [r11+10h]
0x140010d0c  mov     rsi, [r11+18h]
0x140010d10  mov     rsp, r11
0x140010d13  pop     rdi
0x140010d14  retn
```
