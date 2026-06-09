# AddDelBackupEntryHelper(ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x1800151d8`
- end: `0x1800152cf`
- name: `?AddDelBackupEntryHelper@@YAJPEBG00K@Z`
- size: `247`
- prototype: `__int64 __fastcall(LPCWSTR lpKeyName, const unsigned __int16 *, const unsigned __int16 *, char)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180017020`
- `0x1800170d0`
- `0x1800170e0`
- `0x180017190`

## callees

- `0x180003180`
- `0x1800151d8`
- `0x180017fdc`
- `0x18001b980`

## import_xrefs

- `KERNEL32!WritePrivateProfileStringW` at `0x180015270`
- `KERNEL32!WritePrivateProfileStringW` at `0x18001529c`
- `KERNEL32!WritePrivateProfileStringW` at `0x180015270`
- `KERNEL32!WritePrivateProfileStringW` at `0x18001529c`
- `KERNEL32!SetFileAttributesW` at `0x18001523f`
- `KERNEL32!SetFileAttributesW` at `0x1800152ac`
- `KERNEL32!SetFileAttributesW` at `0x18001523f`
- `KERNEL32!SetFileAttributesW` at `0x1800152ac`

## pseudocode

```c
__int64 __fastcall AddDelBackupEntryHelper(
        LPCWSTR lpKeyName,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4)
{
  const WCHAR *v5; // rbx
  const WCHAR *v6; // rdi
  __int64 v7; // rax
  WCHAR FileName[264]; // [rsp+20h] [rbp-238h] BYREF

  v5 = lpKeyName;
  if ( lpKeyName && *lpKeyName )
  {
    BuildPath(FileName, a2, a2, a3);
    StringCchCatW(FileName, 0x104u, L".INI");
    SetFileAttributesW(FileName, 0x80u);
    if ( *v5 )
    {
      v6 = (const WCHAR *)((unsigned __int64)L"-1,0,0,0,0,0,-1" & -(__int64)((a4 & 1) != 0));
      do
      {
        WritePrivateProfileStringW(L"backup", v5, v6, FileName);
        v7 = -1;
        do
          ++v7;
        while ( v5[v7] );
        v5 += v7 + 1;
      }
      while ( *v5 );
    }
    WritePrivateProfileStringW(0, 0, 0, FileName);
    SetFileAttributesW(FileName, 3u);
  }
  return 0;
}

```

## disassembly

```asm
0x1800151d8  push    rbx
0x1800151da  push    rsi
0x1800151db  push    rdi
0x1800151dc  sub     rsp, 240h
0x1800151e3  mov     rax, cs:__security_cookie
0x1800151ea  xor     rax, rsp
0x1800151ed  mov     [rsp+258h+var_28], rax
0x1800151f5  xor     esi, esi
0x1800151f7  mov     edi, r9d
0x1800151fa  mov     rbx, rcx
0x1800151fd  test    rcx, rcx
0x180015200  jz      loc_1800152B2
0x180015206  cmp     [rcx], si
0x180015209  jz      loc_1800152B2
0x18001520f  mov     r9, r8
0x180015212  lea     rcx, [rsp+258h+FileName]
0x180015217  mov     r8, rdx
0x18001521a  call    BuildPath
0x18001521f  lea     r8, aIni_0; ".INI"
0x180015226  mov     edx, 104h; unsigned __int64
0x18001522b  lea     rcx, [rsp+258h+FileName]; unsigned __int16 *
0x180015230  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180015235  mov     edx, 80h; dwFileAttributes
0x18001523a  lea     rcx, [rsp+258h+FileName]; lpFileName
0x18001523f  call    cs:__imp_SetFileAttributesW
0x180015245  cmp     [rbx], si
0x180015248  jz      short loc_180015290
0x18001524a  and     dil, 1
0x18001524e  lea     rax, a1000001; "-1,0,0,0,0,0,-1"
0x180015255  neg     dil
0x180015258  sbb     rdi, rdi
0x18001525b  and     rdi, rax
0x18001525e  lea     r9, [rsp+258h+FileName]; lpFileName
0x180015263  mov     r8, rdi; lpString
0x180015266  mov     rdx, rbx; lpKeyName
0x180015269  lea     rcx, c_szIE4SECTIONNAME; "backup"
0x180015270  call    cs:__imp_WritePrivateProfileStringW
0x180015276  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001527a  inc     rax
0x18001527d  cmp     [rbx+rax*2], si
0x180015281  jnz     short loc_18001527A
0x180015283  lea     rbx, [rbx+rax*2]
0x180015287  add     rbx, 2
0x18001528b  cmp     [rbx], si
0x18001528e  jnz     short loc_18001525E
0x180015290  lea     r9, [rsp+258h+FileName]; lpFileName
0x180015295  xor     r8d, r8d; lpString
0x180015298  xor     edx, edx; lpKeyName
0x18001529a  xor     ecx, ecx; lpAppName
0x18001529c  call    cs:__imp_WritePrivateProfileStringW
0x1800152a2  mov     edx, 3; dwFileAttributes
0x1800152a7  lea     rcx, [rsp+258h+FileName]; lpFileName
0x1800152ac  call    cs:__imp_SetFileAttributesW
0x1800152b2  xor     eax, eax
0x1800152b4  mov     rcx, [rsp+258h+var_28]
0x1800152bc  xor     rcx, rsp; StackCookie
0x1800152bf  call    __security_check_cookie
0x1800152c4  add     rsp, 240h
0x1800152cb  pop     rdi
0x1800152cc  pop     rsi
0x1800152cd  pop     rbx
0x1800152ce  retn
```
