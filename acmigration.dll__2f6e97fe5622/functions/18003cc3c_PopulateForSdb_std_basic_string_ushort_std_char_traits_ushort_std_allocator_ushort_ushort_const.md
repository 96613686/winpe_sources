# PopulateForSdb(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ushort const *)

- ea: `0x18003cc3c`
- end: `0x18003d079`
- name: `?PopulateForSdb@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z`
- size: `1085`
- prototype: `__int64 __fastcall(void *Src, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003ca80`

## callees

- `0x180001cf0`
- `0x18000a51c`
- `0x18000a654`
- `0x18000e064`
- `0x18003cc3c`
- `0x1800543c0`
- `0x180065120`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18003cf0c`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18003cf0c`
- `KERNEL32!GetLastError` at `0x18003d010`
- `KERNEL32!GetLastError` at `0x18003d010`
- `ADVAPI32!RegEnumKeyW` at `0x18003cd7c`
- `ADVAPI32!RegEnumKeyW` at `0x18003cf8f`
- `ADVAPI32!RegEnumKeyW` at `0x18003cd7c`
- `ADVAPI32!RegEnumKeyW` at `0x18003cf8f`
- `ADVAPI32!RegCloseKey` at `0x18003cfb0`
- `ADVAPI32!RegCloseKey` at `0x18003cfb0`
- `ADVAPI32!RegGetValueW` at `0x18003cddb`
- `ADVAPI32!RegGetValueW` at `0x18003ceb9`
- `ADVAPI32!RegGetValueW` at `0x18003cddb`
- `ADVAPI32!RegGetValueW` at `0x18003ceb9`
- `ADVAPI32!RegOpenKeyExW` at `0x18003cd2c`
- `ADVAPI32!RegOpenKeyExW` at `0x18003cd2c`
- `SHLWAPI!PathUnExpandEnvStringsW` at `0x18003cef2`
- `SHLWAPI!PathUnExpandEnvStringsW` at `0x18003cef2`

## string_xrefs

- `0x18003cc9e`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates\`
- `0x18003cd51`: `[MergeSdbShim] Failed to open regkey [%x]`
- `0x18003ce3a`: `                    <pattern type="Registry">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates\%ls [%ls]</pattern>\n                    <pattern type="Registry">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates\%ls\%ls [*]</pattern>\n`
- `0x18003ce89`: `FilePath`
- `0x18003cf17`: `[MergeSdbShim] File path had no backslash [%x]`

## pseudocode

```c
__int64 __fastcall PopulateForSdb(void *Src, STRSAFE_LPCWSTR pszSrc)
{
  wchar_t *v4; // r8
  __int64 v5; // rax
  const wchar_t *v6; // rcx
  __int64 v7; // rdx
  wchar_t *v8; // rcx
  signed int v9; // ebx
  LSTATUS v10; // eax
  const char *v11; // r9
  __int64 v12; // r8
  int v13; // esi
  LSTATUS ValueW; // eax
  LSTATUS v15; // eax
  wchar_t *v16; // rax
  HRESULT v17; // eax
  signed int LastError; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pdwType[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t pszDest[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR pszBuf[264]; // [rsp+480h] [rbp+380h] BYREF
  wchar_t String1[832]; // [rsp+690h] [rbp+590h] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  pdwType[0] = 0;
  pcbData = 0;
  v4 = pszDest;
  v5 = 2147483646;
  v6 = L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates\\";
  v7 = 260;
  do
  {
    if ( !v5 )
      break;
    if ( !*v6 )
      break;
    *v4++ = *v6++;
    --v5;
    --v7;
  }
  while ( v7 );
  v8 = v4 - 1;
  v9 = v7 == 0 ? 0x8007007A : 0;
  if ( v7 )
    v8 = v4;
  *v8 = 0;
  if ( v7 )
  {
    v9 = StringCchCatW(pszDest, 0x104u, pszSrc);
    if ( v9 >= 0 )
    {
      v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0x20019u, &hKey);
      v9 = v10;
      if ( v10 )
      {
        if ( (unsigned int)(v10 - 2) > 1 )
        {
          if ( v10 > 0 )
            v9 = (unsigned __int16)v10 | 0x80070000;
          v11 = "[MergeSdbShim] Failed to open regkey [%x]";
          v12 = 94;
LABEL_49:
          LODWORD(phkResult) = v9;
          AslLogCallPrintf(1, "PopulateForSdb", v12, v11, phkResult);
          goto LABEL_34;
        }
      }
      else
      {
        v13 = 0;
        v9 = RegEnumKeyW(hKey, 0, Name, 0x104u);
        if ( v9 != 259 )
        {
          while ( !v9 )
          {
            pcbData = 1662;
            ValueW = RegGetValueW(hKey, Name, L"MergeInputType", 2u, pdwType, String1, &pcbData);
            v9 = ValueW;
            if ( ValueW )
            {
              if ( (unsigned int)(ValueW - 2) > 1 )
              {
                if ( ValueW > 0 )
                  v9 = (unsigned __int16)ValueW | 0x80070000;
                v11 = "[MergeSdbShim] Failed to get regvalue [%x]";
                v12 = 119;
                goto LABEL_49;
              }
            }
            else if ( !wcscmp_0(String1, L"CandidateMergeSdbAdditions") )
            {
              v9 = StringCchPrintfW(
                     String1,
                     0x33Fu,
                     L"                    <pattern type=\"Registry\">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersio"
                      "n\\AppCompatFlags\\SdbUpdates\\%ls [%ls]</pattern>\r\n"
                      "                    <pattern type=\"Registry\">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersi"
                      "on\\AppCompatFlags\\SdbUpdates\\%ls\\%ls [*]</pattern>\r\n",
                     pszSrc,
                     Name,
                     pszSrc,
                     Name);
              if ( v9 < 0 )
              {
                v11 = "[MergeSdbShim] Failed to print reg data [%x]";
                v12 = 128;
                goto LABEL_49;
              }
              std::wstring::append(Src, String1);
              pcbData = 1662;
              v15 = RegGetValueW(hKey, Name, L"FilePath", 2u, pdwType, String1, &pcbData);
              if ( v15 )
              {
                if ( (unsigned int)(v15 - 2) > 1 )
                {
                  if ( v15 > 0 )
                    v9 = (unsigned __int16)v15 | 0x80070000;
                  else
                    v9 = v15;
                  v11 = "[MergeSdbShim] Failed to get regvalue [%x]";
                  v12 = 143;
                  goto LABEL_49;
                }
              }
              else
              {
                if ( !PathUnExpandEnvStringsW(String1, pszBuf, 0x104u) )
                {
                  LastError = GetLastError();
                  v9 = LastError;
                  if ( LastError > 0 )
                    v9 = (unsigned __int16)LastError | 0x80070000;
                  v11 = "[MergeSdbShim] Failed to unexpand env strings [%x]";
                  v12 = 154;
                  if ( v9 >= 0 )
                    v9 = -2147467259;
                  goto LABEL_49;
                }
                v16 = wcsrchr(pszBuf, 0x5Cu);
                if ( v16 )
                {
                  *v16 = 0;
                  v17 = StringCchPrintfW(
                          String1,
                          0x33Fu,
                          L"                    <pattern type=\"File\">%ls [%ls]</pattern>\r\n",
                          pszBuf,
                          v16 + 1);
                  v9 = v17;
                  if ( v17 < 0 )
                  {
                    LODWORD(phkResult) = v17;
                    AslLogCallPrintf(
                      1,
                      "PopulateForSdb",
                      170,
                      "[MergeSdbShim] Failed to print file data [%x]",
                      phkResult);
                    goto LABEL_34;
                  }
                  std::wstring::append(Src, String1);
                }
                else
                {
                  AslLogCallPrintf(1, "PopulateForSdb", 160, "[MergeSdbShim] File path had no backslash [%x]", v9);
                }
              }
            }
            v9 = RegEnumKeyW(hKey, ++v13, Name, 0x104u);
            if ( v9 == 259 )
              goto LABEL_33;
          }
          if ( v9 > 0 )
            v9 = (unsigned __int16)v9 | 0x80070000;
          v11 = "[MergeSdbShim] Failed to enum regkey [%x]";
          v12 = 106;
          goto LABEL_49;
        }
      }
LABEL_33:
      v9 = 0;
    }
  }
LABEL_34:
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(hKey);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003cc3c  mov     [rsp-8+arg_10], rbx
0x18003cc41  push    rbp
0x18003cc42  push    rsi
0x18003cc43  push    rdi
0x18003cc44  push    r12
0x18003cc46  push    r13
0x18003cc48  push    r14
0x18003cc4a  push    r15
0x18003cc4c  lea     rbp, [rsp-0C20h]
0x18003cc54  sub     rsp, 0D20h
0x18003cc5b  mov     rax, cs:__security_cookie
0x18003cc62  xor     rax, rsp
0x18003cc65  mov     [rbp+0C50h+var_40], rax
0x18003cc6c  xor     r12d, r12d
0x18003cc6f  mov     [rsp+0D50h+hKey], 0FFFFFFFFFFFFFFFFh
0x18003cc78  mov     edi, 104h
0x18003cc7d  mov     [rsp+0D50h+pdwType], r12d
0x18003cc82  mov     r14, rdx
0x18003cc85  mov     [rsp+0D50h+var_D10], r12d
0x18003cc8a  mov     r15, rcx
0x18003cc8d  lea     r8, [rbp+0C50h+pszDest]
0x18003cc94  lea     r13d, [r12+1]
0x18003cc99  mov     eax, 7FFFFFFEh
0x18003cc9e  lea     rcx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003cca5  mov     edx, edi
0x18003cca7  test    rax, rax
0x18003ccaa  jz      short loc_18003CCCA
0x18003ccac  movzx   r9d, word ptr [rcx]
0x18003ccb0  test    r9w, r9w
0x18003ccb4  jz      short loc_18003CCCA
0x18003ccb6  mov     [r8], r9w
0x18003ccba  add     rcx, 2
0x18003ccbe  add     r8, 2
0x18003ccc2  sub     rax, r13
0x18003ccc5  sub     rdx, r13
0x18003ccc8  jnz     short loc_18003CCA7
0x18003ccca  mov     rax, rdx
0x18003cccd  lea     rcx, [r8-2]
0x18003ccd1  neg     rax
0x18003ccd4  sbb     ebx, ebx
0x18003ccd6  not     ebx
0x18003ccd8  and     ebx, 8007007Ah
0x18003ccde  test    rdx, rdx
0x18003cce1  cmovnz  rcx, r8
0x18003cce5  mov     [rcx], r12w
0x18003cce9  jz      loc_18003CFA5
0x18003ccef  mov     r8, r14; pszSrc
0x18003ccf2  lea     rcx, [rbp+0C50h+pszDest]; pszDest
0x18003ccf9  mov     rdx, rdi; cchDest
0x18003ccfc  call    StringCchCatW
0x18003cd01  mov     ebx, eax
0x18003cd03  test    eax, eax
0x18003cd05  js      loc_18003CFA5
0x18003cd0b  lea     rax, [rsp+0D50h+hKey]
0x18003cd10  mov     r9d, 20019h; samDesired
0x18003cd16  xor     r8d, r8d; ulOptions
0x18003cd19  mov     [rsp+0D50h+phkResult], rax; phkResult
0x18003cd1e  lea     rdx, [rbp+0C50h+pszDest]; lpSubKey
0x18003cd25  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003cd2c  call    cs:__imp_RegOpenKeyExW
0x18003cd32  mov     ebx, eax
0x18003cd34  test    eax, eax
0x18003cd36  jz      short loc_18003CD6A
0x18003cd38  add     eax, 0FFFFFFFEh
0x18003cd3b  cmp     eax, r13d
0x18003cd3e  jbe     loc_18003CFA2
0x18003cd44  test    ebx, ebx
0x18003cd46  jle     short loc_18003CD51
0x18003cd48  movzx   ebx, bx
0x18003cd4b  or      ebx, 80070000h
0x18003cd51  lea     r9, aMergesdbshimFa; "[MergeSdbShim] Failed to open regkey [%"...
0x18003cd58  mov     r8d, 5Eh ; '^'
0x18003cd5e  lea     rdx, aPopulateforsdb; "PopulateForSdb"
0x18003cd65  jmp     loc_18003D068
0x18003cd6a  mov     rcx, [rsp+0D50h+hKey]; hKey
0x18003cd6f  lea     r8, [rsp+0D50h+Name]; lpName
0x18003cd74  mov     r9d, edi; cchName
0x18003cd77  xor     edx, edx; dwIndex
0x18003cd79  mov     esi, r12d
0x18003cd7c  call    cs:__imp_RegEnumKeyW
0x18003cd82  mov     ebx, eax
0x18003cd84  cmp     eax, 103h
0x18003cd89  jz      loc_18003CFA2
0x18003cd8f  lea     rdi, aPopulateforsdb; "PopulateForSdb"
0x18003cd96  test    ebx, ebx
0x18003cd98  jnz     loc_18003D04D
0x18003cd9e  mov     rcx, [rsp+0D50h+hKey]; hkey
0x18003cda3  lea     rax, [rsp+0D50h+var_D10]
0x18003cda8  mov     [rsp+0D50h+pcbData], rax; pcbData
0x18003cdad  lea     r9d, [rbx+2]; dwFlags
0x18003cdb1  lea     rax, [rbp+0C50h+String1]
0x18003cdb8  mov     [rsp+0D50h+var_D10], 67Eh
0x18003cdc0  mov     [rsp+0D50h+pvData], rax; pvData
0x18003cdc5  lea     r8, aMergeinputtype; "MergeInputType"
0x18003cdcc  lea     rax, [rsp+0D50h+pdwType]
0x18003cdd1  lea     rdx, [rsp+0D50h+Name]; lpSubKey
0x18003cdd6  mov     [rsp+0D50h+phkResult], rax; pdwType
0x18003cddb  call    cs:__imp_RegGetValueW
0x18003cde1  mov     ebx, eax
0x18003cde3  test    eax, eax
0x18003cde5  jz      short loc_18003CE12
0x18003cde7  add     eax, 0FFFFFFFEh
0x18003cdea  cmp     eax, r13d
0x18003cded  jbe     loc_18003CF7A
0x18003cdf3  test    ebx, ebx
0x18003cdf5  jle     short loc_18003CE00
0x18003cdf7  movzx   ebx, bx
0x18003cdfa  or      ebx, 80070000h
0x18003ce00  lea     r9, aMergesdbshimFa_3; "[MergeSdbShim] Failed to get regvalue ["...
0x18003ce07  mov     r8d, 77h ; 'w'
0x18003ce0d  jmp     loc_18003D065
0x18003ce12  lea     rdx, aCandidatemerge; "CandidateMergeSdbAdditions"
0x18003ce19  lea     rcx, [rbp+0C50h+String1]; String1
0x18003ce20  call    wcscmp_0
0x18003ce25  test    eax, eax
0x18003ce27  jnz     loc_18003CF7A
0x18003ce2d  lea     rax, [rsp+0D50h+Name]
0x18003ce32  mov     r9, r14
0x18003ce35  mov     [rsp+0D50h+pcbData], rax
0x18003ce3a  lea     r8, aPatternTypeReg; "                    <pattern type=\"Reg"...
0x18003ce41  lea     rax, [rsp+0D50h+Name]
0x18003ce46  mov     [rsp+0D50h+pvData], r14
0x18003ce4b  mov     edx, 33Fh; cchDest
0x18003ce50  mov     [rsp+0D50h+phkResult], rax
0x18003ce55  lea     rcx, [rbp+0C50h+String1]; pszDest
0x18003ce5c  call    StringCchPrintfW
0x18003ce61  mov     ebx, eax
0x18003ce63  test    eax, eax
0x18003ce65  js      loc_18003D03E
0x18003ce6b  lea     rdx, [rbp+0C50h+String1]; void *
0x18003ce72  mov     rcx, r15; Src
0x18003ce75  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18003ce7a  mov     rcx, [rsp+0D50h+hKey]; hkey
0x18003ce7f  lea     rax, [rsp+0D50h+var_D10]
0x18003ce84  mov     [rsp+0D50h+pcbData], rax; pcbData
0x18003ce89  lea     r8, aFilepath; "FilePath"
0x18003ce90  lea     rax, [rbp+0C50h+String1]
0x18003ce97  mov     [rsp+0D50h+var_D10], 67Eh
0x18003ce9f  mov     [rsp+0D50h+pvData], rax; pvData
0x18003cea4  lea     rdx, [rsp+0D50h+Name]; lpSubKey
0x18003cea9  lea     rax, [rsp+0D50h+pdwType]
0x18003ceae  mov     r9d, 2; dwFlags
0x18003ceb4  mov     [rsp+0D50h+phkResult], rax; pdwType
0x18003ceb9  call    cs:__imp_RegGetValueW
0x18003cebf  test    eax, eax
0x18003cec1  jz      short loc_18003CEDE
0x18003cec3  lea     ecx, [rax-2]
0x18003cec6  cmp     ecx, r13d
0x18003cec9  jbe     loc_18003CF7A
0x18003cecf  test    eax, eax
0x18003ced1  jg      loc_18003CFE2
0x18003ced7  mov     ebx, eax
0x18003ced9  jmp     loc_18003CFEB
0x18003cede  mov     r8d, 104h; cchBuf
0x18003cee4  lea     rdx, [rbp+0C50h+pszBuf]; pszBuf
0x18003ceeb  lea     rcx, [rbp+0C50h+String1]; pszPath
0x18003cef2  call    cs:__imp_PathUnExpandEnvStringsW
0x18003cef8  test    eax, eax
0x18003cefa  jz      loc_18003D010
0x18003cf00  mov     edx, 5Ch ; '\'; Ch
0x18003cf05  lea     rcx, [rbp+0C50h+pszBuf]; Str
0x18003cf0c  call    cs:__imp_wcsrchr
0x18003cf12  test    rax, rax
0x18003cf15  jnz     short loc_18003CF35
0x18003cf17  lea     r9, aMergesdbshimFi; "[MergeSdbShim] File path had no backsla"...
0x18003cf1e  mov     dword ptr [rsp+0D50h+phkResult], ebx
0x18003cf22  mov     r8d, 0A0h
0x18003cf28  mov     rdx, rdi
0x18003cf2b  mov     ecx, r13d
0x18003cf2e  call    AslLogCallPrintf
0x18003cf33  jmp     short loc_18003CF7A
0x18003cf35  mov     [rax], r12w
0x18003cf39  lea     r9, [rbp+0C50h+pszBuf]
0x18003cf40  add     rax, 2
0x18003cf44  lea     r8, aPatternTypeFil; "                    <pattern type=\"Fil"...
0x18003cf4b  mov     edx, 33Fh; cchDest
0x18003cf50  mov     [rsp+0D50h+phkResult], rax
0x18003cf55  lea     rcx, [rbp+0C50h+String1]; pszDest
0x18003cf5c  call    StringCchPrintfW
0x18003cf61  mov     ebx, eax
0x18003cf63  test    eax, eax
0x18003cf65  js      loc_18003CFFA
0x18003cf6b  lea     rdx, [rbp+0C50h+String1]; void *
0x18003cf72  mov     rcx, r15; Src
0x18003cf75  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18003cf7a  mov     rcx, [rsp+0D50h+hKey]; hKey
0x18003cf7f  lea     r8, [rsp+0D50h+Name]; lpName
0x18003cf84  add     esi, r13d
0x18003cf87  mov     r9d, 104h; cchName
0x18003cf8d  mov     edx, esi; dwIndex
0x18003cf8f  call    cs:__imp_RegEnumKeyW
0x18003cf95  mov     ebx, eax
0x18003cf97  cmp     eax, 103h
0x18003cf9c  jnz     loc_18003CD96
0x18003cfa2  mov     ebx, r12d
0x18003cfa5  mov     rcx, [rsp+0D50h+hKey]; hKey
0x18003cfaa  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003cfae  jz      short loc_18003CFB6
0x18003cfb0  call    cs:__imp_RegCloseKey
0x18003cfb6  mov     eax, ebx
0x18003cfb8  mov     rcx, [rbp+0C50h+var_40]
0x18003cfbf  xor     rcx, rsp; StackCookie
0x18003cfc2  call    __security_check_cookie
0x18003cfc7  mov     rbx, [rsp+0D50h+arg_10]
0x18003cfcf  add     rsp, 0D20h
0x18003cfd6  pop     r15
0x18003cfd8  pop     r14
0x18003cfda  pop     r13
0x18003cfdc  pop     r12
0x18003cfde  pop     rdi
0x18003cfdf  pop     rsi
0x18003cfe0  pop     rbp
0x18003cfe1  retn
0x18003cfe2  movzx   ebx, ax
0x18003cfe5  or      ebx, 80070000h
0x18003cfeb  lea     r9, aMergesdbshimFa_3; "[MergeSdbShim] Failed to get regvalue ["...
0x18003cff2  mov     r8d, 8Fh
0x18003cff8  jmp     short loc_18003D065
0x18003cffa  mov     dword ptr [rsp+0D50h+phkResult], eax
0x18003cffe  lea     r9, aMergesdbshimFa_4; "[MergeSdbShim] Failed to print file dat"...
0x18003d005  mov     r8d, 0AAh
0x18003d00b  mov     rdx, rdi
0x18003d00e  jmp     short loc_18003D06C
0x18003d010  call    cs:__imp_GetLastError
0x18003d016  mov     ebx, eax
0x18003d018  test    eax, eax
0x18003d01a  jle     short loc_18003D025
0x18003d01c  movzx   ebx, ax
0x18003d01f  or      ebx, 80070000h
0x18003d025  test    ebx, ebx
0x18003d027  lea     r9, aMergesdbshimFa_0; "[MergeSdbShim] Failed to unexpand env s"...
0x18003d02e  mov     eax, 80004005h
0x18003d033  mov     r8d, 9Ah
0x18003d039  cmovns  ebx, eax
0x18003d03c  jmp     short loc_18003D065
0x18003d03e  lea     r9, aMergesdbshimFa_7; "[MergeSdbShim] Failed to print reg data"...
0x18003d045  mov     r8d, 80h
0x18003d04b  jmp     short loc_18003D065
0x18003d04d  jle     short loc_18003D058
0x18003d04f  movzx   ebx, bx
0x18003d052  or      ebx, 80070000h
0x18003d058  lea     r9, aMergesdbshimFa_6; "[MergeSdbShim] Failed to enum regkey [%"...
0x18003d05f  mov     r8d, 6Ah ; 'j'
0x18003d065  mov     rdx, rdi
0x18003d068  mov     dword ptr [rsp+0D50h+phkResult], ebx
0x18003d06c  mov     ecx, r13d
0x18003d06f  call    AslLogCallPrintf
0x18003d074  jmp     loc_18003CFA5
```
