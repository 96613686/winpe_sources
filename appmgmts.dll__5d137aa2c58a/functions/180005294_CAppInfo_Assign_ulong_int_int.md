# CAppInfo::Assign(ulong,int,int)

- ea: `0x180005294`
- end: `0x180005a42`
- name: `?Assign@CAppInfo@@QEAAKKHH@Z`
- size: `1966`
- prototype: `__int64 __fastcall(CAppInfo *this, int, int, int)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000239c`
- `0x1800047d0`
- `0x180007410`
- `0x180007c24`

## callees

- `0x1800016d0`
- `0x180005294`
- `0x180005a48`
- `0x180005cec`
- `0x180005f2c`
- `0x18000d11c`
- `0x180012fbc`
- `0x18001b1a0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059ca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800055e0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800055e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000597c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000597c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005563`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000562e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000567c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800056ca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005714`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000575f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800057fc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000583a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000586c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800058a7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800058d2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000596b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005563`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000562e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000567c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800056ca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005714`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000575f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800057fc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000583a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000586c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800058a7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800058d2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000596b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800055a1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800055a1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000599f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000599f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005807`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005807`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005795`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005795`

## string_xrefs

- `0x1800058bb`: `Install UI`

## pseudocode

```c
__int64 __fastcall CAppInfo::Assign(CAppInfo *this, int a2, int a3, int a4)
{
  __int64 v4; // rax
  unsigned int v9; // edi
  int v10; // eax
  int v11; // ecx
  int v12; // r15d
  int v13; // eax
  unsigned int v14; // eax
  int v15; // eax
  int v16; // r15d
  __int64 result; // rax
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  const BYTE *v21; // rcx
  DWORD cbData; // eax
  const BYTE *v23; // rcx
  DWORD v24; // eax
  __int64 v25; // rax
  const BYTE *v26; // rcx
  DWORD v27; // eax
  __int64 v28; // rax
  const BYTE *v29; // rcx
  DWORD v30; // eax
  __int64 v31; // rax
  const BYTE *v32; // rcx
  SIZE_T v33; // rax
  BYTE *v34; // r15
  unsigned __int16 *v35; // rsi
  unsigned int i; // edi
  int v37; // edx
  int v38; // r8d
  int v39; // ecx
  int v40; // eax
  __int64 v41; // rcx
  DWORD LastError; // eax
  DWORD v43; // eax
  BYTE *lpData; // [rsp+20h] [rbp-99h]
  HKEY hKey; // [rsp+50h] [rbp-69h] BYREF
  int v46; // [rsp+58h] [rbp-61h] BYREF
  BYTE Data[4]; // [rsp+5Ch] [rbp-5Dh] BYREF
  int v48; // [rsp+60h] [rbp-59h] BYREF
  int v49; // [rsp+64h] [rbp-55h]
  _WORD v50[12]; // [rsp+68h] [rbp-51h] BYREF
  WCHAR SubKey[40]; // [rsp+80h] [rbp-39h] BYREF

  v4 = *((_QWORD *)this + 2);
  hKey = 0;
  *(_DWORD *)Data = 0;
  v49 = a3;
  if ( (*(_DWORD *)(v4 + 304) || *(_DWORD *)(v4 + 336))
    && ((unsigned int)(*((_DWORD *)this + 57) - 2) <= 1 || (*(_WORD *)&gDebugLevel & 0x100) != 0) )
  {
    if ( *(_DWORD *)&gDebugLevel )
      _DebugMsg(4u, 0xCAAu);
    v9 = 1274;
    *((_DWORD *)this + 58) = 1274;
LABEL_124:
    if ( !v49 )
      return v9;
    goto LABEL_125;
  }
  v46 = 0;
  GuidToString((struct _GUID *)((char *)this + 24), SubKey);
  if ( !a3 )
  {
LABEL_49:
    v9 = RegSetValueExW(
           *(HKEY *)(*((_QWORD *)this + 2) + 288LL),
           *((LPCWSTR *)this + 10),
           0,
           4u,
           (const BYTE *)this + 208,
           4u);
    if ( v9 || !a4 || !*((_DWORD *)this + 53) )
      goto LABEL_124;
    v18 = *((_QWORD *)this + 2);
    if ( *(_DWORD *)(v18 + 396) != 1 && *(_DWORD *)(v18 + 296) )
      RevertToSelf();
    v19 = *((_QWORD *)this + 2);
    hKey = 0;
    v9 = RegCreateKeyExW(*(HKEY *)(v19 + 288), SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
    v20 = -1;
    if ( !v9 )
    {
      v21 = (const BYTE *)*((_QWORD *)this + 5);
      if ( v21 )
      {
        do
          ++v20;
        while ( *(_WORD *)&v21[2 * v20] );
        cbData = 2 * v20 + 2;
      }
      else
      {
        cbData = 0;
      }
      v9 = RegSetValueExW(hKey, L"Deployment Name", 0, 1u, v21, cbData);
      if ( !v9 )
      {
        v23 = (const BYTE *)*((_QWORD *)this + 9);
        if ( v23 )
        {
          v25 = -1;
          do
            ++v25;
          while ( *(_WORD *)&v23[2 * v25] );
          v24 = 2 * v25 + 2;
        }
        else
        {
          v24 = 0;
        }
        v9 = RegSetValueExW(hKey, L"GPO Name", 0, 1u, v23, v24);
        if ( !v9 )
        {
          v26 = (const BYTE *)*((_QWORD *)this + 6);
          if ( v26 )
          {
            v28 = -1;
            do
              ++v28;
            while ( *(_WORD *)&v26[2 * v28] );
            v27 = 2 * v28 + 2;
          }
          else
          {
            v27 = 0;
          }
          v9 = RegSetValueExW(hKey, L"GPO ID", 0, 1u, v26, v27);
          if ( !v9 )
          {
            v29 = (const BYTE *)*((_QWORD *)this + 10);
            if ( v29 )
            {
              v31 = -1;
              do
                ++v31;
              while ( *(_WORD *)&v29[2 * v31] );
              v30 = 2 * v31 + 2;
            }
            else
            {
              v30 = 0;
            }
            v9 = RegSetValueExW(hKey, L"Product ID", 0, 1u, v29, v30);
          }
        }
      }
      v20 = -1;
    }
    v32 = (const BYTE *)*((_QWORD *)this + 19);
    if ( v32 )
    {
      if ( v9 )
        goto LABEL_110;
      do
        ++v20;
      while ( *(_WORD *)&v32[2 * v20] );
      v9 = RegSetValueExW(hKey, L"SupportUrl", 0, 1u, v32, 2 * v20 + 2);
    }
    if ( !v9 )
    {
      if ( !*((_DWORD *)this + 30) )
      {
LABEL_92:
        v9 = RegSetValueExW(hKey, L"AssignCount", 0, 4u, (const BYTE *)this + 188, 4u);
        if ( !v9 )
        {
          v9 = RegSetValueExW(hKey, L"Revision", 0, 4u, (const BYTE *)this + 204, 4u);
          if ( !v9
            && (!*((_DWORD *)this + 51)
             || (v9 = RegSetValueExW(hKey, L"ScriptTime", 0, v9 + 3, (const BYTE *)this + 196, 8u)) == 0) )
          {
            v9 = RegSetValueExW(hKey, L"Install UI", 0, 4u, (const BYTE *)this + 208, 4u);
            if ( !v9 )
            {
              v37 = *((_DWORD *)this + 53);
              if ( v37 )
              {
                if ( (v37 & 0x400) != 0 )
                {
                  v38 = 1;
                }
                else
                {
                  v38 = 0;
                  if ( (v37 & 8) != 0 )
                    v38 = 2;
                }
                v39 = v38 | ((*((_DWORD *)this + 53) & 0x1000) != 0 ? 16 : 8);
                if ( *((_DWORD *)this + 59) )
                  LOBYTE(v39) = v39 | 4;
                LOBYTE(v40) = v39 | 0x80;
                if ( (v37 & 0x2000) == 0 )
                  LOBYTE(v40) = v39;
              }
              else
              {
                v40 = *((_DWORD *)this + 56);
              }
              *(_DWORD *)Data = (unsigned __int8)v40;
              v9 = RegSetValueExW(hKey, L"AppState", 0, 4u, Data, 4u);
            }
          }
        }
        goto LABEL_110;
      }
      v33 = 2LL * (unsigned int)(39 * *((_DWORD *)this + 30) + 1);
      if ( !is_mul_ok((unsigned int)(39 * *((_DWORD *)this + 30) + 1), 2u) )
        v33 = -1;
      v34 = (BYTE *)LocalAlloc(0, v33);
      if ( v34 )
      {
        v35 = (unsigned __int16 *)v34;
        for ( i = 0; i < *((_DWORD *)this + 30); ++i )
        {
          GuidToString((struct _GUID *)(*((_QWORD *)this + 16) + 16LL * i), v35);
          v35 += 39;
        }
        *v35 = 0;
        v9 = RegSetValueExW(hKey, L"SupercededIDs", 0, 7u, v34, 78 * *((_DWORD *)this + 30) + 2);
        LocalFree(v34);
        if ( v9 )
          goto LABEL_110;
        goto LABEL_92;
      }
      v9 = 14;
    }
LABEL_110:
    if ( hKey )
      RegCloseKey(hKey);
    v41 = *((_QWORD *)this + 2);
    if ( *(_DWORD *)(v41 + 396) != 1 && *(_DWORD *)(v41 + 296) && !ImpersonateLoggedOnUser(*(HANDLE *)(v41 + 264)) )
    {
      if ( *(_DWORD *)&gDebugLevel )
      {
        LastError = GetLastError();
        _DebugMsg(2u, 0xBC4u, LastError);
      }
      v43 = GetLastError();
      if ( v43 )
      {
        if ( !v9 )
          v9 = v43;
      }
    }
    goto LABEL_124;
  }
  if ( *(_DWORD *)&gDebugLevel )
    _DebugMsg(4u, 0xBCAu, *((_QWORD *)this + 5), *((_QWORD *)this + 9));
  v9 = CAppInfo::CopyScriptIfNeeded(this);
  if ( v9 && a4 )
    goto LABEL_126;
  v9 = CAppInfo::EnforceAssignmentSecurity(this, &v46);
  if ( !a2 )
  {
    v10 = *((_DWORD *)this + 56);
    if ( (v10 & 0x200) != 0 || (v11 = *((_DWORD *)this + 54), a2 = 32, v11 != 1) && v11 != 3 && v11 != 4 && v11 != 5 )
    {
      a2 = 33;
      v12 = 1;
      if ( *(_DWORD *)(*((_QWORD *)this + 2) + 296LL) )
      {
        v13 = ((__int64 (__fastcall *)(_QWORD))gpfnMsiQueryProductState)(*((_QWORD *)this + 10));
        v48 = 8;
        if ( v13 == 1 || (unsigned int)(v13 - 3) <= 2 )
        {
          v14 = ((__int64 (__fastcall *)(_QWORD, const unsigned __int16 *, _WORD *, int *))gpfnMsiGetProductInfo)(
                  *((_QWORD *)this + 10),
                  L"AssignmentType",
                  v50,
                  &v48);
          if ( !v9 )
            v9 = v14;
          if ( !v14 && v50[0] == 49 )
            v12 = 0;
        }
      }
      v10 = *((_DWORD *)this + 56);
      if ( (v10 & 0x800) == 0 && v12 )
        a2 = 97;
    }
    if ( v46 )
      a2 |= 4u;
    if ( (v10 & 0x4000) != 0 || *((_DWORD *)this + 78) )
    {
      a2 |= 4u;
      if ( (v10 & 0x200) != 0 || (v15 = *((_DWORD *)this + 54), v15 != 1) && (unsigned int)(v15 - 3) > 2 )
        a2 |= 0x100u;
    }
  }
  v16 = a2 | 8;
  if ( *(_DWORD *)(*((_QWORD *)this + 2) + 296LL) )
    v16 = a2;
  if ( v9 )
    goto LABEL_43;
  if ( *(_DWORD *)&gDebugLevel )
    _DebugMsg(4u, 0xBDDu, *((_QWORD *)this + 5), *((_QWORD *)this + 11), v16);
  v9 = CallMsiAdvertiseScript(*((const unsigned __int16 **)this + 11), v16, 0, 0);
  if ( v9 )
  {
LABEL_43:
    if ( *(_DWORD *)&gDebugLevel )
    {
      LODWORD(lpData) = v9;
      _DebugMsg(2u, 0xBDEu, *((_QWORD *)this + 5), *((_QWORD *)this + 11), lpData);
    }
  }
  else if ( (*((_DWORD *)this + 56) & 0x200) != 0 )
  {
    ++*((_DWORD *)this + 47);
  }
  if ( *((_DWORD *)this + 57) != 1 || (result = 1618, v9 != 1618) )
  {
    result = 1624;
    if ( v9 != 1624 )
    {
      if ( v9 )
      {
LABEL_125:
        if ( a4 )
LABEL_126:
          CEvents::Assign((CEvents *)(*((_QWORD *)this + 2) + 344LL), v9, this);
        return v9;
      }
      goto LABEL_49;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005294  mov     [rsp-8+arg_10], rbx
0x180005299  push    rbp
0x18000529a  push    rsi
0x18000529b  push    rdi
0x18000529c  push    r12
0x18000529e  push    r13
0x1800052a0  push    r14
0x1800052a2  push    r15
0x1800052a4  lea     rbp, [rsp-27h]
0x1800052a9  sub     rsp, 0E0h
0x1800052b0  mov     rax, cs:__security_cookie
0x1800052b7  xor     rax, rsp
0x1800052ba  mov     [rbp+57h+var_40], rax
0x1800052be  mov     rax, [rcx+10h]
0x1800052c2  xor     r15d, r15d
0x1800052c5  mov     [rbp+57h+hKey], r15
0x1800052c9  mov     r13d, r9d
0x1800052cc  mov     dword ptr [rbp+57h+Data], r15d
0x1800052d0  mov     edi, r8d
0x1800052d3  mov     [rbp+57h+var_AC], r8d
0x1800052d7  mov     esi, edx
0x1800052d9  lea     r12d, [r15+2]
0x1800052dd  mov     rbx, rcx
0x1800052e0  cmp     [rax+130h], r15d
0x1800052e7  jnz     short loc_1800052F2
0x1800052e9  cmp     [rax+150h], r15d
0x1800052f0  jz      short loc_180005314
0x1800052f2  mov     eax, [rcx+0E4h]
0x1800052f8  mov     ecx, cs:?gDebugLevel@@3KA; ulong gDebugLevel
0x1800052fe  sub     eax, r12d
0x180005301  cmp     eax, 1
0x180005304  jbe     loc_1800059DB
0x18000530a  bt      ecx, 8
0x18000530e  jb      loc_1800059DB
0x180005314  lea     rcx, [rbx+18h]; struct _GUID *
0x180005318  mov     [rbp+57h+var_B8], r15d
0x18000531c  lea     rdx, [rbp+57h+SubKey]; unsigned __int16 *
0x180005320  call    ?GuidToString@@YAXAEAU_GUID@@PEAG@Z; GuidToString(_GUID &,ushort *)
0x180005325  mov     r14d, 4
0x18000532b  test    edi, edi
0x18000532d  jz      loc_18000553D
0x180005333  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x18000533a  jz      short loc_180005351
0x18000533c  mov     r9, [rbx+48h]
0x180005340  mov     edx, 0BCAh; unsigned int
0x180005345  mov     r8, [rbx+28h]
0x180005349  mov     ecx, r14d; unsigned int
0x18000534c  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180005351  mov     rcx, rbx; this
0x180005354  call    ?CopyScriptIfNeeded@CAppInfo@@AEAAKXZ; CAppInfo::CopyScriptIfNeeded(void)
0x180005359  mov     edi, eax
0x18000535b  test    eax, eax
0x18000535d  jz      short loc_180005368
0x18000535f  test    r13d, r13d
0x180005362  jnz     loc_180005A04
0x180005368  lea     rdx, [rbp+57h+var_B8]; int *
0x18000536c  mov     rcx, rbx; this
0x18000536f  call    ?EnforceAssignmentSecurity@CAppInfo@@AEAAKPEAH@Z; CAppInfo::EnforceAssignmentSecurity(int *)
0x180005374  mov     edi, eax
0x180005376  test    esi, esi
0x180005378  jnz     loc_180005482
0x18000537e  mov     eax, [rbx+0E0h]
0x180005384  bt      eax, 9
0x180005388  jb      short loc_1800053B9
0x18000538a  mov     ecx, [rbx+0D8h]
0x180005390  mov     esi, 20h ; ' '
0x180005395  cmp     ecx, 1
0x180005398  jz      loc_18000544A
0x18000539e  cmp     ecx, 3
0x1800053a1  jz      loc_18000544A
0x1800053a7  cmp     ecx, r14d
0x1800053aa  jz      loc_18000544A
0x1800053b0  cmp     ecx, 5
0x1800053b3  jz      loc_18000544A
0x1800053b9  mov     rax, [rbx+10h]
0x1800053bd  mov     esi, 21h ; '!'
0x1800053c2  xor     r12d, r12d
0x1800053c5  lea     r15d, [rsi-20h]
0x1800053c9  cmp     [rax+128h], r12d
0x1800053d0  jz      short loc_18000542B
0x1800053d2  mov     rcx, [rbx+50h]
0x1800053d6  mov     rax, cs:?gpfnMsiQueryProductState@@3P6A?AW4tagINSTALLSTATE@@PEBG@ZEA; tagINSTALLSTATE (*gpfnMsiQueryProductState)(ushort const *)
0x1800053dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053e2  mov     [rbp+57h+var_B0], 8
0x1800053e9  cmp     eax, r15d
0x1800053ec  jz      short loc_1800053F8
0x1800053ee  add     eax, 0FFFFFFFDh
0x1800053f1  lea     ecx, [rsi-1Fh]
0x1800053f4  cmp     eax, ecx
0x1800053f6  ja      short loc_18000542B
0x1800053f8  mov     rcx, [rbx+50h]
0x1800053fc  lea     r9, [rbp+57h+var_B0]
0x180005400  mov     rax, cs:?gpfnMsiGetProductInfo@@3P6AIPEBG0PEAGPEAK@ZEA; uint (*gpfnMsiGetProductInfo)(ushort const *,ushort const *,ushort *,ulong *)
0x180005407  lea     r8, [rbp+57h+var_A8]
0x18000540b  lea     rdx, aAssignmenttype; "AssignmentType"
0x180005412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005417  test    edi, edi
0x180005419  cmovz   edi, eax
0x18000541c  test    eax, eax
0x18000541e  jnz     short loc_18000542B
0x180005420  lea     ecx, [rax+31h]
0x180005423  cmp     cx, [rbp+57h+var_A8]
0x180005427  cmovz   r15d, r12d
0x18000542b  mov     eax, [rbx+0E0h]
0x180005431  mov     r12d, 2
0x180005437  bt      eax, 0Bh
0x18000543b  jb      short loc_180005447
0x18000543d  test    r15d, r15d
0x180005440  jz      short loc_180005447
0x180005442  lea     esi, [r12+5Fh]
0x180005447  xor     r15d, r15d
0x18000544a  cmp     [rbp+57h+var_B8], r15d
0x18000544e  jz      short loc_180005453
0x180005450  or      esi, r14d
0x180005453  bt      eax, 0Eh
0x180005457  jb      short loc_180005462
0x180005459  cmp     [rbx+138h], r15d
0x180005460  jz      short loc_180005482
0x180005462  or      esi, r14d
0x180005465  bt      eax, 9
0x180005469  jb      short loc_18000547E
0x18000546b  mov     eax, [rbx+0D8h]
0x180005471  cmp     eax, 1
0x180005474  jz      short loc_180005482
0x180005476  add     eax, 0FFFFFFFDh
0x180005479  cmp     eax, r12d
0x18000547c  jbe     short loc_180005482
0x18000547e  bts     esi, 8
0x180005482  mov     rax, [rbx+10h]
0x180005486  mov     r15d, esi
0x180005489  or      r15d, 8
0x18000548d  cmp     dword ptr [rax+128h], 0
0x180005494  cmovnz  r15d, esi
0x180005498  test    edi, edi
0x18000549a  jnz     short loc_1800054ED
0x18000549c  cmp     cs:?gDebugLevel@@3KA, edi; ulong gDebugLevel
0x1800054a2  jz      short loc_1800054BE
0x1800054a4  mov     r9, [rbx+58h]
0x1800054a8  mov     edx, 0BDDh; unsigned int
0x1800054ad  mov     r8, [rbx+28h]
0x1800054b1  mov     ecx, r14d; unsigned int
0x1800054b4  mov     dword ptr [rsp+110h+lpData], r15d
0x1800054b9  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800054be  mov     rcx, [rbx+58h]; unsigned __int16 *
0x1800054c2  xor     r9d, r9d; int
0x1800054c5  xor     r8d, r8d; HKEY *
0x1800054c8  mov     edx, r15d; unsigned int
0x1800054cb  call    ?CallMsiAdvertiseScript@@YAKPEBGKPEAPEAUHKEY__@@H@Z; CallMsiAdvertiseScript(ushort const *,ulong,HKEY__ * *,int)
0x1800054d0  xor     r15d, r15d
0x1800054d3  mov     edi, eax
0x1800054d5  test    eax, eax
0x1800054d7  jnz     short loc_1800054F0
0x1800054d9  test    dword ptr [rbx+0E0h], 200h
0x1800054e3  jz      short loc_180005512
0x1800054e5  inc     dword ptr [rbx+0BCh]
0x1800054eb  jmp     short loc_180005512
0x1800054ed  xor     r15d, r15d
0x1800054f0  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x1800054f7  jz      short loc_180005512
0x1800054f9  mov     r9, [rbx+58h]
0x1800054fd  mov     edx, 0BDEh; unsigned int
0x180005502  mov     r8, [rbx+28h]
0x180005506  mov     ecx, r12d; unsigned int
0x180005509  mov     dword ptr [rsp+110h+lpData], edi
0x18000550d  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180005512  cmp     dword ptr [rbx+0E4h], 1
0x180005519  jnz     short loc_180005528
0x18000551b  mov     eax, 652h
0x180005520  cmp     edi, eax
0x180005522  jz      loc_180005A1B
0x180005528  mov     eax, 658h
0x18000552d  cmp     edi, eax
0x18000552f  jz      loc_180005A1B
0x180005535  test    edi, edi
0x180005537  jnz     loc_1800059FF
0x18000553d  mov     rcx, [rbx+10h]
0x180005541  lea     r12, [rbx+0D0h]
0x180005548  mov     rdx, [rbx+50h]; lpValueName
0x18000554c  mov     r9d, r14d; dwType
0x18000554f  mov     [rsp+110h+cbData], r14d; cbData
0x180005554  xor     r8d, r8d; Reserved
0x180005557  mov     [rsp+110h+lpData], r12; lpData
0x18000555c  mov     rcx, [rcx+120h]; hKey
0x180005563  call    cs:__imp_RegSetValueExW
0x180005569  mov     edi, eax
0x18000556b  test    eax, eax
0x18000556d  jnz     loc_1800059F9
0x180005573  test    r13d, r13d
0x180005576  jz      loc_1800059F9
0x18000557c  cmp     [rbx+0D4h], r15d
0x180005583  jz      loc_1800059F9
0x180005589  mov     rax, [rbx+10h]
0x18000558d  lea     esi, [rdi+1]
0x180005590  cmp     [rax+18Ch], esi
0x180005596  jz      short loc_1800055A7
0x180005598  cmp     [rax+128h], r15d
0x18000559f  jz      short loc_1800055A7
0x1800055a1  call    cs:__imp_RevertToSelf
0x1800055a7  mov     rcx, [rbx+10h]
0x1800055ab  lea     rax, [rbp+57h+hKey]
0x1800055af  mov     [rsp+110h+lpdwDisposition], r15; lpdwDisposition
0x1800055b4  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x1800055b8  mov     [rsp+110h+phkResult], rax; phkResult
0x1800055bd  xor     r9d, r9d; lpClass
0x1800055c0  mov     [rbp+57h+hKey], r15
0x1800055c4  xor     r8d, r8d; Reserved
0x1800055c7  mov     rcx, [rcx+120h]; hKey
0x1800055ce  mov     [rsp+110h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800055d3  mov     [rsp+110h+cbData], 2001Fh; samDesired
0x1800055db  mov     dword ptr [rsp+110h+lpData], r15d; dwOptions
0x1800055e0  call    cs:__imp_RegCreateKeyExW
0x1800055e6  mov     edi, eax
0x1800055e8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800055ec  test    edi, edi
0x1800055ee  jnz     loc_180005720
0x1800055f4  mov     rcx, [rbx+28h]
0x1800055f8  test    rcx, rcx
0x1800055fb  jnz     short loc_180005602
0x1800055fd  mov     rax, r15
0x180005600  jmp     short loc_180005614
0x180005602  inc     rax
0x180005605  cmp     [rcx+rax*2], r15w
0x18000560a  jnz     short loc_180005602
0x18000560c  lea     rax, ds:2[rax*2]
0x180005614  mov     [rsp+110h+cbData], eax; cbData
0x180005618  lea     rdx, aDeploymentName; "Deployment Name"
0x18000561f  mov     [rsp+110h+lpData], rcx; lpData
0x180005624  mov     r9d, esi; dwType
0x180005627  mov     rcx, [rbp+57h+hKey]; hKey
0x18000562b  xor     r8d, r8d; Reserved
0x18000562e  call    cs:__imp_RegSetValueExW
0x180005634  mov     edi, eax
0x180005636  test    eax, eax
0x180005638  jnz     loc_18000571C
0x18000563e  mov     rcx, [rbx+48h]
0x180005642  test    rcx, rcx
0x180005645  jnz     short loc_18000564C
0x180005647  mov     rax, r15
0x18000564a  jmp     short loc_180005662
0x18000564c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005650  inc     rax
0x180005653  cmp     [rcx+rax*2], r15w
0x180005658  jnz     short loc_180005650
0x18000565a  lea     rax, ds:2[rax*2]
0x180005662  mov     [rsp+110h+cbData], eax; cbData
0x180005666  lea     rdx, aGpoName; "GPO Name"
0x18000566d  mov     [rsp+110h+lpData], rcx; lpData
0x180005672  mov     r9d, esi; dwType
0x180005675  mov     rcx, [rbp+57h+hKey]; hKey
0x180005679  xor     r8d, r8d; Reserved
0x18000567c  call    cs:__imp_RegSetValueExW
0x180005682  mov     edi, eax
0x180005684  test    eax, eax
0x180005686  jnz     loc_18000571C
0x18000568c  mov     rcx, [rbx+30h]
0x180005690  test    rcx, rcx
0x180005693  jnz     short loc_18000569A
0x180005695  mov     rax, r15
0x180005698  jmp     short loc_1800056B0
0x18000569a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000569e  inc     rax
0x1800056a1  cmp     [rcx+rax*2], r15w
0x1800056a6  jnz     short loc_18000569E
0x1800056a8  lea     rax, ds:2[rax*2]
0x1800056b0  mov     [rsp+110h+cbData], eax; cbData
0x1800056b4  lea     rdx, aGpoId; "GPO ID"
0x1800056bb  mov     [rsp+110h+lpData], rcx; lpData
0x1800056c0  mov     r9d, esi; dwType
0x1800056c3  mov     rcx, [rbp+57h+hKey]; hKey
0x1800056c7  xor     r8d, r8d; Reserved
0x1800056ca  call    cs:__imp_RegSetValueExW
0x1800056d0  mov     edi, eax
0x1800056d2  test    eax, eax
0x1800056d4  jnz     short loc_18000571C
0x1800056d6  mov     rcx, [rbx+50h]
0x1800056da  test    rcx, rcx
0x1800056dd  jnz     short loc_1800056E4
0x1800056df  mov     rax, r15
0x1800056e2  jmp     short loc_1800056FA
0x1800056e4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800056e8  inc     rax
0x1800056eb  cmp     [rcx+rax*2], r15w
0x1800056f0  jnz     short loc_1800056E8
0x1800056f2  lea     rax, ds:2[rax*2]
0x1800056fa  mov     [rsp+110h+cbData], eax; cbData
0x1800056fe  lea     rdx, aProductId; "Product ID"
0x180005705  mov     [rsp+110h+lpData], rcx; lpData
0x18000570a  mov     r9d, esi; dwType
0x18000570d  mov     rcx, [rbp+57h+hKey]; hKey
0x180005711  xor     r8d, r8d; Reserved
0x180005714  call    cs:__imp_RegSetValueExW
0x18000571a  mov     edi, eax
0x18000571c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005720  mov     rcx, [rbx+98h]
0x180005727  test    rcx, rcx
0x18000572a  jz      short loc_180005767
0x18000572c  test    edi, edi
0x18000572e  jnz     loc_180005973
0x180005734  inc     rax
0x180005737  cmp     [rcx+rax*2], r15w
  ... truncated ...
```
