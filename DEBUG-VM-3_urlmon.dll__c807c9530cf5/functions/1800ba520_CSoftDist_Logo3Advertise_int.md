# CSoftDist::Logo3Advertise(int)

- ea: `0x1800ba520`
- end: `0x1800ba8ed`
- name: `?Logo3Advertise@CSoftDist@@AEAAJH@Z`
- size: `973`
- prototype: `__int64 __fastcall(CSoftDist *__hidden this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b7a58`

## callees

- `0x1800150e0`
- `0x180030880`
- `0x180044b84`
- `0x1800b8df0`
- `0x1800ba520`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800ba5cb`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800ba60d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800ba5cb`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800ba60d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800ba58e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800ba62b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800ba69a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800ba58e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800ba62b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800ba69a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800ba74a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800ba796`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800ba7d8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800ba81a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800ba856`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800ba74a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800ba796`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800ba7d8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800ba81a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800ba856`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ba895`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ba8a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ba8b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ba895`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ba8a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ba8b5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800ba876`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800ba876`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800ba664`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800ba6d7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800ba664`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800ba6d7`

## string_xrefs

- `0x1800ba580`: `Software\Microsoft\Windows\CurrentVersion\Uninstall`
- `0x1800ba86f`: `Precache`

## pseudocode

```c
__int64 __fastcall CSoftDist::Logo3Advertise(CSoftDist *this, int a2)
{
  CHAR *v4; // r14
  LSTATUS v5; // ebx
  __int64 v6; // rsi
  size_t cbMultiByte; // rbx
  CHAR *v8; // rax
  LSTATUS v9; // eax
  bool v10; // cc
  __int64 v11; // rax
  const BYTE *v12; // rcx
  __int64 v13; // rax
  const BYTE *v14; // rcx
  __int64 v15; // rax
  const BYTE *v16; // rcx
  bool v17; // cc
  HKEY v19; // [rsp+50h] [rbp-B0h] BYREF
  BYTE v20[8]; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[272]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  phkResult = 0;
  v19 = 0;
  *(_DWORD *)v20 = 0;
  if ( RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\Windows\\CurrentVersion\\Uninstall", 0, 0xF003Fu, &hKey) )
  {
    v4 = 0;
    v5 = -2147467259;
    goto LABEL_34;
  }
  v6 = -1;
  cbMultiByte = (unsigned int)WideCharToMultiByte(0, 0x400u, *((LPCWCH *)this + 2), -1, 0, 0, 0, 0);
  v8 = (CHAR *)operator new(cbMultiByte);
  v4 = v8;
  if ( !v8 )
  {
    v5 = -2147024882;
    goto LABEL_34;
  }
  WideCharToMultiByte(0, 0x400u, *((LPCWCH *)this + 2), -1, v8, cbMultiByte, 0, 0);
  if ( RegOpenKeyExA(hKey, v4, 0, 0xF003Fu, &phkResult)
    && (v9 = RegCreateKeyExA(hKey, v4, 0, 0, 0, 0x2000000u, 0, &phkResult, 0), v5 = v9, v10 = v9 <= 0, v9)
    || RegOpenKeyExA(phkResult, "AvailableVersion", 0, 0xF003Fu, &v19)
    && (v9 = RegCreateKeyExA(phkResult, "AvailableVersion", 0, 0, 0, 0x2000000u, 0, &v19, 0), v5 = v9, v10 = v9 <= 0, v9) )
  {
    if ( v10 )
      goto LABEL_34;
    v5 = (unsigned __int16)v9;
LABEL_33:
    v5 |= 0x80070000;
    goto LABEL_34;
  }
  StringCchPrintfA(
    (char *)Data,
    0x104u,
    "%d,%d,%d,%d",
    *((unsigned __int16 *)this + 13),
    *((unsigned __int16 *)this + 12),
    *((unsigned __int16 *)this + 15),
    *((unsigned __int16 *)this + 14));
  v11 = -1;
  do
    ++v11;
  while ( Data[v11] );
  v5 = RegSetValueExA(v19, 0, 0, 1u, Data, v11 + 1);
  if ( a2 || IsAbstractDifferent(v19, *((char **)this + 9)) )
  {
    *(_DWORD *)v20 = 0;
    v5 = RegSetValueExA(v19, "AdState", 0, 4u, v20, 4u);
    if ( v5 )
      goto LABEL_30;
    v12 = (const BYTE *)*((_QWORD *)this + 10);
    if ( v12 )
    {
      v13 = -1;
      do
        ++v13;
      while ( v12[v13] );
      v5 = RegSetValueExA(v19, "HREF", 0, 1u, v12, v13 + 1);
      if ( v5 )
        goto LABEL_30;
    }
    v14 = (const BYTE *)*((_QWORD *)this + 9);
    if ( v14 )
    {
      v15 = -1;
      do
        ++v15;
      while ( v14[v15] );
      v5 = RegSetValueExA(v19, "Abstract", 0, 1u, v14, v15 + 1);
      if ( v5 )
      {
LABEL_30:
        v17 = v5 <= 0;
        goto LABEL_31;
      }
    }
    v16 = (const BYTE *)*((_QWORD *)this + 7);
    if ( !v16 )
      goto LABEL_28;
    do
      ++v6;
    while ( v16[v6] );
    v5 = RegSetValueExA(v19, "Title", 0, 1u, v16, v6 + 1);
  }
  v17 = v5 <= 0;
  if ( v5 )
  {
LABEL_31:
    if ( v17 )
      goto LABEL_34;
    v5 = (unsigned __int16)v5;
    goto LABEL_33;
  }
LABEL_28:
  v5 = 0;
  if ( a2 )
    RegDeleteValueA(v19, "Precache");
LABEL_34:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v19 )
    RegCloseKey(v19);
  if ( v4 )
    operator delete(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800ba520  push    rbp
0x1800ba522  push    rbx
0x1800ba523  push    rsi
0x1800ba524  push    rdi
0x1800ba525  push    r12
0x1800ba527  push    r13
0x1800ba529  push    r14
0x1800ba52b  push    r15
0x1800ba52d  lea     rbp, [rsp-98h]
0x1800ba535  sub     rsp, 198h
0x1800ba53c  mov     rax, cs:__security_cookie
0x1800ba543  xor     rax, rsp
0x1800ba546  mov     [rbp+0D0h+var_50], rax
0x1800ba54d  xor     r12d, r12d
0x1800ba550  lea     rax, [rsp+1D0h+hKey]
0x1800ba555  mov     r15d, edx
0x1800ba558  mov     [rsp+1D0h+hKey], r12
0x1800ba55d  mov     rdi, rcx
0x1800ba560  mov     [rsp+1D0h+var_170], r12
0x1800ba565  mov     r13d, 0F003Fh
0x1800ba56b  mov     [rsp+1D0h+var_180], r12
0x1800ba570  mov     r9d, r13d; samDesired
0x1800ba573  mov     dword ptr [rsp+1D0h+var_178], r12d
0x1800ba578  xor     r8d, r8d; ulOptions
0x1800ba57b  mov     [rsp+1D0h+phkResult], rax; phkResult
0x1800ba580  lea     rdx, aSoftwareMicros_77; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800ba587  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ba58e  call    cs:__imp_RegOpenKeyExA
0x1800ba594  test    eax, eax
0x1800ba596  jz      short loc_1800BA5A5
0x1800ba598  mov     r14d, r12d
0x1800ba59b  mov     ebx, 80004005h
0x1800ba5a0  jmp     loc_1800BA88B
0x1800ba5a5  mov     r8, [rdi+10h]; lpWideCharStr
0x1800ba5a9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800ba5ad  mov     [rsp+1D0h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x1800ba5b2  mov     r9d, esi; cchWideChar
0x1800ba5b5  mov     [rsp+1D0h+lpDefaultChar], r12; lpDefaultChar
0x1800ba5ba  mov     edx, 400h; dwFlags
0x1800ba5bf  mov     [rsp+1D0h+cbMultiByte], r12d; cbMultiByte
0x1800ba5c4  xor     ecx, ecx; CodePage
0x1800ba5c6  mov     [rsp+1D0h+phkResult], r12; lpMultiByteStr
0x1800ba5cb  call    cs:__imp_WideCharToMultiByte
0x1800ba5d1  mov     ecx, eax; Size
0x1800ba5d3  mov     ebx, eax
0x1800ba5d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ba5da  mov     r14, rax
0x1800ba5dd  test    rax, rax
0x1800ba5e0  jnz     short loc_1800BA5EC
0x1800ba5e2  mov     ebx, 8007000Eh
0x1800ba5e7  jmp     loc_1800BA88B
0x1800ba5ec  mov     r8, [rdi+10h]; lpWideCharStr
0x1800ba5f0  mov     r9d, esi; cchWideChar
0x1800ba5f3  mov     [rsp+1D0h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x1800ba5f8  mov     edx, 400h; dwFlags
0x1800ba5fd  mov     [rsp+1D0h+lpDefaultChar], r12; lpDefaultChar
0x1800ba602  xor     ecx, ecx; CodePage
0x1800ba604  mov     [rsp+1D0h+cbMultiByte], ebx; cbMultiByte
0x1800ba608  mov     [rsp+1D0h+phkResult], r14; lpMultiByteStr
0x1800ba60d  call    cs:__imp_WideCharToMultiByte
0x1800ba613  mov     rcx, [rsp+1D0h+hKey]; hKey
0x1800ba618  lea     rax, [rsp+1D0h+var_170]
0x1800ba61d  mov     r9d, r13d; samDesired
0x1800ba620  mov     [rsp+1D0h+phkResult], rax; phkResult
0x1800ba625  xor     r8d, r8d; ulOptions
0x1800ba628  mov     rdx, r14; lpSubKey
0x1800ba62b  call    cs:__imp_RegOpenKeyExA
0x1800ba631  test    eax, eax
0x1800ba633  jz      short loc_1800BA67E
0x1800ba635  mov     rcx, [rsp+1D0h+hKey]; hKey
0x1800ba63a  lea     rax, [rsp+1D0h+var_170]
0x1800ba63f  mov     [rsp+1D0h+lpdwDisposition], r12; lpdwDisposition
0x1800ba644  xor     r9d, r9d; lpClass
0x1800ba647  mov     [rsp+1D0h+lpUsedDefaultChar], rax; phkResult
0x1800ba64c  xor     r8d, r8d; Reserved
0x1800ba64f  mov     [rsp+1D0h+lpDefaultChar], r12; lpSecurityAttributes
0x1800ba654  mov     rdx, r14; lpSubKey
0x1800ba657  mov     [rsp+1D0h+cbMultiByte], 2000000h; samDesired
0x1800ba65f  mov     dword ptr [rsp+1D0h+phkResult], r12d; dwOptions
0x1800ba664  call    cs:__imp_RegCreateKeyExA
0x1800ba66a  mov     ebx, eax
0x1800ba66c  test    eax, eax
0x1800ba66e  jz      short loc_1800BA67E
0x1800ba670  jle     loc_1800BA88B
0x1800ba676  movzx   ebx, ax
0x1800ba679  jmp     loc_1800BA885
0x1800ba67e  mov     rcx, [rsp+1D0h+var_170]; hKey
0x1800ba683  lea     rax, [rsp+1D0h+var_180]
0x1800ba688  mov     r9d, r13d; samDesired
0x1800ba68b  mov     [rsp+1D0h+phkResult], rax; phkResult
0x1800ba690  xor     r8d, r8d; ulOptions
0x1800ba693  lea     rdx, aAvailableversi; "AvailableVersion"
0x1800ba69a  call    cs:__imp_RegOpenKeyExA
0x1800ba6a0  test    eax, eax
0x1800ba6a2  jz      short loc_1800BA6E3
0x1800ba6a4  mov     rcx, [rsp+1D0h+var_170]; hKey
0x1800ba6a9  lea     rax, [rsp+1D0h+var_180]
0x1800ba6ae  mov     [rsp+1D0h+lpdwDisposition], r12; lpdwDisposition
0x1800ba6b3  lea     rdx, aAvailableversi; "AvailableVersion"
0x1800ba6ba  mov     [rsp+1D0h+lpUsedDefaultChar], rax; phkResult
0x1800ba6bf  xor     r9d, r9d; lpClass
0x1800ba6c2  mov     [rsp+1D0h+lpDefaultChar], r12; lpSecurityAttributes
0x1800ba6c7  xor     r8d, r8d; Reserved
0x1800ba6ca  mov     [rsp+1D0h+cbMultiByte], 2000000h; samDesired
0x1800ba6d2  mov     dword ptr [rsp+1D0h+phkResult], r12d; dwOptions
0x1800ba6d7  call    cs:__imp_RegCreateKeyExA
0x1800ba6dd  mov     ebx, eax
0x1800ba6df  test    eax, eax
0x1800ba6e1  jnz     short loc_1800BA670
0x1800ba6e3  movzx   ecx, word ptr [rdi+1Ch]
0x1800ba6e7  lea     r8, aDDDD_0; "%d,%d,%d,%d"
0x1800ba6ee  movzx   edx, word ptr [rdi+1Eh]
0x1800ba6f2  movzx   eax, word ptr [rdi+18h]
0x1800ba6f6  movzx   r9d, word ptr [rdi+1Ah]
0x1800ba6fb  mov     dword ptr [rsp+1D0h+lpDefaultChar], ecx
0x1800ba6ff  lea     rcx, [rsp+1D0h+Data]; char *
0x1800ba704  mov     [rsp+1D0h+cbMultiByte], edx
0x1800ba708  mov     edx, 104h; unsigned __int64
0x1800ba70d  mov     dword ptr [rsp+1D0h+phkResult], eax
0x1800ba711  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800ba716  lea     rcx, [rsp+1D0h+Data]
0x1800ba71b  mov     rax, rsi
0x1800ba71e  inc     rax
0x1800ba721  cmp     [rcx+rax], r12b
0x1800ba725  jnz     short loc_1800BA71E
0x1800ba727  mov     rcx, [rsp+1D0h+var_180]; hKey
0x1800ba72c  inc     eax
0x1800ba72e  mov     [rsp+1D0h+cbMultiByte], eax; cbData
0x1800ba732  mov     r13d, 1
0x1800ba738  lea     rax, [rsp+1D0h+Data]
0x1800ba73d  mov     r9d, r13d; dwType
0x1800ba740  xor     r8d, r8d; Reserved
0x1800ba743  mov     [rsp+1D0h+phkResult], rax; lpData
0x1800ba748  xor     edx, edx; lpValueName
0x1800ba74a  call    cs:__imp_RegSetValueExA
0x1800ba750  mov     ebx, eax
0x1800ba752  test    r15d, r15d
0x1800ba755  jnz     short loc_1800BA76D
0x1800ba757  mov     rdx, [rdi+48h]; char *
0x1800ba75b  mov     rcx, [rsp+1D0h+var_180]; HKEY
0x1800ba760  call    ?IsAbstractDifferent@@YAHPEAUHKEY__@@PEAD@Z; IsAbstractDifferent(HKEY__ *,char *)
0x1800ba765  test    eax, eax
0x1800ba767  jz      loc_1800BA85E
0x1800ba76d  mov     rcx, [rsp+1D0h+var_180]; hKey
0x1800ba772  lea     rax, [rsp+1D0h+var_178]
0x1800ba777  mov     r9d, 4; dwType
0x1800ba77d  mov     dword ptr [rsp+1D0h+var_178], r12d
0x1800ba782  mov     [rsp+1D0h+cbMultiByte], r9d; cbData
0x1800ba787  lea     rdx, aAdstate; "AdState"
0x1800ba78e  xor     r8d, r8d; Reserved
0x1800ba791  mov     [rsp+1D0h+phkResult], rax; lpData
0x1800ba796  call    cs:__imp_RegSetValueExA
0x1800ba79c  mov     ebx, eax
0x1800ba79e  test    eax, eax
0x1800ba7a0  jnz     loc_1800BA87E
0x1800ba7a6  mov     rcx, [rdi+50h]
0x1800ba7aa  test    rcx, rcx
0x1800ba7ad  jz      short loc_1800BA7E8
0x1800ba7af  mov     rax, rsi
0x1800ba7b2  inc     rax
0x1800ba7b5  cmp     [rcx+rax], r12b
0x1800ba7b9  jnz     short loc_1800BA7B2
0x1800ba7bb  inc     eax
0x1800ba7bd  lea     rdx, aHref; "HREF"
0x1800ba7c4  mov     [rsp+1D0h+cbMultiByte], eax; cbData
0x1800ba7c8  mov     r9d, r13d; dwType
0x1800ba7cb  mov     [rsp+1D0h+phkResult], rcx; lpData
0x1800ba7d0  xor     r8d, r8d; Reserved
0x1800ba7d3  mov     rcx, [rsp+1D0h+var_180]; hKey
0x1800ba7d8  call    cs:__imp_RegSetValueExA
0x1800ba7de  mov     ebx, eax
0x1800ba7e0  test    eax, eax
0x1800ba7e2  jnz     loc_1800BA87E
0x1800ba7e8  mov     rcx, [rdi+48h]
0x1800ba7ec  test    rcx, rcx
0x1800ba7ef  jz      short loc_1800BA826
0x1800ba7f1  mov     rax, rsi
0x1800ba7f4  inc     rax
0x1800ba7f7  cmp     [rcx+rax], r12b
0x1800ba7fb  jnz     short loc_1800BA7F4
0x1800ba7fd  inc     eax
0x1800ba7ff  lea     rdx, aAbstract_0; "Abstract"
0x1800ba806  mov     [rsp+1D0h+cbMultiByte], eax; cbData
0x1800ba80a  mov     r9d, r13d; dwType
0x1800ba80d  mov     [rsp+1D0h+phkResult], rcx; lpData
0x1800ba812  xor     r8d, r8d; Reserved
0x1800ba815  mov     rcx, [rsp+1D0h+var_180]; hKey
0x1800ba81a  call    cs:__imp_RegSetValueExA
0x1800ba820  mov     ebx, eax
0x1800ba822  test    eax, eax
0x1800ba824  jnz     short loc_1800BA87E
0x1800ba826  mov     rcx, [rdi+38h]
0x1800ba82a  test    rcx, rcx
0x1800ba82d  jz      short loc_1800BA862
0x1800ba82f  inc     rsi
0x1800ba832  cmp     [rcx+rsi], r12b
0x1800ba836  jnz     short loc_1800BA82F
0x1800ba838  lea     eax, [rsi+1]
0x1800ba83b  mov     r9d, r13d; dwType
0x1800ba83e  mov     [rsp+1D0h+cbMultiByte], eax; cbData
0x1800ba842  lea     rdx, aTitle_2; "Title"
0x1800ba849  mov     [rsp+1D0h+phkResult], rcx; lpData
0x1800ba84e  xor     r8d, r8d; Reserved
0x1800ba851  mov     rcx, [rsp+1D0h+var_180]; hKey
0x1800ba856  call    cs:__imp_RegSetValueExA
0x1800ba85c  mov     ebx, eax
0x1800ba85e  test    ebx, ebx
0x1800ba860  jnz     short loc_1800BA880
0x1800ba862  mov     ebx, r12d
0x1800ba865  test    r15d, r15d
0x1800ba868  jz      short loc_1800BA88B
0x1800ba86a  mov     rcx, [rsp+1D0h+var_180]; hKey
0x1800ba86f  lea     rdx, aPrecache_0; "Precache"
0x1800ba876  call    cs:__imp_RegDeleteValueA
0x1800ba87c  jmp     short loc_1800BA88B
0x1800ba87e  test    ebx, ebx
0x1800ba880  jle     short loc_1800BA88B
0x1800ba882  movzx   ebx, bx
0x1800ba885  or      ebx, 80070000h
0x1800ba88b  mov     rcx, [rsp+1D0h+hKey]; hKey
0x1800ba890  test    rcx, rcx
0x1800ba893  jz      short loc_1800BA89B
0x1800ba895  call    cs:__imp_RegCloseKey
0x1800ba89b  mov     rcx, [rsp+1D0h+var_170]; hKey
0x1800ba8a0  test    rcx, rcx
0x1800ba8a3  jz      short loc_1800BA8AB
0x1800ba8a5  call    cs:__imp_RegCloseKey
0x1800ba8ab  mov     rcx, [rsp+1D0h+var_180]; hKey
0x1800ba8b0  test    rcx, rcx
0x1800ba8b3  jz      short loc_1800BA8BB
0x1800ba8b5  call    cs:__imp_RegCloseKey
0x1800ba8bb  test    r14, r14
0x1800ba8be  jz      short loc_1800BA8C8
0x1800ba8c0  mov     rcx, r14; void *
0x1800ba8c3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ba8c8  mov     eax, ebx
0x1800ba8ca  mov     rcx, [rbp+0D0h+var_50]
0x1800ba8d1  xor     rcx, rsp; StackCookie
0x1800ba8d4  call    __security_check_cookie
0x1800ba8d9  add     rsp, 198h
0x1800ba8e0  pop     r15
0x1800ba8e2  pop     r14
0x1800ba8e4  pop     r13
0x1800ba8e6  pop     r12
0x1800ba8e8  pop     rdi
0x1800ba8e9  pop     rsi
0x1800ba8ea  pop     rbx
0x1800ba8eb  pop     rbp
0x1800ba8ec  retn
```
