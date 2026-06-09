# Broker::RpcClientToken::AccessCheck(ushort const *,ulong)

- ea: `0x180002e20`
- end: `0x1800030cb`
- name: `?AccessCheck@RpcClientToken@Broker@@QEAAXPEBGK@Z`
- size: `683`
- prototype: `void __fastcall(HANDLE *this, const unsigned __int16 *, DWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001b78`
- `0x180002d10`
- `0x18001e150`

## callees

- `0x180002e20`
- `0x1800030e0`
- `0x18001732c`
- `0x1800195e0`
- `0x18001cf50`
- `0x18001d9ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f4b`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180002eaf`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180002eaf`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180002eee`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180002eee`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180002e6c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180002e6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002f7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002f7a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Broker::RpcClientToken::AccessCheck(HANDLE *this, const unsigned __int16 *a2, DWORD a3)
{
  DWORD LastError; // eax
  DWORD AccessMask[4]; // [rsp+40h] [rbp-C0h] BYREF
  WINBOOL AccessStatus; // [rsp+50h] [rbp-B0h] BYREF
  DWORD GrantedAccess; // [rsp+54h] [rbp-ACh] BYREF
  ULONG SecurityDescriptorSize; // [rsp+58h] [rbp-A8h] BYREF
  DWORD PrivilegeSetLength; // [rsp+5Ch] [rbp-A4h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  void **v11; // [rsp+68h] [rbp-98h] BYREF
  __int128 v12; // [rsp+70h] [rbp-90h]
  int v13; // [rsp+80h] [rbp-80h]
  DWORD v14; // [rsp+88h] [rbp-78h]
  void **pExceptionObject; // [rsp+90h] [rbp-70h] BYREF
  __int128 v16; // [rsp+98h] [rbp-68h]
  int v17; // [rsp+A8h] [rbp-58h]
  DWORD v18; // [rsp+B0h] [rbp-50h]
  _GENERIC_MAPPING GenericMapping; // [rsp+B8h] [rbp-48h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+D0h] [rbp-30h] BYREF

  AccessMask[0] = a3;
  SecurityDescriptorSize = 0;
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(a2, 1u, &SecurityDescriptor, &SecurityDescriptorSize) )
  {
    Broker::Win32Error::Win32Error((Broker::Win32Error *)&v11);
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_a9458e0debc7300a47110d600cc51ede_Traceguids, v14);
    std::exception::exception((std::exception *)&pExceptionObject, (const struct std::exception *)&v11);
    v17 = v13;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v18 = v14;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  GrantedAccess = 0;
  AccessStatus = 0;
  PrivilegeSetLength = 256;
  GenericMapping.GenericRead = 0x20000;
  GenericMapping.GenericWrite = 0x20000;
  GenericMapping.GenericExecute = 0x20000;
  GenericMapping.GenericAll = 2031616;
  MapGenericMask(AccessMask, &GenericMapping);
  if ( !AccessCheck(
          SecurityDescriptor,
          this[1],
          AccessMask[0],
          &GenericMapping,
          &PrivilegeSet,
          &PrivilegeSetLength,
          &GrantedAccess,
          &AccessStatus) )
  {
    Broker::Win32Error::Win32Error((Broker::Win32Error *)&pExceptionObject);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v18);
    Broker::Win32Error::Win32Error((Broker::Win32Error *)&v11);
    throw (Broker::Win32Error *)&v11;
  }
  if ( !AccessStatus )
  {
    v12 = 0;
    v13 = 1;
    v11 = &Broker::Win32Error::`vftable';
    LastError = GetLastError();
    v14 = LastError;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, LastError);
    v16 = 0;
    v17 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v18 = GetLastError();
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  if ( GrantedAccess != AccessMask[0] )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, GrantedAccess);
    v12 = 0;
    v13 = 5;
    v11 = &Broker::AccessDenied::`vftable';
    throw (Broker::AccessDenied *)&v11;
  }
  LocalFree(SecurityDescriptor);
}

```

## disassembly

```asm
0x180002e20  push    rbp
0x180002e22  push    rbx
0x180002e23  push    rdi
0x180002e24  lea     rbp, [rsp-0E0h]
0x180002e2c  sub     rsp, 1E0h
0x180002e33  mov     rax, cs:__security_cookie
0x180002e3a  xor     rax, rsp
0x180002e3d  mov     [rbp+0F0h+var_20], rax
0x180002e44  mov     rax, rdx
0x180002e47  mov     rbx, rcx
0x180002e4a  mov     [rsp+1F0h+AccessMask], r8d
0x180002e4f  xor     edi, edi
0x180002e51  mov     [rsp+1F0h+SecurityDescriptorSize], edi
0x180002e55  mov     [rsp+1F0h+SecurityDescriptor], rdi
0x180002e5a  lea     r9, [rsp+1F0h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180002e5f  lea     r8, [rsp+1F0h+SecurityDescriptor]; SecurityDescriptor
0x180002e64  mov     edx, 1; StringSDRevision
0x180002e69  mov     rcx, rax; StringSecurityDescriptor
0x180002e6c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180002e72  test    eax, eax
0x180002e74  jz      loc_180002FB4
0x180002e7a  mov     [rsp+1F0h+var_19C], edi
0x180002e7e  mov     [rsp+1F0h+var_1A0], edi
0x180002e82  mov     [rsp+1F0h+var_194], 100h
0x180002e8a  mov     [rbp+0F0h+GenericMapping.GenericRead], 20000h
0x180002e91  mov     [rbp+0F0h+GenericMapping.GenericWrite], 20000h
0x180002e98  mov     [rbp+0F0h+GenericMapping.GenericExecute], 20000h
0x180002e9f  mov     [rbp+0F0h+GenericMapping.GenericAll], 1F0000h
0x180002ea6  lea     rdx, [rbp+0F0h+GenericMapping]; GenericMapping
0x180002eaa  lea     rcx, [rsp+1F0h+AccessMask]; AccessMask
0x180002eaf  call    cs:__imp_MapGenericMask
0x180002eb5  lea     rax, [rsp+1F0h+var_1A0]
0x180002eba  mov     [rsp+1F0h+AccessStatus], rax; AccessStatus
0x180002ebf  lea     rax, [rsp+1F0h+var_19C]
0x180002ec4  mov     [rsp+1F0h+GrantedAccess], rax; GrantedAccess
0x180002ec9  lea     rax, [rsp+1F0h+var_194]
0x180002ece  mov     [rsp+1F0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180002ed3  lea     rax, [rbp+0F0h+var_120]
0x180002ed7  mov     [rsp+1F0h+PrivilegeSet], rax; PrivilegeSet
0x180002edc  lea     r9, [rbp+0F0h+GenericMapping]; GenericMapping
0x180002ee0  mov     r8d, [rsp+1F0h+AccessMask]; DesiredAccess
0x180002ee5  mov     rdx, [rbx+8]; ClientToken
0x180002ee9  mov     rcx, [rsp+1F0h+SecurityDescriptor]; pSecurityDescriptor
0x180002eee  call    cs:__imp_AccessCheck
0x180002ef4  test    eax, eax
0x180002ef6  jz      loc_180003024
0x180002efc  cmp     [rsp+1F0h+var_1A0], edi
0x180002f00  jnz     short loc_180002F65
0x180002f02  xorps   xmm0, xmm0
0x180002f05  movups  [rsp+1F0h+var_180], xmm0
0x180002f0a  mov     [rbp+0F0h+var_170], 1
0x180002f11  lea     rbx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180002f18  mov     [rsp+1F0h+var_188], rbx
0x180002f1d  call    cs:__imp_GetLastError
0x180002f23  mov     [rbp+0F0h+var_168], eax
0x180002f26  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f2d  test    byte ptr [rcx+1Ch], 8
0x180002f31  jz      short loc_180002F39
0x180002f33  cmp     byte ptr [rcx+19h], 2
0x180002f37  jnb     short loc_180002F9A
0x180002f39  xorps   xmm0, xmm0
0x180002f3c  movups  [rbp+0F0h+var_158], xmm0
0x180002f40  mov     [rbp+0F0h+var_148], 1
0x180002f47  mov     [rbp+0F0h+pExceptionObject], rbx
0x180002f4b  call    cs:__imp_GetLastError
0x180002f51  mov     [rbp+0F0h+var_140], eax
0x180002f54  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180002f5b  lea     rcx, [rbp+0F0h+pExceptionObject]; pExceptionObject
0x180002f5f  call    _CxxThrowException_0
0x180002f65  mov     r9d, [rsp+1F0h+var_19C]
0x180002f6a  cmp     r9d, [rsp+1F0h+AccessMask]
0x180002f6f  jnz     loc_180003076
0x180002f75  mov     rcx, [rsp+1F0h+SecurityDescriptor]; hMem
0x180002f7a  call    cs:__imp_LocalFree
0x180002f80  mov     rcx, [rbp+0F0h+var_20]
0x180002f87  xor     rcx, rsp; StackCookie
0x180002f8a  call    __security_check_cookie
0x180002f8f  add     rsp, 1E0h
0x180002f96  pop     rdi
0x180002f97  pop     rbx
0x180002f98  pop     rbp
0x180002f99  retn
0x180002f9a  mov     edx, 19h
0x180002f9f  mov     r9d, eax
0x180002fa2  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180002fa9  mov     rcx, [rcx+10h]
0x180002fad  call    WPP_SF_d
0x180002fb2  jmp     short loc_180002F39
0x180002fb4  lea     rcx, [rsp+1F0h+var_188]; this
0x180002fb9  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x180002fbe  nop
0x180002fbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fc6  test    dword ptr [rcx+1Ch], 400h
0x180002fcd  jz      short loc_180002FEE
0x180002fcf  cmp     byte ptr [rcx+19h], 2
0x180002fd3  jb      short loc_180002FEE
0x180002fd5  mov     edx, 0Ah
0x180002fda  mov     r9d, [rbp+0F0h+var_168]
0x180002fde  lea     r8, WPP_a9458e0debc7300a47110d600cc51ede_Traceguids
0x180002fe5  mov     rcx, [rcx+10h]
0x180002fe9  call    WPP_SF_d
0x180002fee  lea     rdx, [rsp+1F0h+var_188]; struct std::exception *
0x180002ff3  lea     rcx, [rbp+0F0h+pExceptionObject]; this
0x180002ff7  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x180002ffc  mov     eax, [rbp+0F0h+var_170]
0x180002fff  mov     [rbp+0F0h+var_148], eax
0x180003002  lea     rbx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180003009  mov     [rbp+0F0h+pExceptionObject], rbx
0x18000300d  mov     eax, [rbp+0F0h+var_168]
0x180003010  mov     [rbp+0F0h+var_140], eax
0x180003013  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000301a  lea     rcx, [rbp+0F0h+pExceptionObject]; pExceptionObject
0x18000301e  call    _CxxThrowException_0
0x180003024  lea     rcx, [rbp+0F0h+pExceptionObject]; this
0x180003028  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x18000302d  nop
0x18000302e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003035  test    byte ptr [rcx+1Ch], 8
0x180003039  jz      short loc_18000305A
0x18000303b  cmp     byte ptr [rcx+19h], 2
0x18000303f  jb      short loc_18000305A
0x180003041  mov     edx, 18h
0x180003046  mov     r9d, [rbp+0F0h+var_140]
0x18000304a  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180003051  mov     rcx, [rcx+10h]
0x180003055  call    WPP_SF_d
0x18000305a  lea     rcx, [rsp+1F0h+var_188]; this
0x18000305f  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x180003064  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000306b  lea     rcx, [rsp+1F0h+var_188]; pExceptionObject
0x180003070  call    _CxxThrowException_0
0x180003076  mov     rcx, cs:WPP_GLOBAL_Control
0x18000307d  test    byte ptr [rcx+1Ch], 8
0x180003081  jz      short loc_18000309E
0x180003083  cmp     byte ptr [rcx+19h], 2
0x180003087  jb      short loc_18000309E
0x180003089  mov     edx, 1Ah
0x18000308e  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180003095  mov     rcx, [rcx+10h]
0x180003099  call    WPP_SF_d
0x18000309e  xorps   xmm0, xmm0
0x1800030a1  movups  [rsp+1F0h+var_180], xmm0
0x1800030a6  mov     [rbp+0F0h+var_170], 5
0x1800030ad  lea     rax, ??_7AccessDenied@Broker@@6B@; const Broker::AccessDenied::`vftable'
0x1800030b4  mov     [rsp+1F0h+var_188], rax
0x1800030b9  lea     rdx, _TI3?AUAccessDenied@Broker@@; pThrowInfo
0x1800030c0  lea     rcx, [rsp+1F0h+var_188]; pExceptionObject
0x1800030c5  call    _CxxThrowException_0
```
