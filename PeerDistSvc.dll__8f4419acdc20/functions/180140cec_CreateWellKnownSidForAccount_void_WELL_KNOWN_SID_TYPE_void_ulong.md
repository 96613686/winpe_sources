# CreateWellKnownSidForAccount(void *,WELL_KNOWN_SID_TYPE,void *,ulong *)

- ea: `0x180140cec`
- end: `0x180140f59`
- name: `?CreateWellKnownSidForAccount@@YAJPEAXW4WELL_KNOWN_SID_TYPE@@0PEAK@Z`
- size: `621`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, enum WELL_KNOWN_SID_TYPE, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180140f60`

## callees

- `0x1800024f0`
- `0x1800024fc`
- `0x180008290`
- `0x180140cec`
- `0x180144882`
- `0x1801448c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180140d58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180140df4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180140e6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180140eae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180140ed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180140f0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180140d58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180140df4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180140e6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180140eae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180140ed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180140f0c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180140ecb`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180140ecb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180140d4e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180140dea`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180140d4e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180140dea`
- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x180140e61`
- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x180140e61`

## pseudocode

```c
__int64 __fastcall CreateWellKnownSidForAccount(
        HANDLE TokenHandle,
        enum WELL_KNOWN_SID_TYPE a2,
        void *a3,
        unsigned int *a4)
{
  DWORD LastError; // ebx
  PSID *v8; // rdi
  signed int v9; // eax
  signed int v10; // eax
  DWORD v11; // eax
  __int64 v12; // rdx
  signed int v13; // eax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-268h] BYREF
  DWORD cbDomainSid[3]; // [rsp+34h] [rbp-264h] BYREF
  _BYTE pDomainSid[544]; // [rsp+40h] [rbp-258h] BYREF

  TokenInformationLength = 0;
  memset_0(pDomainSid, 0, sizeof(pDomainSid));
  cbDomainSid[0] = 68;
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    LastError = GetLastError();
    if ( LastError != 122 )
    {
      v8 = 0;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 44, WPP_b3b735cb11f534e0475daff91a8d2871_Traceguids, LastError);
      }
      if ( (int)LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_33;
    }
  }
  v8 = (PSID *)operator new[](TokenInformationLength);
  if ( !v8 )
  {
    LastError = -2147024882;
    goto LABEL_33;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, v8, TokenInformationLength, &TokenInformationLength) )
  {
    v9 = GetLastError();
    LastError = v9;
    if ( v9 > 0 )
      LastError = (unsigned __int16)v9 | 0x80070000;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 45, WPP_b3b735cb11f534e0475daff91a8d2871_Traceguids, LastError);
    }
    goto LABEL_33;
  }
  if ( GetWindowsAccountDomainSid(*v8, pDomainSid, cbDomainSid) )
  {
    LastError = 0;
    if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, pDomainSid, a3, a4) )
    {
      v13 = GetLastError();
      LastError = v13;
      if ( v13 > 0 )
        LastError = (unsigned __int16)v13 | 0x80070000;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v11 = GetLastError();
        v12 = 47;
        goto LABEL_32;
      }
    }
  }
  else
  {
    v10 = GetLastError();
    LastError = v10;
    if ( v10 > 0 )
      LastError = (unsigned __int16)v10 | 0x80070000;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v11 = GetLastError();
      v12 = 46;
LABEL_32:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), v12, WPP_b3b735cb11f534e0475daff91a8d2871_Traceguids, v11);
    }
  }
LABEL_33:
  operator delete(v8);
  return LastError;
}

```

## disassembly

```asm
0x180140cec  push    rbx
0x180140cee  push    rbp
0x180140cef  push    rsi
0x180140cf0  push    rdi
0x180140cf1  push    r14
0x180140cf3  sub     rsp, 270h
0x180140cfa  mov     rax, cs:__security_cookie
0x180140d01  xor     rax, rsp
0x180140d04  mov     [rsp+298h+var_38], rax
0x180140d0c  mov     rbp, r8
0x180140d0f  mov     [rsp+298h+TokenInformationLength], 0
0x180140d17  mov     rsi, rcx
0x180140d1a  mov     r8d, 220h; Size
0x180140d20  lea     rcx, [rsp+298h+pDomainSid]; void *
0x180140d25  xor     edx, edx; Val
0x180140d27  mov     r14, r9
0x180140d2a  call    memset_0
0x180140d2f  xor     r9d, r9d; TokenInformationLength
0x180140d32  mov     [rsp+298h+cbDomainSid], 44h ; 'D'
0x180140d3a  lea     rax, [rsp+298h+TokenInformationLength]
0x180140d3f  xor     r8d, r8d; TokenInformation
0x180140d42  mov     rcx, rsi; TokenHandle
0x180140d45  mov     [rsp+298h+ReturnLength], rax; ReturnLength
0x180140d4a  lea     edx, [r9+1]; TokenInformationClass
0x180140d4e  call    cs:__imp_GetTokenInformation
0x180140d54  test    eax, eax
0x180140d56  jnz     short loc_180140DB5
0x180140d58  call    cs:__imp_GetLastError
0x180140d5e  mov     ebx, eax
0x180140d60  cmp     eax, 7Ah ; 'z'
0x180140d63  jz      short loc_180140DB5
0x180140d65  xor     edi, edi
0x180140d67  mov     rcx, cs:WPP_GLOBAL_Control
0x180140d6e  lea     rax, WPP_GLOBAL_Control
0x180140d75  cmp     rcx, rax
0x180140d78  jz      short loc_180140D9F
0x180140d7a  test    dword ptr [rcx+6Ch], 8000h
0x180140d81  jz      short loc_180140D9F
0x180140d83  cmp     byte ptr [rcx+69h], 1
0x180140d87  jb      short loc_180140D9F
0x180140d89  mov     rcx, [rcx+60h]
0x180140d8d  lea     edx, [rdi+2Ch]
0x180140d90  mov     r9d, ebx
0x180140d93  lea     r8, WPP_b3b735cb11f534e0475daff91a8d2871_Traceguids
0x180140d9a  call    WPP_SF_d
0x180140d9f  test    ebx, ebx
0x180140da1  jle     loc_180140F31
0x180140da7  movzx   ebx, bx
0x180140daa  or      ebx, 80070000h
0x180140db0  jmp     loc_180140F31
0x180140db5  mov     ecx, [rsp+298h+TokenInformationLength]; unsigned __int64
0x180140db9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180140dbe  mov     rdi, rax
0x180140dc1  test    rax, rax
0x180140dc4  jnz     short loc_180140DD0
0x180140dc6  mov     ebx, 8007000Eh
0x180140dcb  jmp     loc_180140F31
0x180140dd0  mov     r9d, [rsp+298h+TokenInformationLength]; TokenInformationLength
0x180140dd5  lea     rax, [rsp+298h+TokenInformationLength]
0x180140dda  mov     r8, rdi; TokenInformation
0x180140ddd  mov     [rsp+298h+ReturnLength], rax; ReturnLength
0x180140de2  mov     edx, 1; TokenInformationClass
0x180140de7  mov     rcx, rsi; TokenHandle
0x180140dea  call    cs:__imp_GetTokenInformation
0x180140df0  test    eax, eax
0x180140df2  jnz     short loc_180140E54
0x180140df4  call    cs:__imp_GetLastError
0x180140dfa  mov     ebx, eax
0x180140dfc  test    eax, eax
0x180140dfe  jle     short loc_180140E09
0x180140e00  movzx   ebx, ax
0x180140e03  or      ebx, 80070000h
0x180140e09  mov     rcx, cs:WPP_GLOBAL_Control
0x180140e10  lea     rax, WPP_GLOBAL_Control
0x180140e17  cmp     rcx, rax
0x180140e1a  jz      loc_180140F31
0x180140e20  test    dword ptr [rcx+6Ch], 8000h
0x180140e27  jz      loc_180140F31
0x180140e2d  cmp     byte ptr [rcx+69h], 1
0x180140e31  jb      loc_180140F31
0x180140e37  mov     rcx, [rcx+60h]
0x180140e3b  lea     r8, WPP_b3b735cb11f534e0475daff91a8d2871_Traceguids
0x180140e42  mov     edx, 2Dh ; '-'
0x180140e47  mov     r9d, ebx
0x180140e4a  call    WPP_SF_d
0x180140e4f  jmp     loc_180140F31
0x180140e54  mov     rcx, [rdi]; pSid
0x180140e57  lea     r8, [rsp+298h+cbDomainSid]; cbDomainSid
0x180140e5c  lea     rdx, [rsp+298h+pDomainSid]; pDomainSid
0x180140e61  call    cs:__imp_GetWindowsAccountDomainSid
0x180140e67  test    eax, eax
0x180140e69  jnz     short loc_180140EBB
0x180140e6b  call    cs:__imp_GetLastError
0x180140e71  mov     ebx, eax
0x180140e73  test    eax, eax
0x180140e75  jle     short loc_180140E80
0x180140e77  movzx   ebx, ax
0x180140e7a  or      ebx, 80070000h
0x180140e80  mov     rcx, cs:WPP_GLOBAL_Control
0x180140e87  lea     rax, WPP_GLOBAL_Control
0x180140e8e  cmp     rcx, rax
0x180140e91  jz      loc_180140F31
0x180140e97  test    dword ptr [rcx+6Ch], 8000h
0x180140e9e  jz      loc_180140F31
0x180140ea4  cmp     byte ptr [rcx+69h], 1
0x180140ea8  jb      loc_180140F31
0x180140eae  call    cs:__imp_GetLastError
0x180140eb4  mov     edx, 2Eh ; '.'
0x180140eb9  jmp     short loc_180140F17
0x180140ebb  xor     ebx, ebx
0x180140ebd  lea     rdx, [rsp+298h+pDomainSid]; DomainSid
0x180140ec2  mov     r9, r14; cbSid
0x180140ec5  mov     r8, rbp; pSid
0x180140ec8  lea     ecx, [rbx+1Ah]; WellKnownSidType
0x180140ecb  call    cs:__imp_CreateWellKnownSid
0x180140ed1  test    eax, eax
0x180140ed3  jnz     short loc_180140F31
0x180140ed5  call    cs:__imp_GetLastError
0x180140edb  mov     ebx, eax
0x180140edd  test    eax, eax
0x180140edf  jle     short loc_180140EEA
0x180140ee1  movzx   ebx, ax
0x180140ee4  or      ebx, 80070000h
0x180140eea  mov     rcx, cs:WPP_GLOBAL_Control
0x180140ef1  lea     rax, WPP_GLOBAL_Control
0x180140ef8  cmp     rcx, rax
0x180140efb  jz      short loc_180140F31
0x180140efd  test    dword ptr [rcx+6Ch], 8000h
0x180140f04  jz      short loc_180140F31
0x180140f06  cmp     byte ptr [rcx+69h], 1
0x180140f0a  jb      short loc_180140F31
0x180140f0c  call    cs:__imp_GetLastError
0x180140f12  mov     edx, 2Fh ; '/'
0x180140f17  mov     rcx, cs:WPP_GLOBAL_Control
0x180140f1e  lea     r8, WPP_b3b735cb11f534e0475daff91a8d2871_Traceguids
0x180140f25  mov     r9d, eax
0x180140f28  mov     rcx, [rcx+60h]
0x180140f2c  call    WPP_SF_d
0x180140f31  mov     rcx, rdi; Block
0x180140f34  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180140f39  mov     eax, ebx
0x180140f3b  mov     rcx, [rsp+298h+var_38]
0x180140f43  xor     rcx, rsp; StackCookie
0x180140f46  call    __security_check_cookie
0x180140f4b  add     rsp, 270h
0x180140f52  pop     r14
0x180140f54  pop     rdi
0x180140f55  pop     rsi
0x180140f56  pop     rbp
0x180140f57  pop     rbx
0x180140f58  retn
```
