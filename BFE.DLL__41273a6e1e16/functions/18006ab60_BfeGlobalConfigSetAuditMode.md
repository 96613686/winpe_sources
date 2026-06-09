# BfeGlobalConfigSetAuditMode

- ea: `0x18006ab60`
- end: `0x18006ae0a`
- name: `BfeGlobalConfigSetAuditMode`
- size: `682`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180064f10`

## callees

- `0x180001008`
- `0x180010d60`
- `0x180012d8c`
- `0x1800197d0`
- `0x180034554`
- `0x180037954`
- `0x18005aa60`
- `0x18006ab60`
- `0x18006ae10`
- `0x18006ae58`
- `0x18006aeb8`
- `0x18006f49c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006ac57`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006ac57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006ac73`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006ac73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ac30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006acd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ac30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006acd0`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18006ac0e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18006ac0e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18006abe8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18006abe8`

## string_xrefs

- `0x18006ace2`: `BfeGlobalConfigSetAuditMode`
- `0x18006addf`: `BfeGlobalConfigSetAuditMode`
- `0x18006ad21`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`
- `0x18006ad5a`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`

## pseudocode

```c
__int64 __fastcall BfeGlobalConfigSetAuditMode(__int64 a1)
{
  int v1; // esi
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // r8
  __int64 v7; // rcx
  void *Token; // rbx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  int v12; // eax
  __int64 v13; // rax
  PSID Sid; // [rsp+30h] [rbp-19h] BYREF
  WINBOOL IsMember; // [rsp+38h] [rbp-11h] BYREF
  int v17; // [rsp+3Ch] [rbp-Dh] BYREF
  int *v18; // [rsp+60h] [rbp+17h]
  __int64 v19; // [rsp+68h] [rbp+1Fh]

  v1 = DWORD1(gBfeGlobalConfigComponent);
  if ( (Feature_Netsec_AuditMode_Hardening__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_Netsec_AuditMode_Hardening__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_Netsec_AuditMode_Hardening__private_IsEnabledDeviceUsageNoInline();
  if ( !IsEnabledDeviceUsageNoInline )
  {
    v5 = BfeAccessCheck(ParentDescriptor);
    if ( !v5 )
    {
      v5 = BfeRegSetDWord(
             v4,
             L"System\\CurrentControlSet\\Services\\BFE\\Parameters\\Policy\\Options",
             L"EnableAuditMode",
             *(unsigned int *)(a1 + 4));
      if ( !v5 )
      {
        DWORD1(gBfeGlobalConfigComponent) = *(_DWORD *)(a1 + 4);
        return v5;
      }
    }
    goto LABEL_15;
  }
  v5 = BfeAccessCheck(ParentDescriptor);
  if ( !v5 )
  {
    Token = (void *)BfeSessionGetToken();
    if ( Token )
    {
      Sid = 0;
      if ( ConvertStringSidToSidW(L"S-1-5-80-3088073201-1464728630-1879813800-1107566885-823218052", &Sid) )
      {
        IsMember = 0;
        if ( CheckTokenMembership(Token, Sid, &IsMember) && IsMember )
        {
          LocalFree(Sid);
          v5 = BfeDriverSetFirewallAuditMode(*(unsigned int *)(a1 + 4));
          if ( !v5 )
          {
            AcquireSRWLockExclusive(&stru_1800F5D50);
            DWORD1(gBfeGlobalConfigComponent) = *(_DWORD *)(a1 + 4);
            ReleaseSRWLockExclusive(&stru_1800F5D50);
            if ( (unsigned int)dword_1800EE148 >= 6 )
            {
              v17 = *(_DWORD *)(a1 + 4);
              v18 = &v17;
              v19 = 4;
              tlgWriteTransfer_EtwEventWriteTransfer(v9, (unsigned int)byte_1800E2FC9, v10, v11);
            }
            return v5;
          }
          goto LABEL_15;
        }
        LocalFree(Sid);
      }
    }
    v5 = WfpReportSysErrorAsWinError(v7, "BfeGlobalConfigSetAuditMode", 5);
    if ( !v5 )
      return v5;
  }
LABEL_15:
  if ( (Feature_Netsec_AuditMode_Hardening__private_featureState & 0x10) != 0 )
    v12 = Feature_Netsec_AuditMode_Hardening__private_featureState & 1;
  else
    v12 = Feature_Netsec_AuditMode_Hardening__private_IsEnabledDeviceUsageNoInline();
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_ddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        &WPP_GLOBAL_Control,
        v6,
        (unsigned int)v5,
        *(_DWORD *)(a1 + 4),
        v1);
    }
  }
  else
  {
    v13 = BfeRegSetDWord(
            v4,
            L"System\\CurrentControlSet\\Services\\BFE\\Parameters\\Policy\\Options",
            L"EnableAuditMode",
            DWORD1(gBfeGlobalConfigComponent));
    if ( v13
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_4b90860d76c93cdfbba6001e3612bd36_Traceguids,
        (unsigned int)v13);
    }
  }
  WfpReportError(v5, "BfeGlobalConfigSetAuditMode");
  return v5;
}

```

## disassembly

```asm
0x18006ab60  push    rbp
0x18006ab62  push    rbx
0x18006ab63  push    rsi
0x18006ab64  push    rdi
0x18006ab65  lea     rbp, [rsp-3Fh]
0x18006ab6a  sub     rsp, 88h
0x18006ab71  mov     rax, cs:__security_cookie
0x18006ab78  xor     rax, rsp
0x18006ab7b  mov     [rbp+57h+var_30], rax
0x18006ab7f  mov     esi, dword ptr cs:gBfeGlobalConfigComponent+4
0x18006ab85  mov     rdi, rcx
0x18006ab88  mov     eax, cs:Feature_Netsec_AuditMode_Hardening__private_featureState
0x18006ab8e  test    al, 10h
0x18006ab90  jz      short loc_18006AB97
0x18006ab92  and     eax, 1
0x18006ab95  jmp     short loc_18006AB9C
0x18006ab97  call    Feature_Netsec_AuditMode_Hardening__private_IsEnabledDeviceUsageNoInline
0x18006ab9c  mov     rcx, cs:ParentDescriptor; pSecurityDescriptor
0x18006aba3  xor     r8d, r8d
0x18006aba6  mov     edx, 400h
0x18006abab  test    eax, eax
0x18006abad  jz      loc_18006AD09
0x18006abb3  call    BfeAccessCheck
0x18006abb8  mov     rbx, rax
0x18006abbb  test    rax, rax
0x18006abbe  jnz     loc_18006ACFA
0x18006abc4  call    BfeSessionGetToken
0x18006abc9  mov     rbx, rax
0x18006abcc  test    rax, rax
0x18006abcf  jz      loc_18006ACDC
0x18006abd5  lea     rdx, [rbp+57h+Sid]; Sid
0x18006abd9  mov     [rbp+57h+Sid], 0
0x18006abe1  lea     rcx, StringSid; "S-1-5-80-3088073201-1464728630-18798138"...
0x18006abe8  call    cs:__imp_ConvertStringSidToSidW
0x18006abef  nop     dword ptr [rax+rax+00h]
0x18006abf4  test    eax, eax
0x18006abf6  jz      loc_18006ACDC
0x18006abfc  mov     rdx, [rbp+57h+Sid]; SidToCheck
0x18006ac00  lea     r8, [rbp+57h+IsMember]; IsMember
0x18006ac04  mov     rcx, rbx; TokenHandle
0x18006ac07  mov     [rbp+57h+IsMember], 0
0x18006ac0e  call    cs:__imp_CheckTokenMembership
0x18006ac15  nop     dword ptr [rax+rax+00h]
0x18006ac1a  test    eax, eax
0x18006ac1c  jz      loc_18006ACCC
0x18006ac22  cmp     [rbp+57h+IsMember], 0
0x18006ac26  jz      loc_18006ACCC
0x18006ac2c  mov     rcx, [rbp+57h+Sid]; hMem
0x18006ac30  call    cs:__imp_LocalFree
0x18006ac37  nop     dword ptr [rax+rax+00h]
0x18006ac3c  mov     ecx, [rdi+4]
0x18006ac3f  call    BfeDriverSetFirewallAuditMode
0x18006ac44  mov     rbx, rax
0x18006ac47  test    rax, rax
0x18006ac4a  jnz     loc_18006ACFA
0x18006ac50  lea     rcx, stru_1800F5D50; SRWLock
0x18006ac57  call    cs:__imp_AcquireSRWLockExclusive
0x18006ac5e  nop     dword ptr [rax+rax+00h]
0x18006ac63  mov     eax, [rdi+4]
0x18006ac66  lea     rcx, stru_1800F5D50; SRWLock
0x18006ac6d  mov     dword ptr cs:gBfeGlobalConfigComponent+4, eax
0x18006ac73  call    cs:__imp_ReleaseSRWLockExclusive
0x18006ac7a  nop     dword ptr [rax+rax+00h]
0x18006ac7f  mov     eax, cs:dword_1800EE148
0x18006ac85  test    eax, eax
0x18006ac87  jz      loc_18006ADEE
0x18006ac8d  mov     eax, cs:dword_1800EE148
0x18006ac93  cmp     eax, 5
0x18006ac96  jbe     loc_18006ADEE
0x18006ac9c  mov     eax, [rdi+4]
0x18006ac9f  lea     rdx, byte_1800E2FC9
0x18006aca6  mov     [rbp+57h+var_64], eax
0x18006aca9  lea     rax, [rbp+57h+var_64]
0x18006acad  mov     [rbp+57h+var_40], rax
0x18006acb1  lea     rax, [rbp+57h+var_60]
0x18006acb5  mov     [rsp+0A0h+var_78], rax
0x18006acba  mov     [rbp+57h+var_38], 4
0x18006acc2  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18006acc7  jmp     loc_18006ADEE
0x18006accc  mov     rcx, [rbp+57h+Sid]; hMem
0x18006acd0  call    cs:__imp_LocalFree
0x18006acd7  nop     dword ptr [rax+rax+00h]
0x18006acdc  mov     r8d, 5
0x18006ace2  lea     rdx, aBfeglobalconfi_1; "BfeGlobalConfigSetAuditMode"
0x18006ace9  call    WfpReportSysErrorAsWinError
0x18006acee  mov     rbx, rax
0x18006acf1  test    rax, rax
0x18006acf4  jz      loc_18006ADEE
0x18006acfa  mov     eax, cs:Feature_Netsec_AuditMode_Hardening__private_featureState
0x18006ad00  test    al, 10h
0x18006ad02  jz      short loc_18006AD43
0x18006ad04  and     eax, 1
0x18006ad07  jmp     short loc_18006AD48
0x18006ad09  call    BfeAccessCheck
0x18006ad0e  mov     rbx, rax
0x18006ad11  test    rax, rax
0x18006ad14  jnz     short loc_18006ACFA
0x18006ad16  mov     r9d, [rdi+4]
0x18006ad1a  lea     r8, aEnableauditmod; "EnableAuditMode"
0x18006ad21  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\BF"...
0x18006ad28  call    BfeRegSetDWord
0x18006ad2d  mov     rbx, rax
0x18006ad30  test    rax, rax
0x18006ad33  jnz     short loc_18006ACFA
0x18006ad35  mov     eax, [rdi+4]
0x18006ad38  mov     dword ptr cs:gBfeGlobalConfigComponent+4, eax
0x18006ad3e  jmp     loc_18006ADEE
0x18006ad43  call    Feature_Netsec_AuditMode_Hardening__private_IsEnabledDeviceUsageNoInline
0x18006ad48  test    eax, eax
0x18006ad4a  jnz     short loc_18006ADA4
0x18006ad4c  mov     r9d, dword ptr cs:gBfeGlobalConfigComponent+4
0x18006ad53  lea     r8, aEnableauditmod; "EnableAuditMode"
0x18006ad5a  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\BF"...
0x18006ad61  call    BfeRegSetDWord
0x18006ad66  test    rax, rax
0x18006ad69  jz      short loc_18006ADDA
0x18006ad6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ad72  lea     rdx, WPP_GLOBAL_Control
0x18006ad79  cmp     rcx, rdx
0x18006ad7c  jz      short loc_18006ADDA
0x18006ad7e  cmp     byte ptr [rcx+19h], 4
0x18006ad82  jb      short loc_18006ADDA
0x18006ad84  test    byte ptr [rcx+1Ch], 2
0x18006ad88  jz      short loc_18006ADDA
0x18006ad8a  mov     rcx, [rcx+10h]
0x18006ad8e  lea     r8, WPP_4b90860d76c93cdfbba6001e3612bd36_Traceguids
0x18006ad95  mov     r9d, eax
0x18006ad98  mov     edx, 0Ch
0x18006ad9d  call    WPP_SF_D
0x18006ada2  jmp     short loc_18006ADDA
0x18006ada4  mov     rcx, cs:WPP_GLOBAL_Control
0x18006adab  lea     rdx, WPP_GLOBAL_Control
0x18006adb2  cmp     rcx, rdx
0x18006adb5  jz      short loc_18006ADDA
0x18006adb7  cmp     byte ptr [rcx+19h], 4
0x18006adbb  jb      short loc_18006ADDA
0x18006adbd  test    byte ptr [rcx+1Ch], 2
0x18006adc1  jz      short loc_18006ADDA
0x18006adc3  mov     eax, [rdi+4]
0x18006adc6  mov     r9d, ebx
0x18006adc9  mov     rcx, [rcx+10h]
0x18006adcd  mov     dword ptr [rsp+0A0h+var_78], esi
0x18006add1  mov     [rsp+0A0h+var_80], eax
0x18006add5  call    WPP_SF_ddd
0x18006adda  test    rbx, rbx
0x18006addd  jz      short loc_18006ADEE
0x18006addf  lea     rdx, aBfeglobalconfi_1; "BfeGlobalConfigSetAuditMode"
0x18006ade6  mov     rcx, rbx
0x18006ade9  call    WfpReportError
0x18006adee  mov     rax, rbx
0x18006adf1  mov     rcx, [rbp+57h+var_30]
0x18006adf5  xor     rcx, rsp; StackCookie
0x18006adf8  call    __security_check_cookie
0x18006adfd  add     rsp, 88h
0x18006ae04  pop     rdi
0x18006ae05  pop     rsi
0x18006ae06  pop     rbx
0x18006ae07  pop     rbp
0x18006ae08  retn
```
