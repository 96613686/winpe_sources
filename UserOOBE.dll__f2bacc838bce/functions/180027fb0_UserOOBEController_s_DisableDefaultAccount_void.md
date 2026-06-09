# UserOOBEController::s_DisableDefaultAccount(void)

- ea: `0x180027fb0`
- end: `0x18002828f`
- name: `?s_DisableDefaultAccount@UserOOBEController@@CAJXZ`
- size: `735`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180024320`

## callees

- `0x1800032b0`
- `0x180004200`
- `0x180007114`
- `0x180007134`
- `0x180022fd0`
- `0x180027fb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002801d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002801d`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180028144`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180028144`
- `samcli!NetLocalGroupDelMembers` at `0x180028203`
- `samcli!NetLocalGroupDelMembers` at `0x180028203`
- `samcli!NetUserSetInfo` at `0x1800280f9`
- `samcli!NetUserSetInfo` at `0x1800280f9`
- `samcli!NetUserGetInfo` at `0x180028080`
- `samcli!NetUserGetInfo` at `0x180028080`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800281c7`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800281c7`

## string_xrefs

- `0x18002804a`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002815a`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180028250`: `shell\oobe\user\dll\useroobecontroller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 UserOOBEController::s_DisableDefaultAccount(void)
{
  int ValueW; // ebx
  bool v1; // sf
  DWORD Info; // eax
  __int64 i; // rcx
  DWORD v4; // eax
  __int64 j; // rcx
  const char *v6; // r9
  __int64 v7; // rdx
  __int64 v8; // rdx
  DWORD v9; // eax
  __int64 k; // rcx
  int pdwType; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  LPBYTE bufptr; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbSid; // [rsp+50h] [rbp-B0h] BYREF
  _SID_NAME_USE peUse; // [rsp+54h] [rbp-ACh] BYREF
  DWORD cchReferencedDomainName; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchName; // [rsp+5Ch] [rbp-A4h] BYREF
  BYTE buf[16]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pSid[544]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ReferencedDomainName[16]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR username[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR Name[264]; // [rsp+4C0h] [rbp+3C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6E8h] [rbp+5E8h]

  pcbData = 514;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
             L"DefaultAccountSAMName",
             2u,
             0,
             username,
             &pcbData);
  if ( !ValueW )
    goto LABEL_4;
  username[0] = 0;
  v1 = ValueW < 0;
  if ( ValueW > 0 )
  {
    ValueW = (unsigned __int16)ValueW | 0x80070000;
LABEL_4:
    v1 = ValueW < 0;
  }
  if ( v1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CF,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)ValueW,
      pdwType);
    return (unsigned int)ValueW;
  }
  bufptr = 0;
  Info = NetUserGetInfo(0, username, 0x17u, &bufptr);
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 0x7A )
    {
      ValueW = -805306139;
      goto LABEL_34;
    }
    if ( LODWORD(ErrorMap[i]) == Info )
      break;
  }
  ValueW = HIDWORD(ErrorMap[i]) | 0x10000000;
  if ( ErrorMap[i] < 0 )
  {
LABEL_34:
    v8 = 467;
    goto LABEL_35;
  }
  if ( (*((_DWORD *)bufptr + 6) & 0x22) != 2 )
  {
    *((_DWORD *)bufptr + 6) |= 2u;
    *((_DWORD *)bufptr + 6) &= ~0x20u;
    pcbData = *((_DWORD *)bufptr + 6);
    v4 = NetUserSetInfo(0, username, 0x3F0u, (LPBYTE)&pcbData, 0);
    for ( j = 0; ; j = (unsigned int)(j + 1) )
    {
      if ( (unsigned int)j >= 0x7A )
      {
        ValueW = -805306139;
        goto LABEL_22;
      }
      if ( LODWORD(ErrorMap[j]) == v4 )
        break;
    }
    ValueW = HIDWORD(ErrorMap[j]) | 0x10000000;
    if ( ErrorMap[j] >= 0 )
      goto LABEL_18;
LABEL_22:
    v8 = 476;
    goto LABEL_35;
  }
LABEL_18:
  cbSid = 68;
  memset_0(pSid, 0, sizeof(pSid));
  if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, &cbSid) )
  {
    v7 = 482;
LABEL_20:
    ValueW = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v7,
               (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
               v6);
    goto LABEL_36;
  }
  cchName = 256;
  cchReferencedDomainName = 15;
  peUse = 0;
  if ( !LookupAccountSidW(0, pSid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    v7 = 489;
    goto LABEL_20;
  }
  *(_QWORD *)buf = username;
  v9 = NetLocalGroupDelMembers(0, Name, 3u, buf, 1u);
  for ( k = 0; ; k = (unsigned int)(k + 1) )
  {
    if ( (unsigned int)k >= 0x7A )
    {
      ValueW = -805306139;
      goto LABEL_32;
    }
    if ( LODWORD(ErrorMap[k]) == v9 )
      break;
  }
  ValueW = HIDWORD(ErrorMap[k]) | 0x10000000;
  if ( ErrorMap[k] >= 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<_USER_INFO_23 *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_INFO_23 *,_USER_INFO_23 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_USER_INFO_23 *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_INFO_23 *,_USER_INFO_23 *,0,std::nullptr_t>>(&bufptr);
    return 0;
  }
LABEL_32:
  v8 = 492;
LABEL_35:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
    (const char *)(unsigned int)ValueW,
    pdwType);
LABEL_36:
  wil::details::unique_storage<wil::details::resource_policy<_USER_INFO_23 *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_INFO_23 *,_USER_INFO_23 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_USER_INFO_23 *,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_INFO_23 *,_USER_INFO_23 *,0,std::nullptr_t>>(&bufptr);
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x180027fb0  mov     [rsp-8+arg_0], rbx
0x180027fb5  mov     [rsp-8+arg_8], rsi
0x180027fba  push    rbp
0x180027fbb  lea     rbp, [rsp-5E0h]
0x180027fc3  sub     rsp, 6E0h
0x180027fca  mov     rax, cs:__security_cookie
0x180027fd1  xor     rax, rsp
0x180027fd4  mov     [rbp+5E0h+var_10], rax
0x180027fdb  lea     rax, [rsp+6E0h+var_6A0]
0x180027fe0  mov     [rsp+6E0h+var_6A0], 202h
0x180027fe8  mov     [rsp+6E0h+pcbData], rax; pcbData
0x180027fed  lea     r8, aDefaultaccount_0; "DefaultAccountSAMName"
0x180027ff4  lea     rax, [rbp+5E0h+username]
0x180027ffb  mov     r9d, 2; dwFlags
0x180028001  mov     [rsp+6E0h+pvData], rax; pvData
0x180028006  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002800d  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180028014  mov     [rsp+6E0h+pdwType], 0; int
0x18002801d  call    cs:__imp_RegGetValueW
0x180028023  mov     ebx, eax
0x180028025  test    eax, eax
0x180028027  jz      short loc_18002803F
0x180028029  xor     eax, eax
0x18002802b  mov     [rbp+5E0h+username], ax
0x180028032  test    ebx, ebx
0x180028034  jle     short loc_180028041
0x180028036  movzx   ebx, bx
0x180028039  or      ebx, 80070000h
0x18002803f  test    ebx, ebx
0x180028041  jns     short loc_180028063
0x180028043  mov     rcx, [rbp+5E8h]; this
0x18002804a  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180028051  mov     r9d, ebx; char *
0x180028054  mov     edx, 1CFh; void *
0x180028059  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002805e  jmp     loc_180028269
0x180028063  lea     r9, [rsp+6E0h+bufptr]; bufptr
0x180028068  mov     [rsp+6E0h+bufptr], 0
0x180028071  mov     r8d, 17h; level
0x180028077  lea     rdx, [rbp+5E0h+username]; username
0x18002807e  xor     ecx, ecx; servername
0x180028080  call    cs:__imp_NetUserGetInfo
0x180028086  xor     ecx, ecx
0x180028088  lea     rsi, ErrorMap
0x18002808f  cmp     ecx, 7Ah ; 'z'
0x180028092  jnb     loc_18002823F
0x180028098  cmp     [rsi+rcx*8], eax
0x18002809b  jz      short loc_1800280A1
0x18002809d  inc     ecx
0x18002809f  jmp     short loc_18002808F
0x1800280a1  mov     ebx, [rsi+rcx*8+4]
0x1800280a5  or      ebx, 10000000h
0x1800280ab  jl      loc_180028244
0x1800280b1  mov     rdx, [rsp+6E0h+bufptr]
0x1800280b6  mov     ecx, [rdx+18h]
0x1800280b9  mov     eax, ecx
0x1800280bb  and     al, 22h
0x1800280bd  cmp     al, 2
0x1800280bf  jz      short loc_18002811B
0x1800280c1  or      ecx, 2
0x1800280c4  mov     [rsp+6E0h+pdwType], 0; parm_err
0x1800280cd  mov     [rdx+18h], ecx
0x1800280d0  lea     r9, [rsp+6E0h+var_6A0]; buf
0x1800280d5  mov     rax, [rsp+6E0h+bufptr]
0x1800280da  lea     rdx, [rbp+5E0h+username]; username
0x1800280e1  mov     r8d, 3F0h; level
0x1800280e7  and     dword ptr [rax+18h], 0FFFFFFDFh
0x1800280eb  mov     rax, [rsp+6E0h+bufptr]
0x1800280f0  mov     ecx, [rax+18h]
0x1800280f3  mov     [rsp+6E0h+var_6A0], ecx
0x1800280f7  xor     ecx, ecx; servername
0x1800280f9  call    cs:__imp_NetUserSetInfo
0x1800280ff  xor     ecx, ecx
0x180028101  cmp     ecx, 7Ah ; 'z'
0x180028104  jnb     short loc_18002816D
0x180028106  cmp     [rsi+rcx*8], eax
0x180028109  jz      short loc_18002810F
0x18002810b  inc     ecx
0x18002810d  jmp     short loc_180028101
0x18002810f  mov     ebx, [rsi+rcx*8+4]
0x180028113  or      ebx, 10000000h
0x180028119  jl      short loc_180028172
0x18002811b  xor     edx, edx; Val
0x18002811d  mov     [rsp+6E0h+cbSid], 44h ; 'D'
0x180028125  mov     r8d, 220h; Size
0x18002812b  lea     rcx, [rsp+6E0h+pSid]; void *
0x180028130  call    memset_0
0x180028135  xor     edx, edx; DomainSid
0x180028137  lea     r9, [rsp+6E0h+cbSid]; cbSid
0x18002813c  lea     r8, [rsp+6E0h+pSid]; pSid
0x180028141  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x180028144  call    cs:__imp_CreateWellKnownSid
0x18002814a  test    eax, eax
0x18002814c  jnz     short loc_18002817C
0x18002814e  mov     edx, 1E2h; void *
0x180028153  mov     rcx, [rbp+5E8h]; this
0x18002815a  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180028161  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028166  mov     ebx, eax
0x180028168  jmp     loc_18002825F
0x18002816d  mov     ebx, 0D00000E5h
0x180028172  mov     edx, 1DCh
0x180028177  jmp     loc_180028249
0x18002817c  lea     rax, [rsp+6E0h+peUse]
0x180028181  mov     [rsp+6E0h+cchName], 100h
0x180028189  mov     [rsp+6E0h+pcbData], rax; peUse
0x18002818e  lea     r9, [rsp+6E0h+cchName]; cchName
0x180028193  lea     rax, [rsp+6E0h+cchReferencedDomainName]
0x180028198  mov     [rsp+6E0h+cchReferencedDomainName], 0Fh
0x1800281a0  mov     [rsp+6E0h+pvData], rax; cchReferencedDomainName
0x1800281a5  lea     r8, [rbp+5E0h+Name]; Name
0x1800281ac  lea     rax, [rbp+5E0h+ReferencedDomainName]
0x1800281b3  mov     [rsp+6E0h+peUse], 0
0x1800281bb  lea     rdx, [rsp+6E0h+pSid]; Sid
0x1800281c0  mov     [rsp+6E0h+pdwType], rax; ReferencedDomainName
0x1800281c5  xor     ecx, ecx; lpSystemName
0x1800281c7  call    cs:__imp_LookupAccountSidW
0x1800281cd  test    eax, eax
0x1800281cf  jnz     short loc_1800281DB
0x1800281d1  mov     edx, 1E9h
0x1800281d6  jmp     loc_180028153
0x1800281db  lea     rax, [rbp+5E0h+username]
0x1800281e2  mov     dword ptr [rsp+6E0h+pdwType], 1; totalentries
0x1800281ea  lea     r9, [rsp+6E0h+buf]; buf
0x1800281ef  mov     qword ptr [rsp+6E0h+buf], rax
0x1800281f4  mov     r8d, 3; level
0x1800281fa  lea     rdx, [rbp+5E0h+Name]; groupname
0x180028201  xor     ecx, ecx; servername
0x180028203  call    cs:__imp_NetLocalGroupDelMembers
0x180028209  xor     ecx, ecx
0x18002820b  cmp     ecx, 7Ah ; 'z'
0x18002820e  jnb     short loc_180028233
0x180028210  cmp     [rsi+rcx*8], eax
0x180028213  jz      short loc_180028219
0x180028215  inc     ecx
0x180028217  jmp     short loc_18002820B
0x180028219  mov     ebx, [rsi+rcx*8+4]
0x18002821d  or      ebx, 10000000h
0x180028223  jl      short loc_180028238
0x180028225  lea     rcx, [rsp+6E0h+bufptr]
0x18002822a  call    ??1?$unique_storage@U?$resource_policy@PEAU_USER_INFO_23@@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_USER_INFO_23 *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_INFO_23 *,_USER_INFO_23 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_USER_INFO_23 *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_INFO_23 *,_USER_INFO_23 *,0,std::nullptr_t>>(void)
0x18002822f  xor     eax, eax
0x180028231  jmp     short loc_18002826B
0x180028233  mov     ebx, 0D00000E5h
0x180028238  mov     edx, 1ECh
0x18002823d  jmp     short loc_180028249
0x18002823f  mov     ebx, 0D00000E5h
0x180028244  mov     edx, 1D3h; void *
0x180028249  mov     rcx, [rbp+5E8h]; this
0x180028250  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180028257  mov     r9d, ebx; char *
0x18002825a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002825f  lea     rcx, [rsp+6E0h+bufptr]
0x180028264  call    ??1?$unique_storage@U?$resource_policy@PEAU_USER_INFO_23@@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_USER_INFO_23 *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_INFO_23 *,_USER_INFO_23 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_USER_INFO_23 *,ulong (*)(void *),&NetApiBufferFree(void *),wistd::integral_constant<unsigned __int64,0>,_USER_INFO_23 *,_USER_INFO_23 *,0,std::nullptr_t>>(void)
0x180028269  mov     eax, ebx
0x18002826b  mov     rcx, [rbp+5E0h+var_10]
0x180028272  xor     rcx, rsp; StackCookie
0x180028275  call    __security_check_cookie
0x18002827a  lea     r11, [rsp+6E0h+var_s0]
0x180028282  mov     rbx, [r11+10h]
0x180028286  mov     rsi, [r11+18h]
0x18002828a  mov     rsp, r11
0x18002828d  pop     rbp
0x18002828e  retn
```
