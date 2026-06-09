# StoreInitStateForThisUser(ushort const *,bool)

- ea: `0x180017910`
- end: `0x180017b10`
- name: `?StoreInitStateForThisUser@@YAXPEBG_N@Z`
- size: `512`
- prototype: `void __fastcall(LPCWSTR lpValueName, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18001290c`
- `0x1800147b8`

## callees

- `0x180004424`
- `0x18000f380`
- `0x180017910`
- `0x180018bbc`
- `0x180035814`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180017951`
- `ADVAPI32!RegCloseKey` at `0x1800179a2`
- `ADVAPI32!RegCloseKey` at `0x180017a13`
- `ADVAPI32!RegCloseKey` at `0x180017951`
- `ADVAPI32!RegCloseKey` at `0x1800179a2`
- `ADVAPI32!RegCloseKey` at `0x180017a13`
- `ADVAPI32!RegOpenKeyExW` at `0x18001797c`
- `ADVAPI32!RegOpenKeyExW` at `0x18001797c`
- `ADVAPI32!RegSetValueExW` at `0x1800179d2`
- `ADVAPI32!RegSetValueExW` at `0x1800179d2`
- `ADVAPI32!RegDeleteValueW` at `0x1800179f1`
- `ADVAPI32!RegDeleteValueW` at `0x1800179f1`

## string_xrefs

- `0x180017971`: `Printers\V4ConnectionCacheState`

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
        40,
        WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids,
        (unsigned int)v5);
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
          41,
          WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids,
          (unsigned int)v7);
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
          42,
          WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids,
          (unsigned int)v9);
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
0x180017910  mov     rax, rsp
0x180017913  push    rbp
0x180017914  push    rsi
0x180017915  push    rdi
0x180017916  mov     rbp, rsp
0x180017919  sub     rsp, 60h
0x18001791d  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x180017925  mov     [rax+8], rbx
0x180017929  mov     sil, dl
0x18001792c  mov     rdi, rcx
0x18001792f  mov     [rbp+hKey], 0
0x180017937  mov     [rbp+arg_10], 0
0x18001793f  lea     rcx, [rbp+arg_10]; phkResult
0x180017943  call    ?GetCurrentUserLocalSettingsKey@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@@Z; Win32Adapters::Registry::GetCurrentUserLocalSettingsKey(RegistryHandleRAII &)
0x180017948  mov     rcx, [rbp+hKey]; hKey
0x18001794c  test    rcx, rcx
0x18001794f  jz      short loc_18001795F
0x180017951  call    cs:__imp_RegCloseKey
0x180017957  mov     [rbp+hKey], 0
0x18001795f  lea     rax, [rbp+hKey]
0x180017963  mov     [rsp+60h+phkResult], rax; phkResult
0x180017968  mov     r9d, 2001Fh; samDesired
0x18001796e  xor     r8d, r8d; ulOptions
0x180017971  lea     rdx, SubKey; "Printers\\V4ConnectionCacheState"
0x180017978  mov     rcx, [rbp+arg_10]; hKey
0x18001797c  call    cs:__imp_RegOpenKeyExW
0x180017982  mov     ebx, eax
0x180017984  test    eax, eax
0x180017986  jle     short loc_180017991
0x180017988  movzx   ebx, ax
0x18001798b  or      ebx, 80070000h
0x180017991  test    ebx, ebx
0x180017993  js      loc_180017AC3
0x180017999  mov     rcx, [rbp+arg_10]; hKey
0x18001799d  test    rcx, rcx
0x1800179a0  jz      short loc_1800179A8
0x1800179a2  call    cs:__imp_RegCloseKey
0x1800179a8  mov     rdx, rdi; lpValueName
0x1800179ab  mov     rcx, [rbp+hKey]; hKey
0x1800179af  test    sil, sil
0x1800179b2  jz      short loc_1800179F1
0x1800179b4  mov     dword ptr [rbp+arg_10], 1
0x1800179bb  mov     r9d, 4; dwType
0x1800179c1  mov     [rsp+60h+cbData], r9d; cbData
0x1800179c6  lea     rax, [rbp+arg_10]
0x1800179ca  mov     [rsp+60h+phkResult], rax; lpData
0x1800179cf  xor     r8d, r8d; Reserved
0x1800179d2  call    cs:__imp_RegSetValueExW
0x1800179d8  mov     ebx, eax
0x1800179da  test    eax, eax
0x1800179dc  jle     short loc_1800179E7
0x1800179de  movzx   ebx, ax
0x1800179e1  or      ebx, 80070000h
0x1800179e7  test    ebx, ebx
0x1800179e9  js      loc_180017A76
0x1800179ef  jmp     short loc_180017A0A
0x1800179f1  call    cs:__imp_RegDeleteValueW
0x1800179f7  mov     ebx, eax
0x1800179f9  test    eax, eax
0x1800179fb  jle     short loc_180017A06
0x1800179fd  movzx   ebx, ax
0x180017a00  or      ebx, 80070000h
0x180017a06  test    ebx, ebx
0x180017a08  js      short loc_180017A29
0x180017a0a  mov     rcx, [rbp+hKey]; hKey
0x180017a0e  test    rcx, rcx
0x180017a11  jz      short loc_180017A19
0x180017a13  call    cs:__imp_RegCloseKey
0x180017a19  mov     rbx, [rsp+60h+arg_0]
0x180017a21  add     rsp, 60h
0x180017a25  pop     rdi
0x180017a26  pop     rsi
0x180017a27  pop     rbp
0x180017a28  retn
0x180017a29  lea     rax, WPP_GLOBAL_Control
0x180017a30  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a37  cmp     rcx, rax
0x180017a3a  jz      short loc_180017A5A
0x180017a3c  test    byte ptr [rcx+44h], 1
0x180017a40  jz      short loc_180017A5A
0x180017a42  mov     edx, 2Ah ; '*'
0x180017a47  mov     r9d, ebx
0x180017a4a  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x180017a51  mov     rcx, [rcx+38h]
0x180017a55  call    WPP_SF_d
0x180017a5a  mov     edx, ebx; int
0x180017a5c  lea     rcx, [rbp+pExceptionObject]; this
0x180017a60  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180017a65  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180017a6c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017a70  call    _CxxThrowException_0
0x180017a76  lea     rax, WPP_GLOBAL_Control
0x180017a7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a84  cmp     rcx, rax
0x180017a87  jz      short loc_180017AA7
0x180017a89  test    byte ptr [rcx+44h], 1
0x180017a8d  jz      short loc_180017AA7
0x180017a8f  mov     edx, 29h ; ')'
0x180017a94  mov     r9d, ebx
0x180017a97  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x180017a9e  mov     rcx, [rcx+38h]
0x180017aa2  call    WPP_SF_d
0x180017aa7  mov     edx, ebx; int
0x180017aa9  lea     rcx, [rbp+pExceptionObject]; this
0x180017aad  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180017ab2  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180017ab9  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017abd  call    _CxxThrowException_0
0x180017ac3  lea     rax, WPP_GLOBAL_Control
0x180017aca  mov     rcx, cs:WPP_GLOBAL_Control
0x180017ad1  cmp     rcx, rax
0x180017ad4  jz      short loc_180017AF4
0x180017ad6  test    byte ptr [rcx+44h], 1
0x180017ada  jz      short loc_180017AF4
0x180017adc  mov     edx, 28h ; '('
0x180017ae1  mov     r9d, ebx
0x180017ae4  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x180017aeb  mov     rcx, [rcx+38h]
0x180017aef  call    WPP_SF_d
0x180017af4  mov     edx, ebx; int
0x180017af6  lea     rcx, [rbp+pExceptionObject]; this
0x180017afa  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180017aff  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180017b06  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017b0a  call    _CxxThrowException_0
```
