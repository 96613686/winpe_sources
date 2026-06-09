# FindAppRegKey(char const *,char *,unsigned __int64 *,bool *,char const *,uint)

- ea: `0x18002b0c0`
- end: `0x18002b1f7`
- name: `?FindAppRegKey@@YA_NPEBDPEADPEA_KPEA_N0I@Z`
- size: `311`
- prototype: `bool __fastcall(const char *, char *, unsigned __int64 *, bool *, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ae44`

## callees

- `0x18002b050`
- `0x18002b0c0`
- `0x180074a78`
- `0x1800bb480`
- `0x180153578`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1802333c5`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1802333c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180233499`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802334e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18023359b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180233499`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802334e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18023359b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180233473`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1802334d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180233473`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1802334d6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x1802333a6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x1802333a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18002b15f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18023342d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18002b15f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18023342d`

## pseudocode

```c
char __fastcall FindAppRegKey(const char *a1, char *a2, unsigned __int64 *a3, bool *a4, char *a5, unsigned int a6)
{
  int v6; // edi
  HKEY v7; // rsi
  HKEY v8; // r12
  __int64 v9; // r14
  char v10; // r15
  _BYTE *v11; // r12
  char *v12; // r13
  DWORD v14; // ebx
  HKEY v15; // r13
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rax
  LSTATUS v18; // ebx
  int v19; // eax
  DWORD v20; // [rsp+40h] [rbp-C0h]
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v23; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[4]; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned __int64 v26; // [rsp+60h] [rbp-A0h]
  HKEY v27; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  __int64 v29; // [rsp+78h] [rbp-88h]
  unsigned __int64 *v30; // [rsp+80h] [rbp-80h]
  bool *v31; // [rsp+88h] [rbp-78h]
  char *v32; // [rsp+90h] [rbp-70h]
  HKEY hKey[2]; // [rsp+98h] [rbp-68h]
  CHAR Name[272]; // [rsp+B0h] [rbp-50h] BYREF
  CHAR SubKey[272]; // [rsp+1C0h] [rbp+C0h] BYREF
  BYTE v36[272]; // [rsp+2D0h] [rbp+1D0h] BYREF
  char v37[272]; // [rsp+3E0h] [rbp+2E0h] BYREF

  v23 = (HKEY)a5;
  v31 = a4;
  v30 = a3;
  v32 = a2;
  if ( !a3 )
    return 0;
  v6 = 0;
  v7 = v23;
  v8 = 0;
  LODWORD(v26) = 261;
  phkResult = 0;
  v9 = 0;
  *(__m128i *)hKey = _mm_load_si128((const __m128i *)&_xmm_ffffffff80000002ffffffff80000001);
  v10 = 1;
  while ( 2 )
  {
    v23 = hKey[v9];
    if ( RegOpenKeyExA(v23, "Software\\Microsoft\\Direct3D\\Direct3D12", 0, 0x20019u, &phkResult) )
      goto LABEL_4;
    v14 = 0;
    v15 = v23;
    while ( 1 )
    {
      cchName = 261;
      if ( RegEnumKeyExA(phkResult, v14, Name, &cchName, 0, 0, 0, 0) )
        break;
      v20 = ++v14;
      if ( !(unsigned int)_o__stricmp(Name, "MostRecentApplication") )
        goto LABEL_33;
      StringCchPrintfA(SubKey, 0x105u, "%s\\%s", "Software\\Microsoft\\Direct3D\\Direct3D12", Name);
      v27 = 0;
      v29 = cchName + 40;
      if ( RegOpenKeyExA(v15, SubKey, 0, 0x20019u, &v27) )
        goto LABEL_33;
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( RegQueryValueExA(v27, "Size", 0, &Type, Data, &cbData)
        || Type != 4
        || !*(_DWORD *)Data
        || *(_DWORD *)Data == a6 )
      {
        cbData = 261;
        v18 = RegQueryValueExA(v27, "Name", 0, &Type, v36, &cbData);
        RegCloseKey(v27);
        if ( v18 || Type != 1 )
          goto LABEL_32;
        v23 = 0;
        v19 = EvaluatePathCandidate(v36, v7, &v23);
        if ( v19 == 1 )
          goto LABEL_30;
        if ( v19 == 2 )
        {
          if ( v6 != 2 )
          {
LABEL_30:
            v8 = v23;
            v6 = v19;
            StringCchCopyA(v37, 0x105u, SubKey);
            LODWORD(v26) = v29;
            if ( (_DWORD)v9 )
              v10 = 0;
          }
LABEL_32:
          v14 = v20;
          goto LABEL_33;
        }
        if ( v19 != 3 || v6 == 2 )
          goto LABEL_32;
        if ( v6 != 3 )
          goto LABEL_30;
        v14 = v20;
        if ( v23 > v8 )
          goto LABEL_30;
      }
      else
      {
        RegCloseKey(v27);
LABEL_33:
        if ( v6 == 1 )
          break;
      }
    }
    RegCloseKey(phkResult);
    if ( v6 != 1 )
    {
LABEL_4:
      v9 = (unsigned int)(v9 + 1);
      if ( (unsigned int)v9 >= 2 )
        break;
      continue;
    }
    break;
  }
  v11 = v31;
  v12 = v32;
  if ( !v6 )
  {
    *v30 = 0;
    return 0;
  }
  v16 = (unsigned int)v26;
  v17 = *v30;
  *v30 = (unsigned int)v26;
  if ( v17 < v16 )
    return 0;
  if ( v12 )
    StringCchCopyA(v12, v16, v37);
  if ( v11 )
    *v11 = v10;
  return 1;
}

```

## disassembly

```asm
0x18002b0c0  mov     [rsp-8+arg_0], rbx
0x18002b0c5  push    rbp
0x18002b0c6  push    rsi
0x18002b0c7  push    rdi
0x18002b0c8  push    r12
0x18002b0ca  push    r13
0x18002b0cc  push    r14
0x18002b0ce  push    r15
0x18002b0d0  lea     rbp, [rsp-400h]
0x18002b0d8  sub     rsp, 500h
0x18002b0df  mov     rax, cs:__security_cookie
0x18002b0e6  xor     rax, rsp
0x18002b0e9  mov     [rbp+430h+var_40], rax
0x18002b0f0  mov     rax, [rbp+430h+arg_20]
0x18002b0f7  mov     [rsp+530h+var_4E0], rax
0x18002b0fc  mov     [rbp+430h+var_4A8], r9
0x18002b100  mov     [rbp+430h+var_4B0], r8
0x18002b104  mov     [rbp+430h+var_4A0], rdx
0x18002b108  test    r8, r8
0x18002b10b  jz      short loc_18002B189
0x18002b10d  movdqa  xmm0, cs:__xmm@ffffffff80000002ffffffff80000001
0x18002b115  xor     edi, edi
0x18002b117  mov     rsi, [rsp+530h+var_4E0]
0x18002b11c  mov     eax, 105h
0x18002b121  xor     r12d, r12d
0x18002b124  mov     dword ptr [rsp+530h+var_4D0], eax
0x18002b128  mov     [rsp+530h+var_4C0], rdi
0x18002b12d  xor     r14d, r14d
0x18002b130  movdqu  xmmword ptr [rbp+430h+hKey], xmm0
0x18002b135  mov     r15b, 1
0x18002b138  mov     rax, [rbp+r14*8+430h+hKey]
0x18002b13d  lea     rcx, [rsp+530h+var_4C0]
0x18002b142  mov     [rsp+530h+phkResult], rcx; phkResult
0x18002b147  lea     rdx, SubKey; "Software\\Microsoft\\Direct3D\\Direct3D"...
0x18002b14e  mov     rcx, rax; hKey
0x18002b151  mov     [rsp+530h+var_4E0], rax
0x18002b156  mov     r9d, 20019h; samDesired
0x18002b15c  xor     r8d, r8d; ulOptions
0x18002b15f  call    cs:__imp_RegOpenKeyExA
0x18002b165  test    eax, eax
0x18002b167  jz      short loc_18002B1B5
0x18002b169  inc     r14d
0x18002b16c  cmp     r14d, 2
0x18002b170  jb      short loc_18002B138
0x18002b172  mov     rsi, [rbp+430h+var_4B0]
0x18002b176  mov     r12, [rbp+430h+var_4A8]
0x18002b17a  mov     r13, [rbp+430h+var_4A0]
0x18002b17e  test    edi, edi
0x18002b180  jnz     short loc_18002B1CA
0x18002b182  mov     qword ptr [rsi], 0
0x18002b189  xor     al, al
0x18002b18b  mov     rcx, [rbp+430h+var_40]
0x18002b192  xor     rcx, rsp; StackCookie
0x18002b195  call    __security_check_cookie
0x18002b19a  mov     rbx, [rsp+530h+arg_0]
0x18002b1a2  add     rsp, 500h
0x18002b1a9  pop     r15
0x18002b1ab  pop     r14
0x18002b1ad  pop     r13
0x18002b1af  pop     r12
0x18002b1b1  pop     rdi
0x18002b1b2  pop     rsi
0x18002b1b3  pop     rbp
0x18002b1b4  retn
0x18002b1b5  xor     ebx, ebx
0x18002b1b7  cmp     edi, 1
0x18002b1ba  jz      loc_180233596
0x18002b1c0  mov     r13, [rsp+530h+var_4E0]
0x18002b1c5  jmp     loc_18023336A
0x18002b1ca  mov     edx, dword ptr [rsp+530h+var_4D0]; unsigned __int64
0x18002b1ce  mov     rax, [rsi]
0x18002b1d1  mov     [rsi], rdx
0x18002b1d4  cmp     rax, rdx
0x18002b1d7  jb      short loc_18002B189
0x18002b1d9  test    r13, r13
0x18002b1dc  jz      loc_1802335AF
0x18002b1e2  lea     r8, [rbp+430h+var_150]; char *
0x18002b1e9  mov     rcx, r13; char *
0x18002b1ec  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18002b1f1  nop
0x18002b1f2  jmp     loc_1802335AF
0x18023336a  mov     rcx, [rsp+530h+var_4C0]; hKey
0x18023336f  lea     r9, [rsp+530h+cchName]; lpcchName
0x180233374  mov     [rsp+530h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18023337d  lea     r8, [rbp+430h+Name]; lpName
0x180233381  mov     [rsp+530h+lpcchClass], 0; lpcchClass
0x18023338a  mov     edx, ebx; dwIndex
0x18023338c  mov     [rsp+530h+lpClass], 0; lpClass
0x180233395  mov     [rsp+530h+phkResult], 0; lpReserved
0x18023339e  mov     [rsp+530h+cchName], 105h
0x1802333a6  call    cs:__imp_RegEnumKeyExA
0x1802333ac  test    eax, eax
0x1802333ae  jnz     loc_180233596
0x1802333b4  inc     ebx
0x1802333b6  lea     rdx, aMostrecentappl; "MostRecentApplication"
0x1802333bd  lea     rcx, [rbp+430h+Name]
0x1802333c1  mov     [rsp+530h+var_4F0], ebx
0x1802333c5  call    cs:__imp__o__stricmp
0x1802333cb  test    eax, eax
0x1802333cd  jz      loc_18023358D
0x1802333d3  lea     rax, [rbp+430h+Name]
0x1802333d7  mov     edx, 105h; unsigned __int64
0x1802333dc  lea     r9, SubKey; "Software\\Microsoft\\Direct3D\\Direct3D"...
0x1802333e3  mov     [rsp+530h+phkResult], rax
0x1802333e8  lea     r8, aSS_3; "%s\\%s"
0x1802333ef  lea     rcx, [rbp+430h+SubKey]; char *
0x1802333f6  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1802333fb  mov     eax, [rsp+530h+cchName]
0x1802333ff  lea     rdx, [rbp+430h+SubKey]; lpSubKey
0x180233406  add     eax, 28h ; '('
0x180233409  mov     [rsp+530h+var_4C8], 0
0x180233412  mov     [rsp+530h+var_4B8], rax
0x180233417  mov     r9d, 20019h; samDesired
0x18023341d  lea     rax, [rsp+530h+var_4C8]
0x180233422  xor     r8d, r8d; ulOptions
0x180233425  mov     rcx, r13; hKey
0x180233428  mov     [rsp+530h+phkResult], rax; phkResult
0x18023342d  call    cs:__imp_RegOpenKeyExA
0x180233433  test    eax, eax
0x180233435  jnz     loc_18023358D
0x18023343b  mov     rcx, [rsp+530h+var_4C8]; hKey
0x180233440  lea     r9, [rsp+530h+Type]; lpType
0x180233445  mov     [rsp+530h+Type], eax
0x180233449  lea     rdx, aSize; "Size"
0x180233450  mov     dword ptr [rsp+530h+Data], eax
0x180233454  xor     r8d, r8d; lpReserved
0x180233457  lea     rax, [rsp+530h+cbData]
0x18023345c  mov     [rsp+530h+cbData], 4
0x180233464  mov     [rsp+530h+lpClass], rax; lpcbData
0x180233469  lea     rax, [rsp+530h+Data]
0x18023346e  mov     [rsp+530h+phkResult], rax; lpData
0x180233473  call    cs:__imp_RegQueryValueExA
0x180233479  test    eax, eax
0x18023347b  jnz     short loc_1802334A4
0x18023347d  cmp     [rsp+530h+Type], 4
0x180233482  jnz     short loc_1802334A4
0x180233484  mov     eax, dword ptr [rsp+530h+Data]
0x180233488  test    eax, eax
0x18023348a  jz      short loc_1802334A4
0x18023348c  cmp     eax, [rbp+430h+arg_28]
0x180233492  jz      short loc_1802334A4
0x180233494  mov     rcx, [rsp+530h+var_4C8]; hKey
0x180233499  call    cs:__imp_RegCloseKey
0x18023349f  jmp     loc_18023358D
0x1802334a4  mov     rcx, [rsp+530h+var_4C8]; hKey
0x1802334a9  lea     rax, [rsp+530h+cbData]
0x1802334ae  mov     [rsp+530h+lpClass], rax; lpcbData
0x1802334b3  lea     r9, [rsp+530h+Type]; lpType
0x1802334b8  lea     rax, [rbp+430h+var_260]
0x1802334bf  mov     [rsp+530h+cbData], 105h
0x1802334c7  xor     r8d, r8d; lpReserved
0x1802334ca  mov     [rsp+530h+phkResult], rax; lpData
0x1802334cf  lea     rdx, aName_1; "Name"
0x1802334d6  call    cs:__imp_RegQueryValueExA
0x1802334dc  mov     rcx, [rsp+530h+var_4C8]; hKey
0x1802334e1  mov     ebx, eax
0x1802334e3  call    cs:__imp_RegCloseKey
0x1802334e9  test    ebx, ebx
0x1802334eb  jnz     loc_180233589
0x1802334f1  cmp     [rsp+530h+Type], 1
0x1802334f6  jnz     loc_180233589
0x1802334fc  lea     r8, [rsp+530h+var_4E0]
0x180233501  mov     [rsp+530h+var_4E0], 0
0x18023350a  mov     rdx, rsi
0x18023350d  lea     rcx, [rbp+430h+var_260]
0x180233514  call    ?EvaluatePathCandidate@@YA?AW4PATH_CANDIDATE_EVALUATION@@PEBD0PEA_K@Z; EvaluatePathCandidate(char const *,char const *,unsigned __int64 *)
0x180233519  mov     ecx, eax
0x18023351b  sub     ecx, 1
0x18023351e  jz      short loc_180233553
0x180233520  sub     ecx, 1
0x180233523  jz      short loc_180233549
0x180233525  cmp     ecx, 1
0x180233528  jnz     short loc_180233589
0x18023352a  cmp     edi, ecx
0x18023352c  jz      short loc_180233596
0x18023352e  cmp     edi, 2
0x180233531  jz      short loc_180233589
0x180233533  cmp     edi, 3
0x180233536  jnz     short loc_180233553
0x180233538  mov     ebx, [rsp+530h+var_4F0]
0x18023353c  cmp     [rsp+530h+var_4E0], r12
0x180233541  jbe     loc_18023336A
0x180233547  jmp     short loc_180233553
0x180233549  cmp     edi, 1
0x18023354c  jz      short loc_180233596
0x18023354e  cmp     edi, 2
0x180233551  jz      short loc_180233589
0x180233553  mov     r12, [rsp+530h+var_4E0]
0x180233558  lea     r8, [rbp+430h+SubKey]; char *
0x18023355f  mov     edx, 105h; unsigned __int64
0x180233564  lea     rcx, [rbp+430h+var_150]; char *
0x18023356b  mov     edi, eax
0x18023356d  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180233572  mov     r10, [rsp+530h+var_4B8]
0x180233577  xor     eax, eax
0x180233579  test    r14d, r14d
0x18023357c  movzx   r15d, r15b
0x180233580  mov     dword ptr [rsp+530h+var_4D0], r10d
0x180233585  cmovnz  r15d, eax
0x180233589  mov     ebx, [rsp+530h+var_4F0]
0x18023358d  cmp     edi, 1
0x180233590  jnz     loc_18023336A
0x180233596  mov     rcx, [rsp+530h+var_4C0]; hKey
0x18023359b  call    cs:__imp_RegCloseKey
0x1802335a1  cmp     edi, 1
0x1802335a4  jz      loc_18002B172
0x1802335aa  jmp     loc_18002B169
0x1802335af  test    r12, r12
0x1802335b2  jz      short loc_1802335B8
0x1802335b4  mov     [r12], r15b
0x1802335b8  mov     al, 1
0x1802335ba  jmp     loc_18002B18B
```
