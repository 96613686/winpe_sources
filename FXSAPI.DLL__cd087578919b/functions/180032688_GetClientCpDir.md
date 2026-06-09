# GetClientCpDir

- ea: `0x180032688`
- end: `0x180032916`
- name: `GetClientCpDir`
- size: `654`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800312c4`

## callees

- `0x180008374`
- `0x180008438`
- `0x18002c42c`
- `0x18002d0e4`
- `0x18002d854`
- `0x180032688`
- `0x180033184`
- `0x18003d4ca`
- `0x18003d510`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800328e0`
- `KERNEL32!SetLastError` at `0x1800328e0`
- `KERNEL32!GetLastError` at `0x18003280b`
- `KERNEL32!GetLastError` at `0x18003280b`
- `ADVAPI32!RegQueryValueExW` at `0x180032755`
- `ADVAPI32!RegQueryValueExW` at `0x180032755`
- `ADVAPI32!RegCloseKey` at `0x180032766`
- `ADVAPI32!RegCloseKey` at `0x180032766`
- `SHELL32!SHSetLocalizedName` at `0x1800328be`
- `SHELL32!SHSetLocalizedName` at `0x1800328be`
- `SHELL32!SHGetFolderPathAndSubDirW` at `0x18003289a`
- `SHELL32!SHGetFolderPathAndSubDirW` at `0x18003289a`

## string_xrefs

- `0x180032819`: `GetSpecialPath failed err=%ld`
- `0x1800328b0`: `%SystemRoot%\system32\fxsresm.dll`

## pseudocode

```c
__int64 __fastcall GetClientCpDir(unsigned __int16 *a1)
{
  HKEY v2; // rbx
  LSTATUS v3; // esi
  const unsigned __int16 *v4; // rbx
  BYTE *v5; // rax
  __int64 v6; // rdx
  HRESULT v7; // eax
  DWORD LastError; // eax
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData[3]; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int16 Data[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszPath[264]; // [rsp+250h] [rbp+150h] BYREF
  unsigned __int16 v14[264]; // [rsp+460h] [rbp+360h] BYREF

  memset_0(v14, 0, 0x20Au);
  memset_0(Data, 0, 0x20Au);
  memset_0(pszPath, 0, 0x208u);
  cbData[0] = 522;
  Type = 0;
  if ( !a1 )
    return 0;
  *a1 = 0;
  v2 = (HKEY)OpenRegistryKey(-2147483647, L"Software\\Microsoft\\Fax\\Setup", 1, 1);
  if ( !v2 )
    return 0;
  v3 = RegQueryValueExW(v2, L"CoverPageDir", 0, &Type, (LPBYTE)Data, cbData);
  RegCloseKey(v2);
  if ( v3 )
  {
    if ( v3 == 2 )
    {
      v4 = L"\\Fax\\Personal Coverpages\\";
LABEL_13:
      if ( !(unsigned int)GetSpecialPath(5, v14) )
      {
        LastError = GetLastError();
        fax_dprintf(L"GetSpecialPath failed err=%ld", LastError);
        return 0;
      }
      v7 = StringCchCopyW(a1, 0x104u, v14);
      if ( v7 >= 0 )
      {
        if ( *v4 == 92 || (v7 = StringCchCatW(a1, 0x104u, L"\\"), v7 >= 0) )
        {
          v7 = StringCchCatW(a1, 0x104u, v4);
          if ( v7 >= 0 )
          {
            v7 = SHGetFolderPathAndSubDirW(0, 32773, 0, 0, L"\\Fax\\Personal CoverPages", pszPath);
            if ( v7 >= 0 )
            {
              v7 = SHSetLocalizedName(pszPath, L"%SystemRoot%\\system32\\fxsresm.dll", 2365);
              if ( v7 >= 0 )
              {
                MakeDirectory(a1);
                return 1;
              }
            }
          }
        }
      }
LABEL_22:
      SetLastError((unsigned __int16)v7);
    }
  }
  else if ( Type - 1 <= 1 )
  {
    v5 = (BYTE *)Data;
    v6 = 261;
    do
    {
      if ( !*(_WORD *)v5 )
        break;
      v5 += 2;
      --v6;
    }
    while ( v6 );
    v4 = Data;
    if ( v6 )
    {
      if ( *((_WORD *)&cbData[2] + ((261 - v6) & -(__int64)(v6 != 0)) + 1) != 92 )
      {
        v7 = StringCchCatW(Data, 0x105u, L"\\");
        if ( v7 < 0 )
          goto LABEL_22;
      }
    }
    goto LABEL_13;
  }
  return 0;
}

```

## disassembly

```asm
0x180032688  mov     [rsp-8+arg_8], rbx
0x18003268d  mov     [rsp-8+arg_10], rsi
0x180032692  push    rbp
0x180032693  push    rdi
0x180032694  push    r14
0x180032696  lea     rbp, [rsp-580h]
0x18003269e  sub     rsp, 680h
0x1800326a5  mov     rax, cs:__security_cookie
0x1800326ac  xor     rax, rsp
0x1800326af  mov     [rbp+590h+var_20], rax
0x1800326b6  mov     rdi, rcx
0x1800326b9  mov     ebx, 20Ah
0x1800326be  mov     r8d, ebx; Size
0x1800326c1  lea     rcx, [rbp+590h+var_230]; void *
0x1800326c8  xor     edx, edx; Val
0x1800326ca  call    memset_0
0x1800326cf  mov     r8d, ebx; Size
0x1800326d2  lea     rcx, [rsp+690h+Data]; void *
0x1800326d7  xor     edx, edx; Val
0x1800326d9  call    memset_0
0x1800326de  xor     edx, edx; Val
0x1800326e0  lea     r8d, [rbx-2]; Size
0x1800326e4  lea     rcx, [rbp+590h+pszPath]; void *
0x1800326eb  call    memset_0
0x1800326f0  xor     r14d, r14d
0x1800326f3  mov     [rsp+690h+cbData], ebx
0x1800326f7  mov     [rsp+690h+Type], r14d
0x1800326fc  test    rdi, rdi
0x1800326ff  jz      loc_1800328EC
0x180032705  lea     r9d, [r14+1]
0x180032709  mov     [rdi], r14w
0x18003270d  mov     r8d, r9d
0x180032710  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Fax\\Setup"
0x180032717  mov     rcx, 0FFFFFFFF80000001h
0x18003271e  call    OpenRegistryKey
0x180032723  mov     rbx, rax
0x180032726  test    rax, rax
0x180032729  jz      loc_1800328EC
0x18003272f  lea     rax, [rsp+690h+cbData]
0x180032734  xor     r8d, r8d; lpReserved
0x180032737  mov     [rsp+690h+lpcbData], rax; lpcbData
0x18003273c  lea     r9, [rsp+690h+Type]; lpType
0x180032741  lea     rax, [rsp+690h+Data]
0x180032746  mov     rcx, rbx; hKey
0x180032749  lea     rdx, aCoverpagedir; "CoverPageDir"
0x180032750  mov     [rsp+690h+lpData], rax; lpData
0x180032755  call    cs:__imp_RegQueryValueExW
0x18003275c  nop     dword ptr [rax+rax+00h]
0x180032761  mov     rcx, rbx; hKey
0x180032764  mov     esi, eax
0x180032766  call    cs:__imp_RegCloseKey
0x18003276d  nop     dword ptr [rax+rax+00h]
0x180032772  test    esi, esi
0x180032774  jz      short loc_180032788
0x180032776  cmp     esi, 2
0x180032779  jnz     loc_1800328EC
0x18003277f  lea     rbx, aFaxPersonalCov_0; "\\Fax\\Personal Coverpages\\"
0x180032786  jmp     short loc_1800327F6
0x180032788  mov     eax, [rsp+690h+Type]
0x18003278c  dec     eax
0x18003278e  cmp     eax, 1
0x180032791  ja      loc_1800328EC
0x180032797  mov     r9d, 105h
0x18003279d  lea     rax, [rsp+690h+Data]
0x1800327a2  mov     edx, r9d
0x1800327a5  cmp     [rax], r14w
0x1800327a9  jz      short loc_1800327B5
0x1800327ab  add     rax, 2
0x1800327af  sub     rdx, 1
0x1800327b3  jnz     short loc_1800327A5
0x1800327b5  mov     rcx, r9
0x1800327b8  lea     rbx, [rsp+690h+Data]
0x1800327bd  sub     rcx, rdx
0x1800327c0  mov     rax, rdx
0x1800327c3  neg     rax
0x1800327c6  sbb     r8, r8
0x1800327c9  and     r8, rcx
0x1800327cc  test    rdx, rdx
0x1800327cf  jz      short loc_1800327F6
0x1800327d1  cmp     [rsp+r8*2+690h+var_652], 5Ch ; '\'
0x1800327d8  jz      short loc_1800327F6
0x1800327da  lea     r8, SubBlock; "\\"
0x1800327e1  mov     rdx, r9; unsigned __int64
0x1800327e4  lea     rcx, [rsp+690h+Data]; unsigned __int16 *
0x1800327e9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800327ee  test    eax, eax
0x1800327f0  js      loc_1800328DD
0x1800327f6  lea     rdx, [rbp+590h+var_230]; unsigned __int16 *
0x1800327fd  mov     ecx, 5; csidl
0x180032802  call    GetSpecialPath
0x180032807  test    eax, eax
0x180032809  jnz     short loc_18003282A
0x18003280b  call    cs:__imp_GetLastError
0x180032812  nop     dword ptr [rax+rax+00h]
0x180032817  mov     edx, eax
0x180032819  lea     rcx, aGetspecialpath; "GetSpecialPath failed err=%ld"
0x180032820  call    fax_dprintf
0x180032825  jmp     loc_1800328EC
0x18003282a  mov     esi, 104h
0x18003282f  lea     r8, [rbp+590h+var_230]; unsigned __int16 *
0x180032836  mov     edx, esi; unsigned __int64
0x180032838  mov     rcx, rdi; unsigned __int16 *
0x18003283b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180032840  test    eax, eax
0x180032842  js      loc_1800328DD
0x180032848  cmp     word ptr [rbx], 5Ch ; '\'
0x18003284c  jz      short loc_180032863
0x18003284e  lea     r8, SubBlock; "\\"
0x180032855  mov     edx, esi; unsigned __int64
0x180032857  mov     rcx, rdi; unsigned __int16 *
0x18003285a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003285f  test    eax, eax
0x180032861  js      short loc_1800328DD
0x180032863  mov     r8, rbx; unsigned __int16 *
0x180032866  mov     rdx, rsi; unsigned __int64
0x180032869  mov     rcx, rdi; unsigned __int16 *
0x18003286c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180032871  test    eax, eax
0x180032873  js      short loc_1800328DD
0x180032875  lea     rax, [rbp+590h+pszPath]
0x18003287c  xor     r9d, r9d; dwFlags
0x18003287f  mov     [rsp+690h+lpcbData], rax; pszPath
0x180032884  xor     r8d, r8d; hToken
0x180032887  lea     rax, pszSubDir; "\\Fax\\Personal CoverPages"
0x18003288e  mov     edx, 8005h; csidl
0x180032893  xor     ecx, ecx; hwnd
0x180032895  mov     [rsp+690h+lpData], rax; pszSubDir
0x18003289a  call    cs:__imp_SHGetFolderPathAndSubDirW
0x1800328a1  nop     dword ptr [rax+rax+00h]
0x1800328a6  test    eax, eax
0x1800328a8  js      short loc_1800328DD
0x1800328aa  mov     r8d, 93Dh; idsRes
0x1800328b0  lea     rdx, pszResModule; "%SystemRoot%\\system32\\fxsresm.dll"
0x1800328b7  lea     rcx, [rbp+590h+pszPath]; pszPath
0x1800328be  call    cs:__imp_SHSetLocalizedName
0x1800328c5  nop     dword ptr [rax+rax+00h]
0x1800328ca  test    eax, eax
0x1800328cc  js      short loc_1800328DD
0x1800328ce  mov     rcx, rdi; unsigned __int16 *
0x1800328d1  call    MakeDirectory
0x1800328d6  mov     eax, 1
0x1800328db  jmp     short loc_1800328EE
0x1800328dd  movzx   ecx, ax; dwErrCode
0x1800328e0  call    cs:__imp_SetLastError
0x1800328e7  nop     dword ptr [rax+rax+00h]
0x1800328ec  xor     eax, eax
0x1800328ee  mov     rcx, [rbp+590h+var_20]
0x1800328f5  xor     rcx, rsp; StackCookie
0x1800328f8  call    __security_check_cookie
0x1800328fd  lea     r11, [rsp+690h+var_10]
0x180032905  mov     rbx, [r11+28h]
0x180032909  mov     rsi, [r11+30h]
0x18003290d  mov     rsp, r11
0x180032910  pop     r14
0x180032912  pop     rdi
0x180032913  pop     rbp
0x180032914  retn
```
