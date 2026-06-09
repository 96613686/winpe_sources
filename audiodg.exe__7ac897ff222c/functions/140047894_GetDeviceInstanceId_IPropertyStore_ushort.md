# GetDeviceInstanceId(IPropertyStore *,ushort * *)

- ea: `0x140047894`
- end: `0x140047ade`
- name: `?GetDeviceInstanceId@@YAJPEAUIPropertyStore@@PEAPEAG@Z`
- size: `586`
- prototype: `__int64 __fastcall(struct IPropertyStore *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400476e8`

## callees

- `0x140008124`
- `0x14000c33c`
- `0x140016f68`
- `0x14001d790`
- `0x140047894`
- `0x14004df60`
- `0x1400516e8`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400478d5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400478d5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140047948`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140047980`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140047abe`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140047948`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140047980`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140047abe`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall GetDeviceInstanceId(struct IPropertyStore *a1, unsigned __int16 **a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  __int64 v7; // rax
  int v8; // eax
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, unsigned __int16 **); // rbx
  int v12; // eax
  unsigned __int16 *v13; // rax
  int ppv; // [rsp+20h] [rbp-30h]
  LPVOID v16; // [rsp+30h] [rbp-20h] BYREF
  PROPVARIANT pvar[2]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v18; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  __int64 v20; // [rsp+78h] [rbp+28h] BYREF
  unsigned __int16 *v21; // [rsp+80h] [rbp+30h] BYREF
  __int64 v22; // [rsp+88h] [rbp+38h] BYREF

  *a2 = 0;
  v16 = 0;
  v4 = CoCreateInstance(&CLSID_MMDeviceEnumerator, 0, 0x17u, &GUID_a95664d2_9614_4f35_a746_de8db63617e6, &v16);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x196,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)(unsigned int)v4,
      ppv);
LABEL_19:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
    return v5;
  }
  *(_OWORD *)pvar = 0;
  v18 = 0;
  v6 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))a1->lpVtbl->GetValue)(
         a1,
         PKEY_Endpoint_Devnode,
         pvar);
  v5 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x199,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)(unsigned int)v6,
      ppv);
LABEL_5:
    PropVariantClear(pvar);
    goto LABEL_19;
  }
  if ( LOWORD(pvar[0]) == 31 )
  {
    v20 = 0;
    v7 = *(_QWORD *)v16;
    v20 = 0;
    v8 = (*(__int64 (__fastcall **)(LPVOID, PROPVARIANT, __int64 *))(v7 + 40))(v16, pvar[1], &v20);
    v5 = v8;
    if ( v8 >= 0 )
    {
      v22 = 0;
      v9 = wil::com_query_to_nothrow<IPnpDevnode,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(&v20, &v22);
      v5 = v9;
      if ( v9 >= 0 )
      {
        v21 = 0;
        v10 = v22;
        v11 = *(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v22 + 32LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          (void **)&v21,
          0);
        v12 = v11(v10, &v21);
        v5 = v12;
        if ( v12 >= 0 )
        {
          v13 = v21;
          v21 = 0;
          *a2 = v13;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v21);
          wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v22);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
          PropVariantClear(pvar);
          v5 = 0;
          goto LABEL_19;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A3,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
          (const char *)(unsigned int)v12,
          ppv);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v21);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A0,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
          (const char *)(unsigned int)v9,
          ppv);
      }
      wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v22);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19D,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
        (const char *)(unsigned int)v8,
        ppv);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
    goto LABEL_5;
  }
  v5 = -2147418113;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x19A,
    (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
    (const char *)0x8000FFFFLL,
    ppv);
  PropVariantClear(pvar);
  if ( v16 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
  return v5;
}

```

## disassembly

```asm
0x140047894  mov     [rsp-18h+arg_0], rbx
0x140047899  push    rbp
0x14004789a  push    rsi
0x14004789b  push    rdi
0x14004789c  mov     rbp, rsp
0x14004789f  sub     rsp, 50h
0x1400478a3  mov     rsi, rdx
0x1400478a6  mov     rdi, rcx
0x1400478a9  mov     qword ptr [rdx], 0
0x1400478b0  mov     [rbp+var_20], 0
0x1400478b8  lea     rax, [rbp+var_20]
0x1400478bc  mov     qword ptr [rsp+50h+ppv], rax; int
0x1400478c1  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x1400478c8  xor     edx, edx; pUnkOuter
0x1400478ca  lea     r8d, [rdx+17h]; dwClsContext
0x1400478ce  lea     rcx, CLSID_MMDeviceEnumerator; rclsid
0x1400478d5  call    cs:__imp_CoCreateInstance
0x1400478db  mov     ebx, eax
0x1400478dd  test    eax, eax
0x1400478df  jns     short loc_1400478FE
0x1400478e1  mov     rcx, [rbp+18h]; this
0x1400478e5  mov     r9d, eax; char *
0x1400478e8  lea     r8, aAvcoreAudiocor_79; "avcore\\audiocore\\server\\lib\\audioen"...
0x1400478ef  mov     edx, 196h; void *
0x1400478f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400478f9  jmp     loc_140047AC6
0x1400478fe  xorps   xmm0, xmm0
0x140047901  xor     eax, eax
0x140047903  movups  xmmword ptr [rbp+pvar], xmm0
0x140047907  mov     [rbp+var_8], rax
0x14004790b  mov     rax, [rdi]
0x14004790e  lea     r8, [rbp+pvar]
0x140047912  lea     rdx, PKEY_Endpoint_Devnode
0x140047919  mov     rcx, rdi
0x14004791c  mov     rax, [rax+28h]
0x140047920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047925  mov     ebx, eax
0x140047927  test    eax, eax
0x140047929  jns     short loc_140047953
0x14004792b  mov     rcx, [rbp+18h]; this
0x14004792f  mov     r9d, eax; char *
0x140047932  lea     r8, aAvcoreAudiocor_79; "avcore\\audiocore\\server\\lib\\audioen"...
0x140047939  mov     edx, 199h; void *
0x14004793e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140047943  nop
0x140047944  lea     rcx, [rbp+pvar]; pvar
0x140047948  call    cs:__imp_PropVariantClear
0x14004794e  jmp     loc_140047AC6
0x140047953  mov     eax, 1Fh
0x140047958  cmp     ax, word ptr [rbp+pvar]
0x14004795c  jz      short loc_1400479A2
0x14004795e  mov     rcx, [rbp+18h]; this
0x140047962  mov     ebx, 8000FFFFh
0x140047967  mov     r9d, ebx; char *
0x14004796a  lea     r8, aAvcoreAudiocor_79; "avcore\\audiocore\\server\\lib\\audioen"...
0x140047971  mov     edx, 19Ah; void *
0x140047976  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004797b  nop
0x14004797c  lea     rcx, [rbp+pvar]; pvar
0x140047980  call    cs:__imp_PropVariantClear
0x140047986  nop
0x140047987  mov     rcx, [rbp+var_20]
0x14004798b  test    rcx, rcx
0x14004798e  jz      short loc_14004799D
0x140047990  mov     rdx, [rcx]
0x140047993  mov     rax, [rdx+10h]
0x140047997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004799c  nop
0x14004799d  jmp     loc_140047ACF
0x1400479a2  mov     [rbp+arg_8], 0
0x1400479aa  mov     rcx, [rbp+var_20]
0x1400479ae  mov     rax, [rcx]
0x1400479b1  mov     [rbp+arg_8], 0
0x1400479b9  lea     r8, [rbp+arg_8]
0x1400479bd  mov     rdx, [rbp+pvar+8]
0x1400479c1  mov     rax, [rax+28h]
0x1400479c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400479ca  mov     ebx, eax
0x1400479cc  test    eax, eax
0x1400479ce  jns     short loc_1400479F7
0x1400479d0  mov     rcx, [rbp+18h]; this
0x1400479d4  mov     r9d, eax; char *
0x1400479d7  lea     r8, aAvcoreAudiocor_79; "avcore\\audiocore\\server\\lib\\audioen"...
0x1400479de  mov     edx, 19Dh; void *
0x1400479e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400479e8  nop
0x1400479e9  lea     rcx, [rbp+arg_8]
0x1400479ed  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400479f2  jmp     loc_140047944
0x1400479f7  mov     [rbp+arg_18], 0
0x1400479ff  lea     rdx, [rbp+arg_18]
0x140047a03  lea     rcx, [rbp+arg_8]
0x140047a07  call    ??$com_query_to_nothrow@UIPnpDevnode@@AEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@@wil@@YAJAEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@0@PEAPEAUIPnpDevnode@@@Z; wil::com_query_to_nothrow<IPnpDevnode,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &,IPnpDevnode * *)
0x140047a0c  mov     ebx, eax
0x140047a0e  test    eax, eax
0x140047a10  jns     short loc_140047A36
0x140047a12  mov     rcx, [rbp+18h]; this
0x140047a16  mov     r9d, eax; char *
0x140047a19  lea     r8, aAvcoreAudiocor_79; "avcore\\audiocore\\server\\lib\\audioen"...
0x140047a20  mov     edx, 1A0h; void *
0x140047a25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140047a2a  nop
0x140047a2b  lea     rcx, [rbp+arg_18]
0x140047a2f  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x140047a34  jmp     short loc_1400479E9
0x140047a36  mov     [rbp+arg_10], 0
0x140047a3e  mov     rdi, [rbp+arg_18]
0x140047a42  mov     rax, [rdi]
0x140047a45  mov     rbx, [rax+20h]
0x140047a49  xor     edx, edx
0x140047a4b  lea     rcx, [rbp+arg_10]
0x140047a4f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x140047a54  lea     rdx, [rbp+arg_10]
0x140047a58  mov     rcx, rdi
0x140047a5b  mov     rax, rbx
0x140047a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047a63  mov     ebx, eax
0x140047a65  test    eax, eax
0x140047a67  jns     short loc_140047A8D
0x140047a69  mov     rcx, [rbp+18h]; this
0x140047a6d  mov     r9d, eax; char *
0x140047a70  lea     r8, aAvcoreAudiocor_79; "avcore\\audiocore\\server\\lib\\audioen"...
0x140047a77  mov     edx, 1A3h; void *
0x140047a7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140047a81  nop
0x140047a82  lea     rcx, [rbp+arg_10]
0x140047a86  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140047a8b  jmp     short loc_140047A2B
0x140047a8d  mov     rax, [rbp+arg_10]
0x140047a91  mov     [rbp+arg_10], 0
0x140047a99  mov     [rsi], rax
0x140047a9c  lea     rcx, [rbp+arg_10]
0x140047aa0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140047aa5  nop
0x140047aa6  lea     rcx, [rbp+arg_18]
0x140047aaa  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x140047aaf  nop
0x140047ab0  lea     rcx, [rbp+arg_8]
0x140047ab4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140047ab9  nop
0x140047aba  lea     rcx, [rbp+pvar]; pvar
0x140047abe  call    cs:__imp_PropVariantClear
0x140047ac4  xor     ebx, ebx
0x140047ac6  lea     rcx, [rbp+var_20]
0x140047aca  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140047acf  mov     eax, ebx
0x140047ad1  mov     rbx, [rsp+50h+arg_0]
0x140047ad6  add     rsp, 50h
0x140047ada  pop     rdi
0x140047adb  pop     rsi
0x140047adc  pop     rbp
0x140047add  retn
```
