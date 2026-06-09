# CInstalledApp::_IsMsiLuaCompliant(void)

- ea: `0x18002c368`
- end: `0x18002c46e`
- name: `?_IsMsiLuaCompliant@CInstalledApp@@AEAAHXZ`
- size: `262`
- prototype: `__int64 __fastcall(CInstalledApp *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002a830`

## callees

- `0x18002c368`
- `0x1800582e0`

## import_xrefs

- `msi!__imp_MsiCloseHandle` at `0x18002c43c`
- `msi!__imp_MsiCloseHandle` at `0x18002c446`
- `msi!__imp_MsiCloseHandle` at `0x18002c43c`
- `msi!__imp_MsiCloseHandle` at `0x18002c446`
- `msi!__imp_MsiGetProductInfoW` at `0x18002c3b0`
- `msi!__imp_MsiGetProductInfoW` at `0x18002c3b0`
- `msi!__imp_MsiGetSummaryInformationW` at `0x18002c3ea`
- `msi!__imp_MsiGetSummaryInformationW` at `0x18002c3ea`
- `msi!__imp_MsiOpenDatabaseW` at `0x18002c3ce`
- `msi!__imp_MsiOpenDatabaseW` at `0x18002c3ce`
- `msi!__imp_MsiSummaryInfoGetPropertyW` at `0x18002c41c`
- `msi!__imp_MsiSummaryInfoGetPropertyW` at `0x18002c41c`

## pseudocode

```c
__int64 __fastcall CInstalledApp::_IsMsiLuaCompliant(const WCHAR *this)
{
  unsigned int v1; // ebx
  MSIHANDLE phSummaryInfo; // [rsp+40h] [rbp-C0h] BYREF
  MSIHANDLE phDatabase; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int puiDataType; // [rsp+48h] [rbp-B8h] BYREF
  int piValue; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD pcchValueBuf[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ValueBuf[264]; // [rsp+60h] [rbp-A0h] BYREF

  pcchValueBuf[0] = 260;
  v1 = 0;
  if ( !MsiGetProductInfoW(this + 2098, L"LocalPackage", ValueBuf, pcchValueBuf) )
  {
    phDatabase = 0;
    if ( !MsiOpenDatabaseW(ValueBuf, 0, &phDatabase) )
    {
      phSummaryInfo = 0;
      if ( !MsiGetSummaryInformationW(phDatabase, 0, 0, &phSummaryInfo) )
      {
        puiDataType = 0;
        piValue = 0;
        if ( !MsiSummaryInfoGetPropertyW(phSummaryInfo, 0xFu, &puiDataType, &piValue, 0, 0, 0) && puiDataType == 3 )
          v1 = ((unsigned __int8)piValue >> 3) & 1;
        MsiCloseHandle(phSummaryInfo);
      }
      MsiCloseHandle(phDatabase);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18002c368  mov     [rsp-8+arg_8], rbx
0x18002c36d  push    rbp
0x18002c36e  lea     rbp, [rsp-180h]
0x18002c376  sub     rsp, 280h
0x18002c37d  mov     rax, cs:__security_cookie
0x18002c384  xor     rax, rsp
0x18002c387  mov     [rbp+180h+var_10], rax
0x18002c38e  add     rcx, 1064h; szProduct
0x18002c395  mov     [rsp+280h+pcchValueBuf], 104h
0x18002c39d  lea     r9, [rsp+280h+pcchValueBuf]; pcchValueBuf
0x18002c3a2  xor     ebx, ebx
0x18002c3a4  lea     r8, [rsp+280h+ValueBuf]; lpValueBuf
0x18002c3a9  lea     rdx, aLocalpackage; "LocalPackage"
0x18002c3b0  call    cs:__imp_MsiGetProductInfoW
0x18002c3b6  test    eax, eax
0x18002c3b8  jnz     loc_18002C44C
0x18002c3be  lea     r8, [rsp+280h+phDatabase]; phDatabase
0x18002c3c3  mov     [rsp+280h+phDatabase], ebx
0x18002c3c7  xor     edx, edx; szPersist
0x18002c3c9  lea     rcx, [rsp+280h+ValueBuf]; szDatabasePath
0x18002c3ce  call    cs:__imp_MsiOpenDatabaseW
0x18002c3d4  test    eax, eax
0x18002c3d6  jnz     short loc_18002C44C
0x18002c3d8  mov     ecx, [rsp+280h+phDatabase]; hDatabase
0x18002c3dc  lea     r9, [rsp+280h+phSummaryInfo]; phSummaryInfo
0x18002c3e1  xor     r8d, r8d; uiUpdateCount
0x18002c3e4  mov     [rsp+280h+phSummaryInfo], ebx
0x18002c3e8  xor     edx, edx; szDatabasePath
0x18002c3ea  call    cs:__imp_MsiGetSummaryInformationW
0x18002c3f0  test    eax, eax
0x18002c3f2  jnz     short loc_18002C442
0x18002c3f4  mov     ecx, [rsp+280h+phSummaryInfo]; hSummaryInfo
0x18002c3f8  lea     r9, [rsp+280h+piValue]; piValue
0x18002c3fd  mov     [rsp+280h+var_250], rbx; pcchValueBuf
0x18002c402  lea     r8, [rsp+280h+puiDataType]; puiDataType
0x18002c407  mov     [rsp+280h+szValueBuf], rbx; szValueBuf
0x18002c40c  lea     edx, [rbx+0Fh]; uiProperty
0x18002c40f  mov     [rsp+280h+pftValue], rbx; pftValue
0x18002c414  mov     [rsp+280h+puiDataType], ebx
0x18002c418  mov     [rsp+280h+piValue], ebx
0x18002c41c  call    cs:__imp_MsiSummaryInfoGetPropertyW
0x18002c422  test    eax, eax
0x18002c424  jnz     short loc_18002C438
0x18002c426  cmp     [rsp+280h+puiDataType], 3
0x18002c42b  jnz     short loc_18002C438
0x18002c42d  movzx   ebx, byte ptr [rsp+280h+piValue]
0x18002c432  shr     ebx, 3
0x18002c435  and     ebx, 1
0x18002c438  mov     ecx, [rsp+280h+phSummaryInfo]; hAny
0x18002c43c  call    cs:__imp_MsiCloseHandle
0x18002c442  mov     ecx, [rsp+280h+phDatabase]; hAny
0x18002c446  call    cs:__imp_MsiCloseHandle
0x18002c44c  mov     eax, ebx
0x18002c44e  mov     rcx, [rbp+180h+var_10]
0x18002c455  xor     rcx, rsp; StackCookie
0x18002c458  call    __security_check_cookie
0x18002c45d  mov     rbx, [rsp+280h+arg_8]
0x18002c465  add     rsp, 280h
0x18002c46c  pop     rbp
0x18002c46d  retn
```
