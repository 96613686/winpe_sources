# Windows::Security::Isolation::FileOpenDialogBroker::RuntimeClassInitialize(IFileDialog *,void *)

- ea: `0x14000de1c`
- end: `0x14000dee9`
- name: `?RuntimeClassInitialize@FileOpenDialogBroker@Isolation@Security@Windows@@QEAAJPEAUIFileDialog@@PEAX@Z`
- size: `205`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileOpenDialogBroker *this, struct IFileDialog *, char *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000def0`
- `0x1400108a0`

## callees

- `0x140007b38`
- `0x140007df4`
- `0x140007e14`
- `0x140009194`
- `0x14000de1c`
- `0x14000f8d0`
- `0x14000f9c0`
- `0x140014010`

## string_xrefs

- `0x14000de3d`: `FileOpenDialogBroker::RuntimeClassInitialize`
- `0x14000de76`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileOpenDialogBroker::RuntimeClassInitialize(
        Windows::Security::Isolation::FileOpenDialogBroker *this,
        struct IFileDialog *a2,
        char *a3)
{
  char *v6; // rcx
  Windows::Security::Isolation::FileDialogBrokerCommon *v7; // rcx
  struct IFileOpenDialog **v8; // r8
  int CommonFileOpenDialog; // eax
  HRESULT (__stdcall *QueryInterface)(IFileDialog *, const IID *const, void **); // rbx
  __int64 result; // rax
  const char *v12; // r9
  int v13[20]; // [rsp+20h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v13, "FileOpenDialogBroker::RuntimeClassInitialize");
  try
  {
    v6 = (char *)this + 120;
    if ( a2 )
    {
      QueryInterface = a2->lpVtbl->QueryInterface;
      wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(v6);
      ((void (__fastcall *)(struct IFileDialog *, GUID *, char *))QueryInterface)(
        a2,
        &GUID_d57c7288_d4ad_4768_be02_9d969532d960,
        (char *)this + 120);
    }
    else
    {
      wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(v6);
      CommonFileOpenDialog = Windows::Security::Isolation::FileDialogBrokerCommon::GetCommonFileOpenDialog(
                               v7,
                               (const struct _GUID *)((char *)this + 120),
                               v8);
      if ( CommonFileOpenDialog < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x29,
          (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
          (const char *)(unsigned int)CommonFileOpenDialog,
          v13[0]);
    }
    if ( (unsigned __int64)(a3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        (char *)this + 112,
        a3);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v13);
    result = 0;
  }
  catch ( ... )
  {
    wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset((char *)this + 120);
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3B,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x14000de1c  mov     rax, rsp
0x14000de1f  mov     [rax+18h], rbx
0x14000de23  mov     [rax+20h], rsi
0x14000de27  mov     [rax+8], rcx
0x14000de2b  push    rdi
0x14000de2c  push    r14
0x14000de2e  push    r15
0x14000de30  sub     rsp, 70h
0x14000de34  mov     r14, r8
0x14000de37  mov     r15, rdx
0x14000de3a  mov     rdi, rcx
0x14000de3d  lea     rdx, aFileopendialog_3; "FileOpenDialogBroker::RuntimeClassIniti"...
0x14000de44  lea     rcx, [rax-68h]
0x14000de48  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000de4d  nop
0x14000de4e  lea     rsi, [rdi+78h]
0x14000de52  mov     rcx, rsi
0x14000de55  test    r15, r15
0x14000de58  jnz     short loc_14000DE86
0x14000de5a  call    ?reset@?$com_ptr_t@UIFileDialogEvents@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(void)
0x14000de5f  mov     rdx, rsi; struct _GUID *
0x14000de62  call    ?GetCommonFileOpenDialog@FileDialogBrokerCommon@Isolation@Security@Windows@@YAJAEBU_GUID@@PEAPEAUIFileOpenDialog@@@Z; Windows::Security::Isolation::FileDialogBrokerCommon::GetCommonFileOpenDialog(_GUID const &,IFileOpenDialog * *)
0x14000de67  mov     rcx, [rsp+88h]; this
0x14000de6f  test    eax, eax
0x14000de71  jns     short loc_14000DEA6
0x14000de73  mov     r9d, eax; char *
0x14000de76  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000de7d  lea     edx, [r15+29h]; void *
0x14000de81  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000de86  mov     rax, [r15]
0x14000de89  mov     rbx, [rax]
0x14000de8c  call    ?reset@?$com_ptr_t@UIFileDialogEvents@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(void)
0x14000de91  mov     r8, rsi
0x14000de94  lea     rdx, _GUID_d57c7288_d4ad_4768_be02_9d969532d960
0x14000de9b  mov     rcx, r15
0x14000de9e  mov     rax, rbx
0x14000dea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dea6  lea     rax, [r14-1]
0x14000deaa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000deae  ja      short loc_14000DEBD
0x14000deb0  lea     rcx, [rdi+70h]
0x14000deb4  mov     rdx, r14
0x14000deb7  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14000debc  nop
0x14000debd  lea     rcx, [rsp+88h+var_68]; this
0x14000dec2  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000dec7  xor     eax, eax
0x14000dec9  jmp     short loc_14000DED2
0x14000decb  mov     eax, [rsp+88h+arg_8]
0x14000ded2  lea     r11, [rsp+88h+var_18]
0x14000ded7  mov     rbx, [r11+30h]
0x14000dedb  mov     rsi, [r11+38h]
0x14000dedf  mov     rsp, r11
0x14000dee2  pop     r15
0x14000dee4  pop     r14
0x14000dee6  pop     rdi
0x14000dee7  retn
```
