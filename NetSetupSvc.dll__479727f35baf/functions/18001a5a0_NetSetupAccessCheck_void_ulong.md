# NetSetupAccessCheck(void *,ulong)

- ea: `0x18001a5a0`
- end: `0x18001a70d`
- name: `?NetSetupAccessCheck@@YAXPEAXK@Z`
- size: `365`
- prototype: `void __fastcall(HANDLE ClientToken, DWORD)`
- caller_count: `7`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001088c`
- `0x180010930`
- `0x1800109a8`
- `0x180010a50`
- `0x180010ae0`
- `0x180012658`
- `0x180012714`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x1800078f8`
- `0x180008854`
- `0x18001a5a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a633`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a633`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18001a5d1`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18001a5d1`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18001a629`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18001a629`

## pseudocode

```c
void __fastcall NetSetupAccessCheck(HANDLE ClientToken, DWORD a2)
{
  signed int LastError; // ebx
  _BYTE pExceptionObject[208]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD AccessMask; // [rsp+110h] [rbp+10h] BYREF
  WINBOOL AccessStatus; // [rsp+118h] [rbp+18h] BYREF
  DWORD GrantedAccess; // [rsp+11Ch] [rbp+1Ch] BYREF
  DWORD PrivilegeSetLength; // [rsp+120h] [rbp+20h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+128h] [rbp+28h] BYREF

  AccessMask = a2;
  MapGenericMask(&AccessMask, (PGENERIC_MAPPING)&GenericMapping);
  PrivilegeSetLength = 20;
  GrantedAccess = 0;
  AccessStatus = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  if ( !AccessCheck(
          qword_18003E470,
          ClientToken,
          AccessMask,
          (PGENERIC_MAPPING)&GenericMapping,
          &PrivilegeSet,
          &PrivilegeSetLength,
          &GrantedAccess,
          &AccessStatus) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_ed900848e5123e61f3bb69b3da2f293f_Traceguids,
        (unsigned int)LastError);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    HResultException::HResultException((HResultException *)pExceptionObject, LastError);
    throw (HResultException *)pExceptionObject;
  }
  if ( !AccessStatus )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ed900848e5123e61f3bb69b3da2f293f_Traceguids, AccessMask);
    HResultException::HResultException((HResultException *)pExceptionObject, -2147024891);
    throw (HResultException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x18001a5a0  mov     [rsp-8+arg_10], rbx
0x18001a5a5  push    rbp
0x18001a5a6  lea     rbp, [rsp-50h]
0x18001a5ab  sub     rsp, 150h
0x18001a5b2  mov     rax, cs:__security_cookie
0x18001a5b9  xor     rax, rsp
0x18001a5bc  mov     [rbp+50h+var_10], rax
0x18001a5c0  mov     rbx, rcx
0x18001a5c3  mov     [rbp+50h+AccessMask], edx
0x18001a5c6  lea     rdx, GenericMapping; GenericMapping
0x18001a5cd  lea     rcx, [rbp+50h+AccessMask]; AccessMask
0x18001a5d1  call    cs:__imp_MapGenericMask
0x18001a5d7  mov     r8d, [rbp+50h+AccessMask]; DesiredAccess
0x18001a5db  lea     r9, GenericMapping; GenericMapping
0x18001a5e2  xor     eax, eax
0x18001a5e4  mov     [rbp+50h+var_30], 14h
0x18001a5eb  mov     [rbp+50h+var_28.Privilege.Attributes], eax
0x18001a5ee  lea     rcx, qword_18003E470; pSecurityDescriptor
0x18001a5f5  mov     [rbp+50h+var_34], eax
0x18001a5f8  xorps   xmm0, xmm0
0x18001a5fb  mov     [rbp+50h+var_38], eax
0x18001a5fe  mov     rdx, rbx; ClientToken
0x18001a601  lea     rax, [rbp+50h+var_38]
0x18001a605  mov     [rsp+150h+AccessStatus], rax; AccessStatus
0x18001a60a  lea     rax, [rbp+50h+var_34]
0x18001a60e  mov     [rsp+150h+GrantedAccess], rax; GrantedAccess
0x18001a613  lea     rax, [rbp+50h+var_30]
0x18001a617  mov     [rsp+150h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18001a61c  lea     rax, [rbp+50h+var_28]
0x18001a620  mov     [rsp+150h+PrivilegeSet], rax; PrivilegeSet
0x18001a625  movups  xmmword ptr [rbp+50h+var_28.PrivilegeCount], xmm0
0x18001a629  call    cs:__imp_AccessCheck
0x18001a62f  test    eax, eax
0x18001a631  jnz     short loc_18001A697
0x18001a633  call    cs:__imp_GetLastError
0x18001a639  mov     ebx, eax
0x18001a63b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a642  lea     rax, WPP_GLOBAL_Control
0x18001a649  cmp     rcx, rax
0x18001a64c  jz      short loc_18001A66C
0x18001a64e  cmp     byte ptr [rcx+19h], 2
0x18001a652  jb      short loc_18001A66C
0x18001a654  mov     rcx, [rcx+10h]
0x18001a658  lea     r8, WPP_ed900848e5123e61f3bb69b3da2f293f_Traceguids
0x18001a65f  mov     edx, 0Ah
0x18001a664  mov     r9d, ebx
0x18001a667  call    WPP_SF_d
0x18001a66c  test    ebx, ebx
0x18001a66e  jle     short loc_18001A679
0x18001a670  movzx   ebx, bx
0x18001a673  or      ebx, 80070000h
0x18001a679  mov     edx, ebx; int
0x18001a67b  lea     rcx, [rsp+150h+pExceptionObject]; this
0x18001a680  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18001a685  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18001a68c  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x18001a691  call    _CxxThrowException_0
0x18001a697  cmp     [rbp+50h+var_38], 0
0x18001a69b  jnz     short loc_18001A6F0
0x18001a69d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6a4  lea     rax, WPP_GLOBAL_Control
0x18001a6ab  cmp     rcx, rax
0x18001a6ae  jz      short loc_18001A6CF
0x18001a6b0  cmp     byte ptr [rcx+19h], 2
0x18001a6b4  jb      short loc_18001A6CF
0x18001a6b6  mov     r9d, [rbp+50h+AccessMask]
0x18001a6ba  lea     r8, WPP_ed900848e5123e61f3bb69b3da2f293f_Traceguids
0x18001a6c1  mov     rcx, [rcx+10h]
0x18001a6c5  mov     edx, 0Bh
0x18001a6ca  call    WPP_SF_d
0x18001a6cf  mov     edx, 80070005h; int
0x18001a6d4  lea     rcx, [rsp+150h+pExceptionObject]; this
0x18001a6d9  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18001a6de  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18001a6e5  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x18001a6ea  call    _CxxThrowException_0
0x18001a6f0  mov     rcx, [rbp+50h+var_10]
0x18001a6f4  xor     rcx, rsp; StackCookie
0x18001a6f7  call    __security_check_cookie
0x18001a6fc  mov     rbx, [rsp+150h+arg_10]
0x18001a704  add     rsp, 150h
0x18001a70b  pop     rbp
0x18001a70c  retn
```
