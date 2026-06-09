# Windows::Security::Isolation::FileSaveDialogBroker::QueryInterface(_GUID const &,void * *)

- ea: `0x14000d640`
- end: `0x14000d73d`
- name: `?QueryInterface@FileSaveDialogBroker@Isolation@Security@Windows@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `253`
- prototype: `int(Windows::Security::Isolation::FileSaveDialogBroker *__hidden this, const struct _GUID *, void **)`
- caller_count: `8`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400086b4`
- `0x14000d750`
- `0x14000d760`
- `0x14000d770`
- `0x14000d780`
- `0x14000d790`
- `0x14000d7a0`
- `0x140010a28`

## callees

- `0x140007df4`
- `0x140009194`
- `0x14000a00c`
- `0x14000cbec`
- `0x14000d640`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000d695`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000d703`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000d65d`: `FileSaveDialogBroker::QueryInterface`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Security::Isolation::FileSaveDialogBroker::QueryInterface(
        Windows::Security::Isolation::FileSaveDialogBroker *this,
        const struct _GUID *a2,
        void **a3)
{
  __int64 v6; // rax
  int CanCastTo; // edi
  const char *v8; // r9
  __int64 result; // rax
  int v10[20]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v10, (__int64)"FileSaveDialogBroker::QueryInterface");
  v6 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IFileOpenDialog.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IFileOpenDialog.Data1 )
    v6 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IFileOpenDialog.Data4;
  try
  {
    if ( !v6 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD9,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)0x80004002LL,
        v10[0]);
    *a3 = 0;
    if ( (unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046) )
    {
      *a3 = this;
      (*(void (__fastcall **)(Windows::Security::Isolation::FileSaveDialogBroker *))(*(_QWORD *)this + 8LL))(this);
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
        (void *)0xDC,
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
                           (void *)0xE2,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000d640  mov     rax, rsp
0x14000d643  mov     [rax+8], rbx
0x14000d647  mov     [rax+10h], rsi
0x14000d64b  mov     [rax+18h], r8
0x14000d64f  push    rdi
0x14000d650  sub     rsp, 70h
0x14000d654  mov     rbx, r8
0x14000d657  mov     rdi, rdx
0x14000d65a  mov     rsi, rcx
0x14000d65d  lea     rdx, aFilesavedialog; "FileSaveDialogBroker::QueryInterface"
0x14000d664  lea     rcx, [rax-58h]
0x14000d668  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000d66d  nop
0x14000d66e  mov     rax, [rdi]
0x14000d671  sub     rax, qword ptr cs:IID_IFileOpenDialog.Data1
0x14000d678  jnz     short loc_14000D685
0x14000d67a  mov     rax, [rdi+8]
0x14000d67e  sub     rax, qword ptr cs:IID_IFileOpenDialog.Data4
0x14000d685  test    rax, rax
0x14000d688  jnz     short loc_14000D6A7
0x14000d68a  mov     rcx, [rsp+78h]; this
0x14000d68f  mov     r9d, 80004002h; char *
0x14000d695  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000d69c  mov     edx, 0D9h; void *
0x14000d6a1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000d6a7  mov     qword ptr [rbx], 0
0x14000d6ae  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x14000d6b5  mov     rcx, rdi; struct _GUID *
0x14000d6b8  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x14000d6bd  mov     rcx, rsi
0x14000d6c0  test    eax, eax
0x14000d6c2  jnz     short loc_14000D6E6
0x14000d6c4  mov     r8, rbx
0x14000d6c7  mov     rdx, rdi
0x14000d6ca  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$09@WRL@Microsoft@@$0A@U?$ImplementsMarker@U?$Implements@U?$RuntimeClassFlags@$09@WRL@Microsoft@@UIModalWindow@@UIFileDialog@@UIFileDialogInternal@@UIFileDialogPrivate@@UIFileOpenDialog@@UIFileSaveDialog@@UIFileDialogCustomize@@@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<10>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<10>,IModalWindow,IFileDialog,IFileDialogInternal,IFileDialogPrivate,IFileOpenDialog,IFileSaveDialog,IFileDialogCustomize>>>::CanCastTo(_GUID const &,void * *,bool *)
0x14000d6cf  mov     edi, eax
0x14000d6d1  test    eax, eax
0x14000d6d3  js      short loc_14000D6F7
0x14000d6d5  mov     rcx, [rbx]
0x14000d6d8  mov     rax, [rcx]
0x14000d6db  mov     rax, [rax+8]
0x14000d6df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d6e4  jmp     short loc_14000D6F7
0x14000d6e6  mov     [rbx], rsi
0x14000d6e9  mov     rax, [rsi]
0x14000d6ec  mov     rax, [rax+8]
0x14000d6f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d6f5  xor     edi, edi
0x14000d6f7  mov     rcx, [rsp+78h]; this
0x14000d6fc  test    edi, edi
0x14000d6fe  jns     short loc_14000D715
0x14000d700  mov     r9d, edi; char *
0x14000d703  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000d70a  mov     edx, 0DCh; void *
0x14000d70f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000d715  lea     rcx, [rsp+78h+var_58]; this
0x14000d71a  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000d71f  xor     eax, eax
0x14000d721  jmp     short loc_14000D72A
0x14000d723  mov     eax, [rsp+78h+arg_18]
0x14000d72a  lea     r11, [rsp+78h+var_8]
0x14000d72f  mov     rbx, [r11+10h]
0x14000d733  mov     rsi, [r11+18h]
0x14000d737  mov     rsp, r11
0x14000d73a  pop     rdi
0x14000d73b  retn
```
