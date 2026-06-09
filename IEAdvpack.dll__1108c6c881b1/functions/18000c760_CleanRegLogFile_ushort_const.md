# CleanRegLogFile(ushort const *)

- ea: `0x18000c760`
- end: `0x18000c8c2`
- name: `?CleanRegLogFile@@YAXPEBG@Z`
- size: `354`
- prototype: `void __fastcall(LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000e060`

## callees

- `0x1800022bc`
- `0x18000c760`
- `0x1800198d0`
- `0x18001a688`
- `0x18001b294`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetWindowsDirectoryW` at `0x18000c823`
- `KERNEL32!GetWindowsDirectoryW` at `0x18000c823`
- `KERNEL32!DeleteFileW` at `0x18000c898`
- `KERNEL32!DeleteFileW` at `0x18000c898`
- `ADVAPI32!RegQueryValueExW` at `0x18000c7ea`
- `ADVAPI32!RegQueryValueExW` at `0x18000c7ea`
- `ADVAPI32!RegCloseKey` at `0x18000c7fe`
- `ADVAPI32!RegCloseKey` at `0x18000c7fe`
- `ADVAPI32!RegOpenKeyExW` at `0x18000c7b6`
- `ADVAPI32!RegOpenKeyExW` at `0x18000c7b6`

## pseudocode

```c
void __fastcall CleanRegLogFile(LPCWSTR lpValueName)
{
  const WCHAR *v2; // rbx
  ULONG phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v7; // [rsp+42h] [rbp-BEh]
  WCHAR Buffer[264]; // [rsp+250h] [rbp+150h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Advanced INF Setup", 0, 0x20019u, &hKey) )
  {
    cbData = 520;
    if ( RegQueryValueExW(hKey, lpValueName, 0, 0, Data, &cbData) )
      *(_WORD *)Data = 0;
    RegCloseKey(hKey);
  }
  if ( *(_WORD *)Data )
  {
    if ( v7 == 58 )
    {
      StringCchCopyW(Buffer, 0x104u, (const unsigned __int16 *)Data);
    }
    else
    {
      GetWindowsDirectoryW(Buffer, 0x104u);
      v2 = (const WCHAR *)Data;
      if ( !(unsigned int)PathIsUnc2((unsigned __int16 *)Data)
        && !IsExtendedLengthDosDevicePath((const unsigned __int16 *)Data)
        && *(_WORD *)Data == 92 )
      {
        do
          ++v2;
        while ( *v2 == 92 );
      }
      PathCchCombineEx(Buffer, 0x104u, Buffer, v2, phkResult);
    }
    DeleteFileW(Buffer);
  }
}

```

## disassembly

```asm
0x18000c760  mov     [rsp-8+arg_8], rbx
0x18000c765  mov     [rsp-8+arg_10], rdi
0x18000c76a  push    rbp
0x18000c76b  lea     rbp, [rsp-370h]
0x18000c773  sub     rsp, 470h
0x18000c77a  mov     rax, cs:__security_cookie
0x18000c781  xor     rax, rsp
0x18000c784  mov     [rbp+370h+var_10], rax
0x18000c78b  mov     rbx, rcx
0x18000c78e  lea     rax, [rsp+470h+hKey]
0x18000c793  xor     edi, edi
0x18000c795  mov     [rsp+470h+phkResult], rax; phkResult
0x18000c79a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c7a1  mov     [rsp+470h+hKey], rdi
0x18000c7a6  mov     r9d, 20019h; samDesired
0x18000c7ac  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Advanced INF Setup"
0x18000c7b3  xor     r8d, r8d; ulOptions
0x18000c7b6  call    cs:__imp_RegOpenKeyExW
0x18000c7bc  test    eax, eax
0x18000c7be  jnz     short loc_18000C804
0x18000c7c0  mov     rcx, [rsp+470h+hKey]; hKey
0x18000c7c5  lea     rax, [rsp+470h+cbData]
0x18000c7ca  mov     [rsp+470h+lpcbData], rax; lpcbData
0x18000c7cf  xor     r9d, r9d; lpType
0x18000c7d2  lea     rax, [rsp+470h+Data]
0x18000c7d7  mov     [rsp+470h+cbData], 208h
0x18000c7df  xor     r8d, r8d; lpReserved
0x18000c7e2  mov     [rsp+470h+phkResult], rax; dwFlags
0x18000c7e7  mov     rdx, rbx; lpValueName
0x18000c7ea  call    cs:__imp_RegQueryValueExW
0x18000c7f0  test    eax, eax
0x18000c7f2  jz      short loc_18000C7F9
0x18000c7f4  mov     word ptr [rsp+470h+Data], di
0x18000c7f9  mov     rcx, [rsp+470h+hKey]; hKey
0x18000c7fe  call    cs:__imp_RegCloseKey
0x18000c804  cmp     word ptr [rsp+470h+Data], di
0x18000c809  jz      loc_18000C89E
0x18000c80f  cmp     [rsp+470h+var_42E], 3Ah ; ':'
0x18000c815  lea     rcx, [rbp+370h+Buffer]; unsigned __int16 *
0x18000c81c  jz      short loc_18000C882
0x18000c81e  mov     edx, 104h; uSize
0x18000c823  call    cs:__imp_GetWindowsDirectoryW
0x18000c829  lea     r8, IsBackslash
0x18000c830  xor     edx, edx
0x18000c832  lea     rcx, [rsp+470h+Data]; unsigned __int16 *
0x18000c837  lea     rbx, [rsp+470h+Data]
0x18000c83c  call    PathIsUnc2
0x18000c841  test    eax, eax
0x18000c843  jnz     short loc_18000C865
0x18000c845  lea     rcx, [rsp+470h+Data]; unsigned __int16 *
0x18000c84a  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x18000c84f  test    al, al
0x18000c851  jnz     short loc_18000C865
0x18000c853  cmp     word ptr [rsp+470h+Data], 5Ch ; '\'
0x18000c859  jnz     short loc_18000C865
0x18000c85b  add     rbx, 2
0x18000c85f  cmp     word ptr [rbx], 5Ch ; '\'
0x18000c863  jz      short loc_18000C85B
0x18000c865  mov     r9, rbx; pszMore
0x18000c868  lea     r8, [rbp+370h+Buffer]; pszPathIn
0x18000c86f  mov     edx, 104h; cchPathOut
0x18000c874  lea     rcx, [rbp+370h+Buffer]; pszPathOut
0x18000c87b  call    PathCchCombineEx
0x18000c880  jmp     short loc_18000C891
0x18000c882  lea     r8, [rsp+470h+Data]; unsigned __int16 *
0x18000c887  mov     edx, 104h; unsigned __int64
0x18000c88c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c891  lea     rcx, [rbp+370h+Buffer]; lpFileName
0x18000c898  call    cs:__imp_DeleteFileW
0x18000c89e  mov     rcx, [rbp+370h+var_10]
0x18000c8a5  xor     rcx, rsp; StackCookie
0x18000c8a8  call    __security_check_cookie
0x18000c8ad  lea     r11, [rsp+470h+var_s0]
0x18000c8b5  mov     rbx, [r11+18h]
0x18000c8b9  mov     rdi, [r11+20h]
0x18000c8bd  mov     rsp, r11
0x18000c8c0  pop     rbp
0x18000c8c1  retn
```
