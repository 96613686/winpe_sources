# MdmSettings::GetConnectedAccountsHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180012578`
- end: `0x1800126d8`
- name: `?GetConnectedAccountsHash@MdmSettings@@SAJW4MdmDeviceContext@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `352`
- prototype: `__int64 __fastcall(int, _QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800030c0`
- `0x18000c38c`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x180006548`
- `0x180012578`
- `0x1800129b0`
- `0x18001ce60`

## string_xrefs

- `0x1800125e6`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x18001267d`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x18001262d`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x180012669`: `CHR(MdmRegistry::GetStringValue( hKey, wszKey, c_pszConnectedAccountsHash, pszValue))`

## pseudocode

```c
__int64 __fastcall MdmSettings::GetConnectedAccountsHash(int a1, _QWORD *a2)
{
  int v4; // edx
  int v5; // ecx
  int v6; // ebx
  int MdmCommonSettingValuesPersistedLocation; // ebx
  __int64 v8; // rsi
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
          228,
          "CBR(hKey != nullptr)",
          *(_QWORD *)v14);
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
    MdmCommonSettingValuesPersistedLocation = MdmRegistry::GetStringValue((HKEY)v8, v15, L"ConnectedAccountsHash", a2);
    if ( MdmCommonSettingValuesPersistedLocation >= 0 )
      return (unsigned int)MdmCommonSettingValuesPersistedLocation;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v12,
        v11,
        MdmCommonSettingValuesPersistedLocation,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
        236,
        "CHR(MdmRegistry::GetStringValue( hKey, wszKey, c_pszConnectedAccountsHash, pszValue))",
        *(_QWORD *)v14);
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v10,
      v9,
      MdmCommonSettingValuesPersistedLocation,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
      230,
      "CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))",
      *(_QWORD *)v14);
  }
  if ( MdmCommonSettingValuesPersistedLocation == -2147023728 || MdmCommonSettingValuesPersistedLocation == -2147024894 )
  {
    MdmCommonSettingValuesPersistedLocation = 0;
    a2[2] = 0;
    if ( a2[3] > 7u )
      a2 = (_QWORD *)*a2;
    *(_WORD *)a2 = 0;
  }
  return (unsigned int)MdmCommonSettingValuesPersistedLocation;
}

```

## disassembly

```asm
0x180012578  mov     [rsp+arg_0], rbx
0x18001257d  mov     [rsp+arg_10], rsi
0x180012582  push    rdi
0x180012583  sub     rsp, 260h
0x18001258a  mov     rax, cs:__security_cookie
0x180012591  xor     rax, rsp
0x180012594  mov     [rsp+268h+var_18], rax
0x18001259c  mov     rdi, rdx
0x18001259f  mov     ebx, ecx
0x1800125a1  xor     edx, edx; Val
0x1800125a3  lea     rcx, [rsp+268h+var_228]; void *
0x1800125a8  mov     r8d, 208h; Size
0x1800125ae  call    memset_0
0x1800125b3  mov     [rsp+268h+var_238], 104h
0x1800125bb  sub     ebx, 1
0x1800125be  jz      short loc_180012608
0x1800125c0  cmp     ebx, 1
0x1800125c3  jz      short loc_1800125FF
0x1800125c5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800125cc  mov     ebx, 80070057h
0x1800125d1  jz      loc_1800126B1
0x1800125d7  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x1800125de  mov     r8d, ebx
0x1800125e1  mov     [rsp+268h+var_240], rax
0x1800125e6  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800125ed  mov     [rsp+268h+var_248], 1E4h
0x1800125f5  call    McTemplateU0dsqs_EventWriteTransfer
0x1800125fa  jmp     loc_1800126B1
0x1800125ff  mov     rsi, 0FFFFFFFF80000002h
0x180012606  jmp     short loc_18001260F
0x180012608  mov     rsi, 0FFFFFFFF80000001h
0x18001260f  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x180012614  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180012619  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x18001261e  mov     ebx, eax
0x180012620  test    eax, eax
0x180012622  jns     short loc_180012643
0x180012624  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001262b  jz      short loc_18001268C
0x18001262d  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180012634  mov     [rsp+268h+var_240], rax
0x180012639  mov     [rsp+268h+var_248], 1E6h
0x180012641  jmp     short loc_18001267D
0x180012643  mov     r9, rdi
0x180012646  lea     r8, aConnectedaccou_0; "ConnectedAccountsHash"
0x18001264d  lea     rdx, [rsp+268h+var_228]
0x180012652  mov     rcx, rsi
0x180012655  call    ?GetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x18001265a  mov     ebx, eax
0x18001265c  test    eax, eax
0x18001265e  jns     short loc_1800126B1
0x180012660  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012667  jz      short loc_18001268C
0x180012669  lea     rax, aChrMdmregistry_11; "CHR(MdmRegistry::GetStringValue( hKey, "...
0x180012670  mov     [rsp+268h+var_240], rax
0x180012675  mov     [rsp+268h+var_248], 1ECh
0x18001267d  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180012684  mov     r8d, ebx
0x180012687  call    McTemplateU0dsqs_EventWriteTransfer
0x18001268c  cmp     ebx, 80070490h
0x180012692  jz      short loc_18001269C
0x180012694  cmp     ebx, 80070002h
0x18001269a  jnz     short loc_1800126B1
0x18001269c  xor     ebx, ebx
0x18001269e  mov     [rdi+10h], rbx
0x1800126a2  cmp     qword ptr [rdi+18h], 7
0x1800126a7  jbe     short loc_1800126AC
0x1800126a9  mov     rdi, [rdi]
0x1800126ac  xor     eax, eax
0x1800126ae  mov     [rdi], ax
0x1800126b1  mov     eax, ebx
0x1800126b3  mov     rcx, [rsp+268h+var_18]
0x1800126bb  xor     rcx, rsp; StackCookie
0x1800126be  call    __security_check_cookie
0x1800126c3  lea     r11, [rsp+268h+var_8]
0x1800126cb  mov     rbx, [r11+10h]
0x1800126cf  mov     rsi, [r11+20h]
0x1800126d3  mov     rsp, r11
0x1800126d6  pop     rdi
0x1800126d7  retn
```
