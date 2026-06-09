# NcbPolicyOnAppLockScreenAddHandlerUnderLock

- ea: `0x180009dd0`
- end: `0x18000a094`
- name: `NcbPolicyOnAppLockScreenAddHandlerUnderLock`
- size: `708`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022e70`

## callees

- `0x180009dd0`
- `0x18000a0a0`
- `0x18000a160`
- `0x18000a1c0`
- `0x18001d8e0`

## import_xrefs

- `ntdll!RtlLookupEntryHashTable` at `0x180009f24`
- `ntdll!RtlLookupEntryHashTable` at `0x180009f24`
- `ntdll!RtlGetNextEntryHashTable` at `0x180009f60`
- `ntdll!RtlGetNextEntryHashTable` at `0x180009f60`
- `ntdll!RtlInsertEntryHashTable` at `0x180009ff7`
- `ntdll!RtlInsertEntryHashTable` at `0x180009ff7`
- `ntdll!RtlFreeSid` at `0x18000a009`
- `ntdll!RtlFreeSid` at `0x18000a009`
- `ntdll!RtlEqualSid` at `0x180009f39`
- `ntdll!RtlEqualSid` at `0x180009f4a`
- `ntdll!RtlEqualSid` at `0x180009f39`
- `ntdll!RtlEqualSid` at `0x180009f4a`
- `ntdll!RtlLengthSid` at `0x180009edb`
- `ntdll!RtlLengthSid` at `0x180009fba`
- `ntdll!RtlLengthSid` at `0x180009edb`
- `ntdll!RtlLengthSid` at `0x180009fba`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x180009e89`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x180009e89`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180009e71`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180009e71`

## string_xrefs

- `0x18000a07c`: `NcbPolicy: AppContainerDeriveSidFromMoniker failed with error - `

## pseudocode

```c
char __fastcall NcbPolicyOnAppLockScreenAddHandlerUnderLock(unsigned __int16 *a1, const WCHAR *a2, unsigned __int8 *a3)
{
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  PSID v12; // rsi
  char v13; // r12
  ULONG v14; // eax
  unsigned __int8 *v15; // r8
  unsigned int v16; // ecx
  ULONG i; // r9d
  int v18; // edx
  __int64 j; // rax
  __int64 v20; // rbx
  unsigned __int16 *v21; // rcx
  int v22; // edx
  int v23; // eax
  _QWORD *Policy; // rax
  _QWORD *v25; // rdi
  unsigned __int8 *v26; // rbx
  ULONG v27; // eax
  unsigned int v28; // edx
  ULONG k; // r8d
  int v30; // ecx
  UINT32 packageFamilyNameLength; // [rsp+30h] [rbp-298h] BYREF
  PSID Sid1; // [rsp+38h] [rbp-290h] BYREF
  __int128 v34; // [rsp+40h] [rbp-288h] BYREF
  const wchar_t *v35; // [rsp+50h] [rbp-278h]
  __int64 v36; // [rsp+58h] [rbp-270h]
  UINT32 *p_packageFamilyNameLength; // [rsp+60h] [rbp-268h]
  __int64 v38; // [rsp+68h] [rbp-260h]
  WCHAR packageFamilyName[264]; // [rsp+70h] [rbp-258h] BYREF

  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
  {
    packageFamilyNameLength = 0;
    v35 = L"NcbPolicy: NcbPolicyOnAppLockScreenAddHandlerUnderLock called - ";
    v36 = 130;
    p_packageFamilyNameLength = &packageFamilyNameLength;
    v38 = 4;
    McGenEventWrite_EventWriteTransfer(a1, NcbApiStatus, a3, 3, &v34);
  }
  Sid1 = 0;
  packageFamilyNameLength = 260;
  v6 = PackageFamilyNameFromFullName(a2, &packageFamilyNameLength, packageFamilyName);
  if ( v6 )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v8, v7, L"NcbPolicy: PackageFamilyNameFromFullName failed with error - ", v6);
    return 0;
  }
  v9 = AppContainerDeriveSidFromMoniker(packageFamilyName, &Sid1);
  if ( v9 < 0 )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v11,
        v10,
        L"NcbPolicy: AppContainerDeriveSidFromMoniker failed with error - ",
        (unsigned int)v9);
    return 0;
  }
  v12 = Sid1;
  if ( !Sid1 )
    return 0;
  v13 = 0;
  v35 = 0;
  v34 = 0;
  if ( a3 )
  {
    v14 = RtlLengthSid(a3);
    v15 = a3;
    v16 = 0;
    for ( i = 0; i < v14; v16 = v18 + 37 * v16 )
    {
      v18 = *v15++;
      ++i;
    }
    v34 = 0;
    for ( j = RtlLookupEntryHashTable(g_NcbPolicies, v16 | 0x80000000LL, &v34);
          ;
          j = RtlGetNextEntryHashTable(g_NcbPolicies, &v34) )
    {
      v20 = j;
      if ( !j )
        break;
      if ( RtlEqualSid(a3, *(PSID *)(j + 24)) && RtlEqualSid(v12, *(PSID *)(v20 + 40)) )
      {
        if ( !a1 )
          goto LABEL_24;
        v21 = a1;
        do
        {
          v22 = *(unsigned __int16 *)((char *)v21 + *(_QWORD *)(v20 + 48) - (_QWORD)a1);
          v23 = *v21 - v22;
          if ( v23 )
            break;
          ++v21;
        }
        while ( v22 );
        if ( !v23 )
          goto LABEL_24;
      }
    }
  }
  Policy = NcbPolicyCreatePolicy(a3, v12, a1, a2);
  v25 = Policy;
  if ( Policy )
  {
    v26 = (unsigned __int8 *)Policy[3];
    v27 = RtlLengthSid(v26);
    v28 = 0;
    for ( k = 0; k < v27; v28 = v30 + 37 * v28 )
    {
      v30 = *v26++;
      ++k;
    }
    RtlInsertEntryHashTable(g_NcbPolicies, v25, v28 | 0x80000000LL, 0);
    ++g_NcbPolicyCounter;
    v13 = 1;
  }
LABEL_24:
  RtlFreeSid(v12);
  return v13;
}

```

## disassembly

```asm
0x180009dd0  push    rdi
0x180009dd2  push    r13
0x180009dd4  push    r14
0x180009dd6  push    r15
0x180009dd8  sub     rsp, 2A8h
0x180009ddf  mov     rax, cs:__security_cookie
0x180009de6  xor     rax, rsp
0x180009de9  mov     [rsp+2C8h+var_48], rax
0x180009df1  xor     r13d, r13d
0x180009df4  mov     rdi, r8
0x180009df7  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180009dfe  mov     r15, rdx
0x180009e01  mov     r14, rcx
0x180009e04  jz      short loc_180009E4F
0x180009e06  lea     rax, aNcbpolicyNcbpo_10; "NcbPolicy: NcbPolicyOnAppLockScreenAddH"...
0x180009e0d  mov     [rsp+2C8h+packageFamilyNameLength], r13d
0x180009e12  mov     [rsp+2C8h+var_278], rax
0x180009e17  lea     rdx, NcbApiStatus
0x180009e1e  lea     rax, [rsp+2C8h+packageFamilyNameLength]
0x180009e23  mov     [rsp+2C8h+var_270], 82h
0x180009e2c  mov     [rsp+2C8h+var_268], rax
0x180009e31  mov     r9d, 3
0x180009e37  lea     rax, [rsp+2C8h+var_288]
0x180009e3c  mov     [rsp+2C8h+var_260], 4
0x180009e45  mov     [rsp+2C8h+var_2A8], rax
0x180009e4a  call    McGenEventWrite_EventWriteTransfer
0x180009e4f  lea     r8, [rsp+2C8h+packageFamilyName]; packageFamilyName
0x180009e54  mov     [rsp+2C8h+var_30], rsi
0x180009e5c  lea     rdx, [rsp+2C8h+packageFamilyNameLength]; packageFamilyNameLength
0x180009e61  mov     [rsp+2C8h+Sid1], r13
0x180009e66  mov     rcx, r15; packageFullName
0x180009e69  mov     [rsp+2C8h+packageFamilyNameLength], 104h
0x180009e71  call    cs:__imp_PackageFamilyNameFromFullName
0x180009e77  test    eax, eax
0x180009e79  jnz     loc_18000A02D
0x180009e7f  lea     rdx, [rsp+2C8h+Sid1]
0x180009e84  lea     rcx, [rsp+2C8h+packageFamilyName]
0x180009e89  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x180009e8f  test    eax, eax
0x180009e91  js      loc_18000A070
0x180009e97  mov     rsi, [rsp+2C8h+Sid1]
0x180009e9c  test    rsi, rsi
0x180009e9f  jz      loc_18000A036
0x180009ea5  mov     [rsp+2C8h+arg_18], rbx
0x180009ead  xor     eax, eax
0x180009eaf  mov     [rsp+2C8h+var_28], rbp
0x180009eb7  xorps   xmm0, xmm0
0x180009eba  mov     [rsp+2C8h+var_38], r12
0x180009ec2  xor     r12b, r12b
0x180009ec5  mov     [rsp+2C8h+var_278], rax
0x180009eca  movups  [rsp+2C8h+var_288], xmm0
0x180009ecf  test    rdi, rdi
0x180009ed2  jz      loc_18000A08A
0x180009ed8  mov     rcx, rdi; Sid
0x180009edb  call    cs:__imp_RtlLengthSid
0x180009ee1  mov     r8, rdi
0x180009ee4  mov     ecx, r13d
0x180009ee7  mov     r9d, r13d
0x180009eea  test    eax, eax
0x180009eec  jz      short loc_180009F05
0x180009eee  xchg    ax, ax
0x180009ef0  movzx   edx, byte ptr [r8]
0x180009ef4  lea     r8, [r8+1]
0x180009ef8  imul    ecx, 25h ; '%'
0x180009efb  inc     r9d
0x180009efe  add     ecx, edx
0x180009f00  cmp     r9d, eax
0x180009f03  jb      short loc_180009EF0
0x180009f05  mov     edx, ecx
0x180009f07  lea     r8, [rsp+2C8h+var_288]
0x180009f0c  xorps   xmm0, xmm0
0x180009f0f  lea     rcx, g_NcbPolicies
0x180009f16  mov     ebp, 80000000h
0x180009f1b  or      rdx, rbp
0x180009f1e  movdqu  [rsp+2C8h+var_288], xmm0
0x180009f24  call    cs:__imp_RtlLookupEntryHashTable
0x180009f2a  mov     rbx, rax
0x180009f2d  test    rax, rax
0x180009f30  jz      short loc_180009F9A
0x180009f32  mov     rdx, [rax+18h]; Sid2
0x180009f36  mov     rcx, rdi; Sid1
0x180009f39  call    cs:__imp_RtlEqualSid
0x180009f3f  test    al, al
0x180009f41  jz      short loc_180009F54
0x180009f43  mov     rdx, [rbx+28h]; Sid2
0x180009f47  mov     rcx, rsi; Sid1
0x180009f4a  call    cs:__imp_RtlEqualSid
0x180009f50  test    al, al
0x180009f52  jnz     short loc_180009F68
0x180009f54  lea     rdx, [rsp+2C8h+var_288]
0x180009f59  lea     rcx, g_NcbPolicies
0x180009f60  call    cs:__imp_RtlGetNextEntryHashTable
0x180009f66  jmp     short loc_180009F2A
0x180009f68  test    r14, r14
0x180009f6b  jz      loc_18000A006
0x180009f71  mov     r8, [rbx+30h]
0x180009f75  mov     rcx, r14
0x180009f78  sub     r8, r14
0x180009f7b  nop     dword ptr [rax+rax+00h]
0x180009f80  movzx   eax, word ptr [rcx]
0x180009f83  movzx   edx, word ptr [rcx+r8]
0x180009f88  sub     eax, edx
0x180009f8a  jnz     short loc_180009F94
0x180009f8c  add     rcx, 2
0x180009f90  test    edx, edx
0x180009f92  jnz     short loc_180009F80
0x180009f94  test    eax, eax
0x180009f96  jnz     short loc_180009F54
0x180009f98  jmp     short loc_18000A006
0x180009f9a  mov     r9, r15
0x180009f9d  mov     r8, r14
0x180009fa0  mov     rdx, rsi; SourceSid
0x180009fa3  mov     rcx, rdi; Sid
0x180009fa6  call    NcbPolicyCreatePolicy
0x180009fab  mov     rdi, rax
0x180009fae  test    rax, rax
0x180009fb1  jz      short loc_18000A006
0x180009fb3  mov     rbx, [rax+18h]
0x180009fb7  mov     rcx, rbx; Sid
0x180009fba  call    cs:__imp_RtlLengthSid
0x180009fc0  mov     edx, r13d
0x180009fc3  mov     r8d, r13d
0x180009fc6  test    eax, eax
0x180009fc8  jz      short loc_180009FE4
0x180009fca  nop     word ptr [rax+rax+00h]
0x180009fd0  movzx   ecx, byte ptr [rbx]
0x180009fd3  lea     rbx, [rbx+1]
0x180009fd7  imul    edx, 25h ; '%'
0x180009fda  inc     r8d
0x180009fdd  add     edx, ecx
0x180009fdf  cmp     r8d, eax
0x180009fe2  jb      short loc_180009FD0
0x180009fe4  mov     r8d, edx
0x180009fe7  lea     rcx, g_NcbPolicies
0x180009fee  or      r8, rbp
0x180009ff1  xor     r9d, r9d
0x180009ff4  mov     rdx, rdi
0x180009ff7  call    cs:__imp_RtlInsertEntryHashTable
0x180009ffd  inc     cs:g_NcbPolicyCounter
0x18000a003  mov     r12b, 1
0x18000a006  mov     rcx, rsi; Sid
0x18000a009  call    cs:__imp_RtlFreeSid
0x18000a00f  mov     rbp, [rsp+2C8h+var_28]
0x18000a017  movzx   eax, r12b
0x18000a01b  mov     r12, [rsp+2C8h+var_38]
0x18000a023  mov     rbx, [rsp+2C8h+arg_18]
0x18000a02b  jmp     short loc_18000A038
0x18000a02d  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000a034  jnz     short loc_18000A05F
0x18000a036  xor     al, al
0x18000a038  mov     rsi, [rsp+2C8h+var_30]
0x18000a040  mov     rcx, [rsp+2C8h+var_48]
0x18000a048  xor     rcx, rsp; StackCookie
0x18000a04b  call    __security_check_cookie
0x18000a050  add     rsp, 2A8h
0x18000a057  pop     r15
0x18000a059  pop     r14
0x18000a05b  pop     r13
0x18000a05d  pop     rdi
0x18000a05e  retn
0x18000a05f  mov     r9d, eax
0x18000a062  lea     r8, aNcbpolicyPacka; "NcbPolicy: PackageFamilyNameFromFullNam"...
0x18000a069  call    McTemplateU0zq_EventWriteTransfer
0x18000a06e  jmp     short loc_18000A036
0x18000a070  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000a077  jz      short loc_18000A036
0x18000a079  mov     r9d, eax
0x18000a07c  lea     r8, aNcbpolicyAppco; "NcbPolicy: AppContainerDeriveSidFromMon"...
0x18000a083  call    McTemplateU0zq_EventWriteTransfer
0x18000a088  jmp     short loc_18000A036
0x18000a08a  mov     ebp, 80000000h
0x18000a08f  jmp     loc_180009F9A
```
