# sub_1800EDC5C

- ea: `0x1800edc5c`
- end: `0x1800edf3d`
- name: `sub_1800EDC5C`
- size: `737`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800ead74`

## callees

- `0x18003b830`
- `0x1800ea1fc`
- `0x1800ea56c`
- `0x1800ed0d0`
- `0x1800edc5c`
- `0x1800f2ad4`
- `0x1800f30bc`
- `0x1800f315c`
- `0x1800f3280`

## string_xrefs

- `0x1800edd14`: `AzureAdRefreshInterval`
- `0x1800edd76`: `DataDuplicationDirectory`
- `0x1800ede61`: `PoliciesLastUpdated`
- `0x1800ede7c`: `DeduplicateAccessEvents`
- `0x1800ede26`: `SecuredDevicesConfiguration`
- `0x1800ede43`: `CustomSupportLink`
- `0x1800edeb3`: `AadSidCache`

## pseudocode

```c
__int64 __fastcall sub_1800EDC5C(__int64 a1, __int64 a2)
{
  int v3; // r9d
  int v4; // r9d
  int v5; // r9d
  int v6; // r9d
  int v7; // r9d
  int v8; // r9d
  __int64 v10; // [rsp+30h] [rbp-51h]
  int v11; // [rsp+40h] [rbp-41h]
  int v12; // [rsp+48h] [rbp-39h]
  _BYTE v13[80]; // [rsp+68h] [rbp-19h] BYREF

  sub_1800EA1FC(v13, L"Device Control", a2);
  sub_1800F30BC(
    (unsigned int)v13,
    (unsigned int)L"NotificationThrottleMin",
    (unsigned int)L"NotificationThrottleMin",
    300);
  sub_1800F30BC(
    (unsigned int)v13,
    (unsigned int)L"NotificationThrottleMax",
    (unsigned int)L"NotificationThrottleMax",
    3600);
  sub_1800F30BC(
    (unsigned int)v13,
    (unsigned int)L"PolicyRefreshFailureInterval",
    (unsigned int)L"PolicyRefreshFailureInterval",
    360);
  sub_1800F30BC(
    (unsigned int)v13,
    (unsigned int)L"AzureAdRefreshInterval",
    (unsigned int)L"AzureAdRefreshInterval",
    1440);
  sub_1800F30BC(
    (unsigned int)v13,
    (unsigned int)L"DataDuplicationMaximumQuota",
    (unsigned int)L"DataDuplicationMaximumQuota",
    500);
  sub_1800F30BC((unsigned int)v13, (unsigned int)L"DefaultEnforcement", (unsigned int)L"DefaultEnforcement", 1);
  if ( !(unsigned __int8)sub_1800F2AD4(
                           (unsigned int)v13,
                           (unsigned int)L"DataDuplicationDirectory",
                           (unsigned int)L"DataDuplicationDirectory",
                           0,
                           0,
                           2,
                           1024) )
  {
    v12 = 1024;
    v11 = 2;
    LODWORD(v10) = 0;
    sub_1800F3280(
      (unsigned int)v13,
      (unsigned int)L"DataDuplicationDirectory",
      (unsigned int)L"DataDuplicationDirectory",
      52,
      (__int64)L"\\\\.\\GlobalRoot\\SystemRoot\\Defender Duplication Data",
      v10,
      0,
      v11,
      v12);
  }
  sub_1800F315C(
    (unsigned int)v13,
    (unsigned int)L"DataDuplicationRemoteLocation",
    (unsigned int)L"DataDuplicationRemoteLocation",
    v3);
  sub_1800F30BC(
    (unsigned int)v13,
    (unsigned int)L"DataDuplicationLocalRetentionPeriod",
    (unsigned int)L"DataDuplicationLocalRetentionPeriod",
    60);
  sub_1800F30BC((unsigned int)v13, (unsigned int)L"RebootRequired", (unsigned int)L"RebootRequired", 0);
  sub_1800F315C(
    (unsigned int)v13,
    (unsigned int)L"SecuredDevicesConfiguration",
    (unsigned int)L"SecuredDevicesConfiguration",
    v4);
  sub_1800F315C((unsigned int)v13, (unsigned int)L"CustomSupportLink", (unsigned int)L"CustomSupportLink", v5);
  sub_1800F315C((unsigned int)v13, (unsigned int)L"PoliciesLastUpdated", (unsigned int)L"PoliciesLastUpdated", v6);
  sub_1800F30BC(
    (unsigned int)v13,
    (unsigned int)L"DeduplicateAccessEvents",
    (unsigned int)L"DeduplicateAccessEvents",
    0);
  sub_1800F315C(
    (unsigned int)v13,
    (unsigned int)L"LastKnownValidPolicyPackage",
    (unsigned int)L"LastKnownValidPolicyPackage",
    v7);
  sub_1800F315C((unsigned int)v13, (unsigned int)L"AadSidCache", (unsigned int)L"AadSidCache", v8);
  sub_1800F30BC(
    (unsigned int)v13,
    (unsigned int)L"AllowExperimentalDevices",
    (unsigned int)L"AllowExperimentalDevices",
    0);
  sub_1800F30BC((unsigned int)v13, (unsigned int)L"WddState", (unsigned int)L"WddState", 2);
  sub_1800ED0D0(a1, v13);
  sub_1800EA56C(v13);
  return a1;
}

```

## disassembly

```asm
0x1800edc5c  mov     rax, rsp
0x1800edc5f  mov     [rax+10h], rbx
0x1800edc63  mov     [rax+18h], rsi
0x1800edc67  mov     [rax+20h], rdi
0x1800edc6b  push    rbp
0x1800edc6c  push    r14
0x1800edc6e  push    r15
0x1800edc70  lea     rbp, [rax-5Fh]
0x1800edc74  sub     rsp, 0C0h
0x1800edc7b  mov     rax, cs:__security_cookie
0x1800edc82  xor     rax, rsp
0x1800edc85  mov     [rbp+57h+var_20], rax
0x1800edc89  mov     rbx, rcx
0x1800edc8c  mov     [rbp+57h+var_78], rcx
0x1800edc90  xor     esi, esi
0x1800edc92  mov     r8, rdx
0x1800edc95  lea     rdx, aDeviceControl; "Device Control"
0x1800edc9c  lea     rcx, [rbp+57h+var_70]
0x1800edca0  call    sub_1800EA1FC
0x1800edca5  nop
0x1800edca6  mov     r14d, 400h
0x1800edcac  mov     [rsp+0D0h+var_A0], r14d
0x1800edcb1  mov     r9d, 12Ch
0x1800edcb7  lea     rdx, aNotificationth_0; "NotificationThrottleMin"
0x1800edcbe  mov     r8, rdx
0x1800edcc1  lea     rcx, [rbp+57h+var_70]
0x1800edcc5  call    sub_1800F30BC
0x1800edcca  mov     [rsp+0D0h+var_A0], r14d
0x1800edccf  mov     r9d, 0E10h
0x1800edcd5  lea     rdx, aNotificationth_2; "NotificationThrottleMax"
0x1800edcdc  mov     r8, rdx
0x1800edcdf  lea     rcx, [rbp+57h+var_70]
0x1800edce3  call    sub_1800F30BC
0x1800edce8  mov     edi, 480h
0x1800edced  mov     [rsp+0D0h+var_A0], edi
0x1800edcf1  mov     r9d, 168h
0x1800edcf7  lea     rdx, aPolicyrefreshf_0; "PolicyRefreshFailureInterval"
0x1800edcfe  mov     r8, rdx
0x1800edd01  lea     rcx, [rbp+57h+var_70]
0x1800edd05  call    sub_1800F30BC
0x1800edd0a  mov     [rsp+0D0h+var_A0], edi
0x1800edd0e  mov     r9d, 5A0h
0x1800edd14  lea     rdx, aAzureadrefresh_0; "AzureAdRefreshInterval"
0x1800edd1b  mov     r8, rdx
0x1800edd1e  lea     rcx, [rbp+57h+var_70]
0x1800edd22  call    sub_1800F30BC
0x1800edd27  mov     [rsp+0D0h+var_A0], edi
0x1800edd2b  mov     r9d, 1F4h
0x1800edd31  lea     rdx, aDataduplicatio_0; "DataDuplicationMaximumQuota"
0x1800edd38  mov     r8, rdx
0x1800edd3b  lea     rcx, [rbp+57h+var_70]
0x1800edd3f  call    sub_1800F30BC
0x1800edd44  mov     [rsp+0D0h+var_A0], r14d
0x1800edd49  lea     r9d, [rsi+1]
0x1800edd4d  lea     rdx, aDefaultenforce_0; "DefaultEnforcement"
0x1800edd54  mov     r8, rdx
0x1800edd57  lea     rcx, [rbp+57h+var_70]
0x1800edd5b  call    sub_1800F30BC
0x1800edd60  mov     [rsp+0D0h+var_A0], r14d
0x1800edd65  lea     r15d, [rsi+2]
0x1800edd69  mov     dword ptr [rsp+0D0h+var_A8], r15d
0x1800edd6e  mov     qword ptr [rsp+0D0h+var_B0], rsi
0x1800edd73  xor     r9d, r9d
0x1800edd76  lea     rdi, aDataduplicatio_2; "DataDuplicationDirectory"
0x1800edd7d  mov     r8, rdi
0x1800edd80  mov     rdx, rdi
0x1800edd83  lea     rcx, [rbp+57h+var_70]
0x1800edd87  call    sub_1800F2AD4
0x1800edd8c  test    al, al
0x1800edd8e  jnz     short loc_1800EDDC2
0x1800edd90  mov     [rsp+0D0h+var_90], r14d
0x1800edd95  mov     [rsp+0D0h+var_98], r15d
0x1800edd9a  mov     qword ptr [rsp+0D0h+var_A0], rsi
0x1800edd9f  mov     dword ptr [rsp+0D0h+var_A8], esi
0x1800edda3  lea     rax, aGlobalrootSyst; "\\\\.\\GlobalRoot\\SystemRoot\\Defender"...
0x1800eddaa  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800eddaf  lea     r9d, [rsi+34h]
0x1800eddb3  mov     r8, rdi
0x1800eddb6  mov     rdx, rdi
0x1800eddb9  lea     rcx, [rbp+57h+var_70]
0x1800eddbd  call    sub_1800F3280
0x1800eddc2  mov     [rsp+0D0h+var_A0], r14d
0x1800eddc7  mov     dword ptr [rsp+0D0h+var_A8], r15d
0x1800eddcc  lea     rdx, aDataduplicatio_4; "DataDuplicationRemoteLocation"
0x1800eddd3  mov     r8, rdx
0x1800eddd6  lea     rcx, [rbp+57h+var_70]
0x1800eddda  call    sub_1800F315C
0x1800edddf  mov     [rsp+0D0h+var_A0], r14d
0x1800edde4  mov     r9d, 3Ch ; '<'
0x1800eddea  lea     rdx, aDataduplicatio_6; "DataDuplicationLocalRetentionPeriod"
0x1800eddf1  mov     r8, rdx
0x1800eddf4  lea     rcx, [rbp+57h+var_70]
0x1800eddf8  call    sub_1800F30BC
0x1800eddfd  mov     esi, 28h ; '('
0x1800ede02  mov     [rsp+0D0h+var_A0], esi
0x1800ede06  xor     r9d, r9d
0x1800ede09  lea     rdx, aRebootrequired; "RebootRequired"
0x1800ede10  mov     r8, rdx
0x1800ede13  lea     rcx, [rbp+57h+var_70]
0x1800ede17  call    sub_1800F30BC
0x1800ede1c  mov     [rsp+0D0h+var_A0], r14d
0x1800ede21  mov     dword ptr [rsp+0D0h+var_A8], r15d
0x1800ede26  lea     rdx, aSecureddevices_0; "SecuredDevicesConfiguration"
0x1800ede2d  mov     r8, rdx
0x1800ede30  lea     rcx, [rbp+57h+var_70]
0x1800ede34  call    sub_1800F315C
0x1800ede39  mov     [rsp+0D0h+var_A0], r14d
0x1800ede3e  mov     dword ptr [rsp+0D0h+var_A8], r15d
0x1800ede43  lea     rdx, aCustomsupportl_0; "CustomSupportLink"
0x1800ede4a  mov     r8, rdx
0x1800ede4d  lea     rcx, [rbp+57h+var_70]
0x1800ede51  call    sub_1800F315C
0x1800ede56  mov     [rsp+0D0h+var_A0], esi
0x1800ede5a  lea     edi, [rsi-24h]
0x1800ede5d  mov     dword ptr [rsp+0D0h+var_A8], edi
0x1800ede61  lea     rdx, aPolicieslastup; "PoliciesLastUpdated"
0x1800ede68  mov     r8, rdx
0x1800ede6b  lea     rcx, [rbp+57h+var_70]
0x1800ede6f  call    sub_1800F315C
0x1800ede74  mov     [rsp+0D0h+var_A0], r14d
0x1800ede79  xor     r9d, r9d
0x1800ede7c  lea     rdx, aDeduplicateacc_0; "DeduplicateAccessEvents"
0x1800ede83  mov     r8, rdx
0x1800ede86  lea     rcx, [rbp+57h+var_70]
0x1800ede8a  call    sub_1800F30BC
0x1800ede8f  mov     [rsp+0D0h+var_A0], esi
0x1800ede93  mov     dword ptr [rsp+0D0h+var_A8], r15d
0x1800ede98  lea     rdx, aLastknownvalid; "LastKnownValidPolicyPackage"
0x1800ede9f  mov     r8, rdx
0x1800edea2  lea     rcx, [rbp+57h+var_70]
0x1800edea6  call    sub_1800F315C
0x1800edeab  mov     [rsp+0D0h+var_A0], esi
0x1800edeaf  mov     dword ptr [rsp+0D0h+var_A8], edi
0x1800edeb3  lea     rdx, aAadsidcache; "AadSidCache"
0x1800edeba  mov     r8, rdx
0x1800edebd  lea     rcx, [rbp+57h+var_70]
0x1800edec1  call    sub_1800F315C
0x1800edec6  mov     [rsp+0D0h+var_A0], r14d
0x1800edecb  xor     r9d, r9d
0x1800edece  lea     rdx, aAllowexperimen_0; "AllowExperimentalDevices"
0x1800eded5  mov     r8, rdx
0x1800eded8  lea     rcx, [rbp+57h+var_70]
0x1800ededc  call    sub_1800F30BC
0x1800edee1  mov     [rsp+0D0h+var_A0], esi
0x1800edee5  mov     r9d, r15d
0x1800edee8  lea     rdx, aWddstate; "WddState"
0x1800edeef  mov     r8, rdx
0x1800edef2  lea     rcx, [rbp+57h+var_70]
0x1800edef6  call    sub_1800F30BC
0x1800edefb  lea     rdx, [rbp+57h+var_70]
0x1800edeff  mov     rcx, rbx
0x1800edf02  call    sub_1800ED0D0
0x1800edf07  nop
0x1800edf08  lea     rcx, [rbp+57h+var_70]
0x1800edf0c  call    sub_1800EA56C
0x1800edf11  mov     rax, rbx
0x1800edf14  mov     rcx, [rbp+57h+var_20]
0x1800edf18  xor     rcx, rsp; StackCookie
0x1800edf1b  call    __security_check_cookie
0x1800edf20  lea     r11, [rsp+0D0h+var_10]
0x1800edf28  mov     rbx, [r11+28h]
0x1800edf2c  mov     rsi, [r11+30h]
0x1800edf30  mov     rdi, [r11+38h]
0x1800edf34  mov     rsp, r11
0x1800edf37  pop     r15
0x1800edf39  pop     r14
0x1800edf3b  pop     rbp
0x1800edf3c  retn
```
