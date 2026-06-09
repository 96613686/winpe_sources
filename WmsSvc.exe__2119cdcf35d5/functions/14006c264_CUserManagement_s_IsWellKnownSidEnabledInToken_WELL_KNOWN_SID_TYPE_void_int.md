# CUserManagement::s_IsWellKnownSidEnabledInToken(WELL_KNOWN_SID_TYPE,void *,int *)

- ea: `0x14006c264`
- end: `0x14006c42b`
- name: `?s_IsWellKnownSidEnabledInToken@CUserManagement@@SAJW4WELL_KNOWN_SID_TYPE@@PEAXPEAH@Z`
- size: `455`
- prototype: `__int64 __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType, HANDLE TokenHandle, PBOOL IsMember)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400465f0`
- `0x140052830`
- `0x14006c998`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14006c264`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!CreateWellKnownSid` at `0x14006c2b2`
- `ADVAPI32!CreateWellKnownSid` at `0x14006c2b2`
- `ADVAPI32!CheckTokenMembership` at `0x14006c36b`
- `ADVAPI32!CheckTokenMembership` at `0x14006c36b`
- `KERNEL32!GetLastError` at `0x14006c2c0`
- `KERNEL32!GetLastError` at `0x14006c379`
- `KERNEL32!GetLastError` at `0x14006c2c0`
- `KERNEL32!GetLastError` at `0x14006c379`
- `KERNEL32!IsDebuggerPresent` at `0x14006c317`
- `KERNEL32!IsDebuggerPresent` at `0x14006c3d0`
- `KERNEL32!IsDebuggerPresent` at `0x14006c317`
- `KERNEL32!IsDebuggerPresent` at `0x14006c3d0`

## string_xrefs

- `0x14006c2ea`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`
- `0x14006c3a3`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`
- `0x14006c2e3`: `CUserManagement::s_IsWellKnownSidEnabledInToken`
- `0x14006c39c`: `CUserManagement::s_IsWellKnownSidEnabledInToken`

## pseudocode

```c
__int64 __fastcall CUserManagement::s_IsWellKnownSidEnabledInToken(
        WELL_KNOWN_SID_TYPE WellKnownSidType,
        HANDLE TokenHandle,
        PBOOL IsMember)
{
  signed int v6; // eax
  signed int v7; // ebx
  __int64 v8; // r9
  __int64 v9; // r8
  signed int LastError; // eax
  signed int v12; // [rsp+30h] [rbp-A8h]
  signed int v13; // [rsp+38h] [rbp-A0h]
  DWORD cbSid[4]; // [rsp+40h] [rbp-98h] BYREF
  _BYTE pSid[80]; // [rsp+50h] [rbp-88h] BYREF

  memset_0(pSid, 0, 0x44u);
  cbSid[0] = 68;
  if ( CreateWellKnownSid(WellKnownSidType, 0, pSid, cbSid) )
  {
    v7 = 0;
    if ( CheckTokenMembership(TokenHandle, pSid, IsMember) )
      return (unsigned int)v7;
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 >= 0 )
      v7 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
      0x4EBu,
      L"CUserManagement::s_IsWellKnownSidEnabledInToken",
      L"CBRAEx",
      L"fSuccess",
      v7);
    if ( IsDebuggerPresent() )
    {
      v8 = 1259;
      goto LABEL_8;
    }
    v9 = 1259;
LABEL_18:
    v12 = v7;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
      v9,
      L"CUserManagement::s_IsWellKnownSidEnabledInToken",
      L"CBRAEx",
      L"fSuccess",
      v12);
    return (unsigned int)v7;
  }
  v6 = GetLastError();
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 >= 0 )
    v7 = -2147467259;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
    0x4E8u,
    L"CUserManagement::s_IsWellKnownSidEnabledInToken",
    L"CBRAEx",
    L"fSuccess",
    v7);
  if ( !IsDebuggerPresent() )
  {
    v9 = 1256;
    goto LABEL_18;
  }
  v8 = 1256;
LABEL_8:
  v13 = v7;
  DEBUGMSGLEVEL(
    2u,
    L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
    L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
    v8,
    L"CUserManagement::s_IsWellKnownSidEnabledInToken",
    L"CBRAEx",
    L"fSuccess",
    v13);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14006c264  push    rbx
0x14006c266  push    rbp
0x14006c267  push    rsi
0x14006c268  push    rdi
0x14006c269  push    r14
0x14006c26b  sub     rsp, 0B0h
0x14006c272  mov     rax, cs:__security_cookie
0x14006c279  xor     rax, rsp
0x14006c27c  mov     [rsp+0D8h+var_38], rax
0x14006c284  mov     rsi, r8
0x14006c287  mov     rdi, rdx
0x14006c28a  mov     ebx, ecx
0x14006c28c  mov     ebp, 44h ; 'D'
0x14006c291  mov     r8d, ebp; Size
0x14006c294  lea     rcx, [rsp+0D8h+pSid]; void *
0x14006c299  xor     edx, edx; Val
0x14006c29b  call    memset_0
0x14006c2a0  lea     r9, [rsp+0D8h+cbSid]; cbSid
0x14006c2a5  mov     [rsp+0D8h+cbSid], ebp
0x14006c2a9  lea     r8, [rsp+0D8h+pSid]; pSid
0x14006c2ae  xor     edx, edx; DomainSid
0x14006c2b0  mov     ecx, ebx; WellKnownSidType
0x14006c2b2  call    cs:__imp_CreateWellKnownSid
0x14006c2b8  test    eax, eax
0x14006c2ba  jnz     loc_14006C35E
0x14006c2c0  call    cs:__imp_GetLastError
0x14006c2c6  mov     ebx, eax
0x14006c2c8  test    eax, eax
0x14006c2ca  jle     short loc_14006C2D5
0x14006c2cc  movzx   ebx, ax
0x14006c2cf  or      ebx, 80070000h
0x14006c2d5  mov     eax, 80004005h
0x14006c2da  lea     r14, aCbraex; "CBRAEx"
0x14006c2e1  test    ebx, ebx
0x14006c2e3  lea     rsi, aCusermanagemen_12; "CUserManagement::s_IsWellKnownSidEnable"...
0x14006c2ea  lea     rdi, aTermsrvWmsSrcC_11; "termsrv\\wms\\src\\common\\srcutils\\us"...
0x14006c2f1  mov     r9, r14; unsigned __int16 *
0x14006c2f4  cmovns  ebx, eax
0x14006c2f7  lea     rbp, aFsuccess; "fSuccess"
0x14006c2fe  mov     [rsp+0D8h+var_B0], ebx; int
0x14006c302  mov     r8, rsi; unsigned __int16 *
0x14006c305  mov     edx, 4E8h; unsigned int
0x14006c30a  mov     [rsp+0D8h+var_B8], rbp; unsigned __int16 *
0x14006c30f  mov     rcx, rdi; unsigned __int16 *
0x14006c312  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006c317  call    cs:__imp_IsDebuggerPresent
0x14006c31d  test    eax, eax
0x14006c31f  jz      short loc_14006C353
0x14006c321  mov     r9d, 4E8h
0x14006c327  mov     [rsp+0D8h+var_A0], ebx
0x14006c32b  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14006c332  mov     [rsp+0D8h+var_A8], rbp
0x14006c337  mov     r8, rdi
0x14006c33a  mov     qword ptr [rsp+0D8h+var_B0], r14
0x14006c33f  mov     ecx, 2; unsigned __int8
0x14006c344  mov     [rsp+0D8h+var_B8], rsi
0x14006c349  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14006c34e  jmp     loc_14006C40B
0x14006c353  mov     r8d, 4E8h
0x14006c359  jmp     loc_14006C3EB
0x14006c35e  mov     r8, rsi; IsMember
0x14006c361  lea     rdx, [rsp+0D8h+pSid]; SidToCheck
0x14006c366  mov     rcx, rdi; TokenHandle
0x14006c369  xor     ebx, ebx
0x14006c36b  call    cs:__imp_CheckTokenMembership
0x14006c371  test    eax, eax
0x14006c373  jnz     loc_14006C40B
0x14006c379  call    cs:__imp_GetLastError
0x14006c37f  mov     ebx, eax
0x14006c381  test    eax, eax
0x14006c383  jle     short loc_14006C38E
0x14006c385  movzx   ebx, ax
0x14006c388  or      ebx, 80070000h
0x14006c38e  mov     eax, 80004005h
0x14006c393  lea     r14, aCbraex; "CBRAEx"
0x14006c39a  test    ebx, ebx
0x14006c39c  lea     rsi, aCusermanagemen_12; "CUserManagement::s_IsWellKnownSidEnable"...
0x14006c3a3  lea     rdi, aTermsrvWmsSrcC_11; "termsrv\\wms\\src\\common\\srcutils\\us"...
0x14006c3aa  mov     r9, r14; unsigned __int16 *
0x14006c3ad  cmovns  ebx, eax
0x14006c3b0  lea     rbp, aFsuccess; "fSuccess"
0x14006c3b7  mov     [rsp+0D8h+var_B0], ebx; int
0x14006c3bb  mov     r8, rsi; unsigned __int16 *
0x14006c3be  mov     edx, 4EBh; unsigned int
0x14006c3c3  mov     [rsp+0D8h+var_B8], rbp; unsigned __int16 *
0x14006c3c8  mov     rcx, rdi; unsigned __int16 *
0x14006c3cb  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006c3d0  call    cs:__imp_IsDebuggerPresent
0x14006c3d6  test    eax, eax
0x14006c3d8  jz      short loc_14006C3E5
0x14006c3da  mov     r9d, 4EBh
0x14006c3e0  jmp     loc_14006C327
0x14006c3e5  mov     r8d, 4EBh
0x14006c3eb  mov     dword ptr [rsp+0D8h+var_A8], ebx
0x14006c3ef  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14006c3f6  mov     qword ptr [rsp+0D8h+var_B0], rbp
0x14006c3fb  mov     r9, rsi
0x14006c3fe  mov     rdx, rdi
0x14006c401  mov     [rsp+0D8h+var_B8], r14
0x14006c406  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14006c40b  mov     eax, ebx
0x14006c40d  mov     rcx, [rsp+0D8h+var_38]
0x14006c415  xor     rcx, rsp; StackCookie
0x14006c418  call    __security_check_cookie
0x14006c41d  add     rsp, 0B0h
0x14006c424  pop     r14
0x14006c426  pop     rdi
0x14006c427  pop     rsi
0x14006c428  pop     rbp
0x14006c429  pop     rbx
0x14006c42a  retn
```
