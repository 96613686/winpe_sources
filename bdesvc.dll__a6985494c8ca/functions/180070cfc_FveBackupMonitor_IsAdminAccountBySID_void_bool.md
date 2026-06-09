# FveBackupMonitor::IsAdminAccountBySID(void *,bool *)

- ea: `0x180070cfc`
- end: `0x180070f38`
- name: `?IsAdminAccountBySID@FveBackupMonitor@@CAJPEAXPEA_N@Z`
- size: `572`
- prototype: `__int64 __fastcall(PSID Sid, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006ff08`

## callees

- `0x180009f60`
- `0x180034070`
- `0x180034d28`
- `0x180070cfc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070e27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070ea6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070e27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070ea6`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180070e17`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180070e17`
- `samcli!NetUserGetInfo` at `0x180070e82`
- `samcli!NetUserGetInfo` at `0x180070e82`
- `netutils!NetApiBufferFree` at `0x180070f07`
- `netutils!NetApiBufferFree` at `0x180070f07`

## pseudocode

```c
__int64 __fastcall FveBackupMonitor::IsAdminAccountBySID(PSID Sid, bool *a2)
{
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  signed int v7; // eax
  bool v8; // di
  signed int LastError; // eax
  enum _SID_NAME_USE peUse; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  LPBYTE bufptr; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+270h] [rbp+170h] BYREF

  bufptr = 0;
  memset_0(Name, 0, 0x208u);
  memset_0(ReferencedDomainName, 0, 0x208u);
  peUse = 0;
  cchName = 260;
  cchReferencedDomainName = 260;
  if ( !a2 )
  {
    v4 = -2147467261;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      return v4;
    v6 = 51;
    goto LABEL_5;
  }
  if ( !Sid )
  {
    v4 = -2147024809;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      return v4;
    v6 = 52;
    goto LABEL_5;
  }
  *a2 = 0;
  if ( LookupAccountSidW(0, Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    v8 = 0;
    if ( !NetUserGetInfo(0, Name, 1u, &bufptr) && (bufptr[20] & 2) != 0 )
      v8 = (bufptr[40] & 2) == 0;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( !v4 )
      goto LABEL_26;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_929186be452536e5252128d48ffaedab_Traceguids, v4);
    if ( (v4 & 0x80000000) == 0 )
LABEL_26:
      *a2 = v8;
    goto LABEL_27;
  }
  v7 = GetLastError();
  v4 = v7;
  if ( v7 > 0 )
    v4 = (unsigned __int16)v7 | 0x80070000;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    v6 = 53;
LABEL_5:
    WPP_SF_d(v5[2], v6, WPP_929186be452536e5252128d48ffaedab_Traceguids, v4);
  }
LABEL_27:
  if ( bufptr )
    NetApiBufferFree(bufptr);
  return v4;
}

```

## disassembly

```asm
0x180070cfc  mov     [rsp-8+arg_10], rbx
0x180070d01  push    rbp
0x180070d02  push    rsi
0x180070d03  push    rdi
0x180070d04  lea     rbp, [rsp-390h]
0x180070d0c  sub     rsp, 490h
0x180070d13  mov     rax, cs:__security_cookie
0x180070d1a  xor     rax, rsp
0x180070d1d  mov     [rbp+3A0h+var_20], rax
0x180070d24  mov     rsi, rdx
0x180070d27  mov     [rsp+4A0h+bufptr], 0
0x180070d30  mov     rbx, rcx
0x180070d33  mov     edi, 208h
0x180070d38  mov     r8d, edi; Size
0x180070d3b  lea     rcx, [rsp+4A0h+Name]; void *
0x180070d40  xor     edx, edx; Val
0x180070d42  call    memset_0
0x180070d47  mov     r8d, edi; Size
0x180070d4a  lea     rcx, [rbp+3A0h+var_230]; void *
0x180070d51  xor     edx, edx; Val
0x180070d53  call    memset_0
0x180070d58  mov     [rsp+4A0h+var_460], 0
0x180070d60  mov     eax, 104h
0x180070d65  mov     [rsp+4A0h+cchName], eax
0x180070d69  mov     [rsp+4A0h+var_45C], eax
0x180070d6d  test    rsi, rsi
0x180070d70  jnz     short loc_180070DB3
0x180070d72  mov     ebx, 80004003h
0x180070d77  mov     rcx, cs:WPP_GLOBAL_Control
0x180070d7e  lea     rax, WPP_GLOBAL_Control
0x180070d85  cmp     rcx, rax
0x180070d88  jz      loc_180070F13
0x180070d8e  test    byte ptr [rcx+1Ch], 40h
0x180070d92  jz      loc_180070F13
0x180070d98  lea     edx, [rsi+33h]
0x180070d9b  mov     rcx, [rcx+10h]
0x180070d9f  lea     r8, WPP_929186be452536e5252128d48ffaedab_Traceguids
0x180070da6  mov     r9d, ebx
0x180070da9  call    WPP_SF_d
0x180070dae  jmp     loc_180070EFD
0x180070db3  test    rbx, rbx
0x180070db6  jnz     short loc_180070DE5
0x180070db8  mov     ebx, 80070057h
0x180070dbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180070dc4  lea     rax, WPP_GLOBAL_Control
0x180070dcb  cmp     rcx, rax
0x180070dce  jz      loc_180070F13
0x180070dd4  test    byte ptr [rcx+1Ch], 40h
0x180070dd8  jz      loc_180070F13
0x180070dde  mov     edx, 34h ; '4'
0x180070de3  jmp     short loc_180070D9B
0x180070de5  lea     rax, [rsp+4A0h+var_460]
0x180070dea  mov     byte ptr [rsi], 0
0x180070ded  mov     [rsp+4A0h+peUse], rax; peUse
0x180070df2  lea     r9, [rsp+4A0h+cchName]; cchName
0x180070df7  lea     rax, [rsp+4A0h+var_45C]
0x180070dfc  mov     rdx, rbx; Sid
0x180070dff  mov     [rsp+4A0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180070e04  lea     r8, [rsp+4A0h+Name]; Name
0x180070e09  lea     rax, [rbp+3A0h+var_230]
0x180070e10  xor     ecx, ecx; lpSystemName
0x180070e12  mov     [rsp+4A0h+ReferencedDomainName], rax; ReferencedDomainName
0x180070e17  call    cs:__imp_LookupAccountSidW
0x180070e1e  nop     dword ptr [rax+rax+00h]
0x180070e23  test    eax, eax
0x180070e25  jnz     short loc_180070E6D
0x180070e27  call    cs:__imp_GetLastError
0x180070e2e  nop     dword ptr [rax+rax+00h]
0x180070e33  mov     ebx, eax
0x180070e35  test    eax, eax
0x180070e37  jle     short loc_180070E42
0x180070e39  movzx   ebx, ax
0x180070e3c  or      ebx, 80070000h
0x180070e42  mov     rcx, cs:WPP_GLOBAL_Control
0x180070e49  lea     rax, WPP_GLOBAL_Control
0x180070e50  cmp     rcx, rax
0x180070e53  jz      loc_180070EFD
0x180070e59  test    byte ptr [rcx+1Ch], 40h
0x180070e5d  jz      loc_180070EFD
0x180070e63  mov     edx, 35h ; '5'
0x180070e68  jmp     loc_180070D9B
0x180070e6d  lea     r9, [rsp+4A0h+bufptr]; bufptr
0x180070e72  mov     r8d, 1; level
0x180070e78  lea     rdx, [rsp+4A0h+Name]; username
0x180070e7d  xor     ecx, ecx; servername
0x180070e7f  xor     dil, dil
0x180070e82  call    cs:__imp_NetUserGetInfo
0x180070e89  nop     dword ptr [rax+rax+00h]
0x180070e8e  test    eax, eax
0x180070e90  jnz     short loc_180070EA6
0x180070e92  mov     rax, [rsp+4A0h+bufptr]
0x180070e97  test    byte ptr [rax+14h], 2
0x180070e9b  jz      short loc_180070EA6
0x180070e9d  test    byte ptr [rax+28h], 2
0x180070ea1  jnz     short loc_180070EA6
0x180070ea3  mov     dil, 1
0x180070ea6  call    cs:__imp_GetLastError
0x180070ead  nop     dword ptr [rax+rax+00h]
0x180070eb2  mov     ebx, eax
0x180070eb4  test    eax, eax
0x180070eb6  jle     short loc_180070EC1
0x180070eb8  movzx   ebx, ax
0x180070ebb  or      ebx, 80070000h
0x180070ec1  test    ebx, ebx
0x180070ec3  jz      short loc_180070EFA
0x180070ec5  mov     rcx, cs:WPP_GLOBAL_Control
0x180070ecc  lea     rax, WPP_GLOBAL_Control
0x180070ed3  cmp     rcx, rax
0x180070ed6  jz      short loc_180070EF6
0x180070ed8  test    byte ptr [rcx+1Ch], 40h
0x180070edc  jz      short loc_180070EF6
0x180070ede  mov     rcx, [rcx+10h]
0x180070ee2  lea     r8, WPP_929186be452536e5252128d48ffaedab_Traceguids
0x180070ee9  mov     edx, 36h ; '6'
0x180070eee  mov     r9d, ebx
0x180070ef1  call    WPP_SF_d
0x180070ef6  test    ebx, ebx
0x180070ef8  js      short loc_180070EFD
0x180070efa  mov     [rsi], dil
0x180070efd  mov     rcx, [rsp+4A0h+bufptr]; Buffer
0x180070f02  test    rcx, rcx
0x180070f05  jz      short loc_180070F13
0x180070f07  call    cs:__imp_NetApiBufferFree
0x180070f0e  nop     dword ptr [rax+rax+00h]
0x180070f13  mov     eax, ebx
0x180070f15  mov     rcx, [rbp+3A0h+var_20]
0x180070f1c  xor     rcx, rsp; StackCookie
0x180070f1f  call    __security_check_cookie
0x180070f24  mov     rbx, [rsp+4A0h+arg_10]
0x180070f2c  add     rsp, 490h
0x180070f33  pop     rdi
0x180070f34  pop     rsi
0x180070f35  pop     rbp
0x180070f36  retn
```
