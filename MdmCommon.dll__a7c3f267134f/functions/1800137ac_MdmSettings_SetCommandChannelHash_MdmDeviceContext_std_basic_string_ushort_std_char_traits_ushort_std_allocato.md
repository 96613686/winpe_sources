# MdmSettings::SetCommandChannelHash(MdmDeviceContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800137ac`
- end: `0x1800138d6`
- name: `?SetCommandChannelHash@MdmSettings@@SAJW4MdmDeviceContext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `298`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003010`
- `0x180011800`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x1800065c0`
- `0x180012d8c`
- `0x1800137ac`
- `0x18001d908`

## string_xrefs

- `0x180013868`: `CommandChannelHash`
- `0x18001389f`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x18001384f`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`
- `0x18001388b`: `CHR(MdmRegistry::SetStringValue( hKey, wszKey, c_pszCommandChannelHash, pszValue))`

## pseudocode

```c
__int64 __fastcall MdmSettings::SetCommandChannelHash(int a1, __int64 *a2)
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
          201,
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
    MdmCommonSettingValuesPersistedLocation = MdmRegistry::SetStringValue((HKEY)v8, v15, L"CommandChannelHash", a2);
    if ( MdmCommonSettingValuesPersistedLocation < 0
      && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v12,
        v11,
        MdmCommonSettingValuesPersistedLocation,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
        209,
        "CHR(MdmRegistry::SetStringValue( hKey, wszKey, c_pszCommandChannelHash, pszValue))",
        *(_QWORD *)v14);
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v10,
      v9,
      MdmCommonSettingValuesPersistedLocation,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
      203,
      "CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))",
      *(_QWORD *)v14);
  }
  return (unsigned int)MdmCommonSettingValuesPersistedLocation;
}

```

## disassembly

```asm
0x1800137ac  mov     [rsp+arg_0], rbx
0x1800137b1  mov     [rsp+arg_10], rsi
0x1800137b6  push    rdi
0x1800137b7  sub     rsp, 260h
0x1800137be  mov     rax, cs:__security_cookie
0x1800137c5  xor     rax, rsp
0x1800137c8  mov     [rsp+268h+var_18], rax
0x1800137d0  mov     rsi, rdx
0x1800137d3  mov     ebx, ecx
0x1800137d5  xor     edx, edx; Val
0x1800137d7  lea     rcx, [rsp+268h+var_228]; void *
0x1800137dc  mov     r8d, 208h; Size
0x1800137e2  call    memset_0
0x1800137e7  mov     [rsp+268h+var_238], 104h
0x1800137ef  sub     ebx, 1
0x1800137f2  jz      short loc_18001382A
0x1800137f4  cmp     ebx, 1
0x1800137f7  jz      short loc_180013821
0x1800137f9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013800  mov     ebx, 80070057h
0x180013805  jz      loc_1800138AE
0x18001380b  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x180013812  mov     [rsp+268h+var_240], rax
0x180013817  mov     [rsp+268h+var_248], 0C9h
0x18001381f  jmp     short loc_18001389F
0x180013821  mov     rdi, 0FFFFFFFF80000002h
0x180013828  jmp     short loc_180013831
0x18001382a  mov     rdi, 0FFFFFFFF80000001h
0x180013831  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x180013836  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x18001383b  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180013840  mov     ebx, eax
0x180013842  test    eax, eax
0x180013844  jns     short loc_180013865
0x180013846  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001384d  jz      short loc_1800138AE
0x18001384f  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180013856  mov     [rsp+268h+var_240], rax
0x18001385b  mov     [rsp+268h+var_248], 0CBh
0x180013863  jmp     short loc_18001389F
0x180013865  mov     r9, rsi
0x180013868  lea     r8, aCommandchannel; "CommandChannelHash"
0x18001386f  lea     rdx, [rsp+268h+var_228]
0x180013874  mov     rcx, rdi
0x180013877  call    ?SetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; MdmRegistry::SetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring const &,ulong)
0x18001387c  mov     ebx, eax
0x18001387e  test    eax, eax
0x180013880  jns     short loc_1800138AE
0x180013882  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013889  jz      short loc_1800138AE
0x18001388b  lea     rax, aChrMdmregistry_9; "CHR(MdmRegistry::SetStringValue( hKey, "...
0x180013892  mov     [rsp+268h+var_240], rax
0x180013897  mov     [rsp+268h+var_248], 0D1h
0x18001389f  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800138a6  mov     r8d, ebx
0x1800138a9  call    McTemplateU0dsqs_EventWriteTransfer
0x1800138ae  mov     eax, ebx
0x1800138b0  mov     rcx, [rsp+268h+var_18]
0x1800138b8  xor     rcx, rsp; StackCookie
0x1800138bb  call    __security_check_cookie
0x1800138c0  lea     r11, [rsp+268h+var_8]
0x1800138c8  mov     rbx, [r11+10h]
0x1800138cc  mov     rsi, [r11+20h]
0x1800138d0  mov     rsp, r11
0x1800138d3  pop     rdi
0x1800138d4  retn
```
