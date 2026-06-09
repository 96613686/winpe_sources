# StorageWriter::ReadCasMediaType(void)

- ea: `0x180119b44`
- end: `0x180119dbf`
- name: `?ReadCasMediaType@StorageWriter@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `635`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801182a0`

## callees

- `0x180004bd0`
- `0x18003a8d4`
- `0x18003de70`
- `0x1800491e8`
- `0x180119b44`
- `0x18011a0d4`
- `0x18011b8a0`
- `0x18011ba4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180119bef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180119bef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180119c0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180119c0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180119c00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180119cc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180119d4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180119c00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180119cc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180119d4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119cad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119d33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119cad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119d33`

## string_xrefs

- `0x180119d97`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x180119dac`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_OWORD *__fastcall StorageWriter::ReadCasMediaType(__int64 a1)
{
  const unsigned __int16 *v2; // rdx
  const unsigned __int16 *v3; // r8
  __int64 v4; // r8
  int v5; // eax
  const WCHAR *v6; // r8
  int v7; // eax
  _OWORD *result; // rax
  _WORD *v9; // rbx
  __int64 v10; // r8
  _OWORD *v11; // rcx
  HKEY hKey; // [rsp+20h] [rbp-2B8h] BYREF
  _OWORD *v13; // [rsp+28h] [rbp-2B0h]
  LPVOID pv[3]; // [rsp+38h] [rbp-2A0h] BYREF
  __int128 v15; // [rsp+50h] [rbp-288h] BYREF
  __int128 v16; // [rsp+60h] [rbp-278h]
  unsigned __int16 *v17[2]; // [rsp+70h] [rbp-268h] BYREF
  __int128 v18; // [rsp+80h] [rbp-258h]
  _BYTE v19[528]; // [rsp+90h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  v13 = (_OWORD *)a1;
  *(_OWORD *)v17 = 0;
  v18 = 0;
  try
  {
    std::wstring::_Construct<1,unsigned short const *>(
      v17,
      L"SYSTEM\\CurrentControlSet\\Control\\FeatureManagement",
      50);
    v15 = 0;
    v16 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v15, L"CAS_Id", 6);
    hKey = 0;
    v3 = (const unsigned __int16 *)v17;
    if ( *((_QWORD *)&v18 + 1) > 7u )
      v3 = v17[0];
    RegPersistedKey::RegPersistedKey((RegPersistedKey *)v19, v2, v3);
    hKey = 0;
    v5 = RegPersistedKey::RegOpenKeyW((RegPersistedKey *)v19, 0, v4, &hKey);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x54E,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
        (const char *)(unsigned int)v5,
        (int)hKey);
    memset(pv, 0, sizeof(pv));
    v6 = (const WCHAR *)&v15;
    if ( *((_QWORD *)&v16 + 1) > 7u )
      v6 = (const WCHAR *)v15;
    v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeFromRegistry(
           (__int64)pv,
           hKey,
           v6);
    if ( v7 < 0 )
    {
      if ( v7 == -2147024894 )
      {
        *(_OWORD *)a1 = 0;
        *(_QWORD *)(a1 + 16) = 0;
        *(_QWORD *)(a1 + 24) = 0;
        std::wstring::_Construct<1,unsigned short const *>(a1, &dword_1801D0670, 0);
        if ( pv[0] )
          CoTaskMemFree(pv[0]);
        if ( !hKey )
          goto LABEL_14;
LABEL_13:
        RegCloseKey(hKey);
LABEL_14:
        std::wstring::~wstring(&v15);
        std::wstring::~wstring(v17);
        return (_OWORD *)a1;
      }
    }
    else
    {
      v7 = 0;
    }
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x556,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
        (const char *)(unsigned int)v7,
        (int)hKey);
    v9 = pv[0];
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    v10 = -1;
    do
      ++v10;
    while ( v9[v10] );
    std::wstring::_Construct<1,unsigned short const *>(a1, v9, v10);
    if ( v9 )
      CoTaskMemFree(v9);
    if ( !hKey )
      goto LABEL_14;
    goto LABEL_13;
  }
  catch ( ... )
  {
    v11 = v13;
    *v13 = 0;
    *((_QWORD *)v11 + 2) = 0;
    *((_QWORD *)v11 + 3) = 0;
    std::wstring::_Construct<1,unsigned short const *>(v11, &dword_1801D0670, 0);
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x180119b44  push    rbx
0x180119b46  push    rsi
0x180119b47  push    rdi
0x180119b48  push    r14
0x180119b4a  sub     rsp, 2B8h
0x180119b51  mov     rax, cs:__security_cookie
0x180119b58  xor     rax, rsp
0x180119b5b  mov     [rsp+2D8h+var_38], rax
0x180119b63  mov     rdi, rcx
0x180119b66  mov     [rsp+2D8h+var_2B0], rcx
0x180119b6b  xor     r14d, r14d
0x180119b6e  xorps   xmm0, xmm0
0x180119b71  movups  xmmword ptr [rsp+2D8h+var_268], xmm0
0x180119b76  xorps   xmm1, xmm1
0x180119b79  movdqu  [rsp+2D8h+var_258], xmm1
0x180119b82  lea     r8d, [r14+32h]
0x180119b86  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Fea"...
0x180119b8d  lea     rcx, [rsp+2D8h+var_268]
0x180119b92  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180119b97  nop
0x180119b98  xorps   xmm0, xmm0
0x180119b9b  movups  [rsp+2D8h+var_288], xmm0
0x180119ba0  xorps   xmm1, xmm1
0x180119ba3  movdqu  [rsp+2D8h+var_278], xmm1
0x180119ba9  lea     r8d, [r14+6]
0x180119bad  lea     rdx, aCasId; "CAS_Id"
0x180119bb4  lea     rcx, [rsp+2D8h+var_288]
0x180119bb9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180119bbe  nop
0x180119bbf  mov     [rsp+2D8h+hKey], r14
0x180119bc4  lea     r8, [rsp+2D8h+var_268]
0x180119bc9  cmp     qword ptr [rsp+2D8h+var_258+8], 7
0x180119bd2  cmova   r8, [rsp+2D8h+var_268]; unsigned __int16 *
0x180119bd8  lea     rcx, [rsp+2D8h+var_248]; this
0x180119be0  call    ??0RegPersistedKey@@QEAA@PEBG0@Z; RegPersistedKey::RegPersistedKey(ushort const *,ushort const *)
0x180119be5  mov     rsi, [rsp+2D8h+hKey]
0x180119bea  test    rsi, rsi
0x180119bed  jz      short loc_180119C1A
0x180119bef  call    cs:__imp_GetLastError
0x180119bf6  nop     dword ptr [rax+rax+00h]
0x180119bfb  mov     ebx, eax
0x180119bfd  mov     rcx, rsi; hKey
0x180119c00  call    cs:__imp_RegCloseKey
0x180119c07  nop     dword ptr [rax+rax+00h]
0x180119c0c  mov     ecx, ebx; dwErrCode
0x180119c0e  call    cs:__imp_SetLastError
0x180119c15  nop     dword ptr [rax+rax+00h]
0x180119c1a  mov     [rsp+2D8h+hKey], r14; int
0x180119c1f  lea     r9, [rsp+2D8h+hKey]; HKEY *
0x180119c24  xor     edx, edx; unsigned __int16 *
0x180119c26  lea     rcx, [rsp+2D8h+var_248]; this
0x180119c2e  call    ?RegOpenKeyW@RegPersistedKey@@QEAAJPEBGKPEAPEAUHKEY__@@@Z; RegPersistedKey::RegOpenKeyW(ushort const *,ulong,HKEY__ * *)
0x180119c33  mov     rcx, [rsp+2D8h]; this
0x180119c3b  test    eax, eax
0x180119c3d  js      loc_180119D94
0x180119c43  mov     [rsp+2D8h+pv], r14
0x180119c48  mov     [rsp+2D8h+var_298], r14
0x180119c4d  mov     [rsp+2D8h+var_290], r14
0x180119c52  lea     r8, [rsp+2D8h+var_288]
0x180119c57  cmp     qword ptr [rsp+2D8h+var_278+8], 7
0x180119c5d  cmova   r8, qword ptr [rsp+2D8h+var_288]
0x180119c63  mov     rdx, [rsp+2D8h+hKey]
0x180119c68  lea     rcx, [rsp+2D8h+pv]
0x180119c6d  call    ?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x180119c72  test    eax, eax
0x180119c74  js      short loc_180119C7B
0x180119c76  mov     eax, r14d
0x180119c79  jmp     short loc_180119CEE
0x180119c7b  cmp     eax, 80070002h
0x180119c80  jnz     short loc_180119CEE
0x180119c82  xorps   xmm0, xmm0
0x180119c85  movups  xmmword ptr [rdi], xmm0
0x180119c88  mov     [rdi+10h], r14
0x180119c8c  mov     [rdi+18h], r14
0x180119c90  xor     r8d, r8d
0x180119c93  lea     rdx, dword_1801D0670
0x180119c9a  mov     rcx, rdi
0x180119c9d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180119ca2  nop
0x180119ca3  mov     rcx, [rsp+2D8h+pv]; pv
0x180119ca8  test    rcx, rcx
0x180119cab  jz      short loc_180119CBA
0x180119cad  call    cs:__imp_CoTaskMemFree
0x180119cb4  nop     dword ptr [rax+rax+00h]
0x180119cb9  nop
0x180119cba  mov     rcx, [rsp+2D8h+hKey]; hKey
0x180119cbf  test    rcx, rcx
0x180119cc2  jz      short loc_180119CD1
0x180119cc4  call    cs:__imp_RegCloseKey
0x180119ccb  nop     dword ptr [rax+rax+00h]
0x180119cd0  nop
0x180119cd1  lea     rcx, [rsp+2D8h+var_288]; void *
0x180119cd6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180119cdb  nop
0x180119cdc  lea     rcx, [rsp+2D8h+var_268]; void *
0x180119ce1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180119ce6  mov     rax, rdi
0x180119ce9  jmp     loc_180119D76
0x180119cee  mov     rcx, [rsp+2D8h]; this
0x180119cf6  test    eax, eax
0x180119cf8  js      loc_180119DA9
0x180119cfe  mov     rbx, [rsp+2D8h+pv]
0x180119d03  xorps   xmm0, xmm0
0x180119d06  movups  xmmword ptr [rdi], xmm0
0x180119d09  mov     [rdi+10h], r14
0x180119d0d  mov     [rdi+18h], r14
0x180119d11  or      r8, 0FFFFFFFFFFFFFFFFh
0x180119d15  inc     r8
0x180119d18  cmp     [rbx+r8*2], r14w
0x180119d1d  jnz     short loc_180119D15
0x180119d1f  mov     rdx, rbx
0x180119d22  mov     rcx, rdi
0x180119d25  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180119d2a  nop
0x180119d2b  test    rbx, rbx
0x180119d2e  jz      short loc_180119D40
0x180119d30  mov     rcx, rbx; pv
0x180119d33  call    cs:__imp_CoTaskMemFree
0x180119d3a  nop     dword ptr [rax+rax+00h]
0x180119d3f  nop
0x180119d40  mov     rcx, [rsp+2D8h+hKey]; hKey
0x180119d45  test    rcx, rcx
0x180119d48  jz      short loc_180119D57
0x180119d4a  call    cs:__imp_RegCloseKey
0x180119d51  nop     dword ptr [rax+rax+00h]
0x180119d56  nop
0x180119d57  lea     rcx, [rsp+2D8h+var_288]; void *
0x180119d5c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180119d61  nop
0x180119d62  lea     rcx, [rsp+2D8h+var_268]; void *
0x180119d67  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180119d6c  mov     rax, rdi
0x180119d6f  jmp     short loc_180119D76
0x180119d71  mov     rax, [rsp+2D8h+var_2B0]
0x180119d76  mov     rcx, [rsp+2D8h+var_38]
0x180119d7e  xor     rcx, rsp; StackCookie
0x180119d81  call    __security_check_cookie
0x180119d86  add     rsp, 2B8h
0x180119d8d  pop     r14
0x180119d8f  pop     rdi
0x180119d90  pop     rsi
0x180119d91  pop     rbx
0x180119d92  retn
0x180119d94  mov     r9d, eax; char *
0x180119d97  lea     r8, aOnecoreBaseFli_2; "onecore\\base\\flighting\\featuremanage"...
0x180119d9e  mov     edx, 54Eh; void *
0x180119da3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180119da9  mov     r9d, eax; char *
0x180119dac  lea     r8, aOnecoreBaseFli_2; "onecore\\base\\flighting\\featuremanage"...
0x180119db3  mov     edx, 556h; void *
0x180119db8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
