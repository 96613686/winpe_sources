# MdmSettings::HasRegisteredWithService(MdmDeviceContext,int *,int *)

- ea: `0x1800133e8`
- end: `0x1800136b0`
- name: `?HasRegisteredWithService@MdmSettings@@SAJW4MdmDeviceContext@@PEAH1@Z`
- size: `712`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003fa0`
- `0x18000c6e8`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x1800065c0`
- `0x180012d8c`
- `0x1800133e8`
- `0x18001d19c`
- `0x18001d3e4`

## string_xrefs

- `0x1800135be`: `Software\Microsoft\MdmCommon\Internal`
- `0x180013596`: `Software\Microsoft\MdmCommon\Settings`
- `0x18001352d`: `RegisteredWithService`
- `0x180013568`: `RegisteredWithService`
- `0x18001358f`: `RegisteredWithService`
- `0x1800135b7`: `RegisteredWithService`
- `0x180013482`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x1800134c5`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`

## pseudocode

```c
__int64 __fastcall MdmSettings::HasRegisteredWithService(int a1, int *a2, _DWORD *a3)
{
  int v6; // edx
  int v7; // ecx
  int v8; // r8d
  unsigned int MdmCommonSettingValuesPersistedLocation; // ebx
  __int64 v10; // r12
  unsigned int BOOLValue; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  int v14; // edi
  int v15; // esi
  int DWORDValue; // eax
  char v18; // [rsp+20h] [rbp-E0h]
  const char *v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v21; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v22; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v23[264]; // [rsp+40h] [rbp-C0h] BYREF

  memset_0(v23, 0, 0x208u);
  v22 = 260;
  v20 = 0;
  v21 = 0;
  v7 = a1 - 1;
  if ( a1 == 1 )
  {
    v10 = -2147483647;
LABEL_9:
    MdmCommonSettingValuesPersistedLocation = GetMdmCommonSettingValuesPersistedLocation(v23, &v22);
    if ( (MdmCommonSettingValuesPersistedLocation & 0x80000000) != 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        return MdmCommonSettingValuesPersistedLocation;
      v19 = "CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))";
      v18 = 100;
LABEL_12:
      v8 = MdmCommonSettingValuesPersistedLocation;
      goto LABEL_5;
    }
    if ( !a2 )
    {
      MdmCommonSettingValuesPersistedLocation = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v7,
          v6,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
          102,
          "CPR(pfRegistered)");
      return MdmCommonSettingValuesPersistedLocation;
    }
    *a2 = 0;
    if ( a3 )
      *a3 = 0;
    BOOLValue = MdmRegistry::GetBOOLValue((HKEY)v10, v23, L"RegisteredWithService", &v20);
    MdmCommonSettingValuesPersistedLocation = BOOLValue;
    if ( BOOLValue != -2147023728 && BOOLValue != -2147024894 )
      goto LABEL_28;
    if ( a1 == 1 )
      MdmCommonSettingValuesPersistedLocation = MdmRegistry::GetBOOLValue(
                                                  HKEY_LOCAL_MACHINE,
                                                  v23,
                                                  L"RegisteredWithService",
                                                  &v20);
    if ( (MdmCommonSettingValuesPersistedLocation == -2147023728
       || MdmCommonSettingValuesPersistedLocation == -2147024894)
      && ((v12 = MdmRegistry::GetBOOLValue(
                   HKEY_LOCAL_MACHINE,
                   L"Software\\Microsoft\\MdmCommon\\Settings",
                   L"RegisteredWithService",
                   &v20),
           MdmCommonSettingValuesPersistedLocation = v12,
           v12 == -2147023728)
       || v12 == -2147024894)
      && ((v13 = MdmRegistry::GetBOOLValue(
                   HKEY_LOCAL_MACHINE,
                   L"Software\\Microsoft\\MdmCommon\\Internal",
                   L"RegisteredWithService",
                   &v20),
           MdmCommonSettingValuesPersistedLocation = v13,
           v13 == -2147023728)
       || v13 == -2147024894) )
    {
      MdmCommonSettingValuesPersistedLocation = 0;
      v14 = 0;
    }
    else
    {
LABEL_28:
      if ( (MdmCommonSettingValuesPersistedLocation & 0x80000000) != 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          return MdmCommonSettingValuesPersistedLocation;
        v19 = "CHR(hr)";
        v18 = -94;
        goto LABEL_12;
      }
      v14 = v20;
    }
    v15 = 0;
    if ( v14 && a3 )
    {
      DWORDValue = MdmRegistry::GetDWORDValue((HKEY)v10, v23, L"RegisteredVersion", &v21);
      MdmCommonSettingValuesPersistedLocation = DWORDValue;
      if ( DWORDValue == -2147023728 || DWORDValue == -2147024894 )
      {
        MdmCommonSettingValuesPersistedLocation = 0;
      }
      else
      {
        if ( DWORDValue < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
            return MdmCommonSettingValuesPersistedLocation;
          v19 = "CHR(hr)";
          v18 = -70;
          goto LABEL_12;
        }
        LOBYTE(v15) = v21 == 6;
      }
      *a2 = v14;
    }
    else
    {
      *a2 = v14;
      if ( !a3 )
        return MdmCommonSettingValuesPersistedLocation;
    }
    *a3 = v15;
    return MdmCommonSettingValuesPersistedLocation;
  }
  if ( a1 == 2 )
  {
    v10 = -2147483646;
    goto LABEL_9;
  }
  v8 = -2147024809;
  MdmCommonSettingValuesPersistedLocation = -2147024809;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    v19 = "CBR(hKey != nullptr)";
    v18 = 98;
LABEL_5:
    McTemplateU0dsqs_EventWriteTransfer(
      v7,
      v6,
      v8,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
      v18,
      v19);
  }
  return MdmCommonSettingValuesPersistedLocation;
}

```

## disassembly

```asm
0x1800133e8  mov     [rsp-8+arg_0], rbx
0x1800133ed  mov     [rsp-8+arg_18], rsi
0x1800133f2  push    rbp
0x1800133f3  push    rdi
0x1800133f4  push    r12
0x1800133f6  push    r14
0x1800133f8  push    r15
0x1800133fa  lea     rbp, [rsp-160h]
0x180013402  sub     rsp, 260h
0x180013409  mov     rax, cs:__security_cookie
0x180013410  xor     rax, rsp
0x180013413  mov     [rbp+180h+var_30], rax
0x18001341a  mov     r15, r8
0x18001341d  mov     r14, rdx
0x180013420  mov     edi, ecx
0x180013422  xor     edx, edx; Val
0x180013424  mov     r8d, 208h; Size
0x18001342a  lea     rcx, [rsp+280h+var_240]; void *
0x18001342f  call    memset_0
0x180013434  mov     ecx, edi
0x180013436  mov     [rsp+280h+var_248], 104h
0x18001343e  mov     [rsp+280h+var_250], 0
0x180013446  mov     [rsp+280h+var_24C], 0
0x18001344e  sub     ecx, 1
0x180013451  jz      short loc_18001349C
0x180013453  cmp     ecx, 1
0x180013456  jz      short loc_180013493
0x180013458  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001345f  mov     r8d, 80070057h
0x180013465  mov     ebx, r8d
0x180013468  jz      loc_180013682
0x18001346e  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x180013475  mov     [rsp+280h+var_258], rax
0x18001347a  mov     dword ptr [rsp+280h+var_260], 262h
0x180013482  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180013489  call    McTemplateU0dsqs_EventWriteTransfer
0x18001348e  jmp     loc_180013682
0x180013493  mov     r12, 0FFFFFFFF80000002h
0x18001349a  jmp     short loc_1800134A3
0x18001349c  mov     r12, 0FFFFFFFF80000001h
0x1800134a3  lea     rdx, [rsp+280h+var_248]; unsigned int *
0x1800134a8  lea     rcx, [rsp+280h+var_240]; unsigned __int16 *
0x1800134ad  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x1800134b2  mov     ebx, eax
0x1800134b4  test    eax, eax
0x1800134b6  jns     short loc_1800134DE
0x1800134b8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800134bf  jz      loc_180013682
0x1800134c5  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x1800134cc  mov     [rsp+280h+var_258], rax
0x1800134d1  mov     dword ptr [rsp+280h+var_260], 264h
0x1800134d9  mov     r8d, ebx
0x1800134dc  jmp     short loc_180013482
0x1800134de  test    r14, r14
0x1800134e1  jnz     short loc_180013512
0x1800134e3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800134ea  mov     r8d, 80070057h
0x1800134f0  mov     ebx, r8d
0x1800134f3  jz      loc_180013682
0x1800134f9  lea     rax, aCprPfregistere; "CPR(pfRegistered)"
0x180013500  mov     [rsp+280h+var_258], rax
0x180013505  mov     dword ptr [rsp+280h+var_260], 266h
0x18001350d  jmp     loc_180013482
0x180013512  mov     dword ptr [r14], 0
0x180013519  test    r15, r15
0x18001351c  jz      short loc_180013525
0x18001351e  mov     dword ptr [r15], 0
0x180013525  lea     r9, [rsp+280h+var_250]; int *
0x18001352a  mov     rcx, r12; HKEY
0x18001352d  lea     r8, aRegisteredwith; "RegisteredWithService"
0x180013534  lea     rdx, [rsp+280h+var_240]; unsigned __int16 *
0x180013539  call    ?GetBOOLValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAH@Z; MdmRegistry::GetBOOLValue(HKEY__ *,ushort const *,ushort const *,int &)
0x18001353e  mov     ebx, eax
0x180013540  mov     esi, 80070002h
0x180013545  cmp     eax, 80070490h
0x18001354a  jz      short loc_180013554
0x18001354c  cmp     eax, esi
0x18001354e  jnz     loc_1800135D7
0x180013554  cmp     edi, 1
0x180013557  mov     rdi, 0FFFFFFFF80000002h
0x18001355e  jnz     short loc_18001357B
0x180013560  lea     r9, [rsp+280h+var_250]; int *
0x180013565  mov     rcx, rdi; HKEY
0x180013568  lea     r8, aRegisteredwith; "RegisteredWithService"
0x18001356f  lea     rdx, [rsp+280h+var_240]; unsigned __int16 *
0x180013574  call    ?GetBOOLValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAH@Z; MdmRegistry::GetBOOLValue(HKEY__ *,ushort const *,ushort const *,int &)
0x180013579  mov     ebx, eax
0x18001357b  cmp     ebx, 80070490h
0x180013581  jz      short loc_180013587
0x180013583  cmp     ebx, esi
0x180013585  jnz     short loc_1800135D7
0x180013587  lea     r9, [rsp+280h+var_250]; int *
0x18001358c  mov     rcx, rdi; HKEY
0x18001358f  lea     r8, aRegisteredwith; "RegisteredWithService"
0x180013596  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\MdmCommon\\Setting"...
0x18001359d  call    ?GetBOOLValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAH@Z; MdmRegistry::GetBOOLValue(HKEY__ *,ushort const *,ushort const *,int &)
0x1800135a2  mov     ebx, eax
0x1800135a4  cmp     eax, 80070490h
0x1800135a9  jz      short loc_1800135AF
0x1800135ab  cmp     eax, esi
0x1800135ad  jnz     short loc_1800135D7
0x1800135af  lea     r9, [rsp+280h+var_250]; int *
0x1800135b4  mov     rcx, rdi; HKEY
0x1800135b7  lea     r8, aRegisteredwith; "RegisteredWithService"
0x1800135be  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\MdmCommon\\Interna"...
0x1800135c5  call    ?GetBOOLValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAH@Z; MdmRegistry::GetBOOLValue(HKEY__ *,ushort const *,ushort const *,int &)
0x1800135ca  mov     ebx, eax
0x1800135cc  cmp     eax, 80070490h
0x1800135d1  jz      short loc_180013607
0x1800135d3  cmp     eax, esi
0x1800135d5  jz      short loc_180013607
0x1800135d7  test    ebx, ebx
0x1800135d9  jns     short loc_180013601
0x1800135db  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800135e2  jz      loc_180013682
0x1800135e8  lea     rax, aChrHr; "CHR(hr)"
0x1800135ef  mov     [rsp+280h+var_258], rax
0x1800135f4  mov     dword ptr [rsp+280h+var_260], 2A2h
0x1800135fc  jmp     loc_1800134D9
0x180013601  mov     edi, [rsp+280h+var_250]
0x180013605  jmp     short loc_18001360B
0x180013607  xor     ebx, ebx
0x180013609  xor     edi, edi
0x18001360b  xor     esi, esi
0x18001360d  test    edi, edi
0x18001360f  jz      short loc_180013677
0x180013611  test    r15, r15
0x180013614  jz      short loc_180013677
0x180013616  lea     r9, [rsp+280h+var_24C]; unsigned int *
0x18001361b  mov     rcx, r12; HKEY
0x18001361e  lea     r8, aRegisteredvers; "RegisteredVersion"
0x180013625  lea     rdx, [rsp+280h+var_240]; unsigned __int16 *
0x18001362a  call    ?GetDWORDValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAK@Z; MdmRegistry::GetDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong &)
0x18001362f  mov     ebx, eax
0x180013631  cmp     eax, 80070490h
0x180013636  jz      short loc_180013673
0x180013638  cmp     eax, 80070002h
0x18001363d  jz      short loc_180013673
0x18001363f  test    eax, eax
0x180013641  jns     short loc_180013665
0x180013643  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001364a  jz      short loc_180013682
0x18001364c  lea     rax, aChrHr; "CHR(hr)"
0x180013653  mov     [rsp+280h+var_258], rax
0x180013658  mov     dword ptr [rsp+280h+var_260], 2BAh
0x180013660  jmp     loc_1800134D9
0x180013665  cmp     [rsp+280h+var_24C], 6
0x18001366a  setz    sil
0x18001366e  mov     [r14], edi
0x180013671  jmp     short loc_18001367F
0x180013673  xor     ebx, ebx
0x180013675  jmp     short loc_18001366E
0x180013677  mov     [r14], edi
0x18001367a  test    r15, r15
0x18001367d  jz      short loc_180013682
0x18001367f  mov     [r15], esi
0x180013682  mov     eax, ebx
0x180013684  mov     rcx, [rbp+180h+var_30]
0x18001368b  xor     rcx, rsp; StackCookie
0x18001368e  call    __security_check_cookie
0x180013693  lea     r11, [rsp+280h+var_20]
0x18001369b  mov     rbx, [r11+30h]
0x18001369f  mov     rsi, [r11+48h]
0x1800136a3  mov     rsp, r11
0x1800136a6  pop     r15
0x1800136a8  pop     r14
0x1800136aa  pop     r12
0x1800136ac  pop     rdi
0x1800136ad  pop     rbp
0x1800136ae  retn
```
