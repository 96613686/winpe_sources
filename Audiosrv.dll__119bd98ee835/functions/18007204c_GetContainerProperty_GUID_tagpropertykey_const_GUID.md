# GetContainerProperty(_GUID,_tagpropertykey const &,_GUID *)

- ea: `0x18007204c`
- end: `0x1800722b1`
- name: `?GetContainerProperty@@YAJU_GUID@@AEBU_tagpropertykey@@PEAU1@@Z`
- size: `613`
- prototype: `__int64 __fastcall(IID *rclsid, const struct _tagpropertykey *, struct _GUID *)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a6b34`
- `0x180109b3c`
- `0x18011ce7c`

## callees

- `0x18000ae1c`
- `0x18000cba0`
- `0x18000e284`
- `0x18001280c`
- `0x18007204c`
- `0x1800befa8`
- `0x1800cd8d0`
- `0x1800ce898`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180072154`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180072154`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180072226`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180072265`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180072226`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180072265`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18007224d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18007224d`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18007209a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18007209a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800720d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800720d0`
- `MMDevAPI!__imp_MMDeviceCreateRegistryPropertyStore` at `0x1800721a3`
- `MMDevAPI!__imp_MMDeviceCreateRegistryPropertyStore` at `0x1800721a3`

## string_xrefs

- `0x1800720b0`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180072116`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x18007216a`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800721b9`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180072214`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`

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
0x18007204c  mov     [rsp-8+arg_18], rbx
0x180072051  push    rbp
0x180072052  push    rsi
0x180072053  push    rdi
0x180072054  lea     rbp, [rsp-180h]
0x18007205c  sub     rsp, 280h
0x180072063  mov     rax, cs:__security_cookie
0x18007206a  xor     rax, rsp
0x18007206d  mov     [rbp+190h+var_20], rax
0x180072074  mov     rdi, r8
0x180072077  mov     rsi, rdx
0x18007207a  mov     rbx, rcx
0x18007207d  mov     [rsp+290h+lpsz], 0
0x180072086  xor     edx, edx
0x180072088  lea     rcx, [rsp+290h+lpsz]
0x18007208d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180072092  lea     rdx, [rsp+290h+lpsz]; lplpsz
0x180072097  mov     rcx, rbx; rclsid
0x18007209a  call    cs:__imp_StringFromCLSID
0x1800720a0  mov     ebx, eax
0x1800720a2  test    eax, eax
0x1800720a4  jns     short loc_1800720DB
0x1800720a6  mov     rcx, [rbp+198h]; this
0x1800720ad  mov     r9d, eax; char *
0x1800720b0  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800720b7  mov     edx, 0BFh; void *
0x1800720bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800720c1  nop
0x1800720c2  mov     rcx, [rsp+290h+lpsz]; pv
0x1800720c7  test    rcx, rcx
0x1800720ca  jz      loc_18007228D
0x1800720d0  call    cs:__imp_CoTaskMemFree
0x1800720d6  jmp     loc_18007228D
0x1800720db  mov     rax, [rsp+290h+lpsz]
0x1800720e0  mov     qword ptr [rsp+290h+phkResult], rax; int
0x1800720e5  lea     r9, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800720ec  lea     r8, aSS_0; "%s\\%s"
0x1800720f3  mov     edx, 104h; BufferCount
0x1800720f8  lea     rcx, [rsp+290h+Buffer]; Buffer
0x1800720fd  call    swprintf_s
0x180072102  cmp     eax, 0FFFFFFFFh
0x180072105  jnz     short loc_18007212C
0x180072107  mov     rcx, [rbp+198h]; this
0x18007210e  mov     ebx, 8007007Ah
0x180072113  mov     r9d, ebx; char *
0x180072116  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18007211d  mov     edx, 0C2h; void *
0x180072122  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072127  jmp     loc_180072283
0x18007212c  mov     [rsp+290h+var_258], 0
0x180072135  lea     rax, [rsp+290h+var_258]
0x18007213a  mov     qword ptr [rsp+290h+phkResult], rax; int
0x18007213f  mov     r9d, 20019h; samDesired
0x180072145  xor     r8d, r8d; ulOptions
0x180072148  lea     rdx, [rsp+290h+Buffer]; lpSubKey
0x18007214d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180072154  call    cs:__imp_RegOpenKeyExW
0x18007215a  mov     ebx, eax
0x18007215c  test    eax, eax
0x18007215e  jns     short loc_18007218B
0x180072160  mov     rcx, [rbp+198h]; this
0x180072167  mov     r9d, eax; char *
0x18007216a  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180072171  mov     edx, 0C5h; void *
0x180072176  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007217b  nop
0x18007217c  lea     rcx, [rsp+290h+var_258]
0x180072181  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180072186  jmp     loc_180072283
0x18007218b  mov     [rsp+290h+var_260], 0
0x180072194  lea     r8, [rsp+290h+var_260]
0x180072199  mov     edx, 101h
0x18007219e  lea     rcx, [rsp+290h+Buffer]
0x1800721a3  call    cs:__imp_MMDeviceCreateRegistryPropertyStore
0x1800721a9  mov     ebx, eax
0x1800721ab  test    eax, eax
0x1800721ad  jns     short loc_1800721D7
0x1800721af  mov     rcx, [rbp+198h]; this
0x1800721b6  mov     r9d, eax; char *
0x1800721b9  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800721c0  mov     edx, 0C8h; void *
0x1800721c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800721ca  nop
0x1800721cb  lea     rcx, [rsp+290h+var_260]
0x1800721d0  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800721d5  jmp     short loc_18007217C
0x1800721d7  xorps   xmm0, xmm0
0x1800721da  xor     eax, eax
0x1800721dc  movups  xmmword ptr [rsp+290h+pvar], xmm0
0x1800721e1  mov     [rsp+290h+var_238], rax
0x1800721e6  mov     rcx, [rsp+290h+var_260]
0x1800721eb  mov     rax, [rcx]
0x1800721ee  lea     r8, [rsp+290h+pvar]
0x1800721f3  mov     rdx, rsi
0x1800721f6  mov     rax, [rax+28h]
0x1800721fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800721ff  mov     ebx, eax
0x180072201  test    eax, eax
0x180072203  jns     short loc_18007222E
0x180072205  mov     edx, 0CBh; void *
0x18007220a  mov     r9d, eax; char *
0x18007220d  mov     rcx, [rbp+198h]; this
0x180072214  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18007221b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072220  nop
0x180072221  lea     rcx, [rsp+290h+pvar]; pvar
0x180072226  call    cs:__imp_PropVariantClear
0x18007222c  jmp     short loc_1800721CB
0x18007222e  cmp     word ptr [rsp+290h+pvar], 1Fh
0x180072234  jz      short loc_180072245
0x180072236  mov     ebx, 80070057h
0x18007223b  mov     r9d, ebx
0x18007223e  mov     edx, 0CDh
0x180072243  jmp     short loc_18007220D
0x180072245  mov     rdx, rdi; pclsid
0x180072248  mov     rcx, [rsp+290h+pvar+8]; lpsz
0x18007224d  call    cs:__imp_CLSIDFromString
0x180072253  mov     ebx, eax
0x180072255  test    eax, eax
0x180072257  jns     short loc_180072260
0x180072259  mov     edx, 0CFh
0x18007225e  jmp     short loc_18007220A
0x180072260  lea     rcx, [rsp+290h+pvar]; pvar
0x180072265  call    cs:__imp_PropVariantClear
0x18007226b  nop
0x18007226c  lea     rcx, [rsp+290h+var_260]
0x180072271  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180072276  nop
0x180072277  lea     rcx, [rsp+290h+var_258]
0x18007227c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180072281  xor     ebx, ebx
0x180072283  lea     rcx, [rsp+290h+lpsz]
0x180072288  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18007228d  mov     eax, ebx
0x18007228f  mov     rcx, [rbp+190h+var_20]
0x180072296  xor     rcx, rsp; StackCookie
0x180072299  call    __security_check_cookie
0x18007229e  mov     rbx, [rsp+290h+arg_18]
0x1800722a6  add     rsp, 280h
0x1800722ad  pop     rdi
0x1800722ae  pop     rsi
0x1800722af  pop     rbp
0x1800722b0  retn
```
