# Windows::Security::Isolation::FileDialogBroker::ApplyProperties(IShellItem *,IPropertyStore *,HWND__ *,IFileOperationProgressSink *)

- ea: `0x140009e20`
- end: `0x140009eca`
- name: `?ApplyProperties@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAUIShellItem@@PEAUIPropertyStore@@PEAUHWND__@@PEAUIFileOperationProgressSink@@@Z`
- size: `170`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, struct IShellItem *, struct IPropertyStore *, HWND, struct IFileOperationProgressSink *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140007df4`
- `0x140009194`
- `0x140009e20`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x140009e95`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x140009e39`: `FileDialogBroker::ApplyProperties`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::ApplyProperties(
        Windows::Security::Isolation::FileDialogBroker *this,
        struct IShellItem *a2,
        struct IPropertyStore *a3,
        HWND a4,
        struct IFileOperationProgressSink *a5)
{
  __int64 v9; // r10
  int v10; // eax
  const char *v11; // r9
  __int64 result; // rax
  _BYTE v13[120]; // [rsp+30h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v13, "FileDialogBroker::ApplyProperties");
  try
  {
    v9 = (*(__int64 (**)(void))(*((_QWORD *)this - 5) + 48LL))();
    v10 = (*(__int64 (__fastcall **)(__int64, struct IShellItem *, struct IPropertyStore *, HWND))(*(_QWORD *)v9 + 248LL))(
            v9,
            a2,
            a3,
            a4);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5ED,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)v10,
        (int)a5);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v13);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x5F1,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x140009e20  push    rbx
0x140009e22  push    rsi
0x140009e23  push    rdi
0x140009e24  push    r14
0x140009e26  sub     rsp, 88h
0x140009e2d  mov     rdi, r9
0x140009e30  mov     rsi, r8
0x140009e33  mov     r14, rdx
0x140009e36  mov     rbx, rcx
0x140009e39  lea     rdx, aFiledialogbrok_4; "FileDialogBroker::ApplyProperties"
0x140009e40  lea     rcx, [rsp+0A8h+var_78]
0x140009e45  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x140009e4a  nop
0x140009e4b  lea     rcx, [rbx-28h]
0x140009e4f  mov     rax, [rcx]
0x140009e52  mov     rax, [rax+30h]
0x140009e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009e5b  mov     r10, rax
0x140009e5e  mov     rcx, [rax]
0x140009e61  mov     rax, [rcx+0F8h]
0x140009e68  mov     rcx, [rsp+0A8h+arg_20]
0x140009e70  mov     qword ptr [rsp+0A8h+var_88], rcx; int
0x140009e75  mov     r9, rdi
0x140009e78  mov     r8, rsi
0x140009e7b  mov     rdx, r14
0x140009e7e  mov     rcx, r10
0x140009e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009e86  mov     rcx, [rsp+0A8h]; this
0x140009e8e  test    eax, eax
0x140009e90  jns     short loc_140009EA7
0x140009e92  mov     r9d, eax; char *
0x140009e95  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x140009e9c  mov     edx, 5EDh; void *
0x140009ea1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140009ea7  lea     rcx, [rsp+0A8h+var_78]; this
0x140009eac  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x140009eb1  xor     eax, eax
0x140009eb3  jmp     short loc_140009EBC
0x140009eb5  mov     eax, [rsp+0A8h+arg_0]
0x140009ebc  add     rsp, 88h
0x140009ec3  pop     r14
0x140009ec5  pop     rdi
0x140009ec6  pop     rsi
0x140009ec7  pop     rbx
0x140009ec8  retn
```
