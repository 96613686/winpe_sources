# Windows::Internal::AssignedAccess::AssignedAccessConfiguration::HandleMembershipCheckResult(long,ushort const *,ushort const *,bool,bool &)

- ea: `0x180080a30`
- end: `0x180080bb8`
- name: `?HandleMembershipCheckResult@AssignedAccessConfiguration@AssignedAccess@Internal@Windows@@SAJJPEBG0_NAEA_N@Z`
- size: `392`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *, const unsigned __int16 *, bool, bool *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18007eff4`
- `0x18007f1a4`
- `0x180080320`

## callees

- `0x18000b6b4`
- `0x18007da90`
- `0x18007daf0`
- `0x18007db50`
- `0x18007dc10`
- `0x180080a30`
- `0x1800814a4`

## import_xrefs

- `policymanager!PolicyManager_GetPolicyInt` at `0x180080a6b`
- `policymanager!PolicyManager_GetPolicyInt` at `0x180080a6b`

## string_xrefs

- `0x180080a7f`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfiguration.cpp`
- `0x180080adc`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfiguration.cpp`
- `0x180080b11`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfiguration.cpp`
- `0x180080b49`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfiguration.cpp`
- `0x180080a5d`: `AADGroupMembershipCacheValidityInDays`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfiguration::HandleMembershipCheckResult(
        int a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4,
        bool *a5)
{
  int v8; // ebx
  int PolicyInt; // eax
  unsigned int v10; // edi
  int v12; // eax
  unsigned int v13; // edi
  int v14; // eax
  unsigned int v15; // edi
  bool *v16; // rdi
  int v17; // eax
  __int64 v18; // rcx
  unsigned int v19; // ebx
  int v20; // [rsp+20h] [rbp-38h]
  int v21; // [rsp+20h] [rbp-38h]
  int v22; // [rsp+20h] [rbp-38h]
  int v23; // [rsp+20h] [rbp-38h]
  unsigned int v24[10]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v26; // [rsp+60h] [rbp+8h] BYREF

  v26 = a1;
  v8 = a1;
  v24[0] = 0;
  PolicyInt = PolicyManager_GetPolicyInt(L"MixedReality", L"AADGroupMembershipCacheValidityInDays", v24);
  v10 = PolicyInt;
  if ( PolicyInt < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x203,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfiguration.cpp",
      (const char *)(unsigned int)PolicyInt,
      v20);
    return v10;
  }
  if ( v24[0] )
  {
    if ( v8 >= 0 )
    {
      if ( *a5 )
      {
        v12 = Windows::Internal::AssignedAccess::AssignedAccessConfiguration::PerformAADGroupMembershipOperationInCache(
                v24[0],
                (__int64)a2,
                (__int64)a3,
                1u,
                (char *)a5);
        v13 = v12;
        if ( v12 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x20F,
            (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfiguration.cpp",
            (const char *)(unsigned int)v12,
            v21);
          return v13;
        }
      }
      else
      {
        v14 = Windows::Internal::AssignedAccess::AssignedAccessConfiguration::PerformAADGroupMembershipOperationInCache(
                v24[0],
                (__int64)a2,
                (__int64)a3,
                2u,
                (char *)a5);
        v15 = v14;
        if ( v14 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x214,
            (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfiguration.cpp",
            (const char *)(unsigned int)v14,
            v22);
          return v15;
        }
      }
      return (unsigned int)v8;
    }
    v16 = a5;
    v17 = Windows::Internal::AssignedAccess::AssignedAccessConfiguration::PerformAADGroupMembershipOperationInCache(
            v24[0],
            (__int64)a2,
            (__int64)a3,
            0,
            (char *)a5);
    v19 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21A,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfiguration.cpp",
        (const char *)(unsigned int)v17,
        v23);
      return v19;
    }
    if ( *v16 )
    {
      AssignedAccessTelemetry::AssignedAccessConfiguration_MembershipCheck_IgnoreFailure<unsigned short const (&)[23],long &>(
        v18,
        &v26);
    }
    else if ( a4 )
    {
      AssignedAccessTelemetry::AssignedAccessConfiguration_MembershipCheck_IgnoreFailure<unsigned short const (&)[34],long &>(
        v18,
        &v26);
    }
    else
    {
      AssignedAccessTelemetry::AssignedAccessConfiguration_MembershipCheck_IgnoreFailure<unsigned short const (&)[27],long &>(
        v18,
        &v26);
    }
  }
  else
  {
    if ( v8 == -2147483638 || !a4 )
      return (unsigned int)v8;
    AssignedAccessTelemetry::AssignedAccessConfiguration_MembershipCheck_IgnoreFailure<unsigned short const (&)[37],long &>(
      v24[0],
      &v26);
  }
  return 0;
}

```

## disassembly

```asm
0x180080a30  mov     rax, rsp
0x180080a33  mov     [rax+10h], rbx
0x180080a37  mov     [rax+18h], rsi
0x180080a3b  mov     [rax+8], ecx
0x180080a3e  push    rdi
0x180080a3f  push    r14
0x180080a41  push    r15
0x180080a43  sub     rsp, 40h
0x180080a47  mov     sil, r9b
0x180080a4a  mov     r14, r8
0x180080a4d  mov     r15, rdx
0x180080a50  mov     ebx, ecx
0x180080a52  mov     dword ptr [rax-28h], 0
0x180080a59  lea     r8, [rax-28h]
0x180080a5d  lea     rdx, aAadgroupmember; "AADGroupMembershipCacheValidityInDays"
0x180080a64  lea     rcx, aMixedreality; "MixedReality"
0x180080a6b  call    cs:__imp_PolicyManager_GetPolicyInt
0x180080a71  mov     edi, eax
0x180080a73  test    eax, eax
0x180080a75  jns     short loc_180080A97
0x180080a77  mov     rcx, [rsp+58h]; this
0x180080a7c  mov     r9d, eax; char *
0x180080a7f  lea     r8, aOnecoreuapBase_44; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180080a86  mov     edx, 203h; void *
0x180080a8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080a90  mov     eax, edi
0x180080a92  jmp     loc_180080BA3
0x180080a97  mov     ecx, [rsp+58h+var_28]
0x180080a9b  test    ecx, ecx
0x180080a9d  jz      loc_180080B82
0x180080aa3  mov     r8, r14
0x180080aa6  mov     rdx, r15
0x180080aa9  test    ebx, ebx
0x180080aab  js      short loc_180080B26
0x180080aad  mov     rax, [rsp+58h+arg_20]
0x180080ab5  mov     qword ptr [rsp+58h+var_38], rax; int
0x180080aba  cmp     byte ptr [rax], 0
0x180080abd  jz      short loc_180080AF4
0x180080abf  mov     r9d, 1
0x180080ac5  call    ?PerformAADGroupMembershipOperationInCache@AssignedAccessConfiguration@AssignedAccess@Internal@Windows@@CAJKPEBG0W4AADGroupMembershipCacheOperation@1234@AEA_N@Z; Windows::Internal::AssignedAccess::AssignedAccessConfiguration::PerformAADGroupMembershipOperationInCache(ulong,ushort const *,ushort const *,Windows::Internal::AssignedAccess::AssignedAccessConfiguration::AADGroupMembershipCacheOperation,bool &)
0x180080aca  mov     edi, eax
0x180080acc  test    eax, eax
0x180080ace  jns     loc_180080B9B
0x180080ad4  mov     rcx, [rsp+58h]; this
0x180080ad9  mov     r9d, eax; char *
0x180080adc  lea     r8, aOnecoreuapBase_44; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180080ae3  mov     edx, 20Fh; void *
0x180080ae8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080aed  mov     eax, edi
0x180080aef  jmp     loc_180080BA3
0x180080af4  mov     r9d, 2
0x180080afa  call    ?PerformAADGroupMembershipOperationInCache@AssignedAccessConfiguration@AssignedAccess@Internal@Windows@@CAJKPEBG0W4AADGroupMembershipCacheOperation@1234@AEA_N@Z; Windows::Internal::AssignedAccess::AssignedAccessConfiguration::PerformAADGroupMembershipOperationInCache(ulong,ushort const *,ushort const *,Windows::Internal::AssignedAccess::AssignedAccessConfiguration::AADGroupMembershipCacheOperation,bool &)
0x180080aff  mov     edi, eax
0x180080b01  test    eax, eax
0x180080b03  jns     loc_180080B9B
0x180080b09  mov     rcx, [rsp+58h]; this
0x180080b0e  mov     r9d, eax; char *
0x180080b11  lea     r8, aOnecoreuapBase_44; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180080b18  mov     edx, 214h; void *
0x180080b1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080b22  mov     eax, edi
0x180080b24  jmp     short loc_180080BA3
0x180080b26  mov     rdi, [rsp+58h+arg_20]
0x180080b2e  mov     qword ptr [rsp+58h+var_38], rdi; int
0x180080b33  xor     r9d, r9d
0x180080b36  call    ?PerformAADGroupMembershipOperationInCache@AssignedAccessConfiguration@AssignedAccess@Internal@Windows@@CAJKPEBG0W4AADGroupMembershipCacheOperation@1234@AEA_N@Z; Windows::Internal::AssignedAccess::AssignedAccessConfiguration::PerformAADGroupMembershipOperationInCache(ulong,ushort const *,ushort const *,Windows::Internal::AssignedAccess::AssignedAccessConfiguration::AADGroupMembershipCacheOperation,bool &)
0x180080b3b  mov     ebx, eax
0x180080b3d  test    eax, eax
0x180080b3f  jns     short loc_180080B5E
0x180080b41  mov     rcx, [rsp+58h]; this
0x180080b46  mov     r9d, eax; char *
0x180080b49  lea     r8, aOnecoreuapBase_44; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180080b50  mov     edx, 21Ah; void *
0x180080b55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080b5a  mov     eax, ebx
0x180080b5c  jmp     short loc_180080BA3
0x180080b5e  lea     rdx, [rsp+58h+arg_0]
0x180080b63  cmp     byte ptr [rdi], 0
0x180080b66  jz      short loc_180080B6F
0x180080b68  call    ??$AssignedAccessConfiguration_MembershipCheck_IgnoreFailure@AEAY0BH@$$CBGAEAJ@AssignedAccessTelemetry@@SAXAEAY0BH@$$CBGAEAJ@Z; AssignedAccessTelemetry::AssignedAccessConfiguration_MembershipCheck_IgnoreFailure<ushort const (&)[23],long &>(ushort const (&)[23],long &)
0x180080b6d  jmp     short loc_180080B99
0x180080b6f  test    sil, sil
0x180080b72  jz      short loc_180080B7B
0x180080b74  call    ??$AssignedAccessConfiguration_MembershipCheck_IgnoreFailure@AEAY0CC@$$CBGAEAJ@AssignedAccessTelemetry@@SAXAEAY0CC@$$CBGAEAJ@Z; AssignedAccessTelemetry::AssignedAccessConfiguration_MembershipCheck_IgnoreFailure<ushort const (&)[34],long &>(ushort const (&)[34],long &)
0x180080b79  jmp     short loc_180080B99
0x180080b7b  call    ??$AssignedAccessConfiguration_MembershipCheck_IgnoreFailure@AEAY0BL@$$CBGAEAJ@AssignedAccessTelemetry@@SAXAEAY0BL@$$CBGAEAJ@Z; AssignedAccessTelemetry::AssignedAccessConfiguration_MembershipCheck_IgnoreFailure<ushort const (&)[27],long &>(ushort const (&)[27],long &)
0x180080b80  jmp     short loc_180080B99
0x180080b82  cmp     ebx, 8000000Ah
0x180080b88  jz      short loc_180080B9B
0x180080b8a  test    sil, sil
0x180080b8d  jz      short loc_180080B9B
0x180080b8f  lea     rdx, [rsp+58h+arg_0]
0x180080b94  call    ??$AssignedAccessConfiguration_MembershipCheck_IgnoreFailure@AEAY0CF@$$CBGAEAJ@AssignedAccessTelemetry@@SAXAEAY0CF@$$CBGAEAJ@Z; AssignedAccessTelemetry::AssignedAccessConfiguration_MembershipCheck_IgnoreFailure<ushort const (&)[37],long &>(ushort const (&)[37],long &)
0x180080b99  xor     ebx, ebx
0x180080b9b  mov     eax, ebx
0x180080b9d  jmp     short loc_180080BA3
0x180080b9f  mov     eax, [rsp+58h+var_28]
0x180080ba3  mov     rbx, [rsp+58h+arg_8]
0x180080ba8  mov     rsi, [rsp+58h+arg_10]
0x180080bad  add     rsp, 40h
0x180080bb1  pop     r15
0x180080bb3  pop     r14
0x180080bb5  pop     rdi
0x180080bb6  retn
```
