# Windows::Security::Isolation::FileSaveDialogLegacyBroker::GetDialogEvents(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,IFileDialogEvents *)

- ea: `0x14000b350`
- end: `0x14000b471`
- name: `?GetDialogEvents@FileSaveDialogLegacyBroker@Isolation@Security@Windows@@EEBAPEAUIFileDialogEvents@@AEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAU5@@Z`
- size: `289`
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
- `0x14000b350`
- `0x14000f8d0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b422`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b422`

## string_xrefs

- `0x14000b39a`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000b3bb`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000b42f`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000b370`: `FileSaveDialogLegacyBroker::GetDialogEvents`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileSaveDialogLegacyBroker::GetDialogEvents(
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
  FileDialogBrokerTraceLogging::WatchCurrentThread(v14, "FileSaveDialogLegacyBroker::GetDialogEvents");
  v6 = *a2;
  if ( (((unsigned __int64)*a2 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x248,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      (const char *)0x80070006LL,
      v10);
  if ( !a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x249,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      (const char *)0x80004003LL,
      v10);
  *a2 = 0;
  v12 = v6;
  v18 = 0;
  v16 = 3;
  v13 = *(_QWORD *)(a1 + 136);
  wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(&v18);
  v7 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Isolation::FileDialogBrokerController,IFileDialogEvents,IFileDialog *,void * &,IFileDialogEvents * &,enum Windows::Security::Isolation::FDBControllerType>(
         (unsigned int)&v18,
         (unsigned int)&v13,
         (unsigned int)&v12,
         (unsigned int)&v17,
         (__int64)&v16);
  if ( v7 < 0 )
  {
    CloseHandle(v6);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x25A,
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
0x14000b350  mov     [rsp-8+arg_10], r8
0x14000b355  push    rbp
0x14000b356  push    rbx
0x14000b357  push    rsi
0x14000b358  push    rdi
0x14000b359  push    r14
0x14000b35b  lea     rbp, [rsp-37h]
0x14000b360  sub     rsp, 90h
0x14000b367  mov     rdi, r8
0x14000b36a  mov     rsi, rdx
0x14000b36d  mov     r14, rcx
0x14000b370  lea     rdx, aFilesavedialog_2; "FileSaveDialogLegacyBroker::GetDialogEv"...
0x14000b377  lea     rcx, [rbp+57h+var_70]
0x14000b37b  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000b380  nop
0x14000b381  mov     rcx, [rbp+5Fh]; this
0x14000b385  mov     rbx, [rsi]
0x14000b388  lea     rax, [rbx+1]
0x14000b38c  test    rax, 0FFFFFFFFFFFFFFFEh
0x14000b392  jnz     short loc_14000B3AC
0x14000b394  mov     r9d, 80070006h; char *
0x14000b39a  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000b3a1  mov     edx, 248h; void *
0x14000b3a6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000b3ac  mov     rcx, [rbp+5Fh]; this
0x14000b3b0  test    rdi, rdi
0x14000b3b3  jnz     short loc_14000B3CD
0x14000b3b5  mov     r9d, 80004003h; char *
0x14000b3bb  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000b3c2  mov     edx, 249h; void *
0x14000b3c7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000b3cd  mov     qword ptr [rsi], 0
0x14000b3d4  mov     [rbp+57h+var_80], rbx
0x14000b3d8  mov     [rbp+57h+arg_18], 0
0x14000b3e0  mov     [rbp+57h+arg_8], 3
0x14000b3e7  mov     rax, [r14+88h]
0x14000b3ee  mov     [rbp+57h+var_78], rax
0x14000b3f2  lea     rcx, [rbp+57h+arg_18]
0x14000b3f6  call    ?reset@?$com_ptr_t@UIFileDialogEvents@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(void)
0x14000b3fb  lea     rax, [rbp+57h+arg_8]
0x14000b3ff  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x14000b404  lea     r9, [rbp+57h+arg_10]
0x14000b408  lea     r8, [rbp+57h+var_80]
0x14000b40c  lea     rdx, [rbp+57h+var_78]
0x14000b410  lea     rcx, [rbp+57h+arg_18]
0x14000b414  call    ??$MakeAndInitialize@VFileDialogBrokerController@Isolation@Security@Windows@@UIFileDialogEvents@@PEAUIFileDialog@@AEAPEAXAEAPEAU5@W4FDBControllerType@234@@Details@WRL@Microsoft@@YAJPEAPEAUIFileDialogEvents@@$$QEAPEAUIFileDialog@@AEAPEAXAEAPEAU3@$$QEAW4FDBControllerType@Isolation@Security@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Isolation::FileDialogBrokerController,IFileDialogEvents,IFileDialog *,void * &,IFileDialogEvents * &,Windows::Security::Isolation::FDBControllerType>(IFileDialogEvents * *,IFileDialog * &&,void * &,IFileDialogEvents * &,Windows::Security::Isolation::FDBControllerType &&)
0x14000b419  mov     edi, eax
0x14000b41b  test    eax, eax
0x14000b41d  jns     short loc_14000B441
0x14000b41f  mov     rcx, rbx; hObject
0x14000b422  call    cs:__imp_CloseHandle
0x14000b428  mov     rcx, [rbp+5Fh]; this
0x14000b42c  mov     r9d, edi; char *
0x14000b42f  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000b436  mov     edx, 25Ah; void *
0x14000b43b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000b441  mov     rbx, [rbp+57h+arg_18]
0x14000b445  mov     [rbp+57h+arg_18], 0
0x14000b44d  lea     rcx, [rbp+57h+arg_18]
0x14000b451  call    ??1?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(void)
0x14000b456  nop
0x14000b457  lea     rcx, [rbp+57h+var_70]; this
0x14000b45b  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000b460  mov     rax, rbx
0x14000b463  add     rsp, 90h
0x14000b46a  pop     r14
0x14000b46c  pop     rdi
0x14000b46d  pop     rsi
0x14000b46e  pop     rbx
0x14000b46f  pop     rbp
0x14000b470  retn
```
