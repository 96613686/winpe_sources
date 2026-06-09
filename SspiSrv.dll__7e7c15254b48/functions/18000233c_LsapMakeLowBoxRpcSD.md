# LsapMakeLowBoxRpcSD

- ea: `0x18000233c`
- end: `0x180002697`
- name: `LsapMakeLowBoxRpcSD`
- size: `859`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800027c0`

## callees

- `0x18000233c`
- `0x180003340`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x180002489`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800024c8`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180002507`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180002549`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180002587`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800025c7`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180002489`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800024c8`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180002507`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180002549`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180002587`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800025c7`
- `ntdll!RtlCreateAndSetSD` at `0x180002609`
- `ntdll!RtlCreateAndSetSD` at `0x180002609`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800025df`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800025df`
- `ntdll!RtlFreeSid` at `0x180002626`
- `ntdll!RtlFreeSid` at `0x180002636`
- `ntdll!RtlFreeSid` at `0x180002646`
- `ntdll!RtlFreeSid` at `0x180002656`
- `ntdll!RtlFreeSid` at `0x180002665`
- `ntdll!RtlFreeSid` at `0x180002674`
- `ntdll!RtlFreeSid` at `0x180002626`
- `ntdll!RtlFreeSid` at `0x180002636`
- `ntdll!RtlFreeSid` at `0x180002646`
- `ntdll!RtlFreeSid` at `0x180002656`
- `ntdll!RtlFreeSid` at `0x180002665`
- `ntdll!RtlFreeSid` at `0x180002674`

## string_xrefs

- `0x180002384`: `lpacIdentityServices`

## pseudocode

```c
__int64 __fastcall LsapMakeLowBoxRpcSD(PSECURITY_DESCRIPTOR *a1)
{
  NTSTATUS v2; // ebx
  PSID Sid; // [rsp+60h] [rbp-A0h] BYREF
  PSID v5; // [rsp+68h] [rbp-98h] BYREF
  PSID v6; // [rsp+70h] [rbp-90h] BYREF
  PSID v7; // [rsp+78h] [rbp-88h] BYREF
  PSID v8; // [rsp+80h] [rbp-80h] BYREF
  PSID v9; // [rsp+88h] [rbp-78h] BYREF
  _BYTE *v10; // [rsp+90h] [rbp-70h] BYREF
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v12[2]; // [rsp+A0h] [rbp-60h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v13; // [rsp+B0h] [rbp-50h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+B8h] [rbp-48h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v15; // [rsp+C0h] [rbp-40h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v16; // [rsp+C8h] [rbp-38h] BYREF
  __int16 AceData; // [rsp+D0h] [rbp-30h] BYREF
  char v18; // [rsp+D2h] [rbp-2Eh]
  int v19; // [rsp+D4h] [rbp-2Ch]
  PSID *p_Sid; // [rsp+D8h] [rbp-28h]
  __int16 v21; // [rsp+E0h] [rbp-20h]
  char v22; // [rsp+E2h] [rbp-1Eh]
  int v23; // [rsp+E4h] [rbp-1Ch]
  PSID *v24; // [rsp+E8h] [rbp-18h]
  __int16 v25; // [rsp+F0h] [rbp-10h]
  char v26; // [rsp+F2h] [rbp-Eh]
  unsigned int v27; // [rsp+F4h] [rbp-Ch]
  PSID *v28; // [rsp+F8h] [rbp-8h]
  __int16 v29; // [rsp+100h] [rbp+0h]
  char v30; // [rsp+102h] [rbp+2h]
  int v31; // [rsp+104h] [rbp+4h]
  PSID *v32; // [rsp+108h] [rbp+8h]
  __int16 v33; // [rsp+110h] [rbp+10h]
  char v34; // [rsp+112h] [rbp+12h]
  int v35; // [rsp+114h] [rbp+14h]
  PSID *v36; // [rsp+118h] [rbp+18h]
  __int16 v37; // [rsp+120h] [rbp+20h]
  char v38; // [rsp+122h] [rbp+22h]
  unsigned int v39; // [rsp+124h] [rbp+24h]
  PSID *v40; // [rsp+128h] [rbp+28h]
  __int16 v41; // [rsp+130h] [rbp+30h]
  char v42; // [rsp+132h] [rbp+32h]
  unsigned int v43; // [rsp+134h] [rbp+34h]
  _QWORD *v44; // [rsp+138h] [rbp+38h]
  _BYTE v45[48]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v46[48]; // [rsp+170h] [rbp+70h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 256;
  Sid = 0;
  v27 = 0x80000000;
  v39 = 0x80000000;
  v19 = -536870912;
  v12[1] = L"lpacIdentityServices";
  v23 = -536870912;
  p_Sid = &Sid;
  v31 = 0x10000000;
  v24 = &v5;
  v35 = 0x10000000;
  v28 = &v6;
  v43 = 0x80000000;
  v32 = &v7;
  v5 = 0;
  v36 = &v8;
  v40 = &v9;
  v44 = &v10;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v6 = 0;
  v10 = 0;
  NewDescriptor = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_DWORD *)v13.Value = 0;
  *(_WORD *)&v13.Value[4] = 1280;
  *(_DWORD *)v15.Value = 0;
  *(_WORD *)&v15.Value[4] = 768;
  *(_DWORD *)v16.Value = 0;
  *(_WORD *)&v16.Value[4] = 3840;
  v12[0] = 2752552;
  AceData = 0;
  v18 = 0;
  v21 = 1;
  v22 = 0;
  v25 = 0;
  v26 = 0;
  v29 = 0;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v37 = 0;
  v38 = 0;
  v41 = 0;
  v42 = 0;
  v2 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &Sid);
  if ( v2 >= 0 )
  {
    v2 = RtlAllocateAndInitializeSid(&v13, 1u, 0xCu, 0, 0, 0, 0, 0, 0, 0, &v5);
    if ( v2 >= 0 )
    {
      v2 = RtlAllocateAndInitializeSid(&v13, 1u, 7u, 0, 0, 0, 0, 0, 0, 0, &v6);
      if ( v2 >= 0 )
      {
        v2 = RtlAllocateAndInitializeSid(&v13, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v7);
        if ( v2 >= 0 )
        {
          v2 = RtlAllocateAndInitializeSid(&v15, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, &v8);
          if ( v2 >= 0 )
          {
            v2 = RtlAllocateAndInitializeSid(&v16, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, &v9);
            if ( v2 >= 0 )
            {
              v2 = RtlDeriveCapabilitySidsFromName(v12, v46, v45);
              if ( v2 >= 0 )
              {
                v10 = v45;
                v2 = RtlCreateAndSetSD(&AceData, 7u, 0, 0, &NewDescriptor);
                if ( v2 >= 0 )
                  *a1 = NewDescriptor;
              }
            }
          }
        }
      }
    }
  }
  if ( Sid )
    RtlFreeSid(Sid);
  if ( v5 )
    RtlFreeSid(v5);
  if ( v6 )
    RtlFreeSid(v6);
  if ( v7 )
    RtlFreeSid(v7);
  if ( v8 )
    RtlFreeSid(v8);
  if ( v9 )
    RtlFreeSid(v9);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000233c  push    rbp
0x18000233e  push    rbx
0x18000233f  push    rsi
0x180002340  push    rdi
0x180002341  lea     rbp, [rsp-0B8h]
0x180002349  sub     rsp, 1B8h
0x180002350  mov     rax, cs:__security_cookie
0x180002357  xor     rax, rsp
0x18000235a  mov     [rbp+0D0h+var_30], rax
0x180002361  xor     esi, esi
0x180002363  mov     word ptr [rbp+0D0h+IdentifierAuthority.Value+4], 100h
0x180002369  mov     edx, 80000000h
0x18000236e  mov     [rsp+1D0h+var_170], rsi
0x180002373  mov     rdi, rcx
0x180002376  mov     [rbp+0D0h+var_DC], edx
0x180002379  mov     ecx, 0E0000000h
0x18000237e  mov     [rbp+0D0h+var_AC], edx
0x180002381  mov     [rbp+0D0h+var_FC], ecx
0x180002384  lea     rax, aLpacidentityse; "lpacIdentityServices"
0x18000238b  mov     [rbp+0D0h+var_128], rax
0x18000238f  xor     r9d, r9d; SubAuthority1
0x180002392  mov     [rbp+0D0h+var_EC], ecx
0x180002395  lea     rax, [rsp+1D0h+var_170]
0x18000239a  mov     [rbp+0D0h+var_F8], rax
0x18000239e  mov     ecx, 10000000h
0x1800023a3  lea     rax, [rsp+1D0h+var_168]
0x1800023a8  mov     [rbp+0D0h+var_CC], ecx
0x1800023ab  mov     [rbp+0D0h+var_E8], rax
0x1800023af  xor     r8d, r8d; SubAuthority0
0x1800023b2  lea     rax, [rsp+1D0h+var_160]
0x1800023b7  mov     [rbp+0D0h+var_BC], ecx
0x1800023ba  mov     [rbp+0D0h+var_D8], rax
0x1800023be  lea     rcx, [rbp+0D0h+IdentifierAuthority]; IdentifierAuthority
0x1800023c2  lea     rax, [rsp+1D0h+var_158]
0x1800023c7  mov     [rbp+0D0h+var_9C], edx
0x1800023ca  mov     [rbp+0D0h+var_C8], rax
0x1800023ce  mov     dl, 1; SubAuthorityCount
0x1800023d0  lea     rax, [rbp+0D0h+var_150]
0x1800023d4  mov     [rsp+1D0h+var_168], rsi
0x1800023d9  mov     [rbp+0D0h+var_B8], rax
0x1800023dd  lea     rax, [rbp+0D0h+var_148]
0x1800023e1  mov     [rbp+0D0h+var_A8], rax
0x1800023e5  lea     rax, [rbp+0D0h+var_140]
0x1800023e9  mov     [rbp+0D0h+var_98], rax
0x1800023ed  lea     rax, [rsp+1D0h+var_170]
0x1800023f2  mov     [rsp+1D0h+Sid], rax; Sid
0x1800023f7  mov     [rsp+1D0h+SubAuthority7], esi; SubAuthority7
0x1800023fb  mov     [rsp+1D0h+SubAuthority6], esi; SubAuthority6
0x1800023ff  mov     [rsp+1D0h+SubAuthority5], esi; SubAuthority5
0x180002403  mov     [rsp+1D0h+SubAuthority4], esi; SubAuthority4
0x180002407  mov     [rsp+1D0h+SubAuthority3], esi; SubAuthority3
0x18000240b  mov     [rsp+1D0h+SubAuthority2], esi; SubAuthority2
0x18000240f  mov     [rsp+1D0h+var_158], rsi
0x180002414  mov     [rbp+0D0h+var_150], rsi
0x180002418  mov     [rbp+0D0h+var_148], rsi
0x18000241c  mov     [rsp+1D0h+var_160], rsi
0x180002421  mov     [rbp+0D0h+var_140], rsi
0x180002425  mov     [rbp+0D0h+NewDescriptor], rsi
0x180002429  mov     dword ptr [rbp+0D0h+IdentifierAuthority.Value], esi
0x18000242c  mov     dword ptr [rbp+0D0h+var_120.Value], esi
0x18000242f  mov     word ptr [rbp+0D0h+var_120.Value+4], 500h
0x180002435  mov     dword ptr [rbp+0D0h+var_110.Value], esi
0x180002438  mov     word ptr [rbp+0D0h+var_110.Value+4], 300h
0x18000243e  mov     dword ptr [rbp+0D0h+var_108.Value], esi
0x180002441  mov     word ptr [rbp+0D0h+var_108.Value+4], 0F00h
0x180002447  mov     [rbp+0D0h+var_130], 2A0028h
0x18000244f  mov     [rbp+0D0h+AceData], si
0x180002453  mov     [rbp+0D0h+var_FE], sil
0x180002457  mov     [rbp+0D0h+var_F0], 1
0x18000245d  mov     [rbp+0D0h+var_EE], sil
0x180002461  mov     [rbp+0D0h+var_E0], si
0x180002465  mov     [rbp+0D0h+var_DE], sil
0x180002469  mov     [rbp+0D0h+var_D0], si
0x18000246d  mov     [rbp+0D0h+var_CE], sil
0x180002471  mov     [rbp+0D0h+var_C0], si
0x180002475  mov     [rbp+0D0h+var_BE], sil
0x180002479  mov     [rbp+0D0h+var_B0], si
0x18000247d  mov     [rbp+0D0h+var_AE], sil
0x180002481  mov     [rbp+0D0h+var_A0], si
0x180002485  mov     [rbp+0D0h+var_9E], sil
0x180002489  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000248f  mov     ebx, eax
0x180002491  test    eax, eax
0x180002493  js      loc_18000261C
0x180002499  lea     rax, [rsp+1D0h+var_168]
0x18000249e  xor     r9d, r9d; SubAuthority1
0x1800024a1  mov     [rsp+1D0h+Sid], rax; Sid
0x1800024a6  lea     r8d, [rsi+0Ch]; SubAuthority0
0x1800024aa  mov     [rsp+1D0h+SubAuthority7], esi; SubAuthority7
0x1800024ae  lea     rcx, [rbp+0D0h+var_120]; IdentifierAuthority
0x1800024b2  mov     [rsp+1D0h+SubAuthority6], esi; SubAuthority6
0x1800024b6  mov     dl, 1; SubAuthorityCount
0x1800024b8  mov     [rsp+1D0h+SubAuthority5], esi; SubAuthority5
0x1800024bc  mov     [rsp+1D0h+SubAuthority4], esi; SubAuthority4
0x1800024c0  mov     [rsp+1D0h+SubAuthority3], esi; SubAuthority3
0x1800024c4  mov     [rsp+1D0h+SubAuthority2], esi; SubAuthority2
0x1800024c8  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800024ce  mov     ebx, eax
0x1800024d0  test    eax, eax
0x1800024d2  js      loc_18000261C
0x1800024d8  lea     rax, [rsp+1D0h+var_160]
0x1800024dd  xor     r9d, r9d; SubAuthority1
0x1800024e0  mov     [rsp+1D0h+Sid], rax; Sid
0x1800024e5  lea     r8d, [rsi+7]; SubAuthority0
0x1800024e9  mov     [rsp+1D0h+SubAuthority7], esi; SubAuthority7
0x1800024ed  lea     rcx, [rbp+0D0h+var_120]; IdentifierAuthority
0x1800024f1  mov     [rsp+1D0h+SubAuthority6], esi; SubAuthority6
0x1800024f5  mov     dl, 1; SubAuthorityCount
0x1800024f7  mov     [rsp+1D0h+SubAuthority5], esi; SubAuthority5
0x1800024fb  mov     [rsp+1D0h+SubAuthority4], esi; SubAuthority4
0x1800024ff  mov     [rsp+1D0h+SubAuthority3], esi; SubAuthority3
0x180002503  mov     [rsp+1D0h+SubAuthority2], esi; SubAuthority2
0x180002507  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000250d  mov     ebx, eax
0x18000250f  test    eax, eax
0x180002511  js      loc_18000261C
0x180002517  lea     rax, [rsp+1D0h+var_158]
0x18000251c  mov     r9d, 220h; SubAuthority1
0x180002522  mov     [rsp+1D0h+Sid], rax; Sid
0x180002527  lea     r8d, [rsi+20h]; SubAuthority0
0x18000252b  mov     [rsp+1D0h+SubAuthority7], esi; SubAuthority7
0x18000252f  lea     rcx, [rbp+0D0h+var_120]; IdentifierAuthority
0x180002533  mov     [rsp+1D0h+SubAuthority6], esi; SubAuthority6
0x180002537  mov     dl, 2; SubAuthorityCount
0x180002539  mov     [rsp+1D0h+SubAuthority5], esi; SubAuthority5
0x18000253d  mov     [rsp+1D0h+SubAuthority4], esi; SubAuthority4
0x180002541  mov     [rsp+1D0h+SubAuthority3], esi; SubAuthority3
0x180002545  mov     [rsp+1D0h+SubAuthority2], esi; SubAuthority2
0x180002549  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000254f  mov     ebx, eax
0x180002551  test    eax, eax
0x180002553  js      loc_18000261C
0x180002559  lea     rax, [rbp+0D0h+var_150]
0x18000255d  xor     r9d, r9d; SubAuthority1
0x180002560  mov     [rsp+1D0h+Sid], rax; Sid
0x180002565  lea     r8d, [rsi+4]; SubAuthority0
0x180002569  mov     [rsp+1D0h+SubAuthority7], esi; SubAuthority7
0x18000256d  lea     rcx, [rbp+0D0h+var_110]; IdentifierAuthority
0x180002571  mov     [rsp+1D0h+SubAuthority6], esi; SubAuthority6
0x180002575  mov     dl, 1; SubAuthorityCount
0x180002577  mov     [rsp+1D0h+SubAuthority5], esi; SubAuthority5
0x18000257b  mov     [rsp+1D0h+SubAuthority4], esi; SubAuthority4
0x18000257f  mov     [rsp+1D0h+SubAuthority3], esi; SubAuthority3
0x180002583  mov     [rsp+1D0h+SubAuthority2], esi; SubAuthority2
0x180002587  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000258d  mov     ebx, eax
0x18000258f  test    eax, eax
0x180002591  js      loc_18000261C
0x180002597  lea     rax, [rbp+0D0h+var_148]
0x18000259b  mov     [rsp+1D0h+Sid], rax; Sid
0x1800025a0  lea     r8d, [rsi+2]; SubAuthority0
0x1800025a4  mov     [rsp+1D0h+SubAuthority7], esi; SubAuthority7
0x1800025a8  lea     r9d, [rsi+1]; SubAuthority1
0x1800025ac  mov     [rsp+1D0h+SubAuthority6], esi; SubAuthority6
0x1800025b0  lea     rcx, [rbp+0D0h+var_108]; IdentifierAuthority
0x1800025b4  mov     [rsp+1D0h+SubAuthority5], esi; SubAuthority5
0x1800025b8  mov     dl, r8b; SubAuthorityCount
0x1800025bb  mov     [rsp+1D0h+SubAuthority4], esi; SubAuthority4
0x1800025bf  mov     [rsp+1D0h+SubAuthority3], esi; SubAuthority3
0x1800025c3  mov     [rsp+1D0h+SubAuthority2], esi; SubAuthority2
0x1800025c7  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800025cd  mov     ebx, eax
0x1800025cf  test    eax, eax
0x1800025d1  js      short loc_18000261C
0x1800025d3  lea     r8, [rbp+0D0h+var_90]
0x1800025d7  lea     rdx, [rbp+0D0h+var_60]
0x1800025db  lea     rcx, [rbp+0D0h+var_130]
0x1800025df  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x1800025e5  mov     ebx, eax
0x1800025e7  test    eax, eax
0x1800025e9  js      short loc_18000261C
0x1800025eb  lea     rax, [rbp+0D0h+var_90]
0x1800025ef  xor     r9d, r9d; GroupSid
0x1800025f2  mov     [rbp+0D0h+var_140], rax
0x1800025f6  lea     edx, [rsi+7]; AceCount
0x1800025f9  lea     rax, [rbp+0D0h+NewDescriptor]
0x1800025fd  xor     r8d, r8d; OwnerSid
0x180002600  lea     rcx, [rbp+0D0h+AceData]; AceData
0x180002604  mov     qword ptr [rsp+1D0h+SubAuthority2], rax; NewDescriptor
0x180002609  call    cs:__imp_RtlCreateAndSetSD
0x18000260f  mov     ebx, eax
0x180002611  test    eax, eax
0x180002613  js      short loc_18000261C
0x180002615  mov     rax, [rbp+0D0h+NewDescriptor]
0x180002619  mov     [rdi], rax
0x18000261c  mov     rcx, [rsp+1D0h+var_170]; Sid
0x180002621  test    rcx, rcx
0x180002624  jz      short loc_18000262C
0x180002626  call    cs:__imp_RtlFreeSid
0x18000262c  mov     rcx, [rsp+1D0h+var_168]; Sid
0x180002631  test    rcx, rcx
0x180002634  jz      short loc_18000263C
0x180002636  call    cs:__imp_RtlFreeSid
0x18000263c  mov     rcx, [rsp+1D0h+var_160]; Sid
0x180002641  test    rcx, rcx
0x180002644  jz      short loc_18000264C
0x180002646  call    cs:__imp_RtlFreeSid
0x18000264c  mov     rcx, [rsp+1D0h+var_158]; Sid
0x180002651  test    rcx, rcx
0x180002654  jz      short loc_18000265C
0x180002656  call    cs:__imp_RtlFreeSid
0x18000265c  mov     rcx, [rbp+0D0h+var_150]; Sid
0x180002660  test    rcx, rcx
0x180002663  jz      short loc_18000266B
0x180002665  call    cs:__imp_RtlFreeSid
0x18000266b  mov     rcx, [rbp+0D0h+var_148]; Sid
0x18000266f  test    rcx, rcx
0x180002672  jz      short loc_18000267A
0x180002674  call    cs:__imp_RtlFreeSid
0x18000267a  mov     eax, ebx
0x18000267c  mov     rcx, [rbp+0D0h+var_30]
0x180002683  xor     rcx, rsp; StackCookie
0x180002686  call    __security_check_cookie
0x18000268b  add     rsp, 1B8h
0x180002692  pop     rdi
0x180002693  pop     rsi
0x180002694  pop     rbx
0x180002695  pop     rbp
0x180002696  retn
```
