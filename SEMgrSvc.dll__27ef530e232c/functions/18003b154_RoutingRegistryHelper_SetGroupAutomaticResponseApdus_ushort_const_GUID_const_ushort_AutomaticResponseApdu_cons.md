# RoutingRegistryHelper::SetGroupAutomaticResponseApdus(ushort const *,_GUID const &,ushort,_AutomaticResponseApdu const *)

- ea: `0x18003b154`
- end: `0x18003b698`
- name: `?SetGroupAutomaticResponseApdus@RoutingRegistryHelper@@SAJPEBGAEBU_GUID@@GPEBU_AutomaticResponseApdu@@@Z`
- size: `1348`
- prototype: `static int(const unsigned __int16 *, const struct _GUID *, unsigned __int16, const struct _AutomaticResponseApdu *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180033d54`

## callees

- `0x1800049a0`
- `0x180005858`
- `0x18000d4ec`
- `0x180013274`
- `0x18003b154`
- `0x18007d3a0`
- `0x18007d434`
- `0x18007d504`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003b1cb`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003b1cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b21d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b2eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b5f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b21d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b2eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b5f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b230`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b2fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b230`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b2fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b228`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b2f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b5e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b612`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b62a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b669`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b228`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b2f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b5e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b612`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b62a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b669`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003b339`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003b339`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003b286`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003b63c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003b286`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003b63c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b385`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b3c4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b40f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b450`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b4d0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b52a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b576`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b5c2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b385`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b3c4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b40f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b450`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b4d0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b52a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b576`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b5c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b4ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b64b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b4ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b64b`
- `CRYPT32!CryptProtectData` at `0x18003b49c`
- `CRYPT32!CryptProtectData` at `0x18003b49c`

## string_xrefs

- `0x18003b3bd`: `CommandApduBitMask`
- `0x18003b37e`: `CommandApdu`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RoutingRegistryHelper::SetGroupAutomaticResponseApdus(
        const unsigned __int16 *a1,
        const struct _GUID *a2,
        unsigned __int16 a3,
        const struct _AutomaticResponseApdu *a4)
{
  signed int v8; // edi
  unsigned int v9; // edx
  struct _SECURITY_ATTRIBUTES *v10; // r9
  int v11; // eax
  LSTATUS v12; // eax
  unsigned __int16 v13; // r15
  int v14; // eax
  HKEY v15; // r14
  DWORD LastError; // ebx
  bool v17; // sf
  HKEY v18; // rcx
  __int64 v19; // rbx
  bool v20; // sf
  bool v21; // sf
  bool v22; // sf
  bool v23; // sf
  bool v24; // sf
  bool v25; // sf
  bool v26; // sf
  bool v27; // sf
  signed int v28; // eax
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  BYTE v31[8]; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v33; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[4]; // [rsp+6Ch] [rbp-94h] BYREF
  BYTE v35[8]; // [rsp+70h] [rbp-90h] BYREF
  DATA_BLOB pDataOut; // [rsp+78h] [rbp-88h] BYREF
  DATA_BLOB pDataIn; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v38[16]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v39[32]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR SubKey[8]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v41; // [rsp+E0h] [rbp-20h] BYREF
  OLECHAR sz[40]; // [rsp+F0h] [rbp-10h] BYREF

  hKey = 0;
  memset_0(sz, 0, 0x4Eu);
  NfcRegPath::NfcRegPath((NfcRegPath *)v38, (const struct NfcRegistryLocation *)&qword_1800A1C18);
  v33 = 0;
  pDataOut = 0;
  if ( !StringFromGUID2(a2, sz, 39) )
  {
    v8 = -2147467259;
LABEL_57:
    if ( hKey )
      RegDeleteTreeW(hKey, 0);
    goto LABEL_59;
  }
  *(_QWORD *)SubKey = a1;
  *(_QWORD *)&SubKey[4] = sz;
  *(_QWORD *)&v41 = L"AutoResponder";
  *(_QWORD *)&pDataIn.cbData = SubKey;
  pDataIn.pbData = (BYTE *)&v41 + 8;
  NfcRegPath::AppendSubKeys(v38, &pDataIn);
  hKey = 0;
  v11 = NfcRegCreateKeyEx((const struct NfcRegistryLocation *)v38, v9, 0x2001Fu, v10, &hKey, &v33);
  v8 = v11;
  if ( v11 > 0 )
    v8 = (unsigned __int16)v11 | 0x80070000;
  if ( v8 < 0 )
    goto LABEL_57;
  if ( v33 == 2 )
  {
    v12 = RegDeleteTreeW(hKey, 0);
    v8 = v12;
    if ( v12 > 0 )
      v8 = (unsigned __int16)v12 | 0x80070000;
    if ( v8 < 0 )
      goto LABEL_57;
  }
  v8 = 0;
  v13 = 0;
  if ( a3 )
  {
    while ( 1 )
    {
      phkResult = 0;
      *(_OWORD *)SubKey = 0;
      v41 = 0;
      v14 = StringCchPrintfW(SubKey, 0x10u, L"%d", v13);
      if ( v14 < 0 )
      {
LABEL_54:
        v18 = phkResult;
LABEL_55:
        v8 = v14;
        if ( v18 )
          RegCloseKey(v18);
        goto LABEL_57;
      }
      v15 = phkResult;
      if ( phkResult )
      {
        LastError = GetLastError();
        RegCloseKey(v15);
        SetLastError(LastError);
      }
      phkResult = 0;
      v14 = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
      v17 = v14 < 0;
      if ( v14 > 0 )
      {
        v14 = (unsigned __int16)v14 | 0x80070000;
        v17 = v14 < 0;
      }
      v18 = phkResult;
      if ( v17 )
        goto LABEL_55;
      v19 = 88LL * v13;
      v14 = RegSetValueExW(
              phkResult,
              L"CommandApdu",
              0,
              3u,
              *(const BYTE **)((char *)a4 + v19 + 8),
              *(_DWORD *)((char *)a4 + v19));
      v20 = v14 < 0;
      if ( v14 > 0 )
      {
        v14 = (unsigned __int16)v14 | 0x80070000;
        v20 = v14 < 0;
      }
      v18 = phkResult;
      if ( v20 )
        goto LABEL_55;
      v14 = RegSetValueExW(
              phkResult,
              L"CommandApduBitMask",
              0,
              3u,
              *(const BYTE **)((char *)a4 + v19 + 24),
              *(_DWORD *)((char *)a4 + v19 + 16));
      v21 = v14 < 0;
      if ( v14 > 0 )
      {
        v14 = (unsigned __int16)v14 | 0x80070000;
        v21 = v14 < 0;
      }
      v18 = phkResult;
      if ( v21 )
        goto LABEL_55;
      *(_DWORD *)Data = *((_BYTE *)a4 + 88 * v13 + 32) != 0;
      v14 = RegSetValueExW(phkResult, L"ShouldMatchLength", 0, 4u, Data, 4u);
      v22 = v14 < 0;
      if ( v14 > 0 )
      {
        v14 = (unsigned __int16)v14 | 0x80070000;
        v22 = v14 < 0;
      }
      v18 = phkResult;
      if ( v22 )
        goto LABEL_55;
      v14 = RegSetValueExW(
              phkResult,
              L"AppletId",
              0,
              3u,
              (const BYTE *)a4 + v19 + 40,
              *(_DWORD *)((char *)a4 + v19 + 36));
      v23 = v14 < 0;
      if ( v14 > 0 )
      {
        v14 = (unsigned __int16)v14 | 0x80070000;
        v23 = v14 < 0;
      }
      if ( v23 )
        goto LABEL_54;
      *(&pDataIn.cbData + 1) = 0;
      pDataIn.pbData = *(BYTE **)((char *)a4 + v19 + 64);
      pDataIn.cbData = *(_DWORD *)((char *)a4 + v19 + 56);
      if ( !CryptProtectData(&pDataIn, 0, 0, 0, 0, 0, &pDataOut) )
        break;
      v14 = RegSetValueExW(phkResult, L"ResponseApdu", 0, 3u, pDataOut.pbData, pDataOut.cbData);
      v24 = v14 < 0;
      if ( v14 > 0 )
      {
        v14 = (unsigned __int16)v14 | 0x80070000;
        v24 = v14 < 0;
      }
      if ( v24 )
        goto LABEL_54;
      LocalFree(pDataOut.pbData);
      pDataOut.pbData = 0;
      if ( !*((_BYTE *)a4 + v19 + 76) )
      {
        *(_DWORD *)v31 = *(_DWORD *)((char *)a4 + v19 + 72);
        v14 = RegSetValueExW(phkResult, L"InputState", 0, 4u, v31, 4u);
        v25 = v14 < 0;
        if ( v14 > 0 )
        {
          v14 = (unsigned __int16)v14 | 0x80070000;
          v25 = v14 < 0;
        }
        if ( v25 )
          goto LABEL_54;
      }
      if ( !*((_BYTE *)a4 + v19 + 84) )
      {
        *(_DWORD *)v31 = *(_DWORD *)((char *)a4 + v19 + 80);
        v14 = RegSetValueExW(phkResult, L"OutputState", 0, 4u, v31, 4u);
        v26 = v14 < 0;
        if ( v14 > 0 )
        {
          v14 = (unsigned __int16)v14 | 0x80070000;
          v26 = v14 < 0;
        }
        if ( v26 )
          goto LABEL_54;
      }
      *(_DWORD *)v35 = *((_BYTE *)a4 + 88 * v13 + 85) != 0;
      v14 = RegSetValueExW(phkResult, L"AllowWhenDeviceCastleNotPrepared", 0, 4u, v35, 4u);
      v27 = v14 < 0;
      if ( v14 > 0 )
      {
        v14 = (unsigned __int16)v14 | 0x80070000;
        v27 = v14 < 0;
      }
      v18 = phkResult;
      if ( v27 )
        goto LABEL_55;
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( ++v13 >= a3 )
        goto LABEL_59;
    }
    v28 = GetLastError();
    v8 = v28;
    if ( v28 > 0 )
      v8 = (unsigned __int16)v28 | 0x80070000;
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( v8 < 0 )
      goto LABEL_57;
  }
LABEL_59:
  if ( pDataOut.pbData )
  {
    LocalFree(pDataOut.pbData);
    pDataOut.pbData = 0;
  }
  std::wstring::~wstring(v39);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003b154  mov     [rsp-8+arg_0], rbx
0x18003b159  push    rbp
0x18003b15a  push    rsi
0x18003b15b  push    rdi
0x18003b15c  push    r12
0x18003b15e  push    r13
0x18003b160  push    r14
0x18003b162  push    r15
0x18003b164  lea     rbp, [rsp-50h]
0x18003b169  sub     rsp, 150h
0x18003b170  mov     rax, cs:__security_cookie
0x18003b177  xor     rax, rsp
0x18003b17a  mov     [rbp+80h+var_40], rax
0x18003b17e  mov     rsi, r9
0x18003b181  movzx   r12d, r8w
0x18003b185  mov     rbx, rdx
0x18003b188  mov     rdi, rcx
0x18003b18b  xor     r13d, r13d
0x18003b18e  mov     [rsp+180h+hKey], r13
0x18003b193  xor     edx, edx; Val
0x18003b195  lea     r8d, [r13+4Eh]; Size
0x18003b199  lea     rcx, [rbp+80h+sz]; void *
0x18003b19d  call    memset_0
0x18003b1a2  lea     rdx, qword_1800A1C18; struct NfcRegistryLocation *
0x18003b1a9  lea     rcx, [rbp+80h+var_E0]; this
0x18003b1ad  call    ??0NfcRegPath@@QEAA@AEBUNfcRegistryLocation@@@Z; NfcRegPath::NfcRegPath(NfcRegistryLocation const &)
0x18003b1b2  nop
0x18003b1b3  mov     [rsp+180h+var_118], r13d
0x18003b1b8  xorps   xmm0, xmm0
0x18003b1bb  movups  xmmword ptr [rsp+180h+pDataOut.cbData], xmm0
0x18003b1c0  lea     r8d, [r13+27h]; cchMax
0x18003b1c4  lea     rdx, [rbp+80h+sz]; lpsz
0x18003b1c8  mov     rcx, rbx; rguid
0x18003b1cb  call    cs:__imp_StringFromGUID2
0x18003b1d1  test    eax, eax
0x18003b1d3  jnz     short loc_18003B1DF
0x18003b1d5  mov     edi, 80004005h
0x18003b1da  jmp     loc_18003B630
0x18003b1df  mov     qword ptr [rbp+80h+SubKey], rdi
0x18003b1e3  lea     rax, [rbp+80h+sz]
0x18003b1e7  mov     qword ptr [rbp+80h+SubKey+8], rax
0x18003b1eb  lea     rax, aAutoresponder; "AutoResponder"
0x18003b1f2  mov     qword ptr [rbp+80h+var_A0], rax
0x18003b1f6  lea     rax, [rbp+80h+SubKey]
0x18003b1fa  mov     qword ptr [rbp+80h+pDataIn.cbData], rax
0x18003b1fe  lea     rax, [rbp+80h+var_A0+8]
0x18003b202  mov     [rbp+80h+pDataIn.pbData], rax
0x18003b206  lea     rdx, [rbp+80h+pDataIn]
0x18003b20a  lea     rcx, [rbp+80h+var_E0]
0x18003b20e  call    ?AppendSubKeys@NfcRegPath@@QEAAXV?$initializer_list@PEBG@std@@@Z; NfcRegPath::AppendSubKeys(std::initializer_list<ushort const *>)
0x18003b213  mov     rdi, [rsp+180h+hKey]
0x18003b218  test    rdi, rdi
0x18003b21b  jz      short loc_18003B236
0x18003b21d  call    cs:__imp_GetLastError
0x18003b223  mov     ebx, eax
0x18003b225  mov     rcx, rdi; hKey
0x18003b228  call    cs:__imp_RegCloseKey
0x18003b22e  mov     ecx, ebx; dwErrCode
0x18003b230  call    cs:__imp_SetLastError
0x18003b236  mov     [rsp+180h+hKey], r13
0x18003b23b  lea     rax, [rsp+180h+var_118]
0x18003b240  mov     qword ptr [rsp+180h+samDesired], rax; unsigned int *
0x18003b245  lea     rax, [rsp+180h+hKey]
0x18003b24a  mov     qword ptr [rsp+180h+dwOptions], rax; HKEY *
0x18003b24f  mov     r8d, 2001Fh; unsigned int
0x18003b255  lea     rcx, [rbp+80h+var_E0]; struct NfcRegistryLocation *
0x18003b259  call    ?NfcRegCreateKeyEx@@YAJAEBUNfcRegistryLocation@@KKPEAU_SECURITY_ATTRIBUTES@@PEAPEAUHKEY__@@PEAK@Z; NfcRegCreateKeyEx(NfcRegistryLocation const &,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x18003b25e  mov     edi, eax
0x18003b260  mov     r14d, 80070000h
0x18003b266  test    eax, eax
0x18003b268  jle     short loc_18003B270
0x18003b26a  movzx   edi, ax
0x18003b26d  or      edi, r14d
0x18003b270  test    edi, edi
0x18003b272  js      loc_18003B630
0x18003b278  cmp     [rsp+180h+var_118], 2
0x18003b27d  jnz     short loc_18003B2A0
0x18003b27f  xor     edx, edx; lpSubKey
0x18003b281  mov     rcx, [rsp+180h+hKey]; hKey
0x18003b286  call    cs:__imp_RegDeleteTreeW
0x18003b28c  mov     edi, eax
0x18003b28e  test    eax, eax
0x18003b290  jle     short loc_18003B298
0x18003b292  movzx   edi, ax
0x18003b295  or      edi, r14d
0x18003b298  test    edi, edi
0x18003b29a  js      loc_18003B630
0x18003b2a0  mov     edi, r13d
0x18003b2a3  mov     r15d, r13d
0x18003b2a6  cmp     r13w, r12w
0x18003b2aa  jnb     loc_18003B642
0x18003b2b0  mov     [rsp+180h+var_130], r13
0x18003b2b5  xorps   xmm0, xmm0
0x18003b2b8  movups  xmmword ptr [rbp+80h+SubKey], xmm0
0x18003b2bc  movups  [rbp+80h+var_A0], xmm0
0x18003b2c0  movzx   r9d, r15w
0x18003b2c4  lea     r8, aD; "%d"
0x18003b2cb  mov     edx, 10h; unsigned __int64
0x18003b2d0  lea     rcx, [rbp+80h+SubKey]; unsigned __int16 *
0x18003b2d4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b2d9  test    eax, eax
0x18003b2db  js      loc_18003B61E
0x18003b2e1  mov     r14, [rsp+180h+var_130]
0x18003b2e6  test    r14, r14
0x18003b2e9  jz      short loc_18003B304
0x18003b2eb  call    cs:__imp_GetLastError
0x18003b2f1  mov     ebx, eax
0x18003b2f3  mov     rcx, r14; hKey
0x18003b2f6  call    cs:__imp_RegCloseKey
0x18003b2fc  mov     ecx, ebx; dwErrCode
0x18003b2fe  call    cs:__imp_SetLastError
0x18003b304  mov     [rsp+180h+var_130], r13
0x18003b309  mov     [rsp+180h+lpdwDisposition], r13; lpdwDisposition
0x18003b30e  lea     rax, [rsp+180h+var_130]
0x18003b313  mov     [rsp+180h+phkResult], rax; phkResult
0x18003b318  mov     [rsp+180h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18003b31d  mov     [rsp+180h+samDesired], 2001Fh; samDesired
0x18003b325  mov     [rsp+180h+dwOptions], r13d; dwOptions
0x18003b32a  xor     r9d, r9d; lpClass
0x18003b32d  xor     r8d, r8d; Reserved
0x18003b330  lea     rdx, [rbp+80h+SubKey]; lpSubKey
0x18003b334  mov     rcx, [rsp+180h+hKey]; hKey
0x18003b339  call    cs:__imp_RegCreateKeyExW
0x18003b33f  mov     r14d, 80070000h
0x18003b345  test    eax, eax
0x18003b347  jle     short loc_18003B351
0x18003b349  movzx   eax, ax
0x18003b34c  or      eax, r14d
0x18003b34f  test    eax, eax
0x18003b351  mov     rcx, [rsp+180h+var_130]; hKey
0x18003b356  js      loc_18003B623
0x18003b35c  movzx   eax, r15w
0x18003b360  imul    rbx, rax, 58h ; 'X'
0x18003b364  mov     eax, [rbx+rsi]
0x18003b367  mov     [rsp+180h+samDesired], eax; cbData
0x18003b36b  mov     rax, [rbx+rsi+8]
0x18003b370  mov     qword ptr [rsp+180h+dwOptions], rax; lpData
0x18003b375  mov     r9d, 3; dwType
0x18003b37b  xor     r8d, r8d; Reserved
0x18003b37e  lea     rdx, aCommandapdu; "CommandApdu"
0x18003b385  call    cs:__imp_RegSetValueExW
0x18003b38b  test    eax, eax
0x18003b38d  jle     short loc_18003B397
0x18003b38f  movzx   eax, ax
0x18003b392  or      eax, r14d
0x18003b395  test    eax, eax
0x18003b397  mov     rcx, [rsp+180h+var_130]; hKey
0x18003b39c  js      loc_18003B623
0x18003b3a2  mov     eax, [rbx+rsi+10h]
0x18003b3a6  mov     [rsp+180h+samDesired], eax; cbData
0x18003b3aa  mov     rax, [rbx+rsi+18h]
0x18003b3af  mov     qword ptr [rsp+180h+dwOptions], rax; lpData
0x18003b3b4  mov     r9d, 3; dwType
0x18003b3ba  xor     r8d, r8d; Reserved
0x18003b3bd  lea     rdx, aCommandapdubit; "CommandApduBitMask"
0x18003b3c4  call    cs:__imp_RegSetValueExW
0x18003b3ca  test    eax, eax
0x18003b3cc  jle     short loc_18003B3D6
0x18003b3ce  movzx   eax, ax
0x18003b3d1  or      eax, r14d
0x18003b3d4  test    eax, eax
0x18003b3d6  mov     rcx, [rsp+180h+var_130]; hKey
0x18003b3db  js      loc_18003B623
0x18003b3e1  mov     eax, r13d
0x18003b3e4  cmp     [rbx+rsi+20h], r13b
0x18003b3e9  setnz   al
0x18003b3ec  mov     dword ptr [rsp+180h+Data], eax
0x18003b3f0  mov     r9d, 4; dwType
0x18003b3f6  mov     [rsp+180h+samDesired], r9d; cbData
0x18003b3fb  lea     rax, [rsp+180h+Data]
0x18003b400  mov     qword ptr [rsp+180h+dwOptions], rax; lpData
0x18003b405  xor     r8d, r8d; Reserved
0x18003b408  lea     rdx, aShouldmatchlen; "ShouldMatchLength"
0x18003b40f  call    cs:__imp_RegSetValueExW
0x18003b415  test    eax, eax
0x18003b417  jle     short loc_18003B421
0x18003b419  movzx   eax, ax
0x18003b41c  or      eax, r14d
0x18003b41f  test    eax, eax
0x18003b421  mov     rcx, [rsp+180h+var_130]; hKey
0x18003b426  js      loc_18003B623
0x18003b42c  lea     rdx, [rsi+28h]
0x18003b430  add     rdx, rbx
0x18003b433  mov     eax, [rbx+rsi+24h]
0x18003b437  mov     [rsp+180h+samDesired], eax; cbData
0x18003b43b  mov     qword ptr [rsp+180h+dwOptions], rdx; lpData
0x18003b440  mov     r9d, 3; dwType
0x18003b446  xor     r8d, r8d; Reserved
0x18003b449  lea     rdx, aAppletid; "AppletId"
0x18003b450  call    cs:__imp_RegSetValueExW
0x18003b456  test    eax, eax
0x18003b458  jle     short loc_18003B462
0x18003b45a  movzx   eax, ax
0x18003b45d  or      eax, r14d
0x18003b460  test    eax, eax
0x18003b462  js      loc_18003B61E
0x18003b468  mov     dword ptr [rbp+80h+pDataIn+4], r13d
0x18003b46c  mov     rax, [rbx+rsi+40h]
0x18003b471  mov     [rbp+80h+pDataIn.pbData], rax
0x18003b475  mov     eax, [rbx+rsi+38h]
0x18003b479  mov     [rbp+80h+pDataIn.cbData], eax
0x18003b47c  lea     rax, [rsp+180h+pDataOut]
0x18003b481  mov     [rsp+180h+lpSecurityAttributes], rax; pDataOut
0x18003b486  mov     [rsp+180h+samDesired], r13d; dwFlags
0x18003b48b  mov     qword ptr [rsp+180h+dwOptions], r13; pPromptStruct
0x18003b490  xor     r9d, r9d; pvReserved
0x18003b493  xor     r8d, r8d; pOptionalEntropy
0x18003b496  xor     edx, edx; szDataDescr
0x18003b498  lea     rcx, [rbp+80h+pDataIn]; pDataIn
0x18003b49c  call    cs:__imp_CryptProtectData
0x18003b4a2  test    eax, eax
0x18003b4a4  jz      loc_18003B5F6
0x18003b4aa  mov     eax, [rsp+180h+pDataOut.cbData]
0x18003b4ae  mov     [rsp+180h+samDesired], eax; cbData
0x18003b4b2  mov     rax, [rbp+80h+pDataOut.pbData]
0x18003b4b6  mov     qword ptr [rsp+180h+dwOptions], rax; lpData
0x18003b4bb  mov     r9d, 3; dwType
0x18003b4c1  xor     r8d, r8d; Reserved
0x18003b4c4  lea     rdx, aResponseapdu; "ResponseApdu"
0x18003b4cb  mov     rcx, [rsp+180h+var_130]; hKey
0x18003b4d0  call    cs:__imp_RegSetValueExW
0x18003b4d6  test    eax, eax
0x18003b4d8  jle     short loc_18003B4E2
0x18003b4da  movzx   eax, ax
0x18003b4dd  or      eax, r14d
0x18003b4e0  test    eax, eax
0x18003b4e2  js      loc_18003B61E
0x18003b4e8  mov     rcx, [rbp+80h+pDataOut.pbData]; hMem
0x18003b4ec  call    cs:__imp_LocalFree
0x18003b4f2  mov     [rbp+80h+pDataOut.pbData], r13
0x18003b4f6  cmp     [rbx+rsi+4Ch], r13b
0x18003b4fb  jnz     short loc_18003B542
0x18003b4fd  mov     eax, [rbx+rsi+48h]
0x18003b501  mov     dword ptr [rsp+180h+var_128], eax
0x18003b505  mov     ecx, 4
0x18003b50a  mov     [rsp+180h+samDesired], ecx; cbData
0x18003b50e  lea     rax, [rsp+180h+var_128]
0x18003b513  mov     qword ptr [rsp+180h+dwOptions], rax; lpData
0x18003b518  mov     r9d, ecx; dwType
0x18003b51b  xor     r8d, r8d; Reserved
0x18003b51e  lea     rdx, aInputstate; "InputState"
0x18003b525  mov     rcx, [rsp+180h+var_130]; hKey
0x18003b52a  call    cs:__imp_RegSetValueExW
0x18003b530  test    eax, eax
0x18003b532  jle     short loc_18003B53C
0x18003b534  movzx   eax, ax
0x18003b537  or      eax, r14d
0x18003b53a  test    eax, eax
0x18003b53c  js      loc_18003B61E
0x18003b542  cmp     [rbx+rsi+54h], r13b
0x18003b547  jnz     short loc_18003B58E
0x18003b549  mov     eax, [rbx+rsi+50h]
0x18003b54d  mov     dword ptr [rsp+180h+var_128], eax
0x18003b551  mov     ecx, 4
0x18003b556  mov     [rsp+180h+samDesired], ecx; cbData
0x18003b55a  lea     rax, [rsp+180h+var_128]
0x18003b55f  mov     qword ptr [rsp+180h+dwOptions], rax; lpData
0x18003b564  mov     r9d, ecx; dwType
0x18003b567  xor     r8d, r8d; Reserved
0x18003b56a  lea     rdx, aOutputstate; "OutputState"
0x18003b571  mov     rcx, [rsp+180h+var_130]; hKey
0x18003b576  call    cs:__imp_RegSetValueExW
0x18003b57c  test    eax, eax
0x18003b57e  jle     short loc_18003B588
0x18003b580  movzx   eax, ax
0x18003b583  or      eax, r14d
0x18003b586  test    eax, eax
0x18003b588  js      loc_18003B61E
0x18003b58e  mov     eax, r13d
0x18003b591  cmp     [rbx+rsi+55h], r13b
0x18003b596  setnz   al
0x18003b599  mov     dword ptr [rsp+180h+var_110], eax
0x18003b59d  mov     ebx, 4
0x18003b5a2  mov     [rsp+180h+samDesired], ebx; cbData
0x18003b5a6  lea     rax, [rsp+180h+var_110]
0x18003b5ab  mov     qword ptr [rsp+180h+dwOptions], rax; lpData
0x18003b5b0  mov     r9d, ebx; dwType
0x18003b5b3  xor     r8d, r8d; Reserved
0x18003b5b6  lea     rdx, aAllowwhendevic; "AllowWhenDeviceCastleNotPrepared"
0x18003b5bd  mov     rcx, [rsp+180h+var_130]; hKey
0x18003b5c2  call    cs:__imp_RegSetValueExW
0x18003b5c8  test    eax, eax
0x18003b5ca  jle     short loc_18003B5D4
0x18003b5cc  movzx   eax, ax
0x18003b5cf  or      eax, r14d
0x18003b5d2  test    eax, eax
0x18003b5d4  mov     rcx, [rsp+180h+var_130]; hKey
0x18003b5d9  js      short loc_18003B623
0x18003b5db  test    rcx, rcx
0x18003b5de  jz      short loc_18003B5E6
0x18003b5e0  call    cs:__imp_RegCloseKey
0x18003b5e6  inc     r15w
0x18003b5ea  cmp     r15w, r12w
0x18003b5ee  jb      loc_18003B2B0
0x18003b5f4  jmp     short loc_18003B642
0x18003b5f6  call    cs:__imp_GetLastError
0x18003b5fc  mov     edi, eax
0x18003b5fe  test    eax, eax
0x18003b600  jle     short loc_18003B608
0x18003b602  movzx   edi, ax
  ... truncated ...
```
