# Windows::Security::Isolation::FileDialogBroker::GetSelectedItemsInternal(int,int,IShellItemArray * *)

- ea: `0x14000c760`
- end: `0x14000c7de`
- name: `?GetSelectedItemsInternal@FileDialogBroker@Isolation@Security@Windows@@UEAAJHHPEAPEAUIShellItemArray@@@Z`
- size: `126`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBroker *__hidden this, int, int, struct IShellItemArray **)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140009194`
- `0x14000c760`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000c779`: `FileDialogBroker::GetSelectedItemsInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::GetSelectedItemsInternal(
        Windows::Security::Isolation::FileDialogBroker *this,
        unsigned int a2,
        unsigned int a3,
        struct IShellItemArray **a4)
{
  __int64 v8; // rax
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 result; // rax
  _BYTE v12[120]; // [rsp+30h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v12, (__int64)"FileDialogBroker::GetSelectedItemsInternal");
  try
  {
    v8 = (*(__int64 (**)(void))(*((_QWORD *)this - 2) + 64LL))();
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, struct IShellItemArray **))(*(_QWORD *)v8 + 352LL))(
           v8,
           a2,
           a3,
           a4);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v12);
    result = v9;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x42D,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x14000c760  push    rbx
0x14000c762  push    rsi
0x14000c763  push    rdi
0x14000c764  push    r14
0x14000c766  sub     rsp, 88h
0x14000c76d  mov     rdi, r9
0x14000c770  mov     esi, r8d
0x14000c773  mov     r14d, edx
0x14000c776  mov     rbx, rcx
0x14000c779  lea     rdx, aFiledialogbrok_20; "FileDialogBroker::GetSelectedItemsInter"...
0x14000c780  lea     rcx, [rsp+0A8h+var_78]
0x14000c785  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000c78a  nop
0x14000c78b  lea     rcx, [rbx-10h]
0x14000c78f  mov     rax, [rcx]
0x14000c792  mov     rax, [rax+40h]
0x14000c796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c79b  mov     r10, rax
0x14000c79e  mov     rcx, [rax]
0x14000c7a1  mov     rax, [rcx+160h]
0x14000c7a8  mov     r9, rdi
0x14000c7ab  mov     r8d, esi
0x14000c7ae  mov     edx, r14d
0x14000c7b1  mov     rcx, r10
0x14000c7b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c7b9  mov     ebx, eax
0x14000c7bb  lea     rcx, [rsp+0A8h+var_78]; this
0x14000c7c0  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000c7c5  mov     eax, ebx
0x14000c7c7  jmp     short loc_14000C7D0
0x14000c7c9  mov     eax, [rsp+0A8h+arg_0]
0x14000c7d0  add     rsp, 88h
0x14000c7d7  pop     r14
0x14000c7d9  pop     rdi
0x14000c7da  pop     rsi
0x14000c7db  pop     rbx
0x14000c7dc  retn
```
