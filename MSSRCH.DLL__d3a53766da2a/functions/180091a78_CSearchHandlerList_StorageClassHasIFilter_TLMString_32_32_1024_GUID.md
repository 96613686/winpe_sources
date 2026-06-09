# CSearchHandlerList::StorageClassHasIFilter(TLMString<32,32,1024> &,_GUID *)

- ea: `0x180091a78`
- end: `0x180091d36`
- name: `?StorageClassHasIFilter@CSearchHandlerList@@IEAA_NAEAV?$TLMString@$0CA@$0CA@$0EAA@@@PEAU_GUID@@@Z`
- size: `702`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180069d70`
- `0x1800911c0`
- `0x1800b5f80`

## callees

- `0x18000c4cc`
- `0x180091a78`
- `0x1800b837c`
- `0x1800e4710`
- `0x1801244c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180091d2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180091d2b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091acd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091b81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091c41`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091acd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091b81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091c41`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180091bce`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180091c8d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180091cf3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180091bce`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180091c8d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180091cf3`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180091cb4`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180091cb4`

## string_xrefs

- `0x180091b3c`: `%ws\CLSID`
- `0x180091bf8`: `CLSID\%ws\PersistentHandler`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall CSearchHandlerList::StorageClassHasIFilter(__int64 a1, __int64 a2, GUID *a3)
{
  char v4; // bl
  LSTATUS v5; // eax
  bool v6; // sf
  bool v8; // sf
  int ValueW; // ecx
  HKEY *phkResult; // rax
  LSTATUS v11; // eax
  bool v12; // sf
  int v13; // ecx
  bool v14; // sf
  HKEY *v15; // rax
  LSTATUS v16; // eax
  bool v17; // sf
  int v18; // ecx
  bool v19; // sf
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v21; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  _WORD pvData[40]; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR sz[40]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR SubKey[264]; // [rsp+100h] [rbp+0h] BYREF
  _WORD v27[264]; // [rsp+310h] [rbp+210h] BYREF

  v4 = 0;
  hKey = 0;
  v5 = RegOpenKeyExW(HKEY_CLASSES_ROOT, *(LPCWSTR *)(a2 + 8), 0, 0x20019u, &hKey);
  v6 = v5 < 0;
  if ( v5 > 0 )
    v6 = 1;
  if ( !v6 )
  {
    pcbData = 520;
    ValueW = RegGetValueW(hKey, 0, 0, 2u, 0, v27, &pcbData);
    if ( ValueW )
    {
      v27[0] = 0;
      v8 = ValueW < 0;
      if ( ValueW <= 0 )
      {
LABEL_10:
        if ( v8 || (int)StringCchPrintfW(SubKey, 0x104u, L"%ws\\CLSID", v27) < 0 )
          goto LABEL_4;
        hkey = 0;
        phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
        v11 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, phkResult);
        v12 = v11 < 0;
        if ( v11 > 0 )
          v12 = 1;
        if ( v12 )
        {
LABEL_35:
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          goto LABEL_4;
        }
        pcbData = 78;
        v13 = RegGetValueW(hkey, 0, 0, 2u, 0, pvData, &pcbData);
        if ( v13 )
        {
          pvData[0] = 0;
          v14 = v13 < 0;
          if ( v13 <= 0 )
          {
LABEL_19:
            if ( v14 || (int)StringCchPrintfW(SubKey, 0x104u, L"CLSID\\%ws\\PersistentHandler", pvData) < 0 )
              goto LABEL_35;
            v21 = 0;
            v15 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v21);
            v16 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, v15);
            v17 = v16 < 0;
            if ( v16 > 0 )
              v17 = 1;
            if ( v17 )
              goto LABEL_34;
            pcbData = 78;
            v18 = RegGetValueW(v21, 0, 0, 2u, 0, sz, &pcbData);
            if ( v18 )
            {
              sz[0] = 0;
              v19 = v18 < 0;
              if ( v18 <= 0 )
                goto LABEL_28;
              v18 = (unsigned __int16)v18 | 0x80070000;
            }
            v19 = v18 < 0;
LABEL_28:
            if ( v19 )
            {
              if ( v18 == -2147024894 )
              {
LABEL_34:
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v21);
                goto LABEL_35;
              }
            }
            else
            {
              CLSIDFromString(sz, a3);
            }
            v4 = 1;
            goto LABEL_34;
          }
          v13 = (unsigned __int16)v13 | 0x80070000;
        }
        v14 = v13 < 0;
        goto LABEL_19;
      }
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    }
    v8 = ValueW < 0;
    goto LABEL_10;
  }
LABEL_4:
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x180091a78  mov     [rsp-8+arg_0], rbx
0x180091a7d  push    rbp
0x180091a7e  push    rdi
0x180091a7f  push    r14
0x180091a81  lea     rbp, [rsp-430h]
0x180091a89  sub     rsp, 530h
0x180091a90  mov     rax, cs:__security_cookie
0x180091a97  xor     rax, rsp
0x180091a9a  mov     [rbp+440h+var_20], rax
0x180091aa1  mov     rdi, r8
0x180091aa4  xor     bl, bl
0x180091aa6  mov     [rsp+540h+hKey], 0
0x180091aaf  lea     rax, [rsp+540h+hKey]
0x180091ab4  mov     [rsp+540h+phkResult], rax; phkResult
0x180091ab9  mov     r9d, 20019h; samDesired
0x180091abf  xor     r8d, r8d; ulOptions
0x180091ac2  mov     rdx, [rdx+8]; lpSubKey
0x180091ac6  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180091acd  call    cs:__imp_RegOpenKeyExW
0x180091ad3  mov     r14d, 80070000h
0x180091ad9  test    eax, eax
0x180091adb  jle     short loc_180091AE5
0x180091add  movzx   eax, ax
0x180091ae0  or      eax, r14d
0x180091ae3  test    eax, eax
0x180091ae5  jns     loc_180091CBC
0x180091aeb  mov     rcx, [rsp+540h+hKey]; hKey
0x180091af0  test    rcx, rcx
0x180091af3  jnz     loc_180091D2B
0x180091af9  mov     al, bl
0x180091afb  mov     rcx, [rbp+440h+var_20]
0x180091b02  xor     rcx, rsp; StackCookie
0x180091b05  call    __security_check_cookie
0x180091b0a  mov     rbx, [rsp+540h+arg_0]
0x180091b12  add     rsp, 530h
0x180091b19  pop     r14
0x180091b1b  pop     rdi
0x180091b1c  pop     rbp
0x180091b1d  retn
0x180091b1e  xor     eax, eax
0x180091b20  mov     [rbp+440h+var_230], ax
0x180091b27  test    ecx, ecx
0x180091b29  jle     short loc_180091B33
0x180091b2b  movzx   ecx, cx
0x180091b2e  or      ecx, r14d
0x180091b31  test    ecx, ecx
0x180091b33  js      short loc_180091AEB
0x180091b35  lea     r9, [rbp+440h+var_230]
0x180091b3c  lea     r8, aWsClsid; "%ws\\CLSID"
0x180091b43  mov     edx, 104h; unsigned __int64
0x180091b48  lea     rcx, [rbp+440h+SubKey]; wchar_t *
0x180091b4c  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180091b51  test    eax, eax
0x180091b53  js      short loc_180091AEB
0x180091b55  mov     [rsp+540h+hkey], 0
0x180091b5e  lea     rcx, [rsp+540h+hkey]
0x180091b63  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180091b68  mov     [rsp+540h+phkResult], rax; phkResult
0x180091b6d  mov     r9d, 20019h; samDesired
0x180091b73  xor     r8d, r8d; ulOptions
0x180091b76  lea     rdx, [rbp+440h+SubKey]; lpSubKey
0x180091b7a  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180091b81  call    cs:__imp_RegOpenKeyExW
0x180091b87  test    eax, eax
0x180091b89  jle     short loc_180091B93
0x180091b8b  movzx   eax, ax
0x180091b8e  or      eax, r14d
0x180091b91  test    eax, eax
0x180091b93  js      loc_180091D1C
0x180091b99  mov     [rsp+540h+var_500], 4Eh ; 'N'
0x180091ba1  lea     rax, [rsp+540h+var_500]
0x180091ba6  mov     [rsp+540h+pcbData], rax; pcbData
0x180091bab  lea     rax, [rsp+540h+var_4E0]
0x180091bb0  mov     [rsp+540h+pvData], rax; pvData
0x180091bb5  mov     [rsp+540h+phkResult], 0; pdwType
0x180091bbe  mov     r9d, 2; dwFlags
0x180091bc4  xor     r8d, r8d; lpValue
0x180091bc7  xor     edx, edx; lpSubKey
0x180091bc9  mov     rcx, [rsp+540h+hkey]; hkey
0x180091bce  call    cs:__imp_RegGetValueW
0x180091bd4  mov     ecx, eax
0x180091bd6  test    eax, eax
0x180091bd8  jz      short loc_180091BEB
0x180091bda  xor     eax, eax
0x180091bdc  mov     [rsp+540h+var_4E0], ax
0x180091be1  test    ecx, ecx
0x180091be3  jle     short loc_180091BED
0x180091be5  movzx   ecx, cx
0x180091be8  or      ecx, r14d
0x180091beb  test    ecx, ecx
0x180091bed  js      loc_180091D1C
0x180091bf3  lea     r9, [rsp+540h+var_4E0]
0x180091bf8  lea     r8, aClsidWsPersist; "CLSID\\%ws\\PersistentHandler"
0x180091bff  mov     edx, 104h; unsigned __int64
0x180091c04  lea     rcx, [rbp+440h+SubKey]; wchar_t *
0x180091c08  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180091c0d  test    eax, eax
0x180091c0f  js      loc_180091D1C
0x180091c15  mov     [rsp+540h+var_4F8], 0
0x180091c1e  lea     rcx, [rsp+540h+var_4F8]
0x180091c23  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180091c28  mov     [rsp+540h+phkResult], rax; phkResult
0x180091c2d  mov     r9d, 20019h; samDesired
0x180091c33  xor     r8d, r8d; ulOptions
0x180091c36  lea     rdx, [rbp+440h+SubKey]; lpSubKey
0x180091c3a  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180091c41  call    cs:__imp_RegOpenKeyExW
0x180091c47  test    eax, eax
0x180091c49  jle     short loc_180091C53
0x180091c4b  movzx   eax, ax
0x180091c4e  or      eax, r14d
0x180091c51  test    eax, eax
0x180091c53  js      loc_180091D12
0x180091c59  mov     [rsp+540h+var_500], 4Eh ; 'N'
0x180091c61  lea     rax, [rsp+540h+var_500]
0x180091c66  mov     [rsp+540h+pcbData], rax; pcbData
0x180091c6b  lea     rax, [rbp+440h+sz]
0x180091c6f  mov     [rsp+540h+pvData], rax; pvData
0x180091c74  mov     [rsp+540h+phkResult], 0; pdwType
0x180091c7d  mov     r9d, 2; dwFlags
0x180091c83  xor     r8d, r8d; lpValue
0x180091c86  xor     edx, edx; lpSubKey
0x180091c88  mov     rcx, [rsp+540h+var_4F8]; hkey
0x180091c8d  call    cs:__imp_RegGetValueW
0x180091c93  mov     ecx, eax
0x180091c95  test    eax, eax
0x180091c97  jz      short loc_180091CA9
0x180091c99  xor     eax, eax
0x180091c9b  mov     [rbp+440h+sz], ax
0x180091c9f  test    ecx, ecx
0x180091ca1  jle     short loc_180091CAB
0x180091ca3  movzx   ecx, cx
0x180091ca6  or      ecx, r14d
0x180091ca9  test    ecx, ecx
0x180091cab  js      short loc_180091D08
0x180091cad  mov     rdx, rdi; pclsid
0x180091cb0  lea     rcx, [rbp+440h+sz]; lpsz
0x180091cb4  call    cs:__imp_CLSIDFromString
0x180091cba  jmp     short loc_180091D10
0x180091cbc  mov     [rsp+540h+var_500], 208h
0x180091cc4  lea     rax, [rsp+540h+var_500]
0x180091cc9  mov     [rsp+540h+pcbData], rax; pcbData
0x180091cce  lea     rax, [rbp+440h+var_230]
0x180091cd5  mov     [rsp+540h+pvData], rax; pvData
0x180091cda  mov     [rsp+540h+phkResult], 0; pdwType
0x180091ce3  mov     r9d, 2; dwFlags
0x180091ce9  xor     r8d, r8d; lpValue
0x180091cec  xor     edx, edx; lpSubKey
0x180091cee  mov     rcx, [rsp+540h+hKey]; hkey
0x180091cf3  call    cs:__imp_RegGetValueW
0x180091cf9  mov     ecx, eax
0x180091cfb  test    eax, eax
0x180091cfd  jz      loc_180091B31
0x180091d03  jmp     loc_180091B1E
0x180091d08  cmp     ecx, 80070002h
0x180091d0e  jz      short loc_180091D12
0x180091d10  mov     bl, 1
0x180091d12  lea     rcx, [rsp+540h+var_4F8]
0x180091d17  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180091d1c  lea     rcx, [rsp+540h+hkey]
0x180091d21  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180091d26  jmp     loc_180091AEB
0x180091d2b  call    cs:__imp_RegCloseKey
0x180091d31  jmp     loc_180091AF9
```
