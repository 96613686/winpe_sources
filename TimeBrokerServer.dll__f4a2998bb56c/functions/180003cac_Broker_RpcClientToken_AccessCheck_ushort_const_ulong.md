# Broker::RpcClientToken::AccessCheck(ushort const *,ulong)

- ea: `0x180003cac`
- end: `0x180003ea4`
- name: `?AccessCheck@RpcClientToken@Broker@@QEAAXPEBGK@Z`
- size: `504`
- prototype: `void __fastcall(HANDLE *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004274`

## callees

- `0x180003800`
- `0x180003cac`
- `0x180003eac`
- `0x18001181c`
- `0x180012dd0`
- `0x180013978`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180003d64`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180003d64`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180003d25`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180003d25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003e7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003e7e`

## pseudocode

```c
void __fastcall Broker::RpcClientToken::AccessCheck(HANDLE *this, const unsigned __int16 *a2)
{
  DWORD AccessMask[4]; // [rsp+40h] [rbp-C0h] BYREF
  WINBOOL AccessStatus; // [rsp+50h] [rbp-B0h] BYREF
  DWORD GrantedAccess; // [rsp+54h] [rbp-ACh] BYREF
  DWORD PrivilegeSetLength; // [rsp+58h] [rbp-A8h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  void **v8; // [rsp+68h] [rbp-98h] BYREF
  __int128 v9; // [rsp+70h] [rbp-90h]
  int v10; // [rsp+80h] [rbp-80h]
  unsigned int v11; // [rsp+88h] [rbp-78h]
  _BYTE pExceptionObject[32]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v13; // [rsp+B0h] [rbp-50h]
  _GENERIC_MAPPING GenericMapping; // [rsp+B8h] [rbp-48h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+D0h] [rbp-30h] BYREF

  AccessMask[0] = 0x80000000;
  Broker::StringSecurityDescriptor::StringSecurityDescriptor(&pSecurityDescriptor, L"O:SYG:SYD:(A;;GR;;;SY)");
  GrantedAccess = 0;
  AccessStatus = 0;
  PrivilegeSetLength = 256;
  GenericMapping.GenericRead = 0x20000;
  GenericMapping.GenericWrite = 0x20000;
  GenericMapping.GenericExecute = 0x20000;
  GenericMapping.GenericAll = 2031616;
  MapGenericMask(AccessMask, &GenericMapping);
  if ( !AccessCheck(
          pSecurityDescriptor,
          this[1],
          AccessMask[0],
          &GenericMapping,
          &PrivilegeSet,
          &PrivilegeSetLength,
          &GrantedAccess,
          &AccessStatus) )
  {
    Broker::Win32Error::Win32Error((Broker::Win32Error *)&v8);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v11);
    Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject);
    throw (Broker::Win32Error *)pExceptionObject;
  }
  if ( !AccessStatus )
  {
    Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v13);
    Broker::Win32Error::Win32Error((Broker::Win32Error *)&v8);
    throw (Broker::Win32Error *)&v8;
  }
  if ( GrantedAccess != AccessMask[0] )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, GrantedAccess);
    v9 = 0;
    v10 = 5;
    v8 = &Broker::AccessDenied::`vftable';
    throw (Broker::AccessDenied *)&v8;
  }
  LocalFree(pSecurityDescriptor);
}

```

## disassembly

```asm
0x180003cac  mov     [rsp-8+arg_8], rbx
0x180003cb1  push    rbp
0x180003cb2  lea     rbp, [rsp-0E0h]
0x180003cba  sub     rsp, 1E0h
0x180003cc1  mov     rax, cs:__security_cookie
0x180003cc8  xor     rax, rsp
0x180003ccb  mov     [rbp+0E0h+var_10], rax
0x180003cd2  mov     rbx, rcx
0x180003cd5  mov     [rsp+1E0h+AccessMask], 80000000h
0x180003cdd  lea     rdx, StringSecurityDescriptor; "O:SYG:SYD:(A;;GR;;;SY)"
0x180003ce4  lea     rcx, [rsp+1E0h+pSecurityDescriptor]; SecurityDescriptor
0x180003ce9  call    ??0StringSecurityDescriptor@Broker@@QEAA@PEBG@Z; Broker::StringSecurityDescriptor::StringSecurityDescriptor(ushort const *)
0x180003cee  nop
0x180003cef  mov     [rsp+1E0h+var_18C], 0
0x180003cf7  mov     [rsp+1E0h+var_190], 0
0x180003cff  mov     [rsp+1E0h+var_188], 100h
0x180003d07  mov     eax, 20000h
0x180003d0c  mov     [rbp+0E0h+GenericMapping.GenericRead], eax
0x180003d0f  mov     [rbp+0E0h+GenericMapping.GenericWrite], eax
0x180003d12  mov     [rbp+0E0h+GenericMapping.GenericExecute], eax
0x180003d15  mov     [rbp+0E0h+GenericMapping.GenericAll], 1F0000h
0x180003d1c  lea     rdx, [rbp+0E0h+GenericMapping]; GenericMapping
0x180003d20  lea     rcx, [rsp+1E0h+AccessMask]; AccessMask
0x180003d25  call    cs:__imp_MapGenericMask
0x180003d2b  lea     rax, [rsp+1E0h+var_190]
0x180003d30  mov     [rsp+1E0h+AccessStatus], rax; AccessStatus
0x180003d35  lea     rax, [rsp+1E0h+var_18C]
0x180003d3a  mov     [rsp+1E0h+GrantedAccess], rax; GrantedAccess
0x180003d3f  lea     rax, [rsp+1E0h+var_188]
0x180003d44  mov     [rsp+1E0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180003d49  lea     rax, [rbp+0E0h+var_110]
0x180003d4d  mov     [rsp+1E0h+PrivilegeSet], rax; PrivilegeSet
0x180003d52  lea     r9, [rbp+0E0h+GenericMapping]; GenericMapping
0x180003d56  mov     r8d, [rsp+1E0h+AccessMask]; DesiredAccess
0x180003d5b  mov     rdx, [rbx+8]; ClientToken
0x180003d5f  mov     rcx, [rsp+1E0h+pSecurityDescriptor]; pSecurityDescriptor
0x180003d64  call    cs:__imp_AccessCheck
0x180003d6a  test    eax, eax
0x180003d6c  jnz     short loc_180003DBF
0x180003d6e  lea     rcx, [rsp+1E0h+var_178]; this
0x180003d73  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x180003d78  nop
0x180003d79  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d80  test    byte ptr [rcx+1Ch], 8
0x180003d84  jz      short loc_180003DA5
0x180003d86  cmp     byte ptr [rcx+19h], 2
0x180003d8a  jb      short loc_180003DA5
0x180003d8c  mov     edx, 18h
0x180003d91  mov     r9d, [rbp+0E0h+var_158]
0x180003d95  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180003d9c  mov     rcx, [rcx+10h]
0x180003da0  call    WPP_SF_d
0x180003da5  lea     rcx, [rbp+0E0h+pExceptionObject]; this
0x180003da9  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x180003dae  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180003db5  lea     rcx, [rbp+0E0h+pExceptionObject]; pExceptionObject
0x180003db9  call    _CxxThrowException_0
0x180003dbf  cmp     [rsp+1E0h+var_190], 0
0x180003dc4  jnz     short loc_180003E18
0x180003dc6  lea     rcx, [rbp+0E0h+pExceptionObject]; this
0x180003dca  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x180003dcf  nop
0x180003dd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180003dd7  test    byte ptr [rcx+1Ch], 8
0x180003ddb  jz      short loc_180003DFC
0x180003ddd  cmp     byte ptr [rcx+19h], 2
0x180003de1  jb      short loc_180003DFC
0x180003de3  mov     edx, 19h
0x180003de8  mov     r9d, [rbp+0E0h+var_130]
0x180003dec  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180003df3  mov     rcx, [rcx+10h]
0x180003df7  call    WPP_SF_d
0x180003dfc  lea     rcx, [rsp+1E0h+var_178]; this
0x180003e01  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x180003e06  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180003e0d  lea     rcx, [rsp+1E0h+var_178]; pExceptionObject
0x180003e12  call    _CxxThrowException_0
0x180003e18  mov     r9d, [rsp+1E0h+var_18C]
0x180003e1d  cmp     r9d, [rsp+1E0h+AccessMask]
0x180003e22  jz      short loc_180003E79
0x180003e24  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e2b  test    byte ptr [rcx+1Ch], 8
0x180003e2f  jz      short loc_180003E4C
0x180003e31  cmp     byte ptr [rcx+19h], 2
0x180003e35  jb      short loc_180003E4C
0x180003e37  mov     edx, 1Ah
0x180003e3c  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180003e43  mov     rcx, [rcx+10h]
0x180003e47  call    WPP_SF_d
0x180003e4c  xorps   xmm0, xmm0
0x180003e4f  movups  [rsp+1E0h+var_170], xmm0
0x180003e54  mov     [rbp+0E0h+var_160], 5
0x180003e5b  lea     rax, ??_7AccessDenied@Broker@@6B@; const Broker::AccessDenied::`vftable'
0x180003e62  mov     [rsp+1E0h+var_178], rax
0x180003e67  lea     rdx, _TI3?AUAccessDenied@Broker@@; pThrowInfo
0x180003e6e  lea     rcx, [rsp+1E0h+var_178]; pExceptionObject
0x180003e73  call    _CxxThrowException_0
0x180003e79  mov     rcx, [rsp+1E0h+pSecurityDescriptor]; hMem
0x180003e7e  call    cs:__imp_LocalFree
0x180003e84  mov     rcx, [rbp+0E0h+var_10]
0x180003e8b  xor     rcx, rsp; StackCookie
0x180003e8e  call    __security_check_cookie
0x180003e93  mov     rbx, [rsp+1E0h+arg_8]
0x180003e9b  add     rsp, 1E0h
0x180003ea2  pop     rbp
0x180003ea3  retn
```
