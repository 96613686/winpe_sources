# Windows::Security::Isolation::FileOpenDialogBroker::QueryInterface(_GUID const &,void * *)

- ea: `0x14000d360`
- end: `0x14000d45b`
- name: `?QueryInterface@FileOpenDialogBroker@Isolation@Security@Windows@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `251`
- prototype: `int(Windows::Security::Isolation::FileOpenDialogBroker *__hidden this, const struct _GUID *, void **)`
- caller_count: `8`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140008544`
- `0x14000d470`
- `0x14000d480`
- `0x14000d490`
- `0x14000d4a0`
- `0x14000d4b0`
- `0x14000d4c0`
- `0x1400108a0`

## callees

- `0x140007df4`
- `0x140009194`
- `0x14000a00c`
- `0x14000cbec`
- `0x14000d360`
- `0x14000f8d0`
- `0x140014010`

## string_xrefs

- `0x14000d3b5`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000d421`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x14000d37d`: `FileOpenDialogBroker::QueryInterface`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Security::Isolation::FileOpenDialogBroker::QueryInterface(
        Windows::Security::Isolation::FileOpenDialogBroker *this,
        const struct _GUID *a2,
        void **a3)
{
  __int64 v6; // rax
  int CanCastTo; // edi
  const char *v8; // r9
  __int64 result; // rax
  int v10[20]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  FileDialogBrokerTraceLogging::WatchCurrentThread((__int64)v10, (__int64)"FileOpenDialogBroker::QueryInterface");
  v6 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IFileSaveDialog.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IFileSaveDialog.Data1 )
    v6 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IFileSaveDialog.Data4;
  try
  {
    if ( !v6 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x47,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)0x80004002LL,
        v10[0]);
    *a3 = 0;
    if ( (unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046) )
    {
      *a3 = this;
      (*(void (__fastcall **)(Windows::Security::Isolation::FileOpenDialogBroker *))(*(_QWORD *)this + 8LL))(this);
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
        (void *)0x4A,
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
                           (void *)0x50,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000d360  mov     rax, rsp
0x14000d363  mov     [rax+8], rbx
0x14000d367  mov     [rax+10h], rsi
0x14000d36b  mov     [rax+18h], r8
0x14000d36f  push    rdi
0x14000d370  sub     rsp, 70h
0x14000d374  mov     rbx, r8
0x14000d377  mov     rdi, rdx
0x14000d37a  mov     rsi, rcx
0x14000d37d  lea     rdx, aFileopendialog_0; "FileOpenDialogBroker::QueryInterface"
0x14000d384  lea     rcx, [rax-58h]
0x14000d388  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x14000d38d  nop
0x14000d38e  mov     rax, [rdi]
0x14000d391  sub     rax, qword ptr cs:IID_IFileSaveDialog.Data1
0x14000d398  jnz     short loc_14000D3A5
0x14000d39a  mov     rax, [rdi+8]
0x14000d39e  sub     rax, qword ptr cs:IID_IFileSaveDialog.Data4
0x14000d3a5  test    rax, rax
0x14000d3a8  jnz     short loc_14000D3C5
0x14000d3aa  mov     rcx, [rsp+78h]; this
0x14000d3af  mov     r9d, 80004002h; char *
0x14000d3b5  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000d3bc  lea     edx, [rax+47h]; void *
0x14000d3bf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000d3c5  mov     qword ptr [rbx], 0
0x14000d3cc  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x14000d3d3  mov     rcx, rdi; struct _GUID *
0x14000d3d6  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x14000d3db  mov     rcx, rsi
0x14000d3de  test    eax, eax
0x14000d3e0  jnz     short loc_14000D404
0x14000d3e2  mov     r8, rbx
0x14000d3e5  mov     rdx, rdi
0x14000d3e8  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$09@WRL@Microsoft@@$0A@U?$ImplementsMarker@U?$Implements@U?$RuntimeClassFlags@$09@WRL@Microsoft@@UIModalWindow@@UIFileDialog@@UIFileDialogInternal@@UIFileDialogPrivate@@UIFileOpenDialog@@UIFileSaveDialog@@UIFileDialogCustomize@@@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<10>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<10>,IModalWindow,IFileDialog,IFileDialogInternal,IFileDialogPrivate,IFileOpenDialog,IFileSaveDialog,IFileDialogCustomize>>>::CanCastTo(_GUID const &,void * *,bool *)
0x14000d3ed  mov     edi, eax
0x14000d3ef  test    eax, eax
0x14000d3f1  js      short loc_14000D415
0x14000d3f3  mov     rcx, [rbx]
0x14000d3f6  mov     rax, [rcx]
0x14000d3f9  mov     rax, [rax+8]
0x14000d3fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d402  jmp     short loc_14000D415
0x14000d404  mov     [rbx], rsi
0x14000d407  mov     rax, [rsi]
0x14000d40a  mov     rax, [rax+8]
0x14000d40e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d413  xor     edi, edi
0x14000d415  mov     rcx, [rsp+78h]; this
0x14000d41a  test    edi, edi
0x14000d41c  jns     short loc_14000D433
0x14000d41e  mov     r9d, edi; char *
0x14000d421  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x14000d428  mov     edx, 4Ah ; 'J'; void *
0x14000d42d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000d433  lea     rcx, [rsp+78h+var_58]; this
0x14000d438  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x14000d43d  xor     eax, eax
0x14000d43f  jmp     short loc_14000D448
0x14000d441  mov     eax, [rsp+78h+arg_18]
0x14000d448  lea     r11, [rsp+78h+var_8]
0x14000d44d  mov     rbx, [r11+10h]
0x14000d451  mov     rsi, [r11+18h]
0x14000d455  mov     rsp, r11
0x14000d458  pop     rdi
0x14000d459  retn
```
