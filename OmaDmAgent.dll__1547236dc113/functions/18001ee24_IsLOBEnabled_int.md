# IsLOBEnabled(int *)

- ea: `0x18001ee24`
- end: `0x18001f26e`
- name: `?IsLOBEnabled@@YAJPEAH@Z`
- size: `1098`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010700`

## callees

- `0x18000a2c0`
- `0x18001ee24`
- `0x18001f3e6`
- `0x18001f420`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18001f094`
- `KERNEL32!LocalFree` at `0x18001f1cf`
- `KERNEL32!LocalFree` at `0x18001f1e4`
- `KERNEL32!LocalFree` at `0x18001f1f9`
- `KERNEL32!LocalFree` at `0x18001f094`
- `KERNEL32!LocalFree` at `0x18001f1cf`
- `KERNEL32!LocalFree` at `0x18001f1e4`
- `KERNEL32!LocalFree` at `0x18001f1f9`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18001eea7`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18001eea7`
- `RPCRT4!UuidFromStringW` at `0x18001ef64`
- `RPCRT4!UuidFromStringW` at `0x18001ef64`
- `sppc!SLGetSLIDList` at `0x18001f026`
- `sppc!SLGetSLIDList` at `0x18001f026`
- `sppc!SLClose` at `0x18001f1ba`
- `sppc!SLClose` at `0x18001f1ba`
- `sppc!SLOpen` at `0x18001ef1c`
- `sppc!SLOpen` at `0x18001ef1c`
- `sppc!SLGetLicensingStatusInformation` at `0x18001efc7`
- `sppc!SLGetLicensingStatusInformation` at `0x18001efc7`
- `sppc!SLGetProductSkuInformation` at `0x18001f0c9`
- `sppc!SLGetProductSkuInformation` at `0x18001f0c9`

## pseudocode

```c
__int64 __fastcall IsLOBEnabled(int *a1)
{
  unsigned int DWORD; // ebx
  LPCWSTR v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // r9
  HRESULT v6; // eax
  RPC_STATUS v7; // ebx
  UINT v8; // esi
  int v9; // eax
  HRESULT v10; // eax
  UINT i; // ecx
  __int64 v12; // rax
  __int64 v13; // r9
  unsigned int v14; // eax
  unsigned int v16; // [rsp+30h] [rbp-39h] BYREF
  UINT pnReturnIds; // [rsp+34h] [rbp-35h] BYREF
  SLDATATYPE peDataType; // [rsp+38h] [rbp-31h] BYREF
  UINT pcbValue; // [rsp+3Ch] [rbp-2Dh] BYREF
  UINT pnStatusCount; // [rsp+40h] [rbp-29h] BYREF
  HSLC phSLC; // [rsp+48h] [rbp-21h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-19h] BYREF
  HLOCAL ppLicensingStatus; // [rsp+58h] [rbp-11h] BYREF
  SLID *ppReturnIds; // [rsp+60h] [rbp-9h] BYREF
  SLID pProductSkuId; // [rsp+68h] [rbp-1h] BYREF
  UUID Uuid; // [rsp+78h] [rbp+Fh] BYREF

  v16 = 0;
  phSLC = 0;
  pnReturnIds = 0;
  ppReturnIds = 0;
  ppLicensingStatus = 0;
  peDataType = SL_DATA_NONE;
  pcbValue = 0;
  hMem = 0;
  pnStatusCount = 0;
  Uuid = 0;
  pProductSkuId = 0;
  if ( !a1 )
    return (unsigned int)-2147024809;
  DWORD = OmaDmRegistryGetDWORD(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Policies\\Microsoft\\Windows\\Appx\\",
            L"AllowAllTrustedApps",
            &v16);
  if ( (int)(DWORD + 0x80000000) >= 0 && DWORD != -2147024894 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_56;
    v4 = 10;
LABEL_8:
    v5 = DWORD;
LABEL_9:
    WPP_SF_d(*((_QWORD *)v3 + 2), v4, WPP_69165a80032530b6842f0825c7f19a81_Traceguids, v5);
    goto LABEL_56;
  }
  if ( !v16 )
  {
    *a1 = 0;
    DWORD = 0;
    goto LABEL_56;
  }
  v6 = SLOpen(&phSLC);
  DWORD = v6;
  if ( v6 < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_56;
    v4 = 11;
LABEL_16:
    v5 = (unsigned int)v6;
    goto LABEL_9;
  }
  v7 = UuidFromStringW((RPC_WSTR)L"55c92734-d682-4d71-983e-d6ec3f16059f", &Uuid);
  if ( v7 )
  {
    DWORD = v7 | 0x80010000;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_56;
    v4 = 12;
    goto LABEL_8;
  }
  v6 = SLGetLicensingStatusInformation(phSLC, &Uuid, 0, 0, &pnStatusCount, (SL_LICENSING_STATUS **)&ppLicensingStatus);
  DWORD = v6;
  if ( v6 < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_56;
    v4 = 13;
    goto LABEL_16;
  }
  v6 = SLGetSLIDList(phSLC, SL_ID_APPLICATION, &Uuid, SL_ID_PRODUCT_SKU, &pnReturnIds, &ppReturnIds);
  DWORD = v6;
  if ( v6 < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_56;
    v4 = 14;
    goto LABEL_16;
  }
  v8 = 0;
  while ( 1 )
  {
    v9 = 0;
    if ( v8 >= pnReturnIds )
    {
LABEL_55:
      *a1 = v9;
      goto LABEL_56;
    }
    pProductSkuId = ppReturnIds[v8];
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
    v10 = SLGetProductSkuInformation(phSLC, &pProductSkuId, L"AppXLOB", &peDataType, &pcbValue, (PBYTE *)&hMem);
    DWORD = v10;
    if ( v10 == -1073418222 )
      goto LABEL_48;
    if ( v10 < 0 )
      break;
    if ( peDataType != SL_DATA_SZ )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      {
        v4 = 16;
        v5 = 3221549086LL;
        goto LABEL_9;
      }
      goto LABEL_56;
    }
    if ( pcbValue > 1 && !wcscmp_0((const wchar_t *)hMem, L"true") )
    {
      for ( i = 0; i < pnStatusCount; ++i )
      {
        v12 = *(_QWORD *)&pProductSkuId.Data1 - *((_QWORD *)ppLicensingStatus + 5 * i);
        if ( *(_QWORD *)&pProductSkuId.Data1 == *((_QWORD *)ppLicensingStatus + 5 * i) )
          v12 = *(_QWORD *)pProductSkuId.Data4 - *((_QWORD *)ppLicensingStatus + 5 * i + 1);
        if ( !v12 )
        {
          v13 = *((unsigned int *)ppLicensingStatus + 10 * i + 7);
          if ( (int)v13 < 0 )
          {
            if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_69165a80032530b6842f0825c7f19a81_Traceguids, v13);
            break;
          }
          if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_69165a80032530b6842f0825c7f19a81_Traceguids, v13);
          v9 = 1;
          goto LABEL_55;
        }
      }
    }
LABEL_48:
    ++v8;
    v14 = 0;
    if ( DWORD != -1073418222 )
      v14 = DWORD;
    DWORD = v14;
  }
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    v4 = 15;
    goto LABEL_8;
  }
LABEL_56:
  if ( phSLC )
    SLClose(phSLC);
  if ( ppLicensingStatus )
    LocalFree(ppLicensingStatus);
  if ( ppReturnIds )
    LocalFree(ppReturnIds);
  if ( hMem )
    LocalFree(hMem);
  return DWORD;
}

```

## disassembly

```asm
0x18001ee24  push    rbp
0x18001ee26  push    rbx
0x18001ee27  push    rsi
0x18001ee28  push    rdi
0x18001ee29  push    r14
0x18001ee2b  push    r15
0x18001ee2d  lea     rbp, [rsp-2Fh]
0x18001ee32  sub     rsp, 98h
0x18001ee39  mov     rax, cs:__security_cookie
0x18001ee40  xor     rax, rsp
0x18001ee43  mov     [rbp+57h+var_38], rax
0x18001ee47  xor     r15d, r15d
0x18001ee4a  xorps   xmm0, xmm0
0x18001ee4d  mov     [rbp+57h+var_90], r15d
0x18001ee51  xorps   xmm1, xmm1
0x18001ee54  mov     [rbp+57h+phSLC], r15
0x18001ee58  mov     r14, rcx
0x18001ee5b  mov     [rbp+57h+pnReturnIds], r15d
0x18001ee5f  mov     [rbp+57h+ppReturnIds], r15
0x18001ee63  mov     [rbp+57h+var_68], r15
0x18001ee67  mov     [rbp+57h+peDataType], r15d
0x18001ee6b  mov     [rbp+57h+pcbValue], r15d
0x18001ee6f  mov     [rbp+57h+hMem], r15
0x18001ee73  mov     [rbp+57h+var_80], r15d
0x18001ee77  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x18001ee7b  movups  xmmword ptr [rbp+57h+pProductSkuId.Data1], xmm1
0x18001ee7f  test    rcx, rcx
0x18001ee82  jnz     short loc_18001EE8E
0x18001ee84  mov     ebx, 80070057h
0x18001ee89  jmp     loc_18001F205
0x18001ee8e  lea     r9, [rbp+57h+var_90]
0x18001ee92  mov     rcx, 0FFFFFFFF80000002h
0x18001ee99  lea     r8, aAllowalltruste; "AllowAllTrustedApps"
0x18001eea0  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18001eea7  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001eeae  nop     dword ptr [rax+rax+00h]
0x18001eeb3  mov     ebx, eax
0x18001eeb5  mov     eax, 80000000h
0x18001eeba  lea     ecx, [rbx+rax]
0x18001eebd  test    eax, ecx
0x18001eebf  jnz     short loc_18001EF07
0x18001eec1  cmp     ebx, 80070002h
0x18001eec7  jz      short loc_18001EF07
0x18001eec9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eed0  lea     rdi, WPP_GLOBAL_Control
0x18001eed7  cmp     rcx, rdi
0x18001eeda  jz      loc_18001F1B1
0x18001eee0  test    byte ptr [rcx+1Ch], 4
0x18001eee4  jz      loc_18001F1B1
0x18001eeea  mov     edx, 0Ah
0x18001eeef  mov     r9d, ebx
0x18001eef2  mov     rcx, [rcx+10h]
0x18001eef6  lea     r8, WPP_69165a80032530b6842f0825c7f19a81_Traceguids
0x18001eefd  call    WPP_SF_d
0x18001ef02  jmp     loc_18001F1B1
0x18001ef07  cmp     [rbp+57h+var_90], r15d
0x18001ef0b  jnz     short loc_18001EF18
0x18001ef0d  mov     [r14], r15d
0x18001ef10  mov     ebx, r15d
0x18001ef13  jmp     loc_18001F1B1
0x18001ef18  lea     rcx, [rbp+57h+phSLC]; phSLC
0x18001ef1c  call    cs:__imp_SLOpen
0x18001ef23  nop     dword ptr [rax+rax+00h]
0x18001ef28  mov     ebx, eax
0x18001ef2a  test    eax, eax
0x18001ef2c  jns     short loc_18001EF59
0x18001ef2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef35  lea     rdi, WPP_GLOBAL_Control
0x18001ef3c  cmp     rcx, rdi
0x18001ef3f  jz      loc_18001F1B1
0x18001ef45  test    byte ptr [rcx+1Ch], 4
0x18001ef49  jz      loc_18001F1B1
0x18001ef4f  mov     edx, 0Bh
0x18001ef54  mov     r9d, eax
0x18001ef57  jmp     short loc_18001EEF2
0x18001ef59  lea     rdx, [rbp+57h+Uuid]; Uuid
0x18001ef5d  lea     rcx, StringUuid; "55c92734-d682-4d71-983e-d6ec3f16059f"
0x18001ef64  call    cs:__imp_UuidFromStringW
0x18001ef6b  nop     dword ptr [rax+rax+00h]
0x18001ef70  mov     ebx, eax
0x18001ef72  test    eax, eax
0x18001ef74  jz      short loc_18001EFA7
0x18001ef76  or      ebx, 80010000h
0x18001ef7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef83  lea     rdi, WPP_GLOBAL_Control
0x18001ef8a  cmp     rcx, rdi
0x18001ef8d  jz      loc_18001F1B1
0x18001ef93  test    byte ptr [rcx+1Ch], 4
0x18001ef97  jz      loc_18001F1B1
0x18001ef9d  mov     edx, 0Ch
0x18001efa2  jmp     loc_18001EEEF
0x18001efa7  mov     rcx, [rbp+57h+phSLC]; hSLC
0x18001efab  lea     rax, [rbp+57h+var_68]
0x18001efaf  mov     [rsp+0C0h+ppLicensingStatus], rax; ppLicensingStatus
0x18001efb4  lea     rdx, [rbp+57h+Uuid]; pAppID
0x18001efb8  lea     rax, [rbp+57h+var_80]
0x18001efbc  xor     r9d, r9d; pwszRightName
0x18001efbf  xor     r8d, r8d; pProductSkuId
0x18001efc2  mov     [rsp+0C0h+pnStatusCount], rax; pnStatusCount
0x18001efc7  call    cs:__imp_SLGetLicensingStatusInformation
0x18001efce  nop     dword ptr [rax+rax+00h]
0x18001efd3  mov     ebx, eax
0x18001efd5  test    eax, eax
0x18001efd7  jns     short loc_18001F004
0x18001efd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001efe0  lea     rdi, WPP_GLOBAL_Control
0x18001efe7  cmp     rcx, rdi
0x18001efea  jz      loc_18001F1B1
0x18001eff0  test    byte ptr [rcx+1Ch], 4
0x18001eff4  jz      loc_18001F1B1
0x18001effa  mov     edx, 0Dh
0x18001efff  jmp     loc_18001EF54
0x18001f004  mov     rcx, [rbp+57h+phSLC]; hSLC
0x18001f008  lea     rax, [rbp+57h+ppReturnIds]
0x18001f00c  mov     [rsp+0C0h+ppLicensingStatus], rax; ppReturnIds
0x18001f011  lea     r8, [rbp+57h+Uuid]; pQueryId
0x18001f015  lea     rax, [rbp+57h+pnReturnIds]
0x18001f019  mov     r9d, 1; eReturnIdType
0x18001f01f  xor     edx, edx; eQueryIdType
0x18001f021  mov     [rsp+0C0h+pnStatusCount], rax; pnReturnIds
0x18001f026  call    cs:__imp_SLGetSLIDList
0x18001f02d  nop     dword ptr [rax+rax+00h]
0x18001f032  mov     ebx, eax
0x18001f034  test    eax, eax
0x18001f036  jns     short loc_18001F063
0x18001f038  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f03f  lea     rdi, WPP_GLOBAL_Control
0x18001f046  cmp     rcx, rdi
0x18001f049  jz      loc_18001F1B1
0x18001f04f  test    byte ptr [rcx+1Ch], 4
0x18001f053  jz      loc_18001F1B1
0x18001f059  mov     edx, 0Eh
0x18001f05e  jmp     loc_18001EF54
0x18001f063  mov     esi, r15d
0x18001f066  lea     rdi, WPP_GLOBAL_Control
0x18001f06d  mov     eax, r15d
0x18001f070  cmp     esi, [rbp+57h+pnReturnIds]
0x18001f073  jnb     loc_18001F1AE
0x18001f079  mov     rax, [rbp+57h+ppReturnIds]
0x18001f07d  mov     ecx, esi
0x18001f07f  add     rcx, rcx
0x18001f082  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18001f086  mov     rcx, [rbp+57h+hMem]; hMem
0x18001f08a  movdqu  xmmword ptr [rbp+57h+pProductSkuId.Data1], xmm0
0x18001f08f  test    rcx, rcx
0x18001f092  jz      short loc_18001F0A4
0x18001f094  call    cs:__imp_LocalFree
0x18001f09b  nop     dword ptr [rax+rax+00h]
0x18001f0a0  mov     [rbp+57h+hMem], r15
0x18001f0a4  mov     rcx, [rbp+57h+phSLC]; hSLC
0x18001f0a8  lea     rax, [rbp+57h+hMem]
0x18001f0ac  mov     [rsp+0C0h+ppLicensingStatus], rax; ppbValue
0x18001f0b1  lea     r9, [rbp+57h+peDataType]; peDataType
0x18001f0b5  lea     rax, [rbp+57h+pcbValue]
0x18001f0b9  lea     r8, pwszValueName; "AppXLOB"
0x18001f0c0  mov     [rsp+0C0h+pnStatusCount], rax; pcbValue
0x18001f0c5  lea     rdx, [rbp+57h+pProductSkuId]; pProductSkuId
0x18001f0c9  call    cs:__imp_SLGetProductSkuInformation
0x18001f0d0  nop     dword ptr [rax+rax+00h]
0x18001f0d5  mov     ebx, eax
0x18001f0d7  cmp     eax, 0C004F012h
0x18001f0dc  jz      loc_18001F16D
0x18001f0e2  test    eax, eax
0x18001f0e4  js      loc_18001F24A
0x18001f0ea  cmp     [rbp+57h+peDataType], 1
0x18001f0ee  jnz     loc_18001F224
0x18001f0f4  cmp     [rbp+57h+pcbValue], 1
0x18001f0f8  jbe     short loc_18001F16D
0x18001f0fa  mov     rcx, [rbp+57h+hMem]; String1
0x18001f0fe  lea     rdx, aTrue; "true"
0x18001f105  call    wcscmp_0
0x18001f10a  test    eax, eax
0x18001f10c  jnz     short loc_18001F16D
0x18001f10e  mov     ecx, r15d
0x18001f111  cmp     ecx, [rbp+57h+var_80]
0x18001f114  jnb     short loc_18001F16D
0x18001f116  mov     rdx, [rbp+57h+var_68]
0x18001f11a  mov     eax, ecx
0x18001f11c  lea     r9, [rax+rax*4]
0x18001f120  mov     rax, qword ptr [rbp+57h+pProductSkuId.Data1]
0x18001f124  sub     rax, [rdx+r9*8]
0x18001f128  jnz     short loc_18001F133
0x18001f12a  mov     rax, qword ptr [rbp+57h+pProductSkuId.Data4]
0x18001f12e  sub     rax, [rdx+r9*8+8]
0x18001f133  test    rax, rax
0x18001f136  jz      short loc_18001F13C
0x18001f138  inc     ecx
0x18001f13a  jmp     short loc_18001F111
0x18001f13c  mov     r9d, [rdx+r9*8+1Ch]
0x18001f141  test    r9d, r9d
0x18001f144  jns     short loc_18001F182
0x18001f146  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f14d  cmp     rcx, rdi
0x18001f150  jz      short loc_18001F16D
0x18001f152  test    byte ptr [rcx+1Ch], 4
0x18001f156  jz      short loc_18001F16D
0x18001f158  mov     rcx, [rcx+10h]
0x18001f15c  lea     r8, WPP_69165a80032530b6842f0825c7f19a81_Traceguids
0x18001f163  mov     edx, 11h
0x18001f168  call    WPP_SF_d
0x18001f16d  inc     esi
0x18001f16f  mov     eax, r15d
0x18001f172  cmp     ebx, 0C004F012h
0x18001f178  cmovnz  eax, ebx
0x18001f17b  mov     ebx, eax
0x18001f17d  jmp     loc_18001F06D
0x18001f182  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f189  cmp     rcx, rdi
0x18001f18c  jz      short loc_18001F1A9
0x18001f18e  test    byte ptr [rcx+1Ch], 4
0x18001f192  jz      short loc_18001F1A9
0x18001f194  mov     rcx, [rcx+10h]
0x18001f198  lea     r8, WPP_69165a80032530b6842f0825c7f19a81_Traceguids
0x18001f19f  mov     edx, 12h
0x18001f1a4  call    WPP_SF_d
0x18001f1a9  mov     eax, 1
0x18001f1ae  mov     [r14], eax
0x18001f1b1  mov     rcx, [rbp+57h+phSLC]; hSLC
0x18001f1b5  test    rcx, rcx
0x18001f1b8  jz      short loc_18001F1C6
0x18001f1ba  call    cs:__imp_SLClose
0x18001f1c1  nop     dword ptr [rax+rax+00h]
0x18001f1c6  mov     rcx, [rbp+57h+var_68]; hMem
0x18001f1ca  test    rcx, rcx
0x18001f1cd  jz      short loc_18001F1DB
0x18001f1cf  call    cs:__imp_LocalFree
0x18001f1d6  nop     dword ptr [rax+rax+00h]
0x18001f1db  mov     rcx, [rbp+57h+ppReturnIds]; hMem
0x18001f1df  test    rcx, rcx
0x18001f1e2  jz      short loc_18001F1F0
0x18001f1e4  call    cs:__imp_LocalFree
0x18001f1eb  nop     dword ptr [rax+rax+00h]
0x18001f1f0  mov     rcx, [rbp+57h+hMem]; hMem
0x18001f1f4  test    rcx, rcx
0x18001f1f7  jz      short loc_18001F205
0x18001f1f9  call    cs:__imp_LocalFree
0x18001f200  nop     dword ptr [rax+rax+00h]
0x18001f205  mov     eax, ebx
0x18001f207  mov     rcx, [rbp+57h+var_38]
0x18001f20b  xor     rcx, rsp; StackCookie
0x18001f20e  call    __security_check_cookie
0x18001f213  add     rsp, 98h
0x18001f21a  pop     r15
0x18001f21c  pop     r14
0x18001f21e  pop     rdi
0x18001f21f  pop     rsi
0x18001f220  pop     rbx
0x18001f221  pop     rbp
0x18001f222  retn
0x18001f224  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f22b  cmp     rcx, rdi
0x18001f22e  jz      short loc_18001F1B1
0x18001f230  test    byte ptr [rcx+1Ch], 4
0x18001f234  jz      loc_18001F1B1
0x18001f23a  mov     edx, 10h
0x18001f23f  mov     r9d, 0C004F01Eh
0x18001f245  jmp     loc_18001EEF2
0x18001f24a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f251  cmp     rcx, rdi
0x18001f254  jz      loc_18001F1B1
0x18001f25a  test    byte ptr [rcx+1Ch], 4
0x18001f25e  jz      loc_18001F1B1
0x18001f264  mov     edx, 0Fh
0x18001f269  jmp     loc_18001EEEF
```
