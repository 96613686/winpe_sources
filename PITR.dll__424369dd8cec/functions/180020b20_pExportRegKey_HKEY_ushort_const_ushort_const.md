# pExportRegKey(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180020b20`
- end: `0x180020d8b`
- name: `?pExportRegKey@@YAJPEAUHKEY__@@PEBG1@Z`
- size: `619`
- prototype: `__int64 __fastcall(HKEY, const char *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x1800170f0`

## callees

- `0x180009e04`
- `0x180020b20`
- `0x18002125c`
- `0x18003b094`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020d65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020d65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ce7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ce7`
- `api-ms-win-core-registry-l2-1-0!RegSaveKeyW` at `0x180020cca`
- `api-ms-win-core-registry-l2-1-0!RegSaveKeyW` at `0x180020cca`
- `WDSCORE!CurrentIP` at `0x180020b7e`
- `WDSCORE!CurrentIP` at `0x180020c54`
- `WDSCORE!CurrentIP` at `0x180020cef`
- `WDSCORE!CurrentIP` at `0x180020b7e`
- `WDSCORE!CurrentIP` at `0x180020c54`
- `WDSCORE!CurrentIP` at `0x180020cef`
- `WDSCORE!WdsSetupLogMessageW` at `0x180020d55`
- `WDSCORE!WdsSetupLogMessageW` at `0x180020d55`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180020be5`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180020be5`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180020bfc`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180020bfc`
- `unbcl!?Exists@File@UnBCL@@SAHPEBVString@2@@Z` at `0x180020bef`
- `unbcl!?Exists@File@UnBCL@@SAHPEBVString@2@@Z` at `0x180020bef`

## string_xrefs

- `0x180020bc4`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180020c9a`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180020d32`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180020b8d`: `Failed to open subkey %s. Error: 0x%08X`

## pseudocode

```c
__int64 __fastcall pExportRegKey(HKEY a1, const char *a2, const unsigned __int16 *a3)
{
  HKEY v5; // rdi
  int v6; // eax
  unsigned int v7; // esi
  DWORD LastError; // edi
  __int64 v9; // rbx
  struct tagLOG_PARTIAL_MSG *v10; // rax
  const struct UnBCL::String *v11; // rax
  int v12; // ebx
  signed int v13; // eax
  bool v14; // sf
  signed int v15; // eax
  DWORD v16; // edi
  __int64 v17; // rbx
  struct tagLOG_PARTIAL_MSG *v18; // rax
  LSTATUS v19; // eax
  DWORD v20; // edi
  __int64 v21; // rbx
  struct tagLOG_PARTIAL_MSG *v22; // rax
  _BYTE v24[24]; // [rsp+60h] [rbp-58h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-40h] BYREF

  v5 = a1;
  hKey = 0;
  if ( a2 && (v6 = pOpenRegKeyMaxAccess(a1, (LPCWSTR)a2, &hKey), (v7 = v6) != 0) )
  {
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    LastError = GetLastError();
    v9 = CurrentIP();
    v10 = ConstructPartialMsgW(0x3000000u, "Failed to open subkey %s. Error: 0x%08X", a2, v7);
    WdsSetupLogMessageW(
      v10,
      0,
      L"D",
      0,
      833,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"pExportRegKey",
      v9,
      LastError,
      0,
      0);
  }
  else
  {
    v11 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v24, a3);
    v12 = UnBCL::File::Exists(v11);
    UnBCL::String::~String((UnBCL::String *)v24);
    if ( !v12 || DeleteFileEx2((__int64)a3, 0) )
    {
      v7 = 0;
      if ( hKey )
        v5 = hKey;
      v19 = RegSaveKeyW(v5, a3, 0);
      if ( v19 )
      {
        if ( v19 > 0 )
          v7 = (unsigned __int16)v19 | 0x80070000;
        else
          v7 = v19;
        v20 = GetLastError();
        v21 = CurrentIP();
        v22 = ConstructPartialMsgW(0x2000000u, "Failed to export key. Error: 0x%08X", v7);
        WdsSetupLogMessageW(
          v22,
          0,
          L"D",
          0,
          854,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"pExportRegKey",
          v21,
          v20,
          0,
          0);
      }
    }
    else
    {
      v13 = GetLastError();
      v14 = v13 < 0;
      if ( v13 > 0 )
        v14 = 1;
      if ( v14 )
      {
        v15 = GetLastError();
        v7 = v15;
        if ( v15 > 0 )
          v7 = (unsigned __int16)v15 | 0x80070000;
      }
      else
      {
        v7 = -2147467259;
      }
      v16 = GetLastError();
      v17 = CurrentIP();
      v18 = ConstructPartialMsgW(0x2000000u, "Failed to clear export file %s. Error: 0x%08X", (const char *)a3, v7);
      WdsSetupLogMessageW(
        v18,
        0,
        L"D",
        0,
        844,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"pExportRegKey",
        v17,
        v16,
        0,
        0);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x180020b20  push    rbx
0x180020b22  push    rbp
0x180020b23  push    rsi
0x180020b24  push    rdi
0x180020b25  push    r14
0x180020b27  sub     rsp, 90h
0x180020b2e  mov     rax, cs:__security_cookie
0x180020b35  xor     rax, rsp
0x180020b38  mov     [rsp+0B8h+var_38], rax
0x180020b40  mov     rbp, r8
0x180020b43  mov     r14, rdx
0x180020b46  mov     rdi, rcx
0x180020b49  mov     [rsp+0B8h+hKey], 0
0x180020b52  test    rdx, rdx
0x180020b55  jz      loc_180020BDD
0x180020b5b  lea     r8, [rsp+0B8h+hKey]; phkResult
0x180020b60  call    ?pOpenRegKeyMaxAccess@@YAKPEAUHKEY__@@PEBGPEAPEAU1@@Z; pOpenRegKeyMaxAccess(HKEY__ *,ushort const *,HKEY__ * *)
0x180020b65  mov     esi, eax
0x180020b67  test    eax, eax
0x180020b69  jz      short loc_180020BDD
0x180020b6b  jle     short loc_180020B76
0x180020b6d  movzx   esi, ax
0x180020b70  or      esi, 80070000h
0x180020b76  call    cs:__imp_GetLastError
0x180020b7c  mov     edi, eax
0x180020b7e  call    cs:__imp_CurrentIP
0x180020b84  mov     rbx, rax
0x180020b87  mov     r9d, esi
0x180020b8a  mov     r8, r14
0x180020b8d  lea     rdx, aFailedToOpenSu; "Failed to open subkey %s. Error: 0x%08X"
0x180020b94  mov     ecx, 3000000h; unsigned int
0x180020b99  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180020b9e  mov     [rsp+0B8h+var_68], 0
0x180020ba6  mov     [rsp+0B8h+var_70], 0
0x180020baf  mov     [rsp+0B8h+var_78], edi
0x180020bb3  mov     [rsp+0B8h+var_80], rbx
0x180020bb8  lea     rcx, aPexportregkey; "pExportRegKey"
0x180020bbf  mov     [rsp+0B8h+var_88], rcx
0x180020bc4  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180020bcb  mov     [rsp+0B8h+var_90], rcx
0x180020bd0  mov     [rsp+0B8h+var_98], 341h
0x180020bd8  jmp     loc_180020D46
0x180020bdd  mov     rdx, rbp
0x180020be0  lea     rcx, [rsp+0B8h+var_58]
0x180020be5  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180020beb  nop
0x180020bec  mov     rcx, rax
0x180020bef  call    cs:__imp_?Exists@File@UnBCL@@SAHPEBVString@2@@Z; UnBCL::File::Exists(UnBCL::String const *)
0x180020bf5  mov     ebx, eax
0x180020bf7  lea     rcx, [rsp+0B8h+var_58]
0x180020bfc  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180020c02  test    ebx, ebx
0x180020c04  jz      loc_180020CB3
0x180020c0a  xor     edx, edx
0x180020c0c  mov     rcx, rbp
0x180020c0f  call    DeleteFileEx2
0x180020c14  test    eax, eax
0x180020c16  jnz     loc_180020CB3
0x180020c1c  call    cs:__imp_GetLastError
0x180020c22  mov     ebx, 80070000h
0x180020c27  test    eax, eax
0x180020c29  jle     short loc_180020C32
0x180020c2b  movzx   eax, ax
0x180020c2e  or      eax, ebx
0x180020c30  test    eax, eax
0x180020c32  jns     short loc_180020C47
0x180020c34  call    cs:__imp_GetLastError
0x180020c3a  mov     esi, eax
0x180020c3c  test    eax, eax
0x180020c3e  jle     short loc_180020C4C
0x180020c40  movzx   esi, ax
0x180020c43  or      esi, ebx
0x180020c45  jmp     short loc_180020C4C
0x180020c47  mov     esi, 80004005h
0x180020c4c  call    cs:__imp_GetLastError
0x180020c52  mov     edi, eax
0x180020c54  call    cs:__imp_CurrentIP
0x180020c5a  mov     rbx, rax
0x180020c5d  mov     r9d, esi
0x180020c60  mov     r8, rbp
0x180020c63  lea     rdx, aFailedToClearE; "Failed to clear export file %s. Error: "...
0x180020c6a  mov     ecx, 2000000h; unsigned int
0x180020c6f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180020c74  mov     [rsp+0B8h+var_68], 0
0x180020c7c  mov     [rsp+0B8h+var_70], 0
0x180020c85  mov     [rsp+0B8h+var_78], edi
0x180020c89  mov     [rsp+0B8h+var_80], rbx
0x180020c8e  lea     rcx, aPexportregkey; "pExportRegKey"
0x180020c95  mov     [rsp+0B8h+var_88], rcx
0x180020c9a  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180020ca1  mov     [rsp+0B8h+var_90], rcx
0x180020ca6  mov     [rsp+0B8h+var_98], 34Ch
0x180020cae  jmp     loc_180020D46
0x180020cb3  xor     esi, esi
0x180020cb5  mov     rax, [rsp+0B8h+hKey]
0x180020cba  test    rax, rax
0x180020cbd  cmovnz  rdi, rax
0x180020cc1  xor     r8d, r8d; lpSecurityAttributes
0x180020cc4  mov     rdx, rbp; lpFile
0x180020cc7  mov     rcx, rdi; hKey
0x180020cca  call    cs:__imp_RegSaveKeyW
0x180020cd0  test    eax, eax
0x180020cd2  jz      loc_180020D5B
0x180020cd8  jg      short loc_180020CDE
0x180020cda  mov     esi, eax
0x180020cdc  jmp     short loc_180020CE7
0x180020cde  movzx   esi, ax
0x180020ce1  or      esi, 80070000h
0x180020ce7  call    cs:__imp_GetLastError
0x180020ced  mov     edi, eax
0x180020cef  call    cs:__imp_CurrentIP
0x180020cf5  mov     rbx, rax
0x180020cf8  mov     r8d, esi
0x180020cfb  lea     rdx, aFailedToExport_2; "Failed to export key. Error: 0x%08X"
0x180020d02  mov     ecx, 2000000h; unsigned int
0x180020d07  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180020d0c  mov     [rsp+0B8h+var_68], 0
0x180020d14  mov     [rsp+0B8h+var_70], 0
0x180020d1d  mov     [rsp+0B8h+var_78], edi
0x180020d21  mov     [rsp+0B8h+var_80], rbx
0x180020d26  lea     rcx, aPexportregkey; "pExportRegKey"
0x180020d2d  mov     [rsp+0B8h+var_88], rcx
0x180020d32  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180020d39  mov     [rsp+0B8h+var_90], rcx
0x180020d3e  mov     [rsp+0B8h+var_98], 356h
0x180020d46  xor     r9d, r9d
0x180020d49  lea     r8, aD; "D"
0x180020d50  xor     edx, edx
0x180020d52  mov     rcx, rax
0x180020d55  call    cs:__imp_WdsSetupLogMessageW
0x180020d5b  mov     rcx, [rsp+0B8h+hKey]; hKey
0x180020d60  test    rcx, rcx
0x180020d63  jz      short loc_180020D6B
0x180020d65  call    cs:__imp_RegCloseKey
0x180020d6b  mov     eax, esi
0x180020d6d  mov     rcx, [rsp+0B8h+var_38]
0x180020d75  xor     rcx, rsp; StackCookie
0x180020d78  call    __security_check_cookie
0x180020d7d  add     rsp, 90h
0x180020d84  pop     r14
0x180020d86  pop     rdi
0x180020d87  pop     rsi
0x180020d88  pop     rbp
0x180020d89  pop     rbx
0x180020d8a  retn
```
