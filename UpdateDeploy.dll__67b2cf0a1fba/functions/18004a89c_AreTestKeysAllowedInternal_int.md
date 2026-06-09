# AreTestKeysAllowedInternal(int &)

- ea: `0x18004a89c`
- end: `0x18004ac25`
- name: `?AreTestKeysAllowedInternal@@YAJAEAH@Z`
- size: `905`
- prototype: `__int64 __fastcall(int *, unsigned int, __int64, unsigned int *)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001a930`
- `0x18004ac2c`

## callees

- `0x180003180`
- `0x180004170`
- `0x180007b6c`
- `0x18000945c`
- `0x18000970c`
- `0x1800496c4`
- `0x18004a770`
- `0x18004a89c`
- `0x18004aec0`
- `0x18004b014`
- `0x18004bd90`
- `0x18004c26c`
- `0x1800568c4`
- `0x180059dfc`
- `0x18005a5a4`
- `0x180061960`
- `0x180061d54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a96a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a96a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004aa75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004aa75`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004aa1d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004aa1d`

## string_xrefs

- `0x18004a987`: `AlternateTestCabPath`
- `0x18004a95c`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x18004ab4d`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressor.cpp`

## pseudocode

```c
__int64 __fastcall AreTestKeysAllowedInternal(int *a1, unsigned int a2, __int64 a3, unsigned int *a4)
{
  int SusBaseDirectoryW; // ebx
  __int64 v6; // rdx
  __int64 v8; // rcx
  wchar_t **v9; // r9
  wchar_t **v10; // r9
  int LastErrorFailHr; // esi
  __int64 v12; // rdx
  unsigned __int64 v13; // r9
  wil::details *v14; // rcx
  int FileSize; // eax
  __int64 v16; // rdx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // eax
  COutputMemoryFile *v21; // rbx
  int v22; // eax
  COutputMemoryFile *v23; // rdi
  int phkResult; // [rsp+28h] [rbp-E0h]
  unsigned __int64 *phkResulta; // [rsp+28h] [rbp-E0h]
  int phkResultb; // [rsp+28h] [rbp-E0h]
  COutputMemoryFile *v27; // [rsp+68h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-98h] BYREF
  WCHAR FileName[264]; // [rsp+78h] [rbp-90h] BYREF
  wchar_t v30[264]; // [rsp+288h] [rbp+180h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C0h] [rbp+3B8h]

  SusBaseDirectoryW = GetSusBaseDirectoryW(v30, a2, L"\\", a4);
  if ( SusBaseDirectoryW < 0 )
  {
    v6 = 115;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WUTestKeys.cpp",
      (const char *)(unsigned int)SusBaseDirectoryW,
      phkResult);
    return (unsigned int)SusBaseDirectoryW;
  }
  SusBaseDirectoryW = StringCchCopyExW(FileName, 0x104u, v30, 0, 0, 0x100u);
  if ( SusBaseDirectoryW < 0 )
  {
    v6 = 117;
    goto LABEL_3;
  }
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
          0,
          0x20019u,
          &hKey) )
  {
    LODWORD(phkResulta) = 260;
    if ( (int)SafeRegQueryValueCchHelper(v8, hKey, L"AlternateTestCabPath", FileName) < 0 )
      StringCchCopyExW(FileName, 0x104u, v30, 0, 0, 0x100u);
    LastErrorFailHr = StringCchCatExW(FileName, 0x104u, L"\\", v10, phkResulta, 0x100u);
    if ( LastErrorFailHr < 0 )
    {
      v12 = 133;
LABEL_13:
      v13 = (unsigned int)LastErrorFailHr;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WUTestKeys.cpp",
        (const char *)v13,
        (int)phkResulta);
      goto LABEL_19;
    }
  }
  LastErrorFailHr = StringCchCatExW(FileName, 0x104u, L"autest.cab", v9, phkResulta, 0x100u);
  if ( LastErrorFailHr < 0 )
  {
    v12 = 137;
    goto LABEL_13;
  }
  if ( GetFileAttributesW(FileName) != -1
    || (LastErrorFailHr = wil::details::GetLastErrorFailHr(v14), LastErrorFailHr >= 0) )
  {
    v27 = 0;
    FileSize = SusGetFileSize(FileName, (unsigned __int64 *)&v27);
    if ( FileSize >= 0 )
    {
      if ( (unsigned __int64)v27 <= 0x4E20 )
      {
        LODWORD(phkResulta) = 0;
        v17 = VerifyFileTrustImp(FileName, v16, 0);
        LastErrorFailHr = v17;
        if ( v17 >= 0 )
        {
          v27 = 0;
          v20 = DecompressCabFileInternal(v19, v18, FileName, 0);
          LastErrorFailHr = v20;
          v21 = v27;
          if ( v20 >= 0 )
          {
            if ( v27 && *((_DWORD *)v27 + 6) == 1 )
            {
              *((_QWORD *)v27 + 4) = *((_QWORD *)v27 + 1);
              v27 = 0;
              v22 = CSusListIterator<COutputMemoryFile>::Remove(v21, &v27);
              LastErrorFailHr = v22;
              v23 = v27;
              if ( v22 >= 0 )
              {
                *a1 = IsValidAUTestCabFileText(
                        *(_DWORD *)(*((_QWORD *)v27 + 2) + 20LL),
                        *(const char **)(*((_QWORD *)v27 + 2) + 8LL));
                LastErrorFailHr = 0;
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xB0,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WUTestKeys.cpp",
                  (const char *)(unsigned int)v22,
                  0);
              }
              if ( v23 )
              {
                COutputMemoryFile::~COutputMemoryFile(v23);
                operator delete(v23, (const struct std::nothrow_t *)0x120);
              }
            }
            else
            {
              LastErrorFailHr = -2145120257;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x608,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\CabDecompressor.cpp",
              (const char *)(unsigned int)v20,
              0);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA6,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WUTestKeys.cpp",
              (const char *)(unsigned int)LastErrorFailHr,
              phkResultb);
          }
          if ( v21 )
          {
            CSusListIterator<COutputMemoryFile>::~CSusListIterator<COutputMemoryFile>(v21);
            operator delete(v21, (const struct std::nothrow_t *)0x28);
          }
          goto LABEL_19;
        }
        v13 = (unsigned int)v17;
        v12 = 157;
        goto LABEL_25;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x91,
        (int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WUTestKeys.cpp",
        (const char *)(unsigned int)FileSize);
    }
    LastErrorFailHr = -2145120257;
  }
LABEL_19:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)LastErrorFailHr;
}

```

## disassembly

```asm
0x18004a89c  mov     rax, rsp
0x18004a89f  mov     [rax+10h], rbx
0x18004a8a3  mov     [rax+18h], rsi
0x18004a8a7  mov     [rax+20h], rdi
0x18004a8ab  push    rbp
0x18004a8ac  push    r14
0x18004a8ae  push    r15
0x18004a8b0  lea     rbp, [rax-3B8h]
0x18004a8b7  sub     rsp, 4A0h
0x18004a8be  mov     rax, cs:__security_cookie
0x18004a8c5  xor     rax, rsp
0x18004a8c8  mov     [rbp+3B0h+var_20], rax
0x18004a8cf  mov     r14, rcx
0x18004a8d2  lea     r8, SubBlock; "\\"
0x18004a8d9  lea     rcx, [rbp+3B0h+var_230]; wchar_t *
0x18004a8e0  call    ?GetSusBaseDirectoryW@@YAJPEA_WKPEB_WPEAK@Z; GetSusBaseDirectoryW(wchar_t *,ulong,wchar_t const *,ulong *)
0x18004a8e5  mov     ebx, eax
0x18004a8e7  xor     r15d, r15d
0x18004a8ea  test    eax, eax
0x18004a8ec  jns     short loc_18004A90F
0x18004a8ee  lea     edx, [r15+73h]; void *
0x18004a8f2  lea     r8, aCW1SSrcClientL_26; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18004a8f9  mov     r9d, ebx; char *
0x18004a8fc  mov     rcx, [rbp+3B8h]; this
0x18004a903  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a908  mov     eax, ebx
0x18004a90a  jmp     loc_18004AA7D
0x18004a90f  mov     [rsp+4B0h+var_488], 100h; unsigned int
0x18004a917  mov     [rsp+4B0h+phkResult], r15; unsigned __int64 *
0x18004a91c  xor     r9d, r9d; wchar_t **
0x18004a91f  lea     r8, [rbp+3B0h+var_230]; wchar_t *
0x18004a926  mov     edi, 104h
0x18004a92b  mov     edx, edi; unsigned __int64
0x18004a92d  lea     rcx, [rsp+4B0h+FileName]; pszDest
0x18004a932  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18004a937  mov     ebx, eax
0x18004a939  test    eax, eax
0x18004a93b  jns     short loc_18004A944
0x18004a93d  mov     edx, 75h ; 'u'
0x18004a942  jmp     short loc_18004A8F2
0x18004a944  mov     [rsp+4B0h+hKey], r15
0x18004a949  lea     rax, [rsp+4B0h+hKey]
0x18004a94e  mov     [rsp+4B0h+phkResult], rax; int
0x18004a953  mov     r9d, 20019h; samDesired
0x18004a959  xor     r8d, r8d; ulOptions
0x18004a95c  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004a963  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004a96a  call    cs:__imp_RegOpenKeyExW
0x18004a970  test    eax, eax
0x18004a972  jnz     short loc_18004A9E9
0x18004a974  mov     qword ptr [rsp+4B0h+var_480], r15
0x18004a979  mov     qword ptr [rsp+4B0h+var_488], r15
0x18004a97e  mov     dword ptr [rsp+4B0h+phkResult], edi
0x18004a982  lea     r9, [rsp+4B0h+FileName]
0x18004a987  lea     r8, aAlternatetestc; "AlternateTestCabPath"
0x18004a98e  mov     rdx, [rsp+4B0h+hKey]
0x18004a993  call    SafeRegQueryValueCchHelper
0x18004a998  test    eax, eax
0x18004a99a  jns     short loc_18004A9C0
0x18004a99c  mov     [rsp+4B0h+var_488], 100h; unsigned int
0x18004a9a4  mov     [rsp+4B0h+phkResult], r15; unsigned __int64 *
0x18004a9a9  xor     r9d, r9d; wchar_t **
0x18004a9ac  lea     r8, [rbp+3B0h+var_230]; wchar_t *
0x18004a9b3  mov     rdx, rdi; unsigned __int64
0x18004a9b6  lea     rcx, [rsp+4B0h+FileName]; pszDest
0x18004a9bb  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18004a9c0  mov     [rsp+4B0h+var_488], 100h; unsigned int
0x18004a9c8  lea     r8, SubBlock; "\\"
0x18004a9cf  mov     rdx, rdi; unsigned __int64
0x18004a9d2  lea     rcx, [rsp+4B0h+FileName]; pszDest
0x18004a9d7  call    ?StringCchCatExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCatExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18004a9dc  mov     esi, eax
0x18004a9de  test    eax, eax
0x18004a9e0  jns     short loc_18004A9E9
0x18004a9e2  mov     edx, 85h
0x18004a9e7  jmp     short loc_18004AA10
0x18004a9e9  mov     [rsp+4B0h+var_488], 100h; unsigned int
0x18004a9f1  lea     r8, aAutestCab; "autest.cab"
0x18004a9f8  mov     rdx, rdi; unsigned __int64
0x18004a9fb  lea     rcx, [rsp+4B0h+FileName]; pszDest
0x18004aa00  call    ?StringCchCatExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCatExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18004aa05  mov     esi, eax
0x18004aa07  test    eax, eax
0x18004aa09  jns     short loc_18004AA18
0x18004aa0b  mov     edx, 89h
0x18004aa10  mov     r9d, esi
0x18004aa13  jmp     loc_18004AAE5
0x18004aa18  lea     rcx, [rsp+4B0h+FileName]; lpFileName
0x18004aa1d  call    cs:__imp_GetFileAttributesW
0x18004aa23  cmp     eax, 0FFFFFFFFh
0x18004aa26  jnz     short loc_18004AA33
0x18004aa28  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18004aa2d  mov     esi, eax
0x18004aa2f  test    eax, eax
0x18004aa31  js      short loc_18004AA6B
0x18004aa33  mov     [rsp+4B0h+var_450], r15
0x18004aa38  lea     rdx, [rsp+4B0h+var_450]; unsigned __int64 *
0x18004aa3d  lea     rcx, [rsp+4B0h+FileName]; wchar_t *
0x18004aa42  call    ?SusGetFileSize@@YAJPEB_WPEA_K@Z; SusGetFileSize(wchar_t const *,unsigned __int64 *)
0x18004aa47  mov     rcx, [rbp+3B8h]; this
0x18004aa4e  test    eax, eax
0x18004aa50  jns     short loc_18004AAA9
0x18004aa52  mov     r9d, eax; char *
0x18004aa55  lea     r8, aCW1SSrcClientL_26; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18004aa5c  mov     edx, 91h; void *
0x18004aa61  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004aa66  mov     esi, 80240FFFh
0x18004aa6b  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18004aa70  test    rcx, rcx
0x18004aa73  jz      short loc_18004AA7B
0x18004aa75  call    cs:__imp_RegCloseKey
0x18004aa7b  mov     eax, esi
0x18004aa7d  mov     rcx, [rbp+3B0h+var_20]
0x18004aa84  xor     rcx, rsp; StackCookie
0x18004aa87  call    __security_check_cookie
0x18004aa8c  lea     r11, [rsp+4B0h+var_10]
0x18004aa94  mov     rbx, [r11+28h]
0x18004aa98  mov     rsi, [r11+30h]
0x18004aa9c  mov     rdi, [r11+38h]
0x18004aaa0  mov     rsp, r11
0x18004aaa3  pop     r15
0x18004aaa5  pop     r14
0x18004aaa7  pop     rbp
0x18004aaa8  retn
0x18004aaa9  cmp     [rsp+4B0h+var_450], 4E20h
0x18004aab2  ja      short loc_18004AA66
0x18004aab4  mov     [rsp+4B0h+var_480], 3
0x18004aabc  mov     edi, 1
0x18004aac1  mov     [rsp+4B0h+var_488], edi
0x18004aac5  mov     [rsp+4B0h+phkResult], r15; int
0x18004aaca  xor     r8d, r8d
0x18004aacd  lea     rcx, [rsp+4B0h+FileName]
0x18004aad2  call    ?VerifyFileTrustImp@@YAJPEB_WW4_AcceptTrustedPublishersAction@@HPEAUCERT_HASH_BLOB@@0HW4_SignatureStrengthPolicy@@PEAUDualSubCAIdentity@@@Z; VerifyFileTrustImp(wchar_t const *,_AcceptTrustedPublishersAction,int,CERT_HASH_BLOB *,wchar_t const *,int,_SignatureStrengthPolicy,DualSubCAIdentity *)
0x18004aad7  mov     esi, eax
0x18004aad9  test    eax, eax
0x18004aadb  jns     short loc_18004AAFD
0x18004aadd  mov     r9d, eax; char *
0x18004aae0  mov     edx, 9Dh; void *
0x18004aae5  lea     r8, aCW1SSrcClientL_26; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18004aaec  mov     rcx, [rbp+3B8h]; this
0x18004aaf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004aaf8  jmp     loc_18004AA6B
0x18004aafd  mov     [rsp+4B0h+var_450], r15
0x18004ab02  lea     rax, [rsp+4B0h+var_450]
0x18004ab07  mov     [rsp+4B0h+var_458], rax
0x18004ab0c  mov     [rsp+4B0h+var_468], r15d
0x18004ab11  mov     [rsp+4B0h+var_478], r15d
0x18004ab16  mov     [rsp+4B0h+var_480], edi
0x18004ab1a  lea     rax, off_1800A1510; "autest.txt"
0x18004ab21  mov     qword ptr [rsp+4B0h+var_488], rax
0x18004ab26  mov     [rsp+4B0h+phkResult], r15; int
0x18004ab2b  xor     r9d, r9d
0x18004ab2e  lea     r8, [rsp+4B0h+FileName]
0x18004ab33  call    DecompressCabFileInternal
0x18004ab38  mov     esi, eax
0x18004ab3a  mov     rbx, [rsp+4B0h+var_450]
0x18004ab3f  test    eax, eax
0x18004ab41  jns     short loc_18004AB7E
0x18004ab43  mov     rcx, [rbp+3B8h]; this
0x18004ab4a  mov     r9d, eax; char *
0x18004ab4d  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x18004ab54  mov     edx, 608h; void *
0x18004ab59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ab5e  mov     rcx, [rbp+3B8h]; this
0x18004ab65  mov     r9d, esi; char *
0x18004ab68  lea     r8, aCW1SSrcClientL_26; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18004ab6f  mov     edx, 0A6h; void *
0x18004ab74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ab79  jmp     loc_18004AC01
0x18004ab7e  test    rbx, rbx
0x18004ab81  jz      short loc_18004ABFC
0x18004ab83  cmp     [rbx+18h], edi
0x18004ab86  jnz     short loc_18004ABFC
0x18004ab88  mov     rax, [rbx+8]
0x18004ab8c  mov     [rbx+20h], rax
0x18004ab90  mov     [rsp+4B0h+var_450], r15
0x18004ab95  lea     rdx, [rsp+4B0h+var_450]
0x18004ab9a  mov     rcx, rbx
0x18004ab9d  call    ?Remove@?$CSusListIterator@VCOutputMemoryFile@@@@QEAAJPEAPEAVCOutputMemoryFile@@@Z; CSusListIterator<COutputMemoryFile>::Remove(COutputMemoryFile * *)
0x18004aba2  mov     esi, eax
0x18004aba4  mov     rdi, [rsp+4B0h+var_450]
0x18004aba9  test    eax, eax
0x18004abab  jns     short loc_18004ABCA
0x18004abad  mov     rcx, [rbp+3B8h]; this
0x18004abb4  mov     r9d, eax; char *
0x18004abb7  lea     r8, aCW1SSrcClientL_26; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18004abbe  mov     edx, 0B0h; void *
0x18004abc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004abc8  jmp     short loc_18004ABE0
0x18004abca  mov     rcx, [rdi+10h]
0x18004abce  mov     rdx, [rcx+8]; char *
0x18004abd2  mov     ecx, [rcx+14h]; unsigned int
0x18004abd5  call    ?IsValidAUTestCabFileText@@YAHKPEBD@Z; IsValidAUTestCabFileText(ulong,char const *)
0x18004abda  mov     [r14], eax
0x18004abdd  mov     esi, r15d
0x18004abe0  test    rdi, rdi
0x18004abe3  jz      short loc_18004AC01
0x18004abe5  mov     rcx, rdi; this
0x18004abe8  call    ??1COutputMemoryFile@@QEAA@XZ; COutputMemoryFile::~COutputMemoryFile(void)
0x18004abed  mov     edx, 120h; struct std::nothrow_t *
0x18004abf2  mov     rcx, rdi; void *
0x18004abf5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004abfa  jmp     short loc_18004AC01
0x18004abfc  mov     esi, 80240FFFh
0x18004ac01  test    rbx, rbx
0x18004ac04  jz      loc_18004AA6B
0x18004ac0a  mov     rcx, rbx
0x18004ac0d  call    ??1?$CSusListIterator@VCOutputMemoryFile@@@@QEAA@XZ; CSusListIterator<COutputMemoryFile>::~CSusListIterator<COutputMemoryFile>(void)
0x18004ac12  mov     edx, 28h ; '('; struct std::nothrow_t *
0x18004ac17  mov     rcx, rbx; void *
0x18004ac1a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004ac1f  jmp     loc_18004AA6B
```
