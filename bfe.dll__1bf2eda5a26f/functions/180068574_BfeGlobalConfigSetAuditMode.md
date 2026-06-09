# BfeGlobalConfigSetAuditMode

- ea: `0x180068574`
- end: `0x1800687f9`
- name: `BfeGlobalConfigSetAuditMode`
- size: `645`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180062bc0`

## callees

- `0x180001008`
- `0x180010360`
- `0x18001236c`
- `0x180018b74`
- `0x180034650`
- `0x1800390dc`
- `0x180058b30`
- `0x180068574`
- `0x180068800`
- `0x180068844`
- `0x1800688a0`
- `0x18006cdc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180068659`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180068659`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006866f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006866f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180068638`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800686c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180068638`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800686c6`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18006861c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18006861c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800685fc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800685fc`

## string_xrefs

- `0x1800686d2`: `BfeGlobalConfigSetAuditMode`
- `0x1800687cf`: `BfeGlobalConfigSetAuditMode`
- `0x180068711`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`
- `0x18006874a`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`

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

  v1 = HIDWORD(qword_1800F2668[215]);
  if ( (qword_1800F2668[369] & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = qword_1800F2668[369] & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_Netsec_AuditMode_Hardening__private_IsEnabledDeviceUsageNoInline();
  if ( !IsEnabledDeviceUsageNoInline )
  {
    v5 = BfeAccessCheck((char *)qword_1800F2668[173], 0x400u, 0);
    if ( !v5 )
    {
      v5 = BfeRegSetDWord(
             v4,
             L"System\\CurrentControlSet\\Services\\BFE\\Parameters\\Policy\\Options",
             L"EnableAuditMode",
             *(_DWORD *)(a1 + 4));
      if ( !v5 )
      {
        HIDWORD(qword_1800F2668[215]) = *(_DWORD *)(a1 + 4);
        return v5;
      }
    }
    goto LABEL_15;
  }
  v5 = BfeAccessCheck((char *)qword_1800F2668[173], 0x400u, 0);
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
            AcquireSRWLockExclusive((PSRWLOCK)&qword_1800F2668[217]);
            HIDWORD(qword_1800F2668[215]) = *(_DWORD *)(a1 + 4);
            ReleaseSRWLockExclusive((PSRWLOCK)&qword_1800F2668[217]);
            if ( (unsigned int)dword_1800EB148 >= 6 )
            {
              v17 = *(_DWORD *)(a1 + 4);
              v18 = &v17;
              v19 = 4;
              tlgWriteTransfer_EtwEventWriteTransfer(v9, (unsigned int)byte_1800DFFB9, v10, v11);
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
  if ( (qword_1800F2668[369] & 0x10) != 0 )
    v12 = qword_1800F2668[369] & 1;
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
            SHIDWORD(qword_1800F2668[215]));
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
0x180068574  push    rbp
0x180068576  push    rbx
0x180068577  push    rsi
0x180068578  push    rdi
0x180068579  lea     rbp, [rsp-3Fh]
0x18006857e  sub     rsp, 88h
0x180068585  mov     rax, cs:__security_cookie
0x18006858c  xor     rax, rsp
0x18006858f  mov     [rbp+57h+var_30], rax
0x180068593  mov     esi, dword ptr cs:qword_1800F2668+6BCh
0x180068599  mov     rdi, rcx
0x18006859c  mov     eax, dword ptr cs:qword_1800F2668+0B88h
0x1800685a2  test    al, 10h
0x1800685a4  jz      short loc_1800685AB
0x1800685a6  and     eax, 1
0x1800685a9  jmp     short loc_1800685B0
0x1800685ab  call    Feature_Netsec_AuditMode_Hardening__private_IsEnabledDeviceUsageNoInline
0x1800685b0  mov     rcx, cs:qword_1800F2668+568h; pSecurityDescriptor
0x1800685b7  xor     r8d, r8d
0x1800685ba  mov     edx, 400h
0x1800685bf  test    eax, eax
0x1800685c1  jz      loc_1800686F9
0x1800685c7  call    BfeAccessCheck
0x1800685cc  mov     rbx, rax
0x1800685cf  test    rax, rax
0x1800685d2  jnz     loc_1800686EA
0x1800685d8  call    BfeSessionGetToken
0x1800685dd  mov     rbx, rax
0x1800685e0  test    rax, rax
0x1800685e3  jz      loc_1800686CC
0x1800685e9  lea     rdx, [rbp+57h+Sid]; Sid
0x1800685ed  mov     [rbp+57h+Sid], 0
0x1800685f5  lea     rcx, StringSid; "S-1-5-80-3088073201-1464728630-18798138"...
0x1800685fc  call    cs:__imp_ConvertStringSidToSidW
0x180068602  test    eax, eax
0x180068604  jz      loc_1800686CC
0x18006860a  mov     rdx, [rbp+57h+Sid]; SidToCheck
0x18006860e  lea     r8, [rbp+57h+IsMember]; IsMember
0x180068612  mov     rcx, rbx; TokenHandle
0x180068615  mov     [rbp+57h+IsMember], 0
0x18006861c  call    cs:__imp_CheckTokenMembership
0x180068622  test    eax, eax
0x180068624  jz      loc_1800686C2
0x18006862a  cmp     [rbp+57h+IsMember], 0
0x18006862e  jz      loc_1800686C2
0x180068634  mov     rcx, [rbp+57h+Sid]; hMem
0x180068638  call    cs:__imp_LocalFree
0x18006863e  mov     ecx, [rdi+4]
0x180068641  call    BfeDriverSetFirewallAuditMode
0x180068646  mov     rbx, rax
0x180068649  test    rax, rax
0x18006864c  jnz     loc_1800686EA
0x180068652  lea     rcx, qword_1800F2668+6C8h; SRWLock
0x180068659  call    cs:__imp_AcquireSRWLockExclusive
0x18006865f  mov     eax, [rdi+4]
0x180068662  lea     rcx, qword_1800F2668+6C8h; SRWLock
0x180068669  mov     dword ptr cs:qword_1800F2668+6BCh, eax
0x18006866f  call    cs:__imp_ReleaseSRWLockExclusive
0x180068675  mov     eax, cs:dword_1800EB148
0x18006867b  test    eax, eax
0x18006867d  jz      loc_1800687DE
0x180068683  mov     eax, cs:dword_1800EB148
0x180068689  cmp     eax, 5
0x18006868c  jbe     loc_1800687DE
0x180068692  mov     eax, [rdi+4]
0x180068695  lea     rdx, byte_1800DFFB9
0x18006869c  mov     [rbp+57h+var_64], eax
0x18006869f  lea     rax, [rbp+57h+var_64]
0x1800686a3  mov     [rbp+57h+var_40], rax
0x1800686a7  lea     rax, [rbp+57h+var_60]
0x1800686ab  mov     [rsp+0A0h+var_78], rax
0x1800686b0  mov     [rbp+57h+var_38], 4
0x1800686b8  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800686bd  jmp     loc_1800687DE
0x1800686c2  mov     rcx, [rbp+57h+Sid]; hMem
0x1800686c6  call    cs:__imp_LocalFree
0x1800686cc  mov     r8d, 5
0x1800686d2  lea     rdx, aBfeglobalconfi_1; "BfeGlobalConfigSetAuditMode"
0x1800686d9  call    WfpReportSysErrorAsWinError
0x1800686de  mov     rbx, rax
0x1800686e1  test    rax, rax
0x1800686e4  jz      loc_1800687DE
0x1800686ea  mov     eax, dword ptr cs:qword_1800F2668+0B88h
0x1800686f0  test    al, 10h
0x1800686f2  jz      short loc_180068733
0x1800686f4  and     eax, 1
0x1800686f7  jmp     short loc_180068738
0x1800686f9  call    BfeAccessCheck
0x1800686fe  mov     rbx, rax
0x180068701  test    rax, rax
0x180068704  jnz     short loc_1800686EA
0x180068706  mov     r9d, [rdi+4]
0x18006870a  lea     r8, aEnableauditmod; "EnableAuditMode"
0x180068711  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\BF"...
0x180068718  call    BfeRegSetDWord
0x18006871d  mov     rbx, rax
0x180068720  test    rax, rax
0x180068723  jnz     short loc_1800686EA
0x180068725  mov     eax, [rdi+4]
0x180068728  mov     dword ptr cs:qword_1800F2668+6BCh, eax
0x18006872e  jmp     loc_1800687DE
0x180068733  call    Feature_Netsec_AuditMode_Hardening__private_IsEnabledDeviceUsageNoInline
0x180068738  test    eax, eax
0x18006873a  jnz     short loc_180068794
0x18006873c  mov     r9d, dword ptr cs:qword_1800F2668+6BCh
0x180068743  lea     r8, aEnableauditmod; "EnableAuditMode"
0x18006874a  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\BF"...
0x180068751  call    BfeRegSetDWord
0x180068756  test    rax, rax
0x180068759  jz      short loc_1800687CA
0x18006875b  mov     rcx, cs:WPP_GLOBAL_Control
0x180068762  lea     rdx, WPP_GLOBAL_Control
0x180068769  cmp     rcx, rdx
0x18006876c  jz      short loc_1800687CA
0x18006876e  cmp     byte ptr [rcx+19h], 4
0x180068772  jb      short loc_1800687CA
0x180068774  test    byte ptr [rcx+1Ch], 2
0x180068778  jz      short loc_1800687CA
0x18006877a  mov     rcx, [rcx+10h]
0x18006877e  lea     r8, WPP_4b90860d76c93cdfbba6001e3612bd36_Traceguids
0x180068785  mov     r9d, eax
0x180068788  mov     edx, 0Ch
0x18006878d  call    WPP_SF_D
0x180068792  jmp     short loc_1800687CA
0x180068794  mov     rcx, cs:WPP_GLOBAL_Control
0x18006879b  lea     rdx, WPP_GLOBAL_Control
0x1800687a2  cmp     rcx, rdx
0x1800687a5  jz      short loc_1800687CA
0x1800687a7  cmp     byte ptr [rcx+19h], 4
0x1800687ab  jb      short loc_1800687CA
0x1800687ad  test    byte ptr [rcx+1Ch], 2
0x1800687b1  jz      short loc_1800687CA
0x1800687b3  mov     eax, [rdi+4]
0x1800687b6  mov     r9d, ebx
0x1800687b9  mov     rcx, [rcx+10h]
0x1800687bd  mov     dword ptr [rsp+0A0h+var_78], esi
0x1800687c1  mov     [rsp+0A0h+var_80], eax
0x1800687c5  call    WPP_SF_ddd
0x1800687ca  test    rbx, rbx
0x1800687cd  jz      short loc_1800687DE
0x1800687cf  lea     rdx, aBfeglobalconfi_1; "BfeGlobalConfigSetAuditMode"
0x1800687d6  mov     rcx, rbx
0x1800687d9  call    WfpReportError
0x1800687de  mov     rax, rbx
0x1800687e1  mov     rcx, [rbp+57h+var_30]
0x1800687e5  xor     rcx, rsp; StackCookie
0x1800687e8  call    __security_check_cookie
0x1800687ed  add     rsp, 88h
0x1800687f4  pop     rdi
0x1800687f5  pop     rsi
0x1800687f6  pop     rbx
0x1800687f7  pop     rbp
0x1800687f8  retn
```
