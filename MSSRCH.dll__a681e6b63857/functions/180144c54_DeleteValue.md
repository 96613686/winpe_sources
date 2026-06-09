# _DeleteValue

- ea: `0x180144c54`
- end: `0x180144ddf`
- name: `_DeleteValue`
- size: `395`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180143f8c`

## callees

- `0x180119140`
- `0x180144c54`
- `0x18014519c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144cd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144d60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144cd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144d60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180144cb6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180144cb6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180144ca6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180144ca6`
- `WDSCORE!CurrentIP` at `0x180144cd8`
- `WDSCORE!CurrentIP` at `0x180144d68`
- `WDSCORE!CurrentIP` at `0x180144cd8`
- `WDSCORE!CurrentIP` at `0x180144d68`
- `WDSCORE!WdsSetupLogMessageW` at `0x180144d50`
- `WDSCORE!WdsSetupLogMessageW` at `0x180144d50`

## string_xrefs

- `0x180144d2a`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x180144db2`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x180144d0c`: `_DeleteValue`
- `0x180144d94`: `_DeleteValue`
- `0x180144d78`: `MSS: _DeleteValue call failed to open reg key %ls - error 0x%X.`
- `0x180144cf5`: `MSS: _DeleteValue call failed to delete reg value %ls under reg key %ls- error 0x%X.`

## pseudocode

```c
__int64 DeleteValue()
{
  unsigned int v0; // eax
  unsigned int v1; // esi
  DWORD v2; // edi
  __int64 v3; // rbx
  struct tagLOG_PARTIAL_MSG *v4; // rax
  DWORD LastError; // edi
  __int64 v6; // rbx
  struct tagLOG_PARTIAL_MSG *v7; // rax
  HKEY hKey; // [rsp+80h] [rbp+18h] BYREF

  hKey = 0;
  v0 = OpenKeyForBackupRestore(-2147483646, L"SOFTWARE\\Microsoft\\Windows Search", 2, &hKey);
  v1 = v0;
  if ( v0 )
  {
    if ( v0 - 2 > 1 )
    {
      LastError = GetLastError();
      v6 = CurrentIP();
      v7 = ConstructPartialMsgW(
             0x2000000u,
             "MSS: _DeleteValue call failed to open reg key %ls - error 0x%X.",
             L"SOFTWARE\\Microsoft\\Windows Search",
             v1);
      WdsSetupLogMessageW(
        v7,
        983040,
        L"D",
        0,
        126,
        L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
        L"_DeleteValue",
        v6,
        LastError,
        0,
        0);
      return v1;
    }
    return 0;
  }
  v1 = RegDeleteValueW(hKey, L"SystemIndexNormalization");
  RegCloseKey(hKey);
  if ( v1 - 2 <= 1 )
    return 0;
  if ( v1 )
  {
    v2 = GetLastError();
    v3 = CurrentIP();
    v4 = ConstructPartialMsgW(
           0x2000000u,
           "MSS: _DeleteValue call failed to delete reg value %ls under reg key %ls- error 0x%X.",
           L"SystemIndexNormalization",
           L"SOFTWARE\\Microsoft\\Windows Search",
           v1);
    WdsSetupLogMessageW(
      v4,
      983040,
      L"D",
      0,
      118,
      L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
      L"_DeleteValue",
      v3,
      v2,
      0,
      0);
  }
  return v1;
}

```

## disassembly

```asm
0x180144c54  mov     rax, rsp
0x180144c57  mov     [rax+8], rbx
0x180144c5b  mov     [rax+10h], rsi
0x180144c5f  mov     [rax+18h], r8
0x180144c63  push    rdi
0x180144c64  sub     rsp, 60h
0x180144c68  lea     r9, [rax+18h]
0x180144c6c  mov     qword ptr [rax+18h], 0
0x180144c74  mov     r8d, 2
0x180144c7a  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows Search"
0x180144c81  mov     rcx, 0FFFFFFFF80000002h
0x180144c88  call    _OpenKeyForBackupRestore
0x180144c8d  mov     esi, eax
0x180144c8f  test    eax, eax
0x180144c91  jnz     loc_180144D58
0x180144c97  mov     rcx, [rsp+68h+hKey]; hKey
0x180144c9f  lea     rdx, aSystemindexnor; "SystemIndexNormalization"
0x180144ca6  call    cs:__imp_RegDeleteValueW
0x180144cac  mov     rcx, [rsp+68h+hKey]; hKey
0x180144cb4  mov     esi, eax
0x180144cb6  call    cs:__imp_RegCloseKey
0x180144cbc  lea     eax, [rsi-2]
0x180144cbf  cmp     eax, 1
0x180144cc2  jbe     loc_180144DCB
0x180144cc8  test    esi, esi
0x180144cca  jz      loc_180144DCD
0x180144cd0  call    cs:__imp_GetLastError
0x180144cd6  mov     edi, eax
0x180144cd8  call    cs:__imp_CurrentIP
0x180144cde  lea     r9, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows Search"
0x180144ce5  mov     [rsp+68h+var_48], esi
0x180144ce9  lea     r8, aSystemindexnor; "SystemIndexNormalization"
0x180144cf0  mov     ecx, 2000000h; unsigned int
0x180144cf5  lea     rdx, aMssDeletevalue_0; "MSS: _DeleteValue call failed to delete"...
0x180144cfc  mov     rbx, rax
0x180144cff  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180144d04  mov     [rsp+68h+var_18], 0
0x180144d0c  lea     rcx, aDeletevalue; "_DeleteValue"
0x180144d13  mov     [rsp+68h+var_20], 0
0x180144d1c  mov     [rsp+68h+var_28], edi
0x180144d20  mov     [rsp+68h+var_30], rbx
0x180144d25  mov     [rsp+68h+var_38], rcx
0x180144d2a  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180144d31  mov     [rsp+68h+var_40], rcx
0x180144d36  mov     [rsp+68h+var_48], 76h ; 'v'
0x180144d3e  xor     r9d, r9d
0x180144d41  lea     r8, aD_2; "D"
0x180144d48  mov     edx, 0F0000h
0x180144d4d  mov     rcx, rax
0x180144d50  call    cs:__imp_WdsSetupLogMessageW
0x180144d56  jmp     short loc_180144DCD
0x180144d58  add     eax, 0FFFFFFFEh
0x180144d5b  cmp     eax, 1
0x180144d5e  jbe     short loc_180144DCB
0x180144d60  call    cs:__imp_GetLastError
0x180144d66  mov     edi, eax
0x180144d68  call    cs:__imp_CurrentIP
0x180144d6e  mov     r9d, esi
0x180144d71  lea     r8, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows Search"
0x180144d78  lea     rdx, aMssDeletevalue; "MSS: _DeleteValue call failed to open r"...
0x180144d7f  mov     ecx, 2000000h; unsigned int
0x180144d84  mov     rbx, rax
0x180144d87  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180144d8c  mov     [rsp+68h+var_18], 0
0x180144d94  lea     rcx, aDeletevalue; "_DeleteValue"
0x180144d9b  mov     [rsp+68h+var_20], 0
0x180144da4  mov     [rsp+68h+var_28], edi
0x180144da8  mov     [rsp+68h+var_30], rbx
0x180144dad  mov     [rsp+68h+var_38], rcx
0x180144db2  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180144db9  mov     [rsp+68h+var_40], rcx
0x180144dbe  mov     [rsp+68h+var_48], 7Eh ; '~'
0x180144dc6  jmp     loc_180144D3E
0x180144dcb  xor     esi, esi
0x180144dcd  mov     rbx, [rsp+68h+arg_0]
0x180144dd2  mov     eax, esi
0x180144dd4  mov     rsi, [rsp+68h+arg_8]
0x180144dd9  add     rsp, 60h
0x180144ddd  pop     rdi
0x180144dde  retn
```
