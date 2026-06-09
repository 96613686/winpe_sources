# Windows::Security::Isolation::FileDialogBrokerController::OnTypeChange(IFileDialog *)

- ea: `0x140010f40`
- end: `0x140010fb6`
- name: `?OnTypeChange@FileDialogBrokerController@Isolation@Security@Windows@@UEAAJPEAUIFileDialog@@@Z`
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
- `0x140010f40`
- `0x140014010`

## string_xrefs

- `0x140010f52`: `FileDialogBrokerController::OnTypeChange`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBrokerController::OnTypeChange(
        Windows::Security::Isolation::FileDialogBrokerController *this,
        struct IFileDialog *a2)
{
  struct IFileDialogEvents *ClientDialogEvents; // rdi
  HRESULT (__stdcall *OnTypeChange)(IFileDialogEvents *, IFileDialog *); // rsi
  struct IFileDialog *DialogBroker; // rax
  unsigned int v6; // ebx
  const char *v7; // r9
  __int64 result; // rax
  _BYTE v9[80]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v9, (__int64)"FileDialogBrokerController::OnTypeChange");
  try
  {
    ClientDialogEvents = Windows::Security::Isolation::FileDialogBrokerController::GetClientDialogEvents(this);
    OnTypeChange = ClientDialogEvents->lpVtbl->OnTypeChange;
    DialogBroker = Windows::Security::Isolation::FileDialogBrokerController::GetDialogBroker(this);
    v6 = ((__int64 (__fastcall *)(struct IFileDialogEvents *, struct IFileDialog *))OnTypeChange)(
           ClientDialogEvents,
           DialogBroker);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v9);
    result = v6;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x9F,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbrokercontroller.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x140010f40  mov     [rsp+arg_0], rbx
0x140010f45  mov     [rsp+arg_8], rsi
0x140010f4a  push    rdi
0x140010f4b  sub     rsp, 70h
0x140010f4f  mov     rbx, rcx
0x140010f52  lea     rdx, aFiledialogbrok_45; "FileDialogBrokerController::OnTypeChang"...
0x140010f59  lea     rcx, [rsp+78h+var_58]
0x140010f5e  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x140010f63  nop
0x140010f64  mov     rcx, rbx; this
0x140010f67  call    ?GetClientDialogEvents@FileDialogBrokerController@Isolation@Security@Windows@@AEBAPEAUIFileDialogEvents@@XZ; Windows::Security::Isolation::FileDialogBrokerController::GetClientDialogEvents(void)
0x140010f6c  mov     rdi, rax
0x140010f6f  mov     rcx, [rax]
0x140010f72  mov     rsi, [rcx+40h]
0x140010f76  mov     rcx, rbx; this
0x140010f79  call    ?GetDialogBroker@FileDialogBrokerController@Isolation@Security@Windows@@AEBAPEAUIFileDialog@@XZ; Windows::Security::Isolation::FileDialogBrokerController::GetDialogBroker(void)
0x140010f7e  mov     rdx, rax
0x140010f81  mov     rcx, rdi
0x140010f84  mov     rax, rsi
0x140010f87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010f8c  mov     ebx, eax
0x140010f8e  lea     rcx, [rsp+78h+var_58]; this
0x140010f93  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x140010f98  mov     eax, ebx
0x140010f9a  jmp     short loc_140010FA3
0x140010f9c  mov     eax, [rsp+78h+arg_10]
0x140010fa3  lea     r11, [rsp+78h+var_8]
0x140010fa8  mov     rbx, [r11+10h]
0x140010fac  mov     rsi, [r11+18h]
0x140010fb0  mov     rsp, r11
0x140010fb3  pop     rdi
0x140010fb4  retn
```
