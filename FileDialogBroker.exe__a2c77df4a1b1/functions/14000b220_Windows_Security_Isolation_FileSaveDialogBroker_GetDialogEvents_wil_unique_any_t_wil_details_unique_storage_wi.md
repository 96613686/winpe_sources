# Windows::Security::Isolation::FileSaveDialogBroker::GetDialogEvents(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,IFileDialogEvents *)

- ea: `0x14000b220`
- end: `0x14000b33e`
- name: `?GetDialogEvents@FileSaveDialogBroker@Isolation@Security@Windows@@EEBAPEAUIFileDialogEvents@@AEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAU5@@Z`
- size: `286`
- prototype: `__int64 __fastcall(__int64, void **, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400066d0`
- `0x140007df4`
- `0x140007e14`
- `0x14000842c`
- `0x140009194`
- `0x14000b220`
- `0x14000f8d0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b2ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b2ef`

## string_xrefs

- `0x14000b26a`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000b28b`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000b2fc`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000b240`: `FileSaveDialogBroker::GetDialogEvents`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileSaveDialogBroker::GetDialogEvents(
        __int64 a1,
        void **a2,
        __int64 a3)
{
  void *v6; // rbx
  int v7; // edi
  __int64 v8; // rbx
  int v10; // [rsp+20h] [rbp-39h]
  int v11; // [rsp+20h] [rbp-39h]
  void *v12; // [rsp+30h] [rbp-29h] BYREF
  __int64 v13; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v14[112]; // [rsp+40h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  int v16; // [rsp+C8h] [rbp+6Fh] BYREF
  __int64 v17; // [rsp+D0h] [rbp+77h] BYREF
  __int64 v18; // [rsp+D8h] [rbp+7Fh] BYREF

  v17 = a3;
  FileDialogBrokerTraceLogging::WatchCurrentThread(v14, "FileSaveDialogBroker::GetDialogEvents");
  v6 = *a2;
  if ( (((unsigned __int64)*a2 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x121,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      (const char *)0x80070006LL,
      v10);
  if ( !a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x122,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      (const char *)0x80004003LL,
      v10);
  *a2 = 0;
  v12 = v6;
  v18 = 0;
  v16 = 1;
  v13 = *(_QWORD *)(a1 + 120);
  wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(&v18);
  v7 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Isolation::FileDialogBrokerController,IFileDialogEvents,IFileDialog *,void * &,IFileDialogEvents * &,enum Windows::Security::Isolation::FDBControllerType>(
         &v18,
         &v13,
         (__int64 *)&v12,
         &v17,
         &v16);
  if ( v7 < 0 )
  {
    CloseHandle(v6);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x133,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      (const char *)(unsigned int)v7,
      v11);
  }
  v8 = v18;
  v18 = 0;
  wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(&v18);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v14);
  return v8;
}

```

## disassembly

```asm
0x14000b220  mov     [rsp-8+arg_10], r8
0x14000b225  push    rbp
0x14000b226  push    rbx
0x14000b227  push    rsi
0x14000b228  push    rdi
0x14000b229  push    r14
0x14000b22b  lea     rbp, [rsp-37h]
0x14000b230  sub     rsp, 90h
0x14000b237  mov     rdi, r8
0x14000b23a  mov     rsi, rdx
0x14000b23d  mov     r14, rcx
0x14000b240  lea     rdx, aFilesavedialog_0; "FileSaveDialogBroker::GetDialogEvents"
0x14000b247  lea     rcx, [rbp+57h+var_70]
0x14000b24b  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000b250  nop
0x14000b251  mov     rcx, [rbp+5Fh]; this
0x14000b255  mov     rbx, [rsi]
0x14000b258  lea     rax, [rbx+1]
0x14000b25c  test    rax, 0FFFFFFFFFFFFFFFEh
0x14000b262  jnz     short loc_14000B27C
0x14000b264  mov     r9d, 80070006h; char *
0x14000b26a  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000b271  mov     edx, 121h; void *
0x14000b276  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000b27c  mov     rcx, [rbp+5Fh]; this
0x14000b280  test    rdi, rdi
0x14000b283  jnz     short loc_14000B29D
0x14000b285  mov     r9d, 80004003h; char *
0x14000b28b  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000b292  mov     edx, 122h; void *
0x14000b297  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000b29d  mov     qword ptr [rsi], 0
0x14000b2a4  mov     [rbp+57h+var_80], rbx
0x14000b2a8  mov     [rbp+57h+arg_18], 0
0x14000b2b0  mov     [rbp+57h+arg_8], 1
0x14000b2b7  mov     rax, [r14+78h]
0x14000b2bb  mov     [rbp+57h+var_78], rax
0x14000b2bf  lea     rcx, [rbp+57h+arg_18]
0x14000b2c3  call    ?reset@?$com_ptr_t@UIFileDialogEvents@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(void)
0x14000b2c8  lea     rax, [rbp+57h+arg_8]
0x14000b2cc  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x14000b2d1  lea     r9, [rbp+57h+arg_10]
0x14000b2d5  lea     r8, [rbp+57h+var_80]
0x14000b2d9  lea     rdx, [rbp+57h+var_78]
0x14000b2dd  lea     rcx, [rbp+57h+arg_18]
0x14000b2e1  call    ??$MakeAndInitialize@VFileDialogBrokerController@Isolation@Security@Windows@@UIFileDialogEvents@@PEAUIFileDialog@@AEAPEAXAEAPEAU5@W4FDBControllerType@234@@Details@WRL@Microsoft@@YAJPEAPEAUIFileDialogEvents@@$$QEAPEAUIFileDialog@@AEAPEAXAEAPEAU3@$$QEAW4FDBControllerType@Isolation@Security@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Isolation::FileDialogBrokerController,IFileDialogEvents,IFileDialog *,void * &,IFileDialogEvents * &,Windows::Security::Isolation::FDBControllerType>(IFileDialogEvents * *,IFileDialog * &&,void * &,IFileDialogEvents * &,Windows::Security::Isolation::FDBControllerType &&)
0x14000b2e6  mov     edi, eax
0x14000b2e8  test    eax, eax
0x14000b2ea  jns     short loc_14000B30E
0x14000b2ec  mov     rcx, rbx; hObject
0x14000b2ef  call    cs:__imp_CloseHandle
0x14000b2f5  mov     rcx, [rbp+5Fh]; this
0x14000b2f9  mov     r9d, edi; char *
0x14000b2fc  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000b303  mov     edx, 133h; void *
0x14000b308  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000b30e  mov     rbx, [rbp+57h+arg_18]
0x14000b312  mov     [rbp+57h+arg_18], 0
0x14000b31a  lea     rcx, [rbp+57h+arg_18]
0x14000b31e  call    ??1?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(void)
0x14000b323  nop
0x14000b324  lea     rcx, [rbp+57h+var_70]; this
0x14000b328  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000b32d  mov     rax, rbx
0x14000b330  add     rsp, 90h
0x14000b337  pop     r14
0x14000b339  pop     rdi
0x14000b33a  pop     rsi
0x14000b33b  pop     rbx
0x14000b33c  pop     rbp
0x14000b33d  retn
```
