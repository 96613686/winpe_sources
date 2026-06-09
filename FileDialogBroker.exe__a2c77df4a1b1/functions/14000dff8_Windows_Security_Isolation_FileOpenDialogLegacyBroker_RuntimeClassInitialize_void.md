# Windows::Security::Isolation::FileOpenDialogLegacyBroker::RuntimeClassInitialize(void)

- ea: `0x14000dff8`
- end: `0x14000e03d`
- name: `?RuntimeClassInitialize@FileOpenDialogLegacyBroker@Isolation@Security@Windows@@QEAAJXZ`
- size: `69`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileOpenDialogLegacyBroker *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400085fc`

## callees

- `0x140009194`
- `0x14000df3c`
- `0x14000dff8`
- `0x14000f8d0`

## string_xrefs

- `0x14000e001`: `FileOpenDialogLegacyBroker::RuntimeClassInitialize`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileOpenDialogLegacyBroker::RuntimeClassInitialize(IID *this)
{
  _BYTE v3[88]; // [rsp+20h] [rbp-58h] BYREF

  FileDialogBrokerTraceLogging::WatchCurrentThread(
    (__int64)v3,
    (__int64)"FileOpenDialogLegacyBroker::RuntimeClassInitialize");
  LODWORD(this) = Windows::Security::Isolation::FileOpenDialogLegacyBroker::RuntimeClassInitialize(this, 0, 0);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v3);
  return (unsigned int)this;
}

```

## disassembly

```asm
0x14000dff8  push    rbx
0x14000dffa  sub     rsp, 70h
0x14000dffe  mov     rbx, rcx
0x14000e001  lea     rdx, aFileopendialog_1; "FileOpenDialogLegacyBroker::RuntimeClas"...
0x14000e008  lea     rcx, [rsp+78h+var_58]
0x14000e00d  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000e012  xor     r8d, r8d; void *
0x14000e015  xor     edx, edx; struct IFileDialog *
0x14000e017  mov     rcx, rbx; this
0x14000e01a  call    ?RuntimeClassInitialize@FileOpenDialogLegacyBroker@Isolation@Security@Windows@@QEAAJPEAUIFileDialog@@PEAX@Z; Windows::Security::Isolation::FileOpenDialogLegacyBroker::RuntimeClassInitialize(IFileDialog *,void *)
0x14000e01f  mov     ebx, eax
0x14000e021  lea     rcx, [rsp+78h+var_58]; this
0x14000e026  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000e02b  mov     eax, ebx
0x14000e02d  jmp     short loc_14000E036
0x14000e02f  mov     eax, [rsp+78h+arg_8]
0x14000e036  add     rsp, 70h
0x14000e03a  pop     rbx
0x14000e03b  retn
```
