# GetDeviceInstanceId(ushort const *,ushort * *)

- ea: `0x140045b80`
- end: `0x140045f01`
- name: `?GetDeviceInstanceId@@YAJPEBGPEAPEAG@Z`
- size: `897`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140045788`
- `0x140045ac8`

## callees

- `0x140008124`
- `0x14000c33c`
- `0x140016f68`
- `0x14001d790`
- `0x140045b80`
- `0x1400516e8`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140045bc1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140045bc1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140045cc8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140045e3c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140045ea6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140045cc8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140045e3c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140045ea6`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall GetDeviceInstanceId(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rax
  int v7; // eax
  __int64 v8; // rax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, unsigned __int16 **); // rbx
  int v16; // eax
  unsigned __int16 *v18; // rax
  int ppv; // [rsp+20h] [rbp-40h]
  LPVOID v20; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int16 *v21; // [rsp+38h] [rbp-28h] BYREF
  __int64 v22; // [rsp+40h] [rbp-20h] BYREF
  PROPVARIANT pvar[2]; // [rsp+48h] [rbp-18h] BYREF
  __int64 v24; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  __int64 *v26; // [rsp+88h] [rbp+28h] BYREF
  __int64 v27; // [rsp+90h] [rbp+30h] BYREF
  __int64 v28; // [rsp+98h] [rbp+38h] BYREF

  *a2 = 0;
  v20 = 0;
  v4 = CoCreateInstance(&CLSID_MMDeviceEnumerator, 0, 0x17u, &GUID_a95664d2_9614_4f35_a746_de8db63617e6, &v20);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiodgtelemetry.cpp",
      (const char *)(unsigned int)v4,
      ppv);
LABEL_28:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
    return v5;
  }
  v26 = 0;
  v6 = *(_QWORD *)v20;
  v26 = 0;
  v7 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, __int64 **))(v6 + 40))(v20, a1, &v26);
  v5 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiodgtelemetry.cpp",
      (const char *)(unsigned int)v7,
      ppv);
LABEL_27:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
    goto LABEL_28;
  }
  v27 = 0;
  v8 = *v26;
  v27 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v8 + 32))(v26, 0, &v27);
  v5 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiodgtelemetry.cpp",
      (const char *)(unsigned int)v9,
      ppv);
LABEL_26:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
    goto LABEL_27;
  }
  *(_OWORD *)pvar = 0;
  v24 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v27 + 40LL))(
          v27,
          PKEY_Endpoint_Devnode,
          pvar);
  v5 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiodgtelemetry.cpp",
      (const char *)(unsigned int)v10,
      ppv);
    PropVariantClear(pvar);
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    if ( v26 )
      (*(void (__fastcall **)(__int64 *))(*v26 + 16))(v26);
    if ( v20 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
    return v5;
  }
  if ( LOWORD(pvar[0]) != 31 )
  {
    v5 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiodgtelemetry.cpp",
      (const char *)0x8000FFFFLL,
      ppv);
LABEL_25:
    PropVariantClear(pvar);
    goto LABEL_26;
  }
  v28 = 0;
  v11 = *(_QWORD *)v20;
  v28 = 0;
  v12 = (*(__int64 (__fastcall **)(LPVOID, PROPVARIANT, __int64 *))(v11 + 40))(v20, pvar[1], &v28);
  v5 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiodgtelemetry.cpp",
      (const char *)(unsigned int)v12,
      ppv);
LABEL_24:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
    goto LABEL_25;
  }
  v22 = 0;
  v13 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v28)(
          v28,
          &GUID_2efad216_2482_42af_98f5_35d70f3f5e14,
          &v22);
  v5 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiodgtelemetry.cpp",
      (const char *)(unsigned int)v13,
      ppv);
LABEL_23:
    wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v22);
    goto LABEL_24;
  }
  v21 = 0;
  v14 = v22;
  v15 = *(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v22 + 32LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v21,
    0);
  v16 = v15(v14, &v21);
  v5 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiodgtelemetry.cpp",
      (const char *)(unsigned int)v16,
      ppv);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
    goto LABEL_23;
  }
  v18 = v21;
  v21 = 0;
  *a2 = v18;
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  PropVariantClear(pvar);
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v26 )
    (*(void (__fastcall **)(__int64 *))(*v26 + 16))(v26);
  if ( v20 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
  return 0;
}

```

## disassembly

```asm
0x140045b80  mov     [rsp-18h+arg_0], rbx
0x140045b85  push    rbp
0x140045b86  push    rsi
0x140045b87  push    rdi
0x140045b88  mov     rbp, rsp
0x140045b8b  sub     rsp, 60h
0x140045b8f  mov     rsi, rdx
0x140045b92  mov     rdi, rcx
0x140045b95  mov     qword ptr [rdx], 0
0x140045b9c  mov     [rbp+var_30], 0
0x140045ba4  lea     rax, [rbp+var_30]
0x140045ba8  mov     qword ptr [rsp+60h+ppv], rax; int
0x140045bad  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x140045bb4  xor     edx, edx; pUnkOuter
0x140045bb6  lea     r8d, [rdx+17h]; dwClsContext
0x140045bba  lea     rcx, CLSID_MMDeviceEnumerator; rclsid
0x140045bc1  call    cs:__imp_CoCreateInstance
0x140045bc7  mov     ebx, eax
0x140045bc9  test    eax, eax
0x140045bcb  jns     short loc_140045BEA
0x140045bcd  mov     rcx, [rbp+18h]; this
0x140045bd1  mov     r9d, eax; char *
0x140045bd4  lea     r8, aAvcoreAudiocor_41; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140045bdb  mov     edx, 21h ; '!'; void *
0x140045be0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140045be5  jmp     loc_140045E57
0x140045bea  mov     [rbp+arg_8], 0
0x140045bf2  mov     rcx, [rbp+var_30]
0x140045bf6  mov     rax, [rcx]
0x140045bf9  mov     [rbp+arg_8], 0
0x140045c01  lea     r8, [rbp+arg_8]
0x140045c05  mov     rdx, rdi
0x140045c08  mov     rax, [rax+28h]
0x140045c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045c11  mov     ebx, eax
0x140045c13  test    eax, eax
0x140045c15  jns     short loc_140045C34
0x140045c17  mov     rcx, [rbp+18h]; this
0x140045c1b  mov     r9d, eax; char *
0x140045c1e  lea     r8, aAvcoreAudiocor_41; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140045c25  mov     edx, 24h ; '$'; void *
0x140045c2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140045c2f  jmp     loc_140045E4D
0x140045c34  mov     [rbp+arg_10], 0
0x140045c3c  mov     rcx, [rbp+arg_8]
0x140045c40  mov     rax, [rcx]
0x140045c43  mov     [rbp+arg_10], 0
0x140045c4b  lea     r8, [rbp+arg_10]
0x140045c4f  xor     edx, edx
0x140045c51  mov     rax, [rax+20h]
0x140045c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045c5a  mov     ebx, eax
0x140045c5c  test    eax, eax
0x140045c5e  jns     short loc_140045C7D
0x140045c60  mov     rcx, [rbp+18h]; this
0x140045c64  mov     r9d, eax; char *
0x140045c67  lea     r8, aAvcoreAudiocor_41; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140045c6e  mov     edx, 27h ; '''; void *
0x140045c73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140045c78  jmp     loc_140045E43
0x140045c7d  xorps   xmm0, xmm0
0x140045c80  xor     eax, eax
0x140045c82  movups  xmmword ptr [rbp+pvar], xmm0
0x140045c86  mov     [rbp+var_8], rax
0x140045c8a  mov     rcx, [rbp+arg_10]
0x140045c8e  mov     rax, [rcx]
0x140045c91  lea     r8, [rbp+pvar]
0x140045c95  lea     rdx, PKEY_Endpoint_Devnode
0x140045c9c  mov     rax, [rax+28h]
0x140045ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045ca5  mov     ebx, eax
0x140045ca7  test    eax, eax
0x140045ca9  jns     short loc_140045D16
0x140045cab  mov     rcx, [rbp+18h]; this
0x140045caf  mov     r9d, eax; char *
0x140045cb2  lea     r8, aAvcoreAudiocor_41; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140045cb9  mov     edx, 2Ah ; '*'; void *
0x140045cbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140045cc3  nop
0x140045cc4  lea     rcx, [rbp+pvar]; pvar
0x140045cc8  call    cs:__imp_PropVariantClear
0x140045cce  nop
0x140045ccf  mov     rcx, [rbp+arg_10]
0x140045cd3  test    rcx, rcx
0x140045cd6  jz      short loc_140045CE5
0x140045cd8  mov     rax, [rcx]
0x140045cdb  mov     rax, [rax+10h]
0x140045cdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045ce4  nop
0x140045ce5  mov     rcx, [rbp+arg_8]
0x140045ce9  test    rcx, rcx
0x140045cec  jz      short loc_140045CFB
0x140045cee  mov     rax, [rcx]
0x140045cf1  mov     rax, [rax+10h]
0x140045cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045cfa  nop
0x140045cfb  mov     rcx, [rbp+var_30]
0x140045cff  test    rcx, rcx
0x140045d02  jz      short loc_140045D11
0x140045d04  mov     rax, [rcx]
0x140045d07  mov     rax, [rax+10h]
0x140045d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045d10  nop
0x140045d11  jmp     loc_140045E60
0x140045d16  mov     eax, 1Fh
0x140045d1b  cmp     ax, word ptr [rbp+pvar]
0x140045d1f  jz      short loc_140045D41
0x140045d21  mov     rcx, [rbp+18h]; this
0x140045d25  mov     ebx, 8000FFFFh
0x140045d2a  mov     r9d, ebx; char *
0x140045d2d  lea     r8, aAvcoreAudiocor_41; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140045d34  lea     edx, [rax+0Ch]; void *
0x140045d37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140045d3c  jmp     loc_140045E38
0x140045d41  mov     [rbp+arg_18], 0
0x140045d49  mov     rcx, [rbp+var_30]
0x140045d4d  mov     rax, [rcx]
0x140045d50  mov     [rbp+arg_18], 0
0x140045d58  lea     r8, [rbp+arg_18]
0x140045d5c  mov     rdx, [rbp+pvar+8]
0x140045d60  mov     rax, [rax+28h]
0x140045d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045d69  mov     ebx, eax
0x140045d6b  test    eax, eax
0x140045d6d  jns     short loc_140045D8C
0x140045d6f  mov     rcx, [rbp+18h]; this
0x140045d73  mov     r9d, eax; char *
0x140045d76  lea     r8, aAvcoreAudiocor_41; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140045d7d  mov     edx, 2Eh ; '.'; void *
0x140045d82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140045d87  jmp     loc_140045E2E
0x140045d8c  mov     [rbp+var_20], 0
0x140045d94  mov     rcx, [rbp+arg_18]
0x140045d98  mov     rax, [rcx]
0x140045d9b  lea     r8, [rbp+var_20]
0x140045d9f  lea     rdx, _GUID_2efad216_2482_42af_98f5_35d70f3f5e14
0x140045da6  mov     rax, [rax]
0x140045da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045dae  mov     ebx, eax
0x140045db0  test    eax, eax
0x140045db2  jns     short loc_140045DCE
0x140045db4  mov     rcx, [rbp+18h]; this
0x140045db8  mov     r9d, eax; char *
0x140045dbb  lea     r8, aAvcoreAudiocor_41; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140045dc2  mov     edx, 31h ; '1'; void *
0x140045dc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140045dcc  jmp     short loc_140045E24
0x140045dce  mov     [rbp+var_28], 0
0x140045dd6  mov     rdi, [rbp+var_20]
0x140045dda  mov     rax, [rdi]
0x140045ddd  mov     rbx, [rax+20h]
0x140045de1  xor     edx, edx
0x140045de3  lea     rcx, [rbp+var_28]
0x140045de7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x140045dec  lea     rdx, [rbp+var_28]
0x140045df0  mov     rcx, rdi
0x140045df3  mov     rax, rbx
0x140045df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045dfb  mov     ebx, eax
0x140045dfd  test    eax, eax
0x140045dff  jns     short loc_140045E67
0x140045e01  mov     rcx, [rbp+18h]; this
0x140045e05  mov     r9d, eax; char *
0x140045e08  lea     r8, aAvcoreAudiocor_41; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140045e0f  mov     edx, 34h ; '4'; void *
0x140045e14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140045e19  nop
0x140045e1a  lea     rcx, [rbp+var_28]
0x140045e1e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140045e23  nop
0x140045e24  lea     rcx, [rbp+var_20]
0x140045e28  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x140045e2d  nop
0x140045e2e  lea     rcx, [rbp+arg_18]
0x140045e32  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140045e37  nop
0x140045e38  lea     rcx, [rbp+pvar]; pvar
0x140045e3c  call    cs:__imp_PropVariantClear
0x140045e42  nop
0x140045e43  lea     rcx, [rbp+arg_10]
0x140045e47  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140045e4c  nop
0x140045e4d  lea     rcx, [rbp+arg_8]
0x140045e51  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140045e56  nop
0x140045e57  lea     rcx, [rbp+var_30]
0x140045e5b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140045e60  mov     eax, ebx
0x140045e62  jmp     loc_140045EF1
0x140045e67  mov     rax, [rbp+var_28]
0x140045e6b  mov     [rbp+var_28], 0
0x140045e73  mov     [rsi], rax
0x140045e76  mov     rcx, [rbp+var_20]
0x140045e7a  test    rcx, rcx
0x140045e7d  jz      short loc_140045E8C
0x140045e7f  mov     rax, [rcx]
0x140045e82  mov     rax, [rax+10h]
0x140045e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045e8b  nop
0x140045e8c  mov     rcx, [rbp+arg_18]
0x140045e90  test    rcx, rcx
0x140045e93  jz      short loc_140045EA2
0x140045e95  mov     rax, [rcx]
0x140045e98  mov     rax, [rax+10h]
0x140045e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045ea1  nop
0x140045ea2  lea     rcx, [rbp+pvar]; pvar
0x140045ea6  call    cs:__imp_PropVariantClear
0x140045eac  nop
0x140045ead  mov     rcx, [rbp+arg_10]
0x140045eb1  test    rcx, rcx
0x140045eb4  jz      short loc_140045EC3
0x140045eb6  mov     rax, [rcx]
0x140045eb9  mov     rax, [rax+10h]
0x140045ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045ec2  nop
0x140045ec3  mov     rcx, [rbp+arg_8]
0x140045ec7  test    rcx, rcx
0x140045eca  jz      short loc_140045ED9
0x140045ecc  mov     rax, [rcx]
0x140045ecf  mov     rax, [rax+10h]
0x140045ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045ed8  nop
0x140045ed9  mov     rcx, [rbp+var_30]
0x140045edd  test    rcx, rcx
0x140045ee0  jz      short loc_140045EEF
0x140045ee2  mov     rax, [rcx]
0x140045ee5  mov     rax, [rax+10h]
0x140045ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045eee  nop
0x140045eef  xor     eax, eax
0x140045ef1  mov     rbx, [rsp+60h+arg_0]
0x140045ef9  add     rsp, 60h
0x140045efd  pop     rdi
0x140045efe  pop     rsi
0x140045eff  pop     rbp
0x140045f00  retn
```
