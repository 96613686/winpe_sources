# GetUniHiveKeyName(HKEY__ *,ushort *,ulong,ushort const *)

- ea: `0x18000d184`
- end: `0x18000d362`
- name: `?GetUniHiveKeyName@@YAHPEAUHKEY__@@PEAGKPEBG@Z`
- size: `478`
- prototype: `__int64 __fastcall(HKEY, unsigned __int16 *, __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x18000e060`

## callees

- `0x1800022bc`
- `0x1800035c8`
- `0x18000d184`
- `0x1800198d0`
- `0x18001a688`
- `0x18001b294`
- `0x18001b980`

## import_xrefs

- `USER32!CharNextW` at `0x18000d214`
- `USER32!CharNextW` at `0x18000d214`
- `KERNEL32!GetFileAttributesW` at `0x18000d30d`
- `KERNEL32!GetFileAttributesW` at `0x18000d30d`
- `ADVAPI32!RegQueryValueExW` at `0x18000d1ec`
- `ADVAPI32!RegQueryValueExW` at `0x18000d1ec`
- `ADVAPI32!RegCloseKey` at `0x18000d293`
- `ADVAPI32!RegCloseKey` at `0x18000d293`
- `ADVAPI32!RegOpenKeyExW` at `0x18000d284`
- `ADVAPI32!RegOpenKeyExW` at `0x18000d284`
- `SHLWAPI!StrRChrW` at `0x18000d206`
- `SHLWAPI!StrRChrW` at `0x18000d206`

## string_xrefs

- `0x18000d1d5`: `BackupRegPathName`

## pseudocode

```c
__int64 __fastcall GetUniHiveKeyName(HKEY a1, unsigned __int16 *a2, __int64 a3, const unsigned __int16 *a4)
{
  const WCHAR *v6; // rax
  const unsigned __int16 *v7; // rax
  unsigned int v8; // r14d
  int i; // esi
  const WCHAR *v10; // rdi
  ULONG lpData; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v16; // [rsp+246h] [rbp+146h]
  WCHAR pszPathOut[264]; // [rsp+250h] [rbp+150h] BYREF

  cbData = 518;
  v16 = 0;
  if ( RegQueryValueExW(a1, L"BackupRegPathName", 0, 0, Data, &cbData) || (v6 = StrRChrW((PCWSTR)Data, 0, 0x5Cu)) == 0 )
  {
    v8 = 0;
    phkResult = 0;
    for ( i = 0; i < 9999; ++i )
    {
      StringCchPrintfW((unsigned __int16 *)Data, 0x104u, L"AINF%04d", (unsigned int)i);
      if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)Data, 0, 0x20019u, &phkResult) )
      {
        if ( StringCchCopyW(pszPathOut, 0x104u, a4) >= 0 )
        {
          v10 = (const WCHAR *)Data;
          if ( !(unsigned int)PathIsUnc2((unsigned __int16 *)Data)
            && !IsExtendedLengthDosDevicePath((const unsigned __int16 *)Data)
            && *(_WORD *)Data == 92 )
          {
            do
              ++v10;
            while ( *v10 == 92 );
          }
          PathCchCombineEx(pszPathOut, 0x104u, pszPathOut, v10, lpData);
          if ( GetFileAttributesW(pszPathOut) == -1 )
          {
            v8 = 1;
            StringCchCopyW(a2, 0x104u, (const unsigned __int16 *)Data);
            return v8;
          }
        }
      }
      else
      {
        RegCloseKey(phkResult);
      }
    }
  }
  else
  {
    v7 = CharNextW(v6);
    StringCchCopyW(a2, 0x104u, v7);
    return 1;
  }
  return v8;
}

```

## disassembly

```asm
0x18000d184  mov     [rsp-8+arg_10], rbx
0x18000d189  push    rbp
0x18000d18a  push    rsi
0x18000d18b  push    rdi
0x18000d18c  push    r12
0x18000d18e  push    r13
0x18000d190  push    r14
0x18000d192  push    r15
0x18000d194  lea     rbp, [rsp-370h]
0x18000d19c  sub     rsp, 470h
0x18000d1a3  mov     rax, cs:__security_cookie
0x18000d1aa  xor     rax, rsp
0x18000d1ad  mov     [rbp+3A0h+var_40], rax
0x18000d1b4  xor     eax, eax
0x18000d1b6  mov     [rsp+4A0h+cbData], 206h
0x18000d1be  mov     [rbp+3A0h+var_25A], ax
0x18000d1c5  mov     r12, r9
0x18000d1c8  lea     rax, [rsp+4A0h+cbData]
0x18000d1cd  mov     r15, rdx
0x18000d1d0  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x18000d1d5  lea     rdx, aBackupregpathn; "BackupRegPathName"
0x18000d1dc  lea     rax, [rsp+4A0h+Data]
0x18000d1e1  xor     r9d, r9d; lpType
0x18000d1e4  xor     r8d, r8d; lpReserved
0x18000d1e7  mov     [rsp+4A0h+lpData], rax; lpData
0x18000d1ec  call    cs:__imp_RegQueryValueExW
0x18000d1f2  mov     r13d, 5Ch ; '\'
0x18000d1f8  test    eax, eax
0x18000d1fa  jnz     short loc_18000D233
0x18000d1fc  mov     r8d, r13d; wMatch
0x18000d1ff  lea     rcx, [rsp+4A0h+Data]; pszStart
0x18000d204  xor     edx, edx; pszEnd
0x18000d206  call    cs:__imp_StrRChrW
0x18000d20c  test    rax, rax
0x18000d20f  jz      short loc_18000D233
0x18000d211  mov     rcx, rax; lpsz
0x18000d214  call    cs:__imp_CharNextW
0x18000d21a  mov     edx, 104h; unsigned __int64
0x18000d21f  mov     rcx, r15; unsigned __int16 *
0x18000d222  mov     r8, rax; unsigned __int16 *
0x18000d225  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d22a  lea     r14d, [r13-5Bh]
0x18000d22e  jmp     loc_18000D335
0x18000d233  xor     r14d, r14d
0x18000d236  mov     ebx, 104h
0x18000d23b  mov     [rsp+4A0h+phkResult], r14
0x18000d240  xor     esi, esi
0x18000d242  cmp     esi, 270Fh
0x18000d248  jge     loc_18000D335
0x18000d24e  mov     r9d, esi
0x18000d251  lea     r8, aAinf04d; "AINF%04d"
0x18000d258  mov     rdx, rbx; unsigned __int64
0x18000d25b  lea     rcx, [rsp+4A0h+Data]; unsigned __int16 *
0x18000d260  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d265  lea     rax, [rsp+4A0h+phkResult]
0x18000d26a  mov     r9d, 20019h; samDesired
0x18000d270  xor     r8d, r8d; ulOptions
0x18000d273  mov     [rsp+4A0h+lpData], rax; dwFlags
0x18000d278  lea     rdx, [rsp+4A0h+Data]; lpSubKey
0x18000d27d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d284  call    cs:__imp_RegOpenKeyExW
0x18000d28a  test    eax, eax
0x18000d28c  jnz     short loc_18000D29B
0x18000d28e  mov     rcx, [rsp+4A0h+phkResult]; hKey
0x18000d293  call    cs:__imp_RegCloseKey
0x18000d299  jmp     short loc_18000D318
0x18000d29b  mov     r8, r12; unsigned __int16 *
0x18000d29e  lea     rcx, [rbp+3A0h+pszPathOut]; unsigned __int16 *
0x18000d2a5  mov     rdx, rbx; unsigned __int64
0x18000d2a8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d2ad  test    eax, eax
0x18000d2af  js      short loc_18000D318
0x18000d2b1  lea     r8, IsBackslash
0x18000d2b8  xor     edx, edx
0x18000d2ba  lea     rcx, [rsp+4A0h+Data]; unsigned __int16 *
0x18000d2bf  lea     rdi, [rsp+4A0h+Data]
0x18000d2c4  call    PathIsUnc2
0x18000d2c9  test    eax, eax
0x18000d2cb  jnz     short loc_18000D2ED
0x18000d2cd  lea     rcx, [rsp+4A0h+Data]; unsigned __int16 *
0x18000d2d2  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x18000d2d7  test    al, al
0x18000d2d9  jnz     short loc_18000D2ED
0x18000d2db  cmp     word ptr [rsp+4A0h+Data], r13w
0x18000d2e1  jnz     short loc_18000D2ED
0x18000d2e3  add     rdi, 2
0x18000d2e7  cmp     [rdi], r13w
0x18000d2eb  jz      short loc_18000D2E3
0x18000d2ed  mov     r9, rdi; pszMore
0x18000d2f0  lea     r8, [rbp+3A0h+pszPathOut]; pszPathIn
0x18000d2f7  mov     rdx, rbx; cchPathOut
0x18000d2fa  lea     rcx, [rbp+3A0h+pszPathOut]; pszPathOut
0x18000d301  call    PathCchCombineEx
0x18000d306  lea     rcx, [rbp+3A0h+pszPathOut]; lpFileName
0x18000d30d  call    cs:__imp_GetFileAttributesW
0x18000d313  cmp     eax, 0FFFFFFFFh
0x18000d316  jz      short loc_18000D31F
0x18000d318  inc     esi
0x18000d31a  jmp     loc_18000D242
0x18000d31f  lea     r8, [rsp+4A0h+Data]; unsigned __int16 *
0x18000d324  mov     rdx, rbx; unsigned __int64
0x18000d327  mov     rcx, r15; unsigned __int16 *
0x18000d32a  mov     r14d, 1
0x18000d330  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d335  mov     eax, r14d
0x18000d338  mov     rcx, [rbp+3A0h+var_40]
0x18000d33f  xor     rcx, rsp; StackCookie
0x18000d342  call    __security_check_cookie
0x18000d347  mov     rbx, [rsp+4A0h+arg_10]
0x18000d34f  add     rsp, 470h
0x18000d356  pop     r15
0x18000d358  pop     r14
0x18000d35a  pop     r13
0x18000d35c  pop     r12
0x18000d35e  pop     rdi
0x18000d35f  pop     rsi
0x18000d360  pop     rbp
0x18000d361  retn
```
