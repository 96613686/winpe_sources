# ArpApplication::GetFileLocationFromCommandString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000c270`
- end: `0x18000c488`
- name: `?GetFileLocationFromCommandString@ArpApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z`
- size: `536`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000da54`

## callees

- `0x18000c270`
- `0x1800118d0`
- `0x1800150ac`
- `0x1800172bc`
- `0x1800175b0`
- `0x180018450`
- `0x180018a60`
- `0x180018ff4`
- `0x1800260f4`
- `0x1800402b4`
- `0x180045468`
- `0x180046d58`
- `0x18004eab4`
- `0x180059920`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x18000c310`
- `KERNEL32!GetFileAttributesW` at `0x18000c310`
- `SHLWAPI!PathFileExistsW` at `0x18000c2f8`
- `SHLWAPI!PathFileExistsW` at `0x18000c3f8`
- `SHLWAPI!PathFileExistsW` at `0x18000c2f8`
- `SHLWAPI!PathFileExistsW` at `0x18000c3f8`
- `SHLWAPI!PathIsNetworkPathW` at `0x18000c32d`
- `SHLWAPI!PathIsNetworkPathW` at `0x18000c414`
- `SHLWAPI!PathIsNetworkPathW` at `0x18000c32d`
- `SHLWAPI!PathIsNetworkPathW` at `0x18000c414`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall ArpApplication::GetFileLocationFromCommandString(__int64 a1)
{
  __int128 v2; // xmm0
  _QWORD *v3; // rdx
  char v4; // di
  __int64 v5; // r8
  const WCHAR *v6; // rcx
  const WCHAR *v7; // rcx
  DWORD FileAttributesW; // eax
  const WCHAR *v9; // rcx
  __int64 DirectoryFromPath; // rax
  __int64 v11; // rsi
  LPCWSTR *v12; // rcx
  __int64 v13; // rdi
  const WCHAR *v14; // rcx
  const WCHAR *v15; // rcx
  LPCWSTR pszPath[2]; // [rsp+40h] [rbp-21h] BYREF
  __int128 v18; // [rsp+50h] [rbp-11h]
  _OWORD v19[2]; // [rsp+60h] [rbp-1h] BYREF
  _BYTE v20[32]; // [rsp+80h] [rbp+1Fh] BYREF

  v2 = 0;
  memset(v19, 0, sizeof(v19));
  *(double *)&v2 = std::wstring::_Construct_empty(v19);
  v4 = 0;
  *(_OWORD *)pszPath = v2;
  v18 = 0u;
  v5 = v3[2];
  if ( v3[3] > 7u )
    v3 = (_QWORD *)*v3;
  std::wstring::_Construct<2,unsigned short const *>(pszPath, v3, v5);
  v6 = (const WCHAR *)pszPath;
  if ( *((_QWORD *)&v18 + 1) > 7u )
    v6 = pszPath[0];
  if ( PathFileExistsW(v6) )
  {
    v7 = (const WCHAR *)pszPath;
    if ( *((_QWORD *)&v18 + 1) > 7u )
      v7 = pszPath[0];
    FileAttributesW = GetFileAttributesW(v7);
    if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
    {
      v9 = (const WCHAR *)pszPath;
      if ( *((_QWORD *)&v18 + 1) > 7u )
        v9 = pszPath[0];
      if ( !PathIsNetworkPathW(v9) )
      {
        DirectoryFromPath = Utility::GetDirectoryFromPath(v20, pszPath);
        std::wstring::operator=(pszPath, DirectoryFromPath);
        std::wstring::~wstring(v20);
        v4 = 1;
      }
    }
  }
  v11 = 0;
  if ( !v4 )
  {
    while ( v11 != -1 )
    {
      v12 = pszPath;
      if ( *((_QWORD *)&v18 + 1) > 7u )
        v12 = (LPCWSTR *)pszPath[0];
      v11 = std::_Traits_rfind_ch<std::char_traits<unsigned short>>(v12, v18, -1, 92);
      v13 = std::wstring::substr(pszPath, v20, 0, v11);
      if ( pszPath != (LPCWSTR *)v13 )
      {
        std::wstring::_Tidy_deallocate(pszPath);
        *(_OWORD *)pszPath = *(_OWORD *)v13;
        v18 = *(_OWORD *)(v13 + 16);
        *(_QWORD *)(v13 + 16) = 0;
        *(_QWORD *)(v13 + 24) = 7;
        *(_WORD *)v13 = 0;
      }
      std::wstring::~wstring(v20);
      v14 = (const WCHAR *)pszPath;
      if ( *((_QWORD *)&v18 + 1) > 7u )
        v14 = pszPath[0];
      if ( PathFileExistsW(v14) )
      {
        v15 = (const WCHAR *)pszPath;
        if ( *((_QWORD *)&v18 + 1) > 7u )
          v15 = pszPath[0];
        if ( !PathIsNetworkPathW(v15) )
          goto LABEL_26;
      }
    }
    goto LABEL_28;
  }
LABEL_26:
  if ( !(unsigned __int8)Utility::ShouldScanInstallDirectoryForFiles(pszPath) )
  {
LABEL_28:
    std::wstring::wstring(a1);
    goto LABEL_29;
  }
  std::wstring::operator=(v19, pszPath);
  std::wstring::wstring(a1, v19);
LABEL_29:
  std::wstring::~wstring(pszPath);
  std::wstring::~wstring(v19);
  return a1;
}

```

## disassembly

```asm
0x18000c270  mov     rax, rsp
0x18000c273  push    rbp
0x18000c274  push    rsi
0x18000c275  push    rdi
0x18000c276  lea     rbp, [rax-5Fh]
0x18000c27a  sub     rsp, 0A0h
0x18000c281  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFEh
0x18000c289  mov     [rax+18h], rbx
0x18000c28d  mov     rax, cs:__security_cookie
0x18000c294  xor     rax, rsp
0x18000c297  mov     [rbp+57h+var_18], rax
0x18000c29b  mov     rbx, rcx
0x18000c29e  mov     [rbp+57h+var_80], rcx
0x18000c2a2  xorps   xmm0, xmm0
0x18000c2a5  movups  [rbp+57h+var_58], xmm0
0x18000c2a9  xorps   xmm1, xmm1
0x18000c2ac  movdqu  [rbp+57h+var_48], xmm1
0x18000c2b1  lea     rcx, [rbp+57h+var_58]
0x18000c2b5  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000c2ba  nop
0x18000c2bb  xor     dil, dil
0x18000c2be  movups  xmmword ptr [rbp+57h+pszPath], xmm0
0x18000c2c2  mov     qword ptr [rbp+57h+var_68], 0
0x18000c2ca  mov     qword ptr [rbp+57h+var_68+8], 0
0x18000c2d2  mov     r8, [rdx+10h]
0x18000c2d6  cmp     qword ptr [rdx+18h], 7
0x18000c2db  jbe     short loc_18000C2E0
0x18000c2dd  mov     rdx, [rdx]
0x18000c2e0  lea     rcx, [rbp+57h+pszPath]
0x18000c2e4  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x18000c2e9  nop
0x18000c2ea  lea     rcx, [rbp+57h+pszPath]
0x18000c2ee  cmp     qword ptr [rbp+57h+var_68+8], 7
0x18000c2f3  cmova   rcx, [rbp+57h+pszPath]; pszPath
0x18000c2f8  call    cs:__imp_PathFileExistsW
0x18000c2fe  test    eax, eax
0x18000c300  jz      short loc_18000C35C
0x18000c302  lea     rcx, [rbp+57h+pszPath]
0x18000c306  cmp     qword ptr [rbp+57h+var_68+8], 7
0x18000c30b  cmova   rcx, [rbp+57h+pszPath]; lpFileName
0x18000c310  call    cs:__imp_GetFileAttributesW
0x18000c316  cmp     eax, 0FFFFFFFFh
0x18000c319  jz      short loc_18000C31F
0x18000c31b  test    al, 10h
0x18000c31d  jnz     short loc_18000C35C
0x18000c31f  lea     rcx, [rbp+57h+pszPath]
0x18000c323  cmp     qword ptr [rbp+57h+var_68+8], 7
0x18000c328  cmova   rcx, [rbp+57h+pszPath]; pszPath
0x18000c32d  call    cs:__imp_PathIsNetworkPathW
0x18000c333  test    eax, eax
0x18000c335  jnz     short loc_18000C35C
0x18000c337  lea     rdx, [rbp+57h+pszPath]
0x18000c33b  lea     rcx, [rbp+57h+var_38]
0x18000c33f  call    ?GetDirectoryFromPath@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::GetDirectoryFromPath(std::wstring const &)
0x18000c344  mov     rdx, rax
0x18000c347  lea     rcx, [rbp+57h+pszPath]
0x18000c34b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000c350  lea     rcx, [rbp+57h+var_38]
0x18000c354  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000c359  mov     dil, 1
0x18000c35c  xor     esi, esi
0x18000c35e  test    dil, dil
0x18000c361  jnz     loc_18000C422
0x18000c367  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000c36b  jz      loc_18000C44A
0x18000c371  lea     rcx, [rbp+57h+pszPath]
0x18000c375  cmp     qword ptr [rbp+57h+var_68+8], 7
0x18000c37a  cmova   rcx, [rbp+57h+pszPath]
0x18000c37f  mov     r9d, 5Ch ; '\'
0x18000c385  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000c389  mov     rdx, qword ptr [rbp+57h+var_68]
0x18000c38d  call    ??$_Traits_rfind_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_rfind_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x18000c392  mov     rsi, rax
0x18000c395  mov     r9, rax
0x18000c398  xor     r8d, r8d
0x18000c39b  lea     rdx, [rbp+57h+var_38]
0x18000c39f  lea     rcx, [rbp+57h+pszPath]
0x18000c3a3  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18000c3a8  mov     rdi, rax
0x18000c3ab  lea     rax, [rbp+57h+pszPath]
0x18000c3af  cmp     rax, rdi
0x18000c3b2  jz      short loc_18000C3E1
0x18000c3b4  lea     rcx, [rbp+57h+pszPath]
0x18000c3b8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c3bd  movups  xmm0, xmmword ptr [rdi]
0x18000c3c0  movups  xmmword ptr [rbp+57h+pszPath], xmm0
0x18000c3c4  movups  xmm1, xmmword ptr [rdi+10h]
0x18000c3c8  movups  [rbp+57h+var_68], xmm1
0x18000c3cc  mov     qword ptr [rdi+10h], 0
0x18000c3d4  mov     qword ptr [rdi+18h], 7
0x18000c3dc  xor     ecx, ecx
0x18000c3de  mov     [rdi], cx
0x18000c3e1  lea     rcx, [rbp+57h+var_38]
0x18000c3e5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000c3ea  lea     rcx, [rbp+57h+pszPath]
0x18000c3ee  cmp     qword ptr [rbp+57h+var_68+8], 7
0x18000c3f3  cmova   rcx, [rbp+57h+pszPath]; pszPath
0x18000c3f8  call    cs:__imp_PathFileExistsW
0x18000c3fe  test    eax, eax
0x18000c400  jz      loc_18000C367
0x18000c406  lea     rcx, [rbp+57h+pszPath]
0x18000c40a  cmp     qword ptr [rbp+57h+var_68+8], 7
0x18000c40f  cmova   rcx, [rbp+57h+pszPath]; pszPath
0x18000c414  call    cs:__imp_PathIsNetworkPathW
0x18000c41a  test    eax, eax
0x18000c41c  jnz     loc_18000C367
0x18000c422  lea     rcx, [rbp+57h+pszPath]
0x18000c426  call    ?ShouldScanInstallDirectoryForFiles@Utility@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Utility::ShouldScanInstallDirectoryForFiles(std::wstring const &)
0x18000c42b  test    al, al
0x18000c42d  jz      short loc_18000C44A
0x18000c42f  lea     rdx, [rbp+57h+pszPath]
0x18000c433  lea     rcx, [rbp+57h+var_58]
0x18000c437  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000c43c  lea     rdx, [rbp+57h+var_58]
0x18000c440  mov     rcx, rbx
0x18000c443  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18000c448  jmp     short loc_18000C453
0x18000c44a  mov     rcx, rbx
0x18000c44d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000c452  nop
0x18000c453  lea     rcx, [rbp+57h+pszPath]
0x18000c457  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000c45c  nop
0x18000c45d  lea     rcx, [rbp+57h+var_58]
0x18000c461  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000c466  mov     rax, rbx
0x18000c469  mov     rcx, [rbp+57h+var_18]
0x18000c46d  xor     rcx, rsp; StackCookie
0x18000c470  call    __security_check_cookie
0x18000c475  mov     rbx, [rsp+0B0h+arg_10]
0x18000c47d  add     rsp, 0A0h
0x18000c484  pop     rdi
0x18000c485  pop     rsi
0x18000c486  pop     rbp
0x18000c487  retn
```
