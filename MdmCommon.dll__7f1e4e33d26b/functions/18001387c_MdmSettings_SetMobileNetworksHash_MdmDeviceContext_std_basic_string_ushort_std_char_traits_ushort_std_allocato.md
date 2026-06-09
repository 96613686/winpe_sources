# MdmSettings::SetMobileNetworksHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001387c`
- end: `0x1800139a5`
- name: `?SetMobileNetworksHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `297`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003010`
- `0x18001142c`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x180006548`
- `0x1800129b0`
- `0x18001387c`
- `0x18001d248`

## string_xrefs

- `0x18001396f`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x18001391f`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x18001395b`: `CHR(MdmRegistry::SetStringValue( hKey, wszKey, c_pszMobileNetworksHash, pszValue))`

## pseudocode

```c
__int64 __fastcall MdmSettings::SetMobileNetworksHash(int a1, __int64 a2)
{
  int v4; // edx
  int v5; // ecx
  int v6; // ebx
  int MdmCommonSettingValuesPersistedLocation; // ebx
  __int64 v8; // rdi
  int v9; // edx
  int v10; // ecx
  int v11; // edx
  int v12; // ecx
  unsigned int v14[4]; // [rsp+30h] [rbp-238h] BYREF
  unsigned __int16 v15[264]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(v15, 0, 0x208u);
  v14[0] = 260;
  v6 = a1 - 1;
  if ( v6 )
  {
    if ( v6 != 1 )
    {
      MdmCommonSettingValuesPersistedLocation = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v5,
          v4,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
          253,
          (__int64)"CBR(hKey != nullptr)");
      return (unsigned int)MdmCommonSettingValuesPersistedLocation;
    }
    v8 = -2147483646;
  }
  else
  {
    v8 = -2147483647;
  }
  MdmCommonSettingValuesPersistedLocation = GetMdmCommonSettingValuesPersistedLocation(v15, v14);
  if ( MdmCommonSettingValuesPersistedLocation >= 0 )
  {
    MdmCommonSettingValuesPersistedLocation = MdmRegistry::SetStringValue(v8, v15, L"MobileNetworksHash", a2);
    if ( MdmCommonSettingValuesPersistedLocation < 0
      && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v12,
        v11,
        MdmCommonSettingValuesPersistedLocation,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
        5,
        (__int64)"CHR(MdmRegistry::SetStringValue( hKey, wszKey, c_pszMobileNetworksHash, pszValue))");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v10,
      v9,
      MdmCommonSettingValuesPersistedLocation,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
      255,
      (__int64)"CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))");
  }
  return (unsigned int)MdmCommonSettingValuesPersistedLocation;
}

```

## disassembly

```asm
0x18001387c  mov     [rsp+arg_0], rbx
0x180013881  mov     [rsp+arg_10], rsi
0x180013886  push    rdi
0x180013887  sub     rsp, 260h
0x18001388e  mov     rax, cs:__security_cookie
0x180013895  xor     rax, rsp
0x180013898  mov     [rsp+268h+var_18], rax
0x1800138a0  mov     rsi, rdx
0x1800138a3  mov     ebx, ecx
0x1800138a5  xor     edx, edx; Val
0x1800138a7  lea     rcx, [rsp+268h+var_228]; void *
0x1800138ac  mov     r8d, 208h; Size
0x1800138b2  call    memset_0
0x1800138b7  mov     [rsp+268h+var_238], 104h
0x1800138bf  sub     ebx, 1
0x1800138c2  jz      short loc_1800138FA
0x1800138c4  cmp     ebx, 1
0x1800138c7  jz      short loc_1800138F1
0x1800138c9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800138d0  mov     ebx, 80070057h
0x1800138d5  jz      loc_18001397E
0x1800138db  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x1800138e2  mov     [rsp+268h+var_240], rax
0x1800138e7  mov     [rsp+268h+var_248], 0FDh
0x1800138ef  jmp     short loc_18001396F
0x1800138f1  mov     rdi, 0FFFFFFFF80000002h
0x1800138f8  jmp     short loc_180013901
0x1800138fa  mov     rdi, 0FFFFFFFF80000001h
0x180013901  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x180013906  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x18001390b  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180013910  mov     ebx, eax
0x180013912  test    eax, eax
0x180013914  jns     short loc_180013935
0x180013916  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001391d  jz      short loc_18001397E
0x18001391f  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180013926  mov     [rsp+268h+var_240], rax
0x18001392b  mov     [rsp+268h+var_248], 0FFh
0x180013933  jmp     short loc_18001396F
0x180013935  mov     r9, rsi
0x180013938  lea     r8, aMobilenetworks; "MobileNetworksHash"
0x18001393f  lea     rdx, [rsp+268h+var_228]
0x180013944  mov     rcx, rdi
0x180013947  call    ?SetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; MdmRegistry::SetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring const &,ulong)
0x18001394c  mov     ebx, eax
0x18001394e  test    eax, eax
0x180013950  jns     short loc_18001397E
0x180013952  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013959  jz      short loc_18001397E
0x18001395b  lea     rax, aChrMdmregistry_20; "CHR(MdmRegistry::SetStringValue( hKey, "...
0x180013962  mov     [rsp+268h+var_240], rax
0x180013967  mov     [rsp+268h+var_248], 105h
0x18001396f  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180013976  mov     r8d, ebx
0x180013979  call    McTemplateU0dsqs_EventWriteTransfer
0x18001397e  mov     eax, ebx
0x180013980  mov     rcx, [rsp+268h+var_18]
0x180013988  xor     rcx, rsp; StackCookie
0x18001398b  call    __security_check_cookie
0x180013990  lea     r11, [rsp+268h+var_8]
0x180013998  mov     rbx, [r11+10h]
0x18001399c  mov     rsi, [r11+20h]
0x1800139a0  mov     rsp, r11
0x1800139a3  pop     rdi
0x1800139a4  retn
```
