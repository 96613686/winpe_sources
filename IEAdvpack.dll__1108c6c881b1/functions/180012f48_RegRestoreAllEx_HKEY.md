# RegRestoreAllEx(HKEY__ *)

- ea: `0x180012f48`
- end: `0x180013277`
- name: `?RegRestoreAllEx@@YAJPEAUHKEY__@@@Z`
- size: `815`
- prototype: `__int64 __fastcall(HKEY)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e060`
- `0x180010ac0`
- `0x1800142d0`

## callees

- `0x180008a6c`
- `0x180012ea0`
- `0x180012f48`
- `0x1800141f4`
- `0x180014440`
- `0x18001b980`

## import_xrefs

- `msvcrt!_wtoi` at `0x180013104`
- `msvcrt!_wtoi` at `0x180013104`
- `KERNEL32!LocalFree` at `0x1800131f7`
- `KERNEL32!LocalFree` at `0x1800131f7`
- `KERNEL32!LocalAlloc` at `0x180012f85`
- `KERNEL32!LocalAlloc` at `0x180012f85`
- `KERNEL32!CompareStringW` at `0x18001302a`
- `KERNEL32!CompareStringW` at `0x18001302a`
- `ADVAPI32!RegCloseKey` at `0x1800131ac`
- `ADVAPI32!RegCloseKey` at `0x1800131ac`
- `ADVAPI32!RegOpenKeyExW` at `0x180013054`
- `ADVAPI32!RegOpenKeyExW` at `0x180013054`
- `ADVAPI32!RegEnumValueW` at `0x18001309b`
- `ADVAPI32!RegEnumValueW` at `0x180013192`
- `ADVAPI32!RegEnumValueW` at `0x18001309b`
- `ADVAPI32!RegEnumValueW` at `0x180013192`
- `ADVAPI32!RegEnumKeyW` at `0x180012fde`
- `ADVAPI32!RegEnumKeyW` at `0x1800131dc`
- `ADVAPI32!RegEnumKeyW` at `0x180013237`
- `ADVAPI32!RegEnumKeyW` at `0x180012fde`
- `ADVAPI32!RegEnumKeyW` at `0x1800131dc`
- `ADVAPI32!RegEnumKeyW` at `0x180013237`
- `ADVAPI32!RegDeleteKeyW` at `0x18001321c`
- `ADVAPI32!RegDeleteKeyW` at `0x18001321c`
- `SHLWAPI!StrChrW` at `0x180012ff9`
- `SHLWAPI!StrChrW` at `0x180012ff9`

## pseudocode

```c
__int64 __fastcall RegRestoreAllEx(HKEY a1)
{
  BYTE *lpData; // r14
  DWORD v4; // r15d
  int v5; // esi
  LSTATUS i; // eax
  const WCHAR *v7; // rax
  int v8; // r13d
  LSTATUS v9; // ebx
  unsigned __int16 v10; // bx
  const wchar_t *NextToken; // r12
  const WCHAR *v12; // rbx
  DWORD v13; // eax
  HRESULT v14; // eax
  int v15; // ecx
  int v16; // eax
  int v17; // r15d
  DWORD v18; // ebx
  DWORD j; // edx
  LSTATUS v20; // ecx
  int v21; // eax
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD v24; // [rsp+48h] [rbp-B8h]
  BYTE *v25; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR pcszSubKey; // [rsp+60h] [rbp-A0h]
  LPCWSTR pcszRootKey; // [rsp+68h] [rbp-98h]
  WCHAR Name[32]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ValueName[32]; // [rsp+B0h] [rbp-50h] BYREF

  phkResult = 0;
  lpData = (BYTE *)LocalAlloc(0x40u, 0xC00u);
  if ( lpData )
  {
    v4 = 0;
    v5 = 1;
    v24 = 0;
    for ( i = RegEnumKeyW(a1, 0, Name, 0x20u); !i; i = RegEnumKeyW(a1, v4, Name, 0x20u) )
    {
      v7 = StrChrW(Name, 0x2Eu);
      if ( v7 && CompareStringW(0x7Fu, 1u, v7, -1, L".map", -1) == 2 )
      {
        if ( RegOpenKeyExW(a1, Name, 0, 0x20019u, &phkResult) )
        {
          v5 = 0;
        }
        else
        {
          v8 = 0;
          cchValueName = 32;
          cbData = 3072;
          v9 = RegEnumValueW(phkResult, 0, ValueName, &cchValueName, 0, 0, lpData, &cbData);
          if ( !v9 )
          {
            do
            {
              v10 = *(_WORD *)lpData;
              v25 = lpData + 2;
              NextToken = (const wchar_t *)GetNextToken(&v25, v10);
              pcszRootKey = (LPCWSTR)GetNextToken(&v25, v10);
              pcszSubKey = (LPCWSTR)GetNextToken(&v25, v10);
              v12 = (const WCHAR *)GetNextToken(&v25, v10);
              if ( NextToken )
                v13 = _wtoi(NextToken);
              else
                v13 = 0;
              v14 = RegSaveRestoreW(hWnd, pszTitleString, a1, pcszRootKey, pcszSubKey, v12, v13);
              cbData = 3072;
              if ( v14 < 0 )
                v5 = 0;
              v15 = v8 - 1;
              if ( v14 < 0 )
                v15 = v8;
              cchValueName = 32;
              v8 = v15 + 1;
              v9 = RegEnumValueW(phkResult, v15 + 1, ValueName, &cchValueName, 0, 0, lpData, &cbData);
            }
            while ( !v9 );
            v4 = v24;
          }
          RegCloseKey(phkResult);
          v16 = 0;
          if ( v9 == 259 )
            v16 = v5;
          v5 = v16;
        }
      }
      v24 = ++v4;
    }
    v17 = 0;
    if ( i == 259 )
      v17 = v5;
    LocalFree(lpData);
    v18 = 0;
    for ( j = 0; ; j = v18 )
    {
      v20 = RegEnumKeyW(a1, j, Name, 0x20u);
      if ( v20 )
        break;
      if ( RegKeyEmpty(a1, Name) && !RegDeleteKeyW(a1, Name) )
        --v18;
      ++v18;
    }
    v21 = 0;
    if ( v20 == 259 )
      v21 = v17;
    return v21 == 0 ? 0x80004005 : 0;
  }
  else
  {
    MsgBox2Param(hWnd, 0x44Eu, 0, 0, 0x10u, 0);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180012f48  push    rbp
0x180012f4a  push    rbx
0x180012f4b  push    rsi
0x180012f4c  push    rdi
0x180012f4d  push    r12
0x180012f4f  push    r13
0x180012f51  push    r14
0x180012f53  push    r15
0x180012f55  lea     rbp, [rsp-8]
0x180012f5a  sub     rsp, 108h
0x180012f61  mov     rax, cs:__security_cookie
0x180012f68  xor     rax, rsp
0x180012f6b  mov     [rbp+40h+var_50], rax
0x180012f6f  mov     rdi, rcx
0x180012f72  mov     [rsp+140h+phkResult], 0
0x180012f7b  mov     ecx, 40h ; '@'; uFlags
0x180012f80  mov     edx, 0C00h; uBytes
0x180012f85  call    cs:__imp_LocalAlloc
0x180012f8b  mov     r14, rax
0x180012f8e  test    rax, rax
0x180012f91  jnz     short loc_180012FC0
0x180012f93  mov     rcx, cs:hWnd; hWnd
0x180012f9a  xor     r9d, r9d; unsigned __int16 *
0x180012f9d  mov     [rsp+140h+cchCount2], eax; unsigned int
0x180012fa1  xor     r8d, r8d; unsigned __int16 *
0x180012fa4  mov     edx, 44Eh; uID
0x180012fa9  mov     dword ptr [rsp+140h+lpString2], 10h; unsigned int
0x180012fb1  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x180012fb6  mov     eax, 80004005h
0x180012fbb  jmp     loc_180013257
0x180012fc0  xor     r15d, r15d
0x180012fc3  lea     r8, [rsp+140h+Name]; lpName
0x180012fc8  mov     esi, 1
0x180012fcd  mov     [rsp+140h+var_F8], r15d
0x180012fd2  xor     edx, edx; dwIndex
0x180012fd4  mov     rcx, rdi; hKey
0x180012fd7  lea     r12d, [rsi+1Fh]
0x180012fdb  mov     r9d, r12d; cchName
0x180012fde  call    cs:__imp_RegEnumKeyW
0x180012fe4  mov     r13d, 103h
0x180012fea  jmp     loc_1800131E2
0x180012fef  mov     edx, 2Eh ; '.'; wMatch
0x180012ff4  lea     rcx, [rsp+140h+Name]; pszStart
0x180012ff9  call    cs:__imp_StrChrW
0x180012fff  test    rax, rax
0x180013002  jz      loc_1800131C6
0x180013008  lea     rcx, aMap; ".map"
0x18001300f  mov     [rsp+140h+cchCount2], 0FFFFFFFFh; cchCount2
0x180013017  or      r9d, 0FFFFFFFFh; cchCount1
0x18001301b  mov     [rsp+140h+lpString2], rcx; lpString2
0x180013020  mov     r8, rax; lpString1
0x180013023  lea     edx, [r9+2]; dwCmpFlags
0x180013027  lea     ecx, [rdx+7Eh]; Locale
0x18001302a  call    cs:__imp_CompareStringW
0x180013030  cmp     eax, 2
0x180013033  jnz     loc_1800131C6
0x180013039  lea     rax, [rsp+140h+phkResult]
0x18001303e  mov     r9d, 20019h; samDesired
0x180013044  xor     r8d, r8d; ulOptions
0x180013047  mov     [rsp+140h+lpString2], rax; phkResult
0x18001304c  lea     rdx, [rsp+140h+Name]; lpSubKey
0x180013051  mov     rcx, rdi; hKey
0x180013054  call    cs:__imp_RegOpenKeyExW
0x18001305a  test    eax, eax
0x18001305c  jnz     loc_1800131C4
0x180013062  mov     rcx, [rsp+140h+phkResult]; hKey
0x180013067  lea     rax, [rsp+140h+cbData]
0x18001306c  mov     [rsp+140h+lpcbData], rax; lpcbData
0x180013071  lea     r9, [rsp+140h+cchValueName]; lpcchValueName
0x180013076  xor     r13d, r13d
0x180013079  mov     [rsp+140h+lpData], r14; lpData
0x18001307e  mov     qword ptr [rsp+140h+cchCount2], r13; lpType
0x180013083  lea     r8, [rbp+40h+ValueName]; lpValueName
0x180013087  xor     edx, edx; dwIndex
0x180013089  mov     [rsp+140h+lpString2], r13; lpReserved
0x18001308e  mov     [rsp+140h+cchValueName], r12d
0x180013093  mov     [rsp+140h+cbData], 0C00h
0x18001309b  call    cs:__imp_RegEnumValueW
0x1800130a1  mov     ebx, eax
0x1800130a3  test    eax, eax
0x1800130a5  jnz     loc_1800131A7
0x1800130ab  lea     r15, [r14+2]
0x1800130af  movzx   ebx, word ptr [r14]
0x1800130b3  lea     rcx, [rsp+140h+var_F0]
0x1800130b8  movzx   edx, bx
0x1800130bb  mov     [rsp+140h+var_F0], r15
0x1800130c0  call    GetNextToken
0x1800130c5  movzx   edx, bx
0x1800130c8  lea     rcx, [rsp+140h+var_F0]
0x1800130cd  mov     r12, rax
0x1800130d0  call    GetNextToken
0x1800130d5  movzx   edx, bx
0x1800130d8  mov     [rsp+140h+pcszRootKey], rax
0x1800130dd  lea     rcx, [rsp+140h+var_F0]
0x1800130e2  call    GetNextToken
0x1800130e7  movzx   edx, bx
0x1800130ea  mov     [rsp+140h+pcszSubKey], rax
0x1800130ef  lea     rcx, [rsp+140h+var_F0]
0x1800130f4  call    GetNextToken
0x1800130f9  mov     rbx, rax
0x1800130fc  test    r12, r12
0x1800130ff  jz      short loc_18001310C
0x180013101  mov     rcx, r12; String
0x180013104  call    cs:__imp__wtoi
0x18001310a  jmp     short loc_18001310E
0x18001310c  xor     eax, eax
0x18001310e  mov     r9, [rsp+140h+pcszRootKey]; pcszRootKey
0x180013113  mov     r8, rdi; hkBckupKey
0x180013116  mov     rdx, cs:pszTitleString; pszTitleString
0x18001311d  mov     rcx, cs:hWnd; hWnd
0x180013124  mov     dword ptr [rsp+140h+lpData], eax; dwFlags
0x180013128  mov     rax, [rsp+140h+pcszSubKey]
0x18001312d  mov     qword ptr [rsp+140h+cchCount2], rbx; pcszValueName
0x180013132  mov     [rsp+140h+lpString2], rax; pcszSubKey
0x180013137  call    RegSaveRestoreW
0x18001313c  xor     ecx, ecx
0x18001313e  mov     [rsp+140h+cbData], 0C00h
0x180013146  test    eax, eax
0x180013148  lea     r9, [rsp+140h+cchValueName]; lpcchValueName
0x18001314d  lea     rax, [rsp+140h+cbData]
0x180013152  cmovs   esi, ecx
0x180013155  mov     [rsp+140h+lpcbData], rax; lpcbData
0x18001315a  lea     r12d, [rcx+20h]
0x18001315e  mov     [rsp+140h+lpData], r14; lpData
0x180013163  lea     ecx, [r13-1]
0x180013167  mov     qword ptr [rsp+140h+cchCount2], 0; lpType
0x180013170  cmovs   ecx, r13d
0x180013174  mov     [rsp+140h+cchValueName], r12d
0x180013179  lea     r8, [rbp+40h+ValueName]; lpValueName
0x18001317d  mov     [rsp+140h+lpString2], 0; lpReserved
0x180013186  lea     r13d, [rcx+1]
0x18001318a  mov     rcx, [rsp+140h+phkResult]; hKey
0x18001318f  mov     edx, r13d; dwIndex
0x180013192  call    cs:__imp_RegEnumValueW
0x180013198  mov     ebx, eax
0x18001319a  test    eax, eax
0x18001319c  jz      loc_1800130AF
0x1800131a2  mov     r15d, [rsp+140h+var_F8]
0x1800131a7  mov     rcx, [rsp+140h+phkResult]; hKey
0x1800131ac  call    cs:__imp_RegCloseKey
0x1800131b2  xor     eax, eax
0x1800131b4  mov     r13d, 103h
0x1800131ba  cmp     ebx, r13d
0x1800131bd  cmovz   eax, esi
0x1800131c0  mov     esi, eax
0x1800131c2  jmp     short loc_1800131C6
0x1800131c4  xor     esi, esi
0x1800131c6  inc     r15d
0x1800131c9  lea     r8, [rsp+140h+Name]; lpName
0x1800131ce  mov     edx, r15d; dwIndex
0x1800131d1  mov     [rsp+140h+var_F8], r15d
0x1800131d6  mov     r9d, r12d; cchName
0x1800131d9  mov     rcx, rdi; hKey
0x1800131dc  call    cs:__imp_RegEnumKeyW
0x1800131e2  test    eax, eax
0x1800131e4  jz      loc_180012FEF
0x1800131ea  xor     r15d, r15d
0x1800131ed  mov     rcx, r14; hMem
0x1800131f0  cmp     eax, r13d
0x1800131f3  cmovz   r15d, esi
0x1800131f7  call    cs:__imp_LocalFree
0x1800131fd  xor     ebx, ebx
0x1800131ff  xor     edx, edx
0x180013201  jmp     short loc_18001322C
0x180013203  lea     rdx, [rsp+140h+Name]; unsigned __int16 *
0x180013208  mov     rcx, rdi; HKEY
0x18001320b  call    ?RegKeyEmpty@@YAHPEAUHKEY__@@PEBG@Z; RegKeyEmpty(HKEY__ *,ushort const *)
0x180013210  test    eax, eax
0x180013212  jz      short loc_180013228
0x180013214  lea     rdx, [rsp+140h+Name]; lpSubKey
0x180013219  mov     rcx, rdi; hKey
0x18001321c  call    cs:__imp_RegDeleteKeyW
0x180013222  test    eax, eax
0x180013224  jnz     short loc_180013228
0x180013226  dec     ebx
0x180013228  inc     ebx
0x18001322a  mov     edx, ebx; dwIndex
0x18001322c  mov     r9d, r12d; cchName
0x18001322f  lea     r8, [rsp+140h+Name]; lpName
0x180013234  mov     rcx, rdi; hKey
0x180013237  call    cs:__imp_RegEnumKeyW
0x18001323d  mov     ecx, eax
0x18001323f  test    eax, eax
0x180013241  jz      short loc_180013203
0x180013243  xor     eax, eax
0x180013245  cmp     ecx, r13d
0x180013248  cmovz   eax, r15d
0x18001324c  neg     eax
0x18001324e  sbb     eax, eax
0x180013250  not     eax
0x180013252  and     eax, 80004005h
0x180013257  mov     rcx, [rbp+40h+var_50]
0x18001325b  xor     rcx, rsp; StackCookie
0x18001325e  call    __security_check_cookie
0x180013263  add     rsp, 108h
0x18001326a  pop     r15
0x18001326c  pop     r14
0x18001326e  pop     r13
0x180013270  pop     r12
0x180013272  pop     rdi
0x180013273  pop     rsi
0x180013274  pop     rbx
0x180013275  pop     rbp
0x180013276  retn
```
