# AreTestKeysAllowedInternal(int &)

- ea: `0x14000d0fc`
- end: `0x14000d49e`
- name: `?AreTestKeysAllowedInternal@@YAJAEAH@Z`
- size: `930`
- prototype: `__int64 __fastcall(int *, __int64, __int64, unsigned int *)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x140003de4`
- `0x14000d4a4`

## callees

- `0x140008140`
- `0x140008de4`
- `0x14000cfd0`
- `0x14000d0fc`
- `0x14000d65c`
- `0x14000d7b0`
- `0x14000d7e4`
- `0x14000d814`
- `0x14000db18`
- `0x14000e194`
- `0x14000f39c`
- `0x14002bd6c`
- `0x14002fc9c`
- `0x140030484`
- `0x140044a34`
- `0x140045dc0`
- `0x140045de4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000d2e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000d2e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000d1ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000d1ca`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000d28d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000d28d`

## string_xrefs

- `0x14000d1e7`: `AlternateTestCabPath`
- `0x14000d1bc`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x14000d3c6`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressor.cpp`

## pseudocode

```c
__int64 __fastcall AreTestKeysAllowedInternal(int *a1, __int64 a2, __int64 a3, unsigned int *a4)
{
  int SusBaseDirectoryW; // ebx
  __int64 v6; // rdx
  __int64 v8; // rcx
  int LastErrorFailHr; // esi
  __int64 v10; // rdx
  unsigned __int64 v11; // r9
  wil::details *v12; // rcx
  int FileSize; // eax
  __int64 v14; // rdx
  __int64 v15; // r9
  int v16; // eax
  int v17; // eax
  COutputMemoryFile *v18; // rbx
  int v19; // eax
  COutputMemoryFile *v20; // rdi
  int phkResult; // [rsp+28h] [rbp-E0h]
  int phkResulta; // [rsp+28h] [rbp-E0h]
  int phkResultb; // [rsp+28h] [rbp-E0h]
  int phkResultc; // [rsp+28h] [rbp-E0h]
  __int64 v25; // [rsp+48h] [rbp-C0h]
  __int64 v26; // [rsp+58h] [rbp-B0h]
  COutputMemoryFile *v27; // [rsp+68h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-98h] BYREF
  WCHAR FileName[264]; // [rsp+78h] [rbp-90h] BYREF
  wchar_t pszDest[264]; // [rsp+288h] [rbp+180h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C0h] [rbp+3B8h]

  SusBaseDirectoryW = GetSusBaseDirectoryW(pszDest, a2, L"\\", a4);
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
  SusBaseDirectoryW = StringCchCopyExW(FileName, 0x104u, pszDest, 0, 0, 0x100u);
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
    if ( (int)SafeRegQueryValueCchHelper(v8, hKey, L"AlternateTestCabPath", FileName, 260, 0, 0) < 0 )
      StringCchCopyExW(FileName, 0x104u, pszDest, 0, 0, 0x100u);
    LastErrorFailHr = StringCchCatExW(FileName, 0x104u, L"\\", 0, 0, 0x100u);
    if ( LastErrorFailHr < 0 )
    {
      v10 = 133;
LABEL_13:
      v11 = (unsigned int)LastErrorFailHr;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WUTestKeys.cpp",
        (const char *)v11,
        phkResulta);
      goto LABEL_19;
    }
  }
  LastErrorFailHr = StringCchCatExW(FileName, 0x104u, L"autest.cab", 0, 0, 0x100u);
  if ( LastErrorFailHr < 0 )
  {
    v10 = 137;
    goto LABEL_13;
  }
  if ( GetFileAttributesW(FileName) != -1
    || (LastErrorFailHr = wil::details::GetLastErrorFailHr(v12), LastErrorFailHr >= 0) )
  {
    v27 = 0;
    FileSize = SusGetFileSize(FileName, (unsigned __int64 *)&v27);
    if ( FileSize >= 0 )
    {
      if ( (unsigned __int64)v27 <= 0x4E20 )
      {
        v16 = VerifyFileTrustImp(FileName, v14, 0, v15, 0, 1, 3u, 0);
        LastErrorFailHr = v16;
        if ( v16 >= 0 )
        {
          v27 = 0;
          v17 = DecompressCabFileInternal(1, 0, (__int64)FileName, 0, 0, &off_14007F0A8, 1u, 0, v25, 0, v26, &v27);
          LastErrorFailHr = v17;
          v18 = v27;
          if ( v17 >= 0 )
          {
            if ( v27 && *((_DWORD *)v27 + 6) == 1 )
            {
              *((_QWORD *)v27 + 4) = *((_QWORD *)v27 + 1);
              v27 = 0;
              v19 = CSusListIterator<COutputMemoryFile>::Remove(v18, &v27);
              LastErrorFailHr = v19;
              v20 = v27;
              if ( v19 >= 0 )
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
                  (const char *)(unsigned int)v19,
                  phkResultb);
              }
              if ( v20 )
              {
                COutputMemoryFile::~COutputMemoryFile(v20);
                operator delete(v20, (const struct std::nothrow_t *)0x120);
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
              (const char *)(unsigned int)v17,
              phkResultb);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA6,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WUTestKeys.cpp",
              (const char *)(unsigned int)LastErrorFailHr,
              phkResultc);
          }
          if ( v18 )
          {
            CSusListIterator<COutputMemoryFile>::~CSusListIterator<COutputMemoryFile>(v18);
            operator delete(v18, (const struct std::nothrow_t *)0x28);
          }
          goto LABEL_19;
        }
        v11 = (unsigned int)v16;
        v10 = 157;
        goto LABEL_25;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x91,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WUTestKeys.cpp",
        (const char *)(unsigned int)FileSize,
        phkResulta);
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
0x14000d0fc  mov     rax, rsp
0x14000d0ff  mov     [rax+10h], rbx
0x14000d103  mov     [rax+18h], rsi
0x14000d107  mov     [rax+20h], rdi
0x14000d10b  push    rbp
0x14000d10c  push    r14
0x14000d10e  push    r15
0x14000d110  lea     rbp, [rax-3B8h]
0x14000d117  sub     rsp, 4A0h
0x14000d11e  mov     rax, cs:__security_cookie
0x14000d125  xor     rax, rsp
0x14000d128  mov     [rbp+3B0h+var_20], rax
0x14000d12f  mov     r14, rcx
0x14000d132  lea     r8, SubBlock; "\\"
0x14000d139  lea     rcx, [rbp+3B0h+pszDest]; pszDest
0x14000d140  call    ?GetSusBaseDirectoryW@@YAJPEA_WKPEB_WPEAK@Z; GetSusBaseDirectoryW(wchar_t *,ulong,wchar_t const *,ulong *)
0x14000d145  mov     ebx, eax
0x14000d147  xor     r15d, r15d
0x14000d14a  test    eax, eax
0x14000d14c  jns     short loc_14000D16F
0x14000d14e  lea     edx, [r15+73h]; void *
0x14000d152  lea     r8, aCW1SSrcClientL_32; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000d159  mov     r9d, ebx; char *
0x14000d15c  mov     rcx, [rbp+3B8h]; this
0x14000d163  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d168  mov     eax, ebx
0x14000d16a  jmp     loc_14000D2ED
0x14000d16f  mov     [rsp+4B0h+var_488], 100h; unsigned int
0x14000d177  mov     [rsp+4B0h+phkResult], r15; unsigned __int64 *
0x14000d17c  xor     r9d, r9d; wchar_t **
0x14000d17f  lea     r8, [rbp+3B0h+pszDest]; wchar_t *
0x14000d186  mov     edi, 104h
0x14000d18b  mov     edx, edi; unsigned __int64
0x14000d18d  lea     rcx, [rsp+4B0h+FileName]; pszDest
0x14000d192  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x14000d197  mov     ebx, eax
0x14000d199  test    eax, eax
0x14000d19b  jns     short loc_14000D1A4
0x14000d19d  mov     edx, 75h ; 'u'
0x14000d1a2  jmp     short loc_14000D152
0x14000d1a4  mov     [rsp+4B0h+hKey], r15
0x14000d1a9  lea     rax, [rsp+4B0h+hKey]
0x14000d1ae  mov     [rsp+4B0h+phkResult], rax; phkResult
0x14000d1b3  mov     r9d, 20019h; samDesired
0x14000d1b9  xor     r8d, r8d; ulOptions
0x14000d1bc  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14000d1c3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000d1ca  call    cs:__imp_RegOpenKeyExW
0x14000d1d0  test    eax, eax
0x14000d1d2  jnz     short loc_14000D251
0x14000d1d4  mov     [rsp+4B0h+var_480], r15
0x14000d1d9  mov     qword ptr [rsp+4B0h+var_488], r15
0x14000d1de  mov     dword ptr [rsp+4B0h+phkResult], edi
0x14000d1e2  lea     r9, [rsp+4B0h+FileName]
0x14000d1e7  lea     r8, aAlternatetestc; "AlternateTestCabPath"
0x14000d1ee  mov     rdx, [rsp+4B0h+hKey]
0x14000d1f3  call    SafeRegQueryValueCchHelper
0x14000d1f8  test    eax, eax
0x14000d1fa  jns     short loc_14000D220
0x14000d1fc  mov     [rsp+4B0h+var_488], 100h; unsigned int
0x14000d204  mov     [rsp+4B0h+phkResult], r15; unsigned __int64 *
0x14000d209  xor     r9d, r9d; wchar_t **
0x14000d20c  lea     r8, [rbp+3B0h+pszDest]; wchar_t *
0x14000d213  mov     rdx, rdi; unsigned __int64
0x14000d216  lea     rcx, [rsp+4B0h+FileName]; pszDest
0x14000d21b  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x14000d220  mov     [rsp+4B0h+var_488], 100h; unsigned int
0x14000d228  mov     [rsp+4B0h+phkResult], r15; unsigned __int64 *
0x14000d22d  xor     r9d, r9d; wchar_t **
0x14000d230  lea     r8, SubBlock; "\\"
0x14000d237  mov     rdx, rdi; unsigned __int64
0x14000d23a  lea     rcx, [rsp+4B0h+FileName]; pszDest
0x14000d23f  call    ?StringCchCatExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCatExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x14000d244  mov     esi, eax
0x14000d246  test    eax, eax
0x14000d248  jns     short loc_14000D251
0x14000d24a  mov     edx, 85h
0x14000d24f  jmp     short loc_14000D280
0x14000d251  mov     [rsp+4B0h+var_488], 100h; unsigned int
0x14000d259  mov     [rsp+4B0h+phkResult], r15; int
0x14000d25e  xor     r9d, r9d; wchar_t **
0x14000d261  lea     r8, aAutestCab; "autest.cab"
0x14000d268  mov     rdx, rdi; unsigned __int64
0x14000d26b  lea     rcx, [rsp+4B0h+FileName]; pszDest
0x14000d270  call    ?StringCchCatExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCatExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x14000d275  mov     esi, eax
0x14000d277  test    eax, eax
0x14000d279  jns     short loc_14000D288
0x14000d27b  mov     edx, 89h
0x14000d280  mov     r9d, esi
0x14000d283  jmp     loc_14000D35A
0x14000d288  lea     rcx, [rsp+4B0h+FileName]; lpFileName
0x14000d28d  call    cs:__imp_GetFileAttributesW
0x14000d293  cmp     eax, 0FFFFFFFFh
0x14000d296  jnz     short loc_14000D2A3
0x14000d298  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000d29d  mov     esi, eax
0x14000d29f  test    eax, eax
0x14000d2a1  js      short loc_14000D2DB
0x14000d2a3  mov     [rsp+4B0h+var_450], r15
0x14000d2a8  lea     rdx, [rsp+4B0h+var_450]; unsigned __int64 *
0x14000d2ad  lea     rcx, [rsp+4B0h+FileName]; wchar_t *
0x14000d2b2  call    ?SusGetFileSize@@YAJPEB_WPEA_K@Z; SusGetFileSize(wchar_t const *,unsigned __int64 *)
0x14000d2b7  mov     rcx, [rbp+3B8h]; this
0x14000d2be  test    eax, eax
0x14000d2c0  jns     short loc_14000D319
0x14000d2c2  mov     r9d, eax; char *
0x14000d2c5  lea     r8, aCW1SSrcClientL_32; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000d2cc  mov     edx, 91h; void *
0x14000d2d1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000d2d6  mov     esi, 80240FFFh
0x14000d2db  mov     rcx, [rsp+4B0h+hKey]; hKey
0x14000d2e0  test    rcx, rcx
0x14000d2e3  jz      short loc_14000D2EB
0x14000d2e5  call    cs:__imp_RegCloseKey
0x14000d2eb  mov     eax, esi
0x14000d2ed  mov     rcx, [rbp+3B0h+var_20]
0x14000d2f4  xor     rcx, rsp; StackCookie
0x14000d2f7  call    __security_check_cookie
0x14000d2fc  lea     r11, [rsp+4B0h+var_10]
0x14000d304  mov     rbx, [r11+28h]
0x14000d308  mov     rsi, [r11+30h]
0x14000d30c  mov     rdi, [r11+38h]
0x14000d310  mov     rsp, r11
0x14000d313  pop     r15
0x14000d315  pop     r14
0x14000d317  pop     rbp
0x14000d318  retn
0x14000d319  cmp     [rsp+4B0h+var_450], 4E20h
0x14000d322  ja      short loc_14000D2D6
0x14000d324  mov     [rsp+4B0h+var_478], r15
0x14000d329  mov     dword ptr [rsp+4B0h+var_480], 3
0x14000d331  mov     edi, 1
0x14000d336  mov     [rsp+4B0h+var_488], edi
0x14000d33a  mov     [rsp+4B0h+phkResult], r15; int
0x14000d33f  xor     r8d, r8d
0x14000d342  lea     rcx, [rsp+4B0h+FileName]
0x14000d347  call    ?VerifyFileTrustImp@@YAJPEB_WW4_AcceptTrustedPublishersAction@@HPEAUCERT_HASH_BLOB@@0HW4_SignatureStrengthPolicy@@PEAUDualSubCAIdentity@@@Z; VerifyFileTrustImp(wchar_t const *,_AcceptTrustedPublishersAction,int,CERT_HASH_BLOB *,wchar_t const *,int,_SignatureStrengthPolicy,DualSubCAIdentity *)
0x14000d34c  mov     esi, eax
0x14000d34e  test    eax, eax
0x14000d350  jns     short loc_14000D372
0x14000d352  mov     r9d, eax; char *
0x14000d355  mov     edx, 9Dh; void *
0x14000d35a  lea     r8, aCW1SSrcClientL_32; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000d361  mov     rcx, [rbp+3B8h]; this
0x14000d368  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d36d  jmp     loc_14000D2DB
0x14000d372  mov     [rsp+4B0h+var_450], r15
0x14000d377  lea     rax, [rsp+4B0h+var_450]
0x14000d37c  mov     [rsp+4B0h+var_458], rax
0x14000d381  mov     [rsp+4B0h+var_468], r15d
0x14000d386  mov     dword ptr [rsp+4B0h+var_478], r15d
0x14000d38b  mov     dword ptr [rsp+4B0h+var_480], edi
0x14000d38f  lea     rax, off_14007F0A8; "autest.txt"
0x14000d396  mov     qword ptr [rsp+4B0h+var_488], rax
0x14000d39b  mov     [rsp+4B0h+phkResult], r15; int
0x14000d3a0  xor     r9d, r9d
0x14000d3a3  lea     r8, [rsp+4B0h+FileName]
0x14000d3a8  xor     edx, edx
0x14000d3aa  mov     ecx, edi
0x14000d3ac  call    DecompressCabFileInternal
0x14000d3b1  mov     esi, eax
0x14000d3b3  mov     rbx, [rsp+4B0h+var_450]
0x14000d3b8  test    eax, eax
0x14000d3ba  jns     short loc_14000D3F7
0x14000d3bc  mov     rcx, [rbp+3B8h]; this
0x14000d3c3  mov     r9d, eax; char *
0x14000d3c6  lea     r8, aCW1SSrcClientL_3; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x14000d3cd  mov     edx, 608h; void *
0x14000d3d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d3d7  mov     rcx, [rbp+3B8h]; this
0x14000d3de  mov     r9d, esi; char *
0x14000d3e1  lea     r8, aCW1SSrcClientL_32; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000d3e8  mov     edx, 0A6h; void *
0x14000d3ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d3f2  jmp     loc_14000D47A
0x14000d3f7  test    rbx, rbx
0x14000d3fa  jz      short loc_14000D475
0x14000d3fc  cmp     [rbx+18h], edi
0x14000d3ff  jnz     short loc_14000D475
0x14000d401  mov     rax, [rbx+8]
0x14000d405  mov     [rbx+20h], rax
0x14000d409  mov     [rsp+4B0h+var_450], r15
0x14000d40e  lea     rdx, [rsp+4B0h+var_450]
0x14000d413  mov     rcx, rbx
0x14000d416  call    ?Remove@?$CSusListIterator@VCOutputMemoryFile@@@@QEAAJPEAPEAVCOutputMemoryFile@@@Z; CSusListIterator<COutputMemoryFile>::Remove(COutputMemoryFile * *)
0x14000d41b  mov     esi, eax
0x14000d41d  mov     rdi, [rsp+4B0h+var_450]
0x14000d422  test    eax, eax
0x14000d424  jns     short loc_14000D443
0x14000d426  mov     rcx, [rbp+3B8h]; this
0x14000d42d  mov     r9d, eax; char *
0x14000d430  lea     r8, aCW1SSrcClientL_32; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000d437  mov     edx, 0B0h; void *
0x14000d43c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d441  jmp     short loc_14000D459
0x14000d443  mov     rcx, [rdi+10h]
0x14000d447  mov     rdx, [rcx+8]; char *
0x14000d44b  mov     ecx, [rcx+14h]; unsigned int
0x14000d44e  call    ?IsValidAUTestCabFileText@@YAHKPEBD@Z; IsValidAUTestCabFileText(ulong,char const *)
0x14000d453  mov     [r14], eax
0x14000d456  mov     esi, r15d
0x14000d459  test    rdi, rdi
0x14000d45c  jz      short loc_14000D47A
0x14000d45e  mov     rcx, rdi; this
0x14000d461  call    ??1COutputMemoryFile@@QEAA@XZ; COutputMemoryFile::~COutputMemoryFile(void)
0x14000d466  mov     edx, 120h; struct std::nothrow_t *
0x14000d46b  mov     rcx, rdi; void *
0x14000d46e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000d473  jmp     short loc_14000D47A
0x14000d475  mov     esi, 80240FFFh
0x14000d47a  test    rbx, rbx
0x14000d47d  jz      loc_14000D2DB
0x14000d483  mov     rcx, rbx
0x14000d486  call    ??1?$CSusListIterator@VCOutputMemoryFile@@@@QEAA@XZ; CSusListIterator<COutputMemoryFile>::~CSusListIterator<COutputMemoryFile>(void)
0x14000d48b  mov     edx, 28h ; '('; struct std::nothrow_t *
0x14000d490  mov     rcx, rbx; void *
0x14000d493  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000d498  jmp     loc_14000D2DB
```
