# Appx::Packaging::CatalogReaderHelper::VerifyCatalogFileContainsHash(ushort const *,ulong,uchar const *,bool)

- ea: `0x180101720`
- end: `0x180101ab8`
- name: `?VerifyCatalogFileContainsHash@CatalogReaderHelper@Packaging@Appx@@YAJPEBGKPEBE_N@Z`
- size: `920`
- prototype: `__int64 __fastcall(Appx::Packaging::CatalogReaderHelper *this, const unsigned __int16 *, BYTE *, const unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800f7d28`

## callees

- `0x1800133fc`
- `0x18006a900`
- `0x180078454`
- `0x180101720`
- `0x180101ac0`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180101827`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18010187a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801018cf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180101922`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180101977`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801019d8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180101a90`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180101827`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18010187a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801018cf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180101922`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180101977`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801019d8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180101a90`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18010178d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18010178d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801017b0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801017b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801017f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180101843`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180101896`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801018eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010193e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801017f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180101843`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180101896`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801018eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010193e`

## string_xrefs

- `0x180101786`: `wintrust.dll`
- `0x1801017a9`: `wintrust.dll`
- `0x1801017e6`: `CryptCATOpen`
- `0x18010175a`: `onecore\printscan\appxpackaging\lib\crypto\src\catalogreaderhelper.cpp`
- `0x1801017cc`: `onecore\printscan\appxpackaging\lib\crypto\src\catalogreaderhelper.cpp`
- `0x18010180c`: `onecore\printscan\appxpackaging\lib\crypto\src\catalogreaderhelper.cpp`
- `0x18010185f`: `onecore\printscan\appxpackaging\lib\crypto\src\catalogreaderhelper.cpp`
- `0x1801018b4`: `onecore\printscan\appxpackaging\lib\crypto\src\catalogreaderhelper.cpp`
- `0x180101907`: `onecore\printscan\appxpackaging\lib\crypto\src\catalogreaderhelper.cpp`
- `0x18010195c`: `onecore\printscan\appxpackaging\lib\crypto\src\catalogreaderhelper.cpp`
- `0x1801019bd`: `onecore\printscan\appxpackaging\lib\crypto\src\catalogreaderhelper.cpp`
- `0x180101a76`: `onecore\printscan\appxpackaging\lib\crypto\src\catalogreaderhelper.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::CatalogReaderHelper::VerifyCatalogFileContainsHash(
        Appx::Packaging::CatalogReaderHelper *this,
        const unsigned __int16 *a2,
        BYTE *a3,
        const unsigned __int8 *a4)
{
  __int64 v6; // rdx
  HMODULE v8; // rbx
  HMODULE ModuleHandleW; // rdi
  HMODULE Library; // rax
  const char *v11; // r9
  const char *v12; // r9
  FARPROC ProcAddress; // r15
  int HResultFromLastError; // edi
  const char *v15; // r9
  FARPROC v16; // r13
  const char *v17; // r9
  const char *v18; // r9
  FARPROC v19; // r14
  FARPROC v20; // rsi
  const char *v21; // r9
  const char *v22; // r9
  Common *v23; // rcx
  void *v24; // r14
  int v25; // [rsp+20h] [rbp-68h]
  int v26; // [rsp+20h] [rbp-68h]
  struct CRYPTCATMEMBER_ *(*v27)(void *, unsigned __int16 *); // [rsp+40h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  void *v29; // [rsp+90h] [rbp+8h] BYREF
  unsigned int v30; // [rsp+98h] [rbp+10h]
  bool v31; // [rsp+A8h] [rbp+20h]

  v31 = (char)a4;
  v30 = (unsigned int)a2;
  if ( !this )
  {
    v6 = 174;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\catalogreaderhelper.cpp",
      (const char *)0x80004003LL,
      v25);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    v6 = 175;
    goto LABEL_3;
  }
  v8 = 0;
  ModuleHandleW = GetModuleHandleW(L"wintrust.dll");
  if ( !ModuleHandleW )
  {
    Library = LoadLibraryExW(L"wintrust.dll", 0, 0x800u);
    ModuleHandleW = Library;
    if ( !Library )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0xB8,
               (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\catalogreaderhelper.cpp",
               v11);
    v8 = Library;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "CryptCATOpen");
  if ( ProcAddress )
  {
    v16 = GetProcAddress(ModuleHandleW, "CryptCATClose");
    if ( v16 )
    {
      v27 = (struct CRYPTCATMEMBER_ *(*)(void *, unsigned __int16 *))GetProcAddress(
                                                                       ModuleHandleW,
                                                                       "CryptCATGetMemberInfo");
      if ( v27 )
      {
        v19 = GetProcAddress(ModuleHandleW, "CryptCATAdminAcquireContext2");
        if ( v19 )
        {
          v20 = GetProcAddress(ModuleHandleW, "CryptCATAdminReleaseContext");
          if ( v20 )
          {
            v29 = 0;
            if ( ((unsigned int (__fastcall *)(void **, _QWORD, const WCHAR *, _QWORD, _DWORD))v19)(
                   &v29,
                   0,
                   L"SHA256",
                   0,
                   0) )
            {
              v26 = 0;
              v24 = (void *)((__int64 (__fastcall *)(Appx::Packaging::CatalogReaderHelper *, _QWORD, _QWORD, _QWORD))ProcAddress)(
                              this,
                              0,
                              0,
                              0);
              if ( v24 == (void *)-1LL )
              {
                HResultFromLastError = Common::GetHResultFromLastError(v23);
              }
              else
              {
                HResultFromLastError = VerifyCatalogFileContainsHashInternal(
                                         v29,
                                         v24,
                                         (const unsigned __int16 *)this,
                                         v30,
                                         a3,
                                         v31,
                                         v27);
                ((void (__fastcall *)(void *))v16)(v24);
              }
              ((void (__fastcall *)(void *, _QWORD))v20)(v29, 0);
              if ( HResultFromLastError < 0 )
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xE4,
                  (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\catalogreaderhelper.cpp",
                  (const char *)(unsigned int)HResultFromLastError,
                  v26);
              if ( v8 )
                FreeLibrary(v8);
            }
            else
            {
              HResultFromLastError = wil::details::in1diag3::Return_GetLastError(
                                       retaddr,
                                       (void *)0xD4,
                                       (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\catalogreaderhelper.cpp",
                                       v22);
              if ( v8 )
                FreeLibrary(v8);
            }
          }
          else
          {
            HResultFromLastError = wil::details::in1diag3::Return_GetLastError(
                                     retaddr,
                                     (void *)0xCE,
                                     (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\catalogreaderhelper.cpp",
                                     v21);
            if ( v8 )
              FreeLibrary(v8);
          }
        }
        else
        {
          HResultFromLastError = wil::details::in1diag3::Return_GetLastError(
                                   retaddr,
                                   (void *)0xCA,
                                   (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\catalogreaderhelper.cpp",
                                   v18);
          if ( v8 )
            FreeLibrary(v8);
        }
      }
      else
      {
        HResultFromLastError = wil::details::in1diag3::Return_GetLastError(
                                 retaddr,
                                 (void *)0xC6,
                                 (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\catalogreaderhelper.cpp",
                                 v17);
        if ( v8 )
          FreeLibrary(v8);
      }
    }
    else
    {
      HResultFromLastError = wil::details::in1diag3::Return_GetLastError(
                               retaddr,
                               (void *)0xC2,
                               (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\catalogreaderhelper.cpp",
                               v15);
      if ( v8 )
        FreeLibrary(v8);
    }
  }
  else
  {
    HResultFromLastError = wil::details::in1diag3::Return_GetLastError(
                             retaddr,
                             (void *)0xBE,
                             (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\catalogreaderhelper.cpp",
                             v12);
    if ( v8 )
      FreeLibrary(v8);
  }
  return (unsigned int)HResultFromLastError;
}

```

## disassembly

```asm
0x180101720  mov     rax, rsp
0x180101723  mov     [rax+20h], r9b
0x180101727  mov     [rax+10h], edx
0x18010172a  push    rbp
0x18010172b  push    rsi
0x18010172c  push    rdi
0x18010172d  push    r12
0x18010172f  push    r13
0x180101731  push    r14
0x180101733  push    r15
0x180101735  sub     rsp, 50h
0x180101739  mov     qword ptr [rax-40h], 0FFFFFFFFFFFFFFFEh
0x180101741  mov     [rax+18h], rbx
0x180101745  mov     r12, r8
0x180101748  mov     rbp, rcx
0x18010174b  test    rcx, rcx
0x18010174e  jnz     short loc_180101778
0x180101750  mov     edx, 0AEh; void *
0x180101755  mov     ebx, 80004003h
0x18010175a  lea     r8, aOnecorePrintsc_95; "onecore\\printscan\\appxpackaging\\lib"...
0x180101761  mov     r9d, ebx; char *
0x180101764  mov     rcx, [rsp+88h]; this
0x18010176c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101771  mov     eax, ebx
0x180101773  jmp     loc_180101A9F
0x180101778  test    r12, r12
0x18010177b  jnz     short loc_180101784
0x18010177d  mov     edx, 0AFh
0x180101782  jmp     short loc_180101755
0x180101784  xor     ebx, ebx
0x180101786  lea     rcx, aWintrustDll_1; "wintrust.dll"
0x18010178d  call    cs:__imp_GetModuleHandleW
0x180101794  nop     dword ptr [rax+rax+00h]
0x180101799  mov     rdi, rax
0x18010179c  test    rax, rax
0x18010179f  jnz     short loc_1801017E6
0x1801017a1  xor     edx, edx; hFile
0x1801017a3  mov     r8d, 800h; dwFlags
0x1801017a9  lea     rcx, aWintrustDll_1; "wintrust.dll"
0x1801017b0  call    cs:__imp_LoadLibraryExW
0x1801017b7  nop     dword ptr [rax+rax+00h]
0x1801017bc  mov     rdi, rax
0x1801017bf  test    rax, rax
0x1801017c2  jnz     short loc_1801017E3
0x1801017c4  mov     rcx, [rsp+88h]; this
0x1801017cc  lea     r8, aOnecorePrintsc_95; "onecore\\printscan\\appxpackaging\\lib"...
0x1801017d3  mov     edx, 0B8h; void *
0x1801017d8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801017dd  nop
0x1801017de  jmp     loc_180101A9F
0x1801017e3  mov     rbx, rax
0x1801017e6  lea     rdx, aCryptcatopen; "CryptCATOpen"
0x1801017ed  mov     rcx, rdi; hModule
0x1801017f0  call    cs:__imp_GetProcAddress
0x1801017f7  nop     dword ptr [rax+rax+00h]
0x1801017fc  mov     r15, rax
0x1801017ff  test    rax, rax
0x180101802  jnz     short loc_180101839
0x180101804  mov     rcx, [rsp+88h]; this
0x18010180c  lea     r8, aOnecorePrintsc_95; "onecore\\printscan\\appxpackaging\\lib"...
0x180101813  mov     edx, 0BEh; void *
0x180101818  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18010181d  mov     edi, eax
0x18010181f  test    rbx, rbx
0x180101822  jz      short loc_180101834
0x180101824  mov     rcx, rbx; hLibModule
0x180101827  call    cs:__imp_FreeLibrary
0x18010182e  nop     dword ptr [rax+rax+00h]
0x180101833  nop
0x180101834  jmp     loc_180101A9D
0x180101839  lea     rdx, aCryptcatclose; "CryptCATClose"
0x180101840  mov     rcx, rdi; hModule
0x180101843  call    cs:__imp_GetProcAddress
0x18010184a  nop     dword ptr [rax+rax+00h]
0x18010184f  mov     r13, rax
0x180101852  test    rax, rax
0x180101855  jnz     short loc_18010188C
0x180101857  mov     rcx, [rsp+88h]; this
0x18010185f  lea     r8, aOnecorePrintsc_95; "onecore\\printscan\\appxpackaging\\lib"...
0x180101866  mov     edx, 0C2h; void *
0x18010186b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180101870  mov     edi, eax
0x180101872  test    rbx, rbx
0x180101875  jz      short loc_180101887
0x180101877  mov     rcx, rbx; hLibModule
0x18010187a  call    cs:__imp_FreeLibrary
0x180101881  nop     dword ptr [rax+rax+00h]
0x180101886  nop
0x180101887  jmp     loc_180101A9D
0x18010188c  lea     rdx, aCryptcatgetmem; "CryptCATGetMemberInfo"
0x180101893  mov     rcx, rdi; hModule
0x180101896  call    cs:__imp_GetProcAddress
0x18010189d  nop     dword ptr [rax+rax+00h]
0x1801018a2  mov     [rsp+88h+var_48], rax
0x1801018a7  test    rax, rax
0x1801018aa  jnz     short loc_1801018E1
0x1801018ac  mov     rcx, [rsp+88h]; this
0x1801018b4  lea     r8, aOnecorePrintsc_95; "onecore\\printscan\\appxpackaging\\lib"...
0x1801018bb  mov     edx, 0C6h; void *
0x1801018c0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801018c5  mov     edi, eax
0x1801018c7  test    rbx, rbx
0x1801018ca  jz      short loc_1801018DC
0x1801018cc  mov     rcx, rbx; hLibModule
0x1801018cf  call    cs:__imp_FreeLibrary
0x1801018d6  nop     dword ptr [rax+rax+00h]
0x1801018db  nop
0x1801018dc  jmp     loc_180101A9D
0x1801018e1  lea     rdx, aCryptcatadmina; "CryptCATAdminAcquireContext2"
0x1801018e8  mov     rcx, rdi; hModule
0x1801018eb  call    cs:__imp_GetProcAddress
0x1801018f2  nop     dword ptr [rax+rax+00h]
0x1801018f7  mov     r14, rax
0x1801018fa  test    rax, rax
0x1801018fd  jnz     short loc_180101934
0x1801018ff  mov     rcx, [rsp+88h]; this
0x180101907  lea     r8, aOnecorePrintsc_95; "onecore\\printscan\\appxpackaging\\lib"...
0x18010190e  mov     edx, 0CAh; void *
0x180101913  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180101918  mov     edi, eax
0x18010191a  test    rbx, rbx
0x18010191d  jz      short loc_18010192F
0x18010191f  mov     rcx, rbx; hLibModule
0x180101922  call    cs:__imp_FreeLibrary
0x180101929  nop     dword ptr [rax+rax+00h]
0x18010192e  nop
0x18010192f  jmp     loc_180101A9D
0x180101934  lea     rdx, aCryptcatadminr; "CryptCATAdminReleaseContext"
0x18010193b  mov     rcx, rdi; hModule
0x18010193e  call    cs:__imp_GetProcAddress
0x180101945  nop     dword ptr [rax+rax+00h]
0x18010194a  mov     rsi, rax
0x18010194d  xor     edi, edi
0x18010194f  test    rax, rax
0x180101952  jnz     short loc_180101989
0x180101954  mov     rcx, [rsp+88h]; this
0x18010195c  lea     r8, aOnecorePrintsc_95; "onecore\\printscan\\appxpackaging\\lib"...
0x180101963  mov     edx, 0CEh; void *
0x180101968  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18010196d  mov     edi, eax
0x18010196f  test    rbx, rbx
0x180101972  jz      short loc_180101984
0x180101974  mov     rcx, rbx; hLibModule
0x180101977  call    cs:__imp_FreeLibrary
0x18010197e  nop     dword ptr [rax+rax+00h]
0x180101983  nop
0x180101984  jmp     loc_180101A9D
0x180101989  mov     [rsp+88h+arg_0], rdi
0x180101991  mov     dword ptr [rsp+88h+var_68], edi
0x180101995  xor     r9d, r9d
0x180101998  lea     r8, pszAlgId; "SHA256"
0x18010199f  xor     edx, edx
0x1801019a1  lea     rcx, [rsp+88h+arg_0]
0x1801019a9  mov     rax, r14
0x1801019ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801019b1  test    eax, eax
0x1801019b3  jnz     short loc_1801019EA
0x1801019b5  mov     rcx, [rsp+88h]; this
0x1801019bd  lea     r8, aOnecorePrintsc_95; "onecore\\printscan\\appxpackaging\\lib"...
0x1801019c4  mov     edx, 0D4h; void *
0x1801019c9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801019ce  mov     edi, eax
0x1801019d0  test    rbx, rbx
0x1801019d3  jz      short loc_1801019E5
0x1801019d5  mov     rcx, rbx; hLibModule
0x1801019d8  call    cs:__imp_FreeLibrary
0x1801019df  nop     dword ptr [rax+rax+00h]
0x1801019e4  nop
0x1801019e5  jmp     loc_180101A9D
0x1801019ea  mov     dword ptr [rsp+88h+var_68], edi; int
0x1801019ee  xor     r9d, r9d
0x1801019f1  xor     r8d, r8d
0x1801019f4  xor     edx, edx
0x1801019f6  mov     rcx, rbp
0x1801019f9  mov     rax, r15
0x1801019fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101a01  mov     r14, rax
0x180101a04  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180101a08  jz      short loc_180101A4E
0x180101a0a  mov     rax, [rsp+88h+var_48]
0x180101a0f  mov     [rsp+88h+var_58], rax; struct CRYPTCATMEMBER_ *(*)(void *, unsigned __int16 *)
0x180101a14  mov     al, [rsp+88h+arg_18]
0x180101a1b  mov     [rsp+88h+var_60], al; bool
0x180101a1f  mov     [rsp+88h+var_68], r12; unsigned __int8 *
0x180101a24  mov     r9d, [rsp+88h+arg_8]; unsigned int
0x180101a2c  mov     r8, rbp; unsigned __int16 *
0x180101a2f  mov     rdx, r14; void *
0x180101a32  mov     rcx, [rsp+88h+arg_0]; void *
0x180101a3a  call    ?VerifyCatalogFileContainsHashInternal@@YAJPEAX0PEBGKPEBE_NP6APEAUCRYPTCATMEMBER_@@0PEAG@Z@Z; VerifyCatalogFileContainsHashInternal(void *,void *,ushort const *,ulong,uchar const *,bool,CRYPTCATMEMBER_ * (*)(void *,ushort *))
0x180101a3f  mov     edi, eax
0x180101a41  mov     rcx, r14
0x180101a44  mov     rax, r13
0x180101a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101a4c  jmp     short loc_180101A55
0x180101a4e  call    ?GetHResultFromLastError@Common@@YAJXZ; Common::GetHResultFromLastError(void)
0x180101a53  mov     edi, eax
0x180101a55  xor     edx, edx
0x180101a57  mov     rcx, [rsp+88h+arg_0]
0x180101a5f  mov     rax, rsi
0x180101a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101a67  test    edi, edi
0x180101a69  jns     short loc_180101A88
0x180101a6b  mov     rcx, [rsp+88h]; this
0x180101a73  mov     r9d, edi; char *
0x180101a76  lea     r8, aOnecorePrintsc_95; "onecore\\printscan\\appxpackaging\\lib"...
0x180101a7d  mov     edx, 0E4h; void *
0x180101a82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101a87  nop
0x180101a88  test    rbx, rbx
0x180101a8b  jz      short loc_180101A9D
0x180101a8d  mov     rcx, rbx; hLibModule
0x180101a90  call    cs:__imp_FreeLibrary
0x180101a97  nop     dword ptr [rax+rax+00h]
0x180101a9c  nop
0x180101a9d  mov     eax, edi
0x180101a9f  mov     rbx, [rsp+88h+arg_10]
0x180101aa7  add     rsp, 50h
0x180101aab  pop     r15
0x180101aad  pop     r14
0x180101aaf  pop     r13
0x180101ab1  pop     r12
0x180101ab3  pop     rdi
0x180101ab4  pop     rsi
0x180101ab5  pop     rbp
0x180101ab6  retn
```
