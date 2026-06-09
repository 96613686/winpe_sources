# RegValueEnumAction::Enumerate(RegValueEnumAction &,HKEY__ *,ushort const *)

- ea: `0x18003ee94`
- end: `0x18003f355`
- name: `?Enumerate@RegValueEnumAction@@SA_NAEAV1@PEAUHKEY__@@PEBG@Z`
- size: `1217`
- prototype: `bool __fastcall(struct RegValueEnumAction *, HKEY, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18003f7b0`
- `0x18003f8bc`
- `0x1800401c4`

## callees

- `0x180009e04`
- `0x18003ee94`
- `0x1800502c2`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003f15e`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003f15e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003eeed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003eeed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f32f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052638`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f32f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052638`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003effa`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003effa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f029`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f057`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f0ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f0d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f2f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f311`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800525e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005260c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f029`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f057`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f0ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f0d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f2f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f311`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800525e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005260c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003f068`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003f0e7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003f068`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003f0e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003f037`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003f0b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003f306`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003f31f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800525ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005261a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003f037`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003f0b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003f306`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003f31f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800525ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005261a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f337`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f337`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eef9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f1ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f274`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eef9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f1ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f274`
- `WDSCORE!CurrentIP` at `0x18003ef01`
- `WDSCORE!CurrentIP` at `0x18003f1f7`
- `WDSCORE!CurrentIP` at `0x18003f27c`
- `WDSCORE!CurrentIP` at `0x18003ef01`
- `WDSCORE!CurrentIP` at `0x18003f1f7`
- `WDSCORE!CurrentIP` at `0x18003f27c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003f26c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003f26c`

## string_xrefs

- `0x18003ef1c`: `RegValueEnumAction::Enumerate: Failed to open key %s\%s (error %d)`

## pseudocode

```c
bool __fastcall RegValueEnumAction::Enumerate(struct RegValueEnumAction *a1, HKEY a2, const unsigned __int16 *a3)
{
  void *v3; // r15
  void *v4; // r14
  LSTATUS InfoKeyW; // esi
  DWORD LastError; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax
  unsigned int v9; // r12d
  DWORD v10; // r13d
  DWORD v11; // ebx
  DWORD v12; // edi
  HANDLE ProcessHeap; // rax
  HANDLE v14; // rax
  HANDLE v15; // rax
  HANDLE v16; // rax
  int v17; // eax
  DWORD v18; // edi
  __int64 v19; // rbx
  struct tagLOG_PARTIAL_MSG *v20; // rax
  DWORD v21; // edi
  __int64 v22; // rbx
  struct tagLOG_PARTIAL_MSG *v23; // rax
  HANDLE v24; // rax
  HANDLE v25; // rax
  DWORD v27; // [rsp+60h] [rbp-98h]
  DWORD cbData; // [rsp+64h] [rbp-94h] BYREF
  DWORD v29; // [rsp+68h] [rbp-90h]
  HKEY hKey; // [rsp+70h] [rbp-88h] BYREF
  void *v31; // [rsp+78h] [rbp-80h]
  void *v32; // [rsp+80h] [rbp-78h]
  int v33; // [rsp+88h] [rbp-70h]
  int v34; // [rsp+8Ch] [rbp-6Ch]
  DWORD cchValueName; // [rsp+90h] [rbp-68h] BYREF
  void *v36; // [rsp+98h] [rbp-60h] BYREF
  DWORD v37; // [rsp+A0h] [rbp-58h]
  int v38; // [rsp+A4h] [rbp-54h]
  void *v39; // [rsp+A8h] [rbp-50h]
  DWORD v40; // [rsp+B0h] [rbp-48h]
  int v41; // [rsp+B4h] [rbp-44h]
  HKEY cbMaxValueLen; // [rsp+108h] [rbp+10h] BYREF
  const unsigned __int16 *cbMaxValueNameLen; // [rsp+110h] [rbp+18h] BYREF
  DWORD Type; // [rsp+118h] [rbp+20h] BYREF

  cbMaxValueNameLen = a3;
  cbMaxValueLen = a2;
  hKey = 0;
  v3 = 0;
  v32 = 0;
  v4 = 0;
  v31 = 0;
  InfoKeyW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\hivelist", 0, 0x20019u, &hKey);
  if ( InfoKeyW )
  {
    LastError = GetLastError();
    v7 = CurrentIP();
    v8 = ConstructPartialMsgW(
           50331648,
           "RegValueEnumAction::Enumerate: Failed to open key %s\\%s (error %d)",
           (const char *)L"HKEY_LOCAL_MACHINE",
           (const char *)L"System\\CurrentControlSet\\Control\\hivelist",
           InfoKeyW);
    WdsSetupLogMessageW(
      v8,
      0,
      L"D",
      0,
      86,
      L"base\\diagnosis\\srt\\srinfra\\recutil\\reg.cpp",
      L"RegValueEnumAction::Enumerate",
      v7,
      LastError,
      0,
      0);
    goto LABEL_33;
  }
  v9 = 0;
  v33 = 0;
  v10 = 0;
  v34 = 0;
  v11 = 0;
  v27 = 0;
  v12 = 0;
  v29 = 0;
  while ( 1 )
  {
    if ( !v12 )
    {
      LODWORD(cbMaxValueNameLen) = 0;
      LODWORD(cbMaxValueLen) = 0;
      InfoKeyW = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, (LPDWORD)&cbMaxValueNameLen, (LPDWORD)&cbMaxValueLen, 0, 0);
      if ( InfoKeyW )
      {
        v21 = GetLastError();
        v22 = CurrentIP();
        v23 = ConstructPartialMsgW(
                0x2000000,
                "RegValueEnumAction::Enumerate: Failed to query key info: %s\\%s (error %d)",
                (const char *)L"HKEY_LOCAL_MACHINE",
                (const char *)L"System\\CurrentControlSet\\Control\\hivelist",
                InfoKeyW);
        WdsSetupLogMessageW(
          v23,
          0,
          L"D",
          0,
          122,
          L"base\\diagnosis\\srt\\srinfra\\recutil\\reg.cpp",
          L"RegValueEnumAction::Enumerate",
          v22,
          v21,
          0,
          0);
        goto LABEL_33;
      }
      if ( (unsigned int)cbMaxValueNameLen > v9 )
      {
        v9 = (unsigned int)cbMaxValueNameLen;
        v33 = (int)cbMaxValueNameLen;
        if ( v3 )
        {
          ProcessHeap = GetProcessHeap();
          if ( HeapFree(ProcessHeap, 0, v3) )
            v3 = 0;
          v32 = v3;
        }
        v14 = GetProcessHeap();
        v3 = HeapAlloc(v14, 8u, 2LL * (v9 + 1));
        v32 = v3;
        if ( !v3 )
        {
LABEL_12:
          InfoKeyW = 14;
          goto LABEL_33;
        }
        v11 = v27;
      }
      if ( (unsigned int)cbMaxValueLen > v10 )
      {
        v10 = (unsigned int)cbMaxValueLen;
        v34 = (int)cbMaxValueLen;
        if ( v4 )
        {
          v15 = GetProcessHeap();
          if ( HeapFree(v15, 0, v4) )
            v4 = 0;
          v31 = v4;
        }
        v27 = v10 + 5;
        v16 = GetProcessHeap();
        v4 = HeapAlloc(v16, 8u, v10 + 5);
        v31 = v4;
        if ( !v4 )
          goto LABEL_12;
        v11 = v10 + 5;
      }
    }
    memset_0(v4, 0, v11);
    Type = 0;
    cchValueName = v9 + 1;
    cbData = v10;
    InfoKeyW = RegEnumValueW(hKey, v12++, (LPWSTR)v3, &cchValueName, 0, &Type, (LPBYTE)v4, &cbData);
    v29 = v12;
    if ( !InfoKeyW )
      break;
LABEL_26:
    if ( InfoKeyW )
      goto LABEL_27;
  }
  v36 = v3;
  v37 = Type;
  v38 = 0;
  v39 = v4;
  v40 = cbData;
  v41 = 0;
  v17 = (*(__int64 (__fastcall **)(struct RegValueEnumAction *, void **))(*(_QWORD *)a1 + 8LL))(a1, &v36);
  if ( v17 )
  {
    if ( v17 == 2 )
      v12 = 0;
    v29 = v12;
    goto LABEL_26;
  }
  InfoKeyW = 259;
LABEL_27:
  if ( InfoKeyW == 259 )
  {
    InfoKeyW = 0;
  }
  else
  {
    v18 = GetLastError();
    v19 = CurrentIP();
    v20 = ConstructPartialMsgW(
            50331648,
            "RegValueEnumAction::Enumerate: Error enumerating contents of key: %s\\%s (error %d)",
            (const char *)L"HKEY_LOCAL_MACHINE",
            (const char *)L"System\\CurrentControlSet\\Control\\hivelist",
            InfoKeyW);
    WdsSetupLogMessageW(
      v20,
      0,
      L"D",
      0,
      203,
      L"base\\diagnosis\\srt\\srinfra\\recutil\\reg.cpp",
      L"RegValueEnumAction::Enumerate",
      v19,
      v18,
      0,
      0);
  }
LABEL_33:
  if ( v4 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v4);
  }
  if ( v3 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v3);
  }
  if ( hKey )
    RegCloseKey(hKey);
  SetLastError(InfoKeyW);
  return InfoKeyW == 0;
}

```

## disassembly

```asm
0x18003ee94  mov     rax, rsp
0x18003ee97  mov     [rax+18h], r8
0x18003ee9b  mov     [rax+10h], rdx
0x18003ee9f  mov     [rax+8], rcx
0x18003eea3  push    rbx
0x18003eea4  push    rsi
0x18003eea5  push    rdi
0x18003eea6  push    r12
0x18003eea8  push    r13
0x18003eeaa  push    r14
0x18003eeac  push    r15
0x18003eeae  sub     rsp, 0C0h
0x18003eeb5  mov     [rsp+0F8h+hKey], 0
0x18003eebe  xor     r15d, r15d
0x18003eec1  mov     [rax-78h], r15
0x18003eec5  xor     r14d, r14d
0x18003eec8  mov     [rax-80h], r14
0x18003eecc  lea     rax, [rsp+0F8h+hKey]
0x18003eed1  mov     [rsp+0F8h+phkResult], rax; phkResult
0x18003eed6  mov     r9d, 20019h; samDesired
0x18003eedc  xor     r8d, r8d; ulOptions
0x18003eedf  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\hiv"...
0x18003eee6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003eeed  call    cs:__imp_RegOpenKeyExW
0x18003eef3  mov     esi, eax
0x18003eef5  test    eax, eax
0x18003eef7  jz      short loc_18003EF65
0x18003eef9  call    cs:__imp_GetLastError
0x18003eeff  mov     edi, eax
0x18003ef01  call    cs:__imp_CurrentIP
0x18003ef07  mov     rbx, rax
0x18003ef0a  mov     dword ptr [rsp+0F8h+phkResult], esi
0x18003ef0e  lea     r9, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\hiv"...
0x18003ef15  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x18003ef1c  lea     rdx, aRegvalueenumac_2; "RegValueEnumAction::Enumerate: Failed t"...
0x18003ef23  mov     ecx, 3000000h; unsigned int
0x18003ef28  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003ef2d  mov     dword ptr [rsp+0F8h+lpcbSecurityDescriptor], r14d
0x18003ef32  mov     [rsp+0F8h+lpcbMaxValueLen], r14
0x18003ef37  mov     dword ptr [rsp+0F8h+lpcbMaxValueNameLen], edi
0x18003ef3b  mov     [rsp+0F8h+lpcValues], rbx
0x18003ef40  lea     rcx, aRegvalueenumac_1; "RegValueEnumAction::Enumerate"
0x18003ef47  mov     [rsp+0F8h+lpcbMaxClassLen], rcx
0x18003ef4c  lea     rcx, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\srinfra\\recutil"...
0x18003ef53  mov     [rsp+0F8h+lpcbMaxSubKeyLen], rcx
0x18003ef58  mov     dword ptr [rsp+0F8h+phkResult], 56h ; 'V'
0x18003ef60  jmp     loc_18003F25D
0x18003ef65  xor     r12d, r12d
0x18003ef68  mov     [rsp+0F8h+var_70], r12d
0x18003ef70  xor     r13d, r13d
0x18003ef73  mov     [rsp+0F8h+var_6C], r13d
0x18003ef7b  xor     ebx, ebx
0x18003ef7d  mov     [rsp+0F8h+var_98], ebx
0x18003ef81  xor     edi, edi
0x18003ef83  mov     [rsp+0F8h+var_90], edi
0x18003ef87  test    edi, edi
0x18003ef89  jnz     loc_18003F0FE
0x18003ef8f  mov     dword ptr [rsp+0F8h+cbMaxValueNameLen], edi
0x18003ef96  mov     dword ptr [rsp+0F8h+cbMaxValueLen], edi
0x18003ef9d  mov     [rsp+0F8h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18003efa6  mov     [rsp+0F8h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18003efaf  lea     rax, [rsp+0F8h+cbMaxValueLen]
0x18003efb7  mov     [rsp+0F8h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18003efbc  lea     rax, [rsp+0F8h+cbMaxValueNameLen]
0x18003efc4  mov     [rsp+0F8h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18003efc9  mov     [rsp+0F8h+lpcValues], 0; lpcValues
0x18003efd2  mov     [rsp+0F8h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x18003efdb  mov     [rsp+0F8h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x18003efe4  mov     [rsp+0F8h+phkResult], 0; lpcSubKeys
0x18003efed  xor     r9d, r9d; lpReserved
0x18003eff0  xor     r8d, r8d; lpcchClass
0x18003eff3  xor     edx, edx; lpClass
0x18003eff5  mov     rcx, [rsp+0F8h+hKey]; hKey
0x18003effa  call    cs:__imp_RegQueryInfoKeyW
0x18003f000  mov     esi, eax
0x18003f002  test    eax, eax
0x18003f004  jnz     loc_18003F274
0x18003f00a  cmp     dword ptr [rsp+0F8h+cbMaxValueNameLen], r12d
0x18003f012  jbe     short loc_18003F08C
0x18003f014  mov     r12d, dword ptr [rsp+0F8h+cbMaxValueNameLen]
0x18003f01c  mov     [rsp+0F8h+var_70], r12d
0x18003f024  test    r15, r15
0x18003f027  jz      short loc_18003F04F
0x18003f029  call    cs:__imp_GetProcessHeap
0x18003f02f  mov     rcx, rax; hHeap
0x18003f032  mov     r8, r15; lpMem
0x18003f035  xor     edx, edx; dwFlags
0x18003f037  call    cs:__imp_HeapFree
0x18003f03d  mov     ecx, eax
0x18003f03f  xor     eax, eax
0x18003f041  test    ecx, ecx
0x18003f043  cmovnz  r15, rax
0x18003f047  mov     [rsp+0F8h+var_78], r15
0x18003f04f  lea     ebx, [r12+1]
0x18003f054  add     rbx, rbx
0x18003f057  call    cs:__imp_GetProcessHeap
0x18003f05d  mov     rcx, rax; hHeap
0x18003f060  mov     r8, rbx; dwBytes
0x18003f063  mov     edx, 8; dwFlags
0x18003f068  call    cs:__imp_HeapAlloc
0x18003f06e  mov     r15, rax
0x18003f071  mov     [rsp+0F8h+var_78], rax
0x18003f079  test    rax, rax
0x18003f07c  jnz     short loc_18003F088
0x18003f07e  mov     esi, 0Eh
0x18003f083  jmp     loc_18003F2F3
0x18003f088  mov     ebx, [rsp+0F8h+var_98]
0x18003f08c  cmp     dword ptr [rsp+0F8h+cbMaxValueLen], r13d
0x18003f094  jbe     short loc_18003F0FE
0x18003f096  mov     r13d, dword ptr [rsp+0F8h+cbMaxValueLen]
0x18003f09e  mov     [rsp+0F8h+var_6C], r13d
0x18003f0a6  test    r14, r14
0x18003f0a9  jz      short loc_18003F0CC
0x18003f0ab  call    cs:__imp_GetProcessHeap
0x18003f0b1  mov     rcx, rax; hHeap
0x18003f0b4  mov     r8, r14; lpMem
0x18003f0b7  xor     edx, edx; dwFlags
0x18003f0b9  call    cs:__imp_HeapFree
0x18003f0bf  xor     ecx, ecx
0x18003f0c1  test    eax, eax
0x18003f0c3  cmovnz  r14, rcx
0x18003f0c7  mov     [rsp+0F8h+var_80], r14
0x18003f0cc  lea     eax, [r13+5]
0x18003f0d0  mov     [rsp+0F8h+var_98], eax
0x18003f0d4  mov     ebx, eax
0x18003f0d6  call    cs:__imp_GetProcessHeap
0x18003f0dc  mov     rcx, rax; hHeap
0x18003f0df  mov     r8d, ebx; dwBytes
0x18003f0e2  mov     edx, 8; dwFlags
0x18003f0e7  call    cs:__imp_HeapAlloc
0x18003f0ed  mov     r14, rax
0x18003f0f0  mov     [rsp+0F8h+var_80], rax
0x18003f0f5  test    rax, rax
0x18003f0f8  jz      short loc_18003F07E
0x18003f0fa  lea     ebx, [r13+5]
0x18003f0fe  mov     r8d, ebx; Size
0x18003f101  xor     edx, edx; Val
0x18003f103  mov     rcx, r14; void *
0x18003f106  call    memset_0
0x18003f10b  mov     [rsp+0F8h+Type], 0
0x18003f116  lea     eax, [r12+1]
0x18003f11b  mov     [rsp+0F8h+cchValueName], eax
0x18003f122  mov     [rsp+0F8h+cbData], r13d
0x18003f127  lea     rax, [rsp+0F8h+cbData]
0x18003f12c  mov     [rsp+0F8h+lpcValues], rax; lpcbData
0x18003f131  mov     [rsp+0F8h+lpcbMaxClassLen], r14; lpData
0x18003f136  lea     rax, [rsp+0F8h+Type]
0x18003f13e  mov     [rsp+0F8h+lpcbMaxSubKeyLen], rax; lpType
0x18003f143  mov     [rsp+0F8h+phkResult], 0; lpReserved
0x18003f14c  lea     r9, [rsp+0F8h+cchValueName]; lpcchValueName
0x18003f154  mov     r8, r15; lpValueName
0x18003f157  mov     edx, edi; dwIndex
0x18003f159  mov     rcx, [rsp+0F8h+hKey]; hKey
0x18003f15e  call    cs:__imp_RegEnumValueW
0x18003f164  mov     esi, eax
0x18003f166  inc     edi
0x18003f168  mov     [rsp+0F8h+var_90], edi
0x18003f16c  test    eax, eax
0x18003f16e  jnz     short loc_18003F1DB
0x18003f170  mov     [rsp+0F8h+var_60], r15
0x18003f178  mov     eax, [rsp+0F8h+Type]
0x18003f17f  mov     [rsp+0F8h+var_58], eax
0x18003f186  xor     eax, eax
0x18003f188  mov     [rsp+0F8h+var_54], eax
0x18003f18f  mov     [rsp+0F8h+var_50], r14
0x18003f197  mov     eax, [rsp+0F8h+cbData]
0x18003f19b  mov     [rsp+0F8h+var_48], eax
0x18003f1a2  xor     eax, eax
0x18003f1a4  mov     [rsp+0F8h+var_44], eax
0x18003f1ab  mov     rcx, [rsp+0F8h+arg_0]
0x18003f1b3  mov     rax, [rcx]
0x18003f1b6  lea     rdx, [rsp+0F8h+var_60]
0x18003f1be  mov     rax, [rax+8]
0x18003f1c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f1c7  test    eax, eax
0x18003f1c9  jz      loc_18003F2E7
0x18003f1cf  xor     ecx, ecx
0x18003f1d1  cmp     eax, 2
0x18003f1d4  cmovz   edi, ecx
0x18003f1d7  mov     [rsp+0F8h+var_90], edi
0x18003f1db  test    esi, esi
0x18003f1dd  jz      loc_18003EF87
0x18003f1e3  cmp     esi, 103h
0x18003f1e9  jz      loc_18003F2F1
0x18003f1ef  call    cs:__imp_GetLastError
0x18003f1f5  mov     edi, eax
0x18003f1f7  call    cs:__imp_CurrentIP
0x18003f1fd  mov     rbx, rax
0x18003f200  mov     dword ptr [rsp+0F8h+phkResult], esi
0x18003f204  lea     r9, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\hiv"...
0x18003f20b  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x18003f212  lea     rdx, aRegvalueenumac; "RegValueEnumAction::Enumerate: Error en"...
0x18003f219  mov     ecx, 3000000h; unsigned int
0x18003f21e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003f223  mov     dword ptr [rsp+0F8h+lpcbSecurityDescriptor], 0
0x18003f22b  mov     [rsp+0F8h+lpcbMaxValueLen], 0
0x18003f234  mov     dword ptr [rsp+0F8h+lpcbMaxValueNameLen], edi
0x18003f238  mov     [rsp+0F8h+lpcValues], rbx
0x18003f23d  lea     rcx, aRegvalueenumac_1; "RegValueEnumAction::Enumerate"
0x18003f244  mov     [rsp+0F8h+lpcbMaxClassLen], rcx
0x18003f249  lea     rcx, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\srinfra\\recutil"...
0x18003f250  mov     [rsp+0F8h+lpcbMaxSubKeyLen], rcx
0x18003f255  mov     dword ptr [rsp+0F8h+phkResult], 0CBh
0x18003f25d  xor     r9d, r9d
0x18003f260  lea     r8, aD; "D"
0x18003f267  xor     edx, edx
0x18003f269  mov     rcx, rax
0x18003f26c  call    cs:__imp_WdsSetupLogMessageW
0x18003f272  jmp     short loc_18003F2F3
0x18003f274  call    cs:__imp_GetLastError
0x18003f27a  mov     edi, eax
0x18003f27c  call    cs:__imp_CurrentIP
0x18003f282  mov     rbx, rax
0x18003f285  mov     dword ptr [rsp+0F8h+phkResult], esi
0x18003f289  lea     r9, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\hiv"...
0x18003f290  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x18003f297  lea     rdx, aRegvalueenumac_0; "RegValueEnumAction::Enumerate: Failed t"...
0x18003f29e  mov     ecx, 2000000h; unsigned int
0x18003f2a3  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003f2a8  mov     dword ptr [rsp+0F8h+lpcbSecurityDescriptor], 0
0x18003f2b0  mov     [rsp+0F8h+lpcbMaxValueLen], 0
0x18003f2b9  mov     dword ptr [rsp+0F8h+lpcbMaxValueNameLen], edi
0x18003f2bd  mov     [rsp+0F8h+lpcValues], rbx
0x18003f2c2  lea     rcx, aRegvalueenumac_1; "RegValueEnumAction::Enumerate"
0x18003f2c9  mov     [rsp+0F8h+lpcbMaxClassLen], rcx
0x18003f2ce  lea     rcx, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\srinfra\\recutil"...
0x18003f2d5  mov     [rsp+0F8h+lpcbMaxSubKeyLen], rcx
0x18003f2da  mov     dword ptr [rsp+0F8h+phkResult], 7Ah ; 'z'
0x18003f2e2  jmp     loc_18003F25D
0x18003f2e7  mov     esi, 103h
0x18003f2ec  jmp     loc_18003F1E3
0x18003f2f1  xor     esi, esi
0x18003f2f3  test    r14, r14
0x18003f2f6  jz      short loc_18003F30C
0x18003f2f8  call    cs:__imp_GetProcessHeap
0x18003f2fe  mov     rcx, rax; hHeap
0x18003f301  mov     r8, r14; lpMem
0x18003f304  xor     edx, edx; dwFlags
0x18003f306  call    cs:__imp_HeapFree
0x18003f30c  test    r15, r15
0x18003f30f  jz      short loc_18003F325
0x18003f311  call    cs:__imp_GetProcessHeap
0x18003f317  mov     rcx, rax; hHeap
0x18003f31a  mov     r8, r15; lpMem
0x18003f31d  xor     edx, edx; dwFlags
0x18003f31f  call    cs:__imp_HeapFree
0x18003f325  mov     rcx, [rsp+0F8h+hKey]; hKey
0x18003f32a  test    rcx, rcx
0x18003f32d  jz      short loc_18003F335
0x18003f32f  call    cs:__imp_RegCloseKey
0x18003f335  mov     ecx, esi; dwErrCode
0x18003f337  call    cs:__imp_SetLastError
0x18003f33d  test    esi, esi
0x18003f33f  setz    al
0x18003f342  add     rsp, 0C0h
0x18003f349  pop     r15
0x18003f34b  pop     r14
0x18003f34d  pop     r13
0x18003f34f  pop     r12
0x18003f351  pop     rdi
0x18003f352  pop     rsi
0x18003f353  pop     rbx
0x18003f354  retn
0x1800525cd  push    rbx
0x1800525cf  push    rbp
0x1800525d0  sub     rsp, 68h
0x1800525d4  mov     rbp, rdx
0x1800525d7  mov     rbx, [rbp+78h]
0x1800525db  test    rbx, rbx
0x1800525de  jz      short loc_180052600
0x1800525e0  call    cs:__imp_GetProcessHeap
0x1800525e6  mov     rcx, rax; hHeap
0x1800525e9  mov     r8, rbx; lpMem
0x1800525ec  xor     edx, edx; dwFlags
0x1800525ee  call    cs:__imp_HeapFree
0x1800525f4  xor     ecx, ecx
0x1800525f6  test    eax, eax
0x1800525f8  cmovnz  rbx, rcx
0x1800525fc  mov     [rbp+78h], rbx
0x180052600  mov     rbx, [rbp+80h]
0x180052607  test    rbx, rbx
0x18005260a  jz      short loc_18005262F
0x18005260c  call    cs:__imp_GetProcessHeap
0x180052612  mov     rcx, rax; hHeap
0x180052615  mov     r8, rbx; lpMem
0x180052618  xor     edx, edx; dwFlags
0x18005261a  call    cs:__imp_HeapFree
0x180052620  xor     ecx, ecx
0x180052622  test    eax, eax
0x180052624  cmovnz  rbx, rcx
0x180052628  mov     [rbp+80h], rbx
0x18005262f  mov     rcx, [rbp+70h]; hKey
0x180052633  test    rcx, rcx
0x180052636  jz      short loc_18005263F
0x180052638  call    cs:__imp_RegCloseKey
0x18005263e  nop
0x18005263f  add     rsp, 68h
0x180052643  pop     rbp
0x180052644  pop     rbx
0x180052645  retn
  ... truncated ...
```
