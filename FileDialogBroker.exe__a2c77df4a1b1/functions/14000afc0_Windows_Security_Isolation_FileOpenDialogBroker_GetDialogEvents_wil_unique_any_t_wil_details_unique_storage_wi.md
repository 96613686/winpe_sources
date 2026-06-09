# Windows::Security::Isolation::FileOpenDialogBroker::GetDialogEvents(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,IFileDialogEvents *)

- ea: `0x14000afc0`
- end: `0x14000b0de`
- name: `?GetDialogEvents@FileOpenDialogBroker@Isolation@Security@Windows@@EEBAPEAUIFileDialogEvents@@AEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAU5@@Z`
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
- `0x14000afc0`
- `0x14000f8d0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b08f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b08f`

## string_xrefs

- `0x14000b00a`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000b02b`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000b09c`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000afe0`: `FileOpenDialogBroker::GetDialogEvents`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileOpenDialogBroker::GetDialogEvents(
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
  FileDialogBrokerTraceLogging::WatchCurrentThread(v14, "FileOpenDialogBroker::GetDialogEvents");
  v6 = *a2;
  if ( (((unsigned __int64)*a2 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x90,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      (const char *)0x80070006LL,
      v10);
  if ( !a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x91,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
      (const char *)0x80004003LL,
      v10);
  *a2 = 0;
  v12 = v6;
  v18 = 0;
  v16 = 0;
  v13 = *(_QWORD *)(a1 + 120);
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
      (void *)0xA2,
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
0x14000afc0  mov     [rsp-8+arg_10], r8
0x14000afc5  push    rbp
0x14000afc6  push    rbx
0x14000afc7  push    rsi
0x14000afc8  push    rdi
0x14000afc9  push    r14
0x14000afcb  lea     rbp, [rsp-37h]
0x14000afd0  sub     rsp, 90h
0x14000afd7  mov     rdi, r8
0x14000afda  mov     rsi, rdx
0x14000afdd  mov     r14, rcx
0x14000afe0  lea     rdx, aFileopendialog; "FileOpenDialogBroker::GetDialogEvents"
0x14000afe7  lea     rcx, [rbp+57h+var_70]
0x14000afeb  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000aff0  nop
0x14000aff1  mov     rcx, [rbp+5Fh]; this
0x14000aff5  mov     rbx, [rsi]
0x14000aff8  lea     rax, [rbx+1]
0x14000affc  test    rax, 0FFFFFFFFFFFFFFFEh
0x14000b002  jnz     short loc_14000B01C
0x14000b004  mov     r9d, 80070006h; char *
0x14000b00a  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000b011  mov     edx, 90h; void *
0x14000b016  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000b01c  mov     rcx, [rbp+5Fh]; this
0x14000b020  test    rdi, rdi
0x14000b023  jnz     short loc_14000B03D
0x14000b025  mov     r9d, 80004003h; char *
0x14000b02b  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000b032  mov     edx, 91h; void *
0x14000b037  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000b03d  mov     qword ptr [rsi], 0
0x14000b044  mov     [rbp+57h+var_80], rbx
0x14000b048  mov     [rbp+57h+arg_18], 0
0x14000b050  mov     [rbp+57h+arg_8], 0
0x14000b057  mov     rax, [r14+78h]
0x14000b05b  mov     [rbp+57h+var_78], rax
0x14000b05f  lea     rcx, [rbp+57h+arg_18]
0x14000b063  call    ?reset@?$com_ptr_t@UIFileDialogEvents@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(void)
0x14000b068  lea     rax, [rbp+57h+arg_8]
0x14000b06c  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x14000b071  lea     r9, [rbp+57h+arg_10]
0x14000b075  lea     r8, [rbp+57h+var_80]
0x14000b079  lea     rdx, [rbp+57h+var_78]
0x14000b07d  lea     rcx, [rbp+57h+arg_18]
0x14000b081  call    ??$MakeAndInitialize@VFileDialogBrokerController@Isolation@Security@Windows@@UIFileDialogEvents@@PEAUIFileDialog@@AEAPEAXAEAPEAU5@W4FDBControllerType@234@@Details@WRL@Microsoft@@YAJPEAPEAUIFileDialogEvents@@$$QEAPEAUIFileDialog@@AEAPEAXAEAPEAU3@$$QEAW4FDBControllerType@Isolation@Security@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Isolation::FileDialogBrokerController,IFileDialogEvents,IFileDialog *,void * &,IFileDialogEvents * &,Windows::Security::Isolation::FDBControllerType>(IFileDialogEvents * *,IFileDialog * &&,void * &,IFileDialogEvents * &,Windows::Security::Isolation::FDBControllerType &&)
0x14000b086  mov     edi, eax
0x14000b088  test    eax, eax
0x14000b08a  jns     short loc_14000B0AE
0x14000b08c  mov     rcx, rbx; hObject
0x14000b08f  call    cs:__imp_CloseHandle
0x14000b095  mov     rcx, [rbp+5Fh]; this
0x14000b099  mov     r9d, edi; char *
0x14000b09c  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000b0a3  mov     edx, 0A2h; void *
0x14000b0a8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000b0ae  mov     rbx, [rbp+57h+arg_18]
0x14000b0b2  mov     [rbp+57h+arg_18], 0
0x14000b0ba  lea     rcx, [rbp+57h+arg_18]
0x14000b0be  call    ??1?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(void)
0x14000b0c3  nop
0x14000b0c4  lea     rcx, [rbp+57h+var_70]; this
0x14000b0c8  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000b0cd  mov     rax, rbx
0x14000b0d0  add     rsp, 90h
0x14000b0d7  pop     r14
0x14000b0d9  pop     rdi
0x14000b0da  pop     rsi
0x14000b0db  pop     rbx
0x14000b0dc  pop     rbp
0x14000b0dd  retn
```
