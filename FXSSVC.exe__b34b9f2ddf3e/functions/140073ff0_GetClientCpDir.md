# GetClientCpDir

- ea: `0x140073ff0`
- end: `0x14007424f`
- name: `GetClientCpDir`
- size: `607`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14006e6dc`

## callees

- `0x140002c43`
- `0x140004a30`
- `0x14000c450`
- `0x140066db4`
- `0x1400708c4`
- `0x140071ec8`
- `0x140073ff0`
- `0x140074a48`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400740c3`
- `ADVAPI32!RegCloseKey` at `0x1400740c3`
- `ADVAPI32!RegQueryValueExW` at `0x1400740b8`
- `ADVAPI32!RegQueryValueExW` at `0x1400740b8`
- `KERNEL32!GetLastError` at `0x140074165`
- `KERNEL32!GetLastError` at `0x140074165`
- `KERNEL32!SetLastError` at `0x140074228`
- `KERNEL32!SetLastError` at `0x140074228`
- `SHELL32!SHSetLocalizedName` at `0x14007420c`
- `SHELL32!SHSetLocalizedName` at `0x14007420c`
- `SHELL32!SHGetFolderPathAndSubDirW` at `0x1400741ee`
- `SHELL32!SHGetFolderPathAndSubDirW` at `0x1400741ee`

## string_xrefs

- `0x14007416d`: `GetSpecialPath failed err=%ld`
- `0x1400741fe`: `%SystemRoot%\system32\fxsresm.dll`

## pseudocode

```c
__int64 __fastcall GetClientCpDir(unsigned __int16 *a1)
{
  HKEY v2; // rbx
  LSTATUS v3; // esi
  unsigned __int16 *v4; // rbx
  __int64 v5; // rdx
  BYTE *v6; // rax
  int v7; // eax
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
  v2 = OpenRegistryKey(HKEY_CURRENT_USER, L"Software\\Microsoft\\Fax\\Setup", 1, 1u);
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
      if ( !(unsigned int)GetSpecialPath(5, v14, 0x105u) )
      {
        LastError = GetLastError();
        fax_dprintf(L"GetSpecialPath failed err=%ld", LastError);
        return 0;
      }
      v7 = StringCchCopyW(a1, 0x104u, v14);
      if ( v7 >= 0 )
      {
        if ( *v4 == 92 || (v7 = StringCchCatW(a1, 260, L"\\"), v7 >= 0) )
        {
          v7 = StringCchCatW(a1, 260, v4);
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
    v5 = 261;
    v6 = (BYTE *)Data;
    do
    {
      if ( !*(_WORD *)v6 )
        break;
      v6 += 2;
      --v5;
    }
    while ( v5 );
    v4 = Data;
    if ( v5 )
    {
      if ( *((_WORD *)&cbData[2] + ((261 - v5) & -(__int64)(v5 != 0)) + 1) != 92 )
      {
        v7 = StringCchCatW(Data, 261, L"\\");
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
0x140073ff0  push    rbp
0x140073ff2  push    rbx
0x140073ff3  push    rsi
0x140073ff4  push    rdi
0x140073ff5  push    r12
0x140073ff7  push    r14
0x140073ff9  lea     rbp, [rsp-588h]
0x140074001  sub     rsp, 688h
0x140074008  mov     rax, cs:__security_cookie
0x14007400f  xor     rax, rsp
0x140074012  mov     [rbp+5B0h+var_40], rax
0x140074019  mov     rdi, rcx
0x14007401c  mov     ebx, 20Ah
0x140074021  mov     r8d, ebx; Size
0x140074024  lea     rcx, [rbp+5B0h+var_250]; void *
0x14007402b  xor     edx, edx; Val
0x14007402d  call    memset_0
0x140074032  mov     r8d, ebx; Size
0x140074035  lea     rcx, [rsp+6B0h+Data]; void *
0x14007403a  xor     edx, edx; Val
0x14007403c  call    memset_0
0x140074041  xor     edx, edx; Val
0x140074043  lea     r8d, [rbx-2]; Size
0x140074047  lea     rcx, [rbp+5B0h+pszPath]; void *
0x14007404e  call    memset_0
0x140074053  xor     r14d, r14d
0x140074056  mov     [rsp+6B0h+cbData], ebx
0x14007405a  mov     [rsp+6B0h+Type], r14d
0x14007405f  test    rdi, rdi
0x140074062  jz      loc_14007422E
0x140074068  lea     r9d, [r14+1]
0x14007406c  mov     [rdi], r14w
0x140074070  mov     r8d, r9d
0x140074073  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Fax\\Setup"
0x14007407a  mov     rcx, 0FFFFFFFF80000001h
0x140074081  call    OpenRegistryKey
0x140074086  mov     rbx, rax
0x140074089  test    rax, rax
0x14007408c  jz      loc_14007422E
0x140074092  lea     rax, [rsp+6B0h+cbData]
0x140074097  xor     r8d, r8d; lpReserved
0x14007409a  mov     [rsp+6B0h+lpcbData], rax; lpcbData
0x14007409f  lea     r9, [rsp+6B0h+Type]; lpType
0x1400740a4  lea     rax, [rsp+6B0h+Data]
0x1400740a9  mov     rcx, rbx; hKey
0x1400740ac  lea     rdx, aCoverpagedir; "CoverPageDir"
0x1400740b3  mov     [rsp+6B0h+lpData], rax; lpData
0x1400740b8  call    cs:__imp_RegQueryValueExW
0x1400740be  mov     rcx, rbx; hKey
0x1400740c1  mov     esi, eax
0x1400740c3  call    cs:__imp_RegCloseKey
0x1400740c9  mov     r12d, 105h
0x1400740cf  test    esi, esi
0x1400740d1  jz      short loc_1400740E5
0x1400740d3  cmp     esi, 2
0x1400740d6  jnz     loc_14007422E
0x1400740dc  lea     rbx, aFaxPersonalCov_0; "\\Fax\\Personal Coverpages\\"
0x1400740e3  jmp     short loc_14007414D
0x1400740e5  mov     eax, [rsp+6B0h+Type]
0x1400740e9  dec     eax
0x1400740eb  cmp     eax, 1
0x1400740ee  ja      loc_14007422E
0x1400740f4  mov     rdx, r12
0x1400740f7  lea     rax, [rsp+6B0h+Data]
0x1400740fc  cmp     [rax], r14w
0x140074100  jz      short loc_14007410C
0x140074102  add     rax, 2
0x140074106  sub     rdx, 1
0x14007410a  jnz     short loc_1400740FC
0x14007410c  mov     rcx, r12
0x14007410f  lea     rbx, [rsp+6B0h+Data]
0x140074114  sub     rcx, rdx
0x140074117  mov     rax, rdx
0x14007411a  neg     rax
0x14007411d  sbb     r8, r8
0x140074120  and     r8, rcx
0x140074123  test    rdx, rdx
0x140074126  jz      short loc_14007414D
0x140074128  cmp     [rsp+r8*2+6B0h+var_672], 5Ch ; '\'
0x14007412f  jz      short loc_14007414D
0x140074131  lea     r8, SubBlock; "\\"
0x140074138  mov     rdx, r12; unsigned __int64
0x14007413b  lea     rcx, [rsp+6B0h+Data]; unsigned __int16 *
0x140074140  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140074145  test    eax, eax
0x140074147  js      loc_140074225
0x14007414d  mov     r8d, r12d; unsigned __int64
0x140074150  lea     rdx, [rbp+5B0h+var_250]; unsigned __int16 *
0x140074157  mov     ecx, 5; csidl
0x14007415c  call    GetSpecialPath
0x140074161  test    eax, eax
0x140074163  jnz     short loc_14007417E
0x140074165  call    cs:__imp_GetLastError
0x14007416b  mov     edx, eax
0x14007416d  lea     rcx, aGetspecialpath; "GetSpecialPath failed err=%ld"
0x140074174  call    fax_dprintf
0x140074179  jmp     loc_14007422E
0x14007417e  mov     esi, 104h
0x140074183  lea     r8, [rbp+5B0h+var_250]; unsigned __int16 *
0x14007418a  mov     edx, esi; unsigned __int64
0x14007418c  mov     rcx, rdi; unsigned __int16 *
0x14007418f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140074194  test    eax, eax
0x140074196  js      loc_140074225
0x14007419c  cmp     word ptr [rbx], 5Ch ; '\'
0x1400741a0  jz      short loc_1400741B7
0x1400741a2  lea     r8, SubBlock; "\\"
0x1400741a9  mov     edx, esi; unsigned __int64
0x1400741ab  mov     rcx, rdi; unsigned __int16 *
0x1400741ae  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400741b3  test    eax, eax
0x1400741b5  js      short loc_140074225
0x1400741b7  mov     r8, rbx; unsigned __int16 *
0x1400741ba  mov     rdx, rsi; unsigned __int64
0x1400741bd  mov     rcx, rdi; unsigned __int16 *
0x1400741c0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400741c5  test    eax, eax
0x1400741c7  js      short loc_140074225
0x1400741c9  lea     rax, [rbp+5B0h+pszPath]
0x1400741d0  xor     r9d, r9d; dwFlags
0x1400741d3  mov     [rsp+6B0h+lpcbData], rax; pszPath
0x1400741d8  xor     r8d, r8d; hToken
0x1400741db  lea     rax, pszSubDir; "\\Fax\\Personal CoverPages"
0x1400741e2  mov     edx, 8005h; csidl
0x1400741e7  xor     ecx, ecx; hwnd
0x1400741e9  mov     [rsp+6B0h+lpData], rax; pszSubDir
0x1400741ee  call    cs:__imp_SHGetFolderPathAndSubDirW
0x1400741f4  test    eax, eax
0x1400741f6  js      short loc_140074225
0x1400741f8  mov     r8d, 93Dh; idsRes
0x1400741fe  lea     rdx, pszResModule; "%SystemRoot%\\system32\\fxsresm.dll"
0x140074205  lea     rcx, [rbp+5B0h+pszPath]; pszPath
0x14007420c  call    cs:__imp_SHSetLocalizedName
0x140074212  test    eax, eax
0x140074214  js      short loc_140074225
0x140074216  mov     rcx, rdi; unsigned __int16 *
0x140074219  call    MakeDirectory
0x14007421e  mov     eax, 1
0x140074223  jmp     short loc_140074230
0x140074225  movzx   ecx, ax; dwErrCode
0x140074228  call    cs:__imp_SetLastError
0x14007422e  xor     eax, eax
0x140074230  mov     rcx, [rbp+5B0h+var_40]
0x140074237  xor     rcx, rsp; StackCookie
0x14007423a  call    __security_check_cookie
0x14007423f  add     rsp, 688h
0x140074246  pop     r14
0x140074248  pop     r12
0x14007424a  pop     rdi
0x14007424b  pop     rsi
0x14007424c  pop     rbx
0x14007424d  pop     rbp
0x14007424e  retn
```
