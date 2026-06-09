# CheckAccessAllowed

- ea: `0x180004f68`
- end: `0x18000530a`
- name: `CheckAccessAllowed`
- size: `930`
- prototype: `unsigned int __fastcall(__int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18000d3e0`

## callees

- `0x180001c0c`
- `0x1800031dc`
- `0x180004f68`
- `0x18000a3fc`
- `0x18000dbb4`
- `0x18000dbf4`
- `0x18000dc4c`
- `0x18000dca0`
- `0x18000de78`
- `0x18000f5f0`
- `0x180011010`

## import_xrefs

- `ADVAPI32!GetUserNameW` at `0x180004fbc`
- `ADVAPI32!GetUserNameW` at `0x180004fbc`
- `ADVAPI32!AreAllAccessesGranted` at `0x180005145`
- `ADVAPI32!AreAllAccessesGranted` at `0x180005145`
- `ADVAPI32!AccessCheck` at `0x180005131`
- `ADVAPI32!AccessCheck` at `0x180005131`
- `ADVAPI32!OpenThreadToken` at `0x1800050d5`
- `ADVAPI32!OpenThreadToken` at `0x1800050d5`
- `ADVAPI32!GetNamedSecurityInfoA` at `0x1800050a8`
- `ADVAPI32!GetNamedSecurityInfoA` at `0x1800050a8`
- `KERNEL32!GetCurrentThread` at `0x1800050c1`
- `KERNEL32!GetCurrentThread` at `0x1800050c1`
- `KERNEL32!CloseHandle` at `0x180005159`
- `KERNEL32!CloseHandle` at `0x180005159`
- `KERNEL32!LocalFree` at `0x18000516a`
- `KERNEL32!LocalFree` at `0x18000516a`
- `KERNEL32!GetLastError` at `0x1800051d0`
- `KERNEL32!GetLastError` at `0x180005269`
- `KERNEL32!GetLastError` at `0x1800052b8`
- `KERNEL32!GetLastError` at `0x1800051d0`
- `KERNEL32!GetLastError` at `0x180005269`
- `KERNEL32!GetLastError` at `0x1800052b8`

## string_xrefs

- `0x180005006`: `APPL_PHYSICAL_PATH`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned int __fastcall CheckAccessAllowed(__int64 a1)
{
  __int64 v2; // r8
  __int64 v3; // r8
  DWORD NamedSecurityInfoA; // eax
  unsigned int v5; // edi
  HANDLE CurrentThread; // rax
  unsigned int result; // eax
  DWORD LastError; // eax
  unsigned int v9; // edi
  DWORD v10; // eax
  unsigned int v11; // edi
  DWORD v12; // eax
  unsigned int v13; // edi
  DWORD pcbBuffer[2]; // [rsp+40h] [rbp-C0h] BYREF
  PSID ppsidOwner; // [rsp+48h] [rbp-B8h] BYREF
  PACL ppDacl; // [rsp+50h] [rbp-B0h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+68h] [rbp-98h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+88h] [rbp-78h] BYREF
  CHAR pObjectName[272]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Buffer[1000]; // [rsp+1C0h] [rbp+C0h] BYREF

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
  {
    pcbBuffer[0] = 1000;
    if ( GetUserNameW(Buffer, pcbBuffer)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 56, v2, Buffer);
    }
    TraceAuthInfo(a1);
  }
  pcbBuffer[0] = 260;
  if ( !(*(unsigned int (__fastcall **)(_QWORD, const char *, CHAR *, DWORD *))(a1 + 160))(
          *(_QWORD *)(a1 + 8),
          "APPL_PHYSICAL_PATH",
          pObjectName,
          pcbBuffer) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 44, &WPP_f6c5b0cbaa9434e90ba3dff64f25e7f9_Traceguids, LastError);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v9);
    throw (bad_win32_error *)pExceptionObject;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 12), 45, v3, pObjectName);
  pSecurityDescriptor = 0;
  ppDacl = 0;
  ppsidOwner = 0;
  *(_QWORD *)pcbBuffer = 0;
  NamedSecurityInfoA = GetNamedSecurityInfoA(
                         pObjectName,
                         SE_FILE_OBJECT,
                         7u,
                         &ppsidOwner,
                         (PSID *)pcbBuffer,
                         &ppDacl,
                         0,
                         &pSecurityDescriptor);
  v5 = NamedSecurityInfoA;
  if ( NamedSecurityInfoA )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        52,
        &WPP_f6c5b0cbaa9434e90ba3dff64f25e7f9_Traceguids,
        NamedSecurityInfoA);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v5);
    throw (bad_win32_error *)pExceptionObject;
  }
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v10 = GetLastError();
    v11 = v10;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 53, &WPP_f6c5b0cbaa9434e90ba3dff64f25e7f9_Traceguids, v10);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v11);
    throw (bad_win32_error *)pExceptionObject;
  }
  LODWORD(ppsidOwner) = 0;
  pcbBuffer[0] = 0;
  LODWORD(ppDacl) = 32;
  if ( !AccessCheck(
          pSecurityDescriptor,
          TokenHandle,
          2u,
          &GenericMapping,
          &PrivilegeSet,
          (LPDWORD)&ppDacl,
          (LPDWORD)&ppsidOwner,
          (LPBOOL)pcbBuffer) )
  {
    v12 = GetLastError();
    v13 = v12;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 54, pcbBuffer[0], v12, pcbBuffer[0]);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v13);
    throw (bad_win32_error *)pExceptionObject;
  }
  result = AreAllAccessesGranted((DWORD)ppsidOwner, 2u);
  if ( !result )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 12));
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, 5u);
    throw (bad_win32_error *)pExceptionObject;
  }
  if ( TokenHandle )
    result = CloseHandle(TokenHandle);
  if ( pSecurityDescriptor )
    return (unsigned int)LocalFree(pSecurityDescriptor);
  return result;
}

```

## disassembly

```asm
0x180004f68  push    rbp
0x180004f6a  push    rbx
0x180004f6b  push    rdi
0x180004f6c  push    r14
0x180004f6e  lea     rbp, [rsp-8A8h]
0x180004f76  sub     rsp, 9A8h
0x180004f7d  mov     rax, cs:__security_cookie
0x180004f84  xor     rax, rsp
0x180004f87  mov     [rbp+8C0h+var_30], rax
0x180004f8e  mov     rbx, rcx
0x180004f91  mov     rax, cs:WPP_GLOBAL_Control
0x180004f98  lea     r14, WPP_GLOBAL_Control
0x180004f9f  mov     dil, 4
0x180004fa2  test    [rax+6Ch], dil
0x180004fa6  jz      short loc_180004FF5
0x180004fa8  mov     [rsp+9C0h+pcbBuffer], 3E8h
0x180004fb0  lea     rdx, [rsp+9C0h+pcbBuffer]; pcbBuffer
0x180004fb5  lea     rcx, [rbp+8C0h+Buffer]; lpBuffer
0x180004fbc  call    cs:__imp_GetUserNameW
0x180004fc2  test    eax, eax
0x180004fc4  jz      short loc_180004FED
0x180004fc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180004fcd  cmp     rcx, r14
0x180004fd0  jz      short loc_180004FED
0x180004fd2  test    [rcx+6Ch], dil
0x180004fd6  jz      short loc_180004FED
0x180004fd8  mov     edx, 38h ; '8'
0x180004fdd  lea     r9, [rbp+8C0h+Buffer]
0x180004fe4  mov     rcx, [rcx+60h]
0x180004fe8  call    WPP_SF_S
0x180004fed  mov     rcx, rbx
0x180004ff0  call    TraceAuthInfo
0x180004ff5  mov     [rsp+9C0h+pcbBuffer], 104h
0x180004ffd  lea     r9, [rsp+9C0h+pcbBuffer]
0x180005002  lea     r8, [rbp+8C0h+pObjectName]
0x180005006  lea     rdx, aApplPhysicalPa; "APPL_PHYSICAL_PATH"
0x18000500d  mov     rcx, [rbx+8]
0x180005011  mov     rax, [rbx+0A0h]
0x180005018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000501d  test    eax, eax
0x18000501f  jz      loc_1800051D0
0x180005025  mov     rcx, cs:WPP_GLOBAL_Control
0x18000502c  cmp     rcx, r14
0x18000502f  jz      short loc_180005049
0x180005031  test    [rcx+6Ch], dil
0x180005035  jz      short loc_180005049
0x180005037  mov     edx, 2Dh ; '-'
0x18000503c  lea     r9, [rbp+8C0h+pObjectName]
0x180005040  mov     rcx, [rcx+60h]
0x180005044  call    WPP_SF_s
0x180005049  mov     [rsp+9C0h+pSecurityDescriptor], 0
0x180005052  mov     [rsp+9C0h+var_970], 0
0x18000505b  mov     [rsp+9C0h+ppsidOwner], 0
0x180005064  mov     qword ptr [rsp+9C0h+pcbBuffer], 0
0x18000506d  lea     rax, [rsp+9C0h+pSecurityDescriptor]
0x180005072  mov     [rsp+9C0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180005077  mov     [rsp+9C0h+ppSacl], 0; ppSacl
0x180005080  lea     rax, [rsp+9C0h+var_970]
0x180005085  mov     [rsp+9C0h+ppDacl], rax; ppDacl
0x18000508a  lea     rax, [rsp+9C0h+pcbBuffer]
0x18000508f  mov     [rsp+9C0h+ppsidGroup], rax; ppsidGroup
0x180005094  lea     r9, [rsp+9C0h+ppsidOwner]; ppsidOwner
0x180005099  mov     ebx, 1
0x18000509e  lea     r8d, [rbx+6]; SecurityInfo
0x1800050a2  mov     edx, ebx; ObjectType
0x1800050a4  lea     rcx, [rbp+8C0h+pObjectName]; pObjectName
0x1800050a8  call    cs:__imp_GetNamedSecurityInfoA
0x1800050ae  mov     edi, eax
0x1800050b0  test    eax, eax
0x1800050b2  jnz     loc_180005222
0x1800050b8  mov     [rsp+9C0h+TokenHandle], 0
0x1800050c1  call    cs:__imp_GetCurrentThread
0x1800050c7  lea     r9, [rsp+9C0h+TokenHandle]; TokenHandle
0x1800050cc  mov     r8d, ebx; OpenAsSelf
0x1800050cf  lea     edx, [rbx+7]; DesiredAccess
0x1800050d2  mov     rcx, rax; ThreadHandle
0x1800050d5  call    cs:__imp_OpenThreadToken
0x1800050db  test    eax, eax
0x1800050dd  jz      loc_180005269
0x1800050e3  mov     dword ptr [rsp+9C0h+ppsidOwner], edi
0x1800050e7  mov     [rsp+9C0h+pcbBuffer], edi
0x1800050eb  mov     dword ptr [rsp+9C0h+var_970], 20h ; ' '
0x1800050f3  lea     rax, [rsp+9C0h+pcbBuffer]
0x1800050f8  mov     [rsp+9C0h+ppSecurityDescriptor], rax; AccessStatus
0x1800050fd  lea     rax, [rsp+9C0h+ppsidOwner]
0x180005102  mov     [rsp+9C0h+ppSacl], rax; GrantedAccess
0x180005107  lea     rax, [rsp+9C0h+var_970]
0x18000510c  mov     [rsp+9C0h+ppDacl], rax; PrivilegeSetLength
0x180005111  lea     rax, [rbp+8C0h+PrivilegeSet]
0x180005115  mov     [rsp+9C0h+ppsidGroup], rax; PrivilegeSet
0x18000511a  lea     r9, GenericMapping; GenericMapping
0x180005121  lea     edi, [rbx+1]
0x180005124  mov     r8d, edi; DesiredAccess
0x180005127  mov     rdx, [rsp+9C0h+TokenHandle]; ClientToken
0x18000512c  mov     rcx, [rsp+9C0h+pSecurityDescriptor]; pSecurityDescriptor
0x180005131  call    cs:__imp_AccessCheck
0x180005137  test    eax, eax
0x180005139  jz      loc_1800052B8
0x18000513f  mov     edx, edi; DesiredAccess
0x180005141  mov     ecx, dword ptr [rsp+9C0h+ppsidOwner]; GrantedAccess
0x180005145  call    cs:__imp_AreAllAccessesGranted
0x18000514b  test    eax, eax
0x18000514d  jz      short loc_18000518D
0x18000514f  mov     rcx, [rsp+9C0h+TokenHandle]; hObject
0x180005154  test    rcx, rcx
0x180005157  jz      short loc_180005160
0x180005159  call    cs:__imp_CloseHandle
0x18000515f  nop
0x180005160  mov     rcx, [rsp+9C0h+pSecurityDescriptor]; hMem
0x180005165  test    rcx, rcx
0x180005168  jz      short loc_180005171
0x18000516a  call    cs:__imp_LocalFree
0x180005170  nop
0x180005171  mov     rcx, [rbp+8C0h+var_30]
0x180005178  xor     rcx, rsp; StackCookie
0x18000517b  call    __security_check_cookie
0x180005180  add     rsp, 9A8h
0x180005187  pop     r14
0x180005189  pop     rdi
0x18000518a  pop     rbx
0x18000518b  pop     rbp
0x18000518c  retn
0x18000518d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005194  cmp     rcx, r14
0x180005197  jz      short loc_1800051AF
0x180005199  test    [rcx+6Ch], bl
0x18000519c  jz      short loc_1800051AF
0x18000519e  mov     eax, dword ptr [rsp+9C0h+ppsidOwner]
0x1800051a2  mov     dword ptr [rsp+9C0h+ppsidGroup], eax
0x1800051a6  mov     rcx, [rcx+60h]
0x1800051aa  call    WPP_SF_DD
0x1800051af  mov     edx, 5; unsigned int
0x1800051b4  lea     rcx, [rsp+9C0h+pExceptionObject]; this
0x1800051b9  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x1800051be  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x1800051c5  lea     rcx, [rsp+9C0h+pExceptionObject]; pExceptionObject
0x1800051ca  call    _CxxThrowException_0
0x1800051d0  call    cs:__imp_GetLastError
0x1800051d6  mov     edi, eax
0x1800051d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800051df  cmp     rcx, r14
0x1800051e2  jz      short loc_180005204
0x1800051e4  mov     ebx, 1
0x1800051e9  test    [rcx+6Ch], bl
0x1800051ec  jz      short loc_180005204
0x1800051ee  lea     edx, [rbx+2Bh]
0x1800051f1  mov     r9d, eax
0x1800051f4  lea     r8, WPP_f6c5b0cbaa9434e90ba3dff64f25e7f9_Traceguids
0x1800051fb  mov     rcx, [rcx+60h]
0x1800051ff  call    WPP_SF_d
0x180005204  mov     edx, edi; unsigned int
0x180005206  lea     rcx, [rsp+9C0h+pExceptionObject]; this
0x18000520b  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x180005210  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x180005217  lea     rcx, [rsp+9C0h+pExceptionObject]; pExceptionObject
0x18000521c  call    _CxxThrowException_0
0x180005222  mov     rcx, cs:WPP_GLOBAL_Control
0x180005229  cmp     rcx, r14
0x18000522c  jz      short loc_18000524B
0x18000522e  test    [rcx+6Ch], bl
0x180005231  jz      short loc_18000524B
0x180005233  mov     edx, 34h ; '4'
0x180005238  mov     r9d, edi
0x18000523b  lea     r8, WPP_f6c5b0cbaa9434e90ba3dff64f25e7f9_Traceguids
0x180005242  mov     rcx, [rcx+60h]
0x180005246  call    WPP_SF_d
0x18000524b  mov     edx, edi; unsigned int
0x18000524d  lea     rcx, [rsp+9C0h+pExceptionObject]; this
0x180005252  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x180005257  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x18000525e  lea     rcx, [rsp+9C0h+pExceptionObject]; pExceptionObject
0x180005263  call    _CxxThrowException_0
0x180005269  call    cs:__imp_GetLastError
0x18000526f  mov     edi, eax
0x180005271  mov     rcx, cs:WPP_GLOBAL_Control
0x180005278  cmp     rcx, r14
0x18000527b  jz      short loc_18000529A
0x18000527d  test    [rcx+6Ch], bl
0x180005280  jz      short loc_18000529A
0x180005282  mov     edx, 35h ; '5'
0x180005287  mov     r9d, eax
0x18000528a  lea     r8, WPP_f6c5b0cbaa9434e90ba3dff64f25e7f9_Traceguids
0x180005291  mov     rcx, [rcx+60h]
0x180005295  call    WPP_SF_d
0x18000529a  mov     edx, edi; unsigned int
0x18000529c  lea     rcx, [rsp+9C0h+pExceptionObject]; this
0x1800052a1  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x1800052a6  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x1800052ad  lea     rcx, [rsp+9C0h+pExceptionObject]; pExceptionObject
0x1800052b2  call    _CxxThrowException_0
0x1800052b8  call    cs:__imp_GetLastError
0x1800052be  mov     edi, eax
0x1800052c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052c7  cmp     rcx, r14
0x1800052ca  jz      short loc_1800052EC
0x1800052cc  test    [rcx+6Ch], bl
0x1800052cf  jz      short loc_1800052EC
0x1800052d1  mov     edx, 36h ; '6'
0x1800052d6  mov     r8d, [rsp+9C0h+pcbBuffer]
0x1800052db  mov     dword ptr [rsp+9C0h+ppsidGroup], r8d
0x1800052e0  mov     r9d, eax
0x1800052e3  mov     rcx, [rcx+60h]
0x1800052e7  call    WPP_SF_Dd
0x1800052ec  mov     edx, edi; unsigned int
0x1800052ee  lea     rcx, [rsp+9C0h+pExceptionObject]; this
0x1800052f3  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x1800052f8  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x1800052ff  lea     rcx, [rsp+9C0h+pExceptionObject]; pExceptionObject
0x180005304  call    _CxxThrowException_0
```
