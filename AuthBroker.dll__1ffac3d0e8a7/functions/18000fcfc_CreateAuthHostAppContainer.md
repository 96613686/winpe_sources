# _CreateAuthHostAppContainer

- ea: `0x18000fcfc`
- end: `0x180010095`
- name: `_CreateAuthHostAppContainer`
- size: `921`
- prototype: `__int64 __fastcall(unsigned int brokerFlags, int useSsoAppContainer, unsigned int enablePrivateNetwork, _SID_AND_ATTRIBUTES *capabilities, unsigned int capabilityCount, void **appContainerSid, unsigned int *slotIndex)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ed84`
- `0x180010494`

## callees

- `0x180003f40`
- `0x1800053f8`
- `0x180007084`
- `0x18000737c`
- `0x18000fa18`
- `0x18000fbd0`
- `0x18000fcfc`
- `0x180011210`
- `0x180011b30`
- `0x180011d74`
- `0x180020520`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000ffac`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001005a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000ffac`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001005a`
- `USERENV!CreateAppContainerProfile` at `0x18000ffde`
- `USERENV!CreateAppContainerProfile` at `0x18000ffde`
- `USERENV!DeleteAppContainerProfile` at `0x18000ff56`
- `USERENV!DeleteAppContainerProfile` at `0x18000ff56`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x18000fe5c`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x18000fe5c`

## pseudocode

```c
__int64 __fastcall CreateAuthHostAppContainer(
        unsigned int brokerFlags,
        int useSsoAppContainer,
        unsigned int enablePrivateNetwork,
        _SID_AND_ATTRIBUTES *capabilities,
        unsigned int capabilityCount,
        void **appContainerSid,
        unsigned int *slotIndex)
{
  int Logger; // ebx
  unsigned int v12; // r10d
  wchar_t *v13; // r8
  unsigned int v14; // eax
  const wchar_t *v16; // r8
  int v17; // eax
  WPP_PROJECT_CONTROL_BLOCK *v18; // rcx
  unsigned __int16 v19; // dx
  unsigned int v20; // r9d
  const _GUID *v21; // r8
  int v22; // eax
  const _GUID *v23; // r8
  int v24; // eax
  const _GUID *v25; // r8
  unsigned __int8 isAppContainerCacheAccessible[8]; // [rsp+30h] [rbp-A1h] BYREF
  void *appContainerSidLocal; // [rsp+38h] [rbp-99h] BYREF
  wchar_t slotString[8]; // [rsp+40h] [rbp-91h] BYREF
  wchar_t moniker[56]; // [rsp+50h] [rbp-81h] BYREF

  appContainerSidLocal = 0;
  *appContainerSid = 0;
  if ( useSsoAppContainer )
  {
    *slotIndex = 1;
LABEL_3:
    Logger = StringCchCopyW(moniker, 0x32u, L"microsoft.windows.authhost.");
    if ( Logger < 0 )
      goto $Exit_8;
    if ( useSsoAppContainer )
    {
      v13 = L"sso";
    }
    else
    {
      v13 = slotString;
      slotString[0] = *(_WORD *)slotIndex + 95;
      slotString[1] = 0;
    }
    Logger = StringCchCatW(moniker, v12, v13);
    if ( Logger < 0 )
      goto $Exit_8;
    if ( (brokerFlags & 0x100000) != 0 )
    {
      v16 = L".c";
    }
    else
    {
      if ( !enablePrivateNetwork )
      {
LABEL_19:
        Logger = StringCchCatW(moniker, 0x32u, L"_8wekyb3d8bbwe");
        if ( Logger >= 0 )
        {
          v17 = AppContainerDeriveSidFromMoniker(moniker, &appContainerSidLocal);
          Logger = v17;
          if ( v17 < 0 )
          {
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
              || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) == 0
              || WPP_GLOBAL_Control[1].Control.Level < 5u )
            {
              goto $Exit_8;
            }
            v19 = 64;
            goto LABEL_25;
          }
          isAppContainerCacheAccessible[0] = 0;
          if ( !_AuthHostAppContainerProfileExist(moniker) )
            goto LABEL_36;
          v17 = _IsAppContainerCacheAccessible(isAppContainerCacheAccessible, appContainerSidLocal);
          Logger = v17;
          if ( v17 < 0 )
          {
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
              || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) == 0
              || WPP_GLOBAL_Control[1].Control.Level < 5u )
            {
              goto $Exit_8;
            }
            v19 = 65;
LABEL_25:
            v20 = v17;
LABEL_26:
            WPP_SF_d(v18[1].Control.Logger, v19, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids, v20);
            goto $Exit_8;
          }
          if ( !isAppContainerCacheAccessible[0] )
          {
LABEL_36:
            if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
              && WPP_GLOBAL_Control[1].Control.Level >= 5u )
            {
              WPP_SF_Sd(WPP_GLOBAL_Control[1].Control.Logger, 0x42u, v21, moniker, Logger);
            }
            v22 = DeleteAppContainerProfile(moniker);
            Logger = v22;
            if ( v22 < 0 )
            {
              if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
                && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
                && WPP_GLOBAL_Control[1].Control.Level >= 5u )
              {
                WPP_SF_Sd(WPP_GLOBAL_Control[1].Control.Logger, 0x43u, v23, moniker, v22);
              }
              goto $Exit_8;
            }
            if ( appContainerSidLocal )
            {
              FreeSid(appContainerSidLocal);
              appContainerSidLocal = 0;
            }
            v24 = CreateAppContainerProfile(
                    moniker,
                    moniker,
                    moniker,
                    capabilities,
                    capabilityCount,
                    &appContainerSidLocal);
            Logger = v24;
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
              && WPP_GLOBAL_Control[1].Control.Level >= 5u )
            {
              WPP_SF_Sd(WPP_GLOBAL_Control[1].Control.Logger, 0x44u, v25, moniker, v24);
              v18 = WPP_GLOBAL_Control;
            }
            if ( Logger < 0 )
            {
              if ( v18 == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
                || (v18[1].ReserveSpace[28] & 0x10) == 0
                || v18[1].Control.Level < 2u )
              {
                goto $Exit_8;
              }
              v19 = 69;
              v20 = Logger;
              goto LABEL_26;
            }
          }
          *appContainerSid = appContainerSidLocal;
          appContainerSidLocal = 0;
        }
$Exit_8:
        if ( appContainerSidLocal )
          FreeSid(appContainerSidLocal);
        if ( Logger < 0 )
        {
          ReleaseAppContainerSlot(*slotIndex);
          *slotIndex = 0;
        }
        return (unsigned int)Logger;
      }
      v16 = L".p";
    }
    Logger = StringCchCatW(moniker, 0x32u, v16);
    if ( Logger < 0 )
      goto $Exit_8;
    goto LABEL_19;
  }
  v14 = AcquireAppContainerSlot();
  *slotIndex = v14;
  if ( v14 )
    goto LABEL_3;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
    && WPP_GLOBAL_Control[1].Control.Level >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Control.Logger, 0x3Fu, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids);
  }
  return 2147947406LL;
}

```

## disassembly

```asm
0x18000fcfc  push    rbp
0x18000fcfe  push    rbx
0x18000fcff  push    rsi
0x18000fd00  push    rdi
0x18000fd01  push    r12
0x18000fd03  push    r13
0x18000fd05  push    r14
0x18000fd07  push    r15
0x18000fd09  lea     rbp, [rsp-7]
0x18000fd0e  sub     rsp, 0D8h
0x18000fd15  mov     rax, cs:__security_cookie
0x18000fd1c  xor     rax, rsp
0x18000fd1f  mov     [rbp+3Fh+var_50], rax
0x18000fd23  mov     r12, [rbp+3Fh+arg_28]
0x18000fd27  mov     r13, capabilities
0x18000fd2a  mov     r15, [rbp+3Fh+arg_30]
0x18000fd2e  mov     esi, enablePrivateNetwork
0x18000fd31  mov     [rsp+110h+appContainerSidLocal], 0
0x18000fd3a  mov     edi, useSsoAppContainer
0x18000fd3c  mov     r14d, brokerFlags
0x18000fd3f  mov     qword ptr [r12], 0
0x18000fd47  test    useSsoAppContainer, useSsoAppContainer
0x18000fd49  jz      short loc_18000FD8B
0x18000fd4b  mov     dword ptr [r15], 1
0x18000fd52  mov     r10d, 32h ; '2'
0x18000fd58  lea     r8, aMicrosoftWindo; "microsoft.windows.authhost."
0x18000fd5f  mov     useSsoAppContainer, r10d; cchDest
0x18000fd62  lea     rcx, [rsp+110h+moniker]; pszDest
0x18000fd67  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fd6c  mov     ebx, eax
0x18000fd6e  test    eax, eax
0x18000fd70  js      $Exit_8
0x18000fd76  lea     rcx, [rsp+110h+moniker]; pszDest
0x18000fd7b  mov     useSsoAppContainer, r10d; cchDest
0x18000fd7e  test    edi, edi
0x18000fd80  jz      short loc_18000FDD6
0x18000fd82  lea     r8, aSso; "sso"
0x18000fd89  jmp     short loc_18000FDEF
0x18000fd8b  call    _AcquireAppContainerSlot
0x18000fd90  mov     [r15], eax
0x18000fd93  test    eax, eax
0x18000fd95  jnz     short loc_18000FD52
0x18000fd97  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000fd9e  lea     rsi, WPP_GLOBAL_Control
0x18000fda5  cmp     rcx, rsi
0x18000fda8  jz      short loc_18000FDCC
0x18000fdaa  mov     dil, 10h
0x18000fdad  test    [rcx+44h], dil
0x18000fdb1  jz      short loc_18000FDCC
0x18000fdb3  cmp     byte ptr [rcx+41h], 2
0x18000fdb7  jb      short loc_18000FDCC
0x18000fdb9  mov     rcx, [rcx+38h]; Logger
0x18000fdbd  lea     useSsoAppContainer, [rax+3Fh]; id
0x18000fdc0  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x18000fdc7  call    WPP_SF_
0x18000fdcc  mov     eax, 8007138Eh
0x18000fdd1  jmp     loc_180010075
0x18000fdd6  movzx   eax, word ptr [r15]
0x18000fdda  lea     r8, [rsp+110h+slotString]; pszSrc
0x18000fddf  add     ax, 5Fh ; '_'
0x18000fde3  mov     [rsp+110h+slotString], ax
0x18000fde8  xor     eax, eax
0x18000fdea  mov     [rsp+110h+slotString+2], ax
0x18000fdef  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000fdf4  mov     ebx, eax
0x18000fdf6  test    eax, eax
0x18000fdf8  js      $Exit_8
0x18000fdfe  bt      r14d, 14h
0x18000fe03  jnb     short loc_18000FE0E
0x18000fe05  lea     r8, aC; ".c"
0x18000fe0c  jmp     short loc_18000FE19
0x18000fe0e  test    esi, esi
0x18000fe10  jz      short loc_18000FE32
0x18000fe12  lea     r8, aP; ".p"
0x18000fe19  mov     useSsoAppContainer, 32h ; '2'; cchDest
0x18000fe1e  lea     rcx, [rsp+110h+moniker]; pszDest
0x18000fe23  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000fe28  mov     ebx, eax
0x18000fe2a  test    eax, eax
0x18000fe2c  js      $Exit_8
0x18000fe32  lea     r8, a8wekyb3d8bbwe; "_8wekyb3d8bbwe"
0x18000fe39  mov     useSsoAppContainer, 32h ; '2'; cchDest
0x18000fe3e  lea     rcx, [rsp+110h+moniker]; pszDest
0x18000fe43  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000fe48  mov     ebx, eax
0x18000fe4a  test    eax, eax
0x18000fe4c  js      $Exit_8
0x18000fe52  lea     rdx, [rsp+110h+appContainerSidLocal]
0x18000fe57  lea     rcx, [rsp+110h+moniker]
0x18000fe5c  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x18000fe62  mov     ebx, eax
0x18000fe64  test    eax, eax
0x18000fe66  jns     short loc_18000FEB6
0x18000fe68  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000fe6f  lea     rsi, WPP_GLOBAL_Control
0x18000fe76  cmp     rcx, rsi
0x18000fe79  jz      $Exit_8
0x18000fe7f  mov     dil, 10h
0x18000fe82  test    [rcx+44h], dil
0x18000fe86  jz      $Exit_8
0x18000fe8c  mov     r14b, 5
0x18000fe8f  cmp     [rcx+41h], r14b
0x18000fe93  jb      $Exit_8
0x18000fe99  mov     useSsoAppContainer, 40h ; '@'; id
0x18000fe9e  mov     r9d, eax; _a1
0x18000fea1  mov     rcx, [rcx+38h]; Logger
0x18000fea5  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x18000feac  call    WPP_SF_d
0x18000feb1  jmp     $Exit_8
0x18000feb6  lea     rcx, [rsp+110h+moniker]; lpwszMoniker
0x18000febb  call    ?_AuthHostAppContainerProfileExist@@YAEPEAG@Z; _AuthHostAppContainerProfileExist(ushort *)
0x18000fec0  mov     [rsp+110h+isAppContainerCacheAccessible], 0
0x18000fec5  lea     rsi, WPP_GLOBAL_Control
0x18000fecc  mov     dil, 10h
0x18000fecf  mov     r14b, 5
0x18000fed2  test    al, al
0x18000fed4  jz      short loc_18000FF22
0x18000fed6  mov     rdx, [rsp+110h+appContainerSidLocal]; appContainerSid
0x18000fedb  lea     rcx, [rsp+110h+isAppContainerCacheAccessible]; isAppContainerCacheAccessible
0x18000fee0  call    ?_IsAppContainerCacheAccessible@@YAJPEAEPEAX@Z; _IsAppContainerCacheAccessible(uchar *,void *)
0x18000fee5  mov     ebx, eax
0x18000fee7  test    eax, eax
0x18000fee9  jns     short loc_18000FF16
0x18000feeb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000fef2  cmp     rcx, rsi
0x18000fef5  jz      $Exit_8
0x18000fefb  test    [rcx+44h], dil
0x18000feff  jz      $Exit_8
0x18000ff05  cmp     [rcx+41h], r14b
0x18000ff09  jb      $Exit_8
0x18000ff0f  mov     useSsoAppContainer, 41h ; 'A'
0x18000ff14  jmp     short loc_18000FE9E
0x18000ff16  mov     al, [rsp+110h+isAppContainerCacheAccessible]
0x18000ff1a  test    al, al
0x18000ff1c  jnz     loc_18001003E
0x18000ff22  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000ff29  cmp     rcx, rsi
0x18000ff2c  jz      short loc_18000FF51
0x18000ff2e  test    [rcx+44h], dil
0x18000ff32  jz      short loc_18000FF51
0x18000ff34  cmp     [rcx+41h], r14b
0x18000ff38  jb      short loc_18000FF51
0x18000ff3a  mov     rcx, [rcx+38h]; Logger
0x18000ff3e  lea     capabilities, [rsp+110h+moniker]; _a2
0x18000ff43  mov     useSsoAppContainer, 42h ; 'B'; id
0x18000ff48  mov     [rsp+110h+Logger], ebx; Logger
0x18000ff4c  call    WPP_SF_Sd
0x18000ff51  lea     rcx, [rsp+110h+moniker]
0x18000ff56  call    cs:__imp_DeleteAppContainerProfile
0x18000ff5c  mov     ebx, eax
0x18000ff5e  test    eax, eax
0x18000ff60  jns     short loc_18000FFA2
0x18000ff62  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000ff69  cmp     rcx, rsi
0x18000ff6c  jz      $Exit_8
0x18000ff72  test    [rcx+44h], dil
0x18000ff76  jz      $Exit_8
0x18000ff7c  cmp     [rcx+41h], r14b
0x18000ff80  jb      $Exit_8
0x18000ff86  mov     rcx, [rcx+38h]; Logger
0x18000ff8a  lea     capabilities, [rsp+110h+moniker]; _a2
0x18000ff8f  mov     useSsoAppContainer, 43h ; 'C'; id
0x18000ff94  mov     [rsp+110h+Logger], eax; Logger
0x18000ff98  call    WPP_SF_Sd
0x18000ff9d  jmp     $Exit_8
0x18000ffa2  mov     rcx, [rsp+110h+appContainerSidLocal]; pSid
0x18000ffa7  test    rcx, rcx
0x18000ffaa  jz      short loc_18000FFBB
0x18000ffac  call    cs:__imp_FreeSid
0x18000ffb2  mov     [rsp+110h+appContainerSidLocal], 0
0x18000ffbb  lea     rax, [rsp+110h+appContainerSidLocal]
0x18000ffc0  mov     capabilities, r13
0x18000ffc3  mov     [rsp+110h+var_E8], rax
0x18000ffc8  lea     r8, [rsp+110h+moniker]
0x18000ffcd  mov     eax, [rbp+3Fh+arg_20]
0x18000ffd0  lea     rdx, [rsp+110h+moniker]
0x18000ffd5  lea     rcx, [rsp+110h+moniker]
0x18000ffda  mov     [rsp+110h+Logger], eax
0x18000ffde  call    cs:__imp_CreateAppContainerProfile
0x18000ffe4  mov     ebx, eax
0x18000ffe6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000ffed  cmp     rcx, rsi
0x18000fff0  jz      short loc_18001001C
0x18000fff2  test    [rcx+44h], dil
0x18000fff6  jz      short loc_18001001C
0x18000fff8  cmp     [rcx+41h], r14b
0x18000fffc  jb      short loc_18001001C
0x18000fffe  mov     rcx, [rcx+38h]; Logger
0x180010002  lea     capabilities, [rsp+110h+moniker]; _a2
0x180010007  mov     useSsoAppContainer, 44h ; 'D'; id
0x18001000c  mov     [rsp+110h+Logger], eax; Logger
0x180010010  call    WPP_SF_Sd
0x180010015  mov     rcx, cs:WPP_GLOBAL_Control
0x18001001c  test    ebx, ebx
0x18001001e  jns     short loc_18001003E
0x180010020  cmp     rcx, rsi; __annotation("TMF:",
0x180010023  jz      short $Exit_8
0x180010025  test    [rcx+44h], dil
0x180010029  jz      short $Exit_8
0x18001002b  cmp     byte ptr [rcx+41h], 2
0x18001002f  jb      short $Exit_8
0x180010031  mov     useSsoAppContainer, 45h ; 'E'
0x180010036  mov     r9d, ebx
0x180010039  jmp     loc_18000FEA1
0x18001003e  mov     rax, [rsp+110h+appContainerSidLocal]
0x180010043  mov     [r12], rax
0x180010047  mov     [rsp+110h+appContainerSidLocal], 0
0x180010050  mov     rcx, [rsp+110h+appContainerSidLocal]; pSid
0x180010055  test    rcx, rcx
0x180010058  jz      short loc_180010060
0x18001005a  call    cs:__imp_FreeSid
0x180010060  test    ebx, ebx
0x180010062  jns     short loc_180010073
0x180010064  mov     brokerFlags, [r15]; index
0x180010067  call    _ReleaseAppContainerSlot
0x18001006c  mov     dword ptr [r15], 0
0x180010073  mov     eax, ebx
0x180010075  mov     rcx, [rbp+3Fh+var_50]
0x180010079  xor     rcx, rsp; StackCookie
0x18001007c  call    __security_check_cookie
0x180010081  add     rsp, 0D8h
0x180010088  pop     r15
0x18001008a  pop     r14
0x18001008c  pop     r13
0x18001008e  pop     r12
0x180010090  pop     rdi
0x180010091  pop     rsi
0x180010092  pop     rbx
0x180010093  pop     rbp
0x180010094  retn
```
