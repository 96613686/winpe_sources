# OOBETaskSchedulerHelper::GetOrCreateTaskRootFolder(ushort const *,ushort const *,ushort const *,ITaskService *,ITaskFolder * *)

- ea: `0x180025920`
- end: `0x180025b86`
- name: `?GetOrCreateTaskRootFolder@OOBETaskSchedulerHelper@@YAJPEBG00PEAUITaskService@@PEAPEAUITaskFolder@@@Z`
- size: `614`
- prototype: `__int64 __fastcall(OOBETaskSchedulerHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct ITaskService *, struct ITaskFolder **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180029b68`

## callees

- `0x1800067b0`
- `0x18000e2bc`
- `0x180018c78`
- `0x18001cb3c`
- `0x18001cf50`
- `0x180025920`
- `0x18004e010`

## string_xrefs

- `0x180025962`: `shell\OOBE\User\inc\OOBETaskSchedulerHelper.h`
- `0x1800259d0`: `shell\OOBE\User\inc\OOBETaskSchedulerHelper.h`
- `0x180025a0e`: `shell\OOBE\User\inc\OOBETaskSchedulerHelper.h`
- `0x180025a5a`: `shell\OOBE\User\inc\OOBETaskSchedulerHelper.h`
- `0x180025a90`: `shell\OOBE\User\inc\OOBETaskSchedulerHelper.h`
- `0x180025b03`: `shell\OOBE\User\inc\OOBETaskSchedulerHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall OOBETaskSchedulerHelper::GetOrCreateTaskRootFolder(
        OOBETaskSchedulerHelper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct ITaskService *a5)
{
  struct ITaskService *v6; // r14
  const char *v7; // r9
  __int64 (__fastcall *v8)(const unsigned __int16 *, __int64, const unsigned __int16 **); // rdi
  unsigned int v9; // eax
  const char *v11; // r9
  __int64 (__fastcall *v12)(const unsigned __int16 *, __int64, OOBETaskSchedulerHelper **); // rdi
  int v13; // eax
  const char *v14; // r9
  OOBETaskSchedulerHelper *v15; // rsi
  __int64 (__fastcall *v16)(OOBETaskSchedulerHelper *, struct ITaskService *, __int16 *, const unsigned __int16 **); // rdi
  int v17; // eax
  struct ITaskServiceVtbl *v18; // rax
  const char *v19; // r9
  __int64 result; // rax
  int v21; // [rsp+20h] [rbp-48h]
  __int64 v22; // [rsp+30h] [rbp-38h] BYREF
  __int64 v23; // [rsp+38h] [rbp-30h] BYREF
  __int16 v24; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  OOBETaskSchedulerHelper *v26; // [rsp+70h] [rbp+8h] BYREF
  const unsigned __int16 *v27; // [rsp+80h] [rbp+18h] BYREF

  v27 = a3;
  v26 = this;
  v6 = a5;
  a5->lpVtbl = 0;
  wil::make_bstr_nothrow(&v23, a2);
  try
  {
    if ( !v23 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xE,
        (unsigned int)"shell\\OOBE\\User\\inc\\OOBETaskSchedulerHelper.h",
        v7);
    v27 = 0;
    v8 = *(__int64 (__fastcall **)(const unsigned __int16 *, __int64, const unsigned __int16 **))(*(_QWORD *)a4 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    v9 = v8(a4, v23, &v27);
    if ( (int)(v9 + 0x80000000) >= 0 && v9 != -2147024894 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x17,
        (unsigned int)"shell\\OOBE\\User\\inc\\OOBETaskSchedulerHelper.h",
        (const char *)v9,
        v21);
    if ( v9 == -2147024894 )
    {
      wil::make_bstr_nothrow(&v22, L"Microsoft\\Windows");
      if ( !v22 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x1C,
          (unsigned int)"shell\\OOBE\\User\\inc\\OOBETaskSchedulerHelper.h",
          v11);
      v26 = 0;
      v12 = *(__int64 (__fastcall **)(const unsigned __int16 *, __int64, OOBETaskSchedulerHelper **))(*(_QWORD *)a4 + 56LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
      v13 = v12(a4, v22, &v26);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1E,
          (unsigned int)"shell\\OOBE\\User\\inc\\OOBETaskSchedulerHelper.h",
          (const char *)(unsigned int)v13,
          v21);
      wil::make_bstr_nothrow(&a5, L"RetailDemo");
      if ( !a5 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x21,
          (unsigned int)"shell\\OOBE\\User\\inc\\OOBETaskSchedulerHelper.h",
          v14);
      v15 = v26;
      v16 = *(__int64 (__fastcall **)(OOBETaskSchedulerHelper *, struct ITaskService *, __int16 *, const unsigned __int16 **))(*(_QWORD *)v26 + 88LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
      v24 = 0;
      v17 = v16(v15, a5, &v24, &v27);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x23,
          (unsigned int)"shell\\OOBE\\User\\inc\\OOBETaskSchedulerHelper.h",
          (const char *)(unsigned int)v17,
          v21);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&a5);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
    }
    v18 = (struct ITaskServiceVtbl *)v27;
    v27 = 0;
    v6->lpVtbl = v18;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v27) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x29,
                     (unsigned int)"shell\\OOBE\\User\\inc\\OOBETaskSchedulerHelper.h",
                     v19);
    return (unsigned int)v27;
  }
  return result;
}

```

## disassembly

```asm
0x180025920  mov     rax, rsp
0x180025923  mov     [rax+10h], rsi
0x180025927  mov     [rax+20h], rdi
0x18002592b  mov     [rax+18h], r8
0x18002592f  mov     [rax+8], rcx
0x180025933  push    r14
0x180025935  sub     rsp, 60h
0x180025939  mov     rsi, r9
0x18002593c  mov     r14, [rsp+68h+arg_20]
0x180025944  mov     qword ptr [r14], 0
0x18002594b  lea     rcx, [rax-30h]
0x18002594f  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x180025954  nop
0x180025955  mov     rcx, [rsp+68h]; this
0x18002595a  cmp     [rsp+68h+var_30], 0
0x180025960  jnz     short loc_180025973
0x180025962  lea     r8, aShellOobeUserI; "shell\\OOBE\\User\\inc\\OOBETaskSchedul"...
0x180025969  mov     edx, 0Eh; void *
0x18002596e  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180025973  mov     [rsp+68h+arg_10], 0
0x18002597f  mov     rax, [rsi]
0x180025982  mov     rdi, [rax+38h]
0x180025986  lea     rcx, [rsp+68h+arg_10]
0x18002598e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180025993  lea     r8, [rsp+68h+arg_10]
0x18002599b  mov     rdx, [rsp+68h+var_30]
0x1800259a0  mov     rcx, rsi
0x1800259a3  mov     rax, rdi
0x1800259a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259ab  mov     edx, 80000000h
0x1800259b0  lea     ecx, [rax+rdx]
0x1800259b3  test    edx, ecx
0x1800259b5  jnz     short loc_1800259C2
0x1800259b7  cmp     eax, 80070002h
0x1800259bc  jz      short loc_1800259C2
0x1800259be  mov     cl, 1
0x1800259c0  jmp     short loc_1800259C4
0x1800259c2  xor     cl, cl
0x1800259c4  mov     r10, [rsp+68h]
0x1800259c9  test    cl, cl
0x1800259cb  jz      short loc_1800259E4
0x1800259cd  mov     r9d, eax; char *
0x1800259d0  lea     r8, aShellOobeUserI; "shell\\OOBE\\User\\inc\\OOBETaskSchedul"...
0x1800259d7  mov     edx, 17h; void *
0x1800259dc  mov     rcx, r10; this
0x1800259df  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800259e4  cmp     eax, 80070002h
0x1800259e9  jnz     loc_180025B38
0x1800259ef  lea     rdx, pszPathIn; "Microsoft\\Windows"
0x1800259f6  lea     rcx, [rsp+68h+var_38]
0x1800259fb  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x180025a00  nop
0x180025a01  mov     rcx, [rsp+68h]; this
0x180025a06  cmp     [rsp+68h+var_38], 0
0x180025a0c  jnz     short loc_180025A1F
0x180025a0e  lea     r8, aShellOobeUserI; "shell\\OOBE\\User\\inc\\OOBETaskSchedul"...
0x180025a15  mov     edx, 1Ch; void *
0x180025a1a  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180025a1f  mov     [rsp+68h+arg_0], 0
0x180025a28  mov     rax, [rsi]
0x180025a2b  mov     rdi, [rax+38h]
0x180025a2f  lea     rcx, [rsp+68h+arg_0]
0x180025a34  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180025a39  lea     r8, [rsp+68h+arg_0]
0x180025a3e  mov     rdx, [rsp+68h+var_38]
0x180025a43  mov     rcx, rsi
0x180025a46  mov     rax, rdi
0x180025a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a4e  mov     rcx, [rsp+68h]; this
0x180025a53  test    eax, eax
0x180025a55  jns     short loc_180025A6B
0x180025a57  mov     r9d, eax; char *
0x180025a5a  lea     r8, aShellOobeUserI; "shell\\OOBE\\User\\inc\\OOBETaskSchedul"...
0x180025a61  mov     edx, 1Eh; void *
0x180025a66  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025a6b  lea     rdx, aRetaildemo; "RetailDemo"
0x180025a72  lea     rcx, [rsp+68h+arg_20]
0x180025a7a  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x180025a7f  nop
0x180025a80  mov     rcx, [rsp+68h]; this
0x180025a85  cmp     [rsp+68h+arg_20], 0
0x180025a8e  jnz     short loc_180025AA1
0x180025a90  lea     r8, aShellOobeUserI; "shell\\OOBE\\User\\inc\\OOBETaskSchedul"...
0x180025a97  mov     edx, 21h ; '!'; void *
0x180025a9c  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180025aa1  mov     rsi, [rsp+68h+arg_0]
0x180025aa6  mov     rax, [rsi]
0x180025aa9  mov     rdi, [rax+58h]
0x180025aad  lea     rcx, [rsp+68h+arg_10]
0x180025ab5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180025aba  xor     edx, edx
0x180025abc  mov     [rsp+68h+var_28], dx
0x180025ac1  movups  xmm0, [rsp+68h+var_26]
0x180025ac6  movups  [rsp+68h+var_26], xmm0
0x180025acb  movsd   xmm1, qword ptr [rsp+68h+var_26+0Eh]
0x180025ad1  movsd   qword ptr [rsp+68h+var_26+0Eh], xmm1
0x180025ad7  lea     r9, [rsp+68h+arg_10]
0x180025adf  lea     r8, [rsp+68h+var_28]
0x180025ae4  mov     rdx, [rsp+68h+arg_20]
0x180025aec  mov     rcx, rsi
0x180025aef  mov     rax, rdi
0x180025af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025af7  mov     rcx, [rsp+68h]; this
0x180025afc  test    eax, eax
0x180025afe  jns     short loc_180025B15
0x180025b00  mov     r9d, eax; char *
0x180025b03  lea     r8, aShellOobeUserI; "shell\\OOBE\\User\\inc\\OOBETaskSchedul"...
0x180025b0a  mov     edx, 23h ; '#'; void *
0x180025b0f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025b15  lea     rcx, [rsp+68h+arg_20]
0x180025b1d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180025b22  nop
0x180025b23  lea     rcx, [rsp+68h+arg_0]
0x180025b28  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180025b2d  nop
0x180025b2e  lea     rcx, [rsp+68h+var_38]
0x180025b33  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180025b38  mov     rax, [rsp+68h+arg_10]
0x180025b40  mov     [rsp+68h+arg_10], 0
0x180025b4c  mov     [r14], rax
0x180025b4f  lea     rcx, [rsp+68h+arg_10]
0x180025b57  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180025b5c  nop
0x180025b5d  lea     rcx, [rsp+68h+var_30]
0x180025b62  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180025b67  xor     eax, eax
0x180025b69  jmp     short loc_180025B72
0x180025b6b  mov     eax, dword ptr [rsp+68h+arg_10]
0x180025b72  lea     r11, [rsp+68h+var_8]
0x180025b77  mov     rsi, [r11+18h]
0x180025b7b  mov     rdi, [r11+28h]
0x180025b7f  mov     rsp, r11
0x180025b82  pop     r14
0x180025b84  retn
```
