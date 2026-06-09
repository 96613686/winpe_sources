# CopyAndReregisterNonCustomApppatchSdbs(RtlArray<_SavedSdbInfo> &,ushort const *)

- ea: `0x180037c64`
- end: `0x180037eb0`
- name: `?CopyAndReregisterNonCustomApppatchSdbs@@YAJAEAV?$RtlArray@U_SavedSdbInfo@@@@PEBG@Z`
- size: `588`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800382f0`

## callees

- `0x180001cf0`
- `0x18000a51c`
- `0x180037c64`
- `0x180038200`
- `0x18003862c`
- `0x1800392b4`
- `0x1800543c0`
- `0x180060954`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180037e1f`
- `KERNEL32!GetLastError` at `0x180037e1f`
- `ADVAPI32!RegCloseKey` at `0x180037e81`
- `ADVAPI32!RegCloseKey` at `0x180037e81`
- `ADVAPI32!RegOpenKeyExW` at `0x180037d20`
- `ADVAPI32!RegOpenKeyExW` at `0x180037d20`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180037d5c`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180037d5c`

## string_xrefs

- `0x180037ccf`: `\InstalledSDB`
- `0x180037e4d`: `Failed to open installed sdb key: 0x%x`
- `0x180037dfa`: `CopyAndReregisterNonCustomApppatchSdbs`
- `0x180037e66`: `CopyAndReregisterNonCustomApppatchSdbs`

## pseudocode

```c
__int64 __fastcall CopyAndReregisterNonCustomApppatchSdbs(
        unsigned __int64 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int PersistedLocation; // eax
  signed int v7; // ebx
  HRESULT v8; // eax
  LSTATUS v9; // eax
  __int64 v10; // rdx
  unsigned __int64 v11; // rax
  unsigned __int64 i; // rdi
  unsigned __int64 v13; // rbx
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rcx
  int v16; // eax
  signed int LastError; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultb; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v23; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPath[264]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v26[264]; // [rsp+470h] [rbp+370h] BYREF

  hKey = 0;
  v23 = 0;
  PersistedLocation = Windows::Compat::Shared::Registry::GetPersistedLocation(
                        pszDest,
                        (unsigned int)a2,
                        a3,
                        a4,
                        phkResult);
  v7 = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    LODWORD(phkResulta) = PersistedLocation;
    AslLogCallPrintf(
      1,
      "CopyAndReregisterNonCustomApppatchSdbs",
      1144,
      "Failed to get persisted reg key location: 0x%x",
      phkResulta);
    goto LABEL_34;
  }
  v8 = StringCchCatW(pszDest, 0x104u, L"\\InstalledSDB");
  v7 = v8;
  if ( v8 < 0 )
  {
    LODWORD(phkResulta) = v8;
    AslLogCallPrintf(1, "CopyAndReregisterNonCustomApppatchSdbs", 1151, "Failed to concat string: 0x%x", phkResulta);
    goto LABEL_34;
  }
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0x20119u, &hKey);
  v7 = v9;
  if ( v9 )
  {
    if ( v9 > 0 )
      v7 = (unsigned __int16)v9 | 0x80070000;
  }
  else if ( hKey )
  {
    if ( (unsigned int)SdbGetPathCustomSdb(pszPath, v10, &v23) && PathRemoveFileSpecW(pszPath) )
    {
      v11 = a1[2];
      if ( v11 )
      {
        for ( i = 0; i < v11; ++i )
        {
          v13 = 0;
          if ( i < v11 )
          {
            v14 = a1[1] * i;
            if ( !is_mul_ok(a1[1], i) || (v15 = a1[5], v13 = v15 + v14, v15 + v14 < v15) )
              v13 = 0;
          }
          if ( *(_QWORD *)v13 )
          {
            if ( *(_QWORD *)(v13 + 32) )
            {
              if ( !*(_DWORD *)(v13 + 8) )
              {
                if ( *(_DWORD *)(v13 + 24) )
                {
                  if ( CopySdbToNewLocation((struct _SavedSdbInfo *)v13, a2, pszPath, v26, (unsigned __int64)phkResultb) >= 0 )
                  {
                    v16 = ReregisterSdb(hKey, *(const unsigned __int16 **)v13, v26);
                    if ( v16 < 0 )
                      AslLogCallPrintf(
                        1,
                        "CopyAndReregisterNonCustomApppatchSdbs",
                        1219,
                        "Failed to reregister sdb: 0x%x",
                        v16);
                  }
                }
              }
            }
          }
          v11 = a1[2];
        }
      }
      v7 = 0;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( v7 >= 0 )
        v7 = -2147467259;
    }
    goto LABEL_34;
  }
  if ( v7 >= 0 )
    v7 = -2147467259;
  LODWORD(phkResultb) = v7;
  AslLogCallPrintf(
    1,
    "CopyAndReregisterNonCustomApppatchSdbs",
    1163,
    "Failed to open installed sdb key: 0x%x",
    phkResultb);
LABEL_34:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180037c64  mov     [rsp-8+arg_10], rbx
0x180037c69  mov     [rsp-8+arg_18], rsi
0x180037c6e  push    rbp
0x180037c6f  push    rdi
0x180037c70  push    r14
0x180037c72  lea     rbp, [rsp-590h]
0x180037c7a  sub     rsp, 690h
0x180037c81  mov     rax, cs:__security_cookie
0x180037c88  xor     rax, rsp
0x180037c8b  mov     [rbp+5A0h+var_20], rax
0x180037c92  mov     rsi, rcx
0x180037c95  mov     [rsp+6A0h+hKey], 0
0x180037c9e  xorps   xmm0, xmm0
0x180037ca1  lea     rcx, [rsp+6A0h+pszDest]; unsigned __int16 *
0x180037ca6  movups  [rsp+6A0h+var_668], xmm0
0x180037cab  mov     r14, rdx
0x180037cae  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x180037cb3  mov     ebx, eax
0x180037cb5  test    eax, eax
0x180037cb7  jns     short loc_180037CCF
0x180037cb9  mov     dword ptr [rsp+6A0h+phkResult], eax
0x180037cbd  lea     r9, aFailedToGetPer; "Failed to get persisted reg key locatio"...
0x180037cc4  mov     r8d, 478h
0x180037cca  jmp     loc_180037E66
0x180037ccf  lea     r8, aInstalledsdb; "\\InstalledSDB"
0x180037cd6  mov     edx, 104h; cchDest
0x180037cdb  lea     rcx, [rsp+6A0h+pszDest]; pszDest
0x180037ce0  call    StringCchCatW
0x180037ce5  mov     ebx, eax
0x180037ce7  test    eax, eax
0x180037ce9  jns     short loc_180037D01
0x180037ceb  mov     dword ptr [rsp+6A0h+phkResult], eax
0x180037cef  lea     r9, aFailedToConcat; "Failed to concat string: 0x%x"
0x180037cf6  mov     r8d, 47Fh
0x180037cfc  jmp     loc_180037E66
0x180037d01  lea     rax, [rsp+6A0h+hKey]
0x180037d06  mov     r9d, 20119h; samDesired
0x180037d0c  xor     r8d, r8d; ulOptions
0x180037d0f  mov     [rsp+6A0h+phkResult], rax; unsigned __int64
0x180037d14  lea     rdx, [rsp+6A0h+pszDest]; lpSubKey
0x180037d19  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180037d20  call    cs:__imp_RegOpenKeyExW
0x180037d26  mov     ebx, eax
0x180037d28  test    eax, eax
0x180037d2a  jnz     loc_180037E40
0x180037d30  cmp     [rsp+6A0h+hKey], 0
0x180037d36  jz      loc_180037E4B
0x180037d3c  lea     r8, [rsp+6A0h+var_668]
0x180037d41  lea     rcx, [rbp+5A0h+pszPath]
0x180037d48  call    SdbGetPathCustomSdb
0x180037d4d  test    eax, eax
0x180037d4f  jz      loc_180037E1F
0x180037d55  lea     rcx, [rbp+5A0h+pszPath]; pszPath
0x180037d5c  call    cs:__imp_PathRemoveFileSpecW
0x180037d62  test    eax, eax
0x180037d64  jz      loc_180037E1F
0x180037d6a  mov     rax, [rsi+10h]
0x180037d6e  test    rax, rax
0x180037d71  jz      loc_180037E1B
0x180037d77  xor     edi, edi
0x180037d79  xor     ebx, ebx
0x180037d7b  cmp     rdi, rax
0x180037d7e  jnb     short loc_180037D9B
0x180037d80  mov     rax, rdi
0x180037d83  mul     qword ptr [rsi+8]
0x180037d87  test    rdx, rdx
0x180037d8a  jnz     short loc_180037D99
0x180037d8c  mov     rcx, [rsi+28h]
0x180037d90  lea     rbx, [rcx+rax]
0x180037d94  cmp     rbx, rcx
0x180037d97  jnb     short loc_180037D9B
0x180037d99  xor     ebx, ebx
0x180037d9b  cmp     qword ptr [rbx], 0
0x180037d9f  jz      short loc_180037E0B
0x180037da1  cmp     qword ptr [rbx+20h], 0
0x180037da6  jz      short loc_180037E0B
0x180037da8  cmp     dword ptr [rbx+8], 0
0x180037dac  jnz     short loc_180037E0B
0x180037dae  cmp     dword ptr [rbx+18h], 0
0x180037db2  jz      short loc_180037E0B
0x180037db4  lea     r9, [rbp+5A0h+var_230]; unsigned __int16 *
0x180037dbb  mov     rdx, r14; unsigned __int16 *
0x180037dbe  lea     r8, [rbp+5A0h+pszPath]; unsigned __int16 *
0x180037dc5  mov     rcx, rbx; struct _SavedSdbInfo *
0x180037dc8  call    ?CopySdbToNewLocation@@YAJPEAU_SavedSdbInfo@@PEBG1PEAG_K@Z; CopySdbToNewLocation(_SavedSdbInfo *,ushort const *,ushort const *,ushort *,unsigned __int64)
0x180037dcd  test    eax, eax
0x180037dcf  js      short loc_180037E0B
0x180037dd1  mov     rdx, [rbx]; unsigned __int16 *
0x180037dd4  lea     r8, [rbp+5A0h+var_230]; unsigned __int16 *
0x180037ddb  mov     rcx, [rsp+6A0h+hKey]; HKEY
0x180037de0  call    ?ReregisterSdb@@YAJPEAUHKEY__@@PEBG1@Z; ReregisterSdb(HKEY__ *,ushort const *,ushort const *)
0x180037de5  test    eax, eax
0x180037de7  jns     short loc_180037E0B
0x180037de9  lea     r9, aFailedToReregi_0; "Failed to reregister sdb: 0x%x"
0x180037df0  mov     dword ptr [rsp+6A0h+phkResult], eax
0x180037df4  mov     r8d, 4C3h
0x180037dfa  lea     rdx, aCopyandreregis; "CopyAndReregisterNonCustomApppatchSdbs"
0x180037e01  mov     ecx, 1
0x180037e06  call    AslLogCallPrintf
0x180037e0b  mov     rax, [rsi+10h]
0x180037e0f  inc     rdi
0x180037e12  cmp     rdi, rax
0x180037e15  jb      loc_180037D79
0x180037e1b  xor     ebx, ebx
0x180037e1d  jmp     short loc_180037E77
0x180037e1f  call    cs:__imp_GetLastError
0x180037e25  mov     ebx, eax
0x180037e27  test    eax, eax
0x180037e29  jle     short loc_180037E34
0x180037e2b  movzx   ebx, ax
0x180037e2e  or      ebx, 80070000h
0x180037e34  test    ebx, ebx
0x180037e36  mov     eax, 80004005h
0x180037e3b  cmovns  ebx, eax
0x180037e3e  jmp     short loc_180037E77
0x180037e40  jle     short loc_180037E4B
0x180037e42  movzx   ebx, ax
0x180037e45  or      ebx, 80070000h
0x180037e4b  test    ebx, ebx
0x180037e4d  lea     r9, aFailedToOpenIn_0; "Failed to open installed sdb key: 0x%x"
0x180037e54  mov     eax, 80004005h
0x180037e59  mov     r8d, 48Bh
0x180037e5f  cmovns  ebx, eax
0x180037e62  mov     dword ptr [rsp+6A0h+phkResult], ebx
0x180037e66  lea     rdx, aCopyandreregis; "CopyAndReregisterNonCustomApppatchSdbs"
0x180037e6d  mov     ecx, 1
0x180037e72  call    AslLogCallPrintf
0x180037e77  mov     rcx, [rsp+6A0h+hKey]; hKey
0x180037e7c  test    rcx, rcx
0x180037e7f  jz      short loc_180037E87
0x180037e81  call    cs:__imp_RegCloseKey
0x180037e87  mov     eax, ebx
0x180037e89  mov     rcx, [rbp+5A0h+var_20]
0x180037e90  xor     rcx, rsp; StackCookie
0x180037e93  call    __security_check_cookie
0x180037e98  lea     r11, [rsp+6A0h+var_10]
0x180037ea0  mov     rbx, [r11+30h]
0x180037ea4  mov     rsi, [r11+38h]
0x180037ea8  mov     rsp, r11
0x180037eab  pop     r14
0x180037ead  pop     rdi
0x180037eae  pop     rbp
0x180037eaf  retn
```
