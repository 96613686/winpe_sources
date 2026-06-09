# WaasMedic::MiscUtil::ServiceHasHiddenUpdates(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,bool &)

- ea: `0x18002695c`
- end: `0x180026f85`
- name: `?ServiceHasHiddenUpdates@MiscUtil@WaasMedic@@SAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEA_N@Z`
- size: `1577`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180025f00`

## callees

- `0x180003bd4`
- `0x180009a54`
- `0x18000b308`
- `0x18002543c`
- `0x180025828`
- `0x18002695c`
- `0x1800271a8`
- `0x180036918`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800269b0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800269b0`
- `OLEAUT32!__imp_SysAllocString` at `0x180026c90`
- `OLEAUT32!__imp_SysAllocString` at `0x180026c90`

## string_xrefs

- `0x1800269e4`: `Failed to create UpdateSearcher`
- `0x180026dc2`: `Failed to get updates and store them in update collection`
- `0x180026d47`: `This is a new datastore and WU has not performed a scan. No hidden updates present`
- `0x180026eeb`: `Count of hidden updates %ld`
- `0x180026e69`: `Failed to get count of updates in collection`
- `0x180026f73`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall WaasMedic::MiscUtil::ServiceHasHiddenUpdates(_QWORD *a1, bool *a2)
{
  HRESULT v4; // eax
  int v5; // ebx
  int v7; // eax
  __int64 *v8; // rdi
  __int64 v9; // r14
  __int64 v10; // rcx
  BSTR *v11; // rbx
  BSTR v12; // rax
  int v13; // ecx
  int ppv; // [rsp+20h] [rbp-30h]
  char *v15; // [rsp+28h] [rbp-28h]
  LPVOID v16; // [rsp+30h] [rbp-20h] BYREF
  __int64 v17; // [rsp+38h] [rbp-18h] BYREF
  BSTR *v18; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  unsigned int v20; // [rsp+88h] [rbp+38h] BYREF
  __int64 *v21; // [rsp+90h] [rbp+40h] BYREF
  __int64 v22; // [rsp+98h] [rbp+48h] BYREF

  v21 = 0;
  v22 = 0;
  v17 = 0;
  *a2 = 0;
  v16 = 0;
  v4 = CoCreateInstance(
         &GUID_4cb43d7f_7eee_4906_8698_60da1c38f2fe,
         0,
         0x15u,
         &GUID_816858a4_260d_4260_933a_2585f1abc76b,
         &v16);
  if ( v4 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x1C9B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v4,
      ppv);
  v5 = (*(__int64 (__fastcall **)(LPVOID, __int64 **))(*(_QWORD *)v16 + 96LL))(v16, &v21);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x248,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\miscutil.cpp",
      (const char *)(unsigned int)v5,
      (int)"Failed to create UpdateSearcher",
      v15);
    if ( v16 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( v21 )
      (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
    return (unsigned int)v5;
  }
  v5 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v21 + 168))(v21, 0);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x24B,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\miscutil.cpp",
      (const char *)(unsigned int)v5,
      (int)"Failed to put set online search to %hs",
      "false");
    if ( v16 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( v21 )
      (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
    return (unsigned int)v5;
  }
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v21 + 112))(v21, 3);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x24C,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\miscutil.cpp",
      (const char *)(unsigned int)v5,
      (int)"Failed to set serverSelection to ssOthers",
      v15);
    if ( v16 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( v21 )
      (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
    return (unsigned int)v5;
  }
  v7 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v21 + 192))(v21, *a1);
  v5 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24D,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\miscutil.cpp",
      (const char *)(unsigned int)v7,
      ppv);
    if ( v16 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( v21 )
      (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
    return (unsigned int)v5;
  }
  v8 = v21;
  v9 = *v21;
  v10 = v22;
  v22 = 0;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  v11 = (BSTR *)operator new(0x18u);
  v18 = v11;
  v11[1] = 0;
  *((_DWORD *)v11 + 4) = 1;
  v12 = SysAllocString(L"IsHidden=1");
  *v11 = v12;
  if ( !v12 )
    _com_issue_error(v13);
  v18 = v11;
  v5 = (*(__int64 (__fastcall **)(__int64 *, BSTR, __int64 *))(v9 + 152))(v8, v12, &v22);
  _bstr_t::~_bstr_t((_bstr_t *)&v18);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 72LL))(v22, &v17);
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x261,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\miscutil.cpp",
        (const char *)(unsigned int)v5,
        (int)"Failed to get updates and store them in update collection",
        v15);
      if ( v16 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      if ( v22 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      if ( v21 )
        (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
      return (unsigned int)v5;
    }
    v20 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v17 + 80LL))(v17, &v20);
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x264,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\miscutil.cpp",
        (const char *)(unsigned int)v5,
        (int)"Failed to get count of updates in collection",
        v15);
      if ( v16 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      if ( v22 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      if ( v21 )
        (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
      return (unsigned int)v5;
    }
    LogLevelW(4u, L"Count of hidden updates %ld", v20);
    *a2 = (int)v20 > 0;
    if ( v16 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  else
  {
    if ( v5 != -2145091564 && (unsigned int)(v5 + 2145091542) > 2 )
    {
      if ( v16 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      if ( v22 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      if ( v21 )
        (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
      return (unsigned int)v5;
    }
    *a2 = 0;
    LogLevelW(4u, L"This is a new datastore and WU has not performed a scan. No hidden updates present");
    if ( v16 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  if ( v21 )
    (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
  return 0;
}

```

## disassembly

```asm
0x18002695c  push    rbp
0x18002695e  push    rbx
0x18002695f  push    rsi
0x180026960  push    rdi
0x180026961  push    r14
0x180026963  mov     rbp, rsp
0x180026966  sub     rsp, 50h
0x18002696a  mov     rsi, rdx
0x18002696d  mov     rdi, rcx
0x180026970  mov     [rbp+arg_10], 0
0x180026978  mov     [rbp+arg_18], 0
0x180026980  mov     [rbp+var_18], 0
0x180026988  mov     byte ptr [rdx], 0
0x18002698b  mov     [rbp+var_20], 0
0x180026993  lea     rax, [rbp+var_20]
0x180026997  mov     [rsp+50h+ppv], rax; int
0x18002699c  lea     r9, _GUID_816858a4_260d_4260_933a_2585f1abc76b; riid
0x1800269a3  xor     edx, edx; pUnkOuter
0x1800269a5  lea     r8d, [rdx+15h]; dwClsContext
0x1800269a9  lea     rcx, _GUID_4cb43d7f_7eee_4906_8698_60da1c38f2fe; rclsid
0x1800269b0  call    cs:__imp_CoCreateInstance
0x1800269b6  mov     rcx, [rbp+28h]; this
0x1800269ba  test    eax, eax
0x1800269bc  js      loc_180026F70
0x1800269c2  mov     rcx, [rbp+var_20]
0x1800269c6  mov     rax, [rcx]
0x1800269c9  lea     rdx, [rbp+arg_10]
0x1800269cd  mov     rax, [rax+60h]
0x1800269d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269d6  mov     ebx, eax
0x1800269d8  test    eax, eax
0x1800269da  jns     loc_180026A64
0x1800269e0  mov     rcx, [rbp+28h]; this
0x1800269e4  lea     rax, aFailedToCreate_1; "Failed to create UpdateSearcher"
0x1800269eb  mov     [rsp+50h+ppv], rax; int
0x1800269f0  mov     r9d, ebx; char *
0x1800269f3  lea     r8, aOnecoreEnduser_16; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800269fa  mov     edx, 248h; void *
0x1800269ff  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180026a04  nop
0x180026a05  mov     rcx, [rbp+var_20]
0x180026a09  test    rcx, rcx
0x180026a0c  jz      short loc_180026A1B
0x180026a0e  mov     rax, [rcx]
0x180026a11  mov     rax, [rax+10h]
0x180026a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a1a  nop
0x180026a1b  mov     rcx, [rbp+var_18]
0x180026a1f  test    rcx, rcx
0x180026a22  jz      short loc_180026A31
0x180026a24  mov     rax, [rcx]
0x180026a27  mov     rax, [rax+10h]
0x180026a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a30  nop
0x180026a31  mov     rcx, [rbp+arg_18]
0x180026a35  test    rcx, rcx
0x180026a38  jz      short loc_180026A47
0x180026a3a  mov     rax, [rcx]
0x180026a3d  mov     rax, [rax+10h]
0x180026a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a46  nop
0x180026a47  mov     rcx, [rbp+arg_10]
0x180026a4b  test    rcx, rcx
0x180026a4e  jz      short loc_180026A5D
0x180026a50  mov     rax, [rcx]
0x180026a53  mov     rax, [rax+10h]
0x180026a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a5c  nop
0x180026a5d  mov     eax, ebx
0x180026a5f  jmp     loc_180026F5F
0x180026a64  mov     rcx, [rbp+arg_10]
0x180026a68  mov     rax, [rcx]
0x180026a6b  xor     edx, edx
0x180026a6d  mov     rax, [rax+0A8h]
0x180026a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a79  mov     ebx, eax
0x180026a7b  test    eax, eax
0x180026a7d  jns     loc_180026B11
0x180026a83  mov     rcx, [rbp+28h]; this
0x180026a87  lea     rax, aFalse; "false"
0x180026a8e  mov     [rsp+50h+var_28], rax; char *
0x180026a93  lea     rax, aFailedToPutSet; "Failed to put set online search to %hs"
0x180026a9a  mov     [rsp+50h+ppv], rax; int
0x180026a9f  mov     r9d, ebx; char *
0x180026aa2  lea     r8, aOnecoreEnduser_16; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180026aa9  mov     edx, 24Bh; void *
0x180026aae  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180026ab3  nop
0x180026ab4  mov     rcx, [rbp+var_20]
0x180026ab8  test    rcx, rcx
0x180026abb  jz      short loc_180026ACA
0x180026abd  mov     rax, [rcx]
0x180026ac0  mov     rax, [rax+10h]
0x180026ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ac9  nop
0x180026aca  mov     rcx, [rbp+var_18]
0x180026ace  test    rcx, rcx
0x180026ad1  jz      short loc_180026AE0
0x180026ad3  mov     rax, [rcx]
0x180026ad6  mov     rax, [rax+10h]
0x180026ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026adf  nop
0x180026ae0  mov     rcx, [rbp+arg_18]
0x180026ae4  test    rcx, rcx
0x180026ae7  jz      short loc_180026AF6
0x180026ae9  mov     rax, [rcx]
0x180026aec  mov     rax, [rax+10h]
0x180026af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026af5  nop
0x180026af6  mov     rcx, [rbp+arg_10]
0x180026afa  test    rcx, rcx
0x180026afd  jz      short loc_180026B0C
0x180026aff  mov     rax, [rcx]
0x180026b02  mov     rax, [rax+10h]
0x180026b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b0b  nop
0x180026b0c  jmp     loc_180026A5D
0x180026b11  mov     rcx, [rbp+arg_10]
0x180026b15  mov     rax, [rcx]
0x180026b18  mov     edx, 3
0x180026b1d  mov     rax, [rax+70h]
0x180026b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b26  mov     ebx, eax
0x180026b28  test    eax, eax
0x180026b2a  jns     loc_180026BB2
0x180026b30  mov     rcx, [rbp+28h]; this
0x180026b34  lea     rax, aFailedToSetSer; "Failed to set serverSelection to ssOthe"...
0x180026b3b  mov     [rsp+50h+ppv], rax; int
0x180026b40  mov     r9d, ebx; char *
0x180026b43  lea     r8, aOnecoreEnduser_16; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180026b4a  mov     edx, 24Ch; void *
0x180026b4f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180026b54  nop
0x180026b55  mov     rcx, [rbp+var_20]
0x180026b59  test    rcx, rcx
0x180026b5c  jz      short loc_180026B6B
0x180026b5e  mov     rax, [rcx]
0x180026b61  mov     rax, [rax+10h]
0x180026b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b6a  nop
0x180026b6b  mov     rcx, [rbp+var_18]
0x180026b6f  test    rcx, rcx
0x180026b72  jz      short loc_180026B81
0x180026b74  mov     rax, [rcx]
0x180026b77  mov     rax, [rax+10h]
0x180026b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b80  nop
0x180026b81  mov     rcx, [rbp+arg_18]
0x180026b85  test    rcx, rcx
0x180026b88  jz      short loc_180026B97
0x180026b8a  mov     rax, [rcx]
0x180026b8d  mov     rax, [rax+10h]
0x180026b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b96  nop
0x180026b97  mov     rcx, [rbp+arg_10]
0x180026b9b  test    rcx, rcx
0x180026b9e  jz      short loc_180026BAD
0x180026ba0  mov     rax, [rcx]
0x180026ba3  mov     rax, [rax+10h]
0x180026ba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026bac  nop
0x180026bad  jmp     loc_180026A5D
0x180026bb2  mov     rcx, [rbp+arg_10]
0x180026bb6  mov     rax, [rcx]
0x180026bb9  mov     rdx, [rdi]
0x180026bbc  mov     rax, [rax+0C0h]
0x180026bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026bc8  mov     ebx, eax
0x180026bca  test    eax, eax
0x180026bcc  jns     short loc_180026C44
0x180026bce  mov     rcx, [rbp+28h]; this
0x180026bd2  mov     r9d, eax; char *
0x180026bd5  lea     r8, aOnecoreEnduser_16; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180026bdc  mov     edx, 24Dh; void *
0x180026be1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026be6  nop
0x180026be7  mov     rcx, [rbp+var_20]
0x180026beb  test    rcx, rcx
0x180026bee  jz      short loc_180026BFD
0x180026bf0  mov     rax, [rcx]
0x180026bf3  mov     rax, [rax+10h]
0x180026bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026bfc  nop
0x180026bfd  mov     rcx, [rbp+var_18]
0x180026c01  test    rcx, rcx
0x180026c04  jz      short loc_180026C13
0x180026c06  mov     rax, [rcx]
0x180026c09  mov     rax, [rax+10h]
0x180026c0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c12  nop
0x180026c13  mov     rcx, [rbp+arg_18]
0x180026c17  test    rcx, rcx
0x180026c1a  jz      short loc_180026C29
0x180026c1c  mov     rax, [rcx]
0x180026c1f  mov     rax, [rax+10h]
0x180026c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c28  nop
0x180026c29  mov     rcx, [rbp+arg_10]
0x180026c2d  test    rcx, rcx
0x180026c30  jz      short loc_180026C3F
0x180026c32  mov     rax, [rcx]
0x180026c35  mov     rax, [rax+10h]
0x180026c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c3e  nop
0x180026c3f  jmp     loc_180026A5D
0x180026c44  mov     rdi, [rbp+arg_10]
0x180026c48  mov     r14, [rdi]
0x180026c4b  mov     rcx, [rbp+arg_18]
0x180026c4f  mov     [rbp+arg_18], 0
0x180026c57  test    rcx, rcx
0x180026c5a  jz      short loc_180026C69
0x180026c5c  mov     rax, [rcx]
0x180026c5f  mov     rax, [rax+10h]
0x180026c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c68  nop
0x180026c69  mov     ecx, 18h; Size
0x180026c6e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026c73  mov     rbx, rax
0x180026c76  mov     [rbp+var_10], rax
0x180026c7a  mov     qword ptr [rax+8], 0
0x180026c82  mov     dword ptr [rax+10h], 1
0x180026c89  lea     rcx, psz; "IsHidden=1"
0x180026c90  call    cs:__imp_SysAllocString
0x180026c96  mov     [rbx], rax
0x180026c99  test    rax, rax
0x180026c9c  jz      loc_180026F6A
0x180026ca2  mov     [rbp+var_10], rbx
0x180026ca6  lea     r8, [rbp+arg_18]
0x180026caa  mov     rdx, rax
0x180026cad  mov     rcx, rdi
0x180026cb0  mov     rax, [r14+98h]
0x180026cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026cbc  mov     ebx, eax
0x180026cbe  lea     rcx, [rbp+var_10]; this
0x180026cc2  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180026cc7  mov     ecx, ebx
0x180026cc9  shr     ecx, 1Fh
0x180026ccc  test    cl, cl
0x180026cce  jz      loc_180026DA0
0x180026cd4  cmp     ebx, 80248014h
0x180026cda  jz      short loc_180026D44
0x180026cdc  lea     ecx, [rbx+7FDB7FD6h]
0x180026ce2  cmp     ecx, 2
0x180026ce5  jbe     short loc_180026D44
0x180026ce7  mov     rcx, [rbp+var_20]
0x180026ceb  test    rcx, rcx
0x180026cee  jz      short loc_180026CFD
0x180026cf0  mov     rax, [rcx]
0x180026cf3  mov     rax, [rax+10h]
0x180026cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026cfc  nop
0x180026cfd  mov     rcx, [rbp+var_18]
0x180026d01  test    rcx, rcx
0x180026d04  jz      short loc_180026D13
0x180026d06  mov     rax, [rcx]
0x180026d09  mov     rax, [rax+10h]
0x180026d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d12  nop
0x180026d13  mov     rcx, [rbp+arg_18]
0x180026d17  test    rcx, rcx
0x180026d1a  jz      short loc_180026D29
0x180026d1c  mov     rax, [rcx]
0x180026d1f  mov     rax, [rax+10h]
0x180026d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d28  nop
0x180026d29  mov     rcx, [rbp+arg_10]
0x180026d2d  test    rcx, rcx
0x180026d30  jz      short loc_180026D3F
0x180026d32  mov     rax, [rcx]
0x180026d35  mov     rax, [rax+10h]
0x180026d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d3e  nop
0x180026d3f  jmp     loc_180026A5D
0x180026d44  mov     byte ptr [rsi], 0
0x180026d47  lea     rdx, aThisIsANewData; "This is a new datastore and WU has not "...
0x180026d4e  mov     ecx, 4; unsigned __int8
0x180026d53  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180026d58  nop
0x180026d59  mov     rcx, [rbp+var_20]
0x180026d5d  test    rcx, rcx
0x180026d60  jz      short loc_180026D6F
0x180026d62  mov     rax, [rcx]
0x180026d65  mov     rax, [rax+10h]
0x180026d69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d6e  nop
0x180026d6f  mov     rcx, [rbp+var_18]
0x180026d73  test    rcx, rcx
0x180026d76  jz      short loc_180026D85
0x180026d78  mov     rax, [rcx]
0x180026d7b  mov     rax, [rax+10h]
0x180026d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d84  nop
0x180026d85  mov     rcx, [rbp+arg_18]
0x180026d89  test    rcx, rcx
0x180026d8c  jz      short loc_180026D9B
0x180026d8e  mov     rax, [rcx]
0x180026d91  mov     rax, [rax+10h]
0x180026d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d9a  nop
0x180026d9b  jmp     loc_180026F47
  ... truncated ...
```
