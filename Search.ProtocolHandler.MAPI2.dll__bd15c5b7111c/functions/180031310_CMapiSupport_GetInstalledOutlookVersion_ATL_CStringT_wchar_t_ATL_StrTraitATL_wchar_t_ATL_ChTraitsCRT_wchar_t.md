# CMapiSupport::GetInstalledOutlookVersion(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)

- ea: `0x180031310`
- end: `0x18003158d`
- name: `?GetInstalledOutlookVersion@CMapiSupport@@SAJAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z`
- size: `637`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x18000f0d0`
- `0x18002ec78`
- `0x18002f9cc`
- `0x1800303a0`
- `0x180031ddc`
- `0x180032328`
- `0x180035e68`

## callees

- `0x180002300`
- `0x18000f1c4`
- `0x180011884`
- `0x1800122d8`
- `0x1800172fc`
- `0x180028938`
- `0x180031310`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031369`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031495`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800314e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031528`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031369`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031495`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800314e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031528`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800313a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800313a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800313b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031555`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800313b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031555`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall CMapiSupport::GetInstalledOutlookVersion(_QWORD *a1)
{
  LSTATUS v2; // eax
  LSTATUS v3; // ebx
  __int64 v4; // r8
  int v5; // eax
  __int64 v6; // rdx
  volatile signed __int32 *v7; // rcx
  int *v8; // rsi
  volatile signed __int32 *v9; // rbx
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  unsigned int v13; // ebx
  DWORD cbData; // [rsp+30h] [rbp-278h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-270h] BYREF
  DWORD Type; // [rsp+40h] [rbp-268h] BYREF
  __int64 v17; // [rsp+48h] [rbp-260h] BYREF
  ATL::CAtlException *v18; // [rsp+50h] [rbp-258h] BYREF
  ATL::CAtlException *v19; // [rsp+60h] [rbp-248h] BYREF
  _WORD Data[264]; // [rsp+70h] [rbp-238h] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"Outlook.Application\\CurVer", 0, 0x20019u, &hKey);
  if ( v2 )
  {
    if ( v2 == 2 )
    {
      v11 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"Outlook.Application.12", 0, 0x20019u, &hKey);
      if ( !v11 )
      {
        try
        {
          v13 = 0;
          ATL::CSimpleStringT<wchar_t,0>::SetString(a1, L"12", 2);
        }
        catch ( ATL::CAtlException *v18 )
        {
          v13 = *(_DWORD *)v18;
          goto LABEL_20;
        }
        catch ( ... )
        {
          indexer::result::details::result_from_caught_exception<0>();
        }
        goto LABEL_20;
      }
      if ( v11 == 2 )
      {
        v12 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"Outlook.Application.11", 0, 0x20019u, &hKey);
        if ( v12 )
        {
          if ( v12 != 2 || RegOpenKeyExW(HKEY_CLASSES_ROOT, L"Outlook.Application.10", 0, 0x20019u, &hKey) )
            return 1;
          try
          {
            v13 = 0;
            ATL::CSimpleStringT<wchar_t,0>::SetString(a1, L"10", 2);
          }
          catch ( ATL::CAtlException *v19 )
          {
            v13 = *(_DWORD *)v19;
          }
          catch ( ... )
          {
            indexer::result::details::result_from_caught_exception<0>();
          }
        }
        else
        {
          v13 = 0;
          ATL::CSimpleStringT<wchar_t,0>::SetString(a1, L"11", 2);
        }
LABEL_20:
        RegCloseKey(hKey);
        return v13;
      }
    }
    return 1;
  }
  Type = 0;
  cbData = 520;
  v3 = RegQueryValueExW(hKey, 0, 0, &Type, (LPBYTE)Data, &cbData);
  RegCloseKey(hKey);
  if ( v3 )
    return 1;
  v4 = -1;
  do
    ++v4;
  while ( Data[v4] );
  ATL::CSimpleStringT<wchar_t,0>::SetString(a1, Data, v4);
  v5 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::ReverseFind(a1, 46);
  if ( v5 <= 0 )
    return 1;
  v6 = *(_QWORD *)ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Right(
                    a1,
                    &v17,
                    (unsigned int)(*(_DWORD *)(*a1 - 16LL) - v5 - 1));
  v7 = (volatile signed __int32 *)(v6 - 24);
  v8 = (int *)(*a1 - 24LL);
  if ( (int *)(v6 - 24) != v8 )
  {
    if ( v8[4] >= 0 && *(_QWORD *)v7 == *(_QWORD *)v8 )
    {
      v9 = ATL::CSimpleStringT<wchar_t,0>::CloneData(v7);
      ATL::CStringData::Release((ATL::CStringData *)v8);
      *a1 = v9 + 6;
    }
    else
    {
      ATL::CSimpleStringT<wchar_t,0>::SetString(a1, v6, *(unsigned int *)(v6 - 16));
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
  return 0;
}

```

## disassembly

```asm
0x180031310  mov     [rsp+arg_8], rbx
0x180031315  mov     [rsp+arg_10], rsi
0x18003131a  push    rdi
0x18003131b  push    r14
0x18003131d  push    r15
0x18003131f  sub     rsp, 290h
0x180031326  mov     rax, cs:__security_cookie
0x18003132d  xor     rax, rsp
0x180031330  mov     [rsp+2A8h+var_28], rax
0x180031338  mov     rdi, rcx
0x18003133b  xor     r14d, r14d
0x18003133e  mov     [rsp+2A8h+hKey], r14
0x180031343  lea     rax, [rsp+2A8h+hKey]
0x180031348  mov     [rsp+2A8h+phkResult], rax; phkResult
0x18003134d  mov     ebx, 20019h
0x180031352  mov     r9d, ebx; samDesired
0x180031355  xor     r8d, r8d; ulOptions
0x180031358  lea     rdx, aOutlookApplica; "Outlook.Application\\CurVer"
0x18003135f  mov     r15, 0FFFFFFFF80000000h
0x180031366  mov     rcx, r15; hKey
0x180031369  call    cs:__imp_RegOpenKeyExW
0x18003136f  test    eax, eax
0x180031371  jnz     loc_18003146E
0x180031377  mov     [rsp+2A8h+Type], r14d
0x18003137c  mov     [rsp+2A8h+cbData], 208h
0x180031384  lea     rax, [rsp+2A8h+cbData]
0x180031389  mov     [rsp+2A8h+lpcbData], rax; lpcbData
0x18003138e  lea     rax, [rsp+2A8h+Data]
0x180031393  mov     [rsp+2A8h+phkResult], rax; lpData
0x180031398  lea     r9, [rsp+2A8h+Type]; lpType
0x18003139d  xor     r8d, r8d; lpReserved
0x1800313a0  xor     edx, edx; lpValueName
0x1800313a2  mov     rcx, [rsp+2A8h+hKey]; hKey
0x1800313a7  call    cs:__imp_RegQueryValueExW
0x1800313ad  mov     ebx, eax
0x1800313af  mov     rcx, [rsp+2A8h+hKey]; hKey
0x1800313b4  call    cs:__imp_RegCloseKey
0x1800313ba  test    ebx, ebx
0x1800313bc  jnz     loc_18003155F
0x1800313c2  lea     rax, [rsp+2A8h+Data]
0x1800313c7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800313cb  inc     r8
0x1800313ce  cmp     [rax+r8*2], r14w
0x1800313d3  jnz     short loc_1800313CB
0x1800313d5  lea     rdx, [rsp+2A8h+Data]
0x1800313da  mov     rcx, rdi
0x1800313dd  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x1800313e2  mov     edx, 2Eh ; '.'
0x1800313e7  mov     rcx, rdi
0x1800313ea  call    ?ReverseFind@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEBAH_W@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::ReverseFind(wchar_t)
0x1800313ef  test    eax, eax
0x1800313f1  jle     loc_18003155F
0x1800313f7  mov     rcx, [rdi]
0x1800313fa  mov     r8d, [rcx-10h]
0x1800313fe  sub     r8d, eax
0x180031401  dec     r8d
0x180031404  lea     rdx, [rsp+2A8h+var_260]
0x180031409  mov     rcx, rdi
0x18003140c  call    ?Right@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Right(int)
0x180031411  nop
0x180031412  mov     rdx, [rax]
0x180031415  lea     rcx, [rdx-18h]
0x180031419  mov     rsi, [rdi]
0x18003141c  add     rsi, 0FFFFFFFFFFFFFFE8h
0x180031420  cmp     rcx, rsi
0x180031423  jz      short loc_180031459
0x180031425  cmp     [rsi+10h], r14d
0x180031429  jl      short loc_18003144C
0x18003142b  mov     rax, [rsi]
0x18003142e  cmp     [rcx], rax
0x180031431  jnz     short loc_18003144C
0x180031433  call    ?CloneData@?$CSimpleStringT@_W$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,0>::CloneData(ATL::CStringData *)
0x180031438  mov     rbx, rax
0x18003143b  mov     rcx, rsi; this
0x18003143e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031443  lea     rax, [rbx+18h]
0x180031447  mov     [rdi], rax
0x18003144a  jmp     short loc_180031459
0x18003144c  mov     r8d, [rdx-10h]
0x180031450  mov     rcx, rdi
0x180031453  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x180031458  nop
0x180031459  mov     rcx, [rsp+2A8h+var_260]
0x18003145e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180031462  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031467  xor     eax, eax
0x180031469  jmp     loc_180031564
0x18003146e  mov     esi, 2
0x180031473  cmp     eax, esi
0x180031475  jnz     loc_18003155F
0x18003147b  lea     rax, [rsp+2A8h+hKey]
0x180031480  mov     [rsp+2A8h+phkResult], rax; phkResult
0x180031485  mov     r9d, ebx; samDesired
0x180031488  xor     r8d, r8d; ulOptions
0x18003148b  lea     rdx, aOutlookApplica_1; "Outlook.Application.12"
0x180031492  mov     rcx, r15; hKey
0x180031495  call    cs:__imp_RegOpenKeyExW
0x18003149b  test    eax, eax
0x18003149d  jnz     short loc_1800314C3
0x18003149f  mov     ebx, r14d
0x1800314a2  mov     r8d, esi
0x1800314a5  lea     rdx, a12; "12"
0x1800314ac  mov     rcx, rdi
0x1800314af  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x1800314b4  jmp     loc_180031548
0x1800314b9  jmp     loc_18003154C
0x1800314be  jmp     loc_18003154C
0x1800314c3  cmp     eax, esi
0x1800314c5  jnz     loc_18003155F
0x1800314cb  lea     rax, [rsp+2A8h+hKey]
0x1800314d0  mov     [rsp+2A8h+phkResult], rax; phkResult
0x1800314d5  mov     r9d, ebx; samDesired
0x1800314d8  xor     r8d, r8d; ulOptions
0x1800314db  lea     rdx, aOutlookApplica_0; "Outlook.Application.11"
0x1800314e2  mov     rcx, r15; hKey
0x1800314e5  call    cs:__imp_RegOpenKeyExW
0x1800314eb  test    eax, eax
0x1800314ed  jnz     short loc_18003150A
0x1800314ef  mov     ebx, r14d
0x1800314f2  mov     r8d, esi
0x1800314f5  lea     rdx, a11; "11"
0x1800314fc  mov     rcx, rdi
0x1800314ff  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x180031504  jmp     short loc_180031548
0x180031506  jmp     short loc_18003154C
0x180031508  jmp     short loc_18003154C
0x18003150a  cmp     eax, esi
0x18003150c  jnz     short loc_18003155F
0x18003150e  lea     rax, [rsp+2A8h+hKey]
0x180031513  mov     [rsp+2A8h+phkResult], rax; phkResult
0x180031518  mov     r9d, ebx; samDesired
0x18003151b  xor     r8d, r8d; ulOptions
0x18003151e  lea     rdx, aOutlookApplica_2; "Outlook.Application.10"
0x180031525  mov     rcx, r15; hKey
0x180031528  call    cs:__imp_RegOpenKeyExW
0x18003152e  test    eax, eax
0x180031530  jnz     short loc_18003155F
0x180031532  mov     ebx, r14d
0x180031535  mov     r8d, esi
0x180031538  lea     rdx, a10; "10"
0x18003153f  mov     rcx, rdi
0x180031542  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x180031547  nop
0x180031548  jmp     short loc_180031550
0x18003154a  jmp     short $+2
0x18003154c  mov     ebx, [rsp+2A8h+cbData]
0x180031550  mov     rcx, [rsp+2A8h+hKey]; hKey
0x180031555  call    cs:__imp_RegCloseKey
0x18003155b  mov     eax, ebx
0x18003155d  jmp     short loc_180031564
0x18003155f  mov     eax, 1
0x180031564  mov     rcx, [rsp+2A8h+var_28]
0x18003156c  xor     rcx, rsp; StackCookie
0x18003156f  call    __security_check_cookie
0x180031574  lea     r11, [rsp+2A8h+var_18]
0x18003157c  mov     rbx, [r11+28h]
0x180031580  mov     rsi, [r11+30h]
0x180031584  mov     rsp, r11
0x180031587  pop     r15
0x180031589  pop     r14
0x18003158b  pop     rdi
0x18003158c  retn
```
