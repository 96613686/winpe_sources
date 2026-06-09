# RemoveAllAccessForSid

- ea: `0x1800461d0`
- end: `0x1800463dd`
- name: `RemoveAllAccessForSid`
- size: `525`
- prototype: `__int64 __fastcall(WCHAR *pObjectName, const WCHAR *StringSid)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180040d30`
- `0x1800414dc`

## callees

- `0x1800461d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004624f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004631d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004624f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004631d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046262`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046330`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046262`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046330`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180046230`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180046230`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004625a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046328`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004639c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800463ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800463ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004625a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046328`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004639c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800463ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800463ba`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180046349`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180046349`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180046308`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180046308`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18004637e`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18004637e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RemoveAllAccessForSid(WCHAR *pObjectName, const WCHAR *StringSid)
{
  const WCHAR *v2; // rax
  LPWSTR v3; // rdi
  BOOL v5; // r12d
  PSID v6; // r15
  HLOCAL v7; // r14
  DWORD LastError; // ebx
  signed int v9; // eax
  unsigned int v10; // ebx
  const WCHAR *v11; // rcx
  signed int NamedSecurityInfoW; // eax
  bool v13; // cc
  HLOCAL v14; // rsi
  DWORD v15; // ebx
  PACL OldAcl; // [rsp+40h] [rbp-29h] BYREF
  HLOCAL *v17; // [rsp+48h] [rbp-21h]
  PSID Sid; // [rsp+50h] [rbp-19h] BYREF
  char v19; // [rsp+58h] [rbp-11h]
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+60h] [rbp-9h] BYREF
  HLOCAL hMem; // [rsp+D0h] [rbp+67h] BYREF
  HLOCAL v22; // [rsp+E0h] [rbp+77h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+E8h] [rbp+7Fh] BYREF

  v2 = StringSid;
  v3 = pObjectName;
  if ( !*((_QWORD *)pObjectName + 2) )
    return 2147942487LL;
  v13 = *((_QWORD *)StringSid + 3) <= 7u;
  v17 = &v22;
  v19 = 1;
  v22 = 0;
  Sid = 0;
  if ( !v13 )
    v2 = *(const WCHAR **)StringSid;
  v5 = ConvertStringSidToSidW(v2, &Sid);
  if ( v19 )
  {
    v6 = Sid;
    v7 = *v17;
    if ( *v17 )
    {
      LastError = GetLastError();
      LocalFree(v7);
      SetLastError(LastError);
    }
    *v17 = v6;
  }
  if ( v5 )
  {
    v13 = *((_QWORD *)v3 + 3) <= 7u;
    memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 20);
    pListOfExplicitEntries.grfAccessMode = REVOKE_ACCESS;
    pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)v22;
    *(_QWORD *)&pListOfExplicitEntries.Trustee.TrusteeType = 1;
    pListOfExplicitEntries.grfAccessPermissions = 0x10000000;
    pListOfExplicitEntries.grfInheritance = 3;
    OldAcl = 0;
    hMem = 0;
    ppSecurityDescriptor = 0;
    if ( v13 )
      v11 = v3;
    else
      v11 = *(const WCHAR **)v3;
    NamedSecurityInfoW = GetNamedSecurityInfoW(v11, SE_FILE_OBJECT, 4u, 0, 0, &OldAcl, 0, &ppSecurityDescriptor);
    v10 = NamedSecurityInfoW;
    v13 = NamedSecurityInfoW <= 0;
    if ( !NamedSecurityInfoW )
    {
      v14 = hMem;
      if ( hMem )
      {
        v15 = GetLastError();
        LocalFree(v14);
        SetLastError(v15);
      }
      hMem = 0;
      NamedSecurityInfoW = SetEntriesInAclW(1u, &pListOfExplicitEntries, OldAcl, (PACL *)&hMem);
      v10 = NamedSecurityInfoW;
      v13 = NamedSecurityInfoW <= 0;
      if ( !NamedSecurityInfoW )
      {
        if ( *((_QWORD *)v3 + 3) > 7u )
          v3 = *(LPWSTR *)v3;
        NamedSecurityInfoW = SetNamedSecurityInfoW(v3, SE_FILE_OBJECT, 4u, 0, 0, (PACL)hMem, 0);
        v10 = NamedSecurityInfoW;
        v13 = NamedSecurityInfoW <= 0;
      }
    }
    if ( !v13 )
      v10 = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
    if ( ppSecurityDescriptor )
      LocalFree(ppSecurityDescriptor);
    if ( hMem )
      LocalFree(hMem);
  }
  else
  {
    v9 = GetLastError();
    v10 = v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
  }
  if ( v22 )
    LocalFree(v22);
  return v10;
}

```

## disassembly

```asm
0x1800461d0  mov     [rsp-8+arg_8], rbx
0x1800461d5  push    rbp
0x1800461d6  push    rsi
0x1800461d7  push    rdi
0x1800461d8  push    r12
0x1800461da  push    r13
0x1800461dc  push    r14
0x1800461de  push    r15
0x1800461e0  lea     rbp, [rsp-27h]
0x1800461e5  sub     rsp, 90h
0x1800461ec  xor     r13d, r13d
0x1800461ef  mov     rax, rdx
0x1800461f2  mov     rdi, rcx
0x1800461f5  cmp     [rcx+10h], r13
0x1800461f9  jnz     short loc_180046205
0x1800461fb  mov     eax, 80070057h
0x180046200  jmp     loc_1800463C2
0x180046205  cmp     qword ptr [rdx+18h], 7
0x18004620a  lea     rcx, [rbp+57h+arg_10]
0x18004620e  mov     r14d, 1
0x180046214  mov     [rbp+57h+var_78], rcx
0x180046218  mov     [rbp+57h+var_68], r14b
0x18004621c  mov     [rbp+57h+arg_10], r13
0x180046220  mov     [rbp+57h+Sid], r13
0x180046224  jbe     short loc_180046229
0x180046226  mov     rax, [rdx]
0x180046229  lea     rdx, [rbp+57h+Sid]; Sid
0x18004622d  mov     rcx, rax; StringSid
0x180046230  call    cs:__imp_ConvertStringSidToSidW
0x180046236  mov     r12d, eax
0x180046239  cmp     [rbp+57h+var_68], r13b
0x18004623d  jz      short loc_180046271
0x18004623f  mov     rsi, [rbp+57h+var_78]
0x180046243  mov     r15, [rbp+57h+Sid]
0x180046247  mov     r14, [rsi]
0x18004624a  test    r14, r14
0x18004624d  jz      short loc_180046268
0x18004624f  call    cs:__imp_GetLastError
0x180046255  mov     rcx, r14; hMem
0x180046258  mov     ebx, eax
0x18004625a  call    cs:__imp_LocalFree
0x180046260  mov     ecx, ebx; dwErrCode
0x180046262  call    cs:__imp_SetLastError
0x180046268  mov     [rsi], r15
0x18004626b  mov     r14d, 1
0x180046271  test    r12d, r12d
0x180046274  jnz     short loc_180046294
0x180046276  call    cs:__imp_GetLastError
0x18004627c  mov     ebx, eax
0x18004627e  test    eax, eax
0x180046280  jle     loc_1800463B1
0x180046286  movzx   ebx, ax
0x180046289  or      ebx, 80070000h
0x18004628f  jmp     loc_1800463B1
0x180046294  cmp     qword ptr [rdi+18h], 7
0x180046299  xorps   xmm0, xmm0
0x18004629c  mov     rax, [rbp+57h+arg_10]
0x1800462a0  mov     r15d, 4
0x1800462a6  movdqu  xmmword ptr [rbp+57h+pListOfExplicitEntries+0Ch], xmm0
0x1800462ab  mov     [rbp+57h+pListOfExplicitEntries.grfAccessMode], r15d
0x1800462af  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x1800462b3  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 1
0x1800462bb  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x1800462c2  mov     [rbp+57h+pListOfExplicitEntries.grfInheritance], 3
0x1800462c9  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], r13d
0x1800462cd  mov     [rbp+57h+OldAcl], r13
0x1800462d1  mov     [rbp+57h+hMem], r13
0x1800462d5  mov     [rbp+57h+arg_18], r13
0x1800462d9  jbe     short loc_1800462E0
0x1800462db  mov     rcx, [rdi]
0x1800462de  jmp     short loc_1800462E3
0x1800462e0  mov     rcx, rdi; pObjectName
0x1800462e3  lea     rax, [rbp+57h+arg_18]
0x1800462e7  xor     r9d, r9d; ppsidOwner
0x1800462ea  mov     [rsp+0C0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1800462ef  mov     r8d, r15d; SecurityInfo
0x1800462f2  lea     rax, [rbp+57h+OldAcl]
0x1800462f6  mov     [rsp+0C0h+ppSacl], r13; ppSacl
0x1800462fb  mov     [rsp+0C0h+ppDacl], rax; ppDacl
0x180046300  mov     edx, r14d; ObjectType
0x180046303  mov     [rsp+0C0h+ppsidGroup], r13; ppsidGroup
0x180046308  call    cs:__imp_GetNamedSecurityInfoW
0x18004630e  mov     ebx, eax
0x180046310  test    eax, eax
0x180046312  jnz     short loc_180046388
0x180046314  mov     rsi, [rbp+57h+hMem]
0x180046318  test    rsi, rsi
0x18004631b  jz      short loc_180046336
0x18004631d  call    cs:__imp_GetLastError
0x180046323  mov     rcx, rsi; hMem
0x180046326  mov     ebx, eax
0x180046328  call    cs:__imp_LocalFree
0x18004632e  mov     ecx, ebx; dwErrCode
0x180046330  call    cs:__imp_SetLastError
0x180046336  mov     r8, [rbp+57h+OldAcl]; OldAcl
0x18004633a  lea     r9, [rbp+57h+hMem]; NewAcl
0x18004633e  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180046342  mov     [rbp+57h+hMem], r13
0x180046346  mov     ecx, r14d; cCountOfExplicitEntries
0x180046349  call    cs:__imp_SetEntriesInAclW
0x18004634f  mov     ebx, eax
0x180046351  test    eax, eax
0x180046353  jnz     short loc_180046388
0x180046355  cmp     qword ptr [rdi+18h], 7
0x18004635a  mov     rax, [rbp+57h+hMem]
0x18004635e  jbe     short loc_180046363
0x180046360  mov     rdi, [rdi]
0x180046363  mov     [rsp+0C0h+ppSacl], r13; pSacl
0x180046368  xor     r9d, r9d; psidOwner
0x18004636b  mov     [rsp+0C0h+ppDacl], rax; pDacl
0x180046370  mov     r8d, r15d; SecurityInfo
0x180046373  mov     edx, r14d; ObjectType
0x180046376  mov     [rsp+0C0h+ppsidGroup], r13; psidGroup
0x18004637b  mov     rcx, rdi; pObjectName
0x18004637e  call    cs:__imp_SetNamedSecurityInfoW
0x180046384  mov     ebx, eax
0x180046386  test    eax, eax
0x180046388  jle     short loc_180046393
0x18004638a  movzx   ebx, ax
0x18004638d  or      ebx, 80070000h
0x180046393  mov     rcx, [rbp+57h+arg_18]; hMem
0x180046397  test    rcx, rcx
0x18004639a  jz      short loc_1800463A2
0x18004639c  call    cs:__imp_LocalFree
0x1800463a2  mov     rcx, [rbp+57h+hMem]; hMem
0x1800463a6  test    rcx, rcx
0x1800463a9  jz      short loc_1800463B1
0x1800463ab  call    cs:__imp_LocalFree
0x1800463b1  mov     rcx, [rbp+57h+arg_10]; hMem
0x1800463b5  test    rcx, rcx
0x1800463b8  jz      short loc_1800463C0
0x1800463ba  call    cs:__imp_LocalFree
0x1800463c0  mov     eax, ebx
0x1800463c2  mov     rbx, [rsp+0C0h+arg_8]
0x1800463ca  add     rsp, 90h
0x1800463d1  pop     r15
0x1800463d3  pop     r14
0x1800463d5  pop     r13
0x1800463d7  pop     r12
0x1800463d9  pop     rdi
0x1800463da  pop     rsi
0x1800463db  pop     rbp
0x1800463dc  retn
```
