# CIdentityProfileHandler::_AdjustRegSidKeyForUser(HKEY__ *,ushort const *)

- ea: `0x180014974`
- end: `0x180014dde`
- name: `?_AdjustRegSidKeyForUser@CIdentityProfileHandler@@AEAAJPEAUHKEY__@@PEBG@Z`
- size: `1130`
- prototype: `__int64 __fastcall(CIdentityProfileHandler *this, HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800022d0`
- `0x180014de4`

## callees

- `0x1800144b4`
- `0x180014974`
- `0x180019750`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180014d0f`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180014d0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ba4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014cab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ba4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014cab`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014b1f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014b2c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014b39`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014b1f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014b2c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014b39`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180014b9a`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180014b9a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180014bf5`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180014c4b`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180014ca1`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180014bf5`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180014c4b`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180014ca1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014b4b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014b4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014d49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014d59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019f4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019f64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014d49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014d59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019f4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019f64`
- `ntdll!RtlFreeHeap` at `0x180014d7f`
- `ntdll!RtlFreeHeap` at `0x180014da5`
- `ntdll!RtlFreeHeap` at `0x180019f8c`
- `ntdll!RtlFreeHeap` at `0x180019fb4`
- `ntdll!RtlFreeHeap` at `0x180014d7f`
- `ntdll!RtlFreeHeap` at `0x180014da5`
- `ntdll!RtlFreeHeap` at `0x180019f8c`
- `ntdll!RtlFreeHeap` at `0x180019fb4`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180014cf9`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180014cf9`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180014ce3`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180014ce3`
- `ntdll!RtlNtStatusToDosError` at `0x180014a6a`
- `ntdll!RtlNtStatusToDosError` at `0x180014ae7`
- `ntdll!RtlNtStatusToDosError` at `0x180014a6a`
- `ntdll!RtlNtStatusToDosError` at `0x180014ae7`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180014a5e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180014adb`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180014a5e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180014adb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800149d6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800149d6`

## pseudocode

```c
__int64 __fastcall CIdentityProfileHandler::_AdjustRegSidKeyForUser(
        CIdentityProfileHandler *this,
        HKEY a2,
        const unsigned __int16 *a3)
{
  struct _ACL *v4; // rdi
  int LastError; // ebx
  CIdentityProfileHandler *v6; // rcx
  __int64 v7; // rdx
  int v8; // eax
  int v9; // eax
  DWORD LengthSid; // ebx
  DWORD v11; // ebx
  DWORD v12; // ebx
  struct _ACL *v13; // rax
  PSID pSid; // [rsp+60h] [rbp-78h] BYREF
  PSID hMem; // [rsp+68h] [rbp-70h] BYREF
  PSID P; // [rsp+70h] [rbp-68h] BYREF
  struct _ACL *v18; // [rsp+78h] [rbp-60h]
  _BYTE SecurityDescriptor[32]; // [rsp+80h] [rbp-58h] BYREF
  __int64 v20; // [rsp+A0h] [rbp-38h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+A8h] [rbp-30h] BYREF

  hMem = 0;
  P = 0;
  pSid = 0;
  v4 = 0;
  v18 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v20 = 0;
  if ( ConvertStringSidToSidW(a3, &hMem) )
  {
    v8 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &P);
    if ( v8 >= 0 )
    {
      v9 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid);
      if ( v9 >= 0 )
      {
        LengthSid = GetLengthSid(pSid);
        v11 = GetLengthSid(P) + LengthSid;
        v12 = GetLengthSid(hMem) + 32 + v11;
        v13 = (struct _ACL *)LocalAlloc(0x40u, v12);
        v4 = v13;
        v18 = v13;
        if ( v13 )
        {
          if ( InitializeAcl(v13, v12, 2u) )
          {
            if ( AddAccessAllowedAceEx(v4, 2u, 3u, 0x10000000u, pSid) )
            {
              if ( AddAccessAllowedAceEx(v4, 2u, 3u, 0x10000000u, hMem) )
              {
                if ( AddAccessAllowedAceEx(v4, 2u, 3u, 0x10000000u, P) )
                {
                  RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
                  RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v4, 0);
                  LastError = RegSetKeySecurity(a2, 0x80000004, SecurityDescriptor);
                  if ( LastError )
                  {
                    v6 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                    {
                      v7 = 48;
                      goto LABEL_5;
                    }
                  }
                  else
                  {
                    LastError = 0;
                  }
                }
                else
                {
                  LastError = GetLastError();
                  v6 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                  {
                    v7 = 47;
                    goto LABEL_5;
                  }
                }
              }
              else
              {
                LastError = GetLastError();
                v6 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                {
                  v7 = 46;
                  goto LABEL_5;
                }
              }
            }
            else
            {
              LastError = GetLastError();
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                v7 = 45;
                goto LABEL_5;
              }
            }
          }
          else
          {
            LastError = GetLastError();
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v7 = 44;
              goto LABEL_5;
            }
          }
        }
        else
        {
          LastError = GetLastError();
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v7 = 43;
            goto LABEL_5;
          }
        }
      }
      else
      {
        LastError = RtlNtStatusToDosError(v9);
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v7 = 42;
          goto LABEL_5;
        }
      }
    }
    else
    {
      LastError = RtlNtStatusToDosError(v8);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v7 = 41;
        goto LABEL_5;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v7 = 40;
LABEL_5:
      WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_0955e053d70b3b28b837838791dca877_Traceguids, (unsigned int)LastError);
    }
  }
  if ( v4 )
    LocalFree(v4);
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( pSid )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, pSid);
    pSid = 0;
  }
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180014974  mov     r11, rsp
0x180014977  mov     [r11+8], rbx
0x18001497b  push    rsi
0x18001497c  push    rdi
0x18001497d  push    r14
0x18001497f  sub     rsp, 0C0h
0x180014986  mov     rax, cs:__security_cookie
0x18001498d  xor     rax, rsp
0x180014990  mov     [rsp+0D8h+var_28], rax
0x180014998  mov     rsi, rdx
0x18001499b  xor     r14d, r14d
0x18001499e  mov     [r11-70h], r14
0x1800149a2  mov     [r11-68h], r14
0x1800149a6  mov     [r11-78h], r14
0x1800149aa  mov     edi, r14d
0x1800149ad  mov     [r11-60h], r14
0x1800149b1  mov     [r11-30h], r14d
0x1800149b5  mov     word ptr [r11-2Ch], 500h
0x1800149bc  xorps   xmm0, xmm0
0x1800149bf  xor     eax, eax
0x1800149c1  movups  xmmword ptr [r11-58h], xmm0
0x1800149c6  movups  xmmword ptr [r11-48h], xmm0
0x1800149cb  mov     [r11-38h], rax
0x1800149cf  lea     rdx, [r11-70h]; Sid
0x1800149d3  mov     rcx, r8; StringSid
0x1800149d6  call    cs:__imp_ConvertStringSidToSidW
0x1800149dc  test    eax, eax
0x1800149de  jnz     short loc_180014A25
0x1800149e0  call    cs:__imp_GetLastError
0x1800149e6  mov     ebx, eax
0x1800149e8  lea     rax, WPP_GLOBAL_Control
0x1800149ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149f6  cmp     rcx, rax
0x1800149f9  jz      loc_180014D41
0x1800149ff  test    byte ptr [rcx+1Ch], 4
0x180014a03  jz      loc_180014D41
0x180014a09  lea     edx, [r14+28h]
0x180014a0d  mov     r9d, ebx
0x180014a10  lea     r8, WPP_0955e053d70b3b28b837838791dca877_Traceguids
0x180014a17  mov     rcx, [rcx+10h]
0x180014a1b  call    WPP_SF_d
0x180014a20  jmp     loc_180014D41
0x180014a25  lea     rax, [rsp+0D8h+P]
0x180014a2a  mov     [rsp+0D8h+Sid], rax; Sid
0x180014a2f  mov     [rsp+0D8h+SubAuthority7], r14d; SubAuthority7
0x180014a34  mov     [rsp+0D8h+SubAuthority6], r14d; SubAuthority6
0x180014a39  mov     [rsp+0D8h+SubAuthority5], r14d; SubAuthority5
0x180014a3e  mov     [rsp+0D8h+SubAuthority4], r14d; SubAuthority4
0x180014a43  mov     [rsp+0D8h+SubAuthority3], r14d; SubAuthority3
0x180014a48  mov     [rsp+0D8h+SubAuthority2], r14d; SubAuthority2
0x180014a4d  xor     r9d, r9d; SubAuthority1
0x180014a50  lea     r8d, [r9+12h]; SubAuthority0
0x180014a54  mov     dl, 1; SubAuthorityCount
0x180014a56  lea     rcx, [rsp+0D8h+IdentifierAuthority]; IdentifierAuthority
0x180014a5e  call    cs:__imp_RtlAllocateAndInitializeSid
0x180014a64  test    eax, eax
0x180014a66  jns     short loc_180014A9D
0x180014a68  mov     ecx, eax; Status
0x180014a6a  call    cs:__imp_RtlNtStatusToDosError
0x180014a70  mov     ebx, eax
0x180014a72  lea     rax, WPP_GLOBAL_Control
0x180014a79  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a80  cmp     rcx, rax
0x180014a83  jz      loc_180014D41
0x180014a89  test    byte ptr [rcx+1Ch], 4
0x180014a8d  jz      loc_180014D41
0x180014a93  mov     edx, 29h ; ')'
0x180014a98  jmp     loc_180014A0D
0x180014a9d  lea     rax, [rsp+0D8h+pSid]
0x180014aa2  mov     [rsp+0D8h+Sid], rax; Sid
0x180014aa7  mov     [rsp+0D8h+SubAuthority7], r14d; SubAuthority7
0x180014aac  mov     [rsp+0D8h+SubAuthority6], r14d; SubAuthority6
0x180014ab1  mov     [rsp+0D8h+SubAuthority5], r14d; SubAuthority5
0x180014ab6  mov     [rsp+0D8h+SubAuthority4], r14d; SubAuthority4
0x180014abb  mov     [rsp+0D8h+SubAuthority3], r14d; SubAuthority3
0x180014ac0  mov     [rsp+0D8h+SubAuthority2], r14d; SubAuthority2
0x180014ac5  mov     r9d, 220h; SubAuthority1
0x180014acb  mov     r8d, 20h ; ' '; SubAuthority0
0x180014ad1  mov     dl, 2; SubAuthorityCount
0x180014ad3  lea     rcx, [rsp+0D8h+IdentifierAuthority]; IdentifierAuthority
0x180014adb  call    cs:__imp_RtlAllocateAndInitializeSid
0x180014ae1  test    eax, eax
0x180014ae3  jns     short loc_180014B1A
0x180014ae5  mov     ecx, eax; Status
0x180014ae7  call    cs:__imp_RtlNtStatusToDosError
0x180014aed  mov     ebx, eax
0x180014aef  lea     rax, WPP_GLOBAL_Control
0x180014af6  mov     rcx, cs:WPP_GLOBAL_Control
0x180014afd  cmp     rcx, rax
0x180014b00  jz      loc_180014D41
0x180014b06  test    byte ptr [rcx+1Ch], 4
0x180014b0a  jz      loc_180014D41
0x180014b10  mov     edx, 2Ah ; '*'
0x180014b15  jmp     loc_180014A0D
0x180014b1a  mov     rcx, [rsp+0D8h+pSid]; pSid
0x180014b1f  call    cs:__imp_GetLengthSid
0x180014b25  mov     ebx, eax
0x180014b27  mov     rcx, [rsp+0D8h+P]; pSid
0x180014b2c  call    cs:__imp_GetLengthSid
0x180014b32  add     ebx, eax
0x180014b34  mov     rcx, [rsp+0D8h+hMem]; pSid
0x180014b39  call    cs:__imp_GetLengthSid
0x180014b3f  add     eax, 20h ; ' '
0x180014b42  add     ebx, eax
0x180014b44  mov     edx, ebx; uBytes
0x180014b46  mov     ecx, 40h ; '@'; uFlags
0x180014b4b  call    cs:__imp_LocalAlloc
0x180014b51  mov     rdi, rax
0x180014b54  mov     [rsp+0D8h+var_60], rax
0x180014b59  test    rax, rax
0x180014b5c  jnz     short loc_180014B8F
0x180014b5e  call    cs:__imp_GetLastError
0x180014b64  mov     ebx, eax
0x180014b66  lea     rax, WPP_GLOBAL_Control
0x180014b6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b74  cmp     rcx, rax
0x180014b77  jz      loc_180014D41
0x180014b7d  test    byte ptr [rcx+1Ch], 4
0x180014b81  jz      loc_180014D41
0x180014b87  lea     edx, [rdi+2Bh]
0x180014b8a  jmp     loc_180014A0D
0x180014b8f  mov     r8d, 2; dwAclRevision
0x180014b95  mov     edx, ebx; nAclLength
0x180014b97  mov     rcx, rdi; pAcl
0x180014b9a  call    cs:__imp_InitializeAcl
0x180014ba0  test    eax, eax
0x180014ba2  jnz     short loc_180014BD7
0x180014ba4  call    cs:__imp_GetLastError
0x180014baa  mov     ebx, eax
0x180014bac  lea     rax, WPP_GLOBAL_Control
0x180014bb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180014bba  cmp     rcx, rax
0x180014bbd  jz      loc_180014D41
0x180014bc3  test    byte ptr [rcx+1Ch], 4
0x180014bc7  jz      loc_180014D41
0x180014bcd  mov     edx, 2Ch ; ','
0x180014bd2  jmp     loc_180014A0D
0x180014bd7  mov     rax, [rsp+0D8h+pSid]
0x180014bdc  mov     qword ptr [rsp+0D8h+SubAuthority2], rax; pSid
0x180014be1  mov     ebx, 10000000h
0x180014be6  mov     r9d, ebx; AccessMask
0x180014be9  mov     edx, 2; dwAceRevision
0x180014bee  lea     r8d, [rdx+1]; AceFlags
0x180014bf2  mov     rcx, rdi; pAcl
0x180014bf5  call    cs:__imp_AddAccessAllowedAceEx
0x180014bfb  test    eax, eax
0x180014bfd  jnz     short loc_180014C32
0x180014bff  call    cs:__imp_GetLastError
0x180014c05  mov     ebx, eax
0x180014c07  lea     rax, WPP_GLOBAL_Control
0x180014c0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c15  cmp     rcx, rax
0x180014c18  jz      loc_180014D41
0x180014c1e  test    byte ptr [rcx+1Ch], 4
0x180014c22  jz      loc_180014D41
0x180014c28  mov     edx, 2Dh ; '-'
0x180014c2d  jmp     loc_180014A0D
0x180014c32  mov     rax, [rsp+0D8h+hMem]
0x180014c37  mov     qword ptr [rsp+0D8h+SubAuthority2], rax; pSid
0x180014c3c  mov     r9d, ebx; AccessMask
0x180014c3f  mov     edx, 2; dwAceRevision
0x180014c44  lea     r8d, [rdx+1]; AceFlags
0x180014c48  mov     rcx, rdi; pAcl
0x180014c4b  call    cs:__imp_AddAccessAllowedAceEx
0x180014c51  test    eax, eax
0x180014c53  jnz     short loc_180014C88
0x180014c55  call    cs:__imp_GetLastError
0x180014c5b  mov     ebx, eax
0x180014c5d  lea     rax, WPP_GLOBAL_Control
0x180014c64  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c6b  cmp     rcx, rax
0x180014c6e  jz      loc_180014D41
0x180014c74  test    byte ptr [rcx+1Ch], 4
0x180014c78  jz      loc_180014D41
0x180014c7e  mov     edx, 2Eh ; '.'
0x180014c83  jmp     loc_180014A0D
0x180014c88  mov     rax, [rsp+0D8h+P]
0x180014c8d  mov     qword ptr [rsp+0D8h+SubAuthority2], rax; pSid
0x180014c92  mov     r9d, ebx; AccessMask
0x180014c95  mov     edx, 2; dwAceRevision
0x180014c9a  lea     r8d, [rdx+1]; AceFlags
0x180014c9e  mov     rcx, rdi; pAcl
0x180014ca1  call    cs:__imp_AddAccessAllowedAceEx
0x180014ca7  test    eax, eax
0x180014ca9  jnz     short loc_180014CD6
0x180014cab  call    cs:__imp_GetLastError
0x180014cb1  mov     ebx, eax
0x180014cb3  lea     rax, WPP_GLOBAL_Control
0x180014cba  mov     rcx, cs:WPP_GLOBAL_Control
0x180014cc1  cmp     rcx, rax
0x180014cc4  jz      short loc_180014D41
0x180014cc6  test    byte ptr [rcx+1Ch], 4
0x180014cca  jz      short loc_180014D41
0x180014ccc  mov     edx, 2Fh ; '/'
0x180014cd1  jmp     loc_180014A0D
0x180014cd6  mov     edx, 1; Revision
0x180014cdb  lea     rcx, [rsp+0D8h+SecurityDescriptor]; SecurityDescriptor
0x180014ce3  call    cs:__imp_RtlCreateSecurityDescriptor
0x180014ce9  xor     r9d, r9d; DaclDefaulted
0x180014cec  mov     r8, rdi; Dacl
0x180014cef  mov     dl, 1; DaclPresent
0x180014cf1  lea     rcx, [rsp+0D8h+SecurityDescriptor]; SecurityDescriptor
0x180014cf9  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180014cff  lea     r8, [rsp+0D8h+SecurityDescriptor]; pSecurityDescriptor
0x180014d07  mov     edx, 80000004h; SecurityInformation
0x180014d0c  mov     rcx, rsi; hKey
0x180014d0f  call    cs:__imp_RegSetKeySecurity
0x180014d15  mov     ebx, eax
0x180014d17  test    eax, eax
0x180014d19  jz      short loc_180014D3E
0x180014d1b  lea     rax, WPP_GLOBAL_Control
0x180014d22  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d29  cmp     rcx, rax
0x180014d2c  jz      short loc_180014D41
0x180014d2e  test    byte ptr [rcx+1Ch], 4
0x180014d32  jz      short loc_180014D41
0x180014d34  mov     edx, 30h ; '0'
0x180014d39  jmp     loc_180014A0D
0x180014d3e  mov     ebx, r14d
0x180014d41  test    rdi, rdi
0x180014d44  jz      short loc_180014D4F
0x180014d46  mov     rcx, rdi; hMem
0x180014d49  call    cs:__imp_LocalFree
0x180014d4f  mov     rcx, [rsp+0D8h+hMem]; hMem
0x180014d54  test    rcx, rcx
0x180014d57  jz      short loc_180014D64
0x180014d59  call    cs:__imp_LocalFree
0x180014d5f  mov     [rsp+0D8h+hMem], r14
0x180014d64  cmp     [rsp+0D8h+pSid], r14
0x180014d69  jz      short loc_180014D8A
0x180014d6b  mov     rcx, gs:60h
0x180014d74  mov     r8, [rsp+0D8h+pSid]; P
0x180014d79  xor     edx, edx; Flags
0x180014d7b  mov     rcx, [rcx+30h]; HeapHandle
0x180014d7f  call    cs:__imp_RtlFreeHeap
0x180014d85  mov     [rsp+0D8h+pSid], r14
0x180014d8a  cmp     [rsp+0D8h+P], r14
0x180014d8f  jz      short loc_180014DAB
0x180014d91  mov     rcx, gs:60h
0x180014d9a  mov     r8, [rsp+0D8h+P]; P
0x180014d9f  xor     edx, edx; Flags
0x180014da1  mov     rcx, [rcx+30h]; HeapHandle
0x180014da5  call    cs:__imp_RtlFreeHeap
0x180014dab  test    ebx, ebx
0x180014dad  jle     short loc_180014DB8
0x180014daf  movzx   ebx, bx
0x180014db2  or      ebx, 80070000h
0x180014db8  mov     eax, ebx
0x180014dba  mov     rcx, [rsp+0D8h+var_28]
0x180014dc2  xor     rcx, rsp; StackCookie
0x180014dc5  call    __security_check_cookie
0x180014dca  mov     rbx, [rsp+0D8h+arg_0]
0x180014dd2  add     rsp, 0C0h
0x180014dd9  pop     r14
0x180014ddb  pop     rdi
0x180014ddc  pop     rsi
0x180014ddd  retn
0x180019f3b  push    rbp
0x180019f3d  sub     rsp, 60h
0x180019f41  mov     rbp, rdx
0x180019f44  mov     rcx, [rbp+78h]; hMem
0x180019f48  test    rcx, rcx
0x180019f4b  jz      short loc_180019F5B
0x180019f4d  call    cs:__imp_LocalFree
0x180019f53  mov     qword ptr [rbp+78h], 0
0x180019f5b  mov     rcx, [rbp+68h]; hMem
0x180019f5f  test    rcx, rcx
0x180019f62  jz      short loc_180019F72
0x180019f64  call    cs:__imp_LocalFree
0x180019f6a  mov     qword ptr [rbp+68h], 0
0x180019f72  cmp     qword ptr [rbp+60h], 0
0x180019f77  jz      short loc_180019F9A
0x180019f79  mov     rcx, gs:60h
0x180019f82  mov     r8, [rbp+60h]; P
0x180019f86  xor     edx, edx; Flags
0x180019f88  mov     rcx, [rcx+30h]; HeapHandle
0x180019f8c  call    cs:__imp_RtlFreeHeap
0x180019f92  mov     qword ptr [rbp+60h], 0
0x180019f9a  cmp     qword ptr [rbp+70h], 0
0x180019f9f  jz      short loc_180019FBB
0x180019fa1  mov     rcx, gs:60h
0x180019faa  mov     r8, [rbp+70h]; P
0x180019fae  xor     edx, edx; Flags
0x180019fb0  mov     rcx, [rcx+30h]; HeapHandle
0x180019fb4  call    cs:__imp_RtlFreeHeap
0x180019fba  nop
0x180019fbb  add     rsp, 60h
0x180019fbf  pop     rbp
0x180019fc0  retn
```
