# GatherDefaultAssociations(CSimplePointerArrayCoTaskMem<AssociationFileElement,CSimpleArrayStandardCompareHelper<AssociationFileElement *>> &)

- ea: `0x18033b038`
- end: `0x18033b5a1`
- name: `?GatherDefaultAssociations@@YAJAEAV?$CSimplePointerArrayCoTaskMem@UAssociationFileElement@@V?$CSimpleArrayStandardCompareHelper@PEAUAssociationFileElement@@@@@@@Z`
- size: `1385`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1805e265c`

## callees

- `0x18000d6cc`
- `0x180025a28`
- `0x1800432f0`
- `0x18004a030`
- `0x180065950`
- `0x1800a3080`
- `0x1800d13a0`
- `0x180168270`
- `0x1801f85b0`
- `0x18028dea4`
- `0x18033b038`
- `0x18033b5a8`
- `0x1803a4cb0`
- `0x18057583c`
- `0x1805dd590`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18033b42e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18033b44d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18033b568`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18033b42e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18033b44d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18033b568`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18033b19b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18033b19b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18033b127`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18033b127`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033b3ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033b3f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033b40b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033b47a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033b4ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033b532`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033b3ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033b3f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033b40b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033b47a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033b4ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033b532`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall GatherDefaultAssociations(_QWORD *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v4; // eax
  unsigned int i; // r14d
  LSTATUS v6; // eax
  unsigned int v7; // ecx
  DWORD j; // r15d
  void *v9; // rcx
  void *v10; // rdi
  int (__fastcall *v11)(void *, WCHAR *, _QWORD, __int64); // rbx
  int v12; // eax
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdi
  int (__fastcall *v16)(__int64, __int64, _QWORD, __int64); // rbx
  __int64 v17; // rax
  int v18; // eax
  unsigned __int16 *v19; // rdi
  __int64 v20; // rdx
  unsigned __int16 **v21; // rdx
  unsigned __int16 *v22; // rcx
  HKEY v23; // rcx
  __int64 v24; // rdx
  unsigned __int16 *v25; // rcx
  __int64 v26; // rdx
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  unsigned __int16 **v31; // [rsp+40h] [rbp-C0h] BYREF
  void *v32; // [rsp+48h] [rbp-B8h] BYREF
  char v33; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v34; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v36; // [rsp+68h] [rbp-98h] BYREF
  __int64 v37; // [rsp+70h] [rbp-90h] BYREF
  __int64 v38; // [rsp+78h] [rbp-88h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-80h] BYREF
  void *ppv; // [rsp+88h] [rbp-78h] BYREF
  DWORD cchClass; // [rsp+90h] [rbp-70h] BYREF
  DWORD cchName[3]; // [rsp+94h] [rbp-6Ch] BYREF
  WCHAR Name[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Class[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+518h] [rbp+418h]

  v2 = CTSimpleArray<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>>::_EnsureCapacity(
         a1,
         2);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBB,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\appdefaultsparser.cpp",
      (const char *)(unsigned int)v2,
      phkResult);
    return v3;
  }
  ppv = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  v4 = CApplicationAssociationRegistration::CreateInstance(&GUID_a357134e_8c1e_4edd_8474_40a80546f54f, &ppv);
  v3 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\appdefaultsparser.cpp",
      (const char *)(unsigned int)v4,
      phkResult);
    goto LABEL_68;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= 2 )
    {
      v3 = 0;
      goto LABEL_68;
    }
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v6 = RegOpenKeyExW(HKEY_CURRENT_USER, (&off_1806919C0)[2 * (int)i], 0, 0x20019u, &hKey);
    if ( v6 != 2 )
    {
      v7 = v6 > 0 ? (unsigned __int16)v6 | 0x80070000 : v6;
      if ( v7 != -2147024891 )
        break;
    }
    v23 = hKey;
    if ( hKey )
      goto LABEL_44;
LABEL_45:
    ;
  }
  if ( !v6 )
  {
    for ( j = 0; ; ++j )
    {
      cchName[0] = 260;
      cchClass = 260;
      v6 = RegEnumKeyExW(hKey, j, Name, cchName, 0, Class, &cchClass, 0);
      if ( v6 )
        break;
      v34 = 0;
      v31 = &v34;
      v32 = 0;
      v33 = 1;
      v3 = CTCoAllocPolicy::Alloc(v9, 1u, 0x7C0u, &v32);
      wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v31);
      if ( (v3 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD7,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\appdefaultsparser.cpp",
          (const char *)v3,
          phkResulta);
        goto LABEL_60;
      }
      v36 = 0;
      v10 = ppv;
      v11 = *(int (__fastcall **)(void *, WCHAR *, _QWORD, __int64))(*(_QWORD *)ppv + 64LL);
      phkResultb = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v36);
      if ( v11(v10, Name, *((unsigned int *)&off_1806919C0 + 4 * (int)i + 2), 2) >= 0 && !IsGeneratedProgId(v36) )
      {
        v12 = StringCchCopyW(v34, 0x104u, Name);
        v3 = v12;
        if ( v12 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xDC,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\appdefaultsparser.cpp",
            (const char *)(unsigned int)v12,
            phkResultb);
          goto LABEL_57;
        }
        if ( (unsigned int)StringCchCopyW(v34 + 520, 0x27u, v36) == -2147024774 )
        {
          v34[520] = 0;
        }
        else
        {
          v37 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
          v13 = AssocCreateElement(&CLSID_AssocProgidElement, &GUID_3c44ba76_de0e_4049_b6e4_6b31a5262707, &v37);
          v3 = v13;
          if ( v13 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xE8,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\appdefaultsparser.cpp",
              (const char *)(unsigned int)v13,
              phkResultb);
            goto LABEL_55;
          }
          if ( (*(unsigned int (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v37 + 32LL))(v37, v36) == -2147023741 )
          {
            v34[520] = 0;
          }
          else
          {
            v38 = 0;
            v14 = Microsoft::WRL::ComPtr<IPersistString2>::As<IAssociationElement>(&v37, &v38);
            v3 = v14;
            if ( v14 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xF2,
                (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\appdefaultsparser.cpp",
                (const char *)(unsigned int)v14,
                phkResultb);
              goto LABEL_53;
            }
            v34[260] = 0;
            pv = 0;
            v15 = v38;
            v16 = *(int (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v38 + 24LL);
            v17 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
            if ( v16(v15, 35061768, 0, v17) >= 0 )
            {
              v18 = StringCchCopyW(v34 + 260, 0x104u, (const unsigned __int16 *)pv);
              v3 = v18;
              if ( v18 < 0 )
              {
                v24 = 248;
LABEL_49:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v24,
                  (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\appdefaultsparser.cpp",
                  (const char *)(unsigned int)v18,
                  phkResultb);
                if ( pv )
                  CoTaskMemFree(pv);
LABEL_53:
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
LABEL_55:
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
LABEL_57:
                if ( v36 )
                  CoTaskMemFree(v36);
LABEL_60:
                v25 = v34;
                v34 = 0;
                if ( v25 )
                  CoTaskMemFree(v25);
                goto LABEL_65;
              }
            }
            v19 = v34;
            if ( v34[520] )
            {
              v20 = a1[1];
              if ( v20 == a1[3] )
              {
                v18 = CTSimpleArray<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>>::_EnsureCapacity(
                        a1,
                        v20 + 1);
                v3 = v18;
                if ( v18 < 0 )
                {
                  v24 = 253;
                  goto LABEL_49;
                }
              }
              v21 = (unsigned __int16 **)(*a1 + 8 * a1[1]++);
              if ( v21 )
                *v21 = v19;
              v34 = 0;
            }
            if ( pv )
              CoTaskMemFree(pv);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
        }
      }
      if ( v36 )
        CoTaskMemFree(v36);
      v22 = v34;
      v34 = 0;
      if ( v22 )
        CoTaskMemFree(v22);
    }
    if ( v6 != 259 )
    {
      v26 = 264;
      goto LABEL_64;
    }
    v23 = hKey;
    if ( !hKey )
      goto LABEL_45;
LABEL_44:
    RegCloseKey(v23);
    goto LABEL_45;
  }
  v26 = 201;
LABEL_64:
  v3 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v26,
         (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\appdefaultsparser.cpp",
         (const char *)(unsigned int)v6,
         phkResulta);
LABEL_65:
  if ( hKey )
    RegCloseKey(hKey);
LABEL_68:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  return v3;
}

```

## disassembly

```asm
0x18033b038  push    rbp
0x18033b03a  push    rbx
0x18033b03b  push    rsi
0x18033b03c  push    rdi
0x18033b03d  push    r12
0x18033b03f  push    r13
0x18033b041  push    r14
0x18033b043  push    r15
0x18033b045  lea     rbp, [rsp-3D8h]
0x18033b04d  sub     rsp, 4D8h
0x18033b054  mov     rax, cs:__security_cookie
0x18033b05b  xor     rax, rsp
0x18033b05e  mov     [rbp+410h+var_50], rax
0x18033b065  mov     rsi, rcx
0x18033b068  mov     edx, 2
0x18033b06d  call    ?_EnsureCapacity@?$CTSimpleArray@V?$ComPtr@U?$IVectorView@PEAUIStorageItemInformation@BulkAccess@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@U?$IVectorView@PEAUIStorageItemInformation@BulkAccess@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@U?$IVectorView@PEAUIStorageItemInformation@BulkAccess@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@U?$IVectorView@PEAUIStorageItemInformation@BulkAccess@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@@@@QEAAJ_K0@Z; CTSimpleArray<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18033b072  mov     ebx, eax
0x18033b074  xor     r13d, r13d
0x18033b077  test    eax, eax
0x18033b079  jns     short loc_18033B09B
0x18033b07b  mov     rcx, [rbp+418h]; this
0x18033b082  mov     r9d, eax; char *
0x18033b085  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\windows.storage\\sha"...
0x18033b08c  mov     edx, 0BBh; void *
0x18033b091  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033b096  jmp     loc_18033B57C
0x18033b09b  mov     [rbp+410h+ppv], r13
0x18033b09f  lea     rcx, [rbp+410h+ppv]
0x18033b0a3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18033b0a8  lea     rdx, [rbp+410h+ppv]; ppv
0x18033b0ac  lea     rcx, _GUID_a357134e_8c1e_4edd_8474_40a80546f54f; riid
0x18033b0b3  call    ?CreateInstance@CApplicationAssociationRegistration@@SAJAEBU_GUID@@PEAPEAX@Z; CApplicationAssociationRegistration::CreateInstance(_GUID const &,void * *)
0x18033b0b8  mov     ebx, eax
0x18033b0ba  test    eax, eax
0x18033b0bc  jns     short loc_18033B0DE
0x18033b0be  mov     rcx, [rbp+418h]; this
0x18033b0c5  mov     r9d, eax; char *
0x18033b0c8  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\windows.storage\\sha"...
0x18033b0cf  mov     edx, 0BEh; void *
0x18033b0d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033b0d9  jmp     loc_18033B573
0x18033b0de  mov     r14d, r13d
0x18033b0e1  lea     rbx, off_1806919C0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18033b0e8  cmp     r14d, 2
0x18033b0ec  jnb     loc_18033B570
0x18033b0f2  mov     [rsp+510h+hKey], r13
0x18033b0f7  xor     edx, edx
0x18033b0f9  lea     rcx, [rsp+510h+hKey]
0x18033b0fe  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18033b103  movsxd  r12, r14d
0x18033b106  add     r12, r12
0x18033b109  lea     rax, [rsp+510h+hKey]
0x18033b10e  mov     [rsp+510h+phkResult], rax; unsigned int
0x18033b113  mov     r9d, 20019h; samDesired
0x18033b119  xor     r8d, r8d; ulOptions
0x18033b11c  mov     rdx, [rbx+r12*8]; lpSubKey
0x18033b120  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18033b127  call    cs:__imp_RegOpenKeyExW
0x18033b12d  cmp     eax, 2
0x18033b130  jz      loc_18033B443
0x18033b136  test    eax, eax
0x18033b138  jg      short loc_18033B13E
0x18033b13a  mov     ecx, eax
0x18033b13c  jmp     short loc_18033B147
0x18033b13e  movzx   ecx, ax
0x18033b141  or      ecx, 80070000h
0x18033b147  cmp     ecx, 80070005h
0x18033b14d  jz      loc_18033B443
0x18033b153  test    eax, eax
0x18033b155  jnz     loc_18033B541
0x18033b15b  mov     r15d, r13d
0x18033b15e  mov     [rbp+410h+cchName], 104h
0x18033b165  mov     [rbp+410h+cchClass], 104h
0x18033b16c  mov     [rsp+510h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18033b171  lea     rax, [rbp+410h+cchClass]
0x18033b175  mov     [rsp+510h+lpcchClass], rax; lpcchClass
0x18033b17a  lea     rax, [rbp+410h+Class]
0x18033b181  mov     [rsp+510h+lpClass], rax; lpClass
0x18033b186  mov     [rsp+510h+phkResult], r13; int
0x18033b18b  lea     r9, [rbp+410h+cchName]; lpcchName
0x18033b18f  lea     r8, [rbp+410h+Name]; lpName
0x18033b193  mov     edx, r15d; dwIndex
0x18033b196  mov     rcx, [rsp+510h+hKey]; hKey
0x18033b19b  call    cs:__imp_RegEnumKeyExW
0x18033b1a1  test    eax, eax
0x18033b1a3  jnz     loc_18033B419
0x18033b1a9  mov     [rsp+510h+var_4B8], r13
0x18033b1ae  lea     rax, [rsp+510h+var_4B8]
0x18033b1b3  mov     [rsp+510h+var_4D0], rax
0x18033b1b8  mov     [rsp+510h+var_4C8], r13
0x18033b1bd  mov     [rsp+510h+var_4C0], 1
0x18033b1c2  lea     r9, [rsp+510h+var_4C8]; void **
0x18033b1c7  mov     edx, 1; unsigned int
0x18033b1cc  mov     r8d, 7C0h; unsigned __int64
0x18033b1d2  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18033b1d7  mov     ebx, eax
0x18033b1d9  lea     rcx, [rsp+510h+var_4D0]
0x18033b1de  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18033b1e3  test    ebx, ebx
0x18033b1e5  js      loc_18033B507
0x18033b1eb  mov     [rsp+510h+var_4A8], r13
0x18033b1f0  mov     rdi, [rbp+410h+ppv]
0x18033b1f4  mov     rax, [rdi]
0x18033b1f7  mov     rbx, [rax+40h]
0x18033b1fb  lea     rcx, [rsp+510h+var_4A8]
0x18033b200  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18033b205  mov     [rsp+510h+phkResult], rax; int
0x18033b20a  mov     r9d, 2
0x18033b210  lea     rax, off_1806919C0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18033b217  mov     r8d, [rax+r12*8+8]
0x18033b21c  lea     rdx, [rbp+410h+Name]
0x18033b220  mov     rcx, rdi
0x18033b223  mov     rax, rbx
0x18033b226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033b22b  test    eax, eax
0x18033b22d  js      loc_18033B3EB
0x18033b233  mov     rcx, [rsp+510h+var_4A8]; unsigned __int16 *
0x18033b238  call    ?IsGeneratedProgId@@YA_NPEBG@Z; IsGeneratedProgId(ushort const *)
0x18033b23d  test    al, al
0x18033b23f  jnz     loc_18033B3EB
0x18033b245  lea     r8, [rbp+410h+Name]; unsigned __int16 *
0x18033b249  mov     edx, 104h; unsigned __int64
0x18033b24e  mov     rcx, [rsp+510h+var_4B8]; unsigned __int16 *
0x18033b253  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18033b258  mov     ebx, eax
0x18033b25a  test    eax, eax
0x18033b25c  js      loc_18033B4D9
0x18033b262  mov     rcx, [rsp+510h+var_4B8]
0x18033b267  add     rcx, 410h; unsigned __int16 *
0x18033b26e  mov     r8, [rsp+510h+var_4A8]; unsigned __int16 *
0x18033b273  mov     edx, 27h ; '''; unsigned __int64
0x18033b278  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18033b27d  cmp     eax, 8007007Ah
0x18033b282  jnz     short loc_18033B296
0x18033b284  mov     rax, [rsp+510h+var_4B8]
0x18033b289  mov     [rax+410h], r13w
0x18033b291  jmp     loc_18033B3EB
0x18033b296  mov     [rsp+510h+var_4A0], r13
0x18033b29b  lea     rcx, [rsp+510h+var_4A0]
0x18033b2a0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18033b2a5  lea     r8, [rsp+510h+var_4A0]
0x18033b2aa  lea     rdx, _GUID_3c44ba76_de0e_4049_b6e4_6b31a5262707
0x18033b2b1  lea     rcx, CLSID_AssocProgidElement
0x18033b2b8  call    AssocCreateElement
0x18033b2bd  mov     ebx, eax
0x18033b2bf  test    eax, eax
0x18033b2c1  js      loc_18033B4B1
0x18033b2c7  mov     rcx, [rsp+510h+var_4A0]
0x18033b2cc  mov     rax, [rcx]
0x18033b2cf  mov     rdx, [rsp+510h+var_4A8]
0x18033b2d4  mov     rax, [rax+20h]
0x18033b2d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033b2dd  cmp     eax, 80070483h
0x18033b2e2  jnz     short loc_18033B2F6
0x18033b2e4  mov     rax, [rsp+510h+var_4B8]
0x18033b2e9  mov     [rax+410h], r13w
0x18033b2f1  jmp     loc_18033B3E0
0x18033b2f6  mov     [rsp+510h+var_498], r13
0x18033b2fb  lea     rdx, [rsp+510h+var_498]
0x18033b300  lea     rcx, [rsp+510h+var_4A0]
0x18033b305  call    ??$As@UIAssociationElement@@@?$ComPtr@UIPersistString2@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IPersistString2>::As<IAssociationElement>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAssociationElement>>)
0x18033b30a  mov     ebx, eax
0x18033b30c  test    eax, eax
0x18033b30e  js      loc_18033B489
0x18033b314  mov     rax, [rsp+510h+var_4B8]
0x18033b319  mov     [rax+208h], r13w
0x18033b321  mov     [rbp+410h+pv], r13
0x18033b325  mov     rdi, [rsp+510h+var_498]
0x18033b32a  mov     rax, [rdi]
0x18033b32d  mov     rbx, [rax+18h]
0x18033b331  lea     rcx, [rbp+410h+pv]
0x18033b335  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18033b33a  mov     r9, rax
0x18033b33d  xor     r8d, r8d
0x18033b340  mov     edx, 2170008h
0x18033b345  mov     rcx, rdi
0x18033b348  mov     rax, rbx
0x18033b34b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033b350  test    eax, eax
0x18033b352  js      short loc_18033B378
0x18033b354  mov     rcx, [rsp+510h+var_4B8]
0x18033b359  add     rcx, 208h; unsigned __int16 *
0x18033b360  mov     r8, [rbp+410h+pv]; unsigned __int16 *
0x18033b364  mov     edx, 104h; unsigned __int64
0x18033b369  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18033b36e  mov     ebx, eax
0x18033b370  test    eax, eax
0x18033b372  js      loc_18033B455
0x18033b378  mov     rdi, [rsp+510h+var_4B8]
0x18033b37d  cmp     [rdi+410h], r13w
0x18033b385  jz      short loc_18033B3C5
0x18033b387  mov     rdx, [rsi+8]
0x18033b38b  cmp     rdx, [rsi+18h]
0x18033b38f  jnz     short loc_18033B3A6
0x18033b391  inc     rdx
0x18033b394  mov     rcx, rsi
0x18033b397  call    ?_EnsureCapacity@?$CTSimpleArray@V?$ComPtr@U?$IVectorView@PEAUIStorageItemInformation@BulkAccess@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@U?$IVectorView@PEAUIStorageItemInformation@BulkAccess@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@U?$IVectorView@PEAUIStorageItemInformation@BulkAccess@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@U?$IVectorView@PEAUIStorageItemInformation@BulkAccess@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@@@@QEAAJ_K0@Z; CTSimpleArray<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18033b39c  mov     ebx, eax
0x18033b39e  test    eax, eax
0x18033b3a0  js      loc_18033B482
0x18033b3a6  inc     qword ptr [rsi+8]
0x18033b3aa  mov     rdx, [rsi+8]
0x18033b3ae  mov     rax, [rsi]
0x18033b3b1  dec     rdx
0x18033b3b4  lea     rdx, [rax+rdx*8]
0x18033b3b8  test    rdx, rdx
0x18033b3bb  jz      short loc_18033B3C0
0x18033b3bd  mov     [rdx], rdi
0x18033b3c0  mov     [rsp+510h+var_4B8], r13
0x18033b3c5  mov     rcx, [rbp+410h+pv]; pv
0x18033b3c9  test    rcx, rcx
0x18033b3cc  jz      short loc_18033B3D5
0x18033b3ce  call    cs:__imp_CoTaskMemFree
0x18033b3d4  nop
0x18033b3d5  lea     rcx, [rsp+510h+var_498]
0x18033b3da  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18033b3df  nop
0x18033b3e0  lea     rcx, [rsp+510h+var_4A0]
0x18033b3e5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18033b3ea  nop
0x18033b3eb  mov     rcx, [rsp+510h+var_4A8]; pv
0x18033b3f0  test    rcx, rcx
0x18033b3f3  jz      short loc_18033B3FC
0x18033b3f5  call    cs:__imp_CoTaskMemFree
0x18033b3fb  nop
0x18033b3fc  mov     rcx, [rsp+510h+var_4B8]; pv
0x18033b401  mov     [rsp+510h+var_4B8], r13
0x18033b406  test    rcx, rcx
0x18033b409  jz      short loc_18033B411
0x18033b40b  call    cs:__imp_CoTaskMemFree
0x18033b411  inc     r15d
0x18033b414  jmp     loc_18033B15E
0x18033b419  cmp     eax, 103h
0x18033b41e  jnz     loc_18033B53A
0x18033b424  mov     rcx, [rsp+510h+hKey]; hKey
0x18033b429  test    rcx, rcx
0x18033b42c  jz      short loc_18033B434
0x18033b42e  call    cs:__imp_RegCloseKey
0x18033b434  lea     rbx, off_1806919C0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18033b43b  inc     r14d
0x18033b43e  jmp     loc_18033B0E8
0x18033b443  mov     rcx, [rsp+510h+hKey]; hKey
0x18033b448  test    rcx, rcx
0x18033b44b  jz      short loc_18033B43B
0x18033b44d  call    cs:__imp_RegCloseKey
0x18033b453  jmp     short loc_18033B43B
0x18033b455  mov     edx, 0F8h; void *
0x18033b45a  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\windows.storage\\sha"...
0x18033b461  mov     r9d, eax; char *
0x18033b464  mov     rcx, [rbp+418h]; this
0x18033b46b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033b470  nop
0x18033b471  mov     rcx, [rbp+410h+pv]; pv
0x18033b475  test    rcx, rcx
0x18033b478  jz      short loc_18033B4A5
0x18033b47a  call    cs:__imp_CoTaskMemFree
0x18033b480  jmp     short loc_18033B4A5
0x18033b482  mov     edx, 0FDh
0x18033b487  jmp     short loc_18033B45A
0x18033b489  mov     rcx, [rbp+418h]; this
0x18033b490  mov     r9d, eax; char *
0x18033b493  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\windows.storage\\sha"...
0x18033b49a  mov     edx, 0F2h; void *
0x18033b49f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033b4a4  nop
0x18033b4a5  lea     rcx, [rsp+510h+var_498]
0x18033b4aa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18033b4af  jmp     short loc_18033B4CD
0x18033b4b1  mov     rcx, [rbp+418h]; this
0x18033b4b8  mov     r9d, eax; char *
0x18033b4bb  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\windows.storage\\sha"...
0x18033b4c2  mov     edx, 0E8h; void *
0x18033b4c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033b4cc  nop
0x18033b4cd  lea     rcx, [rsp+510h+var_4A0]
0x18033b4d2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18033b4d7  jmp     short loc_18033B4F5
0x18033b4d9  mov     rcx, [rbp+418h]; this
0x18033b4e0  mov     r9d, eax; char *
0x18033b4e3  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\windows.storage\\sha"...
0x18033b4ea  mov     edx, 0DCh; void *
0x18033b4ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033b4f4  nop
0x18033b4f5  mov     rcx, [rsp+510h+var_4A8]; pv
0x18033b4fa  test    rcx, rcx
0x18033b4fd  jz      short loc_18033B523
0x18033b4ff  call    cs:__imp_CoTaskMemFree
0x18033b505  jmp     short loc_18033B523
0x18033b507  mov     rcx, [rbp+418h]; this
0x18033b50e  mov     r9d, ebx; char *
0x18033b511  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\windows.storage\\sha"...
0x18033b518  mov     edx, 0D7h; void *
0x18033b51d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033b522  nop
0x18033b523  mov     rcx, [rsp+510h+var_4B8]; pv
0x18033b528  mov     [rsp+510h+var_4B8], r13
0x18033b52d  test    rcx, rcx
0x18033b530  jz      short loc_18033B55E
0x18033b532  call    cs:__imp_CoTaskMemFree
0x18033b538  jmp     short loc_18033B55E
  ... truncated ...
```
