# Windows::Security::Isolation::FileDialogBrokerController::OnOverwrite(IFileDialog *,IShellItem *,FDE_OVERWRITE_RESPONSE *)

- ea: `0x140010da0`
- end: `0x140010e1c`
- name: `?OnOverwrite@FileDialogBrokerController@Isolation@Security@Windows@@UEAAJPEAUIFileDialog@@PEAUIShellItem@@PEAW4FDE_OVERWRITE_RESPONSE@@@Z`
- size: `124`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBrokerController *__hidden this, struct IFileDialog *, struct IShellItem *, enum FDE_OVERWRITE_RESPONSE *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000f8d0`
- `0x140010bb0`
- `0x140010be8`
- `0x140010da0`
- `0x140014010`

## string_xrefs

- `0x140010db8`: `FileDialogBrokerController::OnOverwrite`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBrokerController::OnOverwrite(
        Windows::Security::Isolation::FileDialogBrokerController *this,
        struct IFileDialog *a2,
        struct IShellItem *a3,
        enum FDE_OVERWRITE_RESPONSE *a4)
{
  struct IFileDialogEvents *ClientDialogEvents; // rdi
  HRESULT (__stdcall *OnOverwrite)(IFileDialogEvents *, IFileDialog *, IShellItem *, FDE_OVERWRITE_RESPONSE *); // rsi
  struct IFileDialog *DialogBroker; // rax
  unsigned int v10; // ebx
  const char *v11; // r9
  __int64 result; // rax
  _BYTE v13[120]; // [rsp+40h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v13, (__int64)"FileDialogBrokerController::OnOverwrite");
  try
  {
    ClientDialogEvents = Windows::Security::Isolation::FileDialogBrokerController::GetClientDialogEvents(this);
    OnOverwrite = ClientDialogEvents->lpVtbl->OnOverwrite;
    DialogBroker = Windows::Security::Isolation::FileDialogBrokerController::GetDialogBroker(this);
    v10 = ((__int64 (__fastcall *)(struct IFileDialogEvents *, struct IFileDialog *, struct IShellItem *, enum FDE_OVERWRITE_RESPONSE *))OnOverwrite)(
            ClientDialogEvents,
            DialogBroker,
            a3,
            a4);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v13);
    result = v10;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xAE,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbrokercontroller.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x140010da0  push    rbx
0x140010da2  push    rsi
0x140010da3  push    rdi
0x140010da4  push    r14
0x140010da6  push    r15
0x140010da8  sub     rsp, 90h
0x140010daf  mov     r14, r9
0x140010db2  mov     r15, r8
0x140010db5  mov     rbx, rcx
0x140010db8  lea     rdx, aFiledialogbrok_61; "FileDialogBrokerController::OnOverwrite"
0x140010dbf  lea     rcx, [rsp+0B8h+var_78]
0x140010dc4  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x140010dc9  nop
0x140010dca  mov     rcx, rbx; this
0x140010dcd  call    ?GetClientDialogEvents@FileDialogBrokerController@Isolation@Security@Windows@@AEBAPEAUIFileDialogEvents@@XZ; Windows::Security::Isolation::FileDialogBrokerController::GetClientDialogEvents(void)
0x140010dd2  mov     rdi, rax
0x140010dd5  mov     rcx, [rax]
0x140010dd8  mov     rsi, [rcx+48h]
0x140010ddc  mov     rcx, rbx; this
0x140010ddf  call    ?GetDialogBroker@FileDialogBrokerController@Isolation@Security@Windows@@AEBAPEAUIFileDialog@@XZ; Windows::Security::Isolation::FileDialogBrokerController::GetDialogBroker(void)
0x140010de4  mov     r9, r14
0x140010de7  mov     r8, r15
0x140010dea  mov     rdx, rax
0x140010ded  mov     rcx, rdi
0x140010df0  mov     rax, rsi
0x140010df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010df8  mov     ebx, eax
0x140010dfa  lea     rcx, [rsp+0B8h+var_78]; this
0x140010dff  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x140010e04  mov     eax, ebx
0x140010e06  jmp     short loc_140010E0C
0x140010e08  mov     eax, [rsp+0B8h+var_88]
0x140010e0c  add     rsp, 90h
0x140010e13  pop     r15
0x140010e15  pop     r14
0x140010e17  pop     rdi
0x140010e18  pop     rsi
0x140010e19  pop     rbx
0x140010e1a  retn
```
