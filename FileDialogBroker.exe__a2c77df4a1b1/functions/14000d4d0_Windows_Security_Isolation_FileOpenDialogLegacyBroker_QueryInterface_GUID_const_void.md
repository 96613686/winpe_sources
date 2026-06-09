# Windows::Security::Isolation::FileOpenDialogLegacyBroker::QueryInterface(_GUID const &,void * *)

- ea: `0x14000d4d0`
- end: `0x14000d5cd`
- name: `?QueryInterface@FileOpenDialogLegacyBroker@Isolation@Security@Windows@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `253`
- prototype: `int(Windows::Security::Isolation::FileOpenDialogLegacyBroker *__hidden this, const struct _GUID *, void **)`
- caller_count: `8`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400085fc`
- `0x14000d5e0`
- `0x14000d5f0`
- `0x14000d600`
- `0x14000d610`
- `0x14000d620`
- `0x14000d630`
- `0x140010964`

## callees

- `0x140007df4`
- `0x140009194`
- `0x14000a00c`
- `0x14000cbec`
- `0x14000d4d0`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000d525`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000d593`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000d4ed`: `FileOpenDialogLegacyBroker::QueryInterface`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Security::Isolation::FileOpenDialogLegacyBroker::QueryInterface(
        Windows::Security::Isolation::FileOpenDialogLegacyBroker *this,
        const struct _GUID *a2,
        void **a3)
{
  __int64 v6; // rax
  int CanCastTo; // edi
  const char *v8; // r9
  __int64 result; // rax
  int v10[20]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v10, (__int64)"FileOpenDialogLegacyBroker::QueryInterface");
  v6 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IFileSaveDialog.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IFileSaveDialog.Data1 )
    v6 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IFileSaveDialog.Data4;
  try
  {
    if ( !v6 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x169,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)0x80004002LL,
        v10[0]);
    *a3 = 0;
    if ( (unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046) )
    {
      *a3 = this;
      (*(void (__fastcall **)(Windows::Security::Isolation::FileOpenDialogLegacyBroker *))(*(_QWORD *)this + 8LL))(this);
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
        (void *)0x16C,
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
                           (void *)0x172,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000d4d0  mov     rax, rsp
0x14000d4d3  mov     [rax+8], rbx
0x14000d4d7  mov     [rax+10h], rsi
0x14000d4db  mov     [rax+18h], r8
0x14000d4df  push    rdi
0x14000d4e0  sub     rsp, 70h
0x14000d4e4  mov     rbx, r8
0x14000d4e7  mov     rdi, rdx
0x14000d4ea  mov     rsi, rcx
0x14000d4ed  lea     rdx, aFileopendialog_2; "FileOpenDialogLegacyBroker::QueryInterf"...
0x14000d4f4  lea     rcx, [rax-58h]
0x14000d4f8  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000d4fd  nop
0x14000d4fe  mov     rax, [rdi]
0x14000d501  sub     rax, qword ptr cs:IID_IFileSaveDialog.Data1
0x14000d508  jnz     short loc_14000D515
0x14000d50a  mov     rax, [rdi+8]
0x14000d50e  sub     rax, qword ptr cs:IID_IFileSaveDialog.Data4
0x14000d515  test    rax, rax
0x14000d518  jnz     short loc_14000D537
0x14000d51a  mov     rcx, [rsp+78h]; this
0x14000d51f  mov     r9d, 80004002h; char *
0x14000d525  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000d52c  mov     edx, 169h; void *
0x14000d531  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000d537  mov     qword ptr [rbx], 0
0x14000d53e  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x14000d545  mov     rcx, rdi; struct _GUID *
0x14000d548  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x14000d54d  mov     rcx, rsi
0x14000d550  test    eax, eax
0x14000d552  jnz     short loc_14000D576
0x14000d554  mov     r8, rbx
0x14000d557  mov     rdx, rdi
0x14000d55a  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$09@WRL@Microsoft@@$0A@U?$ImplementsMarker@U?$Implements@U?$RuntimeClassFlags@$09@WRL@Microsoft@@UIModalWindow@@UIFileDialog@@UIFileDialogInternal@@UIFileDialogPrivate@@UIFileOpenDialog@@UIFileSaveDialog@@UIFileDialogCustomize@@@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<10>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<10>,IModalWindow,IFileDialog,IFileDialogInternal,IFileDialogPrivate,IFileOpenDialog,IFileSaveDialog,IFileDialogCustomize>>>::CanCastTo(_GUID const &,void * *,bool *)
0x14000d55f  mov     edi, eax
0x14000d561  test    eax, eax
0x14000d563  js      short loc_14000D587
0x14000d565  mov     rcx, [rbx]
0x14000d568  mov     rax, [rcx]
0x14000d56b  mov     rax, [rax+8]
0x14000d56f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d574  jmp     short loc_14000D587
0x14000d576  mov     [rbx], rsi
0x14000d579  mov     rax, [rsi]
0x14000d57c  mov     rax, [rax+8]
0x14000d580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d585  xor     edi, edi
0x14000d587  mov     rcx, [rsp+78h]; this
0x14000d58c  test    edi, edi
0x14000d58e  jns     short loc_14000D5A5
0x14000d590  mov     r9d, edi; char *
0x14000d593  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000d59a  mov     edx, 16Ch; void *
0x14000d59f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000d5a5  lea     rcx, [rsp+78h+var_58]; this
0x14000d5aa  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000d5af  xor     eax, eax
0x14000d5b1  jmp     short loc_14000D5BA
0x14000d5b3  mov     eax, [rsp+78h+arg_18]
0x14000d5ba  lea     r11, [rsp+78h+var_8]
0x14000d5bf  mov     rbx, [r11+10h]
0x14000d5c3  mov     rsi, [r11+18h]
0x14000d5c7  mov     rsp, r11
0x14000d5ca  pop     rdi
0x14000d5cb  retn
```
