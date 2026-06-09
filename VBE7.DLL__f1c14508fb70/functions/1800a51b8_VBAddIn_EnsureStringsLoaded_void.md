# VBAddIn::EnsureStringsLoaded(void)

- ea: `0x1800a51b8`
- end: `0x1800a57a1`
- name: `?EnsureStringsLoaded@VBAddIn@@QEAAJXZ`
- size: `1513`
- prototype: `__int64 __fastcall(VBAddIn *__hidden this)`
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a4404`
- `0x1800a456c`
- `0x1800a4aa8`
- `0x1800a6e54`
- `0x1800a8528`

## callees

- `0x18001606c`
- `0x18003acb4`
- `0x180057744`
- `0x18005ab18`
- `0x18005b0d4`
- `0x1800a51b8`
- `0x180379380`
- `0x180379520`
- `0x180379546`
- `0x1803796b4`

## import_xrefs

- `MSVCR100!strcpy_s` at `0x1800a534c`
- `MSVCR100!strcpy_s` at `0x1800a534c`
- `MSVCR100!free` at `0x1800a54a8`
- `MSVCR100!free` at `0x1800a56c7`
- `MSVCR100!free` at `0x1800a56ef`
- `MSVCR100!free` at `0x1800a5732`
- `MSVCR100!free` at `0x1800a575a`
- `MSVCR100!free` at `0x1800a54a8`
- `MSVCR100!free` at `0x1800a56c7`
- `MSVCR100!free` at `0x1800a56ef`
- `MSVCR100!free` at `0x1800a5732`
- `MSVCR100!free` at `0x1800a575a`
- `MSVCR100!malloc` at `0x1800a5460`
- `MSVCR100!malloc` at `0x1800a54b7`
- `MSVCR100!malloc` at `0x1800a5693`
- `MSVCR100!malloc` at `0x1800a56d1`
- `MSVCR100!malloc` at `0x1800a56ff`
- `MSVCR100!malloc` at `0x1800a573c`
- `MSVCR100!malloc` at `0x1800a5460`
- `MSVCR100!malloc` at `0x1800a54b7`
- `MSVCR100!malloc` at `0x1800a5693`
- `MSVCR100!malloc` at `0x1800a56d1`
- `MSVCR100!malloc` at `0x1800a56ff`
- `MSVCR100!malloc` at `0x1800a573c`
- `MSVCR100!strcat_s` at `0x1800a5360`
- `MSVCR100!strcat_s` at `0x1800a5360`
- `MSVCR100!_ultoa_s` at `0x1800a5547`
- `MSVCR100!_ultoa_s` at `0x1800a5547`
- `MSVCR100!atoi` at `0x1800a5228`
- `MSVCR100!atoi` at `0x1800a524e`
- `MSVCR100!atoi` at `0x1800a5228`
- `MSVCR100!atoi` at `0x1800a524e`
- `MSVCR100!strrchr` at `0x1800a5480`
- `MSVCR100!strrchr` at `0x1800a5556`
- `MSVCR100!strrchr` at `0x1800a55fb`
- `MSVCR100!strrchr` at `0x1800a5480`
- `MSVCR100!strrchr` at `0x1800a5556`
- `MSVCR100!strrchr` at `0x1800a55fb`
- `KERNEL32!lstrcpyA` at `0x1800a5471`
- `KERNEL32!lstrcpyA` at `0x1800a54cd`
- `KERNEL32!lstrcpyA` at `0x1800a56e6`
- `KERNEL32!lstrcpyA` at `0x1800a5751`
- `KERNEL32!lstrcpyA` at `0x1800a5471`
- `KERNEL32!lstrcpyA` at `0x1800a54cd`
- `KERNEL32!lstrcpyA` at `0x1800a56e6`
- `KERNEL32!lstrcpyA` at `0x1800a5751`
- `KERNEL32!FreeLibrary` at `0x1800a5763`
- `KERNEL32!FreeLibrary` at `0x1800a5763`
- `KERNEL32!GetLocaleInfoA` at `0x1800a5617`
- `KERNEL32!GetLocaleInfoA` at `0x1800a5617`
- `USER32!LoadStringA` at `0x1800a56b0`
- `USER32!LoadStringA` at `0x1800a571c`
- `USER32!LoadStringA` at `0x1800a56b0`
- `USER32!LoadStringA` at `0x1800a571c`
- `USER32!wsprintfA` at `0x1800a559f`
- `USER32!wsprintfA` at `0x1800a55d3`
- `USER32!wsprintfA` at `0x1800a563d`
- `USER32!wsprintfA` at `0x1800a5669`
- `USER32!wsprintfA` at `0x1800a559f`
- `USER32!wsprintfA` at `0x1800a55d3`
- `USER32!wsprintfA` at `0x1800a563d`
- `USER32!wsprintfA` at `0x1800a5669`
- `USER32!CharNextA` at `0x1800a521f`
- `USER32!CharNextA` at `0x1800a5245`
- `USER32!CharNextA` at `0x1800a5564`
- `USER32!CharNextA` at `0x1800a521f`
- `USER32!CharNextA` at `0x1800a5245`
- `USER32!CharNextA` at `0x1800a5564`
- `ADVAPI32!RegOpenKeyA` at `0x1800a5378`
- `ADVAPI32!RegOpenKeyA` at `0x1800a5378`
- `ADVAPI32!RegCloseKey` at `0x1800a544c`
- `ADVAPI32!RegCloseKey` at `0x1800a544c`
- `ADVAPI32!RegQueryValueA` at `0x1800a53aa`
- `ADVAPI32!RegQueryValueA` at `0x1800a53dc`
- `ADVAPI32!RegQueryValueA` at `0x1800a540a`
- `ADVAPI32!RegQueryValueA` at `0x1800a5438`
- `ADVAPI32!RegQueryValueA` at `0x1800a53aa`
- `ADVAPI32!RegQueryValueA` at `0x1800a53dc`
- `ADVAPI32!RegQueryValueA` at `0x1800a540a`
- `ADVAPI32!RegQueryValueA` at `0x1800a5438`

## string_xrefs

- `0x1800a533b`: `SOFTWARE\Classes\CLSID\`
- `0x1800a562d`: `%s\%s%s.DLL`

## pseudocode

```c
__int64 __fastcall VBAddIn::EnsureStringsLoaded(VBAddIn *this)
{
  __int64 v1; // rdi
  const CHAR *v3; // rcx
  int v4; // r14d
  int v5; // r12d
  int v6; // esi
  UINT v7; // r13d
  UINT v8; // r15d
  const char *v9; // rax
  const CHAR *v10; // rcx
  const char *v11; // rax
  unsigned __int64 v12; // r9
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  void *v15; // rsp
  void *v16; // rsp
  LSTATUS v17; // eax
  LSTATUS v18; // eax
  LSTATUS v19; // eax
  LSTATUS v20; // eax
  LSTATUS v21; // eax
  CHAR *v22; // rax
  char *v23; // rax
  unsigned __int64 v24; // rax
  void *v25; // rcx
  CHAR *v26; // rax
  const CHAR *v27; // rdi
  __int64 v28; // rax
  __int64 v29; // rcx
  unsigned int v30; // ecx
  char *v31; // rax
  LPSTR v32; // rax
  const char *v33; // rcx
  HMODULE Library; // rdi
  CHAR *v35; // rax
  CHAR *v36; // rsi
  int StringA; // eax
  __int64 v38; // r15
  void *v39; // rcx
  CHAR *v40; // rax
  CHAR *v41; // rax
  CHAR *v42; // rsi
  int v43; // eax
  __int64 v44; // r15
  void *v45; // rcx
  CHAR *v46; // rax
  HKEY phkResult; // [rsp+30h] [rbp+0h] BYREF
  struct _GUID v49; // [rsp+38h] [rbp+8h] BYREF
  LONG cbData; // [rsp+48h] [rbp+18h] BYREF
  char v51; // [rsp+4Ch] [rbp+1Ch]
  CHAR LCData[8]; // [rsp+50h] [rbp+20h] BYREF
  char Source[2]; // [rsp+58h] [rbp+28h] BYREF
  _BYTE v54[38]; // [rsp+5Ah] [rbp+2Ah] BYREF
  CHAR Data[2]; // [rsp+80h] [rbp+50h] BYREF
  char v56[2046]; // [rsp+82h] [rbp+52h] BYREF
  char Destination[2]; // [rsp+880h] [rbp+850h] BYREF
  _BYTE v58[2046]; // [rsp+882h] [rbp+852h] BYREF

  v1 = -1;
  v3 = (const CHAR *)*((_QWORD *)this + 11);
  v4 = 0;
  v5 = 0;
  v6 = 0;
  v7 = -1;
  v8 = -1;
  if ( v3 && *v3 == 35 )
  {
    v9 = CharNextA(v3);
    v5 = 1;
    v7 = atoi(v9);
  }
  v10 = (const CHAR *)*((_QWORD *)this + 10);
  if ( v10 && *v10 == 35 )
  {
    v11 = CharNextA(v10);
    v6 = 1;
    v8 = atoi(v11);
  }
  if ( *((_QWORD *)this + 13) )
  {
    if ( *((_QWORD *)this + 12) )
    {
LABEL_28:
      if ( *((_QWORD *)this + 12) && *((_QWORD *)this + 13) )
      {
        v27 = "%s\\%s\\%s\\%s";
        *(_WORD *)Data = 0;
        memset_0(v56, 0, sizeof(v56));
        v51 = 0;
        v28 = *((_QWORD *)this + 18);
        cbData = 0;
        v29 = *(_QWORD *)(v28 + 352);
        if ( v29 )
          v30 = *(_DWORD *)(v29 + 24);
        else
          v30 = Rby_lcidIDE;
        _ultoa_s(v30, (char *)&cbData, 5u, 10);
        v31 = strrchr(*((const char **)this + 12), 92);
        if ( v31 )
        {
          v32 = CharNextA(v31);
          v33 = "%s%s\\%s\\%s";
          if ( *v32 )
            v33 = "%s\\%s\\%s\\%s";
          v27 = v33;
        }
        wsprintfA(Data, v27, *((_QWORD *)this + 12), "resources", &cbData, *((_QWORD *)this + 13));
        Library = (HMODULE)IsolationAwareLoadLibraryExA(Data, 0, 2);
        if ( Library
          || (wsprintfA(Data, "%s\\%s", *((const char **)this + 12), *((const char **)this + 13)),
              (Library = (HMODULE)IsolationAwareLoadLibraryExA(Data, 0, 2)) != 0)
          || !strrchr(*((const char **)this + 13), 46)
          && GetLocaleInfoA(Rby_lcidIDE, 3u, LCData, 5)
          && (wsprintfA(Data, "%s\\%s%s.DLL", *((const char **)this + 12), *((const char **)this + 13), LCData),
              (Library = (HMODULE)IsolationAwareLoadLibraryExA(Data, 0, 2)) != 0)
          || (wsprintfA(Data, "%s", *((const char **)this + 14)),
              (Library = (HMODULE)IsolationAwareLoadLibraryExA(Data, 0, 2)) != 0) )
        {
          if ( v6 )
          {
            v35 = (CHAR *)malloc(0x800u);
            v36 = v35;
            if ( v35 )
            {
              StringA = LoadStringA(Library, v8, v35, 500);
              v38 = StringA;
              if ( StringA )
              {
                v39 = (void *)*((_QWORD *)this + 10);
                if ( v39 )
                  free(v39);
                v40 = (CHAR *)malloc(v38 + 2);
                *((_QWORD *)this + 10) = v40;
                if ( v40 )
                  lstrcpyA(v40, v36);
              }
              free(v36);
            }
          }
          if ( v5 )
          {
            v41 = (CHAR *)malloc(0x800u);
            v42 = v41;
            if ( v41 )
            {
              v43 = LoadStringA(Library, v7, v41, 500);
              v44 = v43;
              if ( v43 )
              {
                v45 = (void *)*((_QWORD *)this + 11);
                if ( v45 )
                  free(v45);
                v46 = (CHAR *)malloc(v44 + 2);
                *((_QWORD *)this + 11) = v46;
                if ( v46 )
                  lstrcpyA(v46, v42);
              }
              free(v42);
            }
          }
          FreeLibrary(Library);
        }
      }
      return (unsigned int)v4;
    }
    phkResult = 0;
    *(_WORD *)Destination = 0;
    memset_0(v58, 0, sizeof(v58));
    *(_WORD *)Data = 0;
    memset_0(v56, 0, sizeof(v56));
    *(_WORD *)Source = 0;
    memset_0(v54, 0, sizeof(v54));
    v12 = *((_QWORD *)this + 9);
    if ( (v12 & 0xFFFFFFFFFFFF0000uLL) != 0 )
    {
      do
        ++v1;
      while ( *(_BYTE *)(v12 + v1) );
      v13 = 2 * v1 + 17;
      if ( v13 <= 2 * v1 + 2 )
        v13 = 0xFFFFFFFFFFFFFF0LL;
      v14 = v13 & 0xFFFFFFFFFFFFFFF0uLL;
      v15 = alloca(v14);
      v16 = alloca(v14);
      v12 = (unsigned __int64)strcpyWfromA((wchar_t *)&phkResult, *((const char **)this + 9));
    }
    v4 = VBCLSIDFromProgID((const wchar_t *)v12, &v49);
    if ( v4 >= 0 )
    {
      StringFromGUID2Ansi(&v49, Source, 40);
      strcpy_s(Destination, 0x800u, "SOFTWARE\\Classes\\CLSID\\");
      strcat_s(Destination, 0x800u, Source);
      v17 = RegOpenKeyA(HKEY_LOCAL_MACHINE, Destination, &phkResult);
      v4 = HrFromRegError(v17);
      if ( v4 >= 0 )
      {
        cbData = 2048;
        v18 = RegQueryValueA(phkResult, "LocalServer32", Data, &cbData);
        v4 = HrFromRegError(v18);
        if ( v4 < 0 )
        {
          cbData = 2048;
          v19 = RegQueryValueA(phkResult, "InprocServer32", Data, &cbData);
          v4 = HrFromRegError(v19);
          if ( v4 < 0 )
          {
            cbData = 2048;
            v20 = RegQueryValueA(phkResult, "LocalServer", Data, &cbData);
            v4 = HrFromRegError(v20);
            if ( v4 < 0 )
            {
              cbData = 2048;
              v21 = RegQueryValueA(phkResult, "InprocServer", Data, &cbData);
              v4 = HrFromRegError(v21);
            }
          }
        }
        RegCloseKey(phkResult);
        if ( v4 >= 0 )
        {
          v22 = (CHAR *)malloc(0x800u);
          *((_QWORD *)this + 14) = v22;
          lstrcpyA(v22, Data);
          v23 = strrchr(Data, 92);
          if ( v23 )
          {
            v24 = v23 - Data;
            if ( v24 >= 0x800 )
              _report_gsfailure(0);
            v25 = (void *)*((_QWORD *)this + 12);
            Data[v24] = 0;
            if ( v25 )
            {
              free(v25);
              *((_QWORD *)this + 12) = 0;
            }
            v26 = (CHAR *)malloc(0x800u);
            *((_QWORD *)this + 12) = v26;
            if ( v26 )
              lstrcpyA(v26, Data);
          }
        }
      }
      goto LABEL_28;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800a51b8  push    rbp
0x1800a51ba  push    r12
0x1800a51bc  push    r13
0x1800a51be  push    r14
0x1800a51c0  push    r15
0x1800a51c2  mov     eax, 1090h
0x1800a51c7  call    _alloca_probe
0x1800a51cc  sub     rsp, rax
0x1800a51cf  lea     rbp, [rsp+30h]
0x1800a51d4  mov     [rbp+1080h+arg_8], rbx
0x1800a51db  mov     [rbp+1080h+arg_10], rsi
0x1800a51e2  mov     [rbp+1080h+arg_18], rdi
0x1800a51e9  mov     rax, cs:__security_cookie
0x1800a51f0  xor     rax, rbp
0x1800a51f3  mov     [rbp+1080h+var_30], rax
0x1800a51fa  xor     eax, eax
0x1800a51fc  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800a5200  mov     rbx, rcx
0x1800a5203  mov     rcx, [rcx+58h]; lpsz
0x1800a5207  mov     r14d, eax
0x1800a520a  mov     r12d, eax
0x1800a520d  mov     esi, eax
0x1800a520f  mov     r13d, edi
0x1800a5212  mov     r15d, edi
0x1800a5215  test    rcx, rcx
0x1800a5218  jz      short loc_1800A5237
0x1800a521a  cmp     byte ptr [rcx], 23h ; '#'
0x1800a521d  jnz     short loc_1800A5237
0x1800a521f  call    cs:__imp_CharNextA
0x1800a5225  mov     rcx, rax; String
0x1800a5228  call    cs:__imp_atoi
0x1800a522e  lea     r12d, [rdi+2]
0x1800a5232  mov     r13d, eax
0x1800a5235  xor     eax, eax
0x1800a5237  mov     rcx, [rbx+50h]; lpsz
0x1800a523b  test    rcx, rcx
0x1800a523e  jz      short loc_1800A525E
0x1800a5240  cmp     byte ptr [rcx], 23h ; '#'
0x1800a5243  jnz     short loc_1800A525E
0x1800a5245  call    cs:__imp_CharNextA
0x1800a524b  mov     rcx, rax; String
0x1800a524e  call    cs:__imp_atoi
0x1800a5254  mov     esi, 1
0x1800a5259  mov     r15d, eax
0x1800a525c  xor     eax, eax
0x1800a525e  cmp     [rbx+68h], rax
0x1800a5262  jz      loc_1800A5769
0x1800a5268  cmp     [rbx+60h], rax
0x1800a526c  jnz     loc_1800A54DD
0x1800a5272  lea     rcx, [rbp+1080h+var_82E]; void *
0x1800a5279  xor     edx, edx; Val
0x1800a527b  mov     r8d, 7FEh; Size
0x1800a5281  mov     [rbp+1080h+phkResult], rax
0x1800a5285  mov     word ptr [rbp+1080h+Destination], ax
0x1800a528c  call    memset_0
0x1800a5291  lea     rcx, [rbp+1080h+var_102E]; void *
0x1800a5295  xor     edx, edx; Val
0x1800a5297  mov     r8d, 7FEh; Size
0x1800a529d  mov     word ptr [rbp+1080h+Data], r14w
0x1800a52a2  call    memset_0
0x1800a52a7  xor     edx, edx; Val
0x1800a52a9  lea     rcx, [rbp+1080h+var_1056]; void *
0x1800a52ad  lea     r8d, [rdx+26h]; Size
0x1800a52b1  mov     word ptr [rbp+1080h+Source], r14w
0x1800a52b6  call    memset_0
0x1800a52bb  mov     r9, [rbx+48h]
0x1800a52bf  test    r9, 0FFFFFFFFFFFF0000h
0x1800a52c6  jz      short loc_1800A530B
0x1800a52c8  inc     rdi
0x1800a52cb  cmp     [r9+rdi], r14b
0x1800a52cf  jnz     short loc_1800A52C8
0x1800a52d1  lea     rax, ds:2[rdi*2]
0x1800a52d9  lea     rcx, [rax+0Fh]
0x1800a52dd  cmp     rcx, rax
0x1800a52e0  ja      short loc_1800A52EC
0x1800a52e2  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800a52ec  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800a52f0  mov     rax, rcx
0x1800a52f3  call    _alloca_probe
0x1800a52f8  sub     rsp, rcx
0x1800a52fb  mov     rdx, r9; char *
0x1800a52fe  lea     rcx, [rsp+10B0h+phkResult]; wchar_t *
0x1800a5303  call    ?strcpyWfromA@@YAPEA_WPEA_WPEBD@Z; strcpyWfromA(wchar_t *,char const *)
0x1800a5308  mov     r9, rax
0x1800a530b  lea     rdx, [rbp+1080h+var_1078]; struct _GUID *
0x1800a530f  mov     rcx, r9; wchar_t *
0x1800a5312  call    ?VBCLSIDFromProgID@@YAJPEB_WPEAU_GUID@@@Z; VBCLSIDFromProgID(wchar_t const *,_GUID *)
0x1800a5317  xor     edi, edi
0x1800a5319  mov     r14d, eax
0x1800a531c  test    eax, eax
0x1800a531e  js      loc_1800A5769
0x1800a5324  lea     r8d, [rdi+28h]; int
0x1800a5328  lea     rdx, [rbp+1080h+Source]; char *
0x1800a532c  lea     rcx, [rbp+1080h+var_1078]; struct _GUID *
0x1800a5330  call    ?StringFromGUID2Ansi@@YAHAEBU_GUID@@PEADH@Z; StringFromGUID2Ansi(_GUID const &,char *,int)
0x1800a5335  mov     r14d, 800h
0x1800a533b  lea     r8, aSoftwareClasse; "SOFTWARE\\Classes\\CLSID\\"
0x1800a5342  lea     rcx, [rbp+1080h+Destination]; Destination
0x1800a5349  mov     edx, r14d; SizeInBytes
0x1800a534c  call    cs:__imp_strcpy_s
0x1800a5352  lea     r8, [rbp+1080h+Source]; Source
0x1800a5356  lea     rcx, [rbp+1080h+Destination]; Destination
0x1800a535d  mov     edx, r14d; SizeInBytes
0x1800a5360  call    cs:__imp_strcat_s
0x1800a5366  lea     r8, [rbp+1080h+phkResult]; phkResult
0x1800a536a  lea     rdx, [rbp+1080h+Destination]; lpSubKey
0x1800a5371  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a5378  call    cs:__imp_RegOpenKeyA
0x1800a537e  mov     ecx, eax; int
0x1800a5380  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x1800a5385  mov     r14d, eax
0x1800a5388  test    eax, eax
0x1800a538a  js      loc_1800A54DF
0x1800a5390  mov     rcx, [rbp+1080h+phkResult]; hKey
0x1800a5394  lea     r9, [rbp+1080h+cbData]; lpcbData
0x1800a5398  lea     r8, [rbp+1080h+Data]; lpData
0x1800a539c  lea     rdx, aLocalserver32; "LocalServer32"
0x1800a53a3  mov     [rbp+1080h+cbData], 800h
0x1800a53aa  call    cs:__imp_RegQueryValueA
0x1800a53b0  mov     ecx, eax; int
0x1800a53b2  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x1800a53b7  mov     r14d, eax
0x1800a53ba  test    eax, eax
0x1800a53bc  jns     loc_1800A5448
0x1800a53c2  mov     rcx, [rbp+1080h+phkResult]; hKey
0x1800a53c6  lea     r9, [rbp+1080h+cbData]; lpcbData
0x1800a53ca  lea     r8, [rbp+1080h+Data]; lpData
0x1800a53ce  lea     rdx, aInprocserver32; "InprocServer32"
0x1800a53d5  mov     [rbp+1080h+cbData], 800h
0x1800a53dc  call    cs:__imp_RegQueryValueA
0x1800a53e2  mov     ecx, eax; int
0x1800a53e4  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x1800a53e9  mov     r14d, eax
0x1800a53ec  test    eax, eax
0x1800a53ee  jns     short loc_1800A5448
0x1800a53f0  mov     rcx, [rbp+1080h+phkResult]; hKey
0x1800a53f4  lea     r9, [rbp+1080h+cbData]; lpcbData
0x1800a53f8  lea     r8, [rbp+1080h+Data]; lpData
0x1800a53fc  lea     rdx, aLocalserver; "LocalServer"
0x1800a5403  mov     [rbp+1080h+cbData], 800h
0x1800a540a  call    cs:__imp_RegQueryValueA
0x1800a5410  mov     ecx, eax; int
0x1800a5412  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x1800a5417  mov     r14d, eax
0x1800a541a  test    eax, eax
0x1800a541c  jns     short loc_1800A5448
0x1800a541e  mov     rcx, [rbp+1080h+phkResult]; hKey
0x1800a5422  lea     r9, [rbp+1080h+cbData]; lpcbData
0x1800a5426  lea     r8, [rbp+1080h+Data]; lpData
0x1800a542a  lea     rdx, aInprocserver; "InprocServer"
0x1800a5431  mov     [rbp+1080h+cbData], 800h
0x1800a5438  call    cs:__imp_RegQueryValueA
0x1800a543e  mov     ecx, eax; int
0x1800a5440  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x1800a5445  mov     r14d, eax
0x1800a5448  mov     rcx, [rbp+1080h+phkResult]; hKey
0x1800a544c  call    cs:__imp_RegCloseKey
0x1800a5452  test    r14d, r14d
0x1800a5455  js      loc_1800A54DF
0x1800a545b  mov     ecx, 800h; Size
0x1800a5460  call    cs:__imp_malloc
0x1800a5466  lea     rdx, [rbp+1080h+Data]; lpString2
0x1800a546a  mov     rcx, rax; lpString1
0x1800a546d  mov     [rbx+70h], rax
0x1800a5471  call    cs:__imp_lstrcpyA
0x1800a5477  lea     rcx, [rbp+1080h+Data]; Str
0x1800a547b  mov     edx, 5Ch ; '\'; Ch
0x1800a5480  call    cs:__imp_strrchr
0x1800a5486  test    rax, rax
0x1800a5489  jz      short loc_1800A54DF
0x1800a548b  lea     rcx, [rbp+1080h+Data]
0x1800a548f  sub     rax, rcx
0x1800a5492  cmp     rax, 800h
0x1800a5498  jnb     short loc_1800A54D5
0x1800a549a  mov     rcx, [rbx+60h]; Block
0x1800a549e  mov     [rbp+rax+1080h+Data], dil
0x1800a54a3  test    rcx, rcx
0x1800a54a6  jz      short loc_1800A54B2
0x1800a54a8  call    cs:__imp_free
0x1800a54ae  mov     [rbx+60h], rdi
0x1800a54b2  mov     ecx, 800h; Size
0x1800a54b7  call    cs:__imp_malloc
0x1800a54bd  mov     [rbx+60h], rax
0x1800a54c1  test    rax, rax
0x1800a54c4  jz      short loc_1800A54DF
0x1800a54c6  lea     rdx, [rbp+1080h+Data]; lpString2
0x1800a54ca  mov     rcx, rax; lpString1
0x1800a54cd  call    cs:__imp_lstrcpyA
0x1800a54d3  jmp     short loc_1800A54DF
0x1800a54d5  xor     ecx, ecx; StackCookie
0x1800a54d7  call    __report_gsfailure
0x1800a54dd  xor     edi, edi
0x1800a54df  cmp     [rbx+60h], rdi
0x1800a54e3  jz      loc_1800A5769
0x1800a54e9  cmp     [rbx+68h], rdi
0x1800a54ed  jz      loc_1800A5769
0x1800a54f3  xor     eax, eax
0x1800a54f5  lea     rcx, [rbp+1080h+var_102E]; void *
0x1800a54f9  xor     edx, edx; Val
0x1800a54fb  mov     r8d, 7FEh; Size
0x1800a5501  lea     rdi, aSSSS; "%s\\%s\\%s\\%s"
0x1800a5508  mov     word ptr [rbp+1080h+Data], ax
0x1800a550c  call    memset_0
0x1800a5511  xor     eax, eax
0x1800a5513  xor     edx, edx
0x1800a5515  mov     [rbp+1080h+var_1064], al
0x1800a5518  mov     rax, [rbx+90h]
0x1800a551f  mov     [rbp+1080h+cbData], edx
0x1800a5522  mov     rcx, [rax+160h]
0x1800a5529  test    rcx, rcx
0x1800a552c  jz      short loc_1800A5533
0x1800a552e  mov     ecx, [rcx+18h]
0x1800a5531  jmp     short loc_1800A5539
0x1800a5533  mov     ecx, cs:?Rby_lcidIDE@@3KA; Value
0x1800a5539  mov     r9d, 0Ah; Radix
0x1800a553f  lea     rdx, [rbp+1080h+cbData]; Buffer
0x1800a5543  lea     r8d, [r9-5]; BufferCount
0x1800a5547  call    cs:__imp__ultoa_s
0x1800a554d  mov     rcx, [rbx+60h]; Str
0x1800a5551  mov     edx, 5Ch ; '\'; Ch
0x1800a5556  call    cs:__imp_strrchr
0x1800a555c  test    rax, rax
0x1800a555f  jz      short loc_1800A557B
0x1800a5561  mov     rcx, rax; lpsz
0x1800a5564  call    cs:__imp_CharNextA
0x1800a556a  lea     rcx, aSSSS_0; "%s%s\\%s\\%s"
0x1800a5571  cmp     byte ptr [rax], 0
0x1800a5574  cmovnz  rcx, rdi
0x1800a5578  mov     rdi, rcx
0x1800a557b  mov     rax, [rbx+68h]
0x1800a557f  mov     r8, [rbx+60h]
0x1800a5583  lea     r9, aResources; "resources"
0x1800a558a  mov     [rsp+10B0h+var_1088], rax
0x1800a558f  lea     rax, [rbp+1080h+cbData]
0x1800a5593  lea     rcx, [rbp+1080h+Data]; LPSTR
0x1800a5597  mov     rdx, rdi; LPCSTR
0x1800a559a  mov     [rsp+10B0h+var_1090], rax
0x1800a559f  call    cs:__imp_wsprintfA
0x1800a55a5  xor     edx, edx
0x1800a55a7  lea     rcx, [rbp+1080h+Data]
0x1800a55ab  lea     r8d, [rdx+2]
0x1800a55af  call    IsolationAwareLoadLibraryExA
0x1800a55b4  mov     rdi, rax
0x1800a55b7  test    rax, rax
0x1800a55ba  jnz     loc_1800A568A
0x1800a55c0  mov     r9, [rbx+68h]
0x1800a55c4  mov     r8, [rbx+60h]
0x1800a55c8  lea     rdx, aSS_1; "%s\\%s"
0x1800a55cf  lea     rcx, [rbp+1080h+Data]; LPSTR
0x1800a55d3  call    cs:__imp_wsprintfA
0x1800a55d9  lea     r8d, [rdi+2]
0x1800a55dd  lea     rcx, [rbp+1080h+Data]
0x1800a55e1  xor     edx, edx
0x1800a55e3  call    IsolationAwareLoadLibraryExA
0x1800a55e8  mov     rdi, rax
0x1800a55eb  test    rax, rax
0x1800a55ee  jnz     loc_1800A568A
0x1800a55f4  mov     rcx, [rbx+68h]; Str
0x1800a55f8  lea     edx, [rax+2Eh]; Ch
0x1800a55fb  call    cs:__imp_strrchr
0x1800a5601  test    rax, rax
0x1800a5604  jnz     short loc_1800A565A
0x1800a5606  mov     ecx, cs:?Rby_lcidIDE@@3KA; Locale
0x1800a560c  lea     r9d, [rdi+5]; cchData
0x1800a5610  lea     r8, [rbp+1080h+LCData]; lpLCData
0x1800a5614  lea     edx, [rdi+3]; LCType
0x1800a5617  call    cs:__imp_GetLocaleInfoA
0x1800a561d  test    eax, eax
0x1800a561f  jz      short loc_1800A565A
0x1800a5621  mov     r9, [rbx+68h]
0x1800a5625  mov     r8, [rbx+60h]
0x1800a5629  lea     rax, [rbp+1080h+LCData]
0x1800a562d  lea     rdx, aSSSDll; "%s\\%s%s.DLL"
0x1800a5634  lea     rcx, [rbp+1080h+Data]; LPSTR
0x1800a5638  mov     [rsp+10B0h+var_1090], rax
0x1800a563d  call    cs:__imp_wsprintfA
0x1800a5643  lea     r8d, [rdi+2]
0x1800a5647  lea     rcx, [rbp+1080h+Data]
0x1800a564b  xor     edx, edx
0x1800a564d  call    IsolationAwareLoadLibraryExA
0x1800a5652  mov     rdi, rax
0x1800a5655  test    rax, rax
0x1800a5658  jnz     short loc_1800A568A
0x1800a565a  mov     r8, [rbx+70h]
0x1800a565e  lea     rdx, aS_8; "%s"
0x1800a5665  lea     rcx, [rbp+1080h+Data]; LPSTR
0x1800a5669  call    cs:__imp_wsprintfA
0x1800a566f  xor     edx, edx
0x1800a5671  lea     rcx, [rbp+1080h+Data]
0x1800a5675  lea     r8d, [rdx+2]
0x1800a5679  call    IsolationAwareLoadLibraryExA
0x1800a567e  mov     rdi, rax
0x1800a5681  test    rax, rax
0x1800a5684  jz      loc_1800A5769
0x1800a568a  test    esi, esi
0x1800a568c  jz      short loc_1800A56F5
0x1800a568e  mov     ecx, 800h; Size
0x1800a5693  call    cs:__imp_malloc
0x1800a5699  mov     rsi, rax
0x1800a569c  test    rax, rax
  ... truncated ...
```
