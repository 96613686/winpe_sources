# PathQualifyDef

- ea: `0x1805bcfc0`
- end: `0x1805bd288`
- name: `PathQualifyDef`
- size: `712`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1802ac220`
- `0x1805aac14`
- `0x1805aad78`
- `0x1805bcfa0`

## callees

- `0x1800a3080`
- `0x1803a4cb0`
- `0x1805bcfc0`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1805bd1b3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1805bd1b3`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x1805bd24e`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x1805bd24e`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1805bd0d8`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1805bd0d8`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x1805bd043`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x1805bd043`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x1805bd22b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x1805bd22b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1805bd179`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1805bd179`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1805bd077`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1805bd077`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x1805bd0f2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x1805bd110`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x1805bd0f2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x1805bd110`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootW` at `0x1805bd08b`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootW` at `0x1805bd08b`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_FixSlashesAndColonW` at `0x1805bd02e`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_FixSlashesAndColonW` at `0x1805bd02e`

## pseudocode

```c
void __fastcall PathQualifyDef(unsigned __int16 *a1, unsigned int a2, unsigned __int16 *a3, char a4)
{
  unsigned __int64 v5; // rdi
  char v7; // r12
  __int64 v8; // r14
  WCHAR *v9; // rbx
  int DriveNumberW; // eax
  unsigned __int16 *v11; // r15
  __int64 v12; // rax
  unsigned __int16 *v13; // rdi
  WCHAR v14; // ax
  __int64 v15; // rax
  WCHAR v16; // ax
  bool v17; // zf
  WCHAR v18; // ax
  LPWSTR v19; // rax
  PCWSTR ppszServer; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR pszPath[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v23; // [rsp+34h] [rbp-CCh] BYREF
  char v24; // [rsp+36h] [rbp-CAh] BYREF
  WCHAR pszRoot[264]; // [rsp+240h] [rbp+140h] BYREF

  if ( a2 )
  {
    v5 = a2;
    v7 = a4;
    if ( (int)StringCchCopyW(pszPath, 0x104u, a1) >= 0 )
    {
      FixSlashesAndColonW(pszPath);
      ppszServer = 0;
      v8 = -1;
      if ( PathIsUNCEx(pszPath, &ppszServer) )
      {
        v9 = (WCHAR *)ppszServer;
        a1[ppszServer - pszPath] = 0;
      }
      else
      {
        DriveNumberW = PathGetDriveNumberW(pszPath);
        if ( DriveNumberW == -1 )
        {
          if ( !a3 || (int)StringCchCopyW(pszRoot, 0x104u, a3) < 0 )
          {
            pszRoot[0] = 0;
            if ( GetWindowsDirectoryW(pszRoot, 0x104u) - 1 > 0x102 )
              return;
            PathStripToRootW(pszRoot);
          }
          v9 = pszPath;
          if ( pszPath[0] == 92 )
            PathStripToRootW(pszRoot);
        }
        else
        {
          PathBuildRootW(pszRoot, DriveNumberW);
          v9 = (WCHAR *)&v24;
          if ( v23 != 92 )
            v9 = (WCHAR *)&v23;
        }
        StringCchCopyW(a1, v5, pszRoot);
      }
      v11 = &a1[v5];
      v12 = -1;
      do
        ++v12;
      while ( a1[v12] );
      v13 = &a1[v12];
      if ( *v9 )
      {
        do
        {
          if ( v13 >= v11 )
            goto LABEL_46;
          if ( *v9 == 46 )
          {
            v14 = v9[1];
            if ( v14 == 46 )
            {
              if ( !v9[2] || v9[2] == 92 )
              {
                *v13 = 0;
                PathRemoveFileSpecW(a1);
                v15 = -1;
                do
                  ++v15;
                while ( a1[v15] );
                v13 = &a1[v15];
LABEL_29:
                v16 = *v9;
                v17 = *v9 == 0;
                if ( !*v9 )
                  continue;
                do
                {
                  if ( v16 == 92 )
                    break;
                  v9 = CharNextW(v9);
                  v16 = *v9;
                }
                while ( *v9 );
                v7 = a4;
                v17 = *v9 == 0;
                if ( !*v9 )
                  continue;
                goto LABEL_43;
              }
            }
            else if ( !v14 || v14 == 92 )
            {
              goto LABEL_29;
            }
          }
          if ( v13 > a1 && *(v13 - 1) != 92 )
          {
            *v13 = 92;
            goto LABEL_40;
          }
          while ( 1 )
          {
            v18 = *v9;
            if ( !*v9 || v18 == 92 || v13 >= v11 )
              break;
            ++v9;
            *v13 = v18;
LABEL_40:
            ++v13;
          }
          if ( !*v9 )
            break;
LABEL_43:
          v17 = *++v9 == 0;
        }
        while ( !v17 );
      }
      if ( v13 >= v11 )
LABEL_46:
        v13 = v11 - 1;
      *v13 = 0;
      PathRemoveBackslashW(a1);
      if ( (v7 & 1) == 0 && *a1 )
      {
        do
          ++v8;
        while ( a1[v8] );
        v19 = CharPrevW(a1, &a1[v8]);
        if ( *v19 == 46 )
          *v19 = 0;
      }
    }
  }
}

```

## disassembly

```asm
0x1805bcfc0  test    edx, edx
0x1805bcfc2  jz      locret_1805BD287
0x1805bcfc8  mov     [rsp-8+arg_18], rbx
0x1805bcfcd  push    rbp
0x1805bcfce  push    rsi
0x1805bcfcf  push    rdi
0x1805bcfd0  push    r12
0x1805bcfd2  push    r13
0x1805bcfd4  push    r14
0x1805bcfd6  push    r15
0x1805bcfd8  lea     rbp, [rsp-360h]
0x1805bcfe0  sub     rsp, 460h
0x1805bcfe7  mov     rax, cs:__security_cookie
0x1805bcfee  xor     rax, rsp
0x1805bcff1  mov     [rbp+390h+var_40], rax
0x1805bcff8  mov     rbx, r8
0x1805bcffb  mov     edi, edx
0x1805bcffd  mov     r8, rcx; unsigned __int16 *
0x1805bd000  mov     [rsp+490h+var_470], r9d
0x1805bd005  mov     rsi, rcx
0x1805bd008  mov     r15d, 104h
0x1805bd00e  mov     edx, r15d; unsigned __int64
0x1805bd011  lea     rcx, [rsp+490h+pszPath]; unsigned __int16 *
0x1805bd016  mov     r12d, r9d
0x1805bd019  xor     r13d, r13d
0x1805bd01c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1805bd021  test    eax, eax
0x1805bd023  js      loc_1805BD25E
0x1805bd029  lea     rcx, [rsp+490h+pszPath]
0x1805bd02e  call    cs:__imp_FixSlashesAndColonW
0x1805bd034  lea     rdx, [rsp+490h+ppszServer]; ppszServer
0x1805bd039  mov     [rsp+490h+ppszServer], r13
0x1805bd03e  lea     rcx, [rsp+490h+pszPath]; pszPath
0x1805bd043  call    cs:__imp_PathIsUNCEx
0x1805bd049  or      r14, 0FFFFFFFFFFFFFFFFh
0x1805bd04d  lea     edx, [r13+5Ch]
0x1805bd051  test    eax, eax
0x1805bd053  jz      short loc_1805BD072
0x1805bd055  mov     rbx, [rsp+490h+ppszServer]
0x1805bd05a  lea     rax, [rsp+490h+pszPath]
0x1805bd05f  mov     rcx, rbx
0x1805bd062  sub     rcx, rax
0x1805bd065  sar     rcx, 1
0x1805bd068  mov     [rsi+rcx*2], r13w
0x1805bd06d  jmp     loc_1805BD12D
0x1805bd072  lea     rcx, [rsp+490h+pszPath]; pszPath
0x1805bd077  call    cs:__imp_PathGetDriveNumberW
0x1805bd07d  cmp     eax, r14d
0x1805bd080  jz      short loc_1805BD0AB
0x1805bd082  mov     edx, eax; iDrive
0x1805bd084  lea     rcx, [rbp+390h+pszRoot]; pszRoot
0x1805bd08b  call    cs:__imp_PathBuildRootW
0x1805bd091  mov     ecx, 5Ch ; '\'
0x1805bd096  lea     rbx, [rsp+490h+var_45A]
0x1805bd09b  cmp     [rsp+490h+var_45C], cx
0x1805bd0a0  lea     rax, [rsp+490h+var_45C]
0x1805bd0a5  cmovnz  rbx, rax
0x1805bd0a9  jmp     short loc_1805BD116
0x1805bd0ab  test    rbx, rbx
0x1805bd0ae  jz      short loc_1805BD0C6
0x1805bd0b0  mov     r8, rbx; unsigned __int16 *
0x1805bd0b3  lea     rcx, [rbp+390h+pszRoot]; unsigned __int16 *
0x1805bd0ba  mov     rdx, r15; unsigned __int64
0x1805bd0bd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1805bd0c2  test    eax, eax
0x1805bd0c4  jns     short loc_1805BD0F8
0x1805bd0c6  mov     edx, r15d; uSize
0x1805bd0c9  mov     [rbp+390h+pszRoot], r13w
0x1805bd0d1  lea     rcx, [rbp+390h+pszRoot]; lpBuffer
0x1805bd0d8  call    cs:__imp_GetWindowsDirectoryW
0x1805bd0de  dec     eax
0x1805bd0e0  cmp     eax, 102h
0x1805bd0e5  ja      loc_1805BD25E
0x1805bd0eb  lea     rcx, [rbp+390h+pszRoot]; pszPath
0x1805bd0f2  call    cs:__imp_PathStripToRootW
0x1805bd0f8  mov     eax, 5Ch ; '\'
0x1805bd0fd  lea     rbx, [rsp+490h+pszPath]
0x1805bd102  cmp     [rsp+490h+pszPath], ax
0x1805bd107  jnz     short loc_1805BD116
0x1805bd109  lea     rcx, [rbp+390h+pszRoot]; pszPath
0x1805bd110  call    cs:__imp_PathStripToRootW
0x1805bd116  lea     r8, [rbp+390h+pszRoot]; unsigned __int16 *
0x1805bd11d  mov     rdx, rdi; unsigned __int64
0x1805bd120  mov     rcx, rsi; unsigned __int16 *
0x1805bd123  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1805bd128  mov     edx, 5Ch ; '\'
0x1805bd12d  lea     r15, [rsi+rdi*2]
0x1805bd131  mov     rax, r14
0x1805bd134  inc     rax
0x1805bd137  cmp     [rsi+rax*2], r13w
0x1805bd13c  jnz     short loc_1805BD134
0x1805bd13e  lea     rdi, [rsi+rax*2]
0x1805bd142  cmp     [rbx], r13w
0x1805bd146  jz      loc_1805BD21B
0x1805bd14c  cmp     rdi, r15
0x1805bd14f  jnb     loc_1805BD220
0x1805bd155  cmp     word ptr [rbx], 2Eh ; '.'
0x1805bd159  jnz     short loc_1805BD1D3
0x1805bd15b  movzx   eax, word ptr [rbx+2]
0x1805bd15f  cmp     ax, 2Eh ; '.'
0x1805bd163  jnz     short loc_1805BD192
0x1805bd165  cmp     [rbx+4], r13w
0x1805bd16a  jz      short loc_1805BD172
0x1805bd16c  cmp     [rbx+4], dx
0x1805bd170  jnz     short loc_1805BD1D3
0x1805bd172  mov     rcx, rsi; pszPath
0x1805bd175  mov     [rdi], r13w
0x1805bd179  call    cs:__imp_PathRemoveFileSpecW
0x1805bd17f  mov     rax, r14
0x1805bd182  inc     rax
0x1805bd185  cmp     [rsi+rax*2], r13w
0x1805bd18a  jnz     short loc_1805BD182
0x1805bd18c  lea     rdi, [rsi+rax*2]
0x1805bd190  jmp     short loc_1805BD19C
0x1805bd192  test    ax, ax
0x1805bd195  jz      short loc_1805BD19C
0x1805bd197  cmp     ax, dx
0x1805bd19a  jnz     short loc_1805BD1D3
0x1805bd19c  movzx   eax, word ptr [rbx]
0x1805bd19f  test    ax, ax
0x1805bd1a2  jz      short loc_1805BD210
0x1805bd1a4  mov     r12d, 5Ch ; '\'
0x1805bd1aa  cmp     ax, r12w
0x1805bd1ae  jz      short loc_1805BD1C4
0x1805bd1b0  mov     rcx, rbx; lpsz
0x1805bd1b3  call    cs:__imp_CharNextW
0x1805bd1b9  mov     rbx, rax
0x1805bd1bc  movzx   eax, word ptr [rax]
0x1805bd1bf  test    ax, ax
0x1805bd1c2  jnz     short loc_1805BD1AA
0x1805bd1c4  movzx   eax, word ptr [rbx]
0x1805bd1c7  mov     r12d, [rsp+490h+var_470]
0x1805bd1cc  test    ax, ax
0x1805bd1cf  jz      short loc_1805BD210
0x1805bd1d1  jmp     short loc_1805BD206
0x1805bd1d3  cmp     rdi, rsi
0x1805bd1d6  jbe     short loc_1805BD1F8
0x1805bd1d8  cmp     dx, [rdi-2]
0x1805bd1dc  jz      short loc_1805BD1F8
0x1805bd1de  mov     [rdi], dx
0x1805bd1e1  jmp     short loc_1805BD1F4
0x1805bd1e3  cmp     ax, dx
0x1805bd1e6  jz      short loc_1805BD200
0x1805bd1e8  cmp     rdi, r15
0x1805bd1eb  jnb     short loc_1805BD200
0x1805bd1ed  add     rbx, 2
0x1805bd1f1  mov     [rdi], ax
0x1805bd1f4  add     rdi, 2
0x1805bd1f8  movzx   eax, word ptr [rbx]
0x1805bd1fb  test    ax, ax
0x1805bd1fe  jnz     short loc_1805BD1E3
0x1805bd200  cmp     [rbx], r13w
0x1805bd204  jz      short loc_1805BD21B
0x1805bd206  add     rbx, 2
0x1805bd20a  movzx   eax, word ptr [rbx]
0x1805bd20d  test    ax, ax
0x1805bd210  mov     edx, 5Ch ; '\'
0x1805bd215  jnz     loc_1805BD14C
0x1805bd21b  cmp     rdi, r15
0x1805bd21e  jb      short loc_1805BD224
0x1805bd220  lea     rdi, [r15-2]
0x1805bd224  mov     rcx, rsi; pszPath
0x1805bd227  mov     [rdi], r13w
0x1805bd22b  call    cs:__imp_PathRemoveBackslashW
0x1805bd231  test    r12b, 1
0x1805bd235  jnz     short loc_1805BD25E
0x1805bd237  cmp     [rsi], r13w
0x1805bd23b  jz      short loc_1805BD25E
0x1805bd23d  inc     r14
0x1805bd240  cmp     [rsi+r14*2], r13w
0x1805bd245  jnz     short loc_1805BD23D
0x1805bd247  lea     rdx, [rsi+r14*2]; lpszCurrent
0x1805bd24b  mov     rcx, rsi; lpszStart
0x1805bd24e  call    cs:__imp_CharPrevW
0x1805bd254  cmp     word ptr [rax], 2Eh ; '.'
0x1805bd258  jnz     short loc_1805BD25E
0x1805bd25a  mov     [rax], r13w
0x1805bd25e  mov     rcx, [rbp+390h+var_40]
0x1805bd265  xor     rcx, rsp; StackCookie
0x1805bd268  call    __security_check_cookie
0x1805bd26d  mov     rbx, [rsp+490h+arg_18]
0x1805bd275  add     rsp, 460h
0x1805bd27c  pop     r15
0x1805bd27e  pop     r14
0x1805bd280  pop     r13
0x1805bd282  pop     r12
0x1805bd284  pop     rdi
0x1805bd285  pop     rsi
0x1805bd286  pop     rbp
0x1805bd287  retn
```
