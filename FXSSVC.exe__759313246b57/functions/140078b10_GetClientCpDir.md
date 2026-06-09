# GetClientCpDir

- ea: `0x140078b10`
- end: `0x140078d94`
- name: `GetClientCpDir`
- size: `644`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140072a70`

## callees

- `0x140002c73`
- `0x140004b70`
- `0x14000cae8`
- `0x14006ab10`
- `0x140074f18`
- `0x140076758`
- `0x140078b10`
- `0x1400795e0`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140078be9`
- `ADVAPI32!RegCloseKey` at `0x140078be9`
- `ADVAPI32!RegQueryValueExW` at `0x140078bd8`
- `ADVAPI32!RegQueryValueExW` at `0x140078bd8`
- `KERNEL32!GetLastError` at `0x140078c91`
- `KERNEL32!GetLastError` at `0x140078c91`
- `KERNEL32!SetLastError` at `0x140078d66`
- `KERNEL32!SetLastError` at `0x140078d66`
- `SHELL32!SHSetLocalizedName` at `0x140078d44`
- `SHELL32!SHSetLocalizedName` at `0x140078d44`
- `SHELL32!SHGetFolderPathAndSubDirW` at `0x140078d20`
- `SHELL32!SHGetFolderPathAndSubDirW` at `0x140078d20`

## string_xrefs

- `0x140078c9f`: `GetSpecialPath failed err=%ld`
- `0x140078d36`: `%SystemRoot%\system32\fxsresm.dll`

## pseudocode

```c
__int64 __fastcall GetClientCpDir(unsigned __int16 *a1)
{
  HKEY v2; // rbx
  LSTATUS v3; // esi
  const unsigned __int16 *v4; // rbx
  __int64 v5; // rdx
  BYTE *v6; // rax
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
      if ( !(unsigned int)GetSpecialPath(5, v14, 0x105u) )
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
0x140078b10  push    rbp
0x140078b12  push    rbx
0x140078b13  push    rsi
0x140078b14  push    rdi
0x140078b15  push    r12
0x140078b17  push    r14
0x140078b19  lea     rbp, [rsp-588h]
0x140078b21  sub     rsp, 688h
0x140078b28  mov     rax, cs:__security_cookie
0x140078b2f  xor     rax, rsp
0x140078b32  mov     [rbp+5B0h+var_40], rax
0x140078b39  mov     rdi, rcx
0x140078b3c  mov     ebx, 20Ah
0x140078b41  mov     r8d, ebx; Size
0x140078b44  lea     rcx, [rbp+5B0h+var_250]; void *
0x140078b4b  xor     edx, edx; Val
0x140078b4d  call    memset_0
0x140078b52  mov     r8d, ebx; Size
0x140078b55  lea     rcx, [rsp+6B0h+Data]; void *
0x140078b5a  xor     edx, edx; Val
0x140078b5c  call    memset_0
0x140078b61  xor     edx, edx; Val
0x140078b63  lea     r8d, [rbx-2]; Size
0x140078b67  lea     rcx, [rbp+5B0h+pszPath]; void *
0x140078b6e  call    memset_0
0x140078b73  xor     r14d, r14d
0x140078b76  mov     [rsp+6B0h+cbData], ebx
0x140078b7a  mov     [rsp+6B0h+Type], r14d
0x140078b7f  test    rdi, rdi
0x140078b82  jz      loc_140078D72
0x140078b88  lea     r9d, [r14+1]
0x140078b8c  mov     [rdi], r14w
0x140078b90  mov     r8d, r9d
0x140078b93  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Fax\\Setup"
0x140078b9a  mov     rcx, 0FFFFFFFF80000001h
0x140078ba1  call    OpenRegistryKey
0x140078ba6  mov     rbx, rax
0x140078ba9  test    rax, rax
0x140078bac  jz      loc_140078D72
0x140078bb2  lea     rax, [rsp+6B0h+cbData]
0x140078bb7  xor     r8d, r8d; lpReserved
0x140078bba  mov     [rsp+6B0h+lpcbData], rax; lpcbData
0x140078bbf  lea     r9, [rsp+6B0h+Type]; lpType
0x140078bc4  lea     rax, [rsp+6B0h+Data]
0x140078bc9  mov     rcx, rbx; hKey
0x140078bcc  lea     rdx, aCoverpagedir; "CoverPageDir"
0x140078bd3  mov     [rsp+6B0h+lpData], rax; lpData
0x140078bd8  call    cs:__imp_RegQueryValueExW
0x140078bdf  nop     dword ptr [rax+rax+00h]
0x140078be4  mov     rcx, rbx; hKey
0x140078be7  mov     esi, eax
0x140078be9  call    cs:__imp_RegCloseKey
0x140078bf0  nop     dword ptr [rax+rax+00h]
0x140078bf5  mov     r12d, 105h
0x140078bfb  test    esi, esi
0x140078bfd  jz      short loc_140078C11
0x140078bff  cmp     esi, 2
0x140078c02  jnz     loc_140078D72
0x140078c08  lea     rbx, aFaxPersonalCov_0; "\\Fax\\Personal Coverpages\\"
0x140078c0f  jmp     short loc_140078C79
0x140078c11  mov     eax, [rsp+6B0h+Type]
0x140078c15  dec     eax
0x140078c17  cmp     eax, 1
0x140078c1a  ja      loc_140078D72
0x140078c20  mov     rdx, r12
0x140078c23  lea     rax, [rsp+6B0h+Data]
0x140078c28  cmp     [rax], r14w
0x140078c2c  jz      short loc_140078C38
0x140078c2e  add     rax, 2
0x140078c32  sub     rdx, 1
0x140078c36  jnz     short loc_140078C28
0x140078c38  mov     rcx, r12
0x140078c3b  lea     rbx, [rsp+6B0h+Data]
0x140078c40  sub     rcx, rdx
0x140078c43  mov     rax, rdx
0x140078c46  neg     rax
0x140078c49  sbb     r8, r8
0x140078c4c  and     r8, rcx
0x140078c4f  test    rdx, rdx
0x140078c52  jz      short loc_140078C79
0x140078c54  cmp     [rsp+r8*2+6B0h+var_672], 5Ch ; '\'
0x140078c5b  jz      short loc_140078C79
0x140078c5d  lea     r8, SubBlock; "\\"
0x140078c64  mov     rdx, r12; unsigned __int64
0x140078c67  lea     rcx, [rsp+6B0h+Data]; unsigned __int16 *
0x140078c6c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140078c71  test    eax, eax
0x140078c73  js      loc_140078D63
0x140078c79  mov     r8d, r12d; unsigned __int64
0x140078c7c  lea     rdx, [rbp+5B0h+var_250]; unsigned __int16 *
0x140078c83  mov     ecx, 5; csidl
0x140078c88  call    GetSpecialPath
0x140078c8d  test    eax, eax
0x140078c8f  jnz     short loc_140078CB0
0x140078c91  call    cs:__imp_GetLastError
0x140078c98  nop     dword ptr [rax+rax+00h]
0x140078c9d  mov     edx, eax
0x140078c9f  lea     rcx, aGetspecialpath; "GetSpecialPath failed err=%ld"
0x140078ca6  call    fax_dprintf
0x140078cab  jmp     loc_140078D72
0x140078cb0  mov     esi, 104h
0x140078cb5  lea     r8, [rbp+5B0h+var_250]; unsigned __int16 *
0x140078cbc  mov     edx, esi; unsigned __int64
0x140078cbe  mov     rcx, rdi; unsigned __int16 *
0x140078cc1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140078cc6  test    eax, eax
0x140078cc8  js      loc_140078D63
0x140078cce  cmp     word ptr [rbx], 5Ch ; '\'
0x140078cd2  jz      short loc_140078CE9
0x140078cd4  lea     r8, SubBlock; "\\"
0x140078cdb  mov     edx, esi; unsigned __int64
0x140078cdd  mov     rcx, rdi; unsigned __int16 *
0x140078ce0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140078ce5  test    eax, eax
0x140078ce7  js      short loc_140078D63
0x140078ce9  mov     r8, rbx; unsigned __int16 *
0x140078cec  mov     rdx, rsi; unsigned __int64
0x140078cef  mov     rcx, rdi; unsigned __int16 *
0x140078cf2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140078cf7  test    eax, eax
0x140078cf9  js      short loc_140078D63
0x140078cfb  lea     rax, [rbp+5B0h+pszPath]
0x140078d02  xor     r9d, r9d; dwFlags
0x140078d05  mov     [rsp+6B0h+lpcbData], rax; pszPath
0x140078d0a  xor     r8d, r8d; hToken
0x140078d0d  lea     rax, pszSubDir; "\\Fax\\Personal CoverPages"
0x140078d14  mov     edx, 8005h; csidl
0x140078d19  xor     ecx, ecx; hwnd
0x140078d1b  mov     [rsp+6B0h+lpData], rax; pszSubDir
0x140078d20  call    cs:__imp_SHGetFolderPathAndSubDirW
0x140078d27  nop     dword ptr [rax+rax+00h]
0x140078d2c  test    eax, eax
0x140078d2e  js      short loc_140078D63
0x140078d30  mov     r8d, 93Dh; idsRes
0x140078d36  lea     rdx, pszResModule; "%SystemRoot%\\system32\\fxsresm.dll"
0x140078d3d  lea     rcx, [rbp+5B0h+pszPath]; pszPath
0x140078d44  call    cs:__imp_SHSetLocalizedName
0x140078d4b  nop     dword ptr [rax+rax+00h]
0x140078d50  test    eax, eax
0x140078d52  js      short loc_140078D63
0x140078d54  mov     rcx, rdi; unsigned __int16 *
0x140078d57  call    MakeDirectory
0x140078d5c  mov     eax, 1
0x140078d61  jmp     short loc_140078D74
0x140078d63  movzx   ecx, ax; dwErrCode
0x140078d66  call    cs:__imp_SetLastError
0x140078d6d  nop     dword ptr [rax+rax+00h]
0x140078d72  xor     eax, eax
0x140078d74  mov     rcx, [rbp+5B0h+var_40]
0x140078d7b  xor     rcx, rsp; StackCookie
0x140078d7e  call    __security_check_cookie
0x140078d83  add     rsp, 688h
0x140078d8a  pop     r14
0x140078d8c  pop     r12
0x140078d8e  pop     rdi
0x140078d8f  pop     rsi
0x140078d90  pop     rbx
0x140078d91  pop     rbp
0x140078d92  retn
```
