# RegValueEnumAction::Enumerate(RegValueEnumAction &,HKEY__ *,ushort const *)

- ea: `0x140056998`
- end: `0x140056ed0`
- name: `?Enumerate@RegValueEnumAction@@SA_NAEAV1@PEAUHKEY__@@PEBG@Z`
- size: `1336`
- prototype: `bool __fastcall(struct RegValueEnumAction *, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140059484`

## callees

- `0x140002116`
- `0x140055d10`
- `0x140056998`
- `0x140082010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1400569ef`
- `ADVAPI32!RegOpenKeyExW` at `0x1400569ef`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140056af9`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140056af9`
- `ADVAPI32!RegCloseKey` at `0x140056e9d`
- `ADVAPI32!RegCloseKey` at `0x1400818bf`
- `ADVAPI32!RegCloseKey` at `0x140056e9d`
- `ADVAPI32!RegCloseKey` at `0x1400818bf`
- `ADVAPI32!RegEnumValueW` at `0x140056c97`
- `ADVAPI32!RegEnumValueW` at `0x140056c97`
- `KERNEL32!HeapFree` at `0x140056b46`
- `KERNEL32!HeapFree` at `0x140056be2`
- `KERNEL32!HeapFree` at `0x140056e62`
- `KERNEL32!HeapFree` at `0x140056e87`
- `KERNEL32!HeapFree` at `0x140081863`
- `KERNEL32!HeapFree` at `0x14008189b`
- `KERNEL32!HeapFree` at `0x140056b46`
- `KERNEL32!HeapFree` at `0x140056be2`
- `KERNEL32!HeapFree` at `0x140056e62`
- `KERNEL32!HeapFree` at `0x140056e87`
- `KERNEL32!HeapFree` at `0x140081863`
- `KERNEL32!HeapFree` at `0x14008189b`
- `KERNEL32!HeapAlloc` at `0x140056b81`
- `KERNEL32!HeapAlloc` at `0x140056c1c`
- `KERNEL32!HeapAlloc` at `0x140056b81`
- `KERNEL32!HeapAlloc` at `0x140056c1c`
- `KERNEL32!GetProcessHeap` at `0x140056b32`
- `KERNEL32!GetProcessHeap` at `0x140056b6a`
- `KERNEL32!GetProcessHeap` at `0x140056bce`
- `KERNEL32!GetProcessHeap` at `0x140056c05`
- `KERNEL32!GetProcessHeap` at `0x140056e4e`
- `KERNEL32!GetProcessHeap` at `0x140056e73`
- `KERNEL32!GetProcessHeap` at `0x14008184f`
- `KERNEL32!GetProcessHeap` at `0x140081887`
- `KERNEL32!GetProcessHeap` at `0x140056b32`
- `KERNEL32!GetProcessHeap` at `0x140056b6a`
- `KERNEL32!GetProcessHeap` at `0x140056bce`
- `KERNEL32!GetProcessHeap` at `0x140056c05`
- `KERNEL32!GetProcessHeap` at `0x140056e4e`
- `KERNEL32!GetProcessHeap` at `0x140056e73`
- `KERNEL32!GetProcessHeap` at `0x14008184f`
- `KERNEL32!GetProcessHeap` at `0x140081887`
- `KERNEL32!GetLastError` at `0x140056a03`
- `KERNEL32!GetLastError` at `0x140056d30`
- `KERNEL32!GetLastError` at `0x140056dc4`
- `KERNEL32!GetLastError` at `0x140056a03`
- `KERNEL32!GetLastError` at `0x140056d30`
- `KERNEL32!GetLastError` at `0x140056dc4`
- `KERNEL32!SetLastError` at `0x140056eab`
- `KERNEL32!SetLastError` at `0x140056eab`
- `WDSCORE!WdsSetupLogMessageW` at `0x140056db3`
- `WDSCORE!WdsSetupLogMessageW` at `0x140056db3`
- `WDSCORE!CurrentIP` at `0x140056a11`
- `WDSCORE!CurrentIP` at `0x140056d3e`
- `WDSCORE!CurrentIP` at `0x140056dd2`
- `WDSCORE!CurrentIP` at `0x140056a11`
- `WDSCORE!CurrentIP` at `0x140056d3e`
- `WDSCORE!CurrentIP` at `0x140056dd2`

## string_xrefs

- `0x140056a32`: `RegValueEnumAction::Enumerate: Failed to open key %s\%s (error %d)`

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
      171,
      L"base\\ntsetup\\setupplatform\\lib\\static\\utilities.cpp",
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
          207,
          L"base\\ntsetup\\setupplatform\\lib\\static\\utilities.cpp",
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
      288,
      L"base\\ntsetup\\setupplatform\\lib\\static\\utilities.cpp",
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
0x140056998  mov     r11, rsp
0x14005699b  mov     [r11+18h], r8
0x14005699f  mov     [r11+10h], rdx
0x1400569a3  mov     [r11+8], rcx
0x1400569a7  push    rbx
0x1400569a8  push    rsi
0x1400569a9  push    rdi
0x1400569aa  push    r12
0x1400569ac  push    r13
0x1400569ae  push    r14
0x1400569b0  push    r15
0x1400569b2  sub     rsp, 0C0h
0x1400569b9  xor     eax, eax
0x1400569bb  mov     [rsp+0F8h+hKey], rax
0x1400569c0  mov     r15d, eax
0x1400569c3  mov     [r11-78h], rax
0x1400569c7  mov     r14d, eax
0x1400569ca  mov     [r11-80h], rax
0x1400569ce  lea     rax, [rsp+0F8h+hKey]
0x1400569d3  mov     [rsp+0F8h+phkResult], rax; phkResult
0x1400569d8  mov     r9d, 20019h; samDesired
0x1400569de  xor     r8d, r8d; ulOptions
0x1400569e1  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\hiv"...
0x1400569e8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400569ef  call    cs:__imp_RegOpenKeyExW
0x1400569f6  nop     dword ptr [rax+rax+00h]
0x1400569fb  mov     esi, eax
0x1400569fd  xor     ecx, ecx
0x1400569ff  test    eax, eax
0x140056a01  jz      short loc_140056A7E
0x140056a03  call    cs:__imp_GetLastError
0x140056a0a  nop     dword ptr [rax+rax+00h]
0x140056a0f  mov     edi, eax
0x140056a11  call    cs:__imp_CurrentIP
0x140056a18  nop     dword ptr [rax+rax+00h]
0x140056a1d  mov     rbx, rax
0x140056a20  mov     dword ptr [rsp+0F8h+phkResult], esi
0x140056a24  lea     r9, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\hiv"...
0x140056a2b  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x140056a32  lea     rdx, aRegvalueenumac_2; "RegValueEnumAction::Enumerate: Failed t"...
0x140056a39  mov     ecx, 3000000h; unsigned int
0x140056a3e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x140056a43  xor     r12d, r12d
0x140056a46  mov     dword ptr [rsp+0F8h+lpcbSecurityDescriptor], r12d
0x140056a4b  mov     [rsp+0F8h+lpcbMaxValueLen], r12
0x140056a50  mov     dword ptr [rsp+0F8h+lpcbMaxValueNameLen], edi
0x140056a54  mov     [rsp+0F8h+lpcValues], rbx
0x140056a59  lea     rcx, aRegvalueenumac_1; "RegValueEnumAction::Enumerate"
0x140056a60  mov     [rsp+0F8h+lpcbMaxClassLen], rcx
0x140056a65  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\lib\\stat"...
0x140056a6c  mov     [rsp+0F8h+lpcbMaxSubKeyLen], rcx
0x140056a71  mov     dword ptr [rsp+0F8h+phkResult], 0ABh
0x140056a79  jmp     loc_140056DA4
0x140056a7e  mov     r12d, ecx
0x140056a81  mov     [rsp+0F8h+var_70], ecx
0x140056a88  mov     r13d, ecx
0x140056a8b  mov     [rsp+0F8h+var_6C], ecx
0x140056a92  mov     ebx, ecx
0x140056a94  mov     [rsp+0F8h+var_98], ecx
0x140056a98  mov     edi, ecx
0x140056a9a  mov     [rsp+0F8h+var_90], ecx
0x140056a9e  test    edi, edi
0x140056aa0  jnz     loc_140056C3D
0x140056aa6  mov     dword ptr [rsp+0F8h+cbMaxValueNameLen], ecx
0x140056aad  mov     dword ptr [rsp+0F8h+cbMaxValueLen], ecx
0x140056ab4  mov     [rsp+0F8h+lpftLastWriteTime], rcx; lpftLastWriteTime
0x140056ab9  mov     [rsp+0F8h+lpcbSecurityDescriptor], rcx; lpcbSecurityDescriptor
0x140056abe  lea     rax, [rsp+0F8h+cbMaxValueLen]
0x140056ac6  mov     [rsp+0F8h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x140056acb  lea     rax, [rsp+0F8h+cbMaxValueNameLen]
0x140056ad3  mov     [rsp+0F8h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x140056ad8  mov     [rsp+0F8h+lpcValues], rcx; lpcValues
0x140056add  mov     [rsp+0F8h+lpcbMaxClassLen], rcx; lpcbMaxClassLen
0x140056ae2  mov     [rsp+0F8h+lpcbMaxSubKeyLen], rcx; lpcbMaxSubKeyLen
0x140056ae7  mov     [rsp+0F8h+phkResult], rcx; lpcSubKeys
0x140056aec  xor     r9d, r9d; lpReserved
0x140056aef  xor     r8d, r8d; lpcchClass
0x140056af2  xor     edx, edx; lpClass
0x140056af4  mov     rcx, [rsp+0F8h+hKey]; hKey
0x140056af9  call    cs:__imp_RegQueryInfoKeyW
0x140056b00  nop     dword ptr [rax+rax+00h]
0x140056b05  mov     esi, eax
0x140056b07  test    eax, eax
0x140056b09  jnz     loc_140056DC4
0x140056b0f  cmp     dword ptr [rsp+0F8h+cbMaxValueNameLen], r12d
0x140056b17  jbe     loc_140056BAB
0x140056b1d  mov     r12d, dword ptr [rsp+0F8h+cbMaxValueNameLen]
0x140056b25  mov     [rsp+0F8h+var_70], r12d
0x140056b2d  test    r15, r15
0x140056b30  jz      short loc_140056B62
0x140056b32  call    cs:__imp_GetProcessHeap
0x140056b39  nop     dword ptr [rax+rax+00h]
0x140056b3e  mov     rcx, rax; hHeap
0x140056b41  mov     r8, r15; lpMem
0x140056b44  xor     edx, edx; dwFlags
0x140056b46  call    cs:__imp_HeapFree
0x140056b4d  nop     dword ptr [rax+rax+00h]
0x140056b52  xor     ecx, ecx
0x140056b54  test    eax, eax
0x140056b56  cmovnz  r15, rcx
0x140056b5a  mov     [rsp+0F8h+var_78], r15
0x140056b62  lea     ebx, [r12+1]
0x140056b67  add     rbx, rbx
0x140056b6a  call    cs:__imp_GetProcessHeap
0x140056b71  nop     dword ptr [rax+rax+00h]
0x140056b76  mov     rcx, rax; hHeap
0x140056b79  mov     r8, rbx; dwBytes
0x140056b7c  mov     edx, 8; dwFlags
0x140056b81  call    cs:__imp_HeapAlloc
0x140056b88  nop     dword ptr [rax+rax+00h]
0x140056b8d  mov     r15, rax
0x140056b90  mov     [rsp+0F8h+var_78], rax
0x140056b98  test    rax, rax
0x140056b9b  jnz     short loc_140056BA7
0x140056b9d  mov     esi, 0Eh
0x140056ba2  jmp     loc_140056E49
0x140056ba7  mov     ebx, [rsp+0F8h+var_98]
0x140056bab  cmp     dword ptr [rsp+0F8h+cbMaxValueLen], r13d
0x140056bb3  jbe     loc_140056C3D
0x140056bb9  mov     r13d, dword ptr [rsp+0F8h+cbMaxValueLen]
0x140056bc1  mov     [rsp+0F8h+var_6C], r13d
0x140056bc9  test    r14, r14
0x140056bcc  jz      short loc_140056BFB
0x140056bce  call    cs:__imp_GetProcessHeap
0x140056bd5  nop     dword ptr [rax+rax+00h]
0x140056bda  mov     rcx, rax; hHeap
0x140056bdd  mov     r8, r14; lpMem
0x140056be0  xor     edx, edx; dwFlags
0x140056be2  call    cs:__imp_HeapFree
0x140056be9  nop     dword ptr [rax+rax+00h]
0x140056bee  xor     ecx, ecx
0x140056bf0  test    eax, eax
0x140056bf2  cmovnz  r14, rcx
0x140056bf6  mov     [rsp+0F8h+var_80], r14
0x140056bfb  lea     eax, [r13+5]
0x140056bff  mov     [rsp+0F8h+var_98], eax
0x140056c03  mov     ebx, eax
0x140056c05  call    cs:__imp_GetProcessHeap
0x140056c0c  nop     dword ptr [rax+rax+00h]
0x140056c11  mov     rcx, rax; hHeap
0x140056c14  mov     r8d, ebx; dwBytes
0x140056c17  mov     edx, 8; dwFlags
0x140056c1c  call    cs:__imp_HeapAlloc
0x140056c23  nop     dword ptr [rax+rax+00h]
0x140056c28  mov     r14, rax
0x140056c2b  mov     [rsp+0F8h+var_80], rax
0x140056c30  test    rax, rax
0x140056c33  jz      loc_140056B9D
0x140056c39  lea     ebx, [r13+5]
0x140056c3d  mov     r8d, ebx; Size
0x140056c40  xor     edx, edx; Val
0x140056c42  mov     rcx, r14; void *
0x140056c45  call    memset_0
0x140056c4a  xor     ecx, ecx
0x140056c4c  mov     [rsp+0F8h+Type], ecx
0x140056c53  lea     eax, [r12+1]
0x140056c58  mov     [rsp+0F8h+cchValueName], eax
0x140056c5f  mov     [rsp+0F8h+cbData], r13d
0x140056c64  lea     rax, [rsp+0F8h+cbData]
0x140056c69  mov     [rsp+0F8h+lpcValues], rax; lpcbData
0x140056c6e  mov     [rsp+0F8h+lpcbMaxClassLen], r14; lpData
0x140056c73  lea     rax, [rsp+0F8h+Type]
0x140056c7b  mov     [rsp+0F8h+lpcbMaxSubKeyLen], rax; lpType
0x140056c80  mov     [rsp+0F8h+phkResult], rcx; lpReserved
0x140056c85  lea     r9, [rsp+0F8h+cchValueName]; lpcchValueName
0x140056c8d  mov     r8, r15; lpValueName
0x140056c90  mov     edx, edi; dwIndex
0x140056c92  mov     rcx, [rsp+0F8h+hKey]; hKey
0x140056c97  call    cs:__imp_RegEnumValueW
0x140056c9e  nop     dword ptr [rax+rax+00h]
0x140056ca3  mov     esi, eax
0x140056ca5  inc     edi
0x140056ca7  mov     [rsp+0F8h+var_90], edi
0x140056cab  xor     ecx, ecx
0x140056cad  test    eax, eax
0x140056caf  jnz     short loc_140056D1C
0x140056cb1  mov     [rsp+0F8h+var_60], r15
0x140056cb9  mov     eax, [rsp+0F8h+Type]
0x140056cc0  mov     [rsp+0F8h+var_58], eax
0x140056cc7  xor     eax, eax
0x140056cc9  mov     [rsp+0F8h+var_54], eax
0x140056cd0  mov     [rsp+0F8h+var_50], r14
0x140056cd8  mov     eax, [rsp+0F8h+cbData]
0x140056cdc  mov     [rsp+0F8h+var_48], eax
0x140056ce3  xor     eax, eax
0x140056ce5  mov     [rsp+0F8h+var_44], eax
0x140056cec  mov     rcx, [rsp+0F8h+arg_0]
0x140056cf4  mov     rax, [rcx]
0x140056cf7  lea     rdx, [rsp+0F8h+var_60]
0x140056cff  mov     rax, [rax+8]
0x140056d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140056d08  xor     ecx, ecx
0x140056d0a  test    eax, eax
0x140056d0c  jz      loc_140056E3D
0x140056d12  cmp     eax, 2
0x140056d15  cmovz   edi, ecx
0x140056d18  mov     [rsp+0F8h+var_90], edi
0x140056d1c  test    esi, esi
0x140056d1e  jz      loc_140056A9E
0x140056d24  cmp     esi, 103h
0x140056d2a  jz      loc_140056E47
0x140056d30  call    cs:__imp_GetLastError
0x140056d37  nop     dword ptr [rax+rax+00h]
0x140056d3c  mov     edi, eax
0x140056d3e  call    cs:__imp_CurrentIP
0x140056d45  nop     dword ptr [rax+rax+00h]
0x140056d4a  mov     rbx, rax
0x140056d4d  mov     dword ptr [rsp+0F8h+phkResult], esi
0x140056d51  lea     r9, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\hiv"...
0x140056d58  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x140056d5f  lea     rdx, aRegvalueenumac; "RegValueEnumAction::Enumerate: Error en"...
0x140056d66  mov     ecx, 3000000h; unsigned int
0x140056d6b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x140056d70  xor     ecx, ecx
0x140056d72  mov     dword ptr [rsp+0F8h+lpcbSecurityDescriptor], ecx
0x140056d76  mov     [rsp+0F8h+lpcbMaxValueLen], rcx
0x140056d7b  mov     dword ptr [rsp+0F8h+lpcbMaxValueNameLen], edi
0x140056d7f  mov     [rsp+0F8h+lpcValues], rbx
0x140056d84  lea     rcx, aRegvalueenumac_1; "RegValueEnumAction::Enumerate"
0x140056d8b  mov     [rsp+0F8h+lpcbMaxClassLen], rcx
0x140056d90  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\lib\\stat"...
0x140056d97  mov     [rsp+0F8h+lpcbMaxSubKeyLen], rcx
0x140056d9c  mov     dword ptr [rsp+0F8h+phkResult], 120h
0x140056da4  xor     r9d, r9d
0x140056da7  lea     r8, aD; "D"
0x140056dae  xor     edx, edx
0x140056db0  mov     rcx, rax
0x140056db3  call    cs:__imp_WdsSetupLogMessageW
0x140056dba  nop     dword ptr [rax+rax+00h]
0x140056dbf  jmp     loc_140056E49
0x140056dc4  call    cs:__imp_GetLastError
0x140056dcb  nop     dword ptr [rax+rax+00h]
0x140056dd0  mov     edi, eax
0x140056dd2  call    cs:__imp_CurrentIP
0x140056dd9  nop     dword ptr [rax+rax+00h]
0x140056dde  mov     rbx, rax
0x140056de1  mov     dword ptr [rsp+0F8h+phkResult], esi
0x140056de5  lea     r9, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\hiv"...
0x140056dec  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x140056df3  lea     rdx, aRegvalueenumac_0; "RegValueEnumAction::Enumerate: Failed t"...
0x140056dfa  mov     ecx, 2000000h; unsigned int
0x140056dff  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x140056e04  xor     ecx, ecx
0x140056e06  mov     dword ptr [rsp+0F8h+lpcbSecurityDescriptor], ecx
0x140056e0a  mov     [rsp+0F8h+lpcbMaxValueLen], rcx
0x140056e0f  mov     dword ptr [rsp+0F8h+lpcbMaxValueNameLen], edi
0x140056e13  mov     [rsp+0F8h+lpcValues], rbx
0x140056e18  lea     rcx, aRegvalueenumac_1; "RegValueEnumAction::Enumerate"
0x140056e1f  mov     [rsp+0F8h+lpcbMaxClassLen], rcx
0x140056e24  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\lib\\stat"...
0x140056e2b  mov     [rsp+0F8h+lpcbMaxSubKeyLen], rcx
0x140056e30  mov     dword ptr [rsp+0F8h+phkResult], 0CFh
0x140056e38  jmp     loc_140056DA4
0x140056e3d  mov     esi, 103h
0x140056e42  jmp     loc_140056D24
0x140056e47  mov     esi, ecx
0x140056e49  test    r14, r14
0x140056e4c  jz      short loc_140056E6E
0x140056e4e  call    cs:__imp_GetProcessHeap
0x140056e55  nop     dword ptr [rax+rax+00h]
0x140056e5a  mov     rcx, rax; hHeap
0x140056e5d  mov     r8, r14; lpMem
0x140056e60  xor     edx, edx; dwFlags
0x140056e62  call    cs:__imp_HeapFree
0x140056e69  nop     dword ptr [rax+rax+00h]
0x140056e6e  test    r15, r15
0x140056e71  jz      short loc_140056E93
0x140056e73  call    cs:__imp_GetProcessHeap
0x140056e7a  nop     dword ptr [rax+rax+00h]
0x140056e7f  mov     rcx, rax; hHeap
0x140056e82  mov     r8, r15; lpMem
0x140056e85  xor     edx, edx; dwFlags
0x140056e87  call    cs:__imp_HeapFree
0x140056e8e  nop     dword ptr [rax+rax+00h]
0x140056e93  mov     rcx, [rsp+0F8h+hKey]; hKey
0x140056e98  test    rcx, rcx
0x140056e9b  jz      short loc_140056EA9
0x140056e9d  call    cs:__imp_RegCloseKey
0x140056ea4  nop     dword ptr [rax+rax+00h]
0x140056ea9  mov     ecx, esi; dwErrCode
0x140056eab  call    cs:__imp_SetLastError
0x140056eb2  nop     dword ptr [rax+rax+00h]
0x140056eb7  test    esi, esi
0x140056eb9  setz    al
0x140056ebc  add     rsp, 0C0h
0x140056ec3  pop     r15
0x140056ec5  pop     r14
0x140056ec7  pop     r13
0x140056ec9  pop     r12
0x140056ecb  pop     rdi
0x140056ecc  pop     rsi
0x140056ecd  pop     rbx
0x140056ece  retn
0x14008183c  push    rbx
0x14008183e  push    rbp
0x14008183f  sub     rsp, 68h
0x140081843  mov     rbp, rdx
0x140081846  mov     rbx, [rbp+78h]
0x14008184a  test    rbx, rbx
0x14008184d  jz      short loc_14008187B
  ... truncated ...
```
