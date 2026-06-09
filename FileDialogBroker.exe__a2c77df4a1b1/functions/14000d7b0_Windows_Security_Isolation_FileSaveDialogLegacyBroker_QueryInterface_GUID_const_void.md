# Windows::Security::Isolation::FileSaveDialogLegacyBroker::QueryInterface(_GUID const &,void * *)

- ea: `0x14000d7b0`
- end: `0x14000d8ad`
- name: `?QueryInterface@FileSaveDialogLegacyBroker@Isolation@Security@Windows@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `253`
- prototype: `int(Windows::Security::Isolation::FileSaveDialogLegacyBroker *__hidden this, const struct _GUID *, void **)`
- caller_count: `8`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000876c`
- `0x14000d8c0`
- `0x14000d8d0`
- `0x14000d8e0`
- `0x14000d8f0`
- `0x14000d900`
- `0x14000d910`
- `0x140010aec`

## callees

- `0x140007df4`
- `0x140009194`
- `0x14000a00c`
- `0x14000cbec`
- `0x14000d7b0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000d805`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000d873`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000d7cd`: `FileSaveDialogLegacyBroker::QueryInterface`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Security::Isolation::FileSaveDialogLegacyBroker::QueryInterface(
        Windows::Security::Isolation::FileSaveDialogLegacyBroker *this,
        const struct _GUID *a2,
        void **a3)
{
  __int64 v6; // rax
  int CanCastTo; // edi
  const char *v8; // r9
  __int64 result; // rax
  int v10[20]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v10, (__int64)"FileSaveDialogLegacyBroker::QueryInterface");
  v6 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IFileOpenDialog.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IFileOpenDialog.Data1 )
    v6 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IFileOpenDialog.Data4;
  try
  {
    if ( !v6 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1FD,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)0x80004002LL,
        v10[0]);
    *a3 = 0;
    if ( (unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046) )
    {
      *a3 = this;
      (*(void (__fastcall **)(Windows::Security::Isolation::FileSaveDialogLegacyBroker *))(*(_QWORD *)this + 8LL))(this);
      CanCastTo = 0;
    }
    else
    {
      CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<10>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<10>,IModalWindow,IFileDialog,IFileDialogInternal,IFileDialogPrivate,IFileOpenDialog,IFileSaveDialog,IFileDialogCustomize>>>::CanCastTo(
                    (__int64)this,
                    a2);
      if ( CanCastTo >= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
    }
    if ( CanCastTo < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x200,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)CanCastTo,
        v10[0]);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
    result = 0;
  }
  catch ( ... )
  {
    *a3 = 0;
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x206,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000d7b0  mov     rax, rsp
0x14000d7b3  mov     [rax+8], rbx
0x14000d7b7  mov     [rax+10h], rsi
0x14000d7bb  mov     [rax+18h], r8
0x14000d7bf  push    rdi
0x14000d7c0  sub     rsp, 70h
0x14000d7c4  mov     rbx, r8
0x14000d7c7  mov     rdi, rdx
0x14000d7ca  mov     rsi, rcx
0x14000d7cd  lea     rdx, aFilesavedialog_1; "FileSaveDialogLegacyBroker::QueryInterf"...
0x14000d7d4  lea     rcx, [rax-58h]
0x14000d7d8  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000d7dd  nop
0x14000d7de  mov     rax, [rdi]
0x14000d7e1  sub     rax, qword ptr cs:IID_IFileOpenDialog.Data1
0x14000d7e8  jnz     short loc_14000D7F5
0x14000d7ea  mov     rax, [rdi+8]
0x14000d7ee  sub     rax, qword ptr cs:IID_IFileOpenDialog.Data4
0x14000d7f5  test    rax, rax
0x14000d7f8  jnz     short loc_14000D817
0x14000d7fa  mov     rcx, [rsp+78h]; this
0x14000d7ff  mov     r9d, 80004002h; char *
0x14000d805  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000d80c  mov     edx, 1FDh; void *
0x14000d811  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000d817  mov     qword ptr [rbx], 0
0x14000d81e  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x14000d825  mov     rcx, rdi; struct _GUID *
0x14000d828  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x14000d82d  mov     rcx, rsi
0x14000d830  test    eax, eax
0x14000d832  jnz     short loc_14000D856
0x14000d834  mov     r8, rbx
0x14000d837  mov     rdx, rdi
0x14000d83a  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$09@WRL@Microsoft@@$0A@U?$ImplementsMarker@U?$Implements@U?$RuntimeClassFlags@$09@WRL@Microsoft@@UIModalWindow@@UIFileDialog@@UIFileDialogInternal@@UIFileDialogPrivate@@UIFileOpenDialog@@UIFileSaveDialog@@UIFileDialogCustomize@@@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<10>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<10>,IModalWindow,IFileDialog,IFileDialogInternal,IFileDialogPrivate,IFileOpenDialog,IFileSaveDialog,IFileDialogCustomize>>>::CanCastTo(_GUID const &,void * *,bool *)
0x14000d83f  mov     edi, eax
0x14000d841  test    eax, eax
0x14000d843  js      short loc_14000D867
0x14000d845  mov     rcx, [rbx]
0x14000d848  mov     rax, [rcx]
0x14000d84b  mov     rax, [rax+8]
0x14000d84f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d854  jmp     short loc_14000D867
0x14000d856  mov     [rbx], rsi
0x14000d859  mov     rax, [rsi]
0x14000d85c  mov     rax, [rax+8]
0x14000d860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d865  xor     edi, edi
0x14000d867  mov     rcx, [rsp+78h]; this
0x14000d86c  test    edi, edi
0x14000d86e  jns     short loc_14000D885
0x14000d870  mov     r9d, edi; char *
0x14000d873  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000d87a  mov     edx, 200h; void *
0x14000d87f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000d885  lea     rcx, [rsp+78h+var_58]; this
0x14000d88a  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000d88f  xor     eax, eax
0x14000d891  jmp     short loc_14000D89A
0x14000d893  mov     eax, [rsp+78h+arg_18]
0x14000d89a  lea     r11, [rsp+78h+var_8]
0x14000d89f  mov     rbx, [r11+10h]
0x14000d8a3  mov     rsi, [r11+18h]
0x14000d8a7  mov     rsp, r11
0x14000d8aa  pop     rdi
0x14000d8ab  retn
```
