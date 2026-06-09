# Windows::Security::Isolation::FileDialogBrokerController::OnShareViolation(IFileDialog *,IShellItem *,FDE_SHAREVIOLATION_RESPONSE *)

- ea: `0x140010eb0`
- end: `0x140010f2c`
- name: `?OnShareViolation@FileDialogBrokerController@Isolation@Security@Windows@@UEAAJPEAUIFileDialog@@PEAUIShellItem@@PEAW4FDE_SHAREVIOLATION_RESPONSE@@@Z`
- size: `124`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBrokerController *__hidden this, struct IFileDialog *, struct IShellItem *, enum FDE_SHAREVIOLATION_RESPONSE *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140009194`
- `0x14000f8d0`
- `0x140010bb0`
- `0x140010be8`
- `0x140010eb0`
- `0x140014010`

## string_xrefs

- `0x140010ec8`: `FileDialogBrokerController::OnShareViolation`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBrokerController::OnShareViolation(
        Windows::Security::Isolation::FileDialogBrokerController *this,
        struct IFileDialog *a2,
        struct IShellItem *a3,
        enum FDE_SHAREVIOLATION_RESPONSE *a4)
{
  struct IFileDialogEvents *ClientDialogEvents; // rdi
  HRESULT (__stdcall *OnShareViolation)(IFileDialogEvents *, IFileDialog *, IShellItem *, FDE_SHAREVIOLATION_RESPONSE *); // rsi
  struct IFileDialog *DialogBroker; // rax
  unsigned int v10; // ebx
  const char *v11; // r9
  __int64 result; // rax
  _BYTE v13[120]; // [rsp+40h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(
    (__int64)v13,
    (__int64)"FileDialogBrokerController::OnShareViolation");
  try
  {
    ClientDialogEvents = Windows::Security::Isolation::FileDialogBrokerController::GetClientDialogEvents(this);
    OnShareViolation = ClientDialogEvents->lpVtbl->OnShareViolation;
    DialogBroker = Windows::Security::Isolation::FileDialogBrokerController::GetDialogBroker(this);
    v10 = ((__int64 (__fastcall *)(struct IFileDialogEvents *, struct IFileDialog *, struct IShellItem *, enum FDE_SHAREVIOLATION_RESPONSE *))OnShareViolation)(
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
                           (void *)0x91,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbrokercontroller.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x140010eb0  push    rbx
0x140010eb2  push    rsi
0x140010eb3  push    rdi
0x140010eb4  push    r14
0x140010eb6  push    r15
0x140010eb8  sub     rsp, 90h
0x140010ebf  mov     r14, r9
0x140010ec2  mov     r15, r8
0x140010ec5  mov     rbx, rcx
0x140010ec8  lea     rdx, aFiledialogbrok_63; "FileDialogBrokerController::OnShareViol"...
0x140010ecf  lea     rcx, [rsp+0B8h+var_78]
0x140010ed4  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x140010ed9  nop
0x140010eda  mov     rcx, rbx; this
0x140010edd  call    ?GetClientDialogEvents@FileDialogBrokerController@Isolation@Security@Windows@@AEBAPEAUIFileDialogEvents@@XZ; Windows::Security::Isolation::FileDialogBrokerController::GetClientDialogEvents(void)
0x140010ee2  mov     rdi, rax
0x140010ee5  mov     rcx, [rax]
0x140010ee8  mov     rsi, [rcx+38h]
0x140010eec  mov     rcx, rbx; this
0x140010eef  call    ?GetDialogBroker@FileDialogBrokerController@Isolation@Security@Windows@@AEBAPEAUIFileDialog@@XZ; Windows::Security::Isolation::FileDialogBrokerController::GetDialogBroker(void)
0x140010ef4  mov     r9, r14
0x140010ef7  mov     r8, r15
0x140010efa  mov     rdx, rax
0x140010efd  mov     rcx, rdi
0x140010f00  mov     rax, rsi
0x140010f03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010f08  mov     ebx, eax
0x140010f0a  lea     rcx, [rsp+0B8h+var_78]; this
0x140010f0f  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x140010f14  mov     eax, ebx
0x140010f16  jmp     short loc_140010F1C
0x140010f18  mov     eax, [rsp+0B8h+var_88]
0x140010f1c  add     rsp, 90h
0x140010f23  pop     r15
0x140010f25  pop     r14
0x140010f27  pop     rdi
0x140010f28  pop     rsi
0x140010f29  pop     rbx
0x140010f2a  retn
```
