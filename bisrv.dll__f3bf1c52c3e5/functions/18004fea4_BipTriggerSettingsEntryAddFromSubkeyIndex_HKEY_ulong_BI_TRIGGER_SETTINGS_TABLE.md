# BipTriggerSettingsEntryAddFromSubkeyIndex(HKEY__ *,ulong,_BI_TRIGGER_SETTINGS_TABLE *)

- ea: `0x18004fea4`
- end: `0x180050418`
- name: `?BipTriggerSettingsEntryAddFromSubkeyIndex@@YAJPEAUHKEY__@@KPEAU_BI_TRIGGER_SETTINGS_TABLE@@@Z`
- size: `1396`
- prototype: `__int64 __fastcall(HKEY hKey, DWORD dwIndex, struct _BI_TRIGGER_SETTINGS_TABLE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180064828`

## callees

- `0x1800254e4`
- `0x1800260e8`
- `0x180026f8c`
- `0x18002d890`
- `0x180030f24`
- `0x180034ae0`
- `0x18004fea4`
- `0x1800848e8`
- `0x180084978`
- `0x180094656`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `msvcrt!swscanf_s` at `0x18004ff84`
- `msvcrt!swscanf_s` at `0x18004ff84`
- `ntdll!RtlFreeUnicodeString` at `0x1800503f3`
- `ntdll!RtlFreeUnicodeString` at `0x1800503f3`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18005034c`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18005034c`
- `ntdll!RtlInitUnicodeString` at `0x18004ff32`
- `ntdll!RtlInitUnicodeString` at `0x18004ffbd`
- `ntdll!RtlInitUnicodeString` at `0x18004fffd`
- `ntdll!RtlInitUnicodeString` at `0x180050041`
- `ntdll!RtlInitUnicodeString` at `0x180050096`
- `ntdll!RtlInitUnicodeString` at `0x1800500d8`
- `ntdll!RtlInitUnicodeString` at `0x18005011c`
- `ntdll!RtlInitUnicodeString` at `0x18005015a`
- `ntdll!RtlInitUnicodeString` at `0x18005019e`
- `ntdll!RtlInitUnicodeString` at `0x1800501d7`
- `ntdll!RtlInitUnicodeString` at `0x180050218`
- `ntdll!RtlInitUnicodeString` at `0x18005025a`
- `ntdll!RtlInitUnicodeString` at `0x1800502b8`
- `ntdll!RtlInitUnicodeString` at `0x1800502f9`
- `ntdll!RtlInitUnicodeString` at `0x180050370`
- `ntdll!RtlInitUnicodeString` at `0x1800503a1`
- `ntdll!RtlInitUnicodeString` at `0x18004ff32`
- `ntdll!RtlInitUnicodeString` at `0x18004ffbd`
- `ntdll!RtlInitUnicodeString` at `0x18004fffd`
- `ntdll!RtlInitUnicodeString` at `0x180050041`
- `ntdll!RtlInitUnicodeString` at `0x180050096`
- `ntdll!RtlInitUnicodeString` at `0x1800500d8`
- `ntdll!RtlInitUnicodeString` at `0x18005011c`
- `ntdll!RtlInitUnicodeString` at `0x18005015a`
- `ntdll!RtlInitUnicodeString` at `0x18005019e`
- `ntdll!RtlInitUnicodeString` at `0x1800501d7`
- `ntdll!RtlInitUnicodeString` at `0x180050218`
- `ntdll!RtlInitUnicodeString` at `0x18005025a`
- `ntdll!RtlInitUnicodeString` at `0x1800502b8`
- `ntdll!RtlInitUnicodeString` at `0x1800502f9`
- `ntdll!RtlInitUnicodeString` at `0x180050370`
- `ntdll!RtlInitUnicodeString` at `0x1800503a1`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18004ffa5`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18004ffa5`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18004ff4a`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18004ff4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800503e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800503e8`

## string_xrefs

- `0x180050035`: `CLSID`
- `0x18005020c`: `ShellReadyBufferingExempt`

## pseudocode

```c
__int64 __fastcall BipTriggerSettingsEntryAddFromSubkeyIndex(
        HKEY hKey,
        DWORD dwIndex,
        struct _BI_TRIGGER_SETTINGS_TABLE *a3)
{
  LSTATUS v6; // eax
  signed int v7; // ebx
  bool v8; // cc
  int v9; // eax
  unsigned __int64 v10; // rdx
  int v11; // eax
  int v12; // ecx
  HKEY phkResult; // [rsp+28h] [rbp-D8h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+44h] [rbp-BCh]
  int v18; // [rsp+48h] [rbp-B8h]
  __int64 v19; // [rsp+50h] [rbp-B0h]
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  int v21; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v22; // [rsp+74h] [rbp-8Ch]
  char v23; // [rsp+78h] [rbp-88h]
  __int16 v24; // [rsp+79h] [rbp-87h]
  char v25; // [rsp+7Bh] [rbp-85h]
  char v26; // [rsp+7Ch] [rbp-84h]
  int v27; // [rsp+80h] [rbp-80h]
  int v28; // [rsp+84h] [rbp-7Ch]
  unsigned __int16 v29[64]; // [rsp+88h] [rbp-78h] BYREF
  char v30; // [rsp+108h] [rbp+8h]
  int v31; // [rsp+10Ch] [rbp+Ch]
  int v32; // [rsp+110h] [rbp+10h]
  GUID Buf1; // [rsp+120h] [rbp+20h] BYREF
  WCHAR Name[32]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v35[64]; // [rsp+170h] [rbp+70h] BYREF

  memset_0(&v21, 0, 0xA4u);
  v19 = 0;
  v16 = 0;
  v17 = 0;
  ValueName = 0;
  v18 = 0;
  Buf1 = 0;
  phkResult = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  v6 = RegEnumKeyW(hKey, dwIndex, Name, 0x20u);
  v7 = v6;
  v8 = v6 <= 0;
  if ( v6 )
    goto LABEL_2;
  BipTriggerSettingsInitialize(&v21);
  if ( swscanf_s(Name, L"%u", &v21) != 1 )
  {
    v7 = -1073741811;
    goto LABEL_44;
  }
  v6 = RegOpenKeyW(hKey, Name, &phkResult);
  v7 = v6;
  v8 = v6 <= 0;
  if ( v6 )
  {
LABEL_2:
    if ( !v8 )
      v7 = (unsigned __int16)v6 | 0xC0070000;
  }
  else
  {
    RtlInitUnicodeString(&ValueName, L"BatterySaverOverride");
    if ( !(unsigned int)BipReadRegUlong(phkResult, &ValueName) )
      v22 &= ~1u;
    RtlInitUnicodeString(&ValueName, L"ExecutionDisabledOverride");
    if ( !(unsigned int)BipReadRegUlong(phkResult, &ValueName) )
      v22 &= ~2u;
    RtlInitUnicodeString(&ValueName, L"CLSID");
    if ( !(unsigned int)BipReadRegGuid(phkResult, &ValueName, &Buf1) )
    {
      v9 = memcmp_0(&Buf1, &GUID_NULL, 0x10u);
      v22 = (v9 != 0 ? 4 : 0) | v22 & 0xFFFFFFFB;
    }
    RtlInitUnicodeString(&ValueName, L"TriggerDisabled");
    if ( !(unsigned int)BipReadRegUlong(phkResult, &ValueName) )
      v22 &= ~8u;
    RtlInitUnicodeString(&ValueName, L"GlobalCoalesceDurationMs");
    if ( !(unsigned int)BipReadRegUlong(phkResult, &ValueName) )
    {
      v23 = 0;
      v24 = 0;
      v25 = 0;
    }
    RtlInitUnicodeString(&ValueName, L"GlobalCoalesceCsOnly");
    if ( !(unsigned int)BipReadRegUlong(phkResult, &ValueName) )
      v26 &= ~1u;
    RtlInitUnicodeString(&ValueName, L"BiCrmActivityId");
    if ( !(unsigned int)BipReadRegUlong(phkResult, &ValueName) )
    {
      v27 = 26;
      v28 = 26;
      RtlInitUnicodeString(&ValueName, L"PrioritizedBiCrmActivityId");
      if ( !(unsigned int)BipReadRegUlong(phkResult, &ValueName) )
        v28 = 26;
      RtlInitUnicodeString(&ValueName, L"CrmPolicyDisabled");
      if ( !(unsigned int)BipReadRegUlong(phkResult, &ValueName) )
        v22 &= ~0x10u;
    }
    RtlInitUnicodeString(&ValueName, L"ShellReadyBufferingExempt");
    if ( !(unsigned int)BipReadRegUlong(phkResult, &ValueName) )
      v22 &= ~0x20u;
    RtlInitUnicodeString(&ValueName, L"BiTriggerSettingFlags");
    if ( !(unsigned int)BipReadRegUlong64(phkResult, &ValueName) && (v19 & 7) == v19 )
      v22 = v22 & 0xFFFFFEBF | ((v19 & 1) << 6) | ((_WORD)v19 << 6) & 0x100;
    RtlInitUnicodeString(&ValueName, L"SupportedActivationTypesMask");
    if ( !(unsigned int)BipReadRegUlong(phkResult, &ValueName) )
      v30 = 0;
    RtlInitUnicodeString(&ValueName, L"ResourceSetType");
    if ( (int)BipReadRegUnicodeString(phkResult, &ValueName, &DestinationString) >= 0
      && (int)RtlStringCbCopyUnicodeString(v35, v10, &DestinationString) >= 0 )
    {
      RtlStringCbCopyW(v29, 0x80u, v35);
    }
    if ( v21 == 107 )
    {
      RtlGetDeviceFamilyInfoEnum(0, &v16, 0);
      if ( v16 != 3 && v16 != 9 )
        v30 |= 4u;
    }
    RtlInitUnicodeString(&ValueName, L"PolicyFlags");
    if ( (int)BipReadRegUlong(phkResult, &ValueName) >= 0 )
      v31 |= v17;
    RtlInitUnicodeString(&ValueName, L"WallClockLimitMs");
    v11 = BipReadRegUlong(phkResult, &ValueName);
    v12 = v32;
    if ( v11 >= 0 )
      v12 = v18;
    v32 = v12;
    v7 = BipTriggerSettingsTableInsert(&v21, a3);
    if ( v7 >= 0 )
      v7 = 0;
  }
LABEL_44:
  if ( phkResult )
    RegCloseKey(phkResult);
  RtlFreeUnicodeString(&DestinationString);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004fea4  push    rbp
0x18004fea6  push    rbx
0x18004fea7  push    rsi
0x18004fea8  push    rdi
0x18004fea9  push    r15
0x18004feab  lea     rbp, [rsp-100h]
0x18004feb3  sub     rsp, 200h
0x18004feba  mov     rax, cs:__security_cookie
0x18004fec1  xor     rax, rsp
0x18004fec4  mov     [rbp+120h+var_30], rax
0x18004fecb  mov     rsi, r8
0x18004fece  mov     ebx, edx
0x18004fed0  mov     rdi, rcx
0x18004fed3  xor     edx, edx; Val
0x18004fed5  mov     r8d, 0A4h; Size
0x18004fedb  lea     rcx, [rsp+220h+var_1B0]; void *
0x18004fee0  call    memset_0
0x18004fee5  xorps   xmm0, xmm0
0x18004fee8  mov     [rsp+220h+var_200], 0
0x18004fef0  xorps   xmm1, xmm1
0x18004fef3  mov     [rsp+220h+var_1D0], 0
0x18004fefc  xor     edx, edx; SourceString
0x18004fefe  mov     [rsp+220h+var_1E0], 0
0x18004ff06  lea     rcx, [rsp+220h+DestinationString]; DestinationString
0x18004ff0b  mov     [rsp+220h+var_1DC], 0
0x18004ff13  movups  xmmword ptr [rsp+220h+ValueName.Length], xmm0
0x18004ff18  mov     [rsp+220h+var_1D8], 0
0x18004ff20  movups  [rbp+120h+Buf1], xmm0
0x18004ff24  mov     [rsp+220h+phkResult], 0
0x18004ff2d  movups  xmmword ptr [rsp+220h+DestinationString.Length], xmm1
0x18004ff32  call    cs:__imp_RtlInitUnicodeString
0x18004ff38  mov     r15d, 20h ; ' '
0x18004ff3e  lea     r8, [rbp+120h+Name]; lpName
0x18004ff42  mov     r9d, r15d; cchName
0x18004ff45  mov     edx, ebx; dwIndex
0x18004ff47  mov     rcx, rdi; hKey
0x18004ff4a  call    cs:__imp_RegEnumKeyW
0x18004ff50  mov     ebx, eax
0x18004ff52  test    eax, eax
0x18004ff54  jz      short loc_18004FF6A
0x18004ff56  jle     loc_1800503DE
0x18004ff5c  movzx   ebx, ax
0x18004ff5f  or      ebx, 0C0070000h
0x18004ff65  jmp     loc_1800503DE
0x18004ff6a  lea     rcx, [rsp+220h+var_1B0]
0x18004ff6f  call    BipTriggerSettingsInitialize
0x18004ff74  lea     r8, [rsp+220h+var_1B0]
0x18004ff79  lea     rdx, aU; "%u"
0x18004ff80  lea     rcx, [rbp+120h+Name]; Buffer
0x18004ff84  call    cs:__imp_swscanf_s
0x18004ff8a  cmp     eax, 1
0x18004ff8d  jz      short loc_18004FF99
0x18004ff8f  mov     ebx, 0C000000Dh
0x18004ff94  jmp     loc_1800503DE
0x18004ff99  lea     r8, [rsp+220h+phkResult]; phkResult
0x18004ff9e  mov     rcx, rdi; hKey
0x18004ffa1  lea     rdx, [rbp+120h+Name]; lpSubKey
0x18004ffa5  call    cs:__imp_RegOpenKeyW
0x18004ffab  mov     ebx, eax
0x18004ffad  test    eax, eax
0x18004ffaf  jnz     short loc_18004FF56
0x18004ffb1  lea     rdx, aBatterysaverov; "BatterySaverOverride"
0x18004ffb8  lea     rcx, [rsp+220h+ValueName]; DestinationString
0x18004ffbd  call    cs:__imp_RtlInitUnicodeString
0x18004ffc3  mov     rcx, [rsp+220h+phkResult]; KeyHandle
0x18004ffc8  lea     r8, [rsp+220h+var_200]
0x18004ffcd  lea     rdx, [rsp+220h+ValueName]; ValueName
0x18004ffd2  call    BipReadRegUlong
0x18004ffd7  test    eax, eax
0x18004ffd9  jnz     short loc_18004FFF1
0x18004ffdb  mov     eax, [rsp+220h+var_1AC]
0x18004ffdf  xor     ecx, ecx
0x18004ffe1  cmp     [rsp+220h+var_200], ecx
0x18004ffe5  setnz   cl
0x18004ffe8  and     eax, 0FFFFFFFEh
0x18004ffeb  or      eax, ecx
0x18004ffed  mov     [rsp+220h+var_1AC], eax
0x18004fff1  lea     rdx, aExecutiondisab; "ExecutionDisabledOverride"
0x18004fff8  lea     rcx, [rsp+220h+ValueName]; DestinationString
0x18004fffd  call    cs:__imp_RtlInitUnicodeString
0x180050003  mov     rcx, [rsp+220h+phkResult]; KeyHandle
0x180050008  lea     r8, [rsp+220h+var_200]
0x18005000d  lea     rdx, [rsp+220h+ValueName]; ValueName
0x180050012  call    BipReadRegUlong
0x180050017  test    eax, eax
0x180050019  jnz     short loc_180050035
0x18005001b  xor     ecx, ecx
0x18005001d  cmp     [rsp+220h+var_200], 1
0x180050022  lea     eax, [rcx+2]
0x180050025  cmovz   ecx, eax
0x180050028  mov     eax, [rsp+220h+var_1AC]
0x18005002c  and     eax, 0FFFFFFFDh
0x18005002f  or      eax, ecx
0x180050031  mov     [rsp+220h+var_1AC], eax
0x180050035  lea     rdx, aClsid; "CLSID"
0x18005003c  lea     rcx, [rsp+220h+ValueName]; DestinationString
0x180050041  call    cs:__imp_RtlInitUnicodeString
0x180050047  mov     rcx, [rsp+220h+phkResult]; KeyHandle
0x18005004c  lea     r8, [rbp+120h+Buf1]; Guid
0x180050050  lea     rdx, [rsp+220h+ValueName]; ValueName
0x180050055  call    BipReadRegGuid
0x18005005a  mov     ebx, 10h
0x18005005f  test    eax, eax
0x180050061  jnz     short loc_18005008A
0x180050063  mov     r8d, ebx; Size
0x180050066  lea     rdx, GUID_NULL; Buf2
0x18005006d  lea     rcx, [rbp+120h+Buf1]; Buf1
0x180050071  call    memcmp_0
0x180050076  neg     eax
0x180050078  mov     eax, [rsp+220h+var_1AC]
0x18005007c  sbb     ecx, ecx
0x18005007e  and     eax, 0FFFFFFFBh
0x180050081  and     ecx, 4
0x180050084  or      eax, ecx
0x180050086  mov     [rsp+220h+var_1AC], eax
0x18005008a  lea     rdx, aTriggerdisable; "TriggerDisabled"
0x180050091  lea     rcx, [rsp+220h+ValueName]; DestinationString
0x180050096  call    cs:__imp_RtlInitUnicodeString
0x18005009c  mov     rcx, [rsp+220h+phkResult]; KeyHandle
0x1800500a1  lea     r8, [rsp+220h+var_200]
0x1800500a6  lea     rdx, [rsp+220h+ValueName]; ValueName
0x1800500ab  call    BipReadRegUlong
0x1800500b0  test    eax, eax
0x1800500b2  jnz     short loc_1800500CC
0x1800500b4  mov     eax, [rsp+220h+var_200]
0x1800500b8  neg     eax
0x1800500ba  mov     eax, [rsp+220h+var_1AC]
0x1800500be  sbb     ecx, ecx
0x1800500c0  and     eax, 0FFFFFFF7h
0x1800500c3  and     ecx, 8
0x1800500c6  or      eax, ecx
0x1800500c8  mov     [rsp+220h+var_1AC], eax
0x1800500cc  lea     rdx, aGlobalcoalesce_0; "GlobalCoalesceDurationMs"
0x1800500d3  lea     rcx, [rsp+220h+ValueName]; DestinationString
0x1800500d8  call    cs:__imp_RtlInitUnicodeString
0x1800500de  mov     rcx, [rsp+220h+phkResult]; KeyHandle
0x1800500e3  lea     r8, [rsp+220h+var_200]
0x1800500e8  lea     rdx, [rsp+220h+ValueName]; ValueName
0x1800500ed  call    BipReadRegUlong
0x1800500f2  test    eax, eax
0x1800500f4  jnz     short loc_180050110
0x1800500f6  mov     al, byte ptr [rsp+220h+var_200]
0x1800500fa  mov     [rsp+220h+var_1A8], al
0x1800500fe  movzx   eax, word ptr [rsp+220h+var_200+1]
0x180050103  mov     [rsp+220h+var_1A7], ax
0x180050108  mov     al, byte ptr [rsp+220h+var_200+3]
0x18005010c  mov     [rsp+220h+var_1A5], al
0x180050110  lea     rdx, aGlobalcoalesce_2; "GlobalCoalesceCsOnly"
0x180050117  lea     rcx, [rsp+220h+ValueName]; DestinationString
0x18005011c  call    cs:__imp_RtlInitUnicodeString
0x180050122  mov     rcx, [rsp+220h+phkResult]; KeyHandle
0x180050127  lea     r8, [rsp+220h+var_200]
0x18005012c  lea     rdx, [rsp+220h+ValueName]; ValueName
0x180050131  call    BipReadRegUlong
0x180050136  test    eax, eax
0x180050138  jnz     short loc_18005014E
0x18005013a  cmp     [rsp+220h+var_200], eax
0x18005013e  mov     cl, [rsp+220h+var_1A4]
0x180050142  setnz   al
0x180050145  and     cl, 0FEh
0x180050148  or      cl, al
0x18005014a  mov     [rsp+220h+var_1A4], cl
0x18005014e  lea     rdx, aBicrmactivityi; "BiCrmActivityId"
0x180050155  lea     rcx, [rsp+220h+ValueName]; DestinationString
0x18005015a  call    cs:__imp_RtlInitUnicodeString
0x180050160  mov     rcx, [rsp+220h+phkResult]; KeyHandle
0x180050165  lea     r8, [rsp+220h+var_200]
0x18005016a  lea     rdx, [rsp+220h+ValueName]; ValueName
0x18005016f  call    BipReadRegUlong
0x180050174  test    eax, eax
0x180050176  jnz     loc_18005020C
0x18005017c  mov     eax, [rsp+220h+var_200]
0x180050180  cmp     eax, 7
0x180050183  jnb     loc_18005020C
0x180050189  add     eax, 1Ah
0x18005018c  lea     rdx, aPrioritizedbic; "PrioritizedBiCrmActivityId"
0x180050193  lea     rcx, [rsp+220h+ValueName]; DestinationString
0x180050198  mov     [rbp+120h+var_1A0], eax
0x18005019b  mov     [rbp+120h+var_19C], eax
0x18005019e  call    cs:__imp_RtlInitUnicodeString
0x1800501a4  mov     rcx, [rsp+220h+phkResult]; KeyHandle
0x1800501a9  lea     r8, [rsp+220h+var_200]
0x1800501ae  lea     rdx, [rsp+220h+ValueName]; ValueName
0x1800501b3  call    BipReadRegUlong
0x1800501b8  test    eax, eax
0x1800501ba  jnz     short loc_1800501CB
0x1800501bc  mov     eax, [rsp+220h+var_200]
0x1800501c0  cmp     eax, 7
0x1800501c3  jnb     short loc_1800501CB
0x1800501c5  add     eax, 1Ah
0x1800501c8  mov     [rbp+120h+var_19C], eax
0x1800501cb  lea     rdx, aCrmpolicydisab; "CrmPolicyDisabled"
0x1800501d2  lea     rcx, [rsp+220h+ValueName]; DestinationString
0x1800501d7  call    cs:__imp_RtlInitUnicodeString
0x1800501dd  mov     rcx, [rsp+220h+phkResult]; KeyHandle
0x1800501e2  lea     r8, [rsp+220h+var_200]
0x1800501e7  lea     rdx, [rsp+220h+ValueName]; ValueName
0x1800501ec  call    BipReadRegUlong
0x1800501f1  test    eax, eax
0x1800501f3  jnz     short loc_18005020C
0x1800501f5  mov     eax, [rsp+220h+var_1AC]
0x1800501f9  xor     ecx, ecx
0x1800501fb  cmp     [rsp+220h+var_200], 1
0x180050200  cmovz   ecx, ebx
0x180050203  and     eax, 0FFFFFFEFh
0x180050206  or      eax, ecx
0x180050208  mov     [rsp+220h+var_1AC], eax
0x18005020c  lea     rdx, aShellreadybuff; "ShellReadyBufferingExempt"
0x180050213  lea     rcx, [rsp+220h+ValueName]; DestinationString
0x180050218  call    cs:__imp_RtlInitUnicodeString
0x18005021e  mov     rcx, [rsp+220h+phkResult]; KeyHandle
0x180050223  lea     r8, [rsp+220h+var_200]
0x180050228  lea     rdx, [rsp+220h+ValueName]; ValueName
0x18005022d  call    BipReadRegUlong
0x180050232  test    eax, eax
0x180050234  jnz     short loc_18005024E
0x180050236  mov     eax, [rsp+220h+var_1AC]
0x18005023a  xor     ecx, ecx
0x18005023c  cmp     [rsp+220h+var_200], 1
0x180050241  cmovz   ecx, r15d
0x180050245  and     eax, 0FFFFFFDFh
0x180050248  or      eax, ecx
0x18005024a  mov     [rsp+220h+var_1AC], eax
0x18005024e  lea     rdx, aBitriggersetti; "BiTriggerSettingFlags"
0x180050255  lea     rcx, [rsp+220h+ValueName]; DestinationString
0x18005025a  call    cs:__imp_RtlInitUnicodeString
0x180050260  mov     rcx, [rsp+220h+phkResult]; KeyHandle
0x180050265  lea     r8, [rsp+220h+var_1D0]
0x18005026a  lea     rdx, [rsp+220h+ValueName]; ValueName
0x18005026f  call    BipReadRegUlong64
0x180050274  test    eax, eax
0x180050276  jnz     short loc_1800502AC
0x180050278  mov     rdx, [rsp+220h+var_1D0]
0x18005027d  mov     rax, rdx
0x180050280  and     eax, 7
0x180050283  cmp     rax, rdx
0x180050286  jnz     short loc_1800502AC
0x180050288  mov     eax, [rsp+220h+var_1AC]
0x18005028c  mov     rcx, rdx
0x18005028f  shl     rcx, 6
0x180050293  and     edx, 1
0x180050296  and     ecx, 100h
0x18005029c  shl     edx, 6
0x18005029f  or      ecx, edx
0x1800502a1  and     eax, 0FFFFFEBFh
0x1800502a6  or      ecx, eax
0x1800502a8  mov     [rsp+220h+var_1AC], ecx
0x1800502ac  lea     rdx, aSupportedactiv; "SupportedActivationTypesMask"
0x1800502b3  lea     rcx, [rsp+220h+ValueName]; DestinationString
0x1800502b8  call    cs:__imp_RtlInitUnicodeString
0x1800502be  mov     rcx, [rsp+220h+phkResult]; KeyHandle
0x1800502c3  lea     r8, [rsp+220h+var_200]
0x1800502c8  lea     rdx, [rsp+220h+ValueName]; ValueName
0x1800502cd  call    BipReadRegUlong
0x1800502d2  test    eax, eax
0x1800502d4  jnz     short loc_1800502ED
0x1800502d6  movzx   ecx, [rbp+120h+var_118]
0x1800502da  test    [rsp+220h+var_200], 0FFFFFFF8h
0x1800502e2  movzx   eax, byte ptr [rsp+220h+var_200]
0x1800502e7  cmovz   ecx, eax
0x1800502ea  mov     [rbp+120h+var_118], cl
0x1800502ed  lea     rdx, ValueName; "ResourceSetType"
0x1800502f4  lea     rcx, [rsp+220h+ValueName]; DestinationString
0x1800502f9  call    cs:__imp_RtlInitUnicodeString
0x1800502ff  mov     rcx, [rsp+220h+phkResult]; KeyHandle
0x180050304  lea     r8, [rsp+220h+DestinationString]; DestinationString
0x180050309  lea     rdx, [rsp+220h+ValueName]; ValueName
0x18005030e  call    BipReadRegUnicodeString
0x180050313  test    eax, eax
0x180050315  js      short loc_18005033B
0x180050317  lea     r8, [rsp+220h+DestinationString]; struct _UNICODE_STRING *
0x18005031c  lea     rcx, [rbp+120h+var_B0]; unsigned __int16 *
0x180050320  call    ?RtlStringCbCopyUnicodeString@@YAJPEAG_KPEBU_UNICODE_STRING@@@Z; RtlStringCbCopyUnicodeString(ushort *,unsigned __int64,_UNICODE_STRING const *)
0x180050325  test    eax, eax
0x180050327  js      short loc_18005033B
0x180050329  lea     r8, [rbp+120h+var_B0]; unsigned __int16 *
0x18005032d  mov     edx, 80h; unsigned __int64
0x180050332  lea     rcx, [rbp+120h+var_198]; unsigned __int16 *
0x180050336  call    ?RtlStringCbCopyW@@YAJPEAG_KPEBG@Z; RtlStringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18005033b  cmp     [rsp+220h+var_1B0], 6Bh ; 'k'
0x180050340  jnz     short loc_180050364
0x180050342  xor     r8d, r8d
0x180050345  lea     rdx, [rsp+220h+var_1E0]
0x18005034a  xor     ecx, ecx
0x18005034c  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180050352  cmp     [rsp+220h+var_1E0], 3
0x180050357  jz      short loc_180050364
0x180050359  cmp     [rsp+220h+var_1E0], 9
0x18005035e  jz      short loc_180050364
0x180050360  or      [rbp+120h+var_118], 4
0x180050364  lea     rdx, aPolicyflags; "PolicyFlags"
0x18005036b  lea     rcx, [rsp+220h+ValueName]; DestinationString
0x180050370  call    cs:__imp_RtlInitUnicodeString
0x180050376  mov     rcx, [rsp+220h+phkResult]; KeyHandle
0x18005037b  lea     r8, [rsp+220h+var_1DC]
0x180050380  lea     rdx, [rsp+220h+ValueName]; ValueName
0x180050385  call    BipReadRegUlong
0x18005038a  test    eax, eax
0x18005038c  js      short loc_180050395
0x18005038e  mov     eax, [rsp+220h+var_1DC]
  ... truncated ...
```
