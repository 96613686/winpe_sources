# GetDeviceInstanceId(IPropertyStore *,ushort * *)

- ea: `0x180021cb0`
- end: `0x180021ed6`
- name: `?GetDeviceInstanceId@@YAJPEAUIPropertyStore@@PEAPEAG@Z`
- size: `550`
- prototype: `__int64 __fastcall(struct IPropertyStore *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002187c`

## callees

- `0x180006b0c`
- `0x18000fb60`
- `0x180010da8`
- `0x180021030`
- `0x180021cb0`
- `0x1800338e0`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021cf1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021cf1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021eb7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021eb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021e87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021e87`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall GetDeviceInstanceId(struct IPropertyStore *a1, unsigned __int16 **a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, LPVOID *); // rbx
  int v14; // eax
  unsigned __int16 *v15; // rax
  int ppv; // [rsp+20h] [rbp-30h]
  LPVOID v18; // [rsp+30h] [rbp-20h] BYREF
  PROPVARIANT pvar[2]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v20; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  __int64 v22; // [rsp+78h] [rbp+28h] BYREF
  __int64 v23; // [rsp+80h] [rbp+30h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+38h] BYREF

  *a2 = 0;
  v18 = 0;
  v4 = CoCreateInstance(&CLSID_MMDeviceEnumerator, 0, 0x17u, &GUID_a95664d2_9614_4f35_a746_de8db63617e6, &v18);
  v5 = v4;
  if ( v4 >= 0 )
  {
    *(_OWORD *)pvar = 0;
    v20 = 0;
    v6 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))a1->lpVtbl->GetValue)(
           a1,
           PKEY_Endpoint_Devnode,
           pvar);
    v5 = v6;
    if ( v6 >= 0 )
    {
      if ( LOWORD(pvar[0]) == 31 )
      {
        v22 = 0;
        v9 = *(_QWORD *)v18;
        v22 = 0;
        v10 = (*(__int64 (__fastcall **)(LPVOID, PROPVARIANT, __int64 *))(v9 + 40))(v18, pvar[1], &v22);
        v5 = v10;
        if ( v10 >= 0 )
        {
          v23 = 0;
          wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v23);
          v11 = wil::com_query_to_nothrow<IPnpDevnode,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(
                  &v22,
                  (__int64)&v23);
          v5 = v11;
          if ( v11 >= 0 )
          {
            pv = 0;
            v12 = v23;
            v13 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v23 + 32LL);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &pv,
              0);
            v14 = v13(v12, &pv);
            v5 = v14;
            if ( v14 >= 0 )
            {
              v15 = (unsigned __int16 *)pv;
              pv = 0;
              *a2 = v15;
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
              v5 = 0;
              goto LABEL_20;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1A3,
              (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
              (const char *)(unsigned int)v14,
              ppv);
            if ( pv )
              CoTaskMemFree(pv);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1A0,
              (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
              (const char *)(unsigned int)v11,
              ppv);
          }
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x19D,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
            (const char *)(unsigned int)v10,
            ppv);
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
LABEL_20:
        PropVariantClear(pvar);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v18);
        return v5;
      }
      v5 = -2147418113;
      v7 = 2147549183LL;
      v8 = 410;
    }
    else
    {
      v7 = (unsigned int)v6;
      v8 = 409;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)v7,
      ppv);
    goto LABEL_20;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x196,
    (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
    (const char *)(unsigned int)v4,
    ppv);
  if ( v18 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
  return v5;
}

```

## disassembly

```asm
0x180021cb0  mov     [rsp-18h+arg_0], rbx
0x180021cb5  push    rbp
0x180021cb6  push    rsi
0x180021cb7  push    rdi
0x180021cb8  mov     rbp, rsp
0x180021cbb  sub     rsp, 50h
0x180021cbf  mov     rsi, rdx
0x180021cc2  mov     rdi, rcx
0x180021cc5  mov     qword ptr [rdx], 0
0x180021ccc  mov     [rbp+var_20], 0
0x180021cd4  lea     rax, [rbp+var_20]
0x180021cd8  mov     qword ptr [rsp+50h+ppv], rax; int
0x180021cdd  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x180021ce4  xor     edx, edx; pUnkOuter
0x180021ce6  lea     r8d, [rdx+17h]; dwClsContext
0x180021cea  lea     rcx, CLSID_MMDeviceEnumerator; rclsid
0x180021cf1  call    cs:__imp_CoCreateInstance
0x180021cf7  mov     ebx, eax
0x180021cf9  test    eax, eax
0x180021cfb  jns     short loc_180021D31
0x180021cfd  mov     rcx, [rbp+18h]; this
0x180021d01  mov     r9d, eax; char *
0x180021d04  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x180021d0b  mov     edx, 196h; void *
0x180021d10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021d15  nop
0x180021d16  mov     rcx, [rbp+var_20]
0x180021d1a  test    rcx, rcx
0x180021d1d  jz      short loc_180021D2C
0x180021d1f  mov     rax, [rcx]
0x180021d22  mov     rax, [rax+10h]
0x180021d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d2b  nop
0x180021d2c  jmp     loc_180021EC7
0x180021d31  xorps   xmm0, xmm0
0x180021d34  xor     eax, eax
0x180021d36  movups  xmmword ptr [rbp+pvar], xmm0
0x180021d3a  mov     [rbp+var_8], rax
0x180021d3e  mov     rax, [rdi]
0x180021d41  lea     r8, [rbp+pvar]
0x180021d45  lea     rdx, PKEY_Endpoint_Devnode
0x180021d4c  mov     rcx, rdi
0x180021d4f  mov     rax, [rax+28h]
0x180021d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d58  mov     ebx, eax
0x180021d5a  test    eax, eax
0x180021d5c  jns     short loc_180021D68
0x180021d5e  mov     r9d, eax
0x180021d61  mov     edx, 199h
0x180021d66  jmp     short loc_180021D80
0x180021d68  mov     eax, 1Fh
0x180021d6d  cmp     ax, word ptr [rbp+pvar]
0x180021d71  jz      short loc_180021D95
0x180021d73  mov     ebx, 8000FFFFh
0x180021d78  mov     r9d, ebx; char *
0x180021d7b  mov     edx, 19Ah; void *
0x180021d80  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x180021d87  mov     rcx, [rbp+18h]; this
0x180021d8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021d90  jmp     loc_180021EB3
0x180021d95  mov     [rbp+arg_8], 0
0x180021d9d  mov     rcx, [rbp+var_20]
0x180021da1  mov     rax, [rcx]
0x180021da4  mov     [rbp+arg_8], 0
0x180021dac  lea     r8, [rbp+arg_8]
0x180021db0  mov     rdx, [rbp+pvar+8]
0x180021db4  mov     rax, [rax+28h]
0x180021db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021dbd  mov     ebx, eax
0x180021dbf  test    eax, eax
0x180021dc1  jns     short loc_180021DEA
0x180021dc3  mov     rcx, [rbp+18h]; this
0x180021dc7  mov     r9d, eax; char *
0x180021dca  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x180021dd1  mov     edx, 19Dh; void *
0x180021dd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021ddb  nop
0x180021ddc  lea     rcx, [rbp+arg_8]
0x180021de0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180021de5  jmp     loc_180021EB3
0x180021dea  mov     [rbp+arg_10], 0
0x180021df2  lea     rcx, [rbp+arg_10]
0x180021df6  call    ?reset@?$com_ptr_t@UIPnpDevnode@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(void)
0x180021dfb  lea     rdx, [rbp+arg_10]
0x180021dff  lea     rcx, [rbp+arg_8]
0x180021e03  call    ??$com_query_to_nothrow@UIPnpDevnode@@AEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@@wil@@YAJAEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@0@PEAPEAUIPnpDevnode@@@Z; wil::com_query_to_nothrow<IPnpDevnode,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &,IPnpDevnode * *)
0x180021e08  mov     ebx, eax
0x180021e0a  test    eax, eax
0x180021e0c  jns     short loc_180021E32
0x180021e0e  mov     rcx, [rbp+18h]; this
0x180021e12  mov     r9d, eax; char *
0x180021e15  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x180021e1c  mov     edx, 1A0h; void *
0x180021e21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021e26  nop
0x180021e27  lea     rcx, [rbp+arg_10]
0x180021e2b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180021e30  jmp     short loc_180021DDC
0x180021e32  mov     [rbp+pv], 0
0x180021e3a  mov     rdi, [rbp+arg_10]
0x180021e3e  mov     rax, [rdi]
0x180021e41  mov     rbx, [rax+20h]
0x180021e45  xor     edx, edx
0x180021e47  lea     rcx, [rbp+pv]
0x180021e4b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180021e50  lea     rdx, [rbp+pv]
0x180021e54  mov     rcx, rdi
0x180021e57  mov     rax, rbx
0x180021e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e5f  mov     ebx, eax
0x180021e61  test    eax, eax
0x180021e63  jns     short loc_180021E8F
0x180021e65  mov     rcx, [rbp+18h]; this
0x180021e69  mov     r9d, eax; char *
0x180021e6c  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x180021e73  mov     edx, 1A3h; void *
0x180021e78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021e7d  nop
0x180021e7e  mov     rcx, [rbp+pv]; pv
0x180021e82  test    rcx, rcx
0x180021e85  jz      short loc_180021E27
0x180021e87  call    cs:__imp_CoTaskMemFree
0x180021e8d  jmp     short loc_180021E27
0x180021e8f  mov     rax, [rbp+pv]
0x180021e93  mov     [rbp+pv], 0
0x180021e9b  mov     [rsi], rax
0x180021e9e  lea     rcx, [rbp+arg_10]
0x180021ea2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180021ea7  nop
0x180021ea8  lea     rcx, [rbp+arg_8]
0x180021eac  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180021eb1  xor     ebx, ebx
0x180021eb3  lea     rcx, [rbp+pvar]; pvar
0x180021eb7  call    cs:__imp_PropVariantClear
0x180021ebd  nop
0x180021ebe  lea     rcx, [rbp+var_20]
0x180021ec2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180021ec7  mov     eax, ebx
0x180021ec9  mov     rbx, [rsp+50h+arg_0]
0x180021ece  add     rsp, 50h
0x180021ed2  pop     rdi
0x180021ed3  pop     rsi
0x180021ed4  pop     rbp
0x180021ed5  retn
```
