# MdmSettings::HasRegisteredWithService(MdmDeviceContext,int *,int *)

- ea: `0x180013004`
- end: `0x1800132cb`
- name: `?HasRegisteredWithService@MdmSettings@@SAJW4MdmDeviceContext@@PEAH1@Z`
- size: `711`
- prototype: `__int64 __fastcall(int, int *, _DWORD *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003f90`
- `0x18000c38c`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x180006548`
- `0x1800129b0`
- `0x180013004`
- `0x18001cb38`
- `0x18001cd64`

## string_xrefs

- `0x1800131da`: `Software\Microsoft\MdmCommon\Internal`
- `0x1800131b2`: `Software\Microsoft\MdmCommon\Settings`
- `0x180013149`: `RegisteredWithService`
- `0x180013184`: `RegisteredWithService`
- `0x1800131ab`: `RegisteredWithService`
- `0x1800131d3`: `RegisteredWithService`
- `0x18001309e`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x1800130e1`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`

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
      DWORDValue = MdmRegistry::GetDWORDValue((HKEY)v10, v23, L"RegisteredVersion", (BYTE *)&v21);
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
0x180013004  mov     [rsp-8+arg_0], rbx
0x180013009  mov     [rsp-8+arg_18], rsi
0x18001300e  push    rbp
0x18001300f  push    rdi
0x180013010  push    r12
0x180013012  push    r14
0x180013014  push    r15
0x180013016  lea     rbp, [rsp-160h]
0x18001301e  sub     rsp, 260h
0x180013025  mov     rax, cs:__security_cookie
0x18001302c  xor     rax, rsp
0x18001302f  mov     [rbp+180h+var_30], rax
0x180013036  mov     r15, r8
0x180013039  mov     r14, rdx
0x18001303c  mov     edi, ecx
0x18001303e  xor     edx, edx; Val
0x180013040  mov     r8d, 208h; Size
0x180013046  lea     rcx, [rsp+280h+var_240]; void *
0x18001304b  call    memset_0
0x180013050  mov     ecx, edi
0x180013052  mov     [rsp+280h+var_248], 104h
0x18001305a  mov     [rsp+280h+var_250], 0
0x180013062  mov     [rsp+280h+var_24C], 0
0x18001306a  sub     ecx, 1
0x18001306d  jz      short loc_1800130B8
0x18001306f  cmp     ecx, 1
0x180013072  jz      short loc_1800130AF
0x180013074  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001307b  mov     r8d, 80070057h
0x180013081  mov     ebx, r8d
0x180013084  jz      loc_18001329E
0x18001308a  lea     rax, aCbrHkeyNullptr; "CBR(hKey != nullptr)"
0x180013091  mov     [rsp+280h+var_258], rax
0x180013096  mov     dword ptr [rsp+280h+var_260], 262h
0x18001309e  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800130a5  call    McTemplateU0dsqs_EventWriteTransfer
0x1800130aa  jmp     loc_18001329E
0x1800130af  mov     r12, 0FFFFFFFF80000002h
0x1800130b6  jmp     short loc_1800130BF
0x1800130b8  mov     r12, 0FFFFFFFF80000001h
0x1800130bf  lea     rdx, [rsp+280h+var_248]; unsigned int *
0x1800130c4  lea     rcx, [rsp+280h+var_240]; unsigned __int16 *
0x1800130c9  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x1800130ce  mov     ebx, eax
0x1800130d0  test    eax, eax
0x1800130d2  jns     short loc_1800130FA
0x1800130d4  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800130db  jz      loc_18001329E
0x1800130e1  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x1800130e8  mov     [rsp+280h+var_258], rax
0x1800130ed  mov     dword ptr [rsp+280h+var_260], 264h
0x1800130f5  mov     r8d, ebx
0x1800130f8  jmp     short loc_18001309E
0x1800130fa  test    r14, r14
0x1800130fd  jnz     short loc_18001312E
0x1800130ff  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013106  mov     r8d, 80070057h
0x18001310c  mov     ebx, r8d
0x18001310f  jz      loc_18001329E
0x180013115  lea     rax, aCprPfregistere; "CPR(pfRegistered)"
0x18001311c  mov     [rsp+280h+var_258], rax
0x180013121  mov     dword ptr [rsp+280h+var_260], 266h
0x180013129  jmp     loc_18001309E
0x18001312e  mov     dword ptr [r14], 0
0x180013135  test    r15, r15
0x180013138  jz      short loc_180013141
0x18001313a  mov     dword ptr [r15], 0
0x180013141  lea     r9, [rsp+280h+var_250]; int *
0x180013146  mov     rcx, r12; HKEY
0x180013149  lea     r8, aRegisteredwith; "RegisteredWithService"
0x180013150  lea     rdx, [rsp+280h+var_240]; unsigned __int16 *
0x180013155  call    ?GetBOOLValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAH@Z; MdmRegistry::GetBOOLValue(HKEY__ *,ushort const *,ushort const *,int &)
0x18001315a  mov     ebx, eax
0x18001315c  mov     esi, 80070002h
0x180013161  cmp     eax, 80070490h
0x180013166  jz      short loc_180013170
0x180013168  cmp     eax, esi
0x18001316a  jnz     loc_1800131F3
0x180013170  cmp     edi, 1
0x180013173  mov     rdi, 0FFFFFFFF80000002h
0x18001317a  jnz     short loc_180013197
0x18001317c  lea     r9, [rsp+280h+var_250]; int *
0x180013181  mov     rcx, rdi; HKEY
0x180013184  lea     r8, aRegisteredwith; "RegisteredWithService"
0x18001318b  lea     rdx, [rsp+280h+var_240]; unsigned __int16 *
0x180013190  call    ?GetBOOLValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAH@Z; MdmRegistry::GetBOOLValue(HKEY__ *,ushort const *,ushort const *,int &)
0x180013195  mov     ebx, eax
0x180013197  cmp     ebx, 80070490h
0x18001319d  jz      short loc_1800131A3
0x18001319f  cmp     ebx, esi
0x1800131a1  jnz     short loc_1800131F3
0x1800131a3  lea     r9, [rsp+280h+var_250]; int *
0x1800131a8  mov     rcx, rdi; HKEY
0x1800131ab  lea     r8, aRegisteredwith; "RegisteredWithService"
0x1800131b2  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\MdmCommon\\Setting"...
0x1800131b9  call    ?GetBOOLValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAH@Z; MdmRegistry::GetBOOLValue(HKEY__ *,ushort const *,ushort const *,int &)
0x1800131be  mov     ebx, eax
0x1800131c0  cmp     eax, 80070490h
0x1800131c5  jz      short loc_1800131CB
0x1800131c7  cmp     eax, esi
0x1800131c9  jnz     short loc_1800131F3
0x1800131cb  lea     r9, [rsp+280h+var_250]; int *
0x1800131d0  mov     rcx, rdi; HKEY
0x1800131d3  lea     r8, aRegisteredwith; "RegisteredWithService"
0x1800131da  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\MdmCommon\\Interna"...
0x1800131e1  call    ?GetBOOLValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAH@Z; MdmRegistry::GetBOOLValue(HKEY__ *,ushort const *,ushort const *,int &)
0x1800131e6  mov     ebx, eax
0x1800131e8  cmp     eax, 80070490h
0x1800131ed  jz      short loc_180013223
0x1800131ef  cmp     eax, esi
0x1800131f1  jz      short loc_180013223
0x1800131f3  test    ebx, ebx
0x1800131f5  jns     short loc_18001321D
0x1800131f7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800131fe  jz      loc_18001329E
0x180013204  lea     rax, aChrHr; "CHR(hr)"
0x18001320b  mov     [rsp+280h+var_258], rax
0x180013210  mov     dword ptr [rsp+280h+var_260], 2A2h
0x180013218  jmp     loc_1800130F5
0x18001321d  mov     edi, [rsp+280h+var_250]
0x180013221  jmp     short loc_180013227
0x180013223  xor     ebx, ebx
0x180013225  xor     edi, edi
0x180013227  xor     esi, esi
0x180013229  test    edi, edi
0x18001322b  jz      short loc_180013293
0x18001322d  test    r15, r15
0x180013230  jz      short loc_180013293
0x180013232  lea     r9, [rsp+280h+var_24C]; unsigned int *
0x180013237  mov     rcx, r12; HKEY
0x18001323a  lea     r8, aRegisteredvers; "RegisteredVersion"
0x180013241  lea     rdx, [rsp+280h+var_240]; unsigned __int16 *
0x180013246  call    ?GetDWORDValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAK@Z; MdmRegistry::GetDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong &)
0x18001324b  mov     ebx, eax
0x18001324d  cmp     eax, 80070490h
0x180013252  jz      short loc_18001328F
0x180013254  cmp     eax, 80070002h
0x180013259  jz      short loc_18001328F
0x18001325b  test    eax, eax
0x18001325d  jns     short loc_180013281
0x18001325f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013266  jz      short loc_18001329E
0x180013268  lea     rax, aChrHr; "CHR(hr)"
0x18001326f  mov     [rsp+280h+var_258], rax
0x180013274  mov     dword ptr [rsp+280h+var_260], 2BAh
0x18001327c  jmp     loc_1800130F5
0x180013281  cmp     [rsp+280h+var_24C], 6
0x180013286  setz    sil
0x18001328a  mov     [r14], edi
0x18001328d  jmp     short loc_18001329B
0x18001328f  xor     ebx, ebx
0x180013291  jmp     short loc_18001328A
0x180013293  mov     [r14], edi
0x180013296  test    r15, r15
0x180013299  jz      short loc_18001329E
0x18001329b  mov     [r15], esi
0x18001329e  mov     eax, ebx
0x1800132a0  mov     rcx, [rbp+180h+var_30]
0x1800132a7  xor     rcx, rsp; StackCookie
0x1800132aa  call    __security_check_cookie
0x1800132af  lea     r11, [rsp+280h+var_20]
0x1800132b7  mov     rbx, [r11+30h]
0x1800132bb  mov     rsi, [r11+48h]
0x1800132bf  mov     rsp, r11
0x1800132c2  pop     r15
0x1800132c4  pop     r14
0x1800132c6  pop     r12
0x1800132c8  pop     rdi
0x1800132c9  pop     rbp
0x1800132ca  retn
```
