# Windows::Security::Isolation::FileOpenDialogLegacyBroker::GetDialogEvents(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,IFileDialogEvents *)

- ea: `0x14000b0f0`
- end: `0x14000b211`
- name: `?GetDialogEvents@FileOpenDialogLegacyBroker@Isolation@Security@Windows@@EEBAPEAUIFileDialogEvents@@AEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAU5@@Z`
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
- `0x14000b0f0`
- `0x14000f8d0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b1c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b1c2`

## string_xrefs

- `0x14000b13a`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000b15b`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000b1cf`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000b110`: `FileOpenDialogLegacyBroker::GetDialogEvents`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileOpenDialogLegacyBroker::GetDialogEvents(
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
  FileDialogBrokerTraceLogging::WatchCurrentThread(v14, "FileOpenDialogLegacyBroker::GetDialogEvents");
  v6 = *a2;
  if ( (((unsigned __int64)*a2 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B4,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      (const char *)0x80070006LL,
      v10);
  if ( !a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B5,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      (const char *)0x80004003LL,
      v10);
  *a2 = 0;
  v12 = v6;
  v18 = 0;
  v16 = 2;
  v13 = *(_QWORD *)(a1 + 136);
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
      (void *)0x1C6,
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
0x14000b0f0  mov     [rsp-8+arg_10], r8
0x14000b0f5  push    rbp
0x14000b0f6  push    rbx
0x14000b0f7  push    rsi
0x14000b0f8  push    rdi
0x14000b0f9  push    r14
0x14000b0fb  lea     rbp, [rsp-37h]
0x14000b100  sub     rsp, 90h
0x14000b107  mov     rdi, r8
0x14000b10a  mov     rsi, rdx
0x14000b10d  mov     r14, rcx
0x14000b110  lea     rdx, aFileopendialog_4; "FileOpenDialogLegacyBroker::GetDialogEv"...
0x14000b117  lea     rcx, [rbp+57h+var_70]
0x14000b11b  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000b120  nop
0x14000b121  mov     rcx, [rbp+5Fh]; this
0x14000b125  mov     rbx, [rsi]
0x14000b128  lea     rax, [rbx+1]
0x14000b12c  test    rax, 0FFFFFFFFFFFFFFFEh
0x14000b132  jnz     short loc_14000B14C
0x14000b134  mov     r9d, 80070006h; char *
0x14000b13a  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000b141  mov     edx, 1B4h; void *
0x14000b146  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000b14c  mov     rcx, [rbp+5Fh]; this
0x14000b150  test    rdi, rdi
0x14000b153  jnz     short loc_14000B16D
0x14000b155  mov     r9d, 80004003h; char *
0x14000b15b  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000b162  mov     edx, 1B5h; void *
0x14000b167  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000b16d  mov     qword ptr [rsi], 0
0x14000b174  mov     [rbp+57h+var_80], rbx
0x14000b178  mov     [rbp+57h+arg_18], 0
0x14000b180  mov     [rbp+57h+arg_8], 2
0x14000b187  mov     rax, [r14+88h]
0x14000b18e  mov     [rbp+57h+var_78], rax
0x14000b192  lea     rcx, [rbp+57h+arg_18]
0x14000b196  call    ?reset@?$com_ptr_t@UIFileDialogEvents@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(void)
0x14000b19b  lea     rax, [rbp+57h+arg_8]
0x14000b19f  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x14000b1a4  lea     r9, [rbp+57h+arg_10]
0x14000b1a8  lea     r8, [rbp+57h+var_80]
0x14000b1ac  lea     rdx, [rbp+57h+var_78]
0x14000b1b0  lea     rcx, [rbp+57h+arg_18]
0x14000b1b4  call    ??$MakeAndInitialize@VFileDialogBrokerController@Isolation@Security@Windows@@UIFileDialogEvents@@PEAUIFileDialog@@AEAPEAXAEAPEAU5@W4FDBControllerType@234@@Details@WRL@Microsoft@@YAJPEAPEAUIFileDialogEvents@@$$QEAPEAUIFileDialog@@AEAPEAXAEAPEAU3@$$QEAW4FDBControllerType@Isolation@Security@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Isolation::FileDialogBrokerController,IFileDialogEvents,IFileDialog *,void * &,IFileDialogEvents * &,Windows::Security::Isolation::FDBControllerType>(IFileDialogEvents * *,IFileDialog * &&,void * &,IFileDialogEvents * &,Windows::Security::Isolation::FDBControllerType &&)
0x14000b1b9  mov     edi, eax
0x14000b1bb  test    eax, eax
0x14000b1bd  jns     short loc_14000B1E1
0x14000b1bf  mov     rcx, rbx; hObject
0x14000b1c2  call    cs:__imp_CloseHandle
0x14000b1c8  mov     rcx, [rbp+5Fh]; this
0x14000b1cc  mov     r9d, edi; char *
0x14000b1cf  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000b1d6  mov     edx, 1C6h; void *
0x14000b1db  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000b1e1  mov     rbx, [rbp+57h+arg_18]
0x14000b1e5  mov     [rbp+57h+arg_18], 0
0x14000b1ed  lea     rcx, [rbp+57h+arg_18]
0x14000b1f1  call    ??1?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(void)
0x14000b1f6  nop
0x14000b1f7  lea     rcx, [rbp+57h+var_70]; this
0x14000b1fb  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000b200  mov     rax, rbx
0x14000b203  add     rsp, 90h
0x14000b20a  pop     r14
0x14000b20c  pop     rdi
0x14000b20d  pop     rsi
0x14000b20e  pop     rbx
0x14000b20f  pop     rbp
0x14000b210  retn
```
