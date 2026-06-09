# Windows::Security::Isolation::FileOpenDialogBroker::RuntimeClassInitialize(void)

- ea: `0x14000def0`
- end: `0x14000df35`
- name: `?RuntimeClassInitialize@FileOpenDialogBroker@Isolation@Security@Windows@@QEAAJXZ`
- size: `69`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileOpenDialogBroker *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140008544`

## callees

- `0x140009194`
- `0x14000de1c`
- `0x14000def0`
- `0x14000f8d0`

## string_xrefs

- `0x14000def9`: `FileOpenDialogBroker::RuntimeClassInitialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileOpenDialogBroker::RuntimeClassInitialize(
        Windows::Security::Isolation::FileOpenDialogBroker *this)
{
  _BYTE v3[88]; // [rsp+20h] [rbp-58h] BYREF

  FileDialogBrokerTraceLogging::WatchCurrentThread(v3, "FileOpenDialogBroker::RuntimeClassInitialize");
  LODWORD(this) = Windows::Security::Isolation::FileOpenDialogBroker::RuntimeClassInitialize(this, 0, 0);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v3);
  return (unsigned int)this;
}

```

## disassembly

```asm
0x14000def0  push    rbx
0x14000def2  sub     rsp, 70h
0x14000def6  mov     rbx, rcx
0x14000def9  lea     rdx, aFileopendialog_3; "FileOpenDialogBroker::RuntimeClassIniti"...
0x14000df00  lea     rcx, [rsp+78h+var_58]
0x14000df05  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000df0a  xor     r8d, r8d; void *
0x14000df0d  xor     edx, edx; struct IFileDialog *
0x14000df0f  mov     rcx, rbx; this
0x14000df12  call    ?RuntimeClassInitialize@FileOpenDialogBroker@Isolation@Security@Windows@@QEAAJPEAUIFileDialog@@PEAX@Z; Windows::Security::Isolation::FileOpenDialogBroker::RuntimeClassInitialize(IFileDialog *,void *)
0x14000df17  mov     ebx, eax
0x14000df19  lea     rcx, [rsp+78h+var_58]; this
0x14000df1e  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000df23  mov     eax, ebx
0x14000df25  jmp     short loc_14000DF2E
0x14000df27  mov     eax, [rsp+78h+arg_8]
0x14000df2e  add     rsp, 70h
0x14000df32  pop     rbx
0x14000df33  retn
```
