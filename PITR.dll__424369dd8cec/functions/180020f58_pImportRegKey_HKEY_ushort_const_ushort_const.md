# pImportRegKey(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180020f58`
- end: `0x180021138`
- name: `?pImportRegKey@@YAJPEAUHKEY__@@PEBG1@Z`
- size: `480`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpFile)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800170f0`

## callees

- `0x180009e04`
- `0x180020f58`
- `0x18002125c`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegRestoreKeyW` at `0x180021078`
- `api-ms-win-core-registry-l1-1-0!RegRestoreKeyW` at `0x180021078`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021113`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021113`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020fe0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020fe0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ff9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021095`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ff9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021095`
- `WDSCORE!CurrentIP` at `0x180021001`
- `WDSCORE!CurrentIP` at `0x18002109d`
- `WDSCORE!CurrentIP` at `0x180021001`
- `WDSCORE!CurrentIP` at `0x18002109d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180021103`
- `WDSCORE!WdsSetupLogMessageW` at `0x180021103`

## string_xrefs

- `0x180021047`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x1800210e0`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18002100a`: `Failed to open/create subkey %s. Error: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall pImportRegKey(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpFile)
{
  HKEY v3; // rax
  HKEY v6; // rbx
  unsigned int v7; // eax
  int v8; // esi
  DWORD LastError; // edi
  __int64 v10; // rbx
  struct tagLOG_PARTIAL_MSG *v11; // rax
  LSTATUS v12; // eax
  DWORD v13; // edi
  __int64 v14; // rbx
  struct tagLOG_PARTIAL_MSG *v15; // rax
  HKEY hKeya; // [rsp+60h] [rbp-28h] BYREF

  v3 = 0;
  hKeya = 0;
  v6 = hKey;
  if ( lpSubKey )
  {
    v7 = pOpenRegKeyMaxAccess(hKey, lpSubKey, &hKeya);
    v8 = v7;
    if ( v7 )
    {
      if ( v7 - 2 > 1 || (v8 = RegCreateKeyExW(v6, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKeya, 0)) != 0 )
      {
        if ( v8 > 0 )
          v8 = (unsigned __int16)v8 | 0x80070000;
        LastError = GetLastError();
        v10 = CurrentIP();
        v11 = ConstructPartialMsgW(
                0x2000000,
                "Failed to open/create subkey %s. Error: 0x%08X",
                (const char *)lpSubKey,
                v8);
        WdsSetupLogMessageW(
          v11,
          0,
          L"D",
          0,
          911,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"pImportRegKey",
          v10,
          LastError,
          0,
          0);
        goto LABEL_16;
      }
    }
    v3 = hKeya;
  }
  v8 = 0;
  if ( v3 )
    v6 = v3;
  v12 = RegRestoreKeyW(v6, lpFile, 8u);
  if ( v12 )
  {
    if ( v12 > 0 )
      v8 = (unsigned __int16)v12 | 0x80070000;
    else
      v8 = v12;
    v13 = GetLastError();
    v14 = CurrentIP();
    v15 = ConstructPartialMsgW(0x2000000, "Failed to import key. Error: 0x%08X", v8);
    WdsSetupLogMessageW(
      v15,
      0,
      L"D",
      0,
      921,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"pImportRegKey",
      v14,
      v13,
      0,
      0);
  }
LABEL_16:
  if ( hKeya )
    RegCloseKey(hKeya);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180020f58  mov     [rsp+arg_18], rbx
0x180020f5d  push    rbp
0x180020f5e  push    rsi
0x180020f5f  push    rdi
0x180020f60  sub     rsp, 70h
0x180020f64  mov     rax, cs:__security_cookie
0x180020f6b  xor     rax, rsp
0x180020f6e  mov     [rsp+88h+var_20], rax
0x180020f73  xor     eax, eax
0x180020f75  mov     rdi, r8
0x180020f78  mov     [rsp+88h+hKey], rax
0x180020f7d  mov     rbp, rdx
0x180020f80  mov     rbx, rcx
0x180020f83  test    rdx, rdx
0x180020f86  jz      loc_180021065
0x180020f8c  lea     r8, [rsp+88h+hKey]; phkResult
0x180020f91  call    ?pOpenRegKeyMaxAccess@@YAKPEAUHKEY__@@PEBGPEAPEAU1@@Z; pOpenRegKeyMaxAccess(HKEY__ *,ushort const *,HKEY__ * *)
0x180020f96  mov     esi, eax
0x180020f98  test    eax, eax
0x180020f9a  jz      loc_180021060
0x180020fa0  add     eax, 0FFFFFFFEh
0x180020fa3  cmp     eax, 1
0x180020fa6  ja      short loc_180020FEC
0x180020fa8  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x180020fb1  lea     rax, [rsp+88h+hKey]
0x180020fb6  mov     [rsp+88h+phkResult], rax; phkResult
0x180020fbb  xor     r9d, r9d; lpClass
0x180020fbe  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180020fc7  xor     r8d, r8d; Reserved
0x180020fca  mov     [rsp+88h+samDesired], 0F003Fh; samDesired
0x180020fd2  mov     rdx, rbp; lpSubKey
0x180020fd5  mov     rcx, rbx; hKey
0x180020fd8  mov     [rsp+88h+dwOptions], 0; dwOptions
0x180020fe0  call    cs:__imp_RegCreateKeyExW
0x180020fe6  mov     esi, eax
0x180020fe8  test    eax, eax
0x180020fea  jz      short loc_180021060
0x180020fec  test    esi, esi
0x180020fee  jle     short loc_180020FF9
0x180020ff0  movzx   esi, si
0x180020ff3  or      esi, 80070000h
0x180020ff9  call    cs:__imp_GetLastError
0x180020fff  mov     edi, eax
0x180021001  call    cs:__imp_CurrentIP
0x180021007  mov     r9d, esi
0x18002100a  lea     rdx, aFailedToOpenCr_0; "Failed to open/create subkey %s. Error:"...
0x180021011  mov     r8, rbp
0x180021014  mov     ecx, 2000000h; unsigned int
0x180021019  mov     rbx, rax
0x18002101c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180021021  mov     [rsp+88h+var_38], 0
0x180021029  lea     rcx, aPimportregkey; "pImportRegKey"
0x180021030  mov     [rsp+88h+var_40], 0
0x180021039  mov     dword ptr [rsp+88h+lpdwDisposition], edi
0x18002103d  mov     [rsp+88h+phkResult], rbx
0x180021042  mov     [rsp+88h+lpSecurityAttributes], rcx
0x180021047  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18002104e  mov     qword ptr [rsp+88h+samDesired], rcx
0x180021053  mov     [rsp+88h+dwOptions], 38Fh
0x18002105b  jmp     loc_1800210F4
0x180021060  mov     rax, [rsp+88h+hKey]
0x180021065  xor     esi, esi
0x180021067  mov     rdx, rdi; lpFile
0x18002106a  test    rax, rax
0x18002106d  cmovnz  rbx, rax
0x180021071  mov     rcx, rbx; hKey
0x180021074  lea     r8d, [rsi+8]; dwFlags
0x180021078  call    cs:__imp_RegRestoreKeyW
0x18002107e  test    eax, eax
0x180021080  jz      loc_180021109
0x180021086  jg      short loc_18002108C
0x180021088  mov     esi, eax
0x18002108a  jmp     short loc_180021095
0x18002108c  movzx   esi, ax
0x18002108f  or      esi, 80070000h
0x180021095  call    cs:__imp_GetLastError
0x18002109b  mov     edi, eax
0x18002109d  call    cs:__imp_CurrentIP
0x1800210a3  mov     r8d, esi
0x1800210a6  lea     rdx, aFailedToImport; "Failed to import key. Error: 0x%08X"
0x1800210ad  mov     ecx, 2000000h; unsigned int
0x1800210b2  mov     rbx, rax
0x1800210b5  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800210ba  mov     [rsp+88h+var_38], 0
0x1800210c2  lea     rcx, aPimportregkey; "pImportRegKey"
0x1800210c9  mov     [rsp+88h+var_40], 0
0x1800210d2  mov     dword ptr [rsp+88h+lpdwDisposition], edi
0x1800210d6  mov     [rsp+88h+phkResult], rbx
0x1800210db  mov     [rsp+88h+lpSecurityAttributes], rcx
0x1800210e0  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x1800210e7  mov     qword ptr [rsp+88h+samDesired], rcx
0x1800210ec  mov     [rsp+88h+dwOptions], 399h
0x1800210f4  xor     r9d, r9d
0x1800210f7  lea     r8, aD; "D"
0x1800210fe  xor     edx, edx
0x180021100  mov     rcx, rax
0x180021103  call    cs:__imp_WdsSetupLogMessageW
0x180021109  mov     rcx, [rsp+88h+hKey]; hKey
0x18002110e  test    rcx, rcx
0x180021111  jz      short loc_180021119
0x180021113  call    cs:__imp_RegCloseKey
0x180021119  mov     eax, esi
0x18002111b  mov     rcx, [rsp+88h+var_20]
0x180021120  xor     rcx, rsp; StackCookie
0x180021123  call    __security_check_cookie
0x180021128  mov     rbx, [rsp+88h+arg_18]
0x180021130  add     rsp, 70h
0x180021134  pop     rdi
0x180021135  pop     rsi
0x180021136  pop     rbp
0x180021137  retn
```
