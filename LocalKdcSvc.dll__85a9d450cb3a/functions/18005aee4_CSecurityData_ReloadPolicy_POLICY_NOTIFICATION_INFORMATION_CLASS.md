# CSecurityData::ReloadPolicy(_POLICY_NOTIFICATION_INFORMATION_CLASS)

- ea: `0x18005aee4`
- end: `0x18005b28b`
- name: `?ReloadPolicy@CSecurityData@@QEAAJW4_POLICY_NOTIFICATION_INFORMATION_CLASS@@@Z`
- size: `935`
- prototype: `__int64 __fastcall(CSecurityData *__hidden this, enum _POLICY_NOTIFICATION_INFORMATION_CLASS)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005ad80`
- `0x18005ae00`

## callees

- `0x180002ad0`
- `0x18000e440`
- `0x1800101c4`
- `0x180010718`
- `0x1800107dc`
- `0x18005a1b4`
- `0x18005aee4`
- `0x18005b7d8`
- `0x180083c9c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x18005b17d`
- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x18005b17d`
- `ntdll!RtlReleaseResource` at `0x18005b254`
- `ntdll!RtlReleaseResource` at `0x18005b254`
- `ntdll!RtlAcquireResourceExclusive` at `0x18005b013`
- `ntdll!RtlAcquireResourceExclusive` at `0x18005b013`
- `LSASRV!LsaIAdtAuditingEnabledBySubCategory` at `0x18005afa5`
- `LSASRV!LsaIAdtAuditingEnabledBySubCategory` at `0x18005afcc`
- `LSASRV!LsaIAdtAuditingEnabledBySubCategory` at `0x18005aff3`
- `LSASRV!LsaIAdtAuditingEnabledBySubCategory` at `0x18005afa5`
- `LSASRV!LsaIAdtAuditingEnabledBySubCategory` at `0x18005afcc`
- `LSASRV!LsaIAdtAuditingEnabledBySubCategory` at `0x18005aff3`
- `LSASRV!LsarQueryDomainInformationPolicy` at `0x18005af6e`
- `LSASRV!LsarQueryDomainInformationPolicy` at `0x18005af6e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSecurityData::ReloadPolicy(CSecurityData *this, enum _POLICY_NOTIFICATION_INFORMATION_CLASS a2)
{
  __int64 v3; // rax
  int v4; // ebx
  __int64 v5; // r8
  int v6; // edi
  CSecurityData *v7; // rcx
  char *v8; // r8
  __int64 v9; // rax
  union _LARGE_INTEGER v10; // rdx
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  char v18; // [rsp+30h] [rbp-50h] BYREF
  char v19; // [rsp+31h] [rbp-4Fh] BYREF
  char v20; // [rsp+32h] [rbp-4Eh] BYREF
  char v21; // [rsp+33h] [rbp-4Dh] BYREF
  char v22; // [rsp+34h] [rbp-4Ch] BYREF
  _BYTE v23[3]; // [rsp+35h] [rbp-4Bh] BYREF
  char *v24; // [rsp+38h] [rbp-48h] BYREF
  int v25; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v26[8]; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v27[16]; // [rsp+50h] [rbp-30h] BYREF
  wchar_t Buffer[8]; // [rsp+60h] [rbp-20h] BYREF
  int v29; // [rsp+70h] [rbp-10h]

  v24 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23[0] = 0;
  *(_OWORD *)Buffer = 0;
  v29 = 0;
  v3 = lambda_2a70c627909d6c04886f368e19249c19_::_lambda_2a70c627909d6c04886f368e19249c19_(v26, &v24);
  wil::scope_exit__lambda_2a70c627909d6c04886f368e19249c19___(v27, v3);
  if ( a2 == PolicyNotifyAuditEventsInformation )
  {
    v4 = LsaIAdtAuditingEnabledBySubCategory(157, 0, 0, &v18, &v19);
    if ( v4 >= 0 )
    {
      v4 = LsaIAdtAuditingEnabledBySubCategory(159, 0, 0, &v20, &v21);
      if ( v4 >= 0 )
      {
        v4 = LsaIAdtAuditingEnabledBySubCategory(156, 0, 0, &v22, v23);
        if ( v4 >= 0 )
          goto LABEL_9;
      }
    }
  }
  else
  {
    if ( a2 != PolicyNotifyDomainKerberosTicketInformation )
    {
LABEL_63:
      v4 = 0;
      goto LABEL_64;
    }
    v4 = LsarQueryDomainInformationPolicy(GlobalPolicyHandle, 3, &v24);
    if ( v4 >= 0 )
    {
      if ( !v24 )
      {
        v4 = -1073741823;
        goto LABEL_64;
      }
LABEL_9:
      RtlAcquireResourceExclusive(&Resource, 1u);
      v6 = a2 - 1;
      if ( !v6 )
      {
        if ( v18 )
          v11 = HIDWORD(qword_1800B2E50) | 4;
        else
          v11 = HIDWORD(qword_1800B2E50) & 0xFFFFFFFB;
        if ( v19 )
          v12 = v11 | 8;
        else
          v12 = v11 & 0xFFFFFFF7;
        if ( v20 )
          v13 = v12 | 1;
        else
          v13 = v12 & 0xFFFFFFFE;
        if ( v21 )
          v14 = v13 | 2;
        else
          v14 = v13 & 0xFFFFFFFD;
        if ( v22 )
          v15 = v14 | 0x10;
        else
          v15 = v14 & 0xFFFFFFEF;
        if ( v23[0] )
          v16 = v15 | 0x20;
        else
          v16 = v15 & 0xFFFFFFDF;
        HIDWORD(qword_1800B2E50) = v16;
        goto LABEL_62;
      }
      if ( v6 != 5 )
      {
LABEL_62:
        RtlReleaseResource(&Resource);
        goto LABEL_63;
      }
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v5, *((_QWORD *)v24 + 1));
          v7 = WPP_GLOBAL_Control;
        }
        if ( v7 != (CSecurityData *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v7 + 28) & 4) != 0 )
          {
            WPP_SF_i(*((_QWORD *)v7 + 2), 11, v5, *((_QWORD *)v24 + 2));
            v7 = WPP_GLOBAL_Control;
          }
          if ( v7 != (CSecurityData *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v7 + 28) & 4) != 0 )
            {
              WPP_SF_i(*((_QWORD *)v7 + 2), 12, v5, *((_QWORD *)v24 + 3));
              v7 = WPP_GLOBAL_Control;
            }
            if ( v7 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 )
              WPP_SF_i(*((_QWORD *)v7 + 2), 13, v5, *((_QWORD *)v24 + 4));
          }
        }
      }
      v8 = v24;
      v9 = *((_QWORD *)v24 + 1);
      if ( v9 > -1
        && *((__int64 *)v24 + 2) > -1
        && *((__int64 *)v24 + 3) > -1
        && *((__int64 *)v24 + 4) > -1
        && v9
        && *((_QWORD *)v24 + 2) )
      {
        qword_1800B2E30 = *((_QWORD *)v24 + 1);
        qword_1800B2E38 = *((_QWORD *)v24 + 2);
        qword_1800B2E40 = *((_QWORD *)v24 + 3);
        v10.QuadPart = 100000000;
        if ( *((__int64 *)v24 + 4) > 100000000 )
          v10 = *(union _LARGE_INTEGER *)(v24 + 32);
        SkewTime = v10;
        if ( Authenticators )
        {
          CAuthenticatorList::SetMaxAge(Authenticators, v10);
          v8 = v24;
          v10 = SkewTime;
        }
        if ( !ReplayDetect )
          goto LABEL_40;
        CAuthenticatorList::SetMaxAge(ReplayDetect, v10);
      }
      else
      {
        v25 = -1073741811;
        _itow(6, Buffer, 10);
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_39025eb542cc3a17cc5bb89d70ac2bcd_Traceguids);
        }
        ReportServiceEvent(1u, 0xC0000005, 4u, &v25, 1u, Buffer);
      }
      v8 = v24;
LABEL_40:
      if ( *v8 >= 0 )
        LODWORD(qword_1800B2E50) = qword_1800B2E50 & 0xFFFFFF7F;
      else
        LODWORD(qword_1800B2E50) = qword_1800B2E50 | 0x80;
      goto LABEL_62;
    }
  }
LABEL_64:
  wil::details::lambda_call__lambda_93184ccf0434d78c50c07b8a3875dc64___::_lambda_call__lambda_93184ccf0434d78c50c07b8a3875dc64___(v27);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18005aee4  mov     [rsp-18h+arg_0], rbx
0x18005aee9  mov     [rsp-18h+arg_10], rsi
0x18005aeee  push    rbp
0x18005aeef  push    rdi
0x18005aef0  push    r14
0x18005aef2  mov     rbp, rsp
0x18005aef5  sub     rsp, 80h
0x18005aefc  mov     rax, cs:__security_cookie
0x18005af03  xor     rax, rsp
0x18005af06  mov     [rbp+var_8], rax
0x18005af0a  mov     edi, edx
0x18005af0c  xor     esi, esi
0x18005af0e  mov     [rbp+var_48], rsi
0x18005af12  mov     [rbp+var_50], sil
0x18005af16  mov     [rbp+var_4F], sil
0x18005af1a  mov     [rbp+var_4E], sil
0x18005af1e  mov     [rbp+var_4D], sil
0x18005af22  mov     [rbp+var_4C], sil
0x18005af26  mov     [rbp+var_4B], sil
0x18005af2a  xorps   xmm0, xmm0
0x18005af2d  xor     eax, eax
0x18005af2f  movups  xmmword ptr [rbp+Buffer], xmm0
0x18005af33  mov     [rbp+var_10], eax
0x18005af36  lea     rdx, [rbp+var_48]
0x18005af3a  lea     rcx, [rbp+var_38]
0x18005af3e  call    _lambda_2a70c627909d6c04886f368e19249c19____lambda_2a70c627909d6c04886f368e19249c19_
0x18005af43  mov     rdx, rax
0x18005af46  lea     rcx, [rbp+var_30]
0x18005af4a  call    wil__scope_exit__lambda_2a70c627909d6c04886f368e19249c19___
0x18005af4f  nop
0x18005af50  mov     ecx, edi
0x18005af52  sub     ecx, 1
0x18005af55  jz      short loc_18005AF8E
0x18005af57  cmp     ecx, 5
0x18005af5a  jnz     loc_18005B25A
0x18005af60  lea     r8, [rbp+var_48]
0x18005af64  lea     edx, [rsi+3]
0x18005af67  mov     rcx, cs:?GlobalPolicyHandle@@3PEAXEA; void * GlobalPolicyHandle
0x18005af6e  call    cs:__imp_LsarQueryDomainInformationPolicy
0x18005af74  mov     ebx, eax
0x18005af76  test    eax, eax
0x18005af78  js      loc_18005B25C
0x18005af7e  cmp     [rbp+var_48], rsi
0x18005af82  jnz     short loc_18005B003
0x18005af84  mov     ebx, 0C0000001h
0x18005af89  jmp     loc_18005B25C
0x18005af8e  lea     rax, [rbp+var_4F]
0x18005af92  mov     qword ptr [rsp+80h+var_60], rax
0x18005af97  lea     r9, [rbp+var_50]
0x18005af9b  xor     r8d, r8d
0x18005af9e  xor     edx, edx
0x18005afa0  mov     ecx, 9Dh
0x18005afa5  call    cs:__imp_LsaIAdtAuditingEnabledBySubCategory
0x18005afab  mov     ebx, eax
0x18005afad  test    eax, eax
0x18005afaf  js      loc_18005B25C
0x18005afb5  lea     rax, [rbp+var_4D]
0x18005afb9  mov     qword ptr [rsp+80h+var_60], rax
0x18005afbe  lea     r9, [rbp+var_4E]
0x18005afc2  xor     r8d, r8d
0x18005afc5  xor     edx, edx
0x18005afc7  mov     ecx, 9Fh
0x18005afcc  call    cs:__imp_LsaIAdtAuditingEnabledBySubCategory
0x18005afd2  mov     ebx, eax
0x18005afd4  test    eax, eax
0x18005afd6  js      loc_18005B25C
0x18005afdc  lea     rax, [rbp+var_4B]
0x18005afe0  mov     qword ptr [rsp+80h+var_60], rax
0x18005afe5  lea     r9, [rbp+var_4C]
0x18005afe9  xor     r8d, r8d
0x18005afec  xor     edx, edx
0x18005afee  mov     ecx, 9Ch
0x18005aff3  call    cs:__imp_LsaIAdtAuditingEnabledBySubCategory
0x18005aff9  mov     ebx, eax
0x18005affb  test    eax, eax
0x18005affd  js      loc_18005B25C
0x18005b003  mov     r14d, 1
0x18005b009  mov     dl, r14b; Wait
0x18005b00c  lea     rcx, Resource; Resource
0x18005b013  call    cs:__imp_RtlAcquireResourceExclusive
0x18005b019  sub     edi, r14d
0x18005b01c  jz      loc_18005B1ED
0x18005b022  cmp     edi, 5
0x18005b025  jnz     loc_18005B24D
0x18005b02b  lea     rbx, WPP_GLOBAL_Control
0x18005b032  lea     edi, [r14+9]
0x18005b036  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b03d  cmp     rcx, rbx
0x18005b040  jz      loc_18005B0D7
0x18005b046  test    byte ptr [rcx+1Ch], 4
0x18005b04a  jz      short loc_18005B066
0x18005b04c  mov     edx, edi
0x18005b04e  mov     r9, [rbp+var_48]
0x18005b052  mov     r9, [r9+8]
0x18005b056  mov     rcx, [rcx+10h]
0x18005b05a  call    WPP_SF_i
0x18005b05f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b066  cmp     rcx, rbx
0x18005b069  jz      short loc_18005B0D7
0x18005b06b  test    byte ptr [rcx+1Ch], 4
0x18005b06f  jz      short loc_18005B08E
0x18005b071  mov     edx, 0Bh
0x18005b076  mov     r9, [rbp+var_48]
0x18005b07a  mov     r9, [r9+10h]
0x18005b07e  mov     rcx, [rcx+10h]
0x18005b082  call    WPP_SF_i
0x18005b087  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b08e  cmp     rcx, rbx
0x18005b091  jz      short loc_18005B0D7
0x18005b093  test    byte ptr [rcx+1Ch], 4
0x18005b097  jz      short loc_18005B0B6
0x18005b099  mov     edx, 0Ch
0x18005b09e  mov     r9, [rbp+var_48]
0x18005b0a2  mov     r9, [r9+18h]
0x18005b0a6  mov     rcx, [rcx+10h]
0x18005b0aa  call    WPP_SF_i
0x18005b0af  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b0b6  cmp     rcx, rbx
0x18005b0b9  jz      short loc_18005B0D7
0x18005b0bb  test    byte ptr [rcx+1Ch], 4
0x18005b0bf  jz      short loc_18005B0D7
0x18005b0c1  mov     edx, 0Dh
0x18005b0c6  mov     r9, [rbp+var_48]
0x18005b0ca  mov     r9, [r9+20h]
0x18005b0ce  mov     rcx, [rcx+10h]
0x18005b0d2  call    WPP_SF_i
0x18005b0d7  mov     r8, [rbp+var_48]
0x18005b0db  mov     rax, [r8+8]
0x18005b0df  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005b0e3  jle     loc_18005B16A
0x18005b0e9  cmp     qword ptr [r8+10h], 0FFFFFFFFFFFFFFFFh
0x18005b0ee  jle     short loc_18005B16A
0x18005b0f0  cmp     qword ptr [r8+18h], 0FFFFFFFFFFFFFFFFh
0x18005b0f5  jle     short loc_18005B16A
0x18005b0f7  cmp     qword ptr [r8+20h], 0FFFFFFFFFFFFFFFFh
0x18005b0fc  jle     short loc_18005B16A
0x18005b0fe  test    rax, rax
0x18005b101  jz      short loc_18005B16A
0x18005b103  cmp     [r8+10h], rsi
0x18005b107  jz      short loc_18005B16A
0x18005b109  mov     cs:qword_1800B2E30, rax
0x18005b110  mov     rax, [r8+10h]
0x18005b114  mov     cs:qword_1800B2E38, rax
0x18005b11b  mov     rax, [r8+18h]
0x18005b11f  mov     cs:qword_1800B2E40, rax
0x18005b126  mov     edx, 5F5E100h
0x18005b12b  cmp     [r8+20h], rdx
0x18005b12f  cmovg   rdx, [r8+20h]; union _LARGE_INTEGER
0x18005b134  mov     qword ptr cs:?SkewTime@@3T_LARGE_INTEGER@@A, rdx; _LARGE_INTEGER SkewTime ...
0x18005b13b  mov     rcx, cs:?Authenticators@@3PEAVCAuthenticatorList@@EA; Table
0x18005b142  test    rcx, rcx
0x18005b145  jz      short loc_18005B157
0x18005b147  call    ?SetMaxAge@CAuthenticatorList@@QEAAXT_LARGE_INTEGER@@@Z; CAuthenticatorList::SetMaxAge(_LARGE_INTEGER)
0x18005b14c  mov     r8, [rbp+var_48]
0x18005b150  mov     rdx, qword ptr cs:?SkewTime@@3T_LARGE_INTEGER@@A; union _LARGE_INTEGER
0x18005b157  mov     rcx, cs:?ReplayDetect@@3PEAVCAuthenticatorList@@EA; Table
0x18005b15e  test    rcx, rcx
0x18005b161  jz      short loc_18005B1D3
0x18005b163  call    ?SetMaxAge@CAuthenticatorList@@QEAAXT_LARGE_INTEGER@@@Z; CAuthenticatorList::SetMaxAge(_LARGE_INTEGER)
0x18005b168  jmp     short loc_18005B1CF
0x18005b16a  mov     [rbp+var_40], 0C000000Dh
0x18005b171  mov     r8d, edi; Radix
0x18005b174  lea     rdx, [rbp+Buffer]; Buffer
0x18005b178  mov     ecx, 6; Value
0x18005b17d  call    cs:__imp__itow
0x18005b183  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b18a  cmp     rcx, rbx
0x18005b18d  jz      short loc_18005B1AA
0x18005b18f  test    [rcx+1Ch], r14b
0x18005b193  jz      short loc_18005B1AA
0x18005b195  mov     edx, 0Eh
0x18005b19a  lea     r8, WPP_39025eb542cc3a17cc5bb89d70ac2bcd_Traceguids
0x18005b1a1  mov     rcx, [rcx+10h]
0x18005b1a5  call    WPP_SF_
0x18005b1aa  lea     rax, [rbp+Buffer]
0x18005b1ae  mov     [rsp+80h+var_58], rax
0x18005b1b3  mov     [rsp+80h+var_60], r14d; unsigned int
0x18005b1b8  lea     r9, [rbp+var_40]; void *
0x18005b1bc  mov     edx, 0C0000005h; unsigned int
0x18005b1c1  mov     r8d, 4; unsigned int
0x18005b1c7  mov     ecx, r14d; unsigned __int16
0x18005b1ca  call    ?ReportServiceEvent@@YAKGKKPEAXKZZ; ReportServiceEvent(ushort,ulong,ulong,void *,ulong,...)
0x18005b1cf  mov     r8, [rbp+var_48]
0x18005b1d3  test    byte ptr [r8], 80h
0x18005b1d7  jz      short loc_18005B1E3
0x18005b1d9  bts     dword ptr cs:qword_1800B2E50, 7
0x18005b1e1  jmp     short loc_18005B24D
0x18005b1e3  btr     dword ptr cs:qword_1800B2E50, 7
0x18005b1eb  jmp     short loc_18005B24D
0x18005b1ed  mov     eax, dword ptr cs:qword_1800B2E50+4
0x18005b1f3  cmp     [rbp+var_50], sil
0x18005b1f7  jz      short loc_18005B1FE
0x18005b1f9  or      eax, 4
0x18005b1fc  jmp     short loc_18005B201
0x18005b1fe  and     eax, 0FFFFFFFBh
0x18005b201  cmp     [rbp+var_4F], sil
0x18005b205  jz      short loc_18005B20C
0x18005b207  or      eax, 8
0x18005b20a  jmp     short loc_18005B20F
0x18005b20c  and     eax, 0FFFFFFF7h
0x18005b20f  cmp     [rbp+var_4E], sil
0x18005b213  jz      short loc_18005B21A
0x18005b215  or      eax, r14d
0x18005b218  jmp     short loc_18005B21D
0x18005b21a  and     eax, 0FFFFFFFEh
0x18005b21d  cmp     [rbp+var_4D], sil
0x18005b221  jz      short loc_18005B228
0x18005b223  or      eax, 2
0x18005b226  jmp     short loc_18005B22B
0x18005b228  and     eax, 0FFFFFFFDh
0x18005b22b  cmp     [rbp+var_4C], sil
0x18005b22f  jz      short loc_18005B236
0x18005b231  or      eax, 10h
0x18005b234  jmp     short loc_18005B239
0x18005b236  and     eax, 0FFFFFFEFh
0x18005b239  cmp     [rbp+var_4B], sil
0x18005b23d  jz      short loc_18005B244
0x18005b23f  or      eax, 20h
0x18005b242  jmp     short loc_18005B247
0x18005b244  and     eax, 0FFFFFFDFh
0x18005b247  mov     dword ptr cs:qword_1800B2E50+4, eax
0x18005b24d  lea     rcx, Resource; Resource
0x18005b254  call    cs:__imp_RtlReleaseResource
0x18005b25a  mov     ebx, esi
0x18005b25c  lea     rcx, [rbp+var_30]
0x18005b260  call    wil__details__lambda_call__lambda_93184ccf0434d78c50c07b8a3875dc64______lambda_call__lambda_93184ccf0434d78c50c07b8a3875dc64___
0x18005b265  mov     eax, ebx
0x18005b267  mov     rcx, [rbp+var_8]
0x18005b26b  xor     rcx, rsp; StackCookie
0x18005b26e  call    __security_check_cookie
0x18005b273  lea     r11, [rsp+80h+var_s0]
0x18005b27b  mov     rbx, [r11+20h]
0x18005b27f  mov     rsi, [r11+30h]
0x18005b283  mov     rsp, r11
0x18005b286  pop     r14
0x18005b288  pop     rdi
0x18005b289  pop     rbp
0x18005b28a  retn
```
