# GetSecureBootUpdateFilePath(ushort const *,ushort *,ulong,SBServiceUpdateCaller::Source)

- ea: `0x180036a98`
- end: `0x180036cdc`
- name: `?GetSecureBootUpdateFilePath@@YAJPEBGPEAGKW4Source@SBServiceUpdateCaller@@@Z`
- size: `580`
- prototype: `int __fastcall(const WCHAR *, unsigned __int16 *, __int64, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002f340`
- `0x180034634`
- `0x180037050`

## callees

- `0x18001bddc`
- `0x180036a98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036c98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036c98`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180036c8c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180036c8c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036ab9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036ada`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036afb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036b1c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036b3d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036b5e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036b7f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036ba0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036bc1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036be2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036c00`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036c1e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036c3c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036c5a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036ab9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036ada`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036afb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036b1c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036b3d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036b5e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036b7f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036ba0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036bc1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036be2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036c00`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036c1e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036c3c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180036c5a`

## string_xrefs

- `0x180036ab2`: `DBUpdate.bin`
- `0x180036ac4`: `DBUpdate.bin`
- `0x180036ad0`: `DBXUpdate.bin`
- `0x180036ae5`: `DBXUpdate.bin`
- `0x180036af1`: `DBUpdate2024.bin`
- `0x180036b06`: `DBUpdate2024.bin`
- `0x180036b12`: `DBXUpdate2024.bin`
- `0x180036b27`: `DBXUpdate2024.bin`
- `0x180036b33`: `DBXUpdateSVN.bin`
- `0x180036b48`: `DBXUpdateSVN.bin`
- `0x180036b96`: `KEKUpdateCombined.bin`
- `0x180036bab`: `KEKUpdateCombined.bin`
- `0x180036bb7`: `DBUpdateOROM2023.bin`
- `0x180036bcc`: `DBUpdateOROM2023.bin`
- `0x180036bd8`: `DBUpdate3P2023.bin`
- `0x180036bed`: `DBUpdate3P2023.bin`
- `0x180036bf6`: `DBXUpdateLegacy.bin`
- `0x180036c0b`: `DBXUpdateLegacy.bin`
- `0x180036c14`: `DBXUpdateSVNLegacy.bin`
- `0x180036c29`: `DBXUpdateSVNLegacy.bin`
- `0x180036c32`: `DBXUpdate2024Legacy.bin`
- `0x180036c47`: `DBXUpdate2024Legacy.bin`

## pseudocode

```c
int __fastcall GetSecureBootUpdateFilePath(const WCHAR *a1, unsigned __int16 *a2, __int64 a3, int a4)
{
  const unsigned __int16 *v6; // r8
  int result; // eax
  UINT SystemDirectoryW; // eax
  signed int LastError; // eax
  signed int v10; // ecx

  if ( a4 == 3 )
  {
    if ( StrStrIW(a1, L"DBUpdate.bin") )
    {
      v6 = L"DBUpdate.bin";
      return StringCchCopyW(a2, 0x104u, v6);
    }
    if ( StrStrIW(a1, L"DBXUpdate.bin") )
    {
      v6 = L"DBXUpdate.bin";
      return StringCchCopyW(a2, 0x104u, v6);
    }
    if ( StrStrIW(a1, L"DBUpdate2024.bin") )
    {
      v6 = L"DBUpdate2024.bin";
      return StringCchCopyW(a2, 0x104u, v6);
    }
    if ( StrStrIW(a1, L"DBXUpdate2024.bin") )
    {
      v6 = L"DBXUpdate2024.bin";
      return StringCchCopyW(a2, 0x104u, v6);
    }
    if ( StrStrIW(a1, L"DBXUpdateSVN.bin") )
    {
      v6 = L"DBXUpdateSVN.bin";
      return StringCchCopyW(a2, 0x104u, v6);
    }
    if ( StrStrIW(a1, L"SkuSiPolicy.p7b") )
    {
      v6 = L"SkuSiPolicy.p7b";
      return StringCchCopyW(a2, 0x104u, v6);
    }
    if ( StrStrIW(a1, L"SbatLevel.txt") )
    {
      v6 = L"SbatLevel.txt";
      return StringCchCopyW(a2, 0x104u, v6);
    }
    if ( StrStrIW(a1, L"KEKUpdateCombined.bin") )
    {
      v6 = L"KEKUpdateCombined.bin";
      return StringCchCopyW(a2, 0x104u, v6);
    }
    if ( StrStrIW(a1, L"DBUpdateOROM2023.bin") )
    {
      v6 = L"DBUpdateOROM2023.bin";
      return StringCchCopyW(a2, 0x104u, v6);
    }
    if ( StrStrIW(a1, L"DBUpdate3P2023.bin") )
    {
      v6 = L"DBUpdate3P2023.bin";
      return StringCchCopyW(a2, 0x104u, v6);
    }
    if ( StrStrIW(a1, L"DBXUpdateLegacy.bin") )
    {
      v6 = L"DBXUpdateLegacy.bin";
      return StringCchCopyW(a2, 0x104u, v6);
    }
    if ( StrStrIW(a1, L"DBXUpdateSVNLegacy.bin") )
    {
      v6 = L"DBXUpdateSVNLegacy.bin";
      return StringCchCopyW(a2, 0x104u, v6);
    }
    if ( StrStrIW(a1, L"DBXUpdate2024Legacy.bin") )
    {
      v6 = L"DBXUpdate2024Legacy.bin";
      return StringCchCopyW(a2, 0x104u, v6);
    }
    if ( StrStrIW(a1, L"BucketConfidenceData.cab") )
    {
      v6 = L"BucketConfidenceData.cab";
      return StringCchCopyW(a2, 0x104u, v6);
    }
    return -2147418113;
  }
  else
  {
    SystemDirectoryW = GetSystemDirectoryW(a2, 0x104u);
    if ( SystemDirectoryW )
    {
      result = StringCchCopyW(&a2[SystemDirectoryW], 260 - SystemDirectoryW, a1);
      if ( result >= 0 )
        return 0;
    }
    else
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      if ( v10 >= 0 )
        return -2147418113;
      return v10;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180036a98  push    rbx
0x180036a9a  push    rsi
0x180036a9b  push    rdi
0x180036a9c  push    r14
0x180036a9e  sub     rsp, 28h
0x180036aa2  mov     r14, rdx
0x180036aa5  mov     rsi, rcx
0x180036aa8  cmp     r9d, 3
0x180036aac  jnz     loc_180036C82
0x180036ab2  lea     rdx, aDbupdateBin; "DBUpdate.bin"
0x180036ab9  call    cs:__imp_StrStrIW
0x180036abf  test    rax, rax
0x180036ac2  jz      short loc_180036AD0
0x180036ac4  lea     r8, aDbupdateBin; "DBUpdate.bin"
0x180036acb  jmp     loc_180036C6C
0x180036ad0  lea     rdx, aDbxupdateBin; "DBXUpdate.bin"
0x180036ad7  mov     rcx, rsi; pszFirst
0x180036ada  call    cs:__imp_StrStrIW
0x180036ae0  test    rax, rax
0x180036ae3  jz      short loc_180036AF1
0x180036ae5  lea     r8, aDbxupdateBin; "DBXUpdate.bin"
0x180036aec  jmp     loc_180036C6C
0x180036af1  lea     rdx, aDbupdate2024Bi; "DBUpdate2024.bin"
0x180036af8  mov     rcx, rsi; pszFirst
0x180036afb  call    cs:__imp_StrStrIW
0x180036b01  test    rax, rax
0x180036b04  jz      short loc_180036B12
0x180036b06  lea     r8, aDbupdate2024Bi; "DBUpdate2024.bin"
0x180036b0d  jmp     loc_180036C6C
0x180036b12  lea     rdx, aDbxupdate2024B; "DBXUpdate2024.bin"
0x180036b19  mov     rcx, rsi; pszFirst
0x180036b1c  call    cs:__imp_StrStrIW
0x180036b22  test    rax, rax
0x180036b25  jz      short loc_180036B33
0x180036b27  lea     r8, aDbxupdate2024B; "DBXUpdate2024.bin"
0x180036b2e  jmp     loc_180036C6C
0x180036b33  lea     rdx, aDbxupdatesvnBi; "DBXUpdateSVN.bin"
0x180036b3a  mov     rcx, rsi; pszFirst
0x180036b3d  call    cs:__imp_StrStrIW
0x180036b43  test    rax, rax
0x180036b46  jz      short loc_180036B54
0x180036b48  lea     r8, aDbxupdatesvnBi; "DBXUpdateSVN.bin"
0x180036b4f  jmp     loc_180036C6C
0x180036b54  lea     rdx, aSkusipolicyP7b_0; "SkuSiPolicy.p7b"
0x180036b5b  mov     rcx, rsi; pszFirst
0x180036b5e  call    cs:__imp_StrStrIW
0x180036b64  test    rax, rax
0x180036b67  jz      short loc_180036B75
0x180036b69  lea     r8, aSkusipolicyP7b_0; "SkuSiPolicy.p7b"
0x180036b70  jmp     loc_180036C6C
0x180036b75  lea     rdx, aSbatlevelTxt; "SbatLevel.txt"
0x180036b7c  mov     rcx, rsi; pszFirst
0x180036b7f  call    cs:__imp_StrStrIW
0x180036b85  test    rax, rax
0x180036b88  jz      short loc_180036B96
0x180036b8a  lea     r8, aSbatlevelTxt; "SbatLevel.txt"
0x180036b91  jmp     loc_180036C6C
0x180036b96  lea     rdx, aKekupdatecombi; "KEKUpdateCombined.bin"
0x180036b9d  mov     rcx, rsi; pszFirst
0x180036ba0  call    cs:__imp_StrStrIW
0x180036ba6  test    rax, rax
0x180036ba9  jz      short loc_180036BB7
0x180036bab  lea     r8, aKekupdatecombi; "KEKUpdateCombined.bin"
0x180036bb2  jmp     loc_180036C6C
0x180036bb7  lea     rdx, aDbupdateorom20; "DBUpdateOROM2023.bin"
0x180036bbe  mov     rcx, rsi; pszFirst
0x180036bc1  call    cs:__imp_StrStrIW
0x180036bc7  test    rax, rax
0x180036bca  jz      short loc_180036BD8
0x180036bcc  lea     r8, aDbupdateorom20; "DBUpdateOROM2023.bin"
0x180036bd3  jmp     loc_180036C6C
0x180036bd8  lea     rdx, aDbupdate3p2023; "DBUpdate3P2023.bin"
0x180036bdf  mov     rcx, rsi; pszFirst
0x180036be2  call    cs:__imp_StrStrIW
0x180036be8  test    rax, rax
0x180036beb  jz      short loc_180036BF6
0x180036bed  lea     r8, aDbupdate3p2023; "DBUpdate3P2023.bin"
0x180036bf4  jmp     short loc_180036C6C
0x180036bf6  lea     rdx, aDbxupdatelegac; "DBXUpdateLegacy.bin"
0x180036bfd  mov     rcx, rsi; pszFirst
0x180036c00  call    cs:__imp_StrStrIW
0x180036c06  test    rax, rax
0x180036c09  jz      short loc_180036C14
0x180036c0b  lea     r8, aDbxupdatelegac; "DBXUpdateLegacy.bin"
0x180036c12  jmp     short loc_180036C6C
0x180036c14  lea     rdx, aDbxupdatesvnle; "DBXUpdateSVNLegacy.bin"
0x180036c1b  mov     rcx, rsi; pszFirst
0x180036c1e  call    cs:__imp_StrStrIW
0x180036c24  test    rax, rax
0x180036c27  jz      short loc_180036C32
0x180036c29  lea     r8, aDbxupdatesvnle; "DBXUpdateSVNLegacy.bin"
0x180036c30  jmp     short loc_180036C6C
0x180036c32  lea     rdx, aDbxupdate2024l; "DBXUpdate2024Legacy.bin"
0x180036c39  mov     rcx, rsi; pszFirst
0x180036c3c  call    cs:__imp_StrStrIW
0x180036c42  test    rax, rax
0x180036c45  jz      short loc_180036C50
0x180036c47  lea     r8, aDbxupdate2024l; "DBXUpdate2024Legacy.bin"
0x180036c4e  jmp     short loc_180036C6C
0x180036c50  lea     rdx, aBucketconfiden_0; "BucketConfidenceData.cab"
0x180036c57  mov     rcx, rsi; pszFirst
0x180036c5a  call    cs:__imp_StrStrIW
0x180036c60  test    rax, rax
0x180036c63  jz      short loc_180036C7B
0x180036c65  lea     r8, aBucketconfiden_0; "BucketConfidenceData.cab"
0x180036c6c  mov     edx, 104h; unsigned __int64
0x180036c71  mov     rcx, r14; unsigned __int16 *
0x180036c74  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180036c79  jmp     short loc_180036CD2
0x180036c7b  mov     eax, 8000FFFFh
0x180036c80  jmp     short loc_180036CD2
0x180036c82  mov     ebx, 104h
0x180036c87  mov     rcx, r14; lpBuffer
0x180036c8a  mov     edx, ebx; uSize
0x180036c8c  call    cs:__imp_GetSystemDirectoryW
0x180036c92  xor     edi, edi
0x180036c94  test    eax, eax
0x180036c96  jnz     short loc_180036CBB
0x180036c98  call    cs:__imp_GetLastError
0x180036c9e  mov     ecx, eax
0x180036ca0  test    eax, eax
0x180036ca2  jle     short loc_180036CAD
0x180036ca4  movzx   ecx, ax
0x180036ca7  or      ecx, 80070000h
0x180036cad  mov     eax, 8000FFFFh
0x180036cb2  test    ecx, ecx
0x180036cb4  cmovns  ecx, eax
0x180036cb7  mov     eax, ecx
0x180036cb9  jmp     short loc_180036CD2
0x180036cbb  sub     ebx, eax
0x180036cbd  mov     r8, rsi; unsigned __int16 *
0x180036cc0  mov     eax, eax
0x180036cc2  mov     edx, ebx; unsigned __int64
0x180036cc4  lea     rcx, [r14+rax*2]; unsigned __int16 *
0x180036cc8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180036ccd  test    eax, eax
0x180036ccf  cmovns  eax, edi
0x180036cd2  add     rsp, 28h
0x180036cd6  pop     r14
0x180036cd8  pop     rdi
0x180036cd9  pop     rsi
0x180036cda  pop     rbx
0x180036cdb  retn
```
