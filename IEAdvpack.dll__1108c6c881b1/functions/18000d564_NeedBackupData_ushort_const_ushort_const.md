# NeedBackupData(ushort const *,ushort const *)

- ea: `0x18000d564`
- end: `0x18000d6c3`
- name: `?NeedBackupData@@YAHPEBG0@Z`
- size: `351`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpAppName)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000e060`

## callees

- `0x180007454`
- `0x18000d564`
- `0x180015c74`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetEnvironmentVariableW` at `0x18000d5ac`
- `KERNEL32!GetEnvironmentVariableW` at `0x18000d5ac`
- `KERNEL32!GetModuleFileNameW` at `0x18000d5c3`
- `KERNEL32!GetModuleFileNameW` at `0x18000d5c3`
- `KERNEL32!CompareStringW` at `0x18000d604`
- `KERNEL32!CompareStringW` at `0x18000d691`
- `KERNEL32!CompareStringW` at `0x18000d604`
- `KERNEL32!CompareStringW` at `0x18000d691`
- `SHLWAPI!StrRChrW` at `0x18000d5d8`
- `SHLWAPI!StrRChrW` at `0x18000d5d8`

## pseudocode

```c
__int64 __fastcall NeedBackupData(const unsigned __int16 *a1, LPCWSTR lpAppName)
{
  unsigned int v4; // ebx
  PWSTR v5; // rax
  int i; // edi
  WCHAR String2[16]; // [rsp+30h] [rbp-258h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-238h] BYREF

  v4 = 1;
  if ( ctx >= 3u
    && GetEnvironmentVariableW(L"Upgrade", Buffer, 0x104u)
    && GetModuleFileNameW(0, Buffer, 0x104u)
    && (v5 = StrRChrW(Buffer, 0, 0x5Cu)) != 0
    && CompareStringW(0x7Fu, 1u, v5 + 1, -1, L"setup.exe", -1) == 2 )
  {
    return 0;
  }
  else if ( (int)GetTranslatedString(a1, lpAppName, L"NoBackupPlatform", Buffer, 0x104u, 0) >= 0 && Buffer[0] )
  {
    for ( i = 0; (unsigned int)GetFieldString(Buffer, i, String2, 10); ++i )
    {
      if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)(&c_pszPlatform)[ctx], -1, String2, -1) == 2 )
        return 0;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000d564  mov     [rsp+arg_10], rbx
0x18000d569  push    rbp
0x18000d56a  push    rsi
0x18000d56b  push    rdi
0x18000d56c  sub     rsp, 270h
0x18000d573  mov     rax, cs:__security_cookie
0x18000d57a  xor     rax, rsp
0x18000d57d  mov     [rsp+288h+var_28], rax
0x18000d585  xor     ebp, ebp
0x18000d587  mov     rsi, rdx
0x18000d58a  cmp     cs:?ctx@@3UADVCONTEXTW@@A, 3; ADVCONTEXTW ctx
0x18000d592  mov     rdi, rcx
0x18000d595  lea     ebx, [rbp+1]
0x18000d598  jb      short loc_18000D613
0x18000d59a  mov     r8d, 104h; nSize
0x18000d5a0  lea     rdx, [rsp+288h+Buffer]; lpBuffer
0x18000d5a5  lea     rcx, aUpgrade; "Upgrade"
0x18000d5ac  call    cs:__imp_GetEnvironmentVariableW
0x18000d5b2  test    eax, eax
0x18000d5b4  jz      short loc_18000D613
0x18000d5b6  mov     r8d, 104h; nSize
0x18000d5bc  lea     rdx, [rsp+288h+Buffer]; lpFilename
0x18000d5c1  xor     ecx, ecx; hModule
0x18000d5c3  call    cs:__imp_GetModuleFileNameW
0x18000d5c9  test    eax, eax
0x18000d5cb  jz      short loc_18000D613
0x18000d5cd  xor     edx, edx; pszEnd
0x18000d5cf  lea     r8d, [rbp+5Ch]; wMatch
0x18000d5d3  lea     rcx, [rsp+288h+Buffer]; pszStart
0x18000d5d8  call    cs:__imp_StrRChrW
0x18000d5de  test    rax, rax
0x18000d5e1  jz      short loc_18000D613
0x18000d5e3  lea     r8, [rax+2]; lpString1
0x18000d5e7  mov     [rsp+288h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000d5ef  lea     rax, aSetupExe; "setup.exe"
0x18000d5f6  or      r9d, 0FFFFFFFFh; cchCount1
0x18000d5fa  mov     edx, ebx; dwCmpFlags
0x18000d5fc  mov     [rsp+288h+lpString2], rax; lpString2
0x18000d601  lea     ecx, [rbp+7Fh]; Locale
0x18000d604  call    cs:__imp_CompareStringW
0x18000d60a  cmp     eax, 2
0x18000d60d  jz      loc_18000D69C
0x18000d613  mov     qword ptr [rsp+288h+cchCount2], rbp; unsigned int *
0x18000d618  lea     r9, [rsp+288h+Buffer]; unsigned __int16 *
0x18000d61d  lea     r8, aNobackupplatfo; "NoBackupPlatform"
0x18000d624  mov     dword ptr [rsp+288h+lpString2], 104h; unsigned int
0x18000d62c  mov     rdx, rsi; lpAppName
0x18000d62f  mov     rcx, rdi; unsigned __int16 *
0x18000d632  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x18000d637  test    eax, eax
0x18000d639  js      short loc_18000D69E
0x18000d63b  cmp     [rsp+288h+Buffer], bp
0x18000d640  jz      short loc_18000D69E
0x18000d642  mov     edi, ebp
0x18000d644  mov     r9d, 0Ah; int
0x18000d64a  lea     r8, [rsp+288h+String2]; unsigned __int16 *
0x18000d64f  mov     edx, edi; int
0x18000d651  lea     rcx, [rsp+288h+Buffer]; unsigned __int16 *
0x18000d656  call    ?GetFieldString@@YAHPEBGHPEAGH@Z; GetFieldString(ushort const *,int,ushort *,int)
0x18000d65b  test    eax, eax
0x18000d65d  jz      short loc_18000D69E
0x18000d65f  movzx   r8d, cs:?ctx@@3UADVCONTEXTW@@A; ADVCONTEXTW ctx
0x18000d667  lea     rcx, ?c_pszPlatform@@3PAPEBGA; ushort const * near * c_pszPlatform
0x18000d66e  lea     rax, [rsp+288h+String2]
0x18000d673  mov     [rsp+288h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000d67b  or      r9d, 0FFFFFFFFh; cchCount1
0x18000d67f  mov     [rsp+288h+lpString2], rax; lpString2
0x18000d684  mov     edx, ebx; dwCmpFlags
0x18000d686  add     edi, ebx
0x18000d688  mov     r8, [rcx+r8*8]; lpString1
0x18000d68c  mov     ecx, 7Fh; Locale
0x18000d691  call    cs:__imp_CompareStringW
0x18000d697  cmp     eax, 2
0x18000d69a  jnz     short loc_18000D644
0x18000d69c  mov     ebx, ebp
0x18000d69e  mov     eax, ebx
0x18000d6a0  mov     rcx, [rsp+288h+var_28]
0x18000d6a8  xor     rcx, rsp; StackCookie
0x18000d6ab  call    __security_check_cookie
0x18000d6b0  mov     rbx, [rsp+288h+arg_10]
0x18000d6b8  add     rsp, 270h
0x18000d6bf  pop     rdi
0x18000d6c0  pop     rsi
0x18000d6c1  pop     rbp
0x18000d6c2  retn
```
