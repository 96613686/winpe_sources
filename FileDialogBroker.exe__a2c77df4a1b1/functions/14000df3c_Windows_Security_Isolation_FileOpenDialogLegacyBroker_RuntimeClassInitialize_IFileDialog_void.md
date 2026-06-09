# Windows::Security::Isolation::FileOpenDialogLegacyBroker::RuntimeClassInitialize(IFileDialog *,void *)

- ea: `0x14000df3c`
- end: `0x14000dff2`
- name: `?RuntimeClassInitialize@FileOpenDialogLegacyBroker@Isolation@Security@Windows@@QEAAJPEAUIFileDialog@@PEAX@Z`
- size: `182`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileOpenDialogLegacyBroker *__hidden this, struct IFileDialog *, void *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000dff8`
- `0x140010964`

## callees

- `0x140007bcc`
- `0x140007df4`
- `0x140007e14`
- `0x140009194`
- `0x1400092a8`
- `0x14000df3c`
- `0x14000f8d0`
- `0x14000f9c0`

## string_xrefs

- `0x14000df98`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000df57`: `FileOpenDialogLegacyBroker::RuntimeClassInitialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileOpenDialogLegacyBroker::RuntimeClassInitialize(
        IID *this,
        struct IFileDialog *a2,
        char *a3)
{
  __int64 *Data4; // rcx
  struct IFileDialog **v7; // r8
  int CommonFileOpenDialogLegacy; // eax
  __int64 result; // rax
  const char *v10; // r9
  int v11[26]; // [rsp+20h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(
    (__int64)v11,
    (__int64)"FileOpenDialogLegacyBroker::RuntimeClassInitialize");
  try
  {
    Data4 = (__int64 *)this[8].Data4;
    if ( a2 )
    {
      wil::com_ptr_t<IFileDialog,wil::err_exception_policy>::operator=(Data4, (__int64)a2);
    }
    else
    {
      wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(Data4);
      CommonFileOpenDialogLegacy = Windows::Security::Isolation::FileDialogBrokerCommon::GetCommonFileOpenDialogLegacy(
                                     this + 7,
                                     (IID *)((char *)this + 136),
                                     v7);
      if ( CommonFileOpenDialogLegacy < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x14C,
          (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
          (const char *)(unsigned int)CommonFileOpenDialogLegacy,
          v11[0]);
    }
    if ( (unsigned __int64)(a3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &this[8],
        a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v11);
    result = 0;
  }
  catch ( ... )
  {
    wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(this[8].Data4);
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x15D,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x14000df3c  mov     [rsp+arg_10], rbx
0x14000df41  mov     [rsp+arg_0], rcx
0x14000df46  push    rsi
0x14000df47  push    rdi
0x14000df48  push    r14
0x14000df4a  sub     rsp, 70h
0x14000df4e  mov     rdi, r8
0x14000df51  mov     r14, rdx
0x14000df54  mov     rbx, rcx
0x14000df57  lea     rdx, aFileopendialog_1; "FileOpenDialogLegacyBroker::RuntimeClas"...
0x14000df5e  lea     rcx, [rsp+88h+var_68]
0x14000df63  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000df68  nop
0x14000df69  lea     rsi, [rbx+88h]
0x14000df70  mov     rcx, rsi
0x14000df73  test    r14, r14
0x14000df76  jnz     short loc_14000DFA9
0x14000df78  call    ?reset@?$com_ptr_t@UIFileDialogEvents@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(void)
0x14000df7d  lea     rcx, [rbx+70h]; rclsid
0x14000df81  mov     rdx, rsi; struct _GUID *
0x14000df84  call    ?GetCommonFileOpenDialogLegacy@FileDialogBrokerCommon@Isolation@Security@Windows@@YAJAEBU_GUID@@PEAPEAUIFileDialog@@@Z; Windows::Security::Isolation::FileDialogBrokerCommon::GetCommonFileOpenDialogLegacy(_GUID const &,IFileDialog * *)
0x14000df89  mov     rcx, [rsp+88h]; this
0x14000df91  test    eax, eax
0x14000df93  jns     short loc_14000DFB1
0x14000df95  mov     r9d, eax; char *
0x14000df98  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000df9f  mov     edx, 14Ch; void *
0x14000dfa4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000dfa9  mov     rdx, r14
0x14000dfac  call    ??4?$com_ptr_t@UIFileDialog@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@PEAUIFileDialog@@@Z; wil::com_ptr_t<IFileDialog,wil::err_exception_policy>::operator=(IFileDialog *)
0x14000dfb1  lea     rax, [rdi-1]
0x14000dfb5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000dfb9  ja      short loc_14000DFCB
0x14000dfbb  lea     rcx, [rbx+80h]
0x14000dfc2  mov     rdx, rdi
0x14000dfc5  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14000dfca  nop
0x14000dfcb  lea     rcx, [rsp+88h+var_68]; this
0x14000dfd0  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000dfd5  xor     eax, eax
0x14000dfd7  jmp     short loc_14000DFE0
0x14000dfd9  mov     eax, [rsp+88h+arg_8]
0x14000dfe0  mov     rbx, [rsp+88h+arg_10]
0x14000dfe8  add     rsp, 70h
0x14000dfec  pop     r14
0x14000dfee  pop     rdi
0x14000dfef  pop     rsi
0x14000dff0  retn
```
