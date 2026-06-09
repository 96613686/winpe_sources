# DmSetWindowsAIKPlatformStorageLocation(unsigned __int64)

- ea: `0x18008b4d0`
- end: `0x18008b7d5`
- name: `?DmSetWindowsAIKPlatformStorageLocation@@YAJ_K@Z`
- size: `773`
- prototype: `__int64 __fastcall(NCRYPT_HANDLE hObject)`
- caller_count: `6`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180087a20`
- `0x1800887d0`
- `0x180089090`
- `0x180089a90`
- `0x18008ac80`
- `0x18008b7dc`

## callees

- `0x18005cb4c`
- `0x180081770`
- `0x18008b4d0`
- `0x180090fb8`
- `0x180091860`
- `0x18009196c`
- `0x180094110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b5ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b5d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b615`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b659`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b5ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b5d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b615`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b659`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18008b574`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18008b59f`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18008b607`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18008b64b`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18008b574`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18008b59f`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18008b607`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18008b64b`
- `ncrypt!NCryptSetProperty` at `0x18008b769`
- `ncrypt!NCryptSetProperty` at `0x18008b769`

## string_xrefs

- `0x18008b547`: `ProgramData`
- `0x18008b595`: `ProgramData`
- `0x18008b51a`: `\ProgramData`

## pseudocode

```c
__int64 __fastcall DmSetWindowsAIKPlatformStorageLocation(NCRYPT_HANDLE hObject)
{
  DWORD EnvironmentVariableW; // eax
  DWORD v3; // ebx
  DWORD v4; // esi
  signed int v5; // eax
  unsigned int v6; // ebx
  signed int LastError; // eax
  __int64 v8; // rbx
  DWORD v9; // ebx
  _WORD *v10; // rdx
  _WORD *v11; // r8
  _WORD *v12; // rdx
  _WORD *v13; // r8
  unsigned __int64 v14; // r9
  SECURITY_STATUS v15; // eax
  __int64 v16; // rcx
  LPWSTR lpBuffer; // [rsp+30h] [rbp-39h] BYREF
  _WORD *v19; // [rsp+38h] [rbp-31h]
  _WORD v20[8]; // [rsp+40h] [rbp-29h] BYREF
  PBYTE pbInput; // [rsp+50h] [rbp-19h] BYREF
  char *v22; // [rsp+58h] [rbp-11h]
  _WORD v23[8]; // [rsp+60h] [rbp-9h] BYREF
  _WORD *v24; // [rsp+70h] [rbp+7h] BYREF
  _WORD *v25; // [rsp+78h] [rbp+Fh]
  _WORD v26[8]; // [rsp+80h] [rbp+17h] BYREF
  _WORD *v27; // [rsp+90h] [rbp+27h] BYREF
  _WORD *v28; // [rsp+98h] [rbp+2Fh]
  _WORD v29[16]; // [rsp+A0h] [rbp+37h] BYREF
  int v30; // [rsp+D8h] [rbp+6Fh] BYREF
  char v31; // [rsp+E0h] [rbp+77h] BYREF

  v27 = v29;
  v28 = v29;
  v29[0] = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
    &v27,
    L"\\Microsoft\\Crypto\\PCPKSP\\WindowsAIK",
    35);
  v24 = v26;
  v25 = v26;
  v26[0] = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
    &v24,
    L"\\ProgramData",
    12);
  lpBuffer = v20;
  v19 = v20;
  v20[0] = 0;
  pbInput = (PBYTE)v23;
  v22 = (char *)v23;
  v23[0] = 0;
  EnvironmentVariableW = GetEnvironmentVariableW(L"ProgramData", 0, 0);
  v3 = EnvironmentVariableW;
  if ( !EnvironmentVariableW )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError != -2147024693 )
      goto LABEL_9;
    v8 = GetEnvironmentVariableW(L"SystemDrive", 0, 0);
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( !(_DWORD)v8 )
      goto LABEL_9;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::resize(
      &lpBuffer,
      v8);
    v9 = GetEnvironmentVariableW(L"SystemDrive", lpBuffer, v8);
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( !v9 )
    {
LABEL_9:
      v6 = LastError;
      goto LABEL_22;
    }
    v30 = 0;
    v10 = *(_WORD **)utl::find<utl::_ArrayIt<unsigned short>,int>(&v31, lpBuffer, v19, &v30);
    v19 = &v11[-(v11 - v10)];
    *v10 = *v11;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
      &lpBuffer,
      v24,
      v25 - v24);
    goto LABEL_17;
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::resize(
    &lpBuffer,
    EnvironmentVariableW);
  v4 = GetEnvironmentVariableW(L"ProgramData", lpBuffer, v3);
  v5 = GetLastError();
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v4 )
  {
LABEL_17:
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
      &pbInput,
      lpBuffer,
      v19 - lpBuffer);
    v30 = 0;
    v12 = *(_WORD **)utl::find<utl::_ArrayIt<unsigned short>,int>(&v31, pbInput, v22, &v30);
    v22 = (char *)&v13[-(v13 - v12)];
    *v12 = *v13;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
      &pbInput,
      v27,
      v28 - v27);
    v14 = (v22 - (char *)pbInput) >> 1;
    if ( v14 < 0x104 )
    {
      v15 = NCryptSetProperty(hObject, L"PCP_ALTERNATE_KEY_STORAGE_LOCATION", pbInput, 2 * v14, 0);
      v6 = v15;
      if ( v15 < 0 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 1) != 0 )
        McTemplateU0zd_EventWriteTransfer(
          v16,
          EnterpriseDiagnosticsTPMFunctionFailure,
          L"NCryptSetProperty(aikStorageLocation)",
          (unsigned int)v15);
    }
    else
    {
      v6 = -2147024785;
    }
  }
LABEL_22:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&pbInput);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&lpBuffer);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v24);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&v27);
  return v6;
}

```

## disassembly

```asm
0x18008b4d0  mov     [rsp-8+arg_0], rbx
0x18008b4d5  push    rbp
0x18008b4d6  push    rsi
0x18008b4d7  push    r14
0x18008b4d9  lea     rbp, [rsp-47h]
0x18008b4de  sub     rsp, 0B0h
0x18008b4e5  lea     rax, [rbp+57h+var_20]
0x18008b4e9  mov     r14, rcx
0x18008b4ec  mov     [rbp+57h+var_30], rax
0x18008b4f0  lea     rdx, aMicrosoftCrypt; "\\Microsoft\\Crypto\\PCPKSP\\WindowsAIK"
0x18008b4f7  lea     rax, [rbp+57h+var_20]
0x18008b4fb  mov     [rbp+57h+var_28], rax
0x18008b4ff  lea     rcx, [rbp+57h+var_30]
0x18008b503  xor     eax, eax
0x18008b505  mov     [rbp+57h+var_20], ax
0x18008b509  lea     r8d, [rax+23h]
0x18008b50d  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18008b512  lea     rax, [rbp+57h+var_40]
0x18008b516  mov     [rbp+57h+var_50], rax
0x18008b51a  lea     rdx, aProgramdata; "\\ProgramData"
0x18008b521  lea     rax, [rbp+57h+var_40]
0x18008b525  mov     [rbp+57h+var_48], rax
0x18008b529  lea     rcx, [rbp+57h+var_50]
0x18008b52d  xor     eax, eax
0x18008b52f  mov     [rbp+57h+var_40], ax
0x18008b533  lea     r8d, [rax+0Ch]
0x18008b537  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18008b53c  lea     rax, [rbp+57h+var_80]
0x18008b540  xor     r8d, r8d; nSize
0x18008b543  mov     [rbp+57h+lpBuffer], rax
0x18008b547  lea     rcx, Name; "ProgramData"
0x18008b54e  lea     rax, [rbp+57h+var_80]
0x18008b552  xor     edx, edx; lpBuffer
0x18008b554  mov     [rbp+57h+var_88], rax
0x18008b558  xor     eax, eax
0x18008b55a  mov     [rbp+57h+var_80], ax
0x18008b55e  lea     rax, [rbp+57h+var_60]
0x18008b562  mov     [rbp+57h+pbInput], rax
0x18008b566  lea     rax, [rbp+57h+var_60]
0x18008b56a  mov     [rbp+57h+var_68], rax
0x18008b56e  xor     eax, eax
0x18008b570  mov     [rbp+57h+var_60], ax
0x18008b574  call    cs:__imp_GetEnvironmentVariableW
0x18008b57b  nop     dword ptr [rax+rax+00h]
0x18008b580  mov     ebx, eax
0x18008b582  test    eax, eax
0x18008b584  jz      short loc_18008B5D5
0x18008b586  mov     edx, ebx
0x18008b588  lea     rcx, [rbp+57h+lpBuffer]
0x18008b58c  call    ?resize@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_N_KG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::resize(unsigned __int64,ushort)
0x18008b591  mov     rdx, [rbp+57h+lpBuffer]; lpBuffer
0x18008b595  lea     rcx, Name; "ProgramData"
0x18008b59c  mov     r8d, ebx; nSize
0x18008b59f  call    cs:__imp_GetEnvironmentVariableW
0x18008b5a6  nop     dword ptr [rax+rax+00h]
0x18008b5ab  mov     esi, eax
0x18008b5ad  call    cs:__imp_GetLastError
0x18008b5b4  nop     dword ptr [rax+rax+00h]
0x18008b5b9  mov     ebx, eax
0x18008b5bb  test    eax, eax
0x18008b5bd  jle     short loc_18008B5C8
0x18008b5bf  movzx   ebx, ax
0x18008b5c2  or      ebx, 80070000h
0x18008b5c8  test    esi, esi
0x18008b5ca  jnz     loc_18008B6CC
0x18008b5d0  jmp     loc_18008B79A
0x18008b5d5  call    cs:__imp_GetLastError
0x18008b5dc  nop     dword ptr [rax+rax+00h]
0x18008b5e1  test    eax, eax
0x18008b5e3  jle     short loc_18008B5ED
0x18008b5e5  movzx   eax, ax
0x18008b5e8  or      eax, 80070000h
0x18008b5ed  cmp     eax, 800700CBh
0x18008b5f2  jz      short loc_18008B5FB
0x18008b5f4  mov     ebx, eax
0x18008b5f6  jmp     loc_18008B79A
0x18008b5fb  xor     r8d, r8d; nSize
0x18008b5fe  lea     rcx, aSystemdrive; "SystemDrive"
0x18008b605  xor     edx, edx; lpBuffer
0x18008b607  call    cs:__imp_GetEnvironmentVariableW
0x18008b60e  nop     dword ptr [rax+rax+00h]
0x18008b613  mov     ebx, eax
0x18008b615  call    cs:__imp_GetLastError
0x18008b61c  nop     dword ptr [rax+rax+00h]
0x18008b621  test    eax, eax
0x18008b623  jle     short loc_18008B62D
0x18008b625  movzx   eax, ax
0x18008b628  or      eax, 80070000h
0x18008b62d  test    ebx, ebx
0x18008b62f  jz      short loc_18008B5F4
0x18008b631  mov     rdx, rbx
0x18008b634  lea     rcx, [rbp+57h+lpBuffer]
0x18008b638  call    ?resize@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_N_KG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::resize(unsigned __int64,ushort)
0x18008b63d  mov     rdx, [rbp+57h+lpBuffer]; lpBuffer
0x18008b641  lea     rcx, aSystemdrive; "SystemDrive"
0x18008b648  mov     r8d, ebx; nSize
0x18008b64b  call    cs:__imp_GetEnvironmentVariableW
0x18008b652  nop     dword ptr [rax+rax+00h]
0x18008b657  mov     ebx, eax
0x18008b659  call    cs:__imp_GetLastError
0x18008b660  nop     dword ptr [rax+rax+00h]
0x18008b665  test    eax, eax
0x18008b667  jle     short loc_18008B671
0x18008b669  movzx   eax, ax
0x18008b66c  or      eax, 80070000h
0x18008b671  test    ebx, ebx
0x18008b673  jz      loc_18008B5F4
0x18008b679  mov     r8, [rbp+57h+var_88]
0x18008b67d  lea     r9, [rbp+57h+arg_8]
0x18008b681  mov     rdx, [rbp+57h+lpBuffer]
0x18008b685  lea     rcx, [rbp+57h+arg_10]
0x18008b689  mov     [rbp+57h+arg_8], 0
0x18008b690  call    ??$find@V?$_ArrayIt@G@utl@@H@utl@@YA?AV?$_ArrayIt@G@0@V10@0AEBH@Z; utl::find<utl::_ArrayIt<ushort>,int>(utl::_ArrayIt<ushort>,utl::_ArrayIt<ushort>,int const &)
0x18008b695  mov     rcx, r8
0x18008b698  mov     rdx, [rax]
0x18008b69b  mov     rax, r8
0x18008b69e  sub     rcx, rdx
0x18008b6a1  sar     rcx, 1
0x18008b6a4  add     rcx, rcx
0x18008b6a7  sub     rax, rcx
0x18008b6aa  lea     rcx, [rbp+57h+lpBuffer]
0x18008b6ae  mov     [rbp+57h+var_88], rax
0x18008b6b2  movzx   eax, word ptr [r8]
0x18008b6b6  mov     [rdx], ax
0x18008b6b9  mov     r8, [rbp+57h+var_48]
0x18008b6bd  mov     rdx, [rbp+57h+var_50]
0x18008b6c1  sub     r8, rdx
0x18008b6c4  sar     r8, 1
0x18008b6c7  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18008b6cc  mov     r8, [rbp+57h+var_88]
0x18008b6d0  lea     rcx, [rbp+57h+pbInput]
0x18008b6d4  mov     rdx, [rbp+57h+lpBuffer]
0x18008b6d8  sub     r8, rdx
0x18008b6db  sar     r8, 1
0x18008b6de  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18008b6e3  mov     r8, [rbp+57h+var_68]
0x18008b6e7  lea     r9, [rbp+57h+arg_8]
0x18008b6eb  mov     rdx, [rbp+57h+pbInput]
0x18008b6ef  lea     rcx, [rbp+57h+arg_10]
0x18008b6f3  mov     [rbp+57h+arg_8], 0
0x18008b6fa  call    ??$find@V?$_ArrayIt@G@utl@@H@utl@@YA?AV?$_ArrayIt@G@0@V10@0AEBH@Z; utl::find<utl::_ArrayIt<ushort>,int>(utl::_ArrayIt<ushort>,utl::_ArrayIt<ushort>,int const &)
0x18008b6ff  mov     rcx, r8
0x18008b702  mov     rdx, [rax]
0x18008b705  mov     rax, r8
0x18008b708  sub     rcx, rdx
0x18008b70b  sar     rcx, 1
0x18008b70e  add     rcx, rcx
0x18008b711  sub     rax, rcx
0x18008b714  lea     rcx, [rbp+57h+pbInput]
0x18008b718  mov     [rbp+57h+var_68], rax
0x18008b71c  movzx   eax, word ptr [r8]
0x18008b720  mov     [rdx], ax
0x18008b723  mov     r8, [rbp+57h+var_28]
0x18008b727  mov     rdx, [rbp+57h+var_30]
0x18008b72b  sub     r8, rdx
0x18008b72e  sar     r8, 1
0x18008b731  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18008b736  mov     r9, [rbp+57h+var_68]
0x18008b73a  mov     r8, [rbp+57h+pbInput]; pbInput
0x18008b73e  sub     r9, r8
0x18008b741  sar     r9, 1
0x18008b744  cmp     r9, 104h
0x18008b74b  jb      short loc_18008B754
0x18008b74d  mov     ebx, 8007006Fh
0x18008b752  jmp     short loc_18008B79A
0x18008b754  add     r9d, r9d; cbInput
0x18008b757  mov     [rsp+0C0h+dwFlags], 0; dwFlags
0x18008b75f  lea     rdx, aPcpAlternateKe; "PCP_ALTERNATE_KEY_STORAGE_LOCATION"
0x18008b766  mov     rcx, r14; hObject
0x18008b769  call    cs:__imp_NCryptSetProperty
0x18008b770  nop     dword ptr [rax+rax+00h]
0x18008b775  mov     ebx, eax
0x18008b777  test    eax, eax
0x18008b779  jns     short loc_18008B79A
0x18008b77b  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 1
0x18008b782  jz      short loc_18008B79A
0x18008b784  mov     r9d, eax
0x18008b787  lea     r8, aNcryptsetprope_0; "NCryptSetProperty(aikStorageLocation)"
0x18008b78e  lea     rdx, EnterpriseDiagnosticsTPMFunctionFailure
0x18008b795  call    McTemplateU0zd_EventWriteTransfer
0x18008b79a  lea     rcx, [rbp+57h+pbInput]
0x18008b79e  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18008b7a3  lea     rcx, [rbp+57h+lpBuffer]
0x18008b7a7  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18008b7ac  lea     rcx, [rbp+57h+var_50]
0x18008b7b0  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18008b7b5  lea     rcx, [rbp+57h+var_30]
0x18008b7b9  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18008b7be  mov     eax, ebx
0x18008b7c0  mov     rbx, [rsp+0C0h+arg_0]
0x18008b7c8  add     rsp, 0B0h
0x18008b7cf  pop     r14
0x18008b7d1  pop     rsi
0x18008b7d2  pop     rbp
0x18008b7d3  retn
```
