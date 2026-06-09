# Windows::Security::Isolation::FileSaveDialogLegacyBroker::RuntimeClassInitialize(IFileDialog *,void *)

- ea: `0x14000e164`
- end: `0x14000e21a`
- name: `?RuntimeClassInitialize@FileSaveDialogLegacyBroker@Isolation@Security@Windows@@QEAAJPEAUIFileDialog@@PEAX@Z`
- size: `182`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileSaveDialogLegacyBroker *__hidden this, struct IFileDialog *, void *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e220`
- `0x140010aec`

## callees

- `0x140007cf8`
- `0x140007df4`
- `0x140007e14`
- `0x140009194`
- `0x1400092a8`
- `0x14000e164`
- `0x14000f8d0`
- `0x14000f9c0`

## string_xrefs

- `0x14000e1c0`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileSaveDialogLegacyBroker::RuntimeClassInitialize(
        IID *this,
        struct IFileDialog *a2,
        char *a3)
{
  __int64 *Data4; // rcx
  struct IFileDialog **v7; // r8
  int CommonFileSaveDialogLegacy; // eax
  __int64 result; // rax
  const char *v10; // r9
  int v11[26]; // [rsp+20h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v11, (__int64)"RuntimeClassInitialize");
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
      CommonFileSaveDialogLegacy = Windows::Security::Isolation::FileDialogBrokerCommon::GetCommonFileSaveDialogLegacy(
                                     this + 7,
                                     (IID *)((char *)this + 136),
                                     v7);
      if ( CommonFileSaveDialogLegacy < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DF,
          (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
          (const char *)(unsigned int)CommonFileSaveDialogLegacy,
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
                           (void *)0x1F1,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x14000e164  mov     [rsp+arg_10], rbx
0x14000e169  mov     [rsp+arg_0], rcx
0x14000e16e  push    rsi
0x14000e16f  push    rdi
0x14000e170  push    r14
0x14000e172  sub     rsp, 70h
0x14000e176  mov     rdi, r8
0x14000e179  mov     r14, rdx
0x14000e17c  mov     rbx, rcx
0x14000e17f  lea     rdx, aRuntimeclassin; "RuntimeClassInitialize"
0x14000e186  lea     rcx, [rsp+88h+var_68]
0x14000e18b  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000e190  nop
0x14000e191  lea     rsi, [rbx+88h]
0x14000e198  mov     rcx, rsi
0x14000e19b  test    r14, r14
0x14000e19e  jnz     short loc_14000E1D1
0x14000e1a0  call    ?reset@?$com_ptr_t@UIFileDialogEvents@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(void)
0x14000e1a5  lea     rcx, [rbx+70h]; rclsid
0x14000e1a9  mov     rdx, rsi; struct _GUID *
0x14000e1ac  call    ?GetCommonFileSaveDialogLegacy@FileDialogBrokerCommon@Isolation@Security@Windows@@YAJAEBU_GUID@@PEAPEAUIFileDialog@@@Z; Windows::Security::Isolation::FileDialogBrokerCommon::GetCommonFileSaveDialogLegacy(_GUID const &,IFileDialog * *)
0x14000e1b1  mov     rcx, [rsp+88h]; this
0x14000e1b9  test    eax, eax
0x14000e1bb  jns     short loc_14000E1D9
0x14000e1bd  mov     r9d, eax; char *
0x14000e1c0  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000e1c7  mov     edx, 1DFh; void *
0x14000e1cc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000e1d1  mov     rdx, r14
0x14000e1d4  call    ??4?$com_ptr_t@UIFileDialog@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@PEAUIFileDialog@@@Z; wil::com_ptr_t<IFileDialog,wil::err_exception_policy>::operator=(IFileDialog *)
0x14000e1d9  lea     rax, [rdi-1]
0x14000e1dd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000e1e1  ja      short loc_14000E1F3
0x14000e1e3  lea     rcx, [rbx+80h]
0x14000e1ea  mov     rdx, rdi
0x14000e1ed  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14000e1f2  nop
0x14000e1f3  lea     rcx, [rsp+88h+var_68]; this
0x14000e1f8  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000e1fd  xor     eax, eax
0x14000e1ff  jmp     short loc_14000E208
0x14000e201  mov     eax, [rsp+88h+arg_8]
0x14000e208  mov     rbx, [rsp+88h+arg_10]
0x14000e210  add     rsp, 70h
0x14000e214  pop     r14
0x14000e216  pop     rdi
0x14000e217  pop     rsi
0x14000e218  retn
```
