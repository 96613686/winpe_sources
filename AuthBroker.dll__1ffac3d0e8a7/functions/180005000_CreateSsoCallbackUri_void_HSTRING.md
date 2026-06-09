# CreateSsoCallbackUri(void *,HSTRING__ * *)

- ea: `0x180005000`
- end: `0x1800053ef`
- name: `?CreateSsoCallbackUri@@YAJPEAXPEAPEAUHSTRING__@@@Z`
- size: `1007`
- prototype: `__int64 __fastcall(void *clientTokenHandle, HSTRING__ **callbackAbsoluteUri)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f568`

## callees

- `0x1800035e0`
- `0x180005000`
- `0x1800053f8`
- `0x18000737c`
- `0x180011b30`
- `0x180011b58`
- `0x180011f80`
- `0x180020520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005206`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800053cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800053cd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800050ae`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800050ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053bf`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180005121`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180005121`

## pseudocode

```c
__int64 __fastcall CreateSsoCallbackUri(void *clientTokenHandle, HSTRING__ **callbackAbsoluteUri)
{
  HSTRING__ *hstring; // rbx
  WPP_PROJECT_CONTROL_BLOCK *v4; // r10
  int v5; // esi
  signed int v6; // eax
  const wchar_t *v7; // rcx
  wchar_t *v8; // r8
  __int64 v9; // rdi
  __int64 v10; // rbp
  __int64 v11; // rdx
  __int64 v12; // rax
  wchar_t *v13; // rcx
  int v14; // r9d
  int v15; // eax
  wchar_t *v16; // rax
  signed int LastError; // eax
  unsigned __int16 v18; // dx
  const _GUID *v19; // r8
  _WORD *v20; // rdx
  const wchar_t *v21; // rcx
  _WORD *v22; // rcx
  wchar_t *clientSid; // [rsp+30h] [rbp-2B8h] BYREF
  unsigned int ReturnLength; // [rsp+38h] [rbp-2B0h] BYREF
  Windows::Internal::String callback; // [rsp+40h] [rbp-2A8h] BYREF
  PSID TokenInformation[10]; // [rsp+50h] [rbp-298h] BYREF
  wchar_t ssoUrl[260]; // [rsp+A0h] [rbp-248h] BYREF
  _BYTE v29[8]; // [rsp+2A8h] [rbp-40h] BYREF

  hstring = 0;
  callback._hstring = 0;
  *callbackAbsoluteUri = 0;
  ReturnLength = 76;
  clientSid = 0;
  if ( !clientTokenHandle )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Control.Logger, 0x20u, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
    v5 = -2147024809;
LABEL_43:
    if ( v4 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (v4[1].ReserveSpace[28] & 8) != 0
      && v4[1].Control.Level >= 2u )
    {
      WPP_SF_d(v4[1].Control.Logger, 0x25u, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids, v5);
    }
    goto $Exit_4;
  }
  if ( GetTokenInformation(clientTokenHandle, TokenAppContainerSid, TokenInformation, 0x4Cu, &ReturnLength) )
  {
    if ( ConvertSidToStringSidW(TokenInformation[0], &clientSid) )
    {
      if ( clientSid && *clientSid == 83 )
        *clientSid = 115;
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 < 0 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto $Exit_4;
        if ( (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0 && WPP_GLOBAL_Control[1].Control.Level >= 2u )
        {
          WPP_SF_dd(WPP_GLOBAL_Control[1].Control.Logger, v18, v19, 0, v5);
          v4 = WPP_GLOBAL_Control;
        }
        goto LABEL_43;
      }
    }
    v4 = WPP_GLOBAL_Control;
  }
  else
  {
    v6 = GetLastError();
    v5 = v6;
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0x21u, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids, v5);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v5 < 0 )
      goto LABEL_43;
  }
  v7 = L"ms-app://";
  v8 = ssoUrl;
  v9 = 260;
  v10 = 2147483646;
  v11 = 260;
  v12 = 2147483646;
  do
  {
    if ( !v12 )
      break;
    if ( !*v7 )
      break;
    *v8++ = *v7++;
    --v12;
    --v11;
  }
  while ( v11 );
  v13 = v8 - 1;
  v5 = -2147024774;
  if ( v11 )
    v13 = v8;
  v14 = -2147024774;
  if ( v11 )
    v14 = 0;
  *v13 = 0;
  if ( !v11 )
  {
    v5 = v14;
    goto LABEL_65;
  }
  v15 = StringCchCatW(ssoUrl, 0x104u, clientSid);
  if ( v15 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    v5 = v15;
    goto LABEL_65;
  }
  v16 = ssoUrl;
  while ( *v16 )
  {
    ++v16;
    if ( !--v9 )
    {
      v5 = -2147024809;
LABEL_35:
      v4 = WPP_GLOBAL_Control;
      goto LABEL_65;
    }
  }
  v20 = &v29[-2 * v9];
  v21 = L"/";
  do
  {
    if ( !v10 )
      break;
    if ( !*v21 )
      break;
    *v20++ = *v21++;
    --v10;
    --v9;
  }
  while ( v9 );
  if ( v9 )
    v5 = 0;
  v22 = v20 - 1;
  if ( v9 )
    v22 = v20;
  *v22 = 0;
  if ( !v9 )
    goto LABEL_35;
  v5 = Windows::Internal::String::_InitializeHelper(&callback, ssoUrl);
  if ( v5 < 0 )
  {
    hstring = callback._hstring;
    v4 = WPP_GLOBAL_Control;
LABEL_65:
    if ( v4 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (v4[1].ReserveSpace[28] & 8) != 0
      && v4[1].Control.Level >= 2u )
    {
      WPP_SF_d(v4[1].Control.Logger, 0x26u, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids, v5);
    }
    goto $Exit_4;
  }
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
    && WPP_GLOBAL_Control[1].Control.Level >= 5u )
  {
    WPP_SF_S(WPP_GLOBAL_Control[1].Control.Logger, 0x27u, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids, ssoUrl);
  }
  v5 = 0;
  *callbackAbsoluteUri = callback._hstring;
$Exit_4:
  if ( clientSid )
    LocalFree(clientSid);
  if ( hstring )
    WindowsDeleteString(hstring);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180005000  mov     r11, rsp
0x180005003  push    rbx
0x180005004  push    rsi
0x180005005  sub     rsp, 2D8h
0x18000500c  mov     rax, cs:__security_cookie
0x180005013  xor     rax, rsp
0x180005016  mov     [rsp+2E8h+var_38], rax
0x18000501e  mov     [r11-18h], r12
0x180005022  xor     r12d, r12d
0x180005025  mov     [r11-20h], r14
0x180005029  mov     ebx, r12d
0x18000502c  mov     [rsp+2E8h+callback._hstring], rbx
0x180005031  mov     r14, callbackAbsoluteUri
0x180005034  mov     [r11-28h], r15
0x180005038  mov     [callbackAbsoluteUri], r12
0x18000503b  mov     [rsp+2E8h+var_2B0], 4Ch ; 'L'
0x180005043  mov     [rsp+2E8h+clientSid], r12
0x180005048  test    clientTokenHandle, clientTokenHandle
0x18000504b  jnz     short loc_180005094
0x18000504d  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180005054  lea     r15, WPP_GLOBAL_Control
0x18000505b  cmp     r10, r15
0x18000505e  jz      short loc_18000508A
0x180005060  test    byte ptr [r10+44h], 10h
0x180005065  jz      short loc_18000508A
0x180005067  cmp     byte ptr [r10+41h], 2
0x18000506c  jb      short loc_18000508A
0x18000506e  mov     clientTokenHandle, [r10+38h]; Logger
0x180005072  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x180005079  mov     edx, 20h ; ' '; id
0x18000507e  call    WPP_SF_
0x180005083  mov     r10, cs:WPP_GLOBAL_Control
0x18000508a  mov     esi, 80070057h
0x18000508f  jmp     loc_180005258
0x180005094  lea     rax, [rsp+2E8h+var_2B0]
0x180005099  mov     r9d, 4Ch ; 'L'; TokenInformationLength
0x18000509f  lea     r8, [rsp+2E8h+TokenInformation]; TokenInformation
0x1800050a4  mov     [rsp+2E8h+ReturnLength], rax; ReturnLength
0x1800050a9  mov     edx, 1Fh; TokenInformationClass
0x1800050ae  call    cs:__imp_GetTokenInformation
0x1800050b4  lea     r15, WPP_GLOBAL_Control
0x1800050bb  test    eax, eax
0x1800050bd  jnz     short loc_180005117
0x1800050bf  call    cs:__imp_GetLastError
0x1800050c5  mov     esi, eax
0x1800050c7  test    eax, eax
0x1800050c9  jle     short loc_1800050D4
0x1800050cb  movzx   esi, ax
0x1800050ce  or      esi, 80070000h
0x1800050d4  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800050db  cmp     r10, r15
0x1800050de  jz      short loc_18000510D
0x1800050e0  test    byte ptr [r10+44h], 10h
0x1800050e5  jz      short loc_18000510D
0x1800050e7  cmp     byte ptr [r10+41h], 2
0x1800050ec  jb      short loc_18000510D
0x1800050ee  mov     clientTokenHandle, [r10+38h]; Logger
0x1800050f2  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x1800050f9  mov     edx, 21h ; '!'; id
0x1800050fe  mov     r9d, esi; _a1
0x180005101  call    WPP_SF_d
0x180005106  mov     r10, cs:WPP_GLOBAL_Control
0x18000510d  test    esi, esi
0x18000510f  js      loc_180005258
0x180005115  jmp     short loc_18000514B
0x180005117  mov     clientTokenHandle, [rsp+2E8h+TokenInformation]; Sid
0x18000511c  lea     callbackAbsoluteUri, [rsp+2E8h+clientSid]; StringSid
0x180005121  call    cs:__imp_ConvertSidToStringSidW
0x180005127  test    eax, eax
0x180005129  jz      loc_180005206
0x18000512f  mov     rax, [rsp+2E8h+clientSid]
0x180005134  test    rax, rax
0x180005137  jz      short loc_180005144
0x180005139  cmp     word ptr [rax], 53h ; 'S'
0x18000513d  jnz     short loc_180005144
0x18000513f  mov     word ptr [rax], 73h ; 's'
0x180005144  mov     r10, cs:WPP_GLOBAL_Control
0x18000514b  mov     [rsp+2E8h+arg_10], rbp
0x180005153  lea     clientTokenHandle, aMsApp_0; "ms-app://"
0x18000515a  mov     [rsp+2E8h+arg_18], rdi
0x180005162  lea     r8, [rsp+2E8h+ssoUrl]
0x18000516a  mov     edi, 104h
0x18000516f  mov     ebp, 7FFFFFFEh
0x180005174  mov     edx, edi
0x180005176  mov     eax, ebp
0x180005178  test    rax, rax
0x18000517b  jz      short loc_18000519C
0x18000517d  movzx   r9d, word ptr [clientTokenHandle]
0x180005181  test    r9w, r9w
0x180005185  jz      short loc_18000519C
0x180005187  mov     [r8], r9w
0x18000518b  add     clientTokenHandle, 2
0x18000518f  add     r8, 2
0x180005193  dec     rax
0x180005196  sub     callbackAbsoluteUri, 1
0x18000519a  jnz     short loc_180005178
0x18000519c  test    callbackAbsoluteUri, callbackAbsoluteUri
0x18000519f  lea     clientTokenHandle, [r8-2]
0x1800051a3  mov     esi, 8007007Ah
0x1800051a8  cmovnz  clientTokenHandle, r8
0x1800051ac  mov     r9d, esi
0x1800051af  cmovnz  r9d, r12d
0x1800051b3  mov     [clientTokenHandle], r12w
0x1800051b7  jz      loc_18000535F
0x1800051bd  mov     r8, [rsp+2E8h+clientSid]; pszSrc
0x1800051c2  lea     clientTokenHandle, [rsp+2E8h+ssoUrl]; pszDest
0x1800051ca  mov     callbackAbsoluteUri, rdi; cchDest
0x1800051cd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800051d2  test    eax, eax
0x1800051d4  js      loc_180005354
0x1800051da  lea     rax, [rsp+2E8h+ssoUrl]
0x1800051e2  cmp     [rax], bx
0x1800051e5  jz      loc_180005294
0x1800051eb  add     rax, 2
0x1800051ef  sub     rdi, 1
0x1800051f3  jnz     short loc_1800051E2
0x1800051f5  mov     esi, 80070057h
0x1800051fa  mov     r10, cs:WPP_GLOBAL_Control
0x180005201  jmp     loc_180005362
0x180005206  call    cs:__imp_GetLastError
0x18000520c  mov     esi, eax
0x18000520e  test    eax, eax
0x180005210  jle     short loc_18000521B
0x180005212  movzx   esi, ax
0x180005215  or      esi, 80070000h
0x18000521b  test    esi, esi
0x18000521d  jns     loc_180005144
0x180005223  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000522a  cmp     r10, r15
0x18000522d  jz      $Exit_4
0x180005233  test    byte ptr [r10+44h], 10h
0x180005238  jz      short loc_180005258
0x18000523a  cmp     byte ptr [r10+41h], 2
0x18000523f  jb      short loc_180005258
0x180005241  mov     clientTokenHandle, [r10+38h]; Logger
0x180005245  xor     r9d, r9d; Logger
0x180005248  mov     dword ptr [rsp+2E8h+ReturnLength], esi; id
0x18000524c  call    WPP_SF_dd
0x180005251  mov     r10, cs:WPP_GLOBAL_Control
0x180005258  cmp     r10, r15; __annotation("TMF:",
0x18000525b  jz      $Exit_4
0x180005261  test    byte ptr [r10+44h], 8
0x180005266  jz      $Exit_4
0x18000526c  cmp     byte ptr [r10+41h], 2
0x180005271  jb      $Exit_4
0x180005277  mov     clientTokenHandle, [r10+38h]; Logger
0x18000527b  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x180005282  mov     edx, 25h ; '%'; id
0x180005287  mov     r9d, esi; _a1
0x18000528a  call    WPP_SF_d
0x18000528f  jmp     $Exit_4
0x180005294  lea     rax, [rdi+rdi]
0x180005298  lea     callbackAbsoluteUri, [rsp+2E8h+var_40]
0x1800052a0  sub     callbackAbsoluteUri, rax
0x1800052a3  lea     clientTokenHandle, asc_1800267C8; "/"
0x1800052aa  test    rdi, rdi
0x1800052ad  jz      short loc_1800052D3
0x1800052af  test    rbp, rbp
0x1800052b2  jz      short loc_1800052D0
0x1800052b4  movzx   eax, word ptr [clientTokenHandle]
0x1800052b7  test    ax, ax
0x1800052ba  jz      short loc_1800052D0
0x1800052bc  mov     [callbackAbsoluteUri], ax
0x1800052bf  add     clientTokenHandle, 2
0x1800052c3  add     callbackAbsoluteUri, 2
0x1800052c7  dec     rbp
0x1800052ca  sub     rdi, 1
0x1800052ce  jnz     short loc_1800052AF
0x1800052d0  test    rdi, rdi
0x1800052d3  cmovnz  esi, r12d
0x1800052d7  lea     clientTokenHandle, [callbackAbsoluteUri-2]
0x1800052db  test    rdi, rdi
0x1800052de  cmovnz  clientTokenHandle, callbackAbsoluteUri
0x1800052e2  mov     [clientTokenHandle], r12w
0x1800052e6  jz      loc_1800051FA
0x1800052ec  lea     callbackAbsoluteUri, [rsp+2E8h+ssoUrl]; str
0x1800052f4  lea     clientTokenHandle, [rsp+2E8h+callback]; this
0x1800052f9  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x1800052fe  mov     esi, eax
0x180005300  test    eax, eax
0x180005302  js      short loc_180005346
0x180005304  mov     clientTokenHandle, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000530b  cmp     clientTokenHandle, r15
0x18000530e  jz      short loc_180005339
0x180005310  test    byte ptr [clientTokenHandle+44h], 8
0x180005314  jz      short loc_180005339
0x180005316  cmp     byte ptr [clientTokenHandle+41h], 5
0x18000531a  jb      short loc_180005339
0x18000531c  mov     clientTokenHandle, [clientTokenHandle+38h]; Logger
0x180005320  lea     r9, [rsp+2E8h+ssoUrl]; _a1
0x180005328  mov     edx, 27h ; '''; id
0x18000532d  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x180005334  call    WPP_SF_S
0x180005339  mov     rax, [rsp+2E8h+callback._hstring]
0x18000533e  mov     esi, r12d
0x180005341  mov     [r14], rax
0x180005344  jmp     short loc_18000538D
0x180005346  mov     rbx, [rsp+2E8h+callback._hstring]
0x18000534b  mov     r10, cs:WPP_GLOBAL_Control
0x180005352  jmp     short loc_180005362
0x180005354  mov     r10, cs:WPP_GLOBAL_Control
0x18000535b  mov     esi, eax
0x18000535d  jmp     short loc_180005362
0x18000535f  mov     esi, r9d
0x180005362  cmp     r10, r15; __annotation("TMF:",
0x180005365  jz      short loc_18000538D
0x180005367  test    byte ptr [r10+44h], 8
0x18000536c  jz      short loc_18000538D
0x18000536e  cmp     byte ptr [r10+41h], 2
0x180005373  jb      short loc_18000538D
0x180005375  mov     clientTokenHandle, [r10+38h]; Logger
0x180005379  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x180005380  mov     edx, 26h ; '&'; id
0x180005385  mov     r9d, esi; _a1
0x180005388  call    WPP_SF_d
0x18000538d  mov     rbp, [rsp+2E8h+arg_10]
0x180005395  mov     rdi, [rsp+2E8h+arg_18]
0x18000539d  mov     clientTokenHandle, [rsp+2E8h+clientSid]; hMem
0x1800053a2  mov     r15, [rsp+2E8h+var_28]
0x1800053aa  mov     r14, [rsp+2E8h+var_20]
0x1800053b2  mov     r12, [rsp+2E8h+var_18]
0x1800053ba  test    clientTokenHandle, clientTokenHandle
0x1800053bd  jz      short loc_1800053C5
0x1800053bf  call    cs:__imp_LocalFree
0x1800053c5  test    rbx, rbx
0x1800053c8  jz      short loc_1800053D3
0x1800053ca  mov     clientTokenHandle, rbx; string
0x1800053cd  call    cs:__imp_WindowsDeleteString
0x1800053d3  mov     eax, esi
0x1800053d5  mov     clientTokenHandle, [rsp+2E8h+var_38]
0x1800053dd  xor     clientTokenHandle, rsp; StackCookie
0x1800053e0  call    __security_check_cookie
0x1800053e5  add     rsp, 2D8h
0x1800053ec  pop     rsi
0x1800053ed  pop     rbx
0x1800053ee  retn
```
