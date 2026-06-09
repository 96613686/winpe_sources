# DdcDeviceInfoHelper::GetDisplayInfoValues(IDxDiagContainer *,std::vector<std::unique_ptr<DisplayInfo,std::default_delete<DisplayInfo>>,std::allocator<std::unique_ptr<DisplayInfo,std::default_delete<DisplayInfo>>>> &)

- ea: `0x180018c8c`
- end: `0x1800190f5`
- name: `?GetDisplayInfoValues@DdcDeviceInfoHelper@@CAJPEAUIDxDiagContainer@@AEAV?$vector@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@@2@@std@@@Z`
- size: `1129`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18001488c`

## callees

- `0x1800024c0`
- `0x180002fc0`
- `0x1800032b8`
- `0x180004060`
- `0x180004db8`
- `0x1800050b8`
- `0x180014038`
- `0x18001416c`
- `0x180014194`
- `0x180014340`
- `0x1800144c8`
- `0x1800145e0`
- `0x1800146d8`
- `0x180014744`
- `0x180018c8c`
- `0x18001a330`
- `0x18001af8c`
- `0x18002a010`

## string_xrefs

- `0x18001905a`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x180019098`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`

## pseudocode

```c
__int64 __fastcall DdcDeviceInfoHelper::GetDisplayInfoValues(__int64 a1, __int64 *a2)
{
  __int64 (__fastcall *v4)(__int64, const wchar_t *, __int64 *); // rbx
  int v5; // edx
  int v6; // ecx
  int StringValue; // edi
  int v8; // edx
  int v9; // ecx
  unsigned int i; // r14d
  unsigned __int16 *v11; // rax
  int v12; // edx
  int v13; // ecx
  unsigned __int16 *v14; // rsi
  int v15; // edx
  int v16; // ecx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _BYTE *, struct IDxDiagContainer **); // rbx
  int v19; // edx
  int v20; // ecx
  int v21; // r9d
  int v22; // edx
  int v23; // ecx
  int v24; // r9d
  int v25; // edx
  int v26; // ecx
  int v27; // r9d
  int v28; // edx
  int v29; // ecx
  int v30; // r9d
  int v31; // edx
  int v32; // ecx
  __int64 v33; // rbx
  __int64 v34; // rcx
  char v35; // al
  __int64 v36; // rcx
  bool v37; // bl
  __int64 v38; // rdx
  unsigned __int16 *v40; // [rsp+30h] [rbp-D0h] BYREF
  struct IDxDiagContainer *v41; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v42; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v43; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v44; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v45[16]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v46[16]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v47; // [rsp+80h] [rbp-80h]
  _BYTE v48[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v49[512]; // [rsp+B0h] [rbp-50h] BYREF

  v43 = 0;
  v42 = 0;
  v41 = 0;
  v44 = 0;
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Alloc_sentinel_and_proxy(&v44);
  v4 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)a1 + 40LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
  StringValue = v4(a1, L"DxDiag_DisplayDevices", &v42);
  if ( StringValue >= 0 )
  {
    StringValue = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v42 + 24LL))(v42, &v43);
    if ( StringValue >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= v43 )
          goto LABEL_41;
        v11 = (unsigned __int16 *)operator new(0x1860u, (const struct std::nothrow_t *)&std::nothrow);
        v14 = v11;
        if ( !v11 )
          break;
        memset_0(v11, 0, 0x1860u);
        v40 = v14;
        StringValue = (*(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *, __int64))(*(_QWORD *)v42 + 32LL))(
                        v42,
                        i,
                        v49,
                        256);
        if ( StringValue < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v16,
              v15,
              StringValue,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
              35,
              "CHR(pContainer->EnumChildContainerNames(nItem, wszContainer, 256))");
          goto LABEL_38;
        }
        v17 = v42;
        v18 = *(__int64 (__fastcall **)(__int64, _BYTE *, struct IDxDiagContainer **))(*(_QWORD *)v42 + 40LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
        StringValue = v18(v17, v49, &v41);
        if ( StringValue < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v20,
              v19,
              StringValue,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
              36,
              "CHR(pContainer->GetChildContainer(wszContainer, &pObject))");
          goto LABEL_38;
        }
        if ( !v41 )
        {
          StringValue = -2147467259;
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              0,
              v19,
              -2147467259,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
              37,
              "CBR(pObject != nullptr)");
          goto LABEL_38;
        }
        StringValue = GetStringValue(v41, L"szDeviceIdentifier", v14 + 2860, v21);
        if ( StringValue < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v23,
              v22,
              StringValue,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
              39,
              "CHR(GetStringValue(pObject.Get(), L\"szDeviceIdentifier\", pDisplayInfo->m_szDeviceIdentifier, sizeof(pDis"
              "playInfo->m_szDeviceIdentifier)/sizeof(TCHAR)))");
          goto LABEL_38;
        }
        StringValue = GetStringValue(v41, L"szManufacturer", v14, v24);
        if ( StringValue < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v26,
              v25,
              StringValue,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
              40,
              "CHR(GetStringValue(pObject.Get(), L\"szManufacturer\", pDisplayInfo->m_szDeviceName, sizeof(pDisplayInfo->"
              "m_szDeviceName)/sizeof(TCHAR)))");
          goto LABEL_38;
        }
        StringValue = GetStringValue(v41, L"szDescription", v14 + 260, v27);
        if ( StringValue < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v29,
              v28,
              StringValue,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
              41,
              "CHR(GetStringValue(pObject.Get(), L\"szDescription\", pDisplayInfo->m_szDescription, sizeof(pDisplayInfo->"
              "m_szDescription)/sizeof(TCHAR)))");
          goto LABEL_38;
        }
        StringValue = GetStringValue(v41, L"szDisplayMemoryEnglish", v14 + 1040, v30);
        if ( StringValue < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v32,
              v31,
              StringValue,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
              42,
              "CHR(GetStringValue(pObject.Get(), L\"szDisplayMemoryEnglish\", pDisplayInfo->m_szDisplayMemoryEnglish, siz"
              "eof(pDisplayInfo->m_szDisplayMemoryEnglish)/sizeof(TCHAR)))");
LABEL_38:
          std::unique_ptr<DisplayInfo>::~unique_ptr<DisplayInfo>((void **)&v40);
          goto LABEL_41;
        }
        v33 = std::wstring::wstring(v48, v14 + 2860);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
          &v44,
          v46,
          v33);
        v35 = std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Lower_bound_duplicate<std::wstring>(
                v34,
                v47,
                v33);
        v36 = v44;
        if ( v35 )
          v36 = v47;
        v37 = v36 == (_QWORD)v44;
        std::wstring::_Tidy_deallocate((__int64)v48);
        if ( v37 )
        {
          std::wstring::wstring(v46, v14 + 2860);
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
            &v44,
            v45,
            v46);
          std::wstring::_Tidy_deallocate((__int64)v46);
          v38 = a2[1];
          if ( v38 == a2[2] )
            std::vector<std::unique_ptr<DisplayInfo>>::_Emplace_reallocate<std::unique_ptr<DisplayInfo>>(
              a2,
              v38,
              (__int64 *)&v40);
          else
            std::vector<std::unique_ptr<DisplayInfo>>::_Emplace_back_with_unused_capacity<std::unique_ptr<DisplayInfo>>(
              (__int64)a2,
              (__int64 *)&v40);
        }
        std::unique_ptr<DisplayInfo>::~unique_ptr<DisplayInfo>((void **)&v40);
      }
      StringValue = -2147024882;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v13,
          v12,
          -2147024882,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          32,
          "CPR(pInfo)");
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v9,
        v8,
        StringValue,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        27,
        "CHR(pContainer->GetNumberOfChildContainers(&nInstanceCount))");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v6,
      v5,
      StringValue,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
      26,
      "CHR(pDxDiagRoot->GetChildContainer( L\"DxDiag_DisplayDevices\", &pContainer))");
  }
LABEL_41:
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v44);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
  return (unsigned int)StringValue;
}

```

## disassembly

```asm
0x180018c8c  mov     [rsp-8+arg_10], rbx
0x180018c91  mov     [rsp-8+arg_18], rsi
0x180018c96  push    rbp
0x180018c97  push    rdi
0x180018c98  push    r12
0x180018c9a  push    r14
0x180018c9c  push    r15
0x180018c9e  lea     rbp, [rsp-1C0h]
0x180018ca6  sub     rsp, 2C0h
0x180018cad  mov     rax, cs:__security_cookie
0x180018cb4  xor     rax, rsp
0x180018cb7  mov     [rbp+1E0h+var_30], rax
0x180018cbe  mov     r15, rdx
0x180018cc1  mov     rdi, rcx
0x180018cc4  mov     [rsp+2E0h+var_298], 0
0x180018ccc  mov     [rsp+2E0h+var_2A0], 0
0x180018cd5  mov     [rsp+2E0h+var_2A8], 0
0x180018cde  xorps   xmm0, xmm0
0x180018ce1  movdqu  [rsp+2E0h+var_290], xmm0
0x180018ce7  lea     rcx, [rsp+2E0h+var_290]
0x180018cec  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Alloc_sentinel_and_proxy(void)
0x180018cf1  nop
0x180018cf2  mov     rax, [rdi]
0x180018cf5  mov     rbx, [rax+28h]
0x180018cf9  lea     rcx, [rsp+2E0h+var_2A0]
0x180018cfe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018d03  lea     r8, [rsp+2E0h+var_2A0]
0x180018d08  lea     rdx, aDxdiagDisplayd; "DxDiag_DisplayDevices"
0x180018d0f  mov     rcx, rdi
0x180018d12  mov     rax, rbx
0x180018d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d1a  mov     edi, eax
0x180018d1c  test    eax, eax
0x180018d1e  jns     short loc_180018D46
0x180018d20  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180018d27  jz      loc_1800190A8
0x180018d2d  lea     rax, aChrPdxdiagroot; "CHR(pDxDiagRoot->GetChildContainer( L\""...
0x180018d34  mov     [rsp+2E0h+var_2B8], rax
0x180018d39  mov     [rsp+2E0h+var_2C0], 71Ah
0x180018d41  jmp     loc_180019098
0x180018d46  mov     rcx, [rsp+2E0h+var_2A0]
0x180018d4b  mov     rax, [rcx]
0x180018d4e  lea     rdx, [rsp+2E0h+var_298]
0x180018d53  mov     rax, [rax+18h]
0x180018d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d5c  mov     edi, eax
0x180018d5e  test    eax, eax
0x180018d60  jns     short loc_180018D88
0x180018d62  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180018d69  jz      loc_1800190A8
0x180018d6f  lea     rax, aChrPcontainerG; "CHR(pContainer->GetNumberOfChildContain"...
0x180018d76  mov     [rsp+2E0h+var_2B8], rax
0x180018d7b  mov     [rsp+2E0h+var_2C0], 71Bh
0x180018d83  jmp     loc_180019098
0x180018d88  xor     r14d, r14d
0x180018d8b  cmp     r14d, [rsp+2E0h+var_298]
0x180018d90  jnb     loc_1800190A8
0x180018d96  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018d9d  mov     ecx, 1860h; unsigned __int64
0x180018da2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180018da7  mov     rsi, rax
0x180018daa  test    rax, rax
0x180018dad  jz      loc_180019076
0x180018db3  xor     edx, edx; Val
0x180018db5  mov     r8d, 1860h; Size
0x180018dbb  mov     rcx, rax; void *
0x180018dbe  call    memset_0
0x180018dc3  mov     [rsp+2E0h+var_2B0], rsi
0x180018dc8  mov     rcx, [rsp+2E0h+var_2A0]
0x180018dcd  mov     rdx, [rcx]
0x180018dd0  mov     rax, [rdx+20h]
0x180018dd4  mov     r9d, 100h
0x180018dda  lea     r8, [rbp+1E0h+var_230]
0x180018dde  mov     edx, r14d
0x180018de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018de6  mov     edi, eax
0x180018de8  test    eax, eax
0x180018dea  js      loc_18001903D
0x180018df0  mov     rdi, [rsp+2E0h+var_2A0]
0x180018df5  mov     rax, [rdi]
0x180018df8  mov     rbx, [rax+28h]
0x180018dfc  lea     rcx, [rsp+2E0h+var_2A8]
0x180018e01  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018e06  lea     r8, [rsp+2E0h+var_2A8]
0x180018e0b  lea     rdx, [rbp+1E0h+var_230]
0x180018e0f  mov     rcx, rdi
0x180018e12  mov     rax, rbx
0x180018e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e1a  mov     edi, eax
0x180018e1c  test    eax, eax
0x180018e1e  js      loc_18001901E
0x180018e24  mov     rcx, [rsp+2E0h+var_2A8]; struct IDxDiagContainer *
0x180018e29  test    rcx, rcx
0x180018e2c  jz      loc_180018FFA
0x180018e32  lea     r12, [rsi+1658h]
0x180018e39  mov     r8, r12; unsigned __int16 *
0x180018e3c  lea     rdx, aSzdeviceidenti; "szDeviceIdentifier"
0x180018e43  call    ?GetStringValue@@YAJPEAUIDxDiagContainer@@PEAG1H@Z; GetStringValue(IDxDiagContainer *,ushort *,ushort *,int)
0x180018e48  mov     edi, eax
0x180018e4a  test    eax, eax
0x180018e4c  js      loc_180018FD7
0x180018e52  mov     r8, rsi; unsigned __int16 *
0x180018e55  lea     rdx, aSzmanufacturer; "szManufacturer"
0x180018e5c  mov     rcx, [rsp+2E0h+var_2A8]; struct IDxDiagContainer *
0x180018e61  call    ?GetStringValue@@YAJPEAUIDxDiagContainer@@PEAG1H@Z; GetStringValue(IDxDiagContainer *,ushort *,ushort *,int)
0x180018e66  mov     edi, eax
0x180018e68  test    eax, eax
0x180018e6a  js      loc_180018FB1
0x180018e70  lea     r8, [rsi+208h]; unsigned __int16 *
0x180018e77  lea     rdx, aSzdescription; "szDescription"
0x180018e7e  mov     rcx, [rsp+2E0h+var_2A8]; struct IDxDiagContainer *
0x180018e83  call    ?GetStringValue@@YAJPEAUIDxDiagContainer@@PEAG1H@Z; GetStringValue(IDxDiagContainer *,ushort *,ushort *,int)
0x180018e88  mov     edi, eax
0x180018e8a  test    eax, eax
0x180018e8c  js      loc_180018F8B
0x180018e92  lea     r8, [rsi+820h]; unsigned __int16 *
0x180018e99  lea     rdx, aSzdisplaymemor; "szDisplayMemoryEnglish"
0x180018ea0  mov     rcx, [rsp+2E0h+var_2A8]; struct IDxDiagContainer *
0x180018ea5  call    ?GetStringValue@@YAJPEAUIDxDiagContainer@@PEAG1H@Z; GetStringValue(IDxDiagContainer *,ushort *,ushort *,int)
0x180018eaa  mov     edi, eax
0x180018eac  test    eax, eax
0x180018eae  js      loc_180018F65
0x180018eb4  mov     rdx, r12
0x180018eb7  lea     rcx, [rbp+1E0h+var_250]
0x180018ebb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180018ec0  mov     rbx, rax
0x180018ec3  mov     r8, rax
0x180018ec6  lea     rdx, [rsp+2E0h+var_270]
0x180018ecb  lea     rcx, [rsp+2E0h+var_290]
0x180018ed0  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x180018ed5  mov     r8, rbx
0x180018ed8  mov     rdx, [rbp+1E0h+var_260]
0x180018edc  call    ??$_Lower_bound_duplicate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::wstring,void *> * const,std::wstring const &)
0x180018ee1  mov     rcx, qword ptr [rsp+2E0h+var_290]
0x180018ee6  test    al, al
0x180018ee8  cmovnz  rcx, [rbp+1E0h+var_260]
0x180018eed  cmp     rcx, qword ptr [rsp+2E0h+var_290]
0x180018ef2  setz    bl
0x180018ef5  lea     rcx, [rbp+1E0h+var_250]
0x180018ef9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018efe  test    bl, bl
0x180018f00  jz      short loc_180018F53
0x180018f02  mov     rdx, r12
0x180018f05  lea     rcx, [rsp+2E0h+var_270]
0x180018f0a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180018f0f  nop
0x180018f10  lea     r8, [rsp+2E0h+var_270]
0x180018f15  lea     rdx, [rsp+2E0h+var_280]
0x180018f1a  lea     rcx, [rsp+2E0h+var_290]
0x180018f1f  call    ??$_Emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(std::wstring &&)
0x180018f24  nop
0x180018f25  lea     rcx, [rsp+2E0h+var_270]
0x180018f2a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018f2f  mov     rdx, [r15+8]
0x180018f33  mov     rcx, r15
0x180018f36  cmp     rdx, [r15+10h]
0x180018f3a  jz      short loc_180018F48
0x180018f3c  lea     rdx, [rsp+2E0h+var_2B0]
0x180018f41  call    ??$_Emplace_back_with_unused_capacity@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@@?$vector@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@@2@@std@@AEAAAEAV?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@1@$$QEAV21@@Z; std::vector<std::unique_ptr<DisplayInfo>>::_Emplace_back_with_unused_capacity<std::unique_ptr<DisplayInfo>>(std::unique_ptr<DisplayInfo> &&)
0x180018f46  jmp     short loc_180018F53
0x180018f48  lea     r8, [rsp+2E0h+var_2B0]
0x180018f4d  call    ??$_Emplace_reallocate@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@@?$vector@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<DisplayInfo>>::_Emplace_reallocate<std::unique_ptr<DisplayInfo>>(std::unique_ptr<DisplayInfo> * const,std::unique_ptr<DisplayInfo> &&)
0x180018f52  nop
0x180018f53  lea     rcx, [rsp+2E0h+var_2B0]
0x180018f58  call    ??1?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@QEAA@XZ; std::unique_ptr<DisplayInfo>::~unique_ptr<DisplayInfo>(void)
0x180018f5d  inc     r14d
0x180018f60  jmp     loc_180018D8B
0x180018f65  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180018f6c  jz      loc_18001906A
0x180018f72  lea     rax, aChrGetstringva_0; "CHR(GetStringValue(pObject.Get(), L\"sz"...
0x180018f79  mov     [rsp+2E0h+var_2B8], rax
0x180018f7e  mov     [rsp+2E0h+var_2C0], 72Ah
0x180018f86  jmp     loc_18001905A
0x180018f8b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180018f92  jz      loc_18001906A
0x180018f98  lea     rax, aChrGetstringva_1; "CHR(GetStringValue(pObject.Get(), L\"sz"...
0x180018f9f  mov     [rsp+2E0h+var_2B8], rax
0x180018fa4  mov     [rsp+2E0h+var_2C0], 729h
0x180018fac  jmp     loc_18001905A
0x180018fb1  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180018fb8  jz      loc_18001906A
0x180018fbe  lea     rax, aChrGetstringva; "CHR(GetStringValue(pObject.Get(), L\"sz"...
0x180018fc5  mov     [rsp+2E0h+var_2B8], rax
0x180018fca  mov     [rsp+2E0h+var_2C0], 728h
0x180018fd2  jmp     loc_18001905A
0x180018fd7  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180018fde  jz      loc_18001906A
0x180018fe4  lea     rax, aChrGetstringva_2; "CHR(GetStringValue(pObject.Get(), L\"sz"...
0x180018feb  mov     [rsp+2E0h+var_2B8], rax
0x180018ff0  mov     [rsp+2E0h+var_2C0], 727h
0x180018ff8  jmp     short loc_18001905A
0x180018ffa  mov     edi, 80004005h
0x180018fff  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019006  jz      short loc_18001906A
0x180019008  lea     rax, aCbrPobjectNull; "CBR(pObject != nullptr)"
0x18001900f  mov     [rsp+2E0h+var_2B8], rax
0x180019014  mov     [rsp+2E0h+var_2C0], 725h
0x18001901c  jmp     short loc_18001905A
0x18001901e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019025  jz      short loc_18001906A
0x180019027  lea     rax, aChrPcontainerG_0; "CHR(pContainer->GetChildContainer(wszCo"...
0x18001902e  mov     [rsp+2E0h+var_2B8], rax
0x180019033  mov     [rsp+2E0h+var_2C0], 724h
0x18001903b  jmp     short loc_18001905A
0x18001903d  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019044  jz      short loc_18001906A
0x180019046  lea     rax, aChrPcontainerE; "CHR(pContainer->EnumChildContainerNames"...
0x18001904d  mov     [rsp+2E0h+var_2B8], rax
0x180019052  mov     [rsp+2E0h+var_2C0], 723h
0x18001905a  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180019061  mov     r8d, edi
0x180019064  call    McTemplateU0dsqs_EventWriteTransfer
0x180019069  nop
0x18001906a  lea     rcx, [rsp+2E0h+var_2B0]
0x18001906f  call    ??1?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@QEAA@XZ; std::unique_ptr<DisplayInfo>::~unique_ptr<DisplayInfo>(void)
0x180019074  jmp     short loc_1800190A8
0x180019076  mov     edi, 8007000Eh
0x18001907b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019082  jz      short loc_1800190A8
0x180019084  lea     rax, aCprPinfo; "CPR(pInfo)"
0x18001908b  mov     [rsp+2E0h+var_2B8], rax
0x180019090  mov     [rsp+2E0h+var_2C0], 720h
0x180019098  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001909f  mov     r8d, edi
0x1800190a2  call    McTemplateU0dsqs_EventWriteTransfer
0x1800190a7  nop
0x1800190a8  lea     rcx, [rsp+2E0h+var_290]
0x1800190ad  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x1800190b2  nop
0x1800190b3  lea     rcx, [rsp+2E0h+var_2A8]
0x1800190b8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800190bd  nop
0x1800190be  lea     rcx, [rsp+2E0h+var_2A0]
0x1800190c3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800190c8  mov     eax, edi
0x1800190ca  mov     rcx, [rbp+1E0h+var_30]
0x1800190d1  xor     rcx, rsp; StackCookie
0x1800190d4  call    __security_check_cookie
0x1800190d9  lea     r11, [rsp+2E0h+var_20]
0x1800190e1  mov     rbx, [r11+40h]
0x1800190e5  mov     rsi, [r11+48h]
0x1800190e9  mov     rsp, r11
0x1800190ec  pop     r15
0x1800190ee  pop     r14
0x1800190f0  pop     r12
0x1800190f2  pop     rdi
0x1800190f3  pop     rbp
0x1800190f4  retn
```
