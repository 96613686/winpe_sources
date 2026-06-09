# Windows::Security::Isolation::FileSaveDialogBroker::RuntimeClassInitialize(IFileDialog *,void *)

- ea: `0x14000e044`
- end: `0x14000e112`
- name: `?RuntimeClassInitialize@FileSaveDialogBroker@Isolation@Security@Windows@@QEAAJPEAUIFileDialog@@PEAX@Z`
- size: `206`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileSaveDialogBroker *this, struct IFileDialog *, char *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e118`
- `0x140010a28`

## callees

- `0x140007c64`
- `0x140007df4`
- `0x140007e14`
- `0x140009194`
- `0x14000e044`
- `0x14000f8d0`
- `0x14000f9c0`
- `0x140014010`

## string_xrefs

- `0x14000e09e`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::FileSaveDialogBroker::RuntimeClassInitialize(
        Windows::Security::Isolation::FileSaveDialogBroker *this,
        struct IFileDialog *a2,
        char *a3)
{
  char *v6; // rcx
  Windows::Security::Isolation::FileDialogBrokerCommon *v7; // rcx
  struct IFileSaveDialog **v8; // r8
  int CommonFileSaveDialog; // eax
  HRESULT (__stdcall *QueryInterface)(IFileDialog *, const IID *const, void **); // rbx
  __int64 result; // rax
  const char *v12; // r9
  int v13[20]; // [rsp+20h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread(v13, "RuntimeClassInitialize");
  try
  {
    v6 = (char *)this + 120;
    if ( a2 )
    {
      QueryInterface = a2->lpVtbl->QueryInterface;
      wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(v6);
      ((void (__fastcall *)(struct IFileDialog *, GUID *, char *))QueryInterface)(
        a2,
        &GUID_84bccd23_5fde_4cdb_aea4_af64b83d78ab,
        (char *)this + 120);
    }
    else
    {
      wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(v6);
      CommonFileSaveDialog = Windows::Security::Isolation::FileDialogBrokerCommon::GetCommonFileSaveDialog(
                               v7,
                               (const struct _GUID *)((char *)this + 120),
                               v8);
      if ( CommonFileSaveDialog < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xBB,
          (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
          (const char *)(unsigned int)CommonFileSaveDialog,
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
                           (void *)0xCD,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x14000e044  mov     rax, rsp
0x14000e047  mov     [rax+18h], rbx
0x14000e04b  mov     [rax+20h], rsi
0x14000e04f  mov     [rax+8], rcx
0x14000e053  push    rdi
0x14000e054  push    r14
0x14000e056  push    r15
0x14000e058  sub     rsp, 70h
0x14000e05c  mov     r14, r8
0x14000e05f  mov     r15, rdx
0x14000e062  mov     rdi, rcx
0x14000e065  lea     rdx, aRuntimeclassin; "RuntimeClassInitialize"
0x14000e06c  lea     rcx, [rax-68h]
0x14000e070  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000e075  nop
0x14000e076  lea     rsi, [rdi+78h]
0x14000e07a  mov     rcx, rsi
0x14000e07d  test    r15, r15
0x14000e080  jnz     short loc_14000E0AF
0x14000e082  call    ?reset@?$com_ptr_t@UIFileDialogEvents@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(void)
0x14000e087  mov     rdx, rsi; struct _GUID *
0x14000e08a  call    ?GetCommonFileSaveDialog@FileDialogBrokerCommon@Isolation@Security@Windows@@YAJAEBU_GUID@@PEAPEAUIFileSaveDialog@@@Z; Windows::Security::Isolation::FileDialogBrokerCommon::GetCommonFileSaveDialog(_GUID const &,IFileSaveDialog * *)
0x14000e08f  mov     rcx, [rsp+88h]; this
0x14000e097  test    eax, eax
0x14000e099  jns     short loc_14000E0CF
0x14000e09b  mov     r9d, eax; char *
0x14000e09e  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000e0a5  mov     edx, 0BBh; void *
0x14000e0aa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000e0af  mov     rax, [r15]
0x14000e0b2  mov     rbx, [rax]
0x14000e0b5  call    ?reset@?$com_ptr_t@UIFileDialogEvents@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(void)
0x14000e0ba  mov     r8, rsi
0x14000e0bd  lea     rdx, _GUID_84bccd23_5fde_4cdb_aea4_af64b83d78ab
0x14000e0c4  mov     rcx, r15
0x14000e0c7  mov     rax, rbx
0x14000e0ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e0cf  lea     rax, [r14-1]
0x14000e0d3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000e0d7  ja      short loc_14000E0E6
0x14000e0d9  lea     rcx, [rdi+70h]
0x14000e0dd  mov     rdx, r14
0x14000e0e0  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14000e0e5  nop
0x14000e0e6  lea     rcx, [rsp+88h+var_68]; this
0x14000e0eb  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000e0f0  xor     eax, eax
0x14000e0f2  jmp     short loc_14000E0FB
0x14000e0f4  mov     eax, [rsp+88h+arg_8]
0x14000e0fb  lea     r11, [rsp+88h+var_18]
0x14000e100  mov     rbx, [r11+30h]
0x14000e104  mov     rsi, [r11+38h]
0x14000e108  mov     rsp, r11
0x14000e10b  pop     r15
0x14000e10d  pop     r14
0x14000e10f  pop     rdi
0x14000e110  retn
```
