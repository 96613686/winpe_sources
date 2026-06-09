# DmGetTpmIsAlgorithmSupported(ushort const *,int *)

- ea: `0x180062960`
- end: `0x180062c01`
- name: `?DmGetTpmIsAlgorithmSupported@@YAJPEBGPEAH@Z`
- size: `673`
- prototype: `__int64 __fastcall(OLECHAR *psz, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180053c78`
- `0x18005427c`
- `0x180057c6c`
- `0x18005e708`
- `0x180062704`
- `0x180062728`
- `0x180062960`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800629a2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800629a2`
- `OLEAUT32!__imp_SysAllocString` at `0x1800629d3`
- `OLEAUT32!__imp_SysAllocString` at `0x1800629d3`
- `ncrypt!NCryptFreeObject` at `0x180062af5`
- `ncrypt!NCryptFreeObject` at `0x180062af5`
- `ncrypt!NCryptIsAlgSupported` at `0x180062b74`
- `ncrypt!NCryptIsAlgSupported` at `0x180062b74`
- `ncrypt!NCryptOpenStorageProvider` at `0x180062b23`
- `ncrypt!NCryptOpenStorageProvider` at `0x180062b23`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall DmGetTpmIsAlgorithmSupported(OLECHAR *psz, int *a2)
{
  HRESULT Instance; // ebx
  __int64 result; // rax
  BSTR v6; // rax
  int v7; // ebx
  const char *v8; // r9
  __int64 v9; // rax
  int v10; // ebx
  NCRYPT_HANDLE v11; // rbx
  SECURITY_STATUS IsAlgSupported; // ebx
  int v13; // [rsp+20h] [rbp-38h]
  BSTR v14; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v15[32]; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  NCRYPT_HANDLE hObject; // [rsp+68h] [rbp+10h] BYREF
  __int64 *v18; // [rsp+70h] [rbp+18h] BYREF
  LPCWSTR pszAlgId; // [rsp+78h] [rbp+20h] BYREF

  hObject = 0;
  *a2 = 0;
  v18 = 0;
  Instance = CoCreateInstance(
               &GUID_884e2000_217d_11da_b2a4_000e7bbb2b09,
               0,
               1u,
               &GUID_728ab300_217d_11da_b2a4_000e7bbb2b09,
               (LPVOID *)&v18);
  if ( Instance < 0 )
  {
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v18);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
    return (unsigned int)Instance;
  }
  v6 = SysAllocString(psz);
  v14 = v6;
  if ( !v6 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9B,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\inventoryutils\\tpm.cpp",
      (const char *)0x8007000ELL,
      v13);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v18);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
    return 2147942414LL;
  }
  try
  {
    v7 = (*(__int64 (**)(void))(*v18 + 64))();
    if ( v7 < 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v18);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      return (unsigned int)v7;
    }
    pszAlgId = 0;
    v9 = *v18;
    pszAlgId = 0;
    v10 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, LPCWSTR *))(v9 + 112))(v18, 3, 0x40000000, &pszAlgId);
    if ( v10 < 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszAlgId);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
      wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v18);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
      return (unsigned int)v10;
    }
    v11 = hObject;
    if ( hObject )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v15);
      NCryptFreeObject(v11);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v15);
    }
    hObject = 0;
    IsAlgSupported = NCryptOpenStorageProvider(&hObject, L"Microsoft Platform Crypto Provider", 0);
    if ( IsAlgSupported < 0 )
      goto LABEL_12;
    IsAlgSupported = NCryptIsAlgSupported(hObject, pszAlgId, 0);
    if ( IsAlgSupported < 0 )
    {
      if ( IsAlgSupported != -2146893783 )
      {
LABEL_12:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszAlgId);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
        wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v18);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
        return (unsigned int)IsAlgSupported;
      }
    }
    else
    {
      *a2 = 1;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszAlgId);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
    wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(&v18);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xBA,
                           (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\inventoryutils\\tpm.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x180062960  mov     r11, rsp
0x180062963  push    rbx
0x180062964  push    rsi
0x180062965  push    rdi
0x180062966  sub     rsp, 40h
0x18006296a  mov     rdi, rdx
0x18006296d  mov     rsi, rcx
0x180062970  mov     qword ptr [r11+10h], 0
0x180062978  mov     dword ptr [rdx], 0
0x18006297e  mov     qword ptr [r11+18h], 0
0x180062986  lea     rax, [r11+18h]
0x18006298a  mov     [r11-38h], rax
0x18006298e  lea     r9, _GUID_728ab300_217d_11da_b2a4_000e7bbb2b09; riid
0x180062995  xor     edx, edx; pUnkOuter
0x180062997  lea     r8d, [rdx+1]; dwClsContext
0x18006299b  lea     rcx, _GUID_884e2000_217d_11da_b2a4_000e7bbb2b09; rclsid
0x1800629a2  call    cs:__imp_CoCreateInstance
0x1800629a9  nop     dword ptr [rax+rax+00h]
0x1800629ae  mov     ebx, eax
0x1800629b0  test    eax, eax
0x1800629b2  jns     short loc_1800629D0
0x1800629b4  lea     rcx, [rsp+58h+arg_10]
0x1800629b9  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x1800629be  nop
0x1800629bf  lea     rcx, [rsp+58h+hObject]
0x1800629c4  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800629c9  mov     eax, ebx
0x1800629cb  jmp     loc_180062BF8
0x1800629d0  mov     rcx, rsi; psz
0x1800629d3  call    cs:__imp_SysAllocString
0x1800629da  nop     dword ptr [rax+rax+00h]
0x1800629df  mov     [rsp+58h+var_28], rax
0x1800629e4  test    rax, rax
0x1800629e7  jnz     short loc_180062A2F
0x1800629e9  mov     rcx, [rsp+58h]; this
0x1800629ee  mov     ebx, 8007000Eh
0x1800629f3  mov     r9d, ebx; char *
0x1800629f6  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\dm\\dmcmnutils\\inve"...
0x1800629fd  mov     edx, 9Bh; void *
0x180062a02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062a07  nop
0x180062a08  lea     rcx, [rsp+58h+var_28]
0x180062a0d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180062a12  nop
0x180062a13  lea     rcx, [rsp+58h+arg_10]
0x180062a18  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180062a1d  nop
0x180062a1e  lea     rcx, [rsp+58h+hObject]
0x180062a23  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180062a28  mov     eax, ebx
0x180062a2a  jmp     loc_180062BF8
0x180062a2f  mov     rcx, [rsp+58h+arg_10]
0x180062a34  mov     rdx, [rcx]
0x180062a37  mov     r8, [rdx+40h]
0x180062a3b  mov     rdx, rax
0x180062a3e  mov     rax, r8
0x180062a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062a46  mov     ebx, eax
0x180062a48  test    eax, eax
0x180062a4a  jns     short loc_180062A73
0x180062a4c  lea     rcx, [rsp+58h+var_28]
0x180062a51  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180062a56  nop
0x180062a57  lea     rcx, [rsp+58h+arg_10]
0x180062a5c  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180062a61  nop
0x180062a62  lea     rcx, [rsp+58h+hObject]
0x180062a67  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180062a6c  mov     eax, ebx
0x180062a6e  jmp     loc_180062BF8
0x180062a73  mov     [rsp+58h+pszAlgId], 0
0x180062a7c  mov     rcx, [rsp+58h+arg_10]
0x180062a81  mov     rax, [rcx]
0x180062a84  mov     [rsp+58h+pszAlgId], 0
0x180062a8d  lea     r9, [rsp+58h+pszAlgId]
0x180062a92  mov     edx, 3
0x180062a97  mov     r8d, 40000000h
0x180062a9d  mov     rax, [rax+70h]
0x180062aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062aa6  mov     ebx, eax
0x180062aa8  test    eax, eax
0x180062aaa  jns     short loc_180062ADE
0x180062aac  lea     rcx, [rsp+58h+pszAlgId]
0x180062ab1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180062ab6  nop
0x180062ab7  lea     rcx, [rsp+58h+var_28]
0x180062abc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180062ac1  nop
0x180062ac2  lea     rcx, [rsp+58h+arg_10]
0x180062ac7  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180062acc  nop
0x180062acd  lea     rcx, [rsp+58h+hObject]
0x180062ad2  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180062ad7  mov     eax, ebx
0x180062ad9  jmp     loc_180062BF8
0x180062ade  mov     rbx, [rsp+58h+hObject]
0x180062ae3  test    rbx, rbx
0x180062ae6  jz      short loc_180062B0B
0x180062ae8  lea     rcx, [rsp+58h+var_20]; this
0x180062aed  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180062af2  mov     rcx, rbx; hObject
0x180062af5  call    cs:__imp_NCryptFreeObject
0x180062afc  nop     dword ptr [rax+rax+00h]
0x180062b01  lea     rcx, [rsp+58h+var_20]; this
0x180062b06  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180062b0b  mov     [rsp+58h+hObject], 0
0x180062b14  xor     r8d, r8d; dwFlags
0x180062b17  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x180062b1e  lea     rcx, [rsp+58h+hObject]; phProvider
0x180062b23  call    cs:__imp_NCryptOpenStorageProvider
0x180062b2a  nop     dword ptr [rax+rax+00h]
0x180062b2f  mov     ebx, eax
0x180062b31  test    eax, eax
0x180062b33  jns     short loc_180062B67
0x180062b35  lea     rcx, [rsp+58h+pszAlgId]
0x180062b3a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180062b3f  nop
0x180062b40  lea     rcx, [rsp+58h+var_28]
0x180062b45  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180062b4a  nop
0x180062b4b  lea     rcx, [rsp+58h+arg_10]
0x180062b50  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180062b55  nop
0x180062b56  lea     rcx, [rsp+58h+hObject]
0x180062b5b  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180062b60  mov     eax, ebx
0x180062b62  jmp     loc_180062BF8
0x180062b67  xor     r8d, r8d; dwFlags
0x180062b6a  mov     rdx, [rsp+58h+pszAlgId]; pszAlgId
0x180062b6f  mov     rcx, [rsp+58h+hObject]; hProvider
0x180062b74  call    cs:__imp_NCryptIsAlgSupported
0x180062b7b  nop     dword ptr [rax+rax+00h]
0x180062b80  mov     ebx, eax
0x180062b82  test    eax, eax
0x180062b84  js      short loc_180062B8E
0x180062b86  mov     dword ptr [rdi], 1
0x180062b8c  jmp     short loc_180062BC5
0x180062b8e  cmp     ebx, 80090029h
0x180062b94  jz      short loc_180062BC5
0x180062b96  lea     rcx, [rsp+58h+pszAlgId]
0x180062b9b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180062ba0  nop
0x180062ba1  lea     rcx, [rsp+58h+var_28]
0x180062ba6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180062bab  nop
0x180062bac  lea     rcx, [rsp+58h+arg_10]
0x180062bb1  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180062bb6  nop
0x180062bb7  lea     rcx, [rsp+58h+hObject]
0x180062bbc  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180062bc1  mov     eax, ebx
0x180062bc3  jmp     short loc_180062BF8
0x180062bc5  lea     rcx, [rsp+58h+pszAlgId]
0x180062bca  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180062bcf  nop
0x180062bd0  lea     rcx, [rsp+58h+var_28]
0x180062bd5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180062bda  nop
0x180062bdb  lea     rcx, [rsp+58h+arg_10]
0x180062be0  call    ??1?$com_ptr_t@UIObjectId@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IObjectId,wil::err_exception_policy>::~com_ptr_t<IObjectId,wil::err_exception_policy>(void)
0x180062be5  nop
0x180062be6  lea     rcx, [rsp+58h+hObject]
0x180062beb  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180062bf0  xor     eax, eax
0x180062bf2  jmp     short loc_180062BF8
0x180062bf4  mov     eax, dword ptr [rsp+58h+hObject]
0x180062bf8  add     rsp, 40h
0x180062bfc  pop     rdi
0x180062bfd  pop     rsi
0x180062bfe  pop     rbx
0x180062bff  retn
```
