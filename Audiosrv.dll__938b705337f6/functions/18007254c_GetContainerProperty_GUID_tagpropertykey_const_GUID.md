# GetContainerProperty(_GUID,_tagpropertykey const &,_GUID *)

- ea: `0x18007254c`
- end: `0x1800727b1`
- name: `?GetContainerProperty@@YAJU_GUID@@AEBU_tagpropertykey@@PEAU1@@Z`
- size: `613`
- prototype: `__int64 __fastcall(IID *rclsid, const struct _tagpropertykey *, struct _GUID *)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a7de4`
- `0x1801098dc`
- `0x18011cc2c`

## callees

- `0x18000accc`
- `0x18000ca50`
- `0x18000e134`
- `0x1800126bc`
- `0x18007254c`
- `0x1800c0af8`
- `0x1800cf8c0`
- `0x1800d0888`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180072654`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180072654`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180072726`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180072765`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180072726`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180072765`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18007274d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18007274d`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18007259a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18007259a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800725d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800725d0`
- `MMDevAPI!__imp_MMDeviceCreateRegistryPropertyStore` at `0x1800726a3`
- `MMDevAPI!__imp_MMDeviceCreateRegistryPropertyStore` at `0x1800726a3`

## string_xrefs

- `0x1800725b0`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180072616`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x18007266a`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800726b9`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180072714`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetContainerProperty(IID *rclsid, const struct _tagpropertykey *a2, struct _GUID *a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  LSTATUS v8; // eax
  int v9; // eax
  HRESULT v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r9
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v18; // [rsp+38h] [rbp-C8h] BYREF
  LPOLESTR lpsz; // [rsp+40h] [rbp-C0h] BYREF
  PROPVARIANT pvar[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v21; // [rsp+58h] [rbp-A8h]
  wchar_t Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  lpsz = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpsz,
    0);
  v6 = StringFromCLSID(rclsid, &lpsz);
  v7 = v6;
  if ( v6 >= 0 )
  {
    phkResulta = (int)lpsz;
    if ( swprintf_s(Buffer, 0x104u, L"%s\\%s", L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio\\Containers\\") == -1 )
    {
      v7 = -2147024774;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC2,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)0x8007007ALL,
        phkResulta);
LABEL_21:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpsz);
      return v7;
    }
    v18 = 0;
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, Buffer, 0, 0x20019u, &v18);
    v7 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC5,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)(unsigned int)v8,
        phkResultb);
LABEL_8:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v18);
      goto LABEL_21;
    }
    v17 = 0;
    v9 = MMDeviceCreateRegistryPropertyStore(Buffer, 257, &v17);
    v7 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC8,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)(unsigned int)v9,
        phkResultb);
LABEL_11:
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v17);
      goto LABEL_8;
    }
    *(_OWORD *)pvar = 0;
    v21 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, const struct _tagpropertykey *, PROPVARIANT *))(*(_QWORD *)v17 + 40LL))(
            v17,
            a2,
            pvar);
    v7 = v10;
    if ( v10 >= 0 )
    {
      if ( LOWORD(pvar[0]) != 31 )
      {
        v7 = -2147024809;
        v12 = 2147942487LL;
        v11 = 205;
        goto LABEL_15;
      }
      v10 = CLSIDFromString((LPCOLESTR)pvar[1], a3);
      v7 = v10;
      if ( v10 >= 0 )
      {
        PropVariantClear(pvar);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v17);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v18);
        v7 = 0;
        goto LABEL_21;
      }
      v11 = 207;
    }
    else
    {
      v11 = 203;
    }
    v12 = (unsigned int)v10;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)v12,
      phkResultb);
    PropVariantClear(pvar);
    goto LABEL_11;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xBF,
    (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
    (const char *)(unsigned int)v6,
    phkResult);
  if ( lpsz )
    CoTaskMemFree(lpsz);
  return v7;
}

```

## disassembly

```asm
0x18007254c  mov     [rsp-8+arg_18], rbx
0x180072551  push    rbp
0x180072552  push    rsi
0x180072553  push    rdi
0x180072554  lea     rbp, [rsp-180h]
0x18007255c  sub     rsp, 280h
0x180072563  mov     rax, cs:__security_cookie
0x18007256a  xor     rax, rsp
0x18007256d  mov     [rbp+190h+var_20], rax
0x180072574  mov     rdi, r8
0x180072577  mov     rsi, rdx
0x18007257a  mov     rbx, rcx
0x18007257d  mov     [rsp+290h+lpsz], 0
0x180072586  xor     edx, edx
0x180072588  lea     rcx, [rsp+290h+lpsz]
0x18007258d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180072592  lea     rdx, [rsp+290h+lpsz]; lplpsz
0x180072597  mov     rcx, rbx; rclsid
0x18007259a  call    cs:__imp_StringFromCLSID
0x1800725a0  mov     ebx, eax
0x1800725a2  test    eax, eax
0x1800725a4  jns     short loc_1800725DB
0x1800725a6  mov     rcx, [rbp+198h]; this
0x1800725ad  mov     r9d, eax; char *
0x1800725b0  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800725b7  mov     edx, 0BFh; void *
0x1800725bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800725c1  nop
0x1800725c2  mov     rcx, [rsp+290h+lpsz]; pv
0x1800725c7  test    rcx, rcx
0x1800725ca  jz      loc_18007278D
0x1800725d0  call    cs:__imp_CoTaskMemFree
0x1800725d6  jmp     loc_18007278D
0x1800725db  mov     rax, [rsp+290h+lpsz]
0x1800725e0  mov     qword ptr [rsp+290h+phkResult], rax; int
0x1800725e5  lea     r9, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800725ec  lea     r8, aSS_0; "%s\\%s"
0x1800725f3  mov     edx, 104h; BufferCount
0x1800725f8  lea     rcx, [rsp+290h+Buffer]; Buffer
0x1800725fd  call    swprintf_s
0x180072602  cmp     eax, 0FFFFFFFFh
0x180072605  jnz     short loc_18007262C
0x180072607  mov     rcx, [rbp+198h]; this
0x18007260e  mov     ebx, 8007007Ah
0x180072613  mov     r9d, ebx; char *
0x180072616  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18007261d  mov     edx, 0C2h; void *
0x180072622  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072627  jmp     loc_180072783
0x18007262c  mov     [rsp+290h+var_258], 0
0x180072635  lea     rax, [rsp+290h+var_258]
0x18007263a  mov     qword ptr [rsp+290h+phkResult], rax; int
0x18007263f  mov     r9d, 20019h; samDesired
0x180072645  xor     r8d, r8d; ulOptions
0x180072648  lea     rdx, [rsp+290h+Buffer]; lpSubKey
0x18007264d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180072654  call    cs:__imp_RegOpenKeyExW
0x18007265a  mov     ebx, eax
0x18007265c  test    eax, eax
0x18007265e  jns     short loc_18007268B
0x180072660  mov     rcx, [rbp+198h]; this
0x180072667  mov     r9d, eax; char *
0x18007266a  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180072671  mov     edx, 0C5h; void *
0x180072676  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007267b  nop
0x18007267c  lea     rcx, [rsp+290h+var_258]
0x180072681  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180072686  jmp     loc_180072783
0x18007268b  mov     [rsp+290h+var_260], 0
0x180072694  lea     r8, [rsp+290h+var_260]
0x180072699  mov     edx, 101h
0x18007269e  lea     rcx, [rsp+290h+Buffer]
0x1800726a3  call    cs:__imp_MMDeviceCreateRegistryPropertyStore
0x1800726a9  mov     ebx, eax
0x1800726ab  test    eax, eax
0x1800726ad  jns     short loc_1800726D7
0x1800726af  mov     rcx, [rbp+198h]; this
0x1800726b6  mov     r9d, eax; char *
0x1800726b9  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800726c0  mov     edx, 0C8h; void *
0x1800726c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800726ca  nop
0x1800726cb  lea     rcx, [rsp+290h+var_260]
0x1800726d0  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800726d5  jmp     short loc_18007267C
0x1800726d7  xorps   xmm0, xmm0
0x1800726da  xor     eax, eax
0x1800726dc  movups  xmmword ptr [rsp+290h+pvar], xmm0
0x1800726e1  mov     [rsp+290h+var_238], rax
0x1800726e6  mov     rcx, [rsp+290h+var_260]
0x1800726eb  mov     rax, [rcx]
0x1800726ee  lea     r8, [rsp+290h+pvar]
0x1800726f3  mov     rdx, rsi
0x1800726f6  mov     rax, [rax+28h]
0x1800726fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800726ff  mov     ebx, eax
0x180072701  test    eax, eax
0x180072703  jns     short loc_18007272E
0x180072705  mov     edx, 0CBh; void *
0x18007270a  mov     r9d, eax; char *
0x18007270d  mov     rcx, [rbp+198h]; this
0x180072714  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18007271b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072720  nop
0x180072721  lea     rcx, [rsp+290h+pvar]; pvar
0x180072726  call    cs:__imp_PropVariantClear
0x18007272c  jmp     short loc_1800726CB
0x18007272e  cmp     word ptr [rsp+290h+pvar], 1Fh
0x180072734  jz      short loc_180072745
0x180072736  mov     ebx, 80070057h
0x18007273b  mov     r9d, ebx
0x18007273e  mov     edx, 0CDh
0x180072743  jmp     short loc_18007270D
0x180072745  mov     rdx, rdi; pclsid
0x180072748  mov     rcx, [rsp+290h+pvar+8]; lpsz
0x18007274d  call    cs:__imp_CLSIDFromString
0x180072753  mov     ebx, eax
0x180072755  test    eax, eax
0x180072757  jns     short loc_180072760
0x180072759  mov     edx, 0CFh
0x18007275e  jmp     short loc_18007270A
0x180072760  lea     rcx, [rsp+290h+pvar]; pvar
0x180072765  call    cs:__imp_PropVariantClear
0x18007276b  nop
0x18007276c  lea     rcx, [rsp+290h+var_260]
0x180072771  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180072776  nop
0x180072777  lea     rcx, [rsp+290h+var_258]
0x18007277c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180072781  xor     ebx, ebx
0x180072783  lea     rcx, [rsp+290h+lpsz]
0x180072788  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18007278d  mov     eax, ebx
0x18007278f  mov     rcx, [rbp+190h+var_20]
0x180072796  xor     rcx, rsp; StackCookie
0x180072799  call    __security_check_cookie
0x18007279e  mov     rbx, [rsp+290h+arg_18]
0x1800727a6  add     rsp, 280h
0x1800727ad  pop     rdi
0x1800727ae  pop     rsi
0x1800727af  pop     rbp
0x1800727b0  retn
```
