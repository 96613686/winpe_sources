# MdmSettings::GetProtectionStateHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800130b4`
- end: `0x180013215`
- name: `?GetProtectionStateHash@MdmSettings@@SAJW4MdmDeviceContext@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `353`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800050a0`
- `0x18000c6e8`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x1800065c0`
- `0x180012d8c`
- `0x1800130b4`
- `0x18001d4f4`

## string_xrefs

- `0x180013122`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x1800131b9`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180013169`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x1800131a5`: `CHR(MdmRegistry::GetStringValue( hKey, wszKey, c_pszProtectionStateHash, pszValue))`

## pseudocode

```c
__int64 __fastcall MdmSettings::GetProtectionStateHash(int a1, _QWORD *a2)
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
          176,
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
    MdmCommonSettingValuesPersistedLocation = MdmRegistry::GetStringValue((HKEY)v8, v15, L"ProtectionStateHash", a2);
    if ( MdmCommonSettingValuesPersistedLocation >= 0 )
      return (unsigned int)MdmCommonSettingValuesPersistedLocation;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v12,
        v11,
        MdmCommonSettingValuesPersistedLocation,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
        184,
        "CHR(MdmRegistry::GetStringValue( hKey, wszKey, c_pszProtectionStateHash, pszValue))",
        *(_QWORD *)v14);
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v10,
      v9,
      MdmCommonSettingValuesPersistedLocation,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
      178,
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
0x1800130b4  mov     [rsp+arg_0], rbx
0x1800130b9  mov     [rsp+arg_10], rsi
0x1800130be  push    rdi
0x1800130bf  sub     rsp, 260h
0x1800130c6  mov     rax, cs:__security_cookie
0x1800130cd  xor     rax, rsp
0x1800130d0  mov     [rsp+268h+var_18], rax
0x1800130d8  mov     rdi, rdx
0x1800130db  mov     ebx, ecx
0x1800130dd  xor     edx, edx; Val
0x1800130df  lea     rcx, [rsp+268h+var_228]; void *
0x1800130e4  mov     r8d, 208h; Size
0x1800130ea  call    memset_0
0x1800130ef  mov     [rsp+268h+var_238], 104h
0x1800130f7  sub     ebx, 1
0x1800130fa  jz      short loc_180013144
0x1800130fc  cmp     ebx, 1
0x1800130ff  jz      short loc_18001313B
0x180013101  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013108  mov     ebx, 80070057h
0x18001310d  jz      loc_1800131ED
0x180013113  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x18001311a  mov     r8d, ebx
0x18001311d  mov     [rsp+268h+var_240], rax
0x180013122  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180013129  mov     [rsp+268h+var_248], 1B0h
0x180013131  call    McTemplateU0dsqs_EventWriteTransfer
0x180013136  jmp     loc_1800131ED
0x18001313b  mov     rsi, 0FFFFFFFF80000002h
0x180013142  jmp     short loc_18001314B
0x180013144  mov     rsi, 0FFFFFFFF80000001h
0x18001314b  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x180013150  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180013155  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x18001315a  mov     ebx, eax
0x18001315c  test    eax, eax
0x18001315e  jns     short loc_18001317F
0x180013160  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013167  jz      short loc_1800131C8
0x180013169  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180013170  mov     [rsp+268h+var_240], rax
0x180013175  mov     [rsp+268h+var_248], 1B2h
0x18001317d  jmp     short loc_1800131B9
0x18001317f  mov     r9, rdi
0x180013182  lea     r8, aProtectionstat; "ProtectionStateHash"
0x180013189  lea     rdx, [rsp+268h+var_228]
0x18001318e  mov     rcx, rsi
0x180013191  call    ?GetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x180013196  mov     ebx, eax
0x180013198  test    eax, eax
0x18001319a  jns     short loc_1800131ED
0x18001319c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800131a3  jz      short loc_1800131C8
0x1800131a5  lea     rax, aChrMdmregistry_18; "CHR(MdmRegistry::GetStringValue( hKey, "...
0x1800131ac  mov     [rsp+268h+var_240], rax
0x1800131b1  mov     [rsp+268h+var_248], 1B8h
0x1800131b9  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800131c0  mov     r8d, ebx
0x1800131c3  call    McTemplateU0dsqs_EventWriteTransfer
0x1800131c8  cmp     ebx, 80070490h
0x1800131ce  jz      short loc_1800131D8
0x1800131d0  cmp     ebx, 80070002h
0x1800131d6  jnz     short loc_1800131ED
0x1800131d8  xor     ebx, ebx
0x1800131da  mov     [rdi+10h], rbx
0x1800131de  cmp     qword ptr [rdi+18h], 7
0x1800131e3  jbe     short loc_1800131E8
0x1800131e5  mov     rdi, [rdi]
0x1800131e8  xor     eax, eax
0x1800131ea  mov     [rdi], ax
0x1800131ed  mov     eax, ebx
0x1800131ef  mov     rcx, [rsp+268h+var_18]
0x1800131f7  xor     rcx, rsp; StackCookie
0x1800131fa  call    __security_check_cookie
0x1800131ff  lea     r11, [rsp+268h+var_8]
0x180013207  mov     rbx, [r11+10h]
0x18001320b  mov     rsi, [r11+20h]
0x18001320f  mov     rsp, r11
0x180013212  pop     rdi
0x180013213  retn
```
