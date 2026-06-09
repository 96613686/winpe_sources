# CFileSyncMetadataStore::GetEseParameterSettings(int,ushort const *,ulong *,ulong *,CEcsMemPtr<ushort,0> &,ulong *)

- ea: `0x1800aae64`
- end: `0x1800ab392`
- name: `?GetEseParameterSettings@CFileSyncMetadataStore@@AEAAJHPEBGPEAK1AEAV?$CEcsMemPtr@G$0A@@@1@Z`
- size: `1326`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x1800ab8d4`

## callees

- `0x180007b9c`
- `0x180007e10`
- `0x180011314`
- `0x18002dad0`
- `0x180059d50`
- `0x18008b634`
- `0x1800aab00`
- `0x1800aae64`
- `0x1800abca0`
- `0x1800abd28`
- `0x1800abdbc`
- `0x1800abe4c`
- `0x1800abeec`

## import_xrefs

- `KERNEL32!GetMaximumProcessorCount` at `0x1800ab1b2`
- `KERNEL32!GetMaximumProcessorCount` at `0x1800ab1b2`
- `ADVAPI32!RegGetValueW` at `0x1800ab0cf`
- `ADVAPI32!RegGetValueW` at `0x1800ab123`
- `ADVAPI32!RegGetValueW` at `0x1800ab0cf`
- `ADVAPI32!RegGetValueW` at `0x1800ab123`
- `ADVAPI32!RegCloseKey` at `0x1800ab240`
- `ADVAPI32!RegCloseKey` at `0x1800ab240`
- `ADVAPI32!RegOpenKeyExW` at `0x1800aaf56`
- `ADVAPI32!RegOpenKeyExW` at `0x1800aaf56`

## string_xrefs

- `0x1800ab02d`: `EseReplicaCacheExpirationMs`

## pseudocode

```c
__int64 __fastcall CFileSyncMetadataStore::GetEseParameterSettings(
        __int64 a1,
        int a2,
        const WCHAR *a3,
        unsigned int *a4,
        unsigned int *a5,
        void **a6,
        _DWORD *a7)
{
  _BYTE *v10; // rax
  char v11; // cl
  unsigned int *v12; // rsi
  _DWORD *v13; // rdi
  void **v14; // r12
  unsigned int v15; // ebx
  __int64 v16; // rdx
  int v17; // edi
  PVOID *v18; // r8
  int v19; // r9d
  PVOID *v20; // rcx
  __int16 v21; // ax
  int ValueW; // eax
  int v23; // eax
  bool v24; // sf
  __int16 v25; // ax
  DWORD MaximumProcessorCount; // eax
  char v27; // al
  unsigned int v28; // eax
  _DWORD *v29; // rbx
  unsigned int v30; // ebx
  int phkResult; // [rsp+20h] [rbp-50h]
  int pvData; // [rsp+28h] [rbp-48h]
  int pcbData; // [rsp+30h] [rbp-40h]
  HKEY *p_hkey; // [rsp+40h] [rbp-30h] BYREF
  int LastFailureAsHRESULT; // [rsp+48h] [rbp-28h] BYREF
  int v37; // [rsp+4Ch] [rbp-24h]
  char v38; // [rsp+50h] [rbp-20h]
  const char *v39; // [rsp+58h] [rbp-18h]
  __int64 v40; // [rsp+60h] [rbp-10h]
  __int64 v41; // [rsp+B0h] [rbp+40h] BYREF
  HKEY hkey; // [rsp+C8h] [rbp+58h] BYREF

  v41 = a1;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, &WPP_fe32ad1c437a354a2b591229e586699e_Traceguids);
    v10 = WPP_GLOBAL_Control;
  }
  if ( (v10[68] & 0x40) == 0 || (v11 = 1, v10[65] < 6u) )
    v11 = 0;
  LastFailureAsHRESULT = 0;
  v39 = "CFileSyncMetadataStore::GetEseParameterSettings";
  v37 = 217;
  v38 = v11;
  v40 = 0;
  if ( a4 )
    *a4 = 0;
  v12 = a5;
  if ( a5 )
    *a5 = 0;
  v13 = a7;
  if ( a7 )
    *a7 = 0;
  v14 = a6;
  CEcsMemPtr<CCloudFileSystemApplier::_FS_APPLIER_SWAP_PLAN_ENTRY,0>::Free(a6);
  *v13 = 900000;
  p_hkey = &hkey;
  v15 = 4;
  LODWORD(v41) = 4;
  hkey = 0;
  v17 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x20019u, &hkey);
  v20 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      15,
      (unsigned int)&WPP_fe32ad1c437a354a2b591229e586699e_Traceguids,
      (_DWORD)a3,
      v17);
    v20 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v17 )
  {
    if ( v17 == 2 )
      goto LABEL_51;
    if ( v17 > 0 )
      v17 = (unsigned __int16)v17 | 0x80070000;
    LastFailureAsHRESULT = v17;
    v25 = 318;
    v24 = v17 < 0;
  }
  else
  {
    LastFailureAsHRESULT = lambda_6b12b68f26395bd983e950a4f04aacbb_::operator()(
                             &p_hkey,
                             &c_pwszEcsEseConcurrentTransactions,
                             a4,
                             0);
    v21 = 274;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_20;
    LOWORD(v37) = 274;
    LastFailureAsHRESULT = lambda_6b12b68f26395bd983e950a4f04aacbb_::operator()(
                             &p_hkey,
                             &c_pwszEcsEseConcurrentOperations,
                             v12,
                             a2 == 0 ? 4 : 0);
    v21 = 280;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_20;
    LOWORD(v37) = 280;
    LastFailureAsHRESULT = lambda_6b12b68f26395bd983e950a4f04aacbb_::operator()(
                             &p_hkey,
                             &c_pwszEcsEseConcurrentOperationsMultiplier,
                             &v41,
                             4);
    v21 = 281;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_20;
    LOWORD(v37) = 281;
    LastFailureAsHRESULT = lambda_6b12b68f26395bd983e950a4f04aacbb_::operator()(
                             &p_hkey,
                             &c_pwszEcsEseReplicaCacheExpirationMs,
                             a7,
                             900000);
    v21 = 283;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_20;
    LOWORD(v37) = 283;
    if ( !(_DWORD)v41 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          16,
          (unsigned int)&WPP_fe32ad1c437a354a2b591229e586699e_Traceguids,
          (unsigned int)&c_pwszEcsEseConcurrentOperationsMultiplier,
          4);
      }
      LODWORD(v41) = 4;
    }
    LODWORD(a5) = 0;
    ValueW = RegGetValueW(hkey, 0, c_pwszEcsEseParameterSettings, 0x20u, 0, 0, (LPDWORD)&a5);
    if ( ValueW )
    {
      if ( ValueW == 2 )
        goto LABEL_34;
      if ( ValueW > 0 )
        ValueW = (unsigned __int16)ValueW | 0x80070000;
      LastFailureAsHRESULT = ValueW;
      v24 = ValueW < 0;
      v25 = 313;
    }
    else
    {
      LastFailureAsHRESULT = CEcsMemPtr<unsigned short,0>::AllocBytes(v14, (unsigned int)a5);
      v21 = 300;
      if ( LastFailureAsHRESULT < 0 )
      {
LABEL_20:
        HIWORD(v37) = v21;
        goto LABEL_60;
      }
      LOWORD(v37) = 300;
      v23 = RegGetValueW(hkey, 0, c_pwszEcsEseParameterSettings, 0x20u, 0, *v14, (LPDWORD)&a5);
      if ( v23 == 2 )
      {
        CEcsMemPtr<CCloudFileSystemApplier::_FS_APPLIER_SWAP_PLAN_ENTRY,0>::Free(v14);
LABEL_34:
        v20 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_51;
      }
      if ( !v23 )
        goto LABEL_34;
      if ( v23 > 0 )
        v23 = (unsigned __int16)v23 | 0x80070000;
      LastFailureAsHRESULT = v23;
      v24 = v23 < 0;
      v25 = 308;
    }
    v20 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v24 )
  {
    HIWORD(v37) = v25;
    goto LABEL_61;
  }
  LOWORD(v37) = v25;
LABEL_51:
  if ( !*v12 )
  {
    MaximumProcessorCount = GetMaximumProcessorCount(0xFFFFu);
    v16 = MaximumProcessorCount;
    if ( !MaximumProcessorCount )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      v21 = 326;
      goto LABEL_20;
    }
    LastFailureAsHRESULT = 0;
    LOWORD(v37) = 326;
    v27 = v41;
    v19 = v41 * v16;
    *v12 = v41 * v16;
    v20 = (PVOID *)WPP_GLOBAL_Control;
    v18 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_LSLL(*((_QWORD *)WPP_GLOBAL_Control + 7), v16, (unsigned int)&WPP_GLOBAL_Control, v19, phkResult, v27, v16);
      v20 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( *a4 )
    goto LABEL_61;
  *a4 = 4 * *v12;
LABEL_60:
  v20 = (PVOID *)WPP_GLOBAL_Control;
LABEL_61:
  if ( hkey )
  {
    RegCloseKey(hkey);
    v20 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *v12 < 4 )
  {
    if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 68) & 0x40) != 0 && *((_BYTE *)v20 + 65) >= 3u )
      WPP_SF_SLLL((unsigned int)v20[7], v16, (_DWORD)v18, v19, *v12);
LABEL_68:
    *v12 = v15;
    v20 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_75;
  }
  v15 = 4096;
  if ( *v12 > 0x1000 )
  {
    if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 68) & 0x40) != 0 && *((_BYTE *)v20 + 65) >= 3u )
      WPP_SF_SLL((unsigned int)v20[7], 19, (_DWORD)v18, (unsigned int)&c_pwszEcsEseConcurrentOperations, 0, 0);
    goto LABEL_68;
  }
  v15 = *v12;
LABEL_75:
  v28 = *a4;
  if ( *a4 >= v15 )
  {
    if ( v28 <= 0x4000 )
      goto LABEL_88;
    if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 68) & 0x40) != 0 && *((_BYTE *)v20 + 65) >= 3u )
      WPP_SF_SLL((unsigned int)v20[7], 21, (_DWORD)v18, (unsigned int)&c_pwszEcsEseConcurrentTransactions, 0, 0);
    *a4 = 0x4000;
  }
  else
  {
    if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 68) & 0x40) != 0 && *((_BYTE *)v20 + 65) >= 3u )
      WPP_SF_SLLSL((TRACEHANDLE)v20[7], v28, pvData, pcbData, v15);
    *a4 = 4 * *v12;
  }
  v20 = (PVOID *)WPP_GLOBAL_Control;
LABEL_88:
  v29 = a7;
  if ( *a7 > 0x5265C00u )
  {
    if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 68) & 0x40) != 0 && *((_BYTE *)v20 + 65) >= 3u )
      WPP_SF_LSL(v20[7], v16, v18, (unsigned int)*a7);
    *v29 = 86400000;
  }
  v30 = LastFailureAsHRESULT;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&LastFailureAsHRESULT);
  return v30;
}

```

## disassembly

```asm
0x1800aae64  mov     [rsp-38h+arg_8], rbx
0x1800aae69  mov     [rsp-38h+arg_0], rcx
0x1800aae6e  push    rbp
0x1800aae6f  push    rsi
0x1800aae70  push    rdi
0x1800aae71  push    r12
0x1800aae73  push    r13
0x1800aae75  push    r14
0x1800aae77  push    r15
0x1800aae79  mov     rbp, rsp
0x1800aae7c  sub     rsp, 70h
0x1800aae80  mov     r14, r9
0x1800aae83  mov     r15, r8
0x1800aae86  mov     r13d, edx
0x1800aae89  mov     rax, cs:WPP_GLOBAL_Control
0x1800aae90  lea     rcx, WPP_GLOBAL_Control
0x1800aae97  cmp     rax, rcx
0x1800aae9a  jz      short loc_1800AAEC4
0x1800aae9c  test    byte ptr [rax+44h], 40h
0x1800aaea0  jz      short loc_1800AAEC4
0x1800aaea2  cmp     byte ptr [rax+41h], 6
0x1800aaea6  jb      short loc_1800AAEC4
0x1800aaea8  mov     rcx, [rax+38h]
0x1800aaeac  lea     r8, WPP_fe32ad1c437a354a2b591229e586699e_Traceguids
0x1800aaeb3  mov     edx, 0Eh
0x1800aaeb8  call    WPP_SF_
0x1800aaebd  mov     rax, cs:WPP_GLOBAL_Control
0x1800aaec4  xor     edx, edx
0x1800aaec6  test    byte ptr [rax+44h], 40h
0x1800aaeca  jz      short loc_1800AAED4
0x1800aaecc  cmp     byte ptr [rax+41h], 6
0x1800aaed0  mov     cl, 1
0x1800aaed2  jnb     short loc_1800AAED6
0x1800aaed4  mov     cl, dl
0x1800aaed6  mov     [rbp+var_28], edx
0x1800aaed9  lea     rax, aCfilesyncmetad_6; "CFileSyncMetadataStore::GetEseParameter"...
0x1800aaee0  mov     [rbp+var_18], rax
0x1800aaee4  mov     [rbp+var_24], 0D9h
0x1800aaeeb  mov     [rbp+var_20], cl
0x1800aaeee  mov     [rbp+var_10], rdx
0x1800aaef2  test    r14, r14
0x1800aaef5  jz      short loc_1800AAEFA
0x1800aaef7  mov     [r14], edx
0x1800aaefa  mov     rsi, [rbp+arg_20]
0x1800aaefe  test    rsi, rsi
0x1800aaf01  jz      short loc_1800AAF05
0x1800aaf03  mov     [rsi], edx
0x1800aaf05  mov     rdi, [rbp+arg_30]
0x1800aaf09  test    rdi, rdi
0x1800aaf0c  jz      short loc_1800AAF10
0x1800aaf0e  mov     [rdi], edx
0x1800aaf10  mov     r12, [rbp+arg_28]
0x1800aaf14  mov     rcx, r12
0x1800aaf17  call    ?Free@?$CEcsMemPtr@U_FS_APPLIER_SWAP_PLAN_ENTRY@CCloudFileSystemApplier@@$0A@@@QEAAXXZ; CEcsMemPtr<CCloudFileSystemApplier::_FS_APPLIER_SWAP_PLAN_ENTRY,0>::Free(void)
0x1800aaf1c  lea     rax, [rbp+hkey]
0x1800aaf20  mov     dword ptr [rdi], 0DBBA0h
0x1800aaf26  mov     [rbp+var_30], rax
0x1800aaf2a  mov     ebx, 4
0x1800aaf2f  lea     rax, [rbp+hkey]
0x1800aaf33  mov     dword ptr [rbp+arg_0], ebx
0x1800aaf36  mov     r9d, 20019h; samDesired
0x1800aaf3c  mov     [rsp+70h+phkResult], rax; phkResult
0x1800aaf41  xor     r8d, r8d; ulOptions
0x1800aaf44  mov     [rbp+hkey], 0
0x1800aaf4c  mov     rdx, r15; lpSubKey
0x1800aaf4f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800aaf56  call    cs:__imp_RegOpenKeyExW
0x1800aaf5c  mov     edi, eax
0x1800aaf5e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aaf65  lea     rax, WPP_GLOBAL_Control
0x1800aaf6c  cmp     rcx, rax
0x1800aaf6f  jz      short loc_1800AAF9D
0x1800aaf71  test    byte ptr [rcx+44h], 40h
0x1800aaf75  jz      short loc_1800AAF9D
0x1800aaf77  cmp     [rcx+41h], bl
0x1800aaf7a  jb      short loc_1800AAF9D
0x1800aaf7c  mov     rcx, [rcx+38h]
0x1800aaf80  lea     edx, [rbx+0Bh]
0x1800aaf83  mov     r9, r15
0x1800aaf86  mov     dword ptr [rsp+70h+phkResult], edi
0x1800aaf8a  lea     r8, WPP_fe32ad1c437a354a2b591229e586699e_Traceguids
0x1800aaf91  call    WPP_SF_Sd
0x1800aaf96  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aaf9d  xor     r15d, r15d
0x1800aafa0  test    edi, edi
0x1800aafa2  jnz     loc_1800AB186
0x1800aafa8  xor     r9d, r9d
0x1800aafab  lea     rdx, ?c_pwszEcsEseConcurrentTransactions@@3PAGA; "EseConcurrentTransactions"
0x1800aafb2  mov     r8, r14
0x1800aafb5  lea     rcx, [rbp+var_30]
0x1800aafb9  call    _lambda_6b12b68f26395bd983e950a4f04aacbb___operator__
0x1800aafbe  mov     [rbp+var_28], eax
0x1800aafc1  test    eax, eax
0x1800aafc3  mov     eax, 112h
0x1800aafc8  jns     short loc_1800AAFD3
0x1800aafca  mov     word ptr [rbp+var_24+2], ax
0x1800aafce  jmp     loc_1800AB22D
0x1800aafd3  neg     r13d
0x1800aafd6  mov     word ptr [rbp+var_24], ax
0x1800aafda  mov     r8, rsi
0x1800aafdd  lea     rdx, ?c_pwszEcsEseConcurrentOperations@@3PAGA; "EseConcurrentOperations"
0x1800aafe4  sbb     r9d, r9d
0x1800aafe7  lea     rcx, [rbp+var_30]
0x1800aafeb  not     r9d
0x1800aafee  and     r9d, ebx
0x1800aaff1  call    _lambda_6b12b68f26395bd983e950a4f04aacbb___operator__
0x1800aaff6  mov     [rbp+var_28], eax
0x1800aaff9  test    eax, eax
0x1800aaffb  mov     eax, 118h
0x1800ab000  js      short loc_1800AAFCA
0x1800ab002  mov     r9d, ebx
0x1800ab005  mov     word ptr [rbp+var_24], ax
0x1800ab009  lea     r8, [rbp+arg_0]
0x1800ab00d  lea     rdx, ?c_pwszEcsEseConcurrentOperationsMultiplier@@3PAGA; "EseConcurrentOperationsMultiplier"
0x1800ab014  lea     rcx, [rbp+var_30]
0x1800ab018  call    _lambda_6b12b68f26395bd983e950a4f04aacbb___operator__
0x1800ab01d  mov     [rbp+var_28], eax
0x1800ab020  test    eax, eax
0x1800ab022  mov     eax, 119h
0x1800ab027  js      short loc_1800AAFCA
0x1800ab029  mov     r8, [rbp+arg_30]
0x1800ab02d  lea     rdx, ?c_pwszEcsEseReplicaCacheExpirationMs@@3PAGA; "EseReplicaCacheExpirationMs"
0x1800ab034  mov     r9d, 0DBBA0h
0x1800ab03a  mov     word ptr [rbp+var_24], ax
0x1800ab03e  lea     rcx, [rbp+var_30]
0x1800ab042  call    _lambda_6b12b68f26395bd983e950a4f04aacbb___operator__
0x1800ab047  mov     [rbp+var_28], eax
0x1800ab04a  test    eax, eax
0x1800ab04c  mov     eax, 11Bh
0x1800ab051  js      loc_1800AAFCA
0x1800ab057  mov     word ptr [rbp+var_24], ax
0x1800ab05b  cmp     dword ptr [rbp+arg_0], r15d
0x1800ab05f  jnz     short loc_1800AB0A3
0x1800ab061  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab068  lea     rax, WPP_GLOBAL_Control
0x1800ab06f  cmp     rcx, rax
0x1800ab072  jz      short loc_1800AB0A0
0x1800ab074  test    byte ptr [rcx+44h], 40h
0x1800ab078  jz      short loc_1800AB0A0
0x1800ab07a  cmp     byte ptr [rcx+41h], 3
0x1800ab07e  jb      short loc_1800AB0A0
0x1800ab080  mov     rcx, [rcx+38h]
0x1800ab084  lea     r9, ?c_pwszEcsEseConcurrentOperationsMultiplier@@3PAGA; "EseConcurrentOperationsMultiplier"
0x1800ab08b  mov     edx, 10h
0x1800ab090  mov     dword ptr [rsp+70h+phkResult], ebx
0x1800ab094  lea     r8, WPP_fe32ad1c437a354a2b591229e586699e_Traceguids
0x1800ab09b  call    WPP_SF_Sd
0x1800ab0a0  mov     dword ptr [rbp+arg_0], ebx
0x1800ab0a3  mov     rcx, [rbp+hkey]; hkey
0x1800ab0a7  lea     rax, [rbp+arg_20]
0x1800ab0ab  mov     [rsp+70h+pcbData], rax; pcbData
0x1800ab0b0  lea     r8, ?c_pwszEcsEseParameterSettings@@3PAGA; "EseParameterSettings"
0x1800ab0b7  mov     edi, 20h ; ' '
0x1800ab0bc  mov     [rsp+70h+pvData], r15; pvData
0x1800ab0c1  mov     r9d, edi; dwFlags
0x1800ab0c4  mov     [rsp+70h+phkResult], r15; pdwType
0x1800ab0c9  xor     edx, edx; lpSubKey
0x1800ab0cb  mov     dword ptr [rbp+arg_20], r15d
0x1800ab0cf  call    cs:__imp_RegGetValueW
0x1800ab0d5  test    eax, eax
0x1800ab0d7  jnz     loc_1800AB169
0x1800ab0dd  mov     edx, dword ptr [rbp+arg_20]; unsigned __int64
0x1800ab0e0  mov     rcx, r12; void **
0x1800ab0e3  call    ?AllocBytes@?$CEcsMemPtr@G$0A@@@QEAAJ_K@Z; CEcsMemPtr<ushort,0>::AllocBytes(unsigned __int64)
0x1800ab0e8  mov     [rbp+var_28], eax
0x1800ab0eb  test    eax, eax
0x1800ab0ed  mov     eax, 12Ch
0x1800ab0f2  js      loc_1800AAFCA
0x1800ab0f8  mov     rcx, [rbp+hkey]; hkey
0x1800ab0fc  lea     r8, ?c_pwszEcsEseParameterSettings@@3PAGA; "EseParameterSettings"
0x1800ab103  mov     word ptr [rbp+var_24], ax
0x1800ab107  mov     r9d, edi; dwFlags
0x1800ab10a  lea     rax, [rbp+arg_20]
0x1800ab10e  xor     edx, edx; lpSubKey
0x1800ab110  mov     [rsp+70h+pcbData], rax; pcbData
0x1800ab115  mov     rax, [r12]
0x1800ab119  mov     [rsp+70h+pvData], rax; pvData
0x1800ab11e  mov     [rsp+70h+phkResult], r15; pdwType
0x1800ab123  call    cs:__imp_RegGetValueW
0x1800ab129  cmp     eax, 2
0x1800ab12c  jnz     short loc_1800AB13F
0x1800ab12e  mov     rcx, r12
0x1800ab131  call    ?Free@?$CEcsMemPtr@U_FS_APPLIER_SWAP_PLAN_ENTRY@CCloudFileSystemApplier@@$0A@@@QEAAXXZ; CEcsMemPtr<CCloudFileSystemApplier::_FS_APPLIER_SWAP_PLAN_ENTRY,0>::Free(void)
0x1800ab136  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab13d  jmp     short loc_1800AB1A8
0x1800ab13f  test    eax, eax
0x1800ab141  jz      short loc_1800AB136
0x1800ab143  jle     short loc_1800AB14D
0x1800ab145  movzx   eax, ax
0x1800ab148  or      eax, 80070000h
0x1800ab14d  mov     [rbp+var_28], eax
0x1800ab150  test    eax, eax
0x1800ab152  mov     eax, 134h
0x1800ab157  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab15e  jns     short loc_1800AB1A4
0x1800ab160  mov     word ptr [rbp+var_24+2], ax
0x1800ab164  jmp     loc_1800AB234
0x1800ab169  cmp     eax, 2
0x1800ab16c  jz      short loc_1800AB136
0x1800ab16e  test    eax, eax
0x1800ab170  jle     short loc_1800AB17A
0x1800ab172  movzx   eax, ax
0x1800ab175  or      eax, 80070000h
0x1800ab17a  mov     [rbp+var_28], eax
0x1800ab17d  test    eax, eax
0x1800ab17f  mov     eax, 139h
0x1800ab184  jmp     short loc_1800AB157
0x1800ab186  cmp     edi, 2
0x1800ab189  jz      short loc_1800AB1A8
0x1800ab18b  test    edi, edi
0x1800ab18d  jle     short loc_1800AB198
0x1800ab18f  movzx   edi, di
0x1800ab192  or      edi, 80070000h
0x1800ab198  mov     [rbp+var_28], edi
0x1800ab19b  mov     eax, 13Eh
0x1800ab1a0  test    edi, edi
0x1800ab1a2  jmp     short loc_1800AB15E
0x1800ab1a4  mov     word ptr [rbp+var_24], ax
0x1800ab1a8  cmp     [rsi], r15d
0x1800ab1ab  jnz     short loc_1800AB220
0x1800ab1ad  mov     ecx, 0FFFFh; GroupNumber
0x1800ab1b2  call    cs:__imp_GetMaximumProcessorCount
0x1800ab1b8  mov     edx, eax
0x1800ab1ba  test    eax, eax
0x1800ab1bc  jnz     short loc_1800AB1D0
0x1800ab1be  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800ab1c3  mov     [rbp+var_28], eax
0x1800ab1c6  mov     eax, 146h
0x1800ab1cb  jmp     loc_1800AAFCA
0x1800ab1d0  mov     eax, 146h
0x1800ab1d5  mov     [rbp+var_28], r15d
0x1800ab1d9  mov     word ptr [rbp+var_24], ax
0x1800ab1dd  mov     r9d, edx
0x1800ab1e0  mov     eax, dword ptr [rbp+arg_0]
0x1800ab1e3  imul    r9d, eax
0x1800ab1e7  mov     [rsi], r9d
0x1800ab1ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab1f1  lea     r8, WPP_GLOBAL_Control
0x1800ab1f8  cmp     rcx, r8
0x1800ab1fb  jz      short loc_1800AB220
0x1800ab1fd  test    byte ptr [rcx+44h], 40h
0x1800ab201  jz      short loc_1800AB220
0x1800ab203  cmp     [rcx+41h], bl
0x1800ab206  jb      short loc_1800AB220
0x1800ab208  mov     rcx, [rcx+38h]
0x1800ab20c  mov     dword ptr [rsp+70h+pcbData], edx; int
0x1800ab210  mov     dword ptr [rsp+70h+pvData], eax; int
0x1800ab214  call    WPP_SF_LSLL
0x1800ab219  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab220  cmp     [r14], r15d
0x1800ab223  jnz     short loc_1800AB234
0x1800ab225  mov     eax, [rsi]
0x1800ab227  shl     eax, 2
0x1800ab22a  mov     [r14], eax
0x1800ab22d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab234  mov     rax, [rbp+hkey]
0x1800ab238  test    rax, rax
0x1800ab23b  jz      short loc_1800AB24D
0x1800ab23d  mov     rcx, rax; hKey
0x1800ab240  call    cs:__imp_RegCloseKey
0x1800ab246  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab24d  mov     eax, [rsi]
0x1800ab24f  cmp     eax, ebx
0x1800ab251  jnb     short loc_1800AB283
0x1800ab253  lea     r15, WPP_GLOBAL_Control
0x1800ab25a  cmp     rcx, r15
0x1800ab25d  jz      short loc_1800AB278
0x1800ab25f  test    byte ptr [rcx+44h], 40h
0x1800ab263  jz      short loc_1800AB278
0x1800ab265  cmp     byte ptr [rcx+41h], 3
0x1800ab269  jb      short loc_1800AB278
0x1800ab26b  mov     rcx, [rcx+38h]
0x1800ab26f  mov     dword ptr [rsp+70h+phkResult], eax
0x1800ab273  call    WPP_SF_SLLL
0x1800ab278  mov     [rsi], ebx
0x1800ab27a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab281  jmp     short loc_1800AB2CC
0x1800ab283  mov     ebx, 1000h
0x1800ab288  cmp     eax, ebx
0x1800ab28a  jbe     short loc_1800AB2C3
0x1800ab28c  lea     r15, WPP_GLOBAL_Control
0x1800ab293  cmp     rcx, r15
0x1800ab296  jz      short loc_1800AB278
0x1800ab298  test    byte ptr [rcx+44h], 40h
0x1800ab29c  jz      short loc_1800AB278
0x1800ab29e  cmp     byte ptr [rcx+41h], 3
0x1800ab2a2  jb      short loc_1800AB278
0x1800ab2a4  mov     rcx, [rcx+38h]
0x1800ab2a8  lea     r9, ?c_pwszEcsEseConcurrentOperations@@3PAGA; "EseConcurrentOperations"
0x1800ab2af  mov     edx, 13h
0x1800ab2b4  mov     dword ptr [rsp+70h+pvData], ebx
0x1800ab2b8  mov     dword ptr [rsp+70h+phkResult], ebx
0x1800ab2bc  call    WPP_SF_SLL
0x1800ab2c1  jmp     short loc_1800AB278
0x1800ab2c3  mov     ebx, eax
0x1800ab2c5  lea     r15, WPP_GLOBAL_Control
0x1800ab2cc  mov     eax, [r14]
0x1800ab2cf  cmp     eax, ebx
0x1800ab2d1  jnb     short loc_1800AB2FF
0x1800ab2d3  cmp     rcx, r15
  ... truncated ...
```
