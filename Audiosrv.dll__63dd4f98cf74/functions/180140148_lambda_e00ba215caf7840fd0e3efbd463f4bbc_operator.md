# _lambda_e00ba215caf7840fd0e3efbd463f4bbc_::operator()

- ea: `0x180140148`
- end: `0x18014051c`
- name: `_lambda_e00ba215caf7840fd0e3efbd463f4bbc_::operator()`
- size: `980`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180144440`

## callees

- `0x18000a470`
- `0x18000ae1c`
- `0x18000cba0`
- `0x18000e284`
- `0x18001280c`
- `0x1800424ec`
- `0x18005d068`
- `0x1800cd8d0`
- `0x180140148`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180140473`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180140473`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18014044c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18014044c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801403ce`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180140489`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801403ce`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180140489`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18014024f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18014024f`

## string_xrefs

- `0x180140265`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall lambda_e00ba215caf7840fd0e3efbd463f4bbc_::operator()(_BYTE **a1)
{
  int v2; // ebx
  __int64 v3; // rax
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64 *); // rbx
  HRESULT v6; // eax
  __int64 v7; // rdx
  LPVOID v8; // rdi
  __int64 (__fastcall *v9)(LPVOID, __int64, _QWORD); // rbx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rax
  unsigned int v13; // r10d
  int ppv; // [rsp+20h] [rbp-E0h]
  __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64 **); // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v19; // [rsp+58h] [rbp-A8h] BYREF
  __int64 (__fastcall ***v20)(_QWORD, GUID *, __int64 **); // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v21; // [rsp+68h] [rbp-98h] BYREF
  __int64 *v22; // [rsp+70h] [rbp-90h] BYREF
  __int64 v23; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v24; // [rsp+80h] [rbp-80h] BYREF
  DWORD pcbData; // [rsp+88h] [rbp-78h] BYREF
  PROPVARIANT pvar[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v27; // [rsp+A0h] [rbp-60h]
  WCHAR SubKey[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR String1[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4F8h] [rbp+3F8h]

  v24 = 0;
  v2 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64, _QWORD, __int64 **))(**(_QWORD **)*a1 + 24LL))(
         *(_QWORD *)*a1,
         &GUID_2a07407e_6497_4a18_9787_32f79bd0d98f,
         23,
         0,
         &v24);
  if ( v2 >= 0 )
  {
    v16 = 0;
    v3 = *v24;
    v16 = 0;
    v2 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v3 + 32))(v24, 0, &v16);
    if ( v2 < 0 )
    {
LABEL_3:
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v16);
      goto LABEL_27;
    }
    v17 = 0;
    v4 = v16;
    v5 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 80LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v17,
      0);
    v2 = v5(v4, &v17);
    if ( v2 < 0 )
    {
LABEL_5:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v17);
      goto LABEL_3;
    }
    v19 = 0;
    v6 = CoCreateInstance(
           &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
           0,
           0x17u,
           &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
           &v19);
    v2 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2449,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
        (const char *)(unsigned int)v6,
        ppv);
LABEL_8:
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v19);
      goto LABEL_5;
    }
    v18 = 0;
    v8 = v19;
    v9 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)v19 + 40LL);
    wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v18, v7);
    v2 = v9(v8, v17, &v18);
    if ( v2 < 0 )
    {
LABEL_10:
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v18);
      goto LABEL_8;
    }
    v21 = 0;
    v2 = (**v18)(v18, &GUID_3ade56af_4375_4413_9c91_4c652595ab07, &v21);
    if ( v2 < 0 )
    {
LABEL_12:
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v21);
      goto LABEL_10;
    }
    v20 = 0;
    v10 = *v21;
    v20 = 0;
    v2 = (*(__int64 (__fastcall **)(__int64 *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 **)))(v10 + 24))(
           v21,
           &v20);
    if ( v2 < 0 )
    {
LABEL_14:
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v20);
      goto LABEL_12;
    }
    v22 = 0;
    wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v22, v11);
    v2 = (**v20)(v20, &GUID_d666063f_1587_4e43_81f1_b948e807363f, &v22);
    if ( v2 < 0 )
    {
LABEL_16:
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v22);
      goto LABEL_14;
    }
    v23 = 0;
    v12 = *v22;
    v23 = 0;
    v2 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v12 + 32))(v22, 0, &v23);
    if ( v2 < 0 )
    {
LABEL_18:
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v23);
      goto LABEL_16;
    }
    *(_OWORD *)pvar = 0;
    v27 = 0;
    v2 = (*(__int64 (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v23 + 40LL))(
           v23,
           &DEVPKEY_Device_Driver,
           pvar);
    if ( v2 < 0 )
    {
LABEL_20:
      PropVariantClear(pvar);
      goto LABEL_18;
    }
    if ( LOWORD(pvar[0]) == 31 )
    {
      pcbData = 520;
      v2 = StringCbCopyW(SubKey, 0x208u, L"SYSTEM\\CurrentControlSet\\Control\\Class\\");
      if ( v2 < 0 )
        goto LABEL_20;
      v2 = StringCbCatW(SubKey, v13, (const unsigned __int16 *)pvar[1]);
      if ( v2 < 0 )
        goto LABEL_20;
      if ( !RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"Driver", 2u, 0, String1, &pcbData) )
        *a1[1] = CompareStringOrdinal(String1, -1, L"smwdm.sys", 9, 1) == 2;
    }
    PropVariantClear(pvar);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v23);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v22);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v20);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v21);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v18);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v19);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v17);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v16);
    v2 = 0;
  }
LABEL_27:
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v24);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180140148  mov     [rsp-8+arg_8], rbx
0x18014014d  mov     [rsp-8+arg_10], rsi
0x180140152  push    rbp
0x180140153  push    rdi
0x180140154  push    r14
0x180140156  lea     rbp, [rsp-3E0h]
0x18014015e  sub     rsp, 4E0h
0x180140165  mov     rax, cs:__security_cookie
0x18014016c  xor     rax, rsp
0x18014016f  mov     [rbp+3F0h+var_20], rax
0x180140176  mov     rsi, rcx
0x180140179  xor     r14d, r14d
0x18014017c  mov     [rbp+3F0h+var_470], r14
0x180140180  mov     rax, [rcx]
0x180140183  mov     rcx, [rax]
0x180140186  mov     rax, [rcx]
0x180140189  mov     [rbp+3F0h+var_470], r14
0x18014018d  lea     rdx, [rbp+3F0h+var_470]
0x180140191  mov     [rsp+4F0h+ppv], rdx
0x180140196  xor     r9d, r9d
0x180140199  lea     r8d, [r14+17h]
0x18014019d  lea     rdx, _GUID_2a07407e_6497_4a18_9787_32f79bd0d98f
0x1801401a4  mov     rax, [rax+18h]
0x1801401a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801401ad  mov     ebx, eax
0x1801401af  test    eax, eax
0x1801401b1  js      loc_1801404EA
0x1801401b7  mov     [rsp+4F0h+var_4B0], r14
0x1801401bc  mov     rcx, [rbp+3F0h+var_470]
0x1801401c0  mov     rax, [rcx]
0x1801401c3  mov     [rsp+4F0h+var_4B0], r14
0x1801401c8  lea     r8, [rsp+4F0h+var_4B0]
0x1801401cd  xor     edx, edx
0x1801401cf  mov     rax, [rax+20h]
0x1801401d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801401d8  mov     ebx, eax
0x1801401da  test    eax, eax
0x1801401dc  jns     short loc_1801401ED
0x1801401de  lea     rcx, [rsp+4F0h+var_4B0]
0x1801401e3  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1801401e8  jmp     loc_1801404EA
0x1801401ed  mov     [rsp+4F0h+var_4A8], r14
0x1801401f2  mov     rdi, [rsp+4F0h+var_4B0]
0x1801401f7  mov     rax, [rdi]
0x1801401fa  mov     rbx, [rax+50h]
0x1801401fe  xor     edx, edx
0x180140200  lea     rcx, [rsp+4F0h+var_4A8]
0x180140205  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18014020a  lea     rdx, [rsp+4F0h+var_4A8]
0x18014020f  mov     rcx, rdi
0x180140212  mov     rax, rbx
0x180140215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014021a  mov     ebx, eax
0x18014021c  test    eax, eax
0x18014021e  jns     short loc_18014022C
0x180140220  lea     rcx, [rsp+4F0h+var_4A8]
0x180140225  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18014022a  jmp     short loc_1801401DE
0x18014022c  mov     [rsp+4F0h+var_498], r14
0x180140231  lea     rax, [rsp+4F0h+var_498]
0x180140236  mov     [rsp+4F0h+ppv], rax; int
0x18014023b  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x180140242  xor     edx, edx; pUnkOuter
0x180140244  lea     r8d, [rdx+17h]; dwClsContext
0x180140248  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x18014024f  call    cs:__imp_CoCreateInstance
0x180140255  mov     ebx, eax
0x180140257  test    eax, eax
0x180140259  jns     short loc_180140283
0x18014025b  mov     rcx, [rbp+3F8h]; this
0x180140262  mov     r9d, eax; char *
0x180140265  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x18014026c  mov     edx, 2449h; void *
0x180140271  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180140276  nop
0x180140277  lea     rcx, [rsp+4F0h+var_498]
0x18014027c  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180140281  jmp     short loc_180140220
0x180140283  mov     [rsp+4F0h+var_4A0], r14
0x180140288  mov     rdi, [rsp+4F0h+var_498]
0x18014028d  mov     rax, [rdi]
0x180140290  mov     rbx, [rax+28h]
0x180140294  lea     rcx, [rsp+4F0h+var_4A0]
0x180140299  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x18014029e  lea     r8, [rsp+4F0h+var_4A0]
0x1801402a3  mov     rdx, [rsp+4F0h+var_4A8]
0x1801402a8  mov     rcx, rdi
0x1801402ab  mov     rax, rbx
0x1801402ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801402b3  mov     ebx, eax
0x1801402b5  test    eax, eax
0x1801402b7  jns     short loc_1801402C5
0x1801402b9  lea     rcx, [rsp+4F0h+var_4A0]
0x1801402be  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1801402c3  jmp     short loc_180140277
0x1801402c5  mov     [rsp+4F0h+var_488], r14
0x1801402ca  mov     rcx, [rsp+4F0h+var_4A0]
0x1801402cf  mov     rax, [rcx]
0x1801402d2  lea     r8, [rsp+4F0h+var_488]
0x1801402d7  lea     rdx, _GUID_3ade56af_4375_4413_9c91_4c652595ab07
0x1801402de  mov     rax, [rax]
0x1801402e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801402e6  mov     ebx, eax
0x1801402e8  test    eax, eax
0x1801402ea  jns     short loc_1801402F8
0x1801402ec  lea     rcx, [rsp+4F0h+var_488]
0x1801402f1  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1801402f6  jmp     short loc_1801402B9
0x1801402f8  mov     [rsp+4F0h+var_490], r14
0x1801402fd  mov     rcx, [rsp+4F0h+var_488]
0x180140302  mov     rax, [rcx]
0x180140305  mov     [rsp+4F0h+var_490], r14
0x18014030a  lea     rdx, [rsp+4F0h+var_490]
0x18014030f  mov     rax, [rax+18h]
0x180140313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180140318  mov     ebx, eax
0x18014031a  test    eax, eax
0x18014031c  jns     short loc_18014032A
0x18014031e  lea     rcx, [rsp+4F0h+var_490]
0x180140323  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180140328  jmp     short loc_1801402EC
0x18014032a  mov     [rsp+4F0h+var_480], r14
0x18014032f  lea     rcx, [rsp+4F0h+var_480]
0x180140334  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x180140339  mov     rcx, [rsp+4F0h+var_490]
0x18014033e  mov     rax, [rcx]
0x180140341  lea     r8, [rsp+4F0h+var_480]
0x180140346  lea     rdx, _GUID_d666063f_1587_4e43_81f1_b948e807363f
0x18014034d  mov     rax, [rax]
0x180140350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180140355  mov     ebx, eax
0x180140357  test    eax, eax
0x180140359  jns     short loc_180140367
0x18014035b  lea     rcx, [rsp+4F0h+var_480]
0x180140360  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180140365  jmp     short loc_18014031E
0x180140367  mov     [rsp+4F0h+var_478], r14
0x18014036c  mov     rcx, [rsp+4F0h+var_480]
0x180140371  mov     rax, [rcx]
0x180140374  mov     [rsp+4F0h+var_478], r14
0x180140379  lea     r8, [rsp+4F0h+var_478]
0x18014037e  xor     edx, edx
0x180140380  mov     rax, [rax+20h]
0x180140384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180140389  mov     ebx, eax
0x18014038b  test    eax, eax
0x18014038d  jns     short loc_18014039B
0x18014038f  lea     rcx, [rsp+4F0h+var_478]
0x180140394  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180140399  jmp     short loc_18014035B
0x18014039b  xorps   xmm0, xmm0
0x18014039e  xor     eax, eax
0x1801403a0  movups  xmmword ptr [rbp+3F0h+pvar], xmm0
0x1801403a4  mov     [rbp+3F0h+var_450], rax
0x1801403a8  mov     rcx, [rsp+4F0h+var_478]
0x1801403ad  mov     rax, [rcx]
0x1801403b0  lea     r8, [rbp+3F0h+pvar]
0x1801403b4  lea     rdx, DEVPKEY_Device_Driver
0x1801403bb  mov     rax, [rax+28h]
0x1801403bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801403c4  mov     ebx, eax
0x1801403c6  test    eax, eax
0x1801403c8  jns     short loc_1801403D6
0x1801403ca  lea     rcx, [rbp+3F0h+pvar]; pvar
0x1801403ce  call    cs:__imp_PropVariantClear
0x1801403d4  jmp     short loc_18014038F
0x1801403d6  cmp     word ptr [rbp+3F0h+pvar], 1Fh
0x1801403db  jnz     loc_180140485
0x1801403e1  mov     r10d, 208h
0x1801403e7  mov     [rbp+3F0h+var_468], r10d
0x1801403eb  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Cla"...
0x1801403f2  mov     edx, r10d; unsigned __int64
0x1801403f5  lea     rcx, [rbp+3F0h+SubKey]; unsigned __int16 *
0x1801403f9  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1801403fe  mov     ebx, eax
0x180140400  test    eax, eax
0x180140402  js      short loc_1801403CA
0x180140404  mov     r8, [rbp+3F0h+pvar+8]; unsigned __int16 *
0x180140408  mov     edx, r10d; unsigned __int64
0x18014040b  lea     rcx, [rbp+3F0h+SubKey]; unsigned __int16 *
0x18014040f  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180140414  mov     ebx, eax
0x180140416  test    eax, eax
0x180140418  js      short loc_1801403CA
0x18014041a  lea     rax, [rbp+3F0h+var_468]
0x18014041e  mov     [rsp+4F0h+pcbData], rax; pcbData
0x180140423  lea     rax, [rbp+3F0h+String1]
0x18014042a  mov     [rsp+4F0h+pvData], rax; pvData
0x18014042f  mov     [rsp+4F0h+ppv], r14; pdwType
0x180140434  mov     r9d, 2; dwFlags
0x18014043a  lea     r8, aDriver; "Driver"
0x180140441  lea     rdx, [rbp+3F0h+SubKey]; lpSubKey
0x180140445  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18014044c  call    cs:__imp_RegGetValueW
0x180140452  test    eax, eax
0x180140454  jnz     short loc_180140485
0x180140456  mov     dword ptr [rsp+4F0h+ppv], 1; bIgnoreCase
0x18014045e  lea     r9d, [rax+9]; cchCount2
0x180140462  lea     r8, aSmwdmSys; "smwdm.sys"
0x180140469  or      edx, 0FFFFFFFFh; cchCount1
0x18014046c  lea     rcx, [rbp+3F0h+String1]; lpString1
0x180140473  call    cs:__imp_CompareStringOrdinal
0x180140479  cmp     eax, 2
0x18014047c  setz    cl
0x18014047f  mov     rax, [rsi+8]
0x180140483  mov     [rax], cl
0x180140485  lea     rcx, [rbp+3F0h+pvar]; pvar
0x180140489  call    cs:__imp_PropVariantClear
0x18014048f  nop
0x180140490  lea     rcx, [rsp+4F0h+var_478]
0x180140495  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18014049a  nop
0x18014049b  lea     rcx, [rsp+4F0h+var_480]
0x1801404a0  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1801404a5  nop
0x1801404a6  lea     rcx, [rsp+4F0h+var_490]
0x1801404ab  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1801404b0  nop
0x1801404b1  lea     rcx, [rsp+4F0h+var_488]
0x1801404b6  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1801404bb  nop
0x1801404bc  lea     rcx, [rsp+4F0h+var_4A0]
0x1801404c1  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1801404c6  nop
0x1801404c7  lea     rcx, [rsp+4F0h+var_498]
0x1801404cc  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1801404d1  nop
0x1801404d2  lea     rcx, [rsp+4F0h+var_4A8]
0x1801404d7  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1801404dc  nop
0x1801404dd  lea     rcx, [rsp+4F0h+var_4B0]
0x1801404e2  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1801404e7  mov     ebx, r14d
0x1801404ea  lea     rcx, [rbp+3F0h+var_470]
0x1801404ee  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1801404f3  mov     eax, ebx
0x1801404f5  mov     rcx, [rbp+3F0h+var_20]
0x1801404fc  xor     rcx, rsp; StackCookie
0x1801404ff  call    __security_check_cookie
0x180140504  lea     r11, [rsp+4F0h+var_10]
0x18014050c  mov     rbx, [r11+28h]
0x180140510  mov     rsi, [r11+30h]
0x180140514  mov     rsp, r11
0x180140517  pop     r14
0x180140519  pop     rdi
0x18014051a  pop     rbp
0x18014051b  retn
```
