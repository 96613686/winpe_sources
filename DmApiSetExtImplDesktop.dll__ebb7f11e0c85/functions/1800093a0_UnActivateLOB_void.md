# UnActivateLOB(void)

- ea: `0x1800093a0`
- end: `0x180009743`
- name: `?UnActivateLOB@@YAJXZ`
- size: `931`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180007b40`

## callees

- `0x1800093a0`
- `0x18000974c`
- `0x180009784`
- `0x180009f0a`
- `0x180009f30`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x180009455`
- `RPCRT4!UuidFromStringW` at `0x180009455`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009527`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800095b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800096f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009707`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000971c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009527`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800095b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800096f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009707`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000971c`
- `sppc!SLGetSLIDList` at `0x1800094bd`
- `sppc!SLGetSLIDList` at `0x1800094bd`
- `sppc!SLGetProductSkuInformation` at `0x180009560`
- `sppc!SLGetProductSkuInformation` at `0x180009560`
- `sppc!SLUninstallProofOfPurchase` at `0x18000964a`
- `sppc!SLUninstallProofOfPurchase` at `0x18000964a`
- `sppc!SLGetInstalledProductKeyIds` at `0x1800095d8`
- `sppc!SLGetInstalledProductKeyIds` at `0x1800095d8`
- `sppc!SLClose` at `0x1800096dd`
- `sppc!SLClose` at `0x1800096dd`
- `sppc!SLOpen` at `0x18000940d`
- `sppc!SLOpen` at `0x18000940d`

## pseudocode

```c
__int64 UnActivateLOB(void)
{
  HRESULT v0; // eax
  __int64 v1; // r8
  unsigned int v2; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  RPC_STATUS v5; // ebx
  __int64 v6; // r9
  UINT i; // esi
  HRESULT v8; // eax
  __int64 v9; // r8
  HRESULT v10; // eax
  __int64 v11; // r8
  UINT pnProductKeyIds; // [rsp+30h] [rbp-29h] BYREF
  HSLC phSLC; // [rsp+38h] [rbp-21h] BYREF
  UINT pnReturnIds; // [rsp+40h] [rbp-19h] BYREF
  SLDATATYPE peDataType; // [rsp+44h] [rbp-15h] BYREF
  UINT pcbValue; // [rsp+48h] [rbp-11h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-9h] BYREF
  HLOCAL v19; // [rsp+58h] [rbp-1h] BYREF
  HLOCAL ppReturnIds; // [rsp+60h] [rbp+7h] BYREF
  SLID pProductSkuId; // [rsp+68h] [rbp+Fh] BYREF
  UUID Uuid; // [rsp+78h] [rbp+1Fh] BYREF

  phSLC = 0;
  pnReturnIds = 0;
  ppReturnIds = 0;
  Uuid = 0;
  peDataType = SL_DATA_NONE;
  pProductSkuId = 0;
  pcbValue = 0;
  hMem = 0;
  pnProductKeyIds = 0;
  v19 = 0;
  v0 = SLOpen(&phSLC);
  v2 = v0;
  if ( v0 >= 0 )
  {
    v5 = UuidFromStringW((RPC_WSTR)L"55c92734-d682-4d71-983e-d6ec3f16059f", &Uuid);
    if ( v5 )
    {
      v2 = v5 | 0x80010000;
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v4 = 20;
        v6 = v2;
LABEL_46:
        WPP_SF_D(v3[2], v4, v1, v6);
      }
    }
    else
    {
      v0 = SLGetSLIDList(phSLC, SL_ID_APPLICATION, &Uuid, SL_ID_PRODUCT_SKU, &pnReturnIds, (SLID **)&ppReturnIds);
      v2 = v0;
      if ( v0 >= 0 )
      {
        for ( i = 0; i < pnReturnIds; ++i )
        {
          pProductSkuId = (SLID)*((_OWORD *)ppReturnIds + i);
          if ( hMem )
          {
            LocalFree(hMem);
            hMem = 0;
          }
          v0 = SLGetProductSkuInformation(phSLC, &pProductSkuId, L"AppXLOB", &peDataType, &pcbValue, (PBYTE *)&hMem);
          if ( v0 != -1073418222 )
          {
            if ( v0 < 0 )
            {
              v2 = v0;
              v3 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                v4 = 22;
                goto LABEL_45;
              }
              break;
            }
            if ( peDataType != SL_DATA_SZ )
            {
              v2 = -1073418210;
              v3 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                v4 = 23;
                v6 = 3221549086LL;
                goto LABEL_46;
              }
              break;
            }
            if ( pcbValue > 1 && !wcscmp_0((const wchar_t *)hMem, L"true") )
            {
              if ( v19 )
              {
                LocalFree(v19);
                v19 = 0;
              }
              v8 = SLGetInstalledProductKeyIds(phSLC, &pProductSkuId, &pnProductKeyIds, (SLID **)&v19);
              if ( v8 >= 0 )
              {
                for ( i = 0; i < pnProductKeyIds; ++i )
                {
                  v10 = SLUninstallProofOfPurchase(phSLC, (const SLID *)v19 + i);
                  if ( v10 < 0
                    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                  {
                    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v11, (unsigned int)v10);
                  }
                }
              }
              else if ( v8 == -1073418222 )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2));
                }
              }
              else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v9, (unsigned int)v8);
              }
            }
          }
        }
      }
      else
      {
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v4 = 21;
          goto LABEL_45;
        }
      }
    }
  }
  else
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v4 = 19;
LABEL_45:
      v6 = (unsigned int)v0;
      goto LABEL_46;
    }
  }
  if ( phSLC )
    SLClose(phSLC);
  if ( ppReturnIds )
    LocalFree(ppReturnIds);
  if ( hMem )
    LocalFree(hMem);
  if ( v19 )
    LocalFree(v19);
  return v2;
}

```

## disassembly

```asm
0x1800093a0  push    rbp
0x1800093a2  push    rbx
0x1800093a3  push    rsi
0x1800093a4  push    rdi
0x1800093a5  lea     rbp, [rsp-3Fh]
0x1800093aa  sub     rsp, 98h
0x1800093b1  mov     rax, cs:__security_cookie
0x1800093b8  xor     rax, rsp
0x1800093bb  mov     [rbp+57h+var_28], rax
0x1800093bf  xorps   xmm0, xmm0
0x1800093c2  mov     [rbp+57h+phSLC], 0
0x1800093ca  xorps   xmm1, xmm1
0x1800093cd  mov     [rbp+57h+var_70], 0
0x1800093d4  lea     rcx, [rbp+57h+phSLC]; phSLC
0x1800093d8  mov     [rbp+57h+var_50], 0
0x1800093e0  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x1800093e4  mov     [rbp+57h+peDataType], 0
0x1800093eb  movups  xmmword ptr [rbp+57h+pProductSkuId.Data1], xmm1
0x1800093ef  mov     [rbp+57h+pcbValue], 0
0x1800093f6  mov     [rbp+57h+hMem], 0
0x1800093fe  mov     [rbp+57h+pnProductKeyIds], 0
0x180009405  mov     [rbp+57h+var_58], 0
0x18000940d  call    cs:__imp_SLOpen
0x180009414  nop     dword ptr [rax+rax+00h]
0x180009419  mov     ebx, eax
0x18000941b  test    eax, eax
0x18000941d  jns     short loc_18000944A
0x18000941f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009426  lea     rdi, WPP_GLOBAL_Control
0x18000942d  cmp     rcx, rdi
0x180009430  jz      loc_1800096D4
0x180009436  test    byte ptr [rcx+1Ch], 4
0x18000943a  jz      loc_1800096D4
0x180009440  mov     edx, 13h
0x180009445  jmp     loc_1800096C8
0x18000944a  lea     rdx, [rbp+57h+Uuid]; Uuid
0x18000944e  lea     rcx, StringUuid; "55c92734-d682-4d71-983e-d6ec3f16059f"
0x180009455  call    cs:__imp_UuidFromStringW
0x18000945c  nop     dword ptr [rax+rax+00h]
0x180009461  mov     ebx, eax
0x180009463  test    eax, eax
0x180009465  jz      short loc_18000949B
0x180009467  or      ebx, 80010000h
0x18000946d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009474  lea     rdi, WPP_GLOBAL_Control
0x18000947b  cmp     rcx, rdi
0x18000947e  jz      loc_1800096D4
0x180009484  test    byte ptr [rcx+1Ch], 4
0x180009488  jz      loc_1800096D4
0x18000948e  mov     edx, 14h
0x180009493  mov     r9d, ebx
0x180009496  jmp     loc_1800096CB
0x18000949b  mov     rcx, [rbp+57h+phSLC]; hSLC
0x18000949f  lea     rax, [rbp+57h+var_50]
0x1800094a3  mov     [rsp+0B0h+ppReturnIds], rax; ppReturnIds
0x1800094a8  lea     r8, [rbp+57h+Uuid]; pQueryId
0x1800094ac  lea     rax, [rbp+57h+var_70]
0x1800094b0  mov     r9d, 1; eReturnIdType
0x1800094b6  xor     edx, edx; eQueryIdType
0x1800094b8  mov     [rsp+0B0h+pnReturnIds], rax; pnReturnIds
0x1800094bd  call    cs:__imp_SLGetSLIDList
0x1800094c4  nop     dword ptr [rax+rax+00h]
0x1800094c9  mov     ebx, eax
0x1800094cb  test    eax, eax
0x1800094cd  jns     short loc_1800094FA
0x1800094cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094d6  lea     rdi, WPP_GLOBAL_Control
0x1800094dd  cmp     rcx, rdi
0x1800094e0  jz      loc_1800096D4
0x1800094e6  test    byte ptr [rcx+1Ch], 4
0x1800094ea  jz      loc_1800096D4
0x1800094f0  mov     edx, 15h
0x1800094f5  jmp     loc_1800096C8
0x1800094fa  xor     esi, esi
0x1800094fc  lea     rdi, WPP_GLOBAL_Control
0x180009503  cmp     esi, [rbp+57h+var_70]
0x180009506  jnb     loc_1800096D4
0x18000950c  mov     rax, [rbp+57h+var_50]
0x180009510  mov     ecx, esi
0x180009512  add     rcx, rcx
0x180009515  movups  xmm0, xmmword ptr [rax+rcx*8]
0x180009519  mov     rcx, [rbp+57h+hMem]; hMem
0x18000951d  movdqu  xmmword ptr [rbp+57h+pProductSkuId.Data1], xmm0
0x180009522  test    rcx, rcx
0x180009525  jz      short loc_18000953B
0x180009527  call    cs:__imp_LocalFree
0x18000952e  nop     dword ptr [rax+rax+00h]
0x180009533  mov     [rbp+57h+hMem], 0
0x18000953b  mov     rcx, [rbp+57h+phSLC]; hSLC
0x18000953f  lea     rax, [rbp+57h+hMem]
0x180009543  mov     [rsp+0B0h+ppReturnIds], rax; ppbValue
0x180009548  lea     r9, [rbp+57h+peDataType]; peDataType
0x18000954c  lea     rax, [rbp+57h+pcbValue]
0x180009550  lea     r8, pwszValueName; "AppXLOB"
0x180009557  mov     [rsp+0B0h+pnReturnIds], rax; pcbValue
0x18000955c  lea     rdx, [rbp+57h+pProductSkuId]; pProductSkuId
0x180009560  call    cs:__imp_SLGetProductSkuInformation
0x180009567  nop     dword ptr [rax+rax+00h]
0x18000956c  cmp     eax, 0C004F012h
0x180009571  jz      loc_180009684
0x180009577  test    eax, eax
0x180009579  js      loc_1800096AF
0x18000957f  cmp     [rbp+57h+peDataType], 1
0x180009583  jnz     loc_18000968B
0x180009589  cmp     [rbp+57h+pcbValue], 1
0x18000958d  jbe     loc_180009684
0x180009593  mov     rcx, [rbp+57h+hMem]; String1
0x180009597  lea     rdx, aTrue; "true"
0x18000959e  call    wcscmp_0
0x1800095a3  test    eax, eax
0x1800095a5  jnz     loc_180009684
0x1800095ab  mov     rcx, [rbp+57h+var_58]; hMem
0x1800095af  test    rcx, rcx
0x1800095b2  jz      short loc_1800095C8
0x1800095b4  call    cs:__imp_LocalFree
0x1800095bb  nop     dword ptr [rax+rax+00h]
0x1800095c0  mov     [rbp+57h+var_58], 0
0x1800095c8  mov     rcx, [rbp+57h+phSLC]; hSLC
0x1800095cc  lea     r9, [rbp+57h+var_58]; ppProductKeyIds
0x1800095d0  lea     r8, [rbp+57h+pnProductKeyIds]; pnProductKeyIds
0x1800095d4  lea     rdx, [rbp+57h+pProductSkuId]; pProductSkuId
0x1800095d8  call    cs:__imp_SLGetInstalledProductKeyIds
0x1800095df  nop     dword ptr [rax+rax+00h]
0x1800095e4  test    eax, eax
0x1800095e6  jns     short loc_180009635
0x1800095e8  cmp     eax, 0C004F012h
0x1800095ed  jnz     short loc_180009610
0x1800095ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095f6  cmp     rcx, rdi
0x1800095f9  jz      loc_180009684
0x1800095ff  test    byte ptr [rcx+1Ch], 1
0x180009603  jz      short loc_180009684
0x180009605  mov     rcx, [rcx+10h]
0x180009609  call    WPP_SF_
0x18000960e  jmp     short loc_180009684
0x180009610  mov     rcx, cs:WPP_GLOBAL_Control
0x180009617  cmp     rcx, rdi
0x18000961a  jz      short loc_180009684
0x18000961c  test    byte ptr [rcx+1Ch], 4
0x180009620  jz      short loc_180009684
0x180009622  mov     rcx, [rcx+10h]
0x180009626  mov     edx, 19h
0x18000962b  mov     r9d, eax
0x18000962e  call    WPP_SF_D
0x180009633  jmp     short loc_180009684
0x180009635  xor     esi, esi
0x180009637  cmp     [rbp+57h+pnProductKeyIds], esi
0x18000963a  jbe     short loc_180009684
0x18000963c  mov     rcx, [rbp+57h+phSLC]; hSLC
0x180009640  mov     edx, esi
0x180009642  shl     rdx, 4
0x180009646  add     rdx, [rbp+57h+var_58]; pPKeyId
0x18000964a  call    cs:__imp_SLUninstallProofOfPurchase
0x180009651  nop     dword ptr [rax+rax+00h]
0x180009656  test    eax, eax
0x180009658  jns     short loc_18000967D
0x18000965a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009661  cmp     rcx, rdi
0x180009664  jz      short loc_18000967D
0x180009666  test    byte ptr [rcx+1Ch], 4
0x18000966a  jz      short loc_18000967D
0x18000966c  mov     rcx, [rcx+10h]
0x180009670  mov     edx, 1Ah
0x180009675  mov     r9d, eax
0x180009678  call    WPP_SF_D
0x18000967d  inc     esi
0x18000967f  cmp     esi, [rbp+57h+pnProductKeyIds]
0x180009682  jb      short loc_18000963C
0x180009684  inc     esi
0x180009686  jmp     loc_180009503
0x18000968b  mov     ebx, 0C004F01Eh
0x180009690  mov     rcx, cs:WPP_GLOBAL_Control
0x180009697  cmp     rcx, rdi
0x18000969a  jz      short loc_1800096D4
0x18000969c  test    byte ptr [rcx+1Ch], 4
0x1800096a0  jz      short loc_1800096D4
0x1800096a2  mov     edx, 17h
0x1800096a7  mov     r9d, 0C004F01Eh
0x1800096ad  jmp     short loc_1800096CB
0x1800096af  mov     ebx, eax
0x1800096b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800096b8  cmp     rcx, rdi
0x1800096bb  jz      short loc_1800096D4
0x1800096bd  test    byte ptr [rcx+1Ch], 4
0x1800096c1  jz      short loc_1800096D4
0x1800096c3  mov     edx, 16h
0x1800096c8  mov     r9d, eax
0x1800096cb  mov     rcx, [rcx+10h]
0x1800096cf  call    WPP_SF_D
0x1800096d4  mov     rcx, [rbp+57h+phSLC]; hSLC
0x1800096d8  test    rcx, rcx
0x1800096db  jz      short loc_1800096E9
0x1800096dd  call    cs:__imp_SLClose
0x1800096e4  nop     dword ptr [rax+rax+00h]
0x1800096e9  mov     rcx, [rbp+57h+var_50]; hMem
0x1800096ed  test    rcx, rcx
0x1800096f0  jz      short loc_1800096FE
0x1800096f2  call    cs:__imp_LocalFree
0x1800096f9  nop     dword ptr [rax+rax+00h]
0x1800096fe  mov     rcx, [rbp+57h+hMem]; hMem
0x180009702  test    rcx, rcx
0x180009705  jz      short loc_180009713
0x180009707  call    cs:__imp_LocalFree
0x18000970e  nop     dword ptr [rax+rax+00h]
0x180009713  mov     rcx, [rbp+57h+var_58]; hMem
0x180009717  test    rcx, rcx
0x18000971a  jz      short loc_180009728
0x18000971c  call    cs:__imp_LocalFree
0x180009723  nop     dword ptr [rax+rax+00h]
0x180009728  mov     eax, ebx
0x18000972a  mov     rcx, [rbp+57h+var_28]
0x18000972e  xor     rcx, rsp; StackCookie
0x180009731  call    __security_check_cookie
0x180009736  add     rsp, 98h
0x18000973d  pop     rdi
0x18000973e  pop     rsi
0x18000973f  pop     rbx
0x180009740  pop     rbp
0x180009741  retn
```
