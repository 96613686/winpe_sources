# GetAuthBrokerClientAppContainerStringInfo(ClientAppContainerStringInfoType,void *,ushort * *)

- ea: `0x1800045c0`
- end: `0x1800047bb`
- name: `?GetAuthBrokerClientAppContainerStringInfo@@YAJW4ClientAppContainerStringInfoType@@PEAXPEAPEAG@Z`
- size: `507`
- prototype: `__int64 __fastcall(int infoType, void *clientTokenHandle, wchar_t **string)`
- caller_count: `8`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800073bc`
- `0x180011034`
- `0x1800113a8`
- `0x1800154bc`
- `0x180019484`
- `0x18001a9e0`
- `0x18001e210`
- `0x18001fab0`

## callees

- `0x1800045c0`
- `0x180004f00`
- `0x18000737c`
- `0x180010be0`
- `0x180011b30`
- `0x180011f80`
- `0x180020520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000465e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000474e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000465e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000474e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004654`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004654`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000472d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000472d`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerLookupMoniker` at `0x1800046e5`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerLookupMoniker` at `0x1800046e5`

## pseudocode

```c
__int64 __fastcall GetAuthBrokerClientAppContainerStringInfo(int infoType, void *clientTokenHandle, wchar_t **string)
{
  unsigned int PackageFullNameFromMoniker; // ebx
  unsigned __int16 v6; // dx
  const _GUID *v7; // r8
  signed int LastError; // eax
  int v9; // eax
  wchar_t *v10; // rbp
  wchar_t *v11; // rax
  signed int v12; // eax
  unsigned int appContainerInfoSize[4]; // [rsp+30h] [rbp-88h] BYREF
  PSID appContainerInfo[10]; // [rsp+40h] [rbp-78h] BYREF

  appContainerInfoSize[0] = 76;
  *string = 0;
  if ( !clientTokenHandle )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Control.Logger, 0x20u, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids);
    }
    return (unsigned int)-2147024809;
  }
  if ( !GetTokenInformation(clientTokenHandle, TokenAppContainerSid, appContainerInfo, 0x4Cu, appContainerInfoSize) )
  {
    LastError = GetLastError();
    PackageFullNameFromMoniker = LastError;
    if ( LastError > 0 )
      PackageFullNameFromMoniker = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control[1].Control.Logger,
        0x21u,
        WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids,
        PackageFullNameFromMoniker);
    }
    return PackageFullNameFromMoniker;
  }
  if ( infoType )
  {
    if ( (unsigned int)(infoType - 1) >= 2 )
    {
      PackageFullNameFromMoniker = -2147418113;
LABEL_29:
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
        && WPP_GLOBAL_Control[1].Control.Level >= 2u )
      {
        WPP_SF_dd(WPP_GLOBAL_Control[1].Control.Logger, v6, v7, infoType, PackageFullNameFromMoniker);
      }
      return PackageFullNameFromMoniker;
    }
    v9 = AppContainerLookupMoniker(appContainerInfo[0], string);
    PackageFullNameFromMoniker = v9;
    if ( infoType == 2 )
    {
      if ( v9 < 0 )
        goto LABEL_29;
      v10 = *string;
      if ( !*string )
        return PackageFullNameFromMoniker;
      *string = 0;
      PackageFullNameFromMoniker = GetPackageFullNameFromMoniker(v10, string);
      FreeAuthBrokerClientAppContainerString(ClientAppContainerMonikerInfo, v10);
    }
LABEL_28:
    if ( (PackageFullNameFromMoniker & 0x80000000) == 0 )
      return PackageFullNameFromMoniker;
    goto LABEL_29;
  }
  if ( !ConvertSidToStringSidW(appContainerInfo[0], string) )
  {
    v12 = GetLastError();
    PackageFullNameFromMoniker = v12;
    if ( v12 > 0 )
      PackageFullNameFromMoniker = (unsigned __int16)v12 | 0x80070000;
    goto LABEL_28;
  }
  v11 = *string;
  if ( *string && *v11 == 83 )
    *v11 = 115;
  return 0;
}

```

## disassembly

```asm
0x1800045c0  push    rbx
0x1800045c2  push    rsi
0x1800045c3  push    rdi
0x1800045c4  sub     rsp, 0A0h
0x1800045cb  mov     rax, cs:__security_cookie
0x1800045d2  xor     rax, rsp
0x1800045d5  mov     [rsp+0B8h+var_28], rax
0x1800045dd  mov     [rsp+0B8h+appContainerInfoSize], 4Ch ; 'L'
0x1800045e5  mov     rdi, string
0x1800045e8  mov     qword ptr [string], 0
0x1800045ef  mov     rax, clientTokenHandle
0x1800045f2  mov     esi, infoType
0x1800045f4  test    clientTokenHandle, clientTokenHandle
0x1800045f7  jnz     short loc_180004637
0x1800045f9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180004600  lea     rax, WPP_GLOBAL_Control
0x180004607  cmp     rcx, rax
0x18000460a  jz      short loc_18000462D
0x18000460c  test    byte ptr [rcx+44h], 10h
0x180004610  jz      short loc_18000462D
0x180004612  cmp     byte ptr [rcx+41h], 2
0x180004616  jb      short loc_18000462D
0x180004618  mov     rcx, [rcx+38h]; Logger
0x18000461c  lea     string, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x180004623  mov     edx, 20h ; ' '; id
0x180004628  call    WPP_SF_
0x18000462d  mov     ebx, 80070057h
0x180004632  jmp     $Exit_2
0x180004637  lea     rcx, [rsp+0B8h+appContainerInfoSize]
0x18000463c  mov     r9d, 4Ch ; 'L'; TokenInformationLength
0x180004642  mov     [rsp+0B8h+ReturnLength], rcx; ReturnLength
0x180004647  lea     string, [rsp+0B8h+appContainerInfo]; TokenInformation
0x18000464c  mov     rcx, rax; TokenHandle
0x18000464f  mov     edx, 1Fh; TokenInformationClass
0x180004654  call    cs:__imp_GetTokenInformation
0x18000465a  test    eax, eax
0x18000465c  jnz     short loc_1800046BB
0x18000465e  call    cs:__imp_GetLastError
0x180004664  mov     ebx, eax
0x180004666  test    eax, eax
0x180004668  jle     short loc_180004673
0x18000466a  movzx   ebx, ax
0x18000466d  or      ebx, 80070000h
0x180004673  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000467a  lea     rax, WPP_GLOBAL_Control
0x180004681  cmp     rcx, rax
0x180004684  jz      $Exit_2
0x18000468a  test    byte ptr [rcx+44h], 10h
0x18000468e  jz      $Exit_2
0x180004694  cmp     byte ptr [rcx+41h], 2
0x180004698  jb      $Exit_2
0x18000469e  mov     rcx, [rcx+38h]; Logger
0x1800046a2  lea     string, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x1800046a9  mov     edx, 21h ; '!'; id
0x1800046ae  mov     r9d, ebx; _a1
0x1800046b1  call    WPP_SF_d
0x1800046b6  jmp     $Exit_2
0x1800046bb  mov     [rsp+0B8h+arg_18], rbp
0x1800046c3  mov     infoType, esi
0x1800046c5  test    esi, esi
0x1800046c7  jz      short loc_180004725
0x1800046c9  sub     infoType, 1
0x1800046cc  jz      short loc_1800046DD
0x1800046ce  cmp     infoType, 1
0x1800046d1  jz      short loc_1800046DD
0x1800046d3  mov     ebx, 8000FFFFh
0x1800046d8  jmp     loc_180004767
0x1800046dd  mov     rcx, [rsp+0B8h+appContainerInfo]
0x1800046e2  mov     clientTokenHandle, rdi
0x1800046e5  call    cs:__imp_AppContainerLookupMoniker
0x1800046eb  mov     ebx, eax
0x1800046ed  cmp     esi, 2
0x1800046f0  jnz     short loc_180004763
0x1800046f2  test    eax, eax
0x1800046f4  js      short loc_180004767
0x1800046f6  mov     rbp, [rdi]
0x1800046f9  test    rbp, rbp
0x1800046fc  jz      loc_180004796
0x180004702  mov     clientTokenHandle, rdi; packageFullName
0x180004705  mov     qword ptr [rdi], 0
0x18000470c  mov     rcx, rbp; moniker
0x18000470f  call    _GetPackageFullNameFromMoniker
0x180004714  mov     clientTokenHandle, rbp; string
0x180004717  mov     infoType, 1; infoType
0x18000471c  mov     ebx, eax
0x18000471e  call    ?FreeAuthBrokerClientAppContainerString@@YAXW4ClientAppContainerStringInfoType@@PEAG@Z; FreeAuthBrokerClientAppContainerString(ClientAppContainerStringInfoType,ushort *)
0x180004723  jmp     short loc_180004763
0x180004725  mov     rcx, [rsp+0B8h+appContainerInfo]; Sid
0x18000472a  mov     clientTokenHandle, rdi; StringSid
0x18000472d  call    cs:__imp_ConvertSidToStringSidW
0x180004733  test    eax, eax
0x180004735  jz      short loc_18000474E
0x180004737  mov     rax, [rdi]
0x18000473a  test    rax, rax
0x18000473d  jz      short loc_18000474A
0x18000473f  cmp     word ptr [rax], 53h ; 'S'
0x180004743  jnz     short loc_18000474A
0x180004745  mov     word ptr [rax], 73h ; 's'
0x18000474a  xor     ebx, ebx
0x18000474c  jmp     short loc_180004796
0x18000474e  call    cs:__imp_GetLastError
0x180004754  mov     ebx, eax
0x180004756  test    eax, eax
0x180004758  jle     short loc_180004763
0x18000475a  movzx   ebx, ax
0x18000475d  or      ebx, 80070000h
0x180004763  test    ebx, ebx
0x180004765  jns     short loc_180004796
0x180004767  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000476e  lea     rax, WPP_GLOBAL_Control
0x180004775  cmp     rcx, rax
0x180004778  jz      short loc_180004796
0x18000477a  test    byte ptr [rcx+44h], 10h
0x18000477e  jz      short loc_180004796
0x180004780  cmp     byte ptr [rcx+41h], 2
0x180004784  jb      short loc_180004796
0x180004786  mov     rcx, [rcx+38h]; Logger
0x18000478a  mov     r9d, esi; Logger
0x18000478d  mov     dword ptr [rsp+0B8h+ReturnLength], ebx; id
0x180004791  call    WPP_SF_dd
0x180004796  mov     rbp, [rsp+0B8h+arg_18]
0x18000479e  mov     eax, ebx
0x1800047a0  mov     rcx, [rsp+0B8h+var_28]
0x1800047a8  xor     rcx, rsp; StackCookie
0x1800047ab  call    __security_check_cookie
0x1800047b0  add     rsp, 0A0h
0x1800047b7  pop     rdi
0x1800047b8  pop     rsi
0x1800047b9  pop     rbx
0x1800047ba  retn
```
