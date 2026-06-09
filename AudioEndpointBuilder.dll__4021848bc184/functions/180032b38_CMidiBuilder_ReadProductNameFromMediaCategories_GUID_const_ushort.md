# CMidiBuilder::ReadProductNameFromMediaCategories(_GUID const &,ushort * *)

- ea: `0x180032b38`
- end: `0x180032d93`
- name: `?ReadProductNameFromMediaCategories@CMidiBuilder@@AEAAJAEBU_GUID@@PEAPEAG@Z`
- size: `603`
- prototype: `int(CMidiBuilder *__hidden this, const struct _GUID *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003ce28`

## callees

- `0x180009650`
- `0x18000fb60`
- `0x180010da8`
- `0x180018db0`
- `0x180032b38`
- `0x180033464`
- `0x18003e920`
- `0x180052f9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032c64`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032d1c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032c64`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032d1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032c99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032c99`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180032b99`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180032b99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032bc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032ccb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032d43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032d53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032d6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032bc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032ccb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032d43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032d53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032d6a`

## string_xrefs

- `0x180032bae`: `avcore\audiocore\server\audioendpointbuilder\dll\midibuilder.cpp`
- `0x180032c72`: `avcore\audiocore\server\audioendpointbuilder\dll\midibuilder.cpp`
- `0x180032d2a`: `avcore\audiocore\server\audioendpointbuilder\dll\midibuilder.cpp`

## pseudocode

```c
__int64 __fastcall CMidiBuilder::ReadProductNameFromMediaCategories(
        CMidiBuilder *this,
        const struct _GUID *a2,
        unsigned __int16 **a3)
{
  HRESULT v5; // ebx
  __int64 v6; // rdx
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // r9
  unsigned int ValueW; // eax
  __int64 v11; // rbx
  _WORD *v12; // rax
  PVOID v13; // rbx
  unsigned int v14; // eax
  unsigned int v15; // edi
  LPOLESTR v16; // rcx
  unsigned int cchToCopy; // [rsp+20h] [rbp-E0h]
  unsigned int cchToCopya; // [rsp+20h] [rbp-E0h]
  LPOLESTR lpsz; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pdwType; // [rsp+4Ch] [rbp-B4h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  PVOID pvData; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t pszDest[96]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  lpsz = 0;
  pcbData = 0;
  pdwType = 0;
  pvData = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpsz,
    0);
  v5 = StringFromCLSID(a2, &lpsz);
  if ( v5 < 0 )
  {
    v6 = 645;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\midibuilder.cpp",
      (const char *)(unsigned int)v5,
      cchToCopy);
LABEL_4:
    if ( lpsz )
      CoTaskMemFree(lpsz);
    return (unsigned int)v5;
  }
  v5 = StringCopyWorkerW(pszDest, 0x59u, 0, L"SYSTEM\\CurrentControlSet\\Control\\MediaCategories\\", 0x32u);
  if ( v5 < 0 )
  {
    v6 = 648;
    goto LABEL_3;
  }
  v5 = StringCchCatNW(pszDest, v8, lpsz, v9);
  if ( v5 < 0 )
  {
    v6 = 651;
    goto LABEL_3;
  }
  pcbData = 0;
  pdwType = 0;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, pszDest, L"Name", 2u, &pdwType, 0, &pcbData);
  if ( ValueW )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x297,
           (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\midibuilder.cpp",
           (const char *)ValueW,
           cchToCopy);
    goto LABEL_4;
  }
  v11 = pcbData;
  v12 = CoTaskMemAlloc(2LL * pcbData + 2);
  if ( v12 )
  {
    *v12 = 0;
    v12[v11] = 0;
  }
  pv = v12;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &pvData,
    &pv);
  if ( pv )
    CoTaskMemFree(pv);
  v13 = pvData;
  if ( !pvData )
  {
    v5 = -2147024882;
    v6 = 667;
    goto LABEL_3;
  }
  v14 = RegGetValueW(HKEY_LOCAL_MACHINE, pszDest, L"Name", 2u, &pdwType, pvData, &pcbData);
  if ( v14 )
  {
    v15 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x2A5,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\midibuilder.cpp",
            (const char *)v14,
            cchToCopya);
    CoTaskMemFree(v13);
    if ( lpsz )
      CoTaskMemFree(lpsz);
    return v15;
  }
  else
  {
    v16 = lpsz;
    *a3 = (unsigned __int16 *)v13;
    if ( v16 )
      CoTaskMemFree(v16);
    return 0;
  }
}

```

## disassembly

```asm
0x180032b38  mov     [rsp-8+arg_0], rbx
0x180032b3d  mov     [rsp-8+arg_18], rdi
0x180032b42  push    rbp
0x180032b43  lea     rbp, [rsp-30h]
0x180032b48  sub     rsp, 130h
0x180032b4f  mov     rax, cs:__security_cookie
0x180032b56  xor     rax, rsp
0x180032b59  mov     [rbp+30h+var_10], rax
0x180032b5d  mov     rbx, rdx
0x180032b60  mov     [rsp+130h+lpsz], 0
0x180032b69  xor     edx, edx
0x180032b6b  mov     [rsp+130h+var_E8], 0
0x180032b73  lea     rcx, [rsp+130h+lpsz]
0x180032b78  mov     [rsp+130h+pdwType], 0
0x180032b80  mov     rdi, r8
0x180032b83  mov     [rsp+130h+var_D8], 0
0x180032b8c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180032b91  lea     rdx, [rsp+130h+lpsz]; lplpsz
0x180032b96  mov     rcx, rbx; rclsid
0x180032b99  call    cs:__imp_StringFromCLSID
0x180032b9f  mov     ebx, eax
0x180032ba1  test    eax, eax
0x180032ba3  jns     short loc_180032BD4
0x180032ba5  mov     edx, 285h; void *
0x180032baa  mov     rcx, [rbp+38h]; this
0x180032bae  lea     r8, aAvcoreAudiocor_16; "avcore\\audiocore\\server\\audioendpoin"...
0x180032bb5  mov     r9d, ebx; char *
0x180032bb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032bbd  mov     rcx, [rsp+130h+lpsz]; pv
0x180032bc2  test    rcx, rcx
0x180032bc5  jz      short loc_180032BCD
0x180032bc7  call    cs:__imp_CoTaskMemFree
0x180032bcd  mov     eax, ebx
0x180032bcf  jmp     loc_180032D72
0x180032bd4  xor     r8d, r8d; pcchNewDestLength
0x180032bd7  mov     [rsp+130h+cchToCopy], 32h ; '2'; cchToCopy
0x180032be0  lea     r9, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Med"...
0x180032be7  lea     rcx, [rsp+130h+pszDest]; pszDest
0x180032bec  lea     edx, [r8+59h]; cchDest
0x180032bf0  call    StringCopyWorkerW
0x180032bf5  mov     ebx, eax
0x180032bf7  test    eax, eax
0x180032bf9  jns     short loc_180032C02
0x180032bfb  mov     edx, 288h
0x180032c00  jmp     short loc_180032BAA
0x180032c02  mov     r8, [rsp+130h+lpsz]; unsigned __int16 *
0x180032c07  lea     rcx, [rsp+130h+pszDest]; unsigned __int16 *
0x180032c0c  call    ?StringCchCatNW@@YAJPEAG_KPEBG1@Z; StringCchCatNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180032c11  mov     ebx, eax
0x180032c13  test    eax, eax
0x180032c15  jns     short loc_180032C1E
0x180032c17  mov     edx, 28Bh
0x180032c1c  jmp     short loc_180032BAA
0x180032c1e  lea     rax, [rsp+130h+var_E8]
0x180032c23  mov     [rsp+130h+var_E8], 0
0x180032c2b  mov     [rsp+130h+pcbData], rax; pcbData
0x180032c30  lea     r8, aName_0; "Name"
0x180032c37  lea     rax, [rsp+130h+pdwType]
0x180032c3c  mov     [rsp+130h+pvData], 0; pvData
0x180032c45  mov     r9d, 2; dwFlags
0x180032c4b  mov     [rsp+130h+cchToCopy], rax; unsigned int
0x180032c50  lea     rdx, [rsp+130h+pszDest]; lpSubKey
0x180032c55  mov     [rsp+130h+pdwType], 0
0x180032c5d  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180032c64  call    cs:__imp_RegGetValueW
0x180032c6a  test    eax, eax
0x180032c6c  jz      short loc_180032C8D
0x180032c6e  mov     rcx, [rbp+38h]; this
0x180032c72  lea     r8, aAvcoreAudiocor_16; "avcore\\audiocore\\server\\audioendpoin"...
0x180032c79  mov     r9d, eax; char *
0x180032c7c  mov     edx, 297h; void *
0x180032c81  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180032c86  mov     ebx, eax
0x180032c88  jmp     loc_180032BBD
0x180032c8d  mov     ebx, [rsp+130h+var_E8]
0x180032c91  lea     rcx, ds:2[rbx*2]; cb
0x180032c99  call    cs:__imp_CoTaskMemAlloc
0x180032c9f  test    rax, rax
0x180032ca2  jz      short loc_180032CAD
0x180032ca4  xor     ecx, ecx
0x180032ca6  mov     [rax], cx
0x180032ca9  mov     [rax+rbx*2], cx
0x180032cad  lea     rdx, [rsp+130h+pv]
0x180032cb2  mov     [rsp+130h+pv], rax
0x180032cb7  lea     rcx, [rsp+130h+var_D8]
0x180032cbc  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180032cc1  mov     rcx, [rsp+130h+pv]; pv
0x180032cc6  test    rcx, rcx
0x180032cc9  jz      short loc_180032CD1
0x180032ccb  call    cs:__imp_CoTaskMemFree
0x180032cd1  mov     rbx, [rsp+130h+var_D8]
0x180032cd6  test    rbx, rbx
0x180032cd9  jnz     short loc_180032CEA
0x180032cdb  mov     ebx, 8007000Eh
0x180032ce0  mov     edx, 29Bh
0x180032ce5  jmp     loc_180032BAA
0x180032cea  lea     rax, [rsp+130h+var_E8]
0x180032cef  mov     r9d, 2; dwFlags
0x180032cf5  mov     [rsp+130h+pcbData], rax; pcbData
0x180032cfa  lea     r8, aName_0; "Name"
0x180032d01  lea     rax, [rsp+130h+pdwType]
0x180032d06  mov     [rsp+130h+pvData], rbx; pvData
0x180032d0b  lea     rdx, [rsp+130h+pszDest]; lpSubKey
0x180032d10  mov     [rsp+130h+cchToCopy], rax; unsigned int
0x180032d15  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180032d1c  call    cs:__imp_RegGetValueW
0x180032d22  test    eax, eax
0x180032d24  jz      short loc_180032D5D
0x180032d26  mov     rcx, [rbp+38h]; this
0x180032d2a  lea     r8, aAvcoreAudiocor_16; "avcore\\audiocore\\server\\audioendpoin"...
0x180032d31  mov     r9d, eax; char *
0x180032d34  mov     edx, 2A5h; void *
0x180032d39  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180032d3e  mov     rcx, rbx; pv
0x180032d41  mov     edi, eax
0x180032d43  call    cs:__imp_CoTaskMemFree
0x180032d49  mov     rcx, [rsp+130h+lpsz]; pv
0x180032d4e  test    rcx, rcx
0x180032d51  jz      short loc_180032D59
0x180032d53  call    cs:__imp_CoTaskMemFree
0x180032d59  mov     eax, edi
0x180032d5b  jmp     short loc_180032D72
0x180032d5d  mov     rcx, [rsp+130h+lpsz]; pv
0x180032d62  mov     [rdi], rbx
0x180032d65  test    rcx, rcx
0x180032d68  jz      short loc_180032D70
0x180032d6a  call    cs:__imp_CoTaskMemFree
0x180032d70  xor     eax, eax
0x180032d72  mov     rcx, [rbp+30h+var_10]
0x180032d76  xor     rcx, rsp; StackCookie
0x180032d79  call    __security_check_cookie
0x180032d7e  lea     r11, [rsp+130h+var_s0]
0x180032d86  mov     rbx, [r11+10h]
0x180032d8a  mov     rdi, [r11+28h]
0x180032d8e  mov     rsp, r11
0x180032d91  pop     rbp
0x180032d92  retn
```
