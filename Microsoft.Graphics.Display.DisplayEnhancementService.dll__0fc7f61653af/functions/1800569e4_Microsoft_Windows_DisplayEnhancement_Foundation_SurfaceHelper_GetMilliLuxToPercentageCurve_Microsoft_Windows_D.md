# Microsoft::Windows::DisplayEnhancement::Foundation::SurfaceHelper::GetMilliLuxToPercentageCurve(Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToPercentageCurve &)

- ea: `0x1800569e4`
- end: `0x180056ec0`
- name: `?GetMilliLuxToPercentageCurve@SurfaceHelper@Foundation@DisplayEnhancement@Windows@Microsoft@@SA_NAEAUMilliLuxToPercentageCurve@2345@@Z`
- size: `1244`
- prototype: `bool __fastcall(struct Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToPercentageCurve *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800571e0`

## callees

- `0x180005860`
- `0x180006440`
- `0x1800064ac`
- `0x180006574`
- `0x180011814`
- `0x180012358`
- `0x18001f890`
- `0x18001f9d8`
- `0x18004ea90`
- `0x180056030`
- `0x1800566b4`
- `0x1800569e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180056d0c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180056d93`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180056d0c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180056d93`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056ca2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056ca2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Microsoft::Windows::DisplayEnhancement::Foundation::SurfaceHelper::GetMilliLuxToPercentageCurve(
        struct Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToPercentageCurve *a1)
{
  LSTATUS v2; // ebx
  unsigned int i; // ebx
  unsigned int j; // edi
  __int64 v6; // rax
  __int64 v7; // rbx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  int v10; // [rsp+40h] [rbp-C0h] BYREF
  int v11; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v12; // [rsp+48h] [rbp-B8h] BYREF
  int v13; // [rsp+50h] [rbp-B0h] BYREF
  int v14; // [rsp+54h] [rbp-ACh] BYREF
  _BYTE v15[8]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v16; // [rsp+60h] [rbp-A0h]
  _QWORD *v17; // [rsp+68h] [rbp-98h]
  HKEY *p_hKey; // [rsp+70h] [rbp-90h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  char v20; // [rsp+80h] [rbp-80h]
  _BYTE v21[24]; // [rsp+88h] [rbp-78h] BYREF
  wchar_t Format[16]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR SubKey[136]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t Buffer[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  wchar_t Data[64]; // [rsp+210h] [rbp+110h] BYREF

  wcscpy(
    SubKey,
    L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AdaptiveDisplayBrightness\\{23B44AF2-78CE-4943-81DF-89817E8D23FD}\\"
     "CustomAdbConfiguration");
  wcscpy(Format, L"AdbCurve%03d");
  hKey = 0;
  cbData = 0;
  v10 = 0;
  v11 = 0;
  v14 = 0;
  v13 = 0;
  p_hKey = &hKey;
  phkResult = 0;
  v20 = 1;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &phkResult);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( v2 )
    goto LABEL_14;
  for ( i = 0; i < 0x200; ++i )
  {
    swprintf_s(Buffer, 0x20u, Format, i);
    cbData = 128;
    if ( RegQueryValueExW(hKey, Buffer, 0, 0, (LPBYTE)Data, &cbData) )
      break;
  }
  if ( i < 2 )
  {
LABEL_14:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return 0;
  }
  else
  {
    std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToPercentageMapping>::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToPercentageMapping>(v15);
    for ( j = 0; j < i; ++j )
    {
      swprintf_s(Buffer, 0x20u, Format, j);
      memset_0(Data, 0, sizeof(Data));
      cbData = 128;
      if ( RegQueryValueExW(hKey, Buffer, 0, 0, (LPBYTE)Data, &cbData) )
      {
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::ClientContextHandle>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::ClientContextHandle>>>>>>>(v15);
        goto LABEL_14;
      }
      swscanf_s(Data, L"%d:%d:%d:%d", &v10, &v11, &v14, &v13);
      LODWORD(v12) = 1000 * v10;
      BYTE4(v12) = v11;
      if ( v16 == v17 )
        std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToMilliNitsMapping>::_Emplace_reallocate<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToMilliNitsMapping>(
          v15,
          v16,
          &v12);
      else
        *v16++ = v12;
    }
    v6 = std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToMilliNitsMapping>::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToMilliNitsMapping>(
           &p_hKey,
           v15);
    v7 = Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToPercentageCurve::MilliLuxToPercentageCurve(
           v21,
           v6);
    if ( a1 != (struct Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToPercentageCurve *)v7 )
    {
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::ClientContextHandle>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::ClientContextHandle>>>>>>>(a1);
      *(_QWORD *)a1 = *(_QWORD *)v7;
      *((_QWORD *)a1 + 1) = *(_QWORD *)(v7 + 8);
      *((_QWORD *)a1 + 2) = *(_QWORD *)(v7 + 16);
      *(_QWORD *)v7 = 0;
      *(_QWORD *)(v7 + 8) = 0;
      *(_QWORD *)(v7 + 16) = 0;
    }
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::ClientContextHandle>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::ClientContextHandle>>>>>>>(v21);
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::ClientContextHandle>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::ClientContextHandle>>>>>>>(v15);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return 1;
  }
}

```

## disassembly

```asm
0x1800569e4  push    rbp
0x1800569e6  push    rbx
0x1800569e7  push    rsi
0x1800569e8  push    rdi
0x1800569e9  push    r12
0x1800569eb  push    r13
0x1800569ed  push    r14
0x1800569ef  push    r15
0x1800569f1  lea     rbp, [rsp-1A8h]
0x1800569f9  sub     rsp, 2A8h
0x180056a00  mov     rax, cs:__security_cookie
0x180056a07  xor     rax, rsp
0x180056a0a  mov     [rbp+1E0h+var_50], rax
0x180056a11  mov     rsi, rcx
0x180056a14  mov     dword ptr [rbp+1E0h+SubKey], 6F0053h
0x180056a1b  mov     [rbp+1E0h+var_21C], 740066h
0x180056a22  mov     [rbp+1E0h+var_218], 610077h
0x180056a29  mov     [rbp+1E0h+var_214], 650072h
0x180056a30  mov     [rbp+1E0h+var_210], 4D005Ch
0x180056a37  mov     [rbp+1E0h+var_20C], 630069h
0x180056a3e  mov     [rbp+1E0h+var_208], 6F0072h
0x180056a45  mov     [rbp+1E0h+var_204], 6F0073h
0x180056a4c  mov     [rbp+1E0h+var_200], 740066h
0x180056a53  mov     [rbp+1E0h+var_1FC], 57005Ch
0x180056a5a  mov     [rbp+1E0h+var_1F8], 6E0069h
0x180056a61  mov     [rbp+1E0h+var_1F4], 6F0064h
0x180056a68  mov     [rbp+1E0h+var_1F0], 730077h
0x180056a6f  mov     [rbp+1E0h+var_1EC], 4E0020h
0x180056a76  mov     [rbp+1E0h+var_1E8], 5C0054h
0x180056a7d  mov     [rbp+1E0h+var_1E4], 750043h
0x180056a84  mov     [rbp+1E0h+var_1E0], 720072h
0x180056a8b  mov     [rbp+1E0h+var_1DC], 6E0065h
0x180056a92  mov     [rbp+1E0h+var_1D8], 560074h
0x180056a99  mov     [rbp+1E0h+var_1D4], 720065h
0x180056aa0  mov     [rbp+1E0h+var_1D0], 690073h
0x180056aa7  mov     [rbp+1E0h+var_1CC], 6E006Fh
0x180056aae  mov     [rbp+1E0h+var_1C8], 41005Ch
0x180056ab5  mov     [rbp+1E0h+var_1C4], 610064h
0x180056abc  mov     [rbp+1E0h+var_1C0], 740070h
0x180056ac3  mov     [rbp+1E0h+var_1BC], 760069h
0x180056aca  mov     [rbp+1E0h+var_1B8], 440065h
0x180056ad1  mov     [rbp+1E0h+var_1B4], 730069h
0x180056ad8  mov     [rbp+1E0h+var_1B0], 6C0070h
0x180056adf  mov     [rbp+1E0h+var_1AC], 790061h
0x180056ae6  mov     [rbp+1E0h+var_1A8], 720042h
0x180056aed  mov     [rbp+1E0h+var_1A4], 670069h
0x180056af4  mov     [rbp+1E0h+var_1A0], 740068h
0x180056afb  mov     [rbp+1E0h+var_19C], 65006Eh
0x180056b02  mov     [rbp+1E0h+var_198], 730073h
0x180056b09  mov     [rbp+1E0h+var_194], 7B005Ch
0x180056b10  mov     [rbp+1E0h+var_190], 330032h
0x180056b17  mov     [rbp+1E0h+var_18C], 340042h
0x180056b1e  mov     [rbp+1E0h+var_188], 410034h
0x180056b25  mov     [rbp+1E0h+var_184], 320046h
0x180056b2c  mov     [rbp+1E0h+var_180], 37002Dh
0x180056b33  mov     [rbp+1E0h+var_17C], 430038h
0x180056b3a  mov     [rbp+1E0h+var_178], 2D0045h
0x180056b41  mov     [rbp+1E0h+var_174], 390034h
0x180056b48  mov     [rbp+1E0h+var_170], 330034h
0x180056b4f  mov     [rbp+1E0h+var_16C], 38002Dh
0x180056b56  mov     [rbp+1E0h+var_168], 440031h
0x180056b5d  mov     [rbp+1E0h+var_164], 2D0046h
0x180056b64  mov     [rbp+1E0h+var_160], 390038h
0x180056b6e  mov     [rbp+1E0h+var_15C], 310038h
0x180056b78  mov     [rbp+1E0h+var_158], 450037h
0x180056b82  mov     [rbp+1E0h+var_154], 440038h
0x180056b8c  mov     [rbp+1E0h+var_150], 330032h
0x180056b96  mov     [rbp+1E0h+var_14C], 440046h
0x180056ba0  mov     [rbp+1E0h+var_148], 5C007Dh
0x180056baa  mov     [rbp+1E0h+var_144], 750043h
0x180056bb4  mov     [rbp+1E0h+var_140], 740073h
0x180056bbe  mov     [rbp+1E0h+var_13C], 6D006Fh
0x180056bc8  mov     [rbp+1E0h+var_138], 640041h
0x180056bd2  mov     [rbp+1E0h+var_134], 430062h
0x180056bdc  mov     [rbp+1E0h+var_130], 6E006Fh
0x180056be6  mov     [rbp+1E0h+var_12C], 690066h
0x180056bf0  mov     [rbp+1E0h+var_128], 750067h
0x180056bfa  mov     [rbp+1E0h+var_124], 610072h
0x180056c04  mov     [rbp+1E0h+var_120], 690074h
0x180056c0e  mov     [rbp+1E0h+var_11C], 6E006Fh
0x180056c18  xor     eax, eax
0x180056c1a  mov     [rbp+1E0h+var_118], ax
0x180056c21  mov     dword ptr [rbp+1E0h+Format], 640041h
0x180056c28  mov     [rbp+1E0h+var_23C], 430062h
0x180056c2f  mov     [rbp+1E0h+var_238], 720075h
0x180056c36  mov     [rbp+1E0h+var_234], 650076h
0x180056c3d  mov     [rbp+1E0h+var_230], 300025h
0x180056c44  mov     [rbp+1E0h+var_22C], 640033h
0x180056c4b  xor     r14d, r14d
0x180056c4e  mov     [rbp+1E0h+var_228], r14w
0x180056c53  mov     [rsp+2E0h+hKey], r14
0x180056c58  mov     [rsp+2E0h+cbData], r14d
0x180056c5d  mov     [rsp+2E0h+var_2A0], r14d
0x180056c62  mov     [rsp+2E0h+var_29C], r14d
0x180056c67  mov     [rsp+2E0h+var_28C], r14d
0x180056c6c  mov     [rsp+2E0h+var_290], r14d
0x180056c71  lea     rax, [rsp+2E0h+hKey]
0x180056c76  mov     [rsp+2E0h+var_270], rax
0x180056c7b  mov     [rsp+2E0h+var_268], r14
0x180056c80  mov     [rbp+1E0h+var_260], 1
0x180056c84  lea     rax, [rsp+2E0h+var_268]
0x180056c89  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180056c8e  mov     r9d, 20019h; samDesired
0x180056c94  xor     r8d, r8d; ulOptions
0x180056c97  lea     rdx, [rbp+1E0h+SubKey]; lpSubKey
0x180056c9b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180056ca2  call    cs:__imp_RegOpenKeyExW
0x180056ca8  mov     ebx, eax
0x180056caa  lea     rcx, [rsp+2E0h+var_270]
0x180056caf  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180056cb4  test    ebx, ebx
0x180056cb6  jnz     loc_180056E1F
0x180056cbc  mov     ebx, r14d
0x180056cbf  mov     r15d, 80h
0x180056cc5  lea     r12d, [r14+20h]
0x180056cc9  mov     r9d, ebx
0x180056ccc  lea     r8, [rbp+1E0h+Format]; Format
0x180056cd0  mov     rdx, r12; BufferCount
0x180056cd3  lea     rcx, [rbp+1E0h+Buffer]; Buffer
0x180056cda  call    swprintf_s
0x180056cdf  mov     [rsp+2E0h+cbData], r15d
0x180056ce4  lea     rax, [rsp+2E0h+cbData]
0x180056ce9  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x180056cee  lea     rax, [rbp+1E0h+Data]
0x180056cf5  mov     [rsp+2E0h+phkResult], rax; lpData
0x180056cfa  xor     r9d, r9d; lpType
0x180056cfd  xor     r8d, r8d; lpReserved
0x180056d00  lea     rdx, [rbp+1E0h+Buffer]; lpValueName
0x180056d07  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180056d0c  call    cs:__imp_RegQueryValueExW
0x180056d12  test    eax, eax
0x180056d14  jnz     short loc_180056D20
0x180056d16  inc     ebx
0x180056d18  cmp     ebx, 200h
0x180056d1e  jb      short loc_180056CC9
0x180056d20  cmp     ebx, 2
0x180056d23  jb      loc_180056E1F
0x180056d29  lea     rcx, [rsp+2E0h+var_288]
0x180056d2e  call    ??0?$vector@UMilliLuxToPercentageMapping@Foundation@DisplayEnhancement@Windows@Microsoft@@V?$allocator@UMilliLuxToPercentageMapping@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToPercentageMapping>::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToPercentageMapping>(void)
0x180056d33  nop
0x180056d34  mov     edi, r14d
0x180056d37  cmp     edi, ebx
0x180056d39  jnb     loc_180056E4E
0x180056d3f  mov     r9d, edi
0x180056d42  lea     r8, [rbp+1E0h+Format]; Format
0x180056d46  mov     rdx, r12; BufferCount
0x180056d49  lea     rcx, [rbp+1E0h+Buffer]; Buffer
0x180056d50  call    swprintf_s
0x180056d55  mov     r8, r15; Size
0x180056d58  xor     edx, edx; Val
0x180056d5a  lea     rcx, [rbp+1E0h+Data]; void *
0x180056d61  call    memset_0
0x180056d66  mov     [rsp+2E0h+cbData], r15d
0x180056d6b  lea     rax, [rsp+2E0h+cbData]
0x180056d70  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x180056d75  lea     rax, [rbp+1E0h+Data]
0x180056d7c  mov     [rsp+2E0h+phkResult], rax; lpData
0x180056d81  xor     r9d, r9d; lpType
0x180056d84  xor     r8d, r8d; lpReserved
0x180056d87  lea     rdx, [rbp+1E0h+Buffer]; lpValueName
0x180056d8e  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180056d93  call    cs:__imp_RegQueryValueExW
0x180056d99  test    eax, eax
0x180056d9b  jnz     short loc_180056E14
0x180056d9d  lea     rax, [rsp+2E0h+var_290]
0x180056da2  mov     [rsp+2E0h+lpcbData], rax
0x180056da7  lea     rax, [rsp+2E0h+var_28C]
0x180056dac  mov     [rsp+2E0h+phkResult], rax
0x180056db1  lea     r9, [rsp+2E0h+var_29C]
0x180056db6  lea     r8, [rsp+2E0h+var_2A0]
0x180056dbb  lea     rdx, aDDDD; "%d:%d:%d:%d"
0x180056dc2  lea     rcx, [rbp+1E0h+Data]; Buffer
0x180056dc9  call    swscanf_s
0x180056dce  imul    eax, [rsp+2E0h+var_2A0], 3E8h
0x180056dd6  mov     dword ptr [rsp+2E0h+var_298], eax
0x180056dda  mov     al, byte ptr [rsp+2E0h+var_29C]
0x180056dde  mov     byte ptr [rsp+2E0h+var_298+4], al
0x180056de2  mov     rdx, [rsp+2E0h+var_280]
0x180056de7  cmp     rdx, [rsp+2E0h+var_278]
0x180056dec  jz      short loc_180056DFE
0x180056dee  mov     rax, [rsp+2E0h+var_298]
0x180056df3  mov     [rdx], rax
0x180056df6  add     [rsp+2E0h+var_280], 8
0x180056dfc  jmp     short loc_180056E0D
0x180056dfe  lea     r8, [rsp+2E0h+var_298]
0x180056e03  lea     rcx, [rsp+2E0h+var_288]
0x180056e08  call    ??$_Emplace_reallocate@UMilliLuxToMilliNitsMapping@Foundation@DisplayEnhancement@Windows@Microsoft@@@?$vector@UMilliLuxToMilliNitsMapping@Foundation@DisplayEnhancement@Windows@Microsoft@@V?$allocator@UMilliLuxToMilliNitsMapping@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@AEAAPEAUMilliLuxToMilliNitsMapping@Foundation@DisplayEnhancement@Windows@Microsoft@@QEAU23456@$$QEAU23456@@Z; std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToMilliNitsMapping>::_Emplace_reallocate<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToMilliNitsMapping>(Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToMilliNitsMapping * const,Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToMilliNitsMapping &&)
0x180056e0d  inc     edi
0x180056e0f  jmp     loc_180056D37
0x180056e14  lea     rcx, [rsp+2E0h+var_288]
0x180056e19  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAXV?$shared_ptr@VClientContextHandle@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::ClientContextHandle>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::ClientContextHandle>>>>>>>(void)
0x180056e1e  nop
0x180056e1f  lea     rcx, [rsp+2E0h+hKey]
0x180056e24  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180056e29  xor     al, al
0x180056e2b  mov     rcx, [rbp+1E0h+var_50]
0x180056e32  xor     rcx, rsp; StackCookie
0x180056e35  call    __security_check_cookie
0x180056e3a  add     rsp, 2A8h
0x180056e41  pop     r15
0x180056e43  pop     r14
0x180056e45  pop     r13
0x180056e47  pop     r12
0x180056e49  pop     rdi
0x180056e4a  pop     rsi
0x180056e4b  pop     rbx
0x180056e4c  pop     rbp
0x180056e4d  retn
0x180056e4e  lea     rdx, [rsp+2E0h+var_288]
0x180056e53  lea     rcx, [rsp+2E0h+var_270]
0x180056e58  call    ??0?$vector@UMilliLuxToMilliNitsMapping@Foundation@DisplayEnhancement@Windows@Microsoft@@V?$allocator@UMilliLuxToMilliNitsMapping@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToMilliNitsMapping>::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToMilliNitsMapping>(std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToMilliNitsMapping> const &)
0x180056e5d  mov     rdx, rax
0x180056e60  lea     rcx, [rbp+1E0h+var_258]
0x180056e64  call    ??0MilliLuxToPercentageCurve@Foundation@DisplayEnhancement@Windows@Microsoft@@QEAA@V?$vector@UMilliLuxToPercentageMapping@Foundation@DisplayEnhancement@Windows@Microsoft@@V?$allocator@UMilliLuxToPercentageMapping@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@@Z; Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToPercentageCurve::MilliLuxToPercentageCurve(std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToPercentageMapping>)
0x180056e69  mov     rbx, rax
0x180056e6c  cmp     rsi, rax
0x180056e6f  jz      short loc_180056E9A
0x180056e71  mov     rcx, rsi
0x180056e74  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAXV?$shared_ptr@VClientContextHandle@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::ClientContextHandle>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::ClientContextHandle>>>>>>>(void)
0x180056e79  mov     rax, [rbx]
0x180056e7c  mov     [rsi], rax
0x180056e7f  mov     rax, [rbx+8]
0x180056e83  mov     [rsi+8], rax
0x180056e87  mov     rcx, [rbx+10h]
0x180056e8b  mov     [rsi+10h], rcx
0x180056e8f  mov     [rbx], r14
0x180056e92  mov     [rbx+8], r14
0x180056e96  mov     [rbx+10h], r14
0x180056e9a  lea     rcx, [rbp+1E0h+var_258]
0x180056e9e  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAXV?$shared_ptr@VClientContextHandle@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::ClientContextHandle>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::ClientContextHandle>>>>>>>(void)
0x180056ea3  nop
0x180056ea4  lea     rcx, [rsp+2E0h+var_288]
0x180056ea9  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAXV?$shared_ptr@VClientContextHandle@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::ClientContextHandle>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::ClientContextHandle>>>>>>>(void)
0x180056eae  nop
0x180056eaf  lea     rcx, [rsp+2E0h+hKey]
0x180056eb4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180056eb9  mov     al, 1
0x180056ebb  jmp     loc_180056E2B
```
