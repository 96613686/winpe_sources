# ReadProductNameFromMediaCategories(_GUID const &,ushort * *)

- ea: `0x1800328d4`
- end: `0x180032b2f`
- name: `?ReadProductNameFromMediaCategories@@YAJAEBU_GUID@@PEAPEAG@Z`
- size: `603`
- prototype: `__int64 __fastcall(IID *rclsid, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800381a8`

## callees

- `0x180009650`
- `0x18000fb60`
- `0x180010da8`
- `0x180018db0`
- `0x1800328d4`
- `0x180033464`
- `0x18003e920`
- `0x180052f9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032a00`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032ab8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032a00`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032ab8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032a35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032a35`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180032935`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180032935`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032963`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032a67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032adf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032aef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032b06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032963`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032a67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032adf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032aef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032b06`

## string_xrefs

- `0x18003294a`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180032a0e`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180032ac6`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
__int64 __fastcall ReadProductNameFromMediaCategories(IID *rclsid, unsigned __int16 **a2)
{
  HRESULT v4; // ebx
  __int64 v5; // rdx
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // r9
  unsigned int ValueW; // eax
  __int64 v10; // rbx
  _WORD *v11; // rax
  PVOID v12; // rbx
  unsigned int v13; // eax
  unsigned int v14; // edi
  LPOLESTR v15; // rcx
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
  v4 = StringFromCLSID(rclsid, &lpsz);
  if ( v4 < 0 )
  {
    v5 = 4824;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v4,
      cchToCopy);
LABEL_4:
    if ( lpsz )
      CoTaskMemFree(lpsz);
    return (unsigned int)v4;
  }
  v4 = StringCopyWorkerW(pszDest, 0x59u, 0, L"SYSTEM\\CurrentControlSet\\Control\\MediaCategories\\", 0x32u);
  if ( v4 < 0 )
  {
    v5 = 4827;
    goto LABEL_3;
  }
  v4 = StringCchCatNW(pszDest, v7, lpsz, v8);
  if ( v4 < 0 )
  {
    v5 = 4830;
    goto LABEL_3;
  }
  pcbData = 0;
  pdwType = 0;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, pszDest, L"Name", 2u, &pdwType, 0, &pcbData);
  if ( ValueW )
  {
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x12EA,
           (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
           (const char *)ValueW,
           cchToCopy);
    goto LABEL_4;
  }
  v10 = pcbData;
  v11 = CoTaskMemAlloc(2LL * pcbData + 2);
  if ( v11 )
  {
    *v11 = 0;
    v11[v10] = 0;
  }
  pv = v11;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &pvData,
    &pv);
  if ( pv )
    CoTaskMemFree(pv);
  v12 = pvData;
  if ( !pvData )
  {
    v4 = -2147024882;
    v5 = 4846;
    goto LABEL_3;
  }
  v13 = RegGetValueW(HKEY_LOCAL_MACHINE, pszDest, L"Name", 2u, &pdwType, pvData, &pcbData);
  if ( v13 )
  {
    v14 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x12F8,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
            (const char *)v13,
            cchToCopya);
    CoTaskMemFree(v12);
    if ( lpsz )
      CoTaskMemFree(lpsz);
    return v14;
  }
  else
  {
    v15 = lpsz;
    *a2 = (unsigned __int16 *)v12;
    if ( v15 )
      CoTaskMemFree(v15);
    return 0;
  }
}

```

## disassembly

```asm
0x1800328d4  mov     [rsp-8+arg_10], rbx
0x1800328d9  mov     [rsp-8+arg_18], rdi
0x1800328de  push    rbp
0x1800328df  lea     rbp, [rsp-30h]
0x1800328e4  sub     rsp, 130h
0x1800328eb  mov     rax, cs:__security_cookie
0x1800328f2  xor     rax, rsp
0x1800328f5  mov     [rbp+30h+var_10], rax
0x1800328f9  mov     rdi, rdx
0x1800328fc  mov     [rsp+130h+lpsz], 0
0x180032905  mov     rbx, rcx
0x180032908  mov     [rsp+130h+var_E8], 0
0x180032910  xor     edx, edx
0x180032912  mov     [rsp+130h+pdwType], 0
0x18003291a  lea     rcx, [rsp+130h+lpsz]
0x18003291f  mov     [rsp+130h+var_D8], 0
0x180032928  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003292d  lea     rdx, [rsp+130h+lpsz]; lplpsz
0x180032932  mov     rcx, rbx; rclsid
0x180032935  call    cs:__imp_StringFromCLSID
0x18003293b  mov     ebx, eax
0x18003293d  test    eax, eax
0x18003293f  jns     short loc_180032970
0x180032941  mov     edx, 12D8h; void *
0x180032946  mov     rcx, [rbp+38h]; this
0x18003294a  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180032951  mov     r9d, ebx; char *
0x180032954  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032959  mov     rcx, [rsp+130h+lpsz]; pv
0x18003295e  test    rcx, rcx
0x180032961  jz      short loc_180032969
0x180032963  call    cs:__imp_CoTaskMemFree
0x180032969  mov     eax, ebx
0x18003296b  jmp     loc_180032B0E
0x180032970  xor     r8d, r8d; pcchNewDestLength
0x180032973  mov     [rsp+130h+cchToCopy], 32h ; '2'; cchToCopy
0x18003297c  lea     r9, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Med"...
0x180032983  lea     rcx, [rsp+130h+pszDest]; pszDest
0x180032988  lea     edx, [r8+59h]; cchDest
0x18003298c  call    StringCopyWorkerW
0x180032991  mov     ebx, eax
0x180032993  test    eax, eax
0x180032995  jns     short loc_18003299E
0x180032997  mov     edx, 12DBh
0x18003299c  jmp     short loc_180032946
0x18003299e  mov     r8, [rsp+130h+lpsz]; unsigned __int16 *
0x1800329a3  lea     rcx, [rsp+130h+pszDest]; unsigned __int16 *
0x1800329a8  call    ?StringCchCatNW@@YAJPEAG_KPEBG1@Z; StringCchCatNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800329ad  mov     ebx, eax
0x1800329af  test    eax, eax
0x1800329b1  jns     short loc_1800329BA
0x1800329b3  mov     edx, 12DEh
0x1800329b8  jmp     short loc_180032946
0x1800329ba  lea     rax, [rsp+130h+var_E8]
0x1800329bf  mov     [rsp+130h+var_E8], 0
0x1800329c7  mov     [rsp+130h+pcbData], rax; pcbData
0x1800329cc  lea     r8, aName; "Name"
0x1800329d3  lea     rax, [rsp+130h+pdwType]
0x1800329d8  mov     [rsp+130h+pvData], 0; pvData
0x1800329e1  mov     r9d, 2; dwFlags
0x1800329e7  mov     [rsp+130h+cchToCopy], rax; unsigned int
0x1800329ec  lea     rdx, [rsp+130h+pszDest]; lpSubKey
0x1800329f1  mov     [rsp+130h+pdwType], 0
0x1800329f9  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180032a00  call    cs:__imp_RegGetValueW
0x180032a06  test    eax, eax
0x180032a08  jz      short loc_180032A29
0x180032a0a  mov     rcx, [rbp+38h]; this
0x180032a0e  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180032a15  mov     r9d, eax; char *
0x180032a18  mov     edx, 12EAh; void *
0x180032a1d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180032a22  mov     ebx, eax
0x180032a24  jmp     loc_180032959
0x180032a29  mov     ebx, [rsp+130h+var_E8]
0x180032a2d  lea     rcx, ds:2[rbx*2]; cb
0x180032a35  call    cs:__imp_CoTaskMemAlloc
0x180032a3b  test    rax, rax
0x180032a3e  jz      short loc_180032A49
0x180032a40  xor     ecx, ecx
0x180032a42  mov     [rax], cx
0x180032a45  mov     [rax+rbx*2], cx
0x180032a49  lea     rdx, [rsp+130h+pv]
0x180032a4e  mov     [rsp+130h+pv], rax
0x180032a53  lea     rcx, [rsp+130h+var_D8]
0x180032a58  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180032a5d  mov     rcx, [rsp+130h+pv]; pv
0x180032a62  test    rcx, rcx
0x180032a65  jz      short loc_180032A6D
0x180032a67  call    cs:__imp_CoTaskMemFree
0x180032a6d  mov     rbx, [rsp+130h+var_D8]
0x180032a72  test    rbx, rbx
0x180032a75  jnz     short loc_180032A86
0x180032a77  mov     ebx, 8007000Eh
0x180032a7c  mov     edx, 12EEh
0x180032a81  jmp     loc_180032946
0x180032a86  lea     rax, [rsp+130h+var_E8]
0x180032a8b  mov     r9d, 2; dwFlags
0x180032a91  mov     [rsp+130h+pcbData], rax; pcbData
0x180032a96  lea     r8, aName; "Name"
0x180032a9d  lea     rax, [rsp+130h+pdwType]
0x180032aa2  mov     [rsp+130h+pvData], rbx; pvData
0x180032aa7  lea     rdx, [rsp+130h+pszDest]; lpSubKey
0x180032aac  mov     [rsp+130h+cchToCopy], rax; unsigned int
0x180032ab1  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180032ab8  call    cs:__imp_RegGetValueW
0x180032abe  test    eax, eax
0x180032ac0  jz      short loc_180032AF9
0x180032ac2  mov     rcx, [rbp+38h]; this
0x180032ac6  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180032acd  mov     r9d, eax; char *
0x180032ad0  mov     edx, 12F8h; void *
0x180032ad5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180032ada  mov     rcx, rbx; pv
0x180032add  mov     edi, eax
0x180032adf  call    cs:__imp_CoTaskMemFree
0x180032ae5  mov     rcx, [rsp+130h+lpsz]; pv
0x180032aea  test    rcx, rcx
0x180032aed  jz      short loc_180032AF5
0x180032aef  call    cs:__imp_CoTaskMemFree
0x180032af5  mov     eax, edi
0x180032af7  jmp     short loc_180032B0E
0x180032af9  mov     rcx, [rsp+130h+lpsz]; pv
0x180032afe  mov     [rdi], rbx
0x180032b01  test    rcx, rcx
0x180032b04  jz      short loc_180032B0C
0x180032b06  call    cs:__imp_CoTaskMemFree
0x180032b0c  xor     eax, eax
0x180032b0e  mov     rcx, [rbp+30h+var_10]
0x180032b12  xor     rcx, rsp; StackCookie
0x180032b15  call    __security_check_cookie
0x180032b1a  lea     r11, [rsp+130h+var_s0]
0x180032b22  mov     rbx, [r11+20h]
0x180032b26  mov     rdi, [r11+28h]
0x180032b2a  mov     rsp, r11
0x180032b2d  pop     rbp
0x180032b2e  retn
```
