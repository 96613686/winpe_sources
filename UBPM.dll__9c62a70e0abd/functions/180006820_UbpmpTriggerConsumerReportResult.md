# UbpmpTriggerConsumerReportResult

- ea: `0x180006820`
- end: `0x180006e0c`
- name: `UbpmpTriggerConsumerReportResult`
- size: `1516`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180007000`
- `0x180009a30`
- `0x18000a230`
- `0x180011480`
- `0x180011a90`

## callees

- `0x180003790`
- `0x180006820`
- `0x1800182a0`
- `0x1800373c0`
- `0x180040260`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800069e1`
- `ntdll!RtlInitUnicodeString` at `0x180006b8c`
- `ntdll!RtlInitUnicodeString` at `0x1800069e1`
- `ntdll!RtlInitUnicodeString` at `0x180006b8c`
- `ntdll!RtlHashUnicodeString` at `0x180006a01`
- `ntdll!RtlHashUnicodeString` at `0x180006bac`
- `ntdll!RtlHashUnicodeString` at `0x180006a01`
- `ntdll!RtlHashUnicodeString` at `0x180006bac`
- `ntdll!WinSqmIsOptedIn` at `0x1800068ca`
- `ntdll!WinSqmIsOptedIn` at `0x180006d69`
- `ntdll!WinSqmIsOptedIn` at `0x1800068ca`
- `ntdll!WinSqmIsOptedIn` at `0x180006d69`
- `ntdll!WinSqmAddToStream` at `0x180006dc7`
- `ntdll!WinSqmAddToStream` at `0x180006dc7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006d0f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006d0f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800068df`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800068df`

## pseudocode

```c
__int64 __fastcall UbpmpTriggerConsumerReportResult(__int64 a1, int a2, char a3)
{
  unsigned int v6; // r12d
  int v7; // esi
  ULONG v8; // ebx
  unsigned int v9; // r14d
  unsigned __int64 v10; // r9
  unsigned __int64 v11; // r8
  __int64 v12; // rdx
  NTSTATUS v13; // eax
  ULONG v14; // r15d
  struct _FILETIME v15; // rax
  DWORD dwHighDateTime; // eax
  unsigned __int64 v17; // r9
  unsigned __int64 v18; // r10
  unsigned __int64 v19; // r8
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 *v24; // rcx
  __int64 v25; // rax
  unsigned int v27; // eax
  char v29; // [rsp+30h] [rbp-D0h]
  ULONG HashValue; // [rsp+34h] [rbp-CCh] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-C8h] BYREF
  int v32; // [rsp+40h] [rbp-C0h]
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v34; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v35[2]; // [rsp+5Ch] [rbp-A4h] BYREF
  int IsOptedIn; // [rsp+64h] [rbp-9Ch]
  __int64 v37; // [rsp+68h] [rbp-98h] BYREF
  __int64 v38; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v39[36]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE UserData[24]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v41; // [rsp+B8h] [rbp-48h]
  __int128 v42; // [rsp+C8h] [rbp-38h]
  __int128 v43; // [rsp+D8h] [rbp-28h]
  __int64 v44; // [rsp+E8h] [rbp-18h]
  _DWORD *v45; // [rsp+F0h] [rbp-10h]
  __int64 v46; // [rsp+F8h] [rbp-8h]
  unsigned int *v47; // [rsp+100h] [rbp+0h]
  __int64 v48; // [rsp+108h] [rbp+8h]
  ULONG *p_HashValue; // [rsp+110h] [rbp+10h]
  __int64 v50; // [rsp+118h] [rbp+18h]

  SystemTimeAsFileTime = 0;
  memset(v39, 0, sizeof(v39));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_SL(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      75,
      (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
      *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL),
      a2);
  v6 = UbpmStatsOperation(a1, 0, v39);
  if ( !v6 )
  {
    IsOptedIn = WinSqmIsOptedIn();
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( a3 == 1 )
    {
      v7 = *(_DWORD *)&v39[24];
      v8 = 0x7FFFFFFF;
      v32 = 0;
      if ( *(_QWORD *)&v39[12] )
      {
        LODWORD(v10) = 0;
        if ( *(_QWORD *)&v39[12] < *(unsigned __int64 *)&SystemTimeAsFileTime
          && *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&v39[12] < 0x98968000000000uLL )
        {
          v10 = (*(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&v39[12]) / 0x989680uLL;
        }
        v9 = (unsigned int)v10 / 0x3C;
      }
      else
      {
        v9 = 0x7FFFFFFF;
      }
      if ( *(_DWORD *)&v39[32] || *(_DWORD *)&v39[28] )
      {
        LODWORD(v11) = 0;
        if ( *(_QWORD *)&v39[28] < *(unsigned __int64 *)&SystemTimeAsFileTime
          && *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&v39[28] < 0x98968000000000uLL )
        {
          v11 = (*(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&v39[28]) / 0x989680uLL;
        }
        v8 = (unsigned int)v11 / 0x3C;
      }
      v12 = *(_QWORD *)(a1 + 24);
      HashValue = 0;
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(v12 + 8));
      v13 = RtlHashUnicodeString(&DestinationString, 1u, 1u, &HashValue);
      v14 = 0;
      *(_DWORD *)&v39[24] = a2;
      *(struct _FILETIME *)&v39[12] = SystemTimeAsFileTime;
      if ( v13 >= 0 )
        v14 = HashValue;
LABEL_55:
      v6 = UbpmStatsOperation(a1, 1, v39);
      if ( !v6 )
      {
        if ( IsOptedIn )
        {
          *(_DWORD *)UserData = 0;
          *(_OWORD *)&UserData[8] = 0;
          v44 = 0;
          v41 = 0;
          v42 = 0;
          v43 = 0;
          if ( (unsigned int)WinSqmIsOptedIn() )
          {
            if ( v14 )
            {
              LODWORD(v44) = v32;
              *(_DWORD *)&UserData[8] = v14;
              *(_DWORD *)UserData = 1;
              LODWORD(v41) = v7;
              *(_DWORD *)&UserData[16] = 1;
              LODWORD(v42) = v9;
              DWORD2(v41) = 1;
              LODWORD(v43) = v8;
              DWORD2(v42) = 1;
              DWORD2(v43) = 1;
              WinSqmAddToStream(0, 11240, 5, UserData);
            }
          }
        }
      }
      goto LABEL_60;
    }
    if ( !a3 )
    {
      v7 = *(_DWORD *)&v39[24];
      v29 = 0;
      if ( *(_DWORD *)&v39[24] != -2147023605
        && *(_DWORD *)&v39[24] != 1291
        && *(_DWORD *)&v39[24] != -2147023829
        && *(_DWORD *)&v39[24] != 1067 )
      {
        if ( a2 != -2147023605 && a2 != 1291 && a2 != -2147023829 )
        {
          v15 = *(struct _FILETIME *)&v39[28];
          if ( a2 != 1067 )
            v15 = SystemTimeAsFileTime;
          *(struct _FILETIME *)&v39[28] = v15;
        }
        v7 = a2;
        *(_DWORD *)&v39[24] = a2;
        v29 = 1;
      }
      dwHighDateTime = SystemTimeAsFileTime.dwHighDateTime;
      v8 = 0x7FFFFFFF;
      v32 = 1;
      if ( *(_QWORD *)&v39[12] )
      {
        LODWORD(v17) = 0;
        v18 = *(unsigned int *)&v39[12] | (HIDWORD(*(_QWORD *)&v39[12]) << 32);
        if ( v18 < *(_QWORD *)&SystemTimeAsFileTime && *(_QWORD *)&SystemTimeAsFileTime - v18 < 0x98968000000000LL )
          v17 = (*(_QWORD *)&SystemTimeAsFileTime - v18) / 0x989680;
        dwHighDateTime = SystemTimeAsFileTime.dwHighDateTime;
        v9 = (unsigned int)v17 / 0x3C;
      }
      else
      {
        v9 = 0x7FFFFFFF;
      }
      if ( *(_DWORD *)&v39[32] || *(_DWORD *)&v39[28] )
      {
        LODWORD(v19) = 0;
        v20 = SystemTimeAsFileTime.dwLowDateTime | ((unsigned __int64)dwHighDateTime << 32);
        if ( *(_QWORD *)&v39[28] < v20 )
        {
          v21 = v20 - *(_QWORD *)&v39[28];
          if ( v21 < 0x98968000000000LL )
            v19 = v21 / 0x989680;
        }
        v8 = (unsigned int)v19 / 0x3C;
      }
      v22 = *(_QWORD *)(a1 + 24);
      HashValue = 0;
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(v22 + 8));
      v14 = 0;
      if ( RtlHashUnicodeString(&DestinationString, 1u, 1u, &HashValue) >= 0 )
        v14 = HashValue;
      if ( (unsigned int)dword_18004F0F0 > 3 )
      {
        v35[0] = *(_DWORD *)&v39[24];
        v37 = *(_QWORD *)&v39[28];
        v38 = *(_QWORD *)&v39[12];
        v23 = *(_QWORD *)(a1 + 24);
        HashValue = v8;
        v34 = v9;
        v50 = 4;
        v24 = *(__int64 **)(v23 + 8);
        p_HashValue = &HashValue;
        v47 = &v34;
        v45 = v35;
        *((_QWORD *)&v43 + 1) = &v37;
        *((_QWORD *)&v42 + 1) = &v38;
        v48 = 4;
        v46 = 4;
        v44 = 8;
        *(_QWORD *)&v43 = 8;
        if ( v24 )
        {
          v25 = -1;
          while ( *((_WORD *)v24 + ++v25) != 0 )
            ;
          v27 = 2 * v25 + 2;
        }
        else
        {
          v24 = &qword_1800439C0;
          v27 = 2;
        }
        *(_QWORD *)&v42 = v27;
        *(_DWORD *)(&DestinationString.MaximumLength + 1) = 3;
        *(_QWORD *)UserData = off_18004F0F8;
        *((_QWORD *)&v41 + 1) = v24;
        *(_DWORD *)&DestinationString.Length = 184549376;
        DestinationString.Buffer = 0;
        *(_QWORD *)&UserData[8] = *(unsigned __int16 *)off_18004F0F8 | 0x200000000LL;
        *(_QWORD *)&UserData[16] = &byte_1800461CF;
        *(_QWORD *)&v41 = 0x10000007FLL;
        v35[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(
          RegHandle,
          (PCEVENT_DESCRIPTOR)&DestinationString,
          0,
          0,
          8u,
          (PEVENT_DATA_DESCRIPTOR)UserData);
      }
      if ( v29 == 1 )
        goto LABEL_55;
    }
  }
LABEL_60:
  UbpmTriggerConsumerPublishStateChange(a1);
  return v6;
}

```

## disassembly

```asm
0x180006820  push    rbp
0x180006822  push    rbx
0x180006823  push    rdi
0x180006824  push    r12
0x180006826  push    r13
0x180006828  push    r14
0x18000682a  lea     rbp, [rsp-38h]
0x18000682f  sub     rsp, 138h
0x180006836  mov     rax, cs:__security_cookie
0x18000683d  xor     rax, rsp
0x180006840  mov     [rbp+60h+var_40], rax
0x180006844  xor     eax, eax
0x180006846  xorps   xmm0, xmm0
0x180006849  xor     r14d, r14d
0x18000684c  mov     dword ptr [rbp+60h+var_D8+10h], eax
0x18000684f  mov     qword ptr [rsp+160h+SystemTimeAsFileTime.dwLowDateTime], r14
0x180006854  movzx   ebx, r8b
0x180006858  mov     edi, edx
0x18000685a  mov     r13, rcx
0x18000685d  movups  [rsp+160h+var_E8], xmm0
0x180006862  movups  xmmword ptr [rbp+60h+var_D8], xmm0
0x180006866  mov     rcx, cs:WPP_GLOBAL_Control
0x18000686d  lea     rax, WPP_GLOBAL_Control
0x180006874  cmp     rcx, rax
0x180006877  jz      short loc_1800068A0
0x180006879  test    byte ptr [rcx+1Ch], 4
0x18000687d  jz      short loc_1800068A0
0x18000687f  mov     r9, [r13+18h]
0x180006883  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18000688a  mov     rcx, [rcx+10h]
0x18000688e  mov     edx, 4Bh ; 'K'
0x180006893  mov     [rsp+160h+UserDataCount], edi
0x180006897  mov     r9, [r9+8]
0x18000689b  call    WPP_SF_SL
0x1800068a0  lea     r8, [rsp+160h+var_E8]
0x1800068a5  xor     edx, edx
0x1800068a7  mov     rcx, r13
0x1800068aa  call    UbpmStatsOperation
0x1800068af  mov     r12d, eax
0x1800068b2  test    eax, eax
0x1800068b4  jnz     loc_180006DE3
0x1800068ba  mov     [rsp+160h+arg_10], rsi
0x1800068c2  mov     [rsp+160h+var_30], r15
0x1800068ca  call    cs:__imp_WinSqmIsOptedIn
0x1800068d1  nop     dword ptr [rax+rax+00h]
0x1800068d6  lea     rcx, [rsp+160h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800068db  mov     [rsp+160h+var_FC], eax
0x1800068df  call    cs:__imp_GetSystemTimeAsFileTime
0x1800068e6  nop     dword ptr [rax+rax+00h]
0x1800068eb  cmp     bl, 1
0x1800068ee  jnz     loc_180006A2B
0x1800068f4  mov     r8d, dword ptr [rbp+60h+var_D8]
0x1800068f8  mov     r15, 98968000000000h
0x180006902  mov     esi, dword ptr [rbp+60h+var_D8+8]
0x180006905  mov     r11, 0D6BF94D5E57A42BDh
0x18000690f  mov     rcx, qword ptr [rsp+160h+SystemTimeAsFileTime.dwLowDateTime]
0x180006914  mov     ebx, 7FFFFFFFh
0x180006919  mov     r12d, [rsp+160h+SystemTimeAsFileTime.dwHighDateTime]
0x18000691e  mov     r10d, dword ptr [rbp+60h+var_E8+0Ch]
0x180006922  mov     [rsp+160h+var_120], r14d
0x180006927  test    r8d, r8d
0x18000692a  jnz     short loc_180006936
0x18000692c  test    r10d, r10d
0x18000692f  jnz     short loc_180006936
0x180006931  mov     r14d, ebx
0x180006934  jmp     short loc_180006975
0x180006936  shl     r8, 20h
0x18000693a  mov     rdx, r12
0x18000693d  shl     rdx, 20h
0x180006941  or      r8, r10
0x180006944  mov     eax, ecx
0x180006946  mov     r9d, r14d
0x180006949  or      rdx, rax
0x18000694c  cmp     r8, rdx
0x18000694f  jnb     short loc_180006966
0x180006951  sub     rdx, r8
0x180006954  cmp     rdx, r15
0x180006957  jnb     short loc_180006966
0x180006959  mov     rax, r11
0x18000695c  mul     rdx
0x18000695f  mov     r9, rdx
0x180006962  shr     r9, 17h
0x180006966  mov     eax, 88888889h
0x18000696b  mul     r9d
0x18000696e  mov     r14d, edx
0x180006971  shr     r14d, 5
0x180006975  mov     r9d, dword ptr [rbp+60h+var_D8+10h]
0x180006979  mov     r10d, dword ptr [rbp+60h+var_D8+0Ch]
0x18000697d  test    r9d, r9d
0x180006980  jnz     short loc_180006987
0x180006982  test    r10d, r10d
0x180006985  jz      short loc_1800069C4
0x180006987  shl     r9, 20h
0x18000698b  mov     rdx, r12
0x18000698e  shl     rdx, 20h
0x180006992  xor     r8d, r8d
0x180006995  mov     eax, ecx
0x180006997  or      r9, r10
0x18000699a  or      rdx, rax
0x18000699d  cmp     r9, rdx
0x1800069a0  jnb     short loc_1800069B7
0x1800069a2  sub     rdx, r9
0x1800069a5  cmp     rdx, r15
0x1800069a8  jnb     short loc_1800069B7
0x1800069aa  mov     rax, r11
0x1800069ad  mul     rdx
0x1800069b0  mov     r8, rdx
0x1800069b3  shr     r8, 17h
0x1800069b7  mov     eax, 88888889h
0x1800069bc  mul     r8d
0x1800069bf  mov     ebx, edx
0x1800069c1  shr     ebx, 5
0x1800069c4  mov     rdx, [r13+18h]
0x1800069c8  lea     rcx, [rsp+160h+DestinationString]; DestinationString
0x1800069cd  xorps   xmm0, xmm0
0x1800069d0  mov     [rsp+160h+HashValue], 0
0x1800069d8  movups  xmmword ptr [rsp+160h+DestinationString.Length], xmm0
0x1800069dd  mov     rdx, [rdx+8]; SourceString
0x1800069e1  call    cs:__imp_RtlInitUnicodeString
0x1800069e8  nop     dword ptr [rax+rax+00h]
0x1800069ed  mov     r8d, 1; HashAlgorithm
0x1800069f3  lea     r9, [rsp+160h+HashValue]; HashValue
0x1800069f8  movzx   edx, r8b; CaseInSensitive
0x1800069fc  lea     rcx, [rsp+160h+DestinationString]; String
0x180006a01  call    cs:__imp_RtlHashUnicodeString
0x180006a08  nop     dword ptr [rax+rax+00h]
0x180006a0d  xor     r15d, r15d
0x180006a10  mov     dword ptr [rbp+60h+var_D8+8], edi
0x180006a13  test    eax, eax
0x180006a15  mov     rax, qword ptr [rsp+160h+SystemTimeAsFileTime.dwLowDateTime]
0x180006a1a  mov     qword ptr [rbp+60h+var_E8+0Ch], rax
0x180006a1e  cmovns  r15d, [rsp+160h+HashValue]
0x180006a24  xor     edi, edi
0x180006a26  jmp     loc_180006D26
0x180006a2b  test    bl, bl
0x180006a2d  jnz     loc_180006DD3
0x180006a33  mov     esi, dword ptr [rbp+60h+var_D8+8]
0x180006a36  mov     rcx, qword ptr [rsp+160h+SystemTimeAsFileTime.dwLowDateTime]
0x180006a3b  mov     [rsp+160h+var_130], r14b
0x180006a40  cmp     esi, 8007050Bh
0x180006a46  jz      short loc_180006A94
0x180006a48  cmp     esi, 50Bh
0x180006a4e  jz      short loc_180006A94
0x180006a50  cmp     esi, 8007042Bh
0x180006a56  jz      short loc_180006A94
0x180006a58  cmp     esi, 42Bh
0x180006a5e  jz      short loc_180006A94
0x180006a60  cmp     edi, 8007050Bh
0x180006a66  jz      short loc_180006A8A
0x180006a68  cmp     edi, 50Bh
0x180006a6e  jz      short loc_180006A8A
0x180006a70  cmp     edi, 8007042Bh
0x180006a76  jz      short loc_180006A8A
0x180006a78  mov     rax, qword ptr [rbp+60h+var_D8+0Ch]
0x180006a7c  cmp     edi, 42Bh
0x180006a82  cmovnz  rax, rcx
0x180006a86  mov     qword ptr [rbp+60h+var_D8+0Ch], rax
0x180006a8a  mov     esi, edi
0x180006a8c  mov     dword ptr [rbp+60h+var_D8+8], edi
0x180006a8f  mov     [rsp+160h+var_130], 1
0x180006a94  mov     r8, qword ptr [rbp+60h+var_E8+0Ch]
0x180006a98  mov     r15, 98968000000000h
0x180006aa2  mov     eax, [rsp+160h+SystemTimeAsFileTime.dwHighDateTime]
0x180006aa6  mov     r11, 0D6BF94D5E57A42BDh
0x180006ab0  mov     edi, dword ptr [rbp+60h+var_E8+0Ch]
0x180006ab3  mov     ebx, 7FFFFFFFh
0x180006ab8  shr     r8, 20h
0x180006abc  mov     [rsp+160h+var_120], 1
0x180006ac4  test    r8d, r8d
0x180006ac7  jnz     short loc_180006AD2
0x180006ac9  test    edi, edi
0x180006acb  jnz     short loc_180006AD2
0x180006acd  mov     r14d, ebx
0x180006ad0  jmp     short loc_180006B18
0x180006ad2  mov     rdx, rax
0x180006ad5  mov     r10, r8
0x180006ad8  shl     rdx, 20h
0x180006adc  mov     r9d, r14d
0x180006adf  shl     r10, 20h
0x180006ae3  mov     eax, ecx
0x180006ae5  or      r10, rdi
0x180006ae8  or      rdx, rax
0x180006aeb  cmp     r10, rdx
0x180006aee  jnb     short loc_180006B05
0x180006af0  sub     rdx, r10
0x180006af3  cmp     rdx, r15
0x180006af6  jnb     short loc_180006B05
0x180006af8  mov     rax, r11
0x180006afb  mul     rdx
0x180006afe  mov     r9, rdx
0x180006b01  shr     r9, 17h
0x180006b05  mov     eax, 88888889h
0x180006b0a  mul     r9d
0x180006b0d  mov     eax, [rsp+160h+SystemTimeAsFileTime.dwHighDateTime]
0x180006b11  mov     r14d, edx
0x180006b14  shr     r14d, 5
0x180006b18  mov     r9, qword ptr [rbp+60h+var_D8+0Ch]
0x180006b1c  mov     r10d, dword ptr [rbp+60h+var_D8+0Ch]
0x180006b20  shr     r9, 20h
0x180006b24  test    r9d, r9d
0x180006b27  jnz     short loc_180006B32
0x180006b29  test    r10d, r10d
0x180006b2c  jnz     short loc_180006B32
0x180006b2e  xor     edi, edi
0x180006b30  jmp     short loc_180006B73
0x180006b32  mov     edx, eax
0x180006b34  xor     edi, edi
0x180006b36  mov     eax, ecx
0x180006b38  mov     r8d, edi
0x180006b3b  shl     rdx, 20h
0x180006b3f  mov     rcx, r9
0x180006b42  shl     rcx, 20h
0x180006b46  or      rdx, rax
0x180006b49  or      rcx, r10
0x180006b4c  cmp     rcx, rdx
0x180006b4f  jnb     short loc_180006B66
0x180006b51  sub     rdx, rcx
0x180006b54  cmp     rdx, r15
0x180006b57  jnb     short loc_180006B66
0x180006b59  mov     rax, r11
0x180006b5c  mul     rdx
0x180006b5f  mov     r8, rdx
0x180006b62  shr     r8, 17h
0x180006b66  mov     eax, 88888889h
0x180006b6b  mul     r8d
0x180006b6e  mov     ebx, edx
0x180006b70  shr     ebx, 5
0x180006b73  mov     rdx, [r13+18h]
0x180006b77  lea     rcx, [rsp+160h+DestinationString]; DestinationString
0x180006b7c  xorps   xmm0, xmm0
0x180006b7f  mov     [rsp+160h+HashValue], edi
0x180006b83  movups  xmmword ptr [rsp+160h+DestinationString.Length], xmm0
0x180006b88  mov     rdx, [rdx+8]; SourceString
0x180006b8c  call    cs:__imp_RtlInitUnicodeString
0x180006b93  nop     dword ptr [rax+rax+00h]
0x180006b98  mov     r8d, 1; HashAlgorithm
0x180006b9e  lea     r9, [rsp+160h+HashValue]; HashValue
0x180006ba3  movzx   edx, r8b; CaseInSensitive
0x180006ba7  lea     rcx, [rsp+160h+DestinationString]; String
0x180006bac  call    cs:__imp_RtlHashUnicodeString
0x180006bb3  nop     dword ptr [rax+rax+00h]
0x180006bb8  test    eax, eax
0x180006bba  mov     r15d, edi
0x180006bbd  mov     eax, cs:dword_18004F0F0
0x180006bc3  cmovns  r15d, [rsp+160h+HashValue]
0x180006bc9  cmp     eax, 3
0x180006bcc  jbe     loc_180006D1B
0x180006bd2  mov     eax, dword ptr [rbp+60h+var_D8+8]
0x180006bd5  mov     [rsp+160h+var_104], eax
0x180006bd9  mov     rax, qword ptr [rbp+60h+var_D8+0Ch]
0x180006bdd  mov     [rsp+160h+var_F8], rax
0x180006be2  mov     rax, qword ptr [rbp+60h+var_E8+0Ch]
0x180006be6  mov     [rsp+160h+var_F0], rax
0x180006beb  mov     rax, [r13+18h]
0x180006bef  mov     [rsp+160h+HashValue], ebx
0x180006bf3  mov     [rsp+160h+var_108], r14d
0x180006bf8  mov     [rbp+60h+var_48], 4
0x180006c00  mov     rcx, [rax+8]
0x180006c04  lea     rax, [rsp+160h+HashValue]
0x180006c09  mov     [rbp+60h+var_50], rax
0x180006c0d  lea     rax, [rsp+160h+var_108]
0x180006c12  mov     [rbp+60h+var_60], rax
0x180006c16  lea     rax, [rsp+160h+var_104]
0x180006c1b  mov     [rbp+60h+var_70], rax
0x180006c1f  lea     rax, [rsp+160h+var_F8]
0x180006c24  mov     qword ptr [rbp+60h+var_88+8], rax
0x180006c28  lea     rax, [rsp+160h+var_F0]
0x180006c2d  mov     qword ptr [rbp+60h+var_98+8], rax
0x180006c31  mov     [rbp+60h+var_58], 4
0x180006c39  mov     [rbp+60h+var_68], 4
0x180006c41  mov     [rbp+60h+var_78], 8
0x180006c49  mov     qword ptr [rbp+60h+var_88], 8
0x180006c51  test    rcx, rcx
0x180006c54  jz      short loc_180006C75
0x180006c56  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180006c5d  nop     dword ptr [rax]
0x180006c60  cmp     word ptr [rcx+rax*2+2], 0
0x180006c66  lea     rax, [rax+1]
0x180006c6a  jnz     short loc_180006C60
0x180006c6c  lea     eax, ds:2[rax*2]
0x180006c73  jmp     short loc_180006C81
0x180006c75  lea     rcx, qword_1800439C0
0x180006c7c  mov     eax, 2
0x180006c81  mov     dword ptr [rbp+60h+var_98], eax
0x180006c84  lea     rdx, [rsp+160h+DestinationString]; EventDescriptor
0x180006c89  movzx   eax, cs:word_1800461C5
0x180006c90  xor     r9d, r9d; RelatedActivityId
0x180006c93  mov     dword ptr [rsp+160h+DestinationString+4], eax
0x180006c97  xor     r8d, r8d; ActivityId
0x180006c9a  mov     rax, cs:off_18004F0F8
0x180006ca1  mov     qword ptr [rbp+60h+var_C0], rax
0x180006ca5  mov     qword ptr [rbp+60h+var_A8+8], rcx
0x180006ca9  lea     rcx, _TraceLoggingMetadata
0x180006cb0  mov     dword ptr [rbp+60h+var_98+4], edi
0x180006cb3  mov     dword ptr [rsp+160h+DestinationString.Length], 0B000000h
0x180006cbb  mov     [rsp+160h+DestinationString.Buffer], rdi
0x180006cc0  movzx   eax, word ptr [rax]
0x180006cc3  mov     dword ptr [rbp+60h+var_C0+8], eax
0x180006cc6  lea     rax, byte_1800461CF
0x180006ccd  mov     qword ptr [rbp+60h+var_C0+10h], rax
  ... truncated ...
```
