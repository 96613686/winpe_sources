# StoreInitStateForThisUser(ushort const *,bool)

- ea: `0x1800183f8`
- end: `0x18001861d`
- name: `?StoreInitStateForThisUser@@YAXPEBG_N@Z`
- size: `549`
- prototype: `void __fastcall(LPCWSTR lpValueName, struct RegistryHandleRAII *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180013090`
- `0x1800150ac`

## callees

- `0x180004564`
- `0x18000f830`
- `0x1800183f8`
- `0x1800197b4`
- `0x180036a4c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180018439`
- `ADVAPI32!RegCloseKey` at `0x180018496`
- `ADVAPI32!RegCloseKey` at `0x180018519`
- `ADVAPI32!RegCloseKey` at `0x180018439`
- `ADVAPI32!RegCloseKey` at `0x180018496`
- `ADVAPI32!RegCloseKey` at `0x180018519`
- `ADVAPI32!RegOpenKeyExW` at `0x18001846a`
- `ADVAPI32!RegOpenKeyExW` at `0x18001846a`
- `ADVAPI32!RegSetValueExW` at `0x1800184cc`
- `ADVAPI32!RegSetValueExW` at `0x1800184cc`
- `ADVAPI32!RegDeleteValueW` at `0x1800184f1`
- `ADVAPI32!RegDeleteValueW` at `0x1800184f1`

## string_xrefs

- `0x18001845f`: `Printers\V4ConnectionCacheState`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall StoreInitStateForThisUser(LPCWSTR lpValueName, struct RegistryHandleRAII *a2)
{
  char v2; // si
  LSTATUS v4; // eax
  signed int v5; // ebx
  LSTATUS v6; // eax
  signed int v7; // ebx
  LSTATUS v8; // eax
  signed int v9; // ebx
  _BYTE pExceptionObject[40]; // [rsp+38h] [rbp-28h] BYREF
  HKEY v11; // [rsp+90h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+38h] BYREF

  v2 = (char)a2;
  hKey = 0;
  v11 = 0;
  Win32Adapters::Registry::GetCurrentUserLocalSettingsKey(&v11, a2);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v4 = RegOpenKeyExW(v11, L"Printers\\V4ConnectionCacheState", 0, 0x2001Fu, &hKey);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x28u,
        (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
        v5);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v5);
    throw (hr_error *)pExceptionObject;
  }
  if ( v11 )
    RegCloseKey(v11);
  if ( v2 )
  {
    LODWORD(v11) = 1;
    v6 = RegSetValueExW(hKey, lpValueName, 0, 4u, (const BYTE *)&v11, 4u);
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x29u,
          (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
          v7);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v7);
      throw (hr_error *)pExceptionObject;
    }
  }
  else
  {
    v8 = RegDeleteValueW(hKey, lpValueName);
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x2Au,
          (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
          v9);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v9);
      throw (hr_error *)pExceptionObject;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x1800183f8  mov     rax, rsp
0x1800183fb  push    rbp
0x1800183fc  push    rsi
0x1800183fd  push    rdi
0x1800183fe  mov     rbp, rsp
0x180018401  sub     rsp, 60h
0x180018405  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x18001840d  mov     [rax+8], rbx
0x180018411  mov     sil, dl
0x180018414  mov     rdi, rcx
0x180018417  mov     [rbp+hKey], 0
0x18001841f  mov     [rbp+arg_10], 0
0x180018427  lea     rcx, [rbp+arg_10]; phkResult
0x18001842b  call    ?GetCurrentUserLocalSettingsKey@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@@Z; Win32Adapters::Registry::GetCurrentUserLocalSettingsKey(RegistryHandleRAII &)
0x180018430  mov     rcx, [rbp+hKey]; hKey
0x180018434  test    rcx, rcx
0x180018437  jz      short loc_18001844D
0x180018439  call    cs:__imp_RegCloseKey
0x180018440  nop     dword ptr [rax+rax+00h]
0x180018445  mov     [rbp+hKey], 0
0x18001844d  lea     rax, [rbp+hKey]
0x180018451  mov     [rsp+60h+phkResult], rax; phkResult
0x180018456  mov     r9d, 2001Fh; samDesired
0x18001845c  xor     r8d, r8d; ulOptions
0x18001845f  lea     rdx, SubKey; "Printers\\V4ConnectionCacheState"
0x180018466  mov     rcx, [rbp+arg_10]; hKey
0x18001846a  call    cs:__imp_RegOpenKeyExW
0x180018471  nop     dword ptr [rax+rax+00h]
0x180018476  mov     ebx, eax
0x180018478  test    eax, eax
0x18001847a  jle     short loc_180018485
0x18001847c  movzx   ebx, ax
0x18001847f  or      ebx, 80070000h
0x180018485  test    ebx, ebx
0x180018487  js      loc_1800185D0
0x18001848d  mov     rcx, [rbp+arg_10]; hKey
0x180018491  test    rcx, rcx
0x180018494  jz      short loc_1800184A2
0x180018496  call    cs:__imp_RegCloseKey
0x18001849d  nop     dword ptr [rax+rax+00h]
0x1800184a2  mov     rdx, rdi; lpValueName
0x1800184a5  mov     rcx, [rbp+hKey]; hKey
0x1800184a9  test    sil, sil
0x1800184ac  jz      short loc_1800184F1
0x1800184ae  mov     dword ptr [rbp+arg_10], 1
0x1800184b5  mov     r9d, 4; dwType
0x1800184bb  mov     [rsp+60h+cbData], r9d; cbData
0x1800184c0  lea     rax, [rbp+arg_10]
0x1800184c4  mov     [rsp+60h+phkResult], rax; lpData
0x1800184c9  xor     r8d, r8d; Reserved
0x1800184cc  call    cs:__imp_RegSetValueExW
0x1800184d3  nop     dword ptr [rax+rax+00h]
0x1800184d8  mov     ebx, eax
0x1800184da  test    eax, eax
0x1800184dc  jle     short loc_1800184E7
0x1800184de  movzx   ebx, ax
0x1800184e1  or      ebx, 80070000h
0x1800184e7  test    ebx, ebx
0x1800184e9  js      loc_180018583
0x1800184ef  jmp     short loc_180018510
0x1800184f1  call    cs:__imp_RegDeleteValueW
0x1800184f8  nop     dword ptr [rax+rax+00h]
0x1800184fd  mov     ebx, eax
0x1800184ff  test    eax, eax
0x180018501  jle     short loc_18001850C
0x180018503  movzx   ebx, ax
0x180018506  or      ebx, 80070000h
0x18001850c  test    ebx, ebx
0x18001850e  js      short loc_180018536
0x180018510  mov     rcx, [rbp+hKey]; hKey
0x180018514  test    rcx, rcx
0x180018517  jz      short loc_180018525
0x180018519  call    cs:__imp_RegCloseKey
0x180018520  nop     dword ptr [rax+rax+00h]
0x180018525  mov     rbx, [rsp+60h+arg_0]
0x18001852d  add     rsp, 60h
0x180018531  pop     rdi
0x180018532  pop     rsi
0x180018533  pop     rbp
0x180018534  retn
0x180018536  lea     rax, WPP_GLOBAL_Control
0x18001853d  mov     rcx, cs:WPP_GLOBAL_Control
0x180018544  cmp     rcx, rax
0x180018547  jz      short loc_180018567
0x180018549  test    byte ptr [rcx+44h], 1
0x18001854d  jz      short loc_180018567
0x18001854f  mov     edx, 2Ah ; '*'
0x180018554  mov     r9d, ebx
0x180018557  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x18001855e  mov     rcx, [rcx+38h]
0x180018562  call    WPP_SF_d
0x180018567  mov     edx, ebx; int
0x180018569  lea     rcx, [rbp+pExceptionObject]; this
0x18001856d  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180018572  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180018579  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001857d  call    _CxxThrowException_0
0x180018583  lea     rax, WPP_GLOBAL_Control
0x18001858a  mov     rcx, cs:WPP_GLOBAL_Control
0x180018591  cmp     rcx, rax
0x180018594  jz      short loc_1800185B4
0x180018596  test    byte ptr [rcx+44h], 1
0x18001859a  jz      short loc_1800185B4
0x18001859c  mov     edx, 29h ; ')'
0x1800185a1  mov     r9d, ebx
0x1800185a4  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x1800185ab  mov     rcx, [rcx+38h]
0x1800185af  call    WPP_SF_d
0x1800185b4  mov     edx, ebx; int
0x1800185b6  lea     rcx, [rbp+pExceptionObject]; this
0x1800185ba  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800185bf  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800185c6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800185ca  call    _CxxThrowException_0
0x1800185d0  lea     rax, WPP_GLOBAL_Control
0x1800185d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800185de  cmp     rcx, rax
0x1800185e1  jz      short loc_180018601
0x1800185e3  test    byte ptr [rcx+44h], 1
0x1800185e7  jz      short loc_180018601
0x1800185e9  mov     edx, 28h ; '('
0x1800185ee  mov     r9d, ebx
0x1800185f1  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x1800185f8  mov     rcx, [rcx+38h]
0x1800185fc  call    WPP_SF_d
0x180018601  mov     edx, ebx; int
0x180018603  lea     rcx, [rbp+pExceptionObject]; this
0x180018607  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18001860c  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180018613  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180018617  call    _CxxThrowException_0
```
