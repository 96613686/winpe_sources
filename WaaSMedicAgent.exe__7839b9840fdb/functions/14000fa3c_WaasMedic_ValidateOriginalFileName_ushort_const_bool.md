# WaasMedic::ValidateOriginalFileName(ushort const *,bool &)

- ea: `0x14000fa3c`
- end: `0x14000fe69`
- name: `?ValidateOriginalFileName@WaasMedic@@YAJPEBGAEA_N@Z`
- size: `1069`
- prototype: `__int64 __fastcall(LPCWSTR lpwstrFilename, unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update`

## callers

- `0x14000f744`

## callees

- `0x140002a30`
- `0x140003708`
- `0x140004290`
- `0x140004670`
- `0x140009960`
- `0x14000b470`
- `0x14000ea60`
- `0x14000efd4`
- `0x14000f228`
- `0x14000f27c`
- `0x14000f34c`
- `0x14000fa3c`
- `0x14000fe70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000fd9c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000fd9c`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x14000fb48`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x14000fb48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fc5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fcc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fc5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fcc7`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x14000fc53`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x14000fc53`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x14000fcbd`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x14000fcbd`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x14000fd0c`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x14000fd62`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x14000fd0c`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x14000fd62`

## string_xrefs

- `0x14000fe01`: `Caller passed library name that did not end in "dll".`

## pseudocode

```c
__int64 __fastcall WaasMedic::ValidateOriginalFileName(LPCWSTR lpwstrFilename, unsigned __int16 *a2, bool *a3)
{
  unsigned __int64 v5; // r8
  __int128 *v7; // rsi
  __int128 *v8; // rdx
  unsigned __int16 *v9; // r15
  unsigned __int16 *v10; // rbx
  const wchar_t *v11; // rdx
  const wchar_t *v12; // rax
  __int64 last_of; // rax
  __int64 v14; // rcx
  unsigned __int64 v15; // r8
  __int128 *v16; // rax
  DWORD FileVersionInfoSize; // eax
  DWORD v18; // ebx
  signed int v19; // eax
  unsigned int v20; // ebx
  void *v21; // rax
  void *v22; // rsi
  signed int LastError; // eax
  void *v24; // rdx
  unsigned __int16 *v25; // rcx
  char **v26; // rcx
  int v27; // eax
  char **v28; // r8
  LPVOID lpData; // [rsp+28h] [rbp-E0h]
  DWORD dwHandle; // [rsp+38h] [rbp-D0h] BYREF
  unsigned int puLen; // [rsp+3Ch] [rbp-CCh] BYREF
  __int64 v32; // [rsp+40h] [rbp-C8h] BYREF
  LPVOID lpBuffer; // [rsp+48h] [rbp-C0h] BYREF
  LPVOID v34[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v35; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v36; // [rsp+70h] [rbp-98h]
  char *v37[3]; // [rsp+80h] [rbp-88h] BYREF
  unsigned __int64 v38; // [rsp+98h] [rbp-70h]
  wchar_t *S2[2]; // [rsp+A0h] [rbp-68h] BYREF
  size_t N; // [rsp+B0h] [rbp-58h]
  unsigned __int64 v41; // [rsp+B8h] [rbp-50h]
  _OWORD v42[2]; // [rsp+C0h] [rbp-48h] BYREF
  wchar_t Buffer[256]; // [rsp+E8h] [rbp-20h] BYREF

  v34[1] = (LPVOID)-2LL;
  *(_BYTE *)a2 = 0;
  v34[0] = 0;
  dwHandle = 0;
  v35 = 0;
  v36 = 0;
  v5 = -1;
  do
    ++v5;
  while ( lpwstrFilename[v5] );
  std::wstring::_Construct<1,unsigned short const *>((char **)&v35, lpwstrFilename, v5);
  std::wstring::wstring(v37, &v35);
  lpBuffer = 0;
  LODWORD(v32) = 78644233;
  puLen = 0;
  if ( !lpwstrFilename )
  {
    LogLevelW(2u, L"Caller passed null parameter to ValidateOriginalFileName.");
    std::wstring::~wstring(v37);
    std::wstring::~wstring((char **)&v35);
    return 2147500035LL;
  }
  if ( *((_QWORD *)&v36 + 1) > 7u )
  {
    v7 = (__int128 *)v35;
    v8 = (__int128 *)v35;
  }
  else
  {
    v7 = &v35;
    v8 = &v35;
  }
  v9 = (unsigned __int16 *)v8 + v36;
  v10 = (unsigned __int16 *)&v35;
  if ( *((_QWORD *)&v36 + 1) > 7u )
    v10 = (unsigned __int16 *)v35;
  while ( v10 != v9 )
  {
    *(_WORD *)v7 = _o_tolower(*v10);
    v7 = (__int128 *)((char *)v7 + 2);
    ++v10;
  }
  *(_OWORD *)S2 = 0;
  N = 0;
  v41 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)S2, L".dll", 4u);
  if ( (unsigned __int64)v36 <= N )
    goto LABEL_53;
  if ( (unsigned __int64)v36 < N )
    goto LABEL_54;
  v11 = (const wchar_t *)S2;
  if ( v41 > 7 )
    v11 = S2[0];
  v12 = (const wchar_t *)&v35;
  if ( *((_QWORD *)&v36 + 1) > 7u )
    v12 = (const wchar_t *)v35;
  if ( wmemcmp(&v12[v36 - N], v11, N) )
  {
LABEL_53:
    LogLevelW(2u, L"Caller passed library name that did not end in \"dll\".");
    std::wstring::~wstring((char **)S2);
    std::wstring::~wstring(v37);
    std::wstring::~wstring((char **)&v35);
    return 2147942487LL;
  }
  last_of = std::wstring::find_last_of(&v35);
  if ( last_of != -1 )
  {
    v14 = last_of + 1;
    memset(v42, 0, sizeof(v42));
    if ( (unsigned __int64)v36 >= last_of + 1 )
    {
      v15 = v36 - v14;
      if ( (__int64)v36 - v14 >= (unsigned __int64)(v36 - 1) )
        v15 = v36 - 1;
      v16 = &v35;
      if ( *((_QWORD *)&v36 + 1) > 7u )
        v16 = (__int128 *)v35;
      std::wstring::_Construct<1,unsigned short const *>((char **)v42, (char *)v16 + 2 * v14, v15);
      std::wstring::operator=(v37, v42);
      std::wstring::~wstring((char **)v42);
      goto LABEL_27;
    }
LABEL_54:
    std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
  }
LABEL_27:
  FileVersionInfoSize = GetFileVersionInfoSizeExW(0, lpwstrFilename, &dwHandle);
  v18 = FileVersionInfoSize;
  if ( FileVersionInfoSize )
  {
    v21 = WaasMedic::SafeAlloc((WaasMedic *)FileVersionInfoSize);
    v22 = v21;
    if ( v21 )
    {
      if ( GetFileVersionInfoExW(0, lpwstrFilename, dwHandle, v18, v21) )
      {
        v20 = 0;
        if ( VerQueryValueW(v22, L"\\VarFileInfo\\Translation", &lpBuffer, &puLen) )
        {
          v25 = (unsigned __int16 *)lpBuffer;
        }
        else
        {
          v25 = (unsigned __int16 *)&v32;
          lpBuffer = &v32;
        }
        if ( v25 )
        {
          LODWORD(lpData) = v25[1];
          swprintf_s(Buffer, 0xFEu, L"\\StringFileInfo\\%04x%04x\\OriginalFilename", *v25, lpData);
          if ( VerQueryValueW(v22, Buffer, v34, &puLen) )
          {
            v24 = v34[0];
            if ( v34[0] )
            {
              v26 = v37;
              if ( v38 > 7 )
                v26 = (char **)v37[0];
              v27 = _o__wcsicmp(v26, v34[0]);
              *(_BYTE *)a2 = v27 == 0;
              if ( v27 )
              {
                v28 = v37;
                if ( v38 > 7 )
                  v28 = (char **)v37[0];
                LogLevelW(2u, L"Expected: %ws Found: %ws", v28, v34[0]);
              }
            }
          }
          else
          {
            LogLevelW(2u, L"The original file name could not be retrieved.");
            v20 = -2147467259;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v20 = LastError;
        if ( LastError > 0 )
          v20 = (unsigned __int16)LastError | 0x80070000;
        LogLevelW(2u, L"Error trying to get the file version info. hr = 0x%08X", v20);
      }
      WaasMedic::SafeFree((WaasMedic *)v22, v24);
    }
    else
    {
      v20 = -2147024882;
      LogLevelW(2u, L"Failed to allocate memory for file version info. hr = 0x%08X", 2147942414LL);
    }
  }
  else
  {
    v19 = GetLastError();
    v20 = v19;
    if ( v19 > 0 )
      v20 = (unsigned __int16)v19 | 0x80070000;
    LogLevelW(2u, L"Error trying to get the file version info size. hr = 0x%08X", v20);
  }
  std::wstring::~wstring((char **)S2);
  std::wstring::~wstring(v37);
  std::wstring::~wstring((char **)&v35);
  return v20;
}

```

## disassembly

```asm
0x14000fa3c  mov     rax, rsp
0x14000fa3f  push    rbp
0x14000fa40  push    r12
0x14000fa42  push    r13
0x14000fa44  push    r14
0x14000fa46  push    r15
0x14000fa48  lea     rbp, [rax-218h]
0x14000fa4f  sub     rsp, 2F0h
0x14000fa56  mov     qword ptr [rsp+310h+var_2C0], 0FFFFFFFFFFFFFFFEh
0x14000fa5f  mov     [rax+18h], rbx
0x14000fa63  mov     [rax+20h], rsi
0x14000fa67  mov     rax, cs:__security_cookie
0x14000fa6e  xor     rax, rsp
0x14000fa71  mov     [rbp+210h+var_30], rax
0x14000fa78  mov     r12, rdx
0x14000fa7b  mov     r14, rcx
0x14000fa7e  xor     r13d, r13d
0x14000fa81  mov     [rdx], r13b
0x14000fa84  mov     [rsp+310h+var_2C8], r13
0x14000fa89  mov     [rsp+310h+dwHandle], r13d
0x14000fa8e  xorps   xmm0, xmm0
0x14000fa91  movups  [rsp+310h+var_2C0+8], xmm0
0x14000fa96  xorps   xmm1, xmm1
0x14000fa99  movdqu  [rsp+310h+var_2B0+8], xmm1
0x14000fa9f  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000faa3  inc     r8
0x14000faa6  cmp     [rcx+r8*2], r13w
0x14000faab  jnz     short loc_14000FAA3
0x14000faad  mov     rdx, r14
0x14000fab0  lea     rcx, [rsp+310h+var_2C0+8]
0x14000fab5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000faba  nop
0x14000fabb  lea     rdx, [rsp+310h+var_2C0+8]
0x14000fac0  lea     rcx, [rsp+310h+var_298]
0x14000fac5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000faca  nop
0x14000facb  mov     [rsp+310h+lpBuffer], r13
0x14000fad0  mov     dword ptr [rsp+310h+var_2D8], 4B00409h
0x14000fad8  mov     [rsp+310h+puLen], r13d
0x14000fadd  test    r14, r14
0x14000fae0  jnz     short loc_14000FB12
0x14000fae2  lea     rdx, aCallerPassedNu; "Caller passed null parameter to Validat"...
0x14000fae9  lea     ecx, [r14+2]; unsigned __int8
0x14000faed  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x14000faf2  nop
0x14000faf3  lea     rcx, [rsp+310h+var_298]; void *
0x14000faf8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000fafd  nop
0x14000fafe  lea     rcx, [rsp+310h+var_2C0+8]; void *
0x14000fb03  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000fb08  mov     eax, 80004003h
0x14000fb0d  jmp     loc_14000FE37
0x14000fb12  mov     rcx, qword ptr [rsp+310h+var_2C0+8]
0x14000fb17  cmp     [rsp+310h+var_2A0], 7
0x14000fb1d  ja      short loc_14000FB2B
0x14000fb1f  lea     rsi, [rsp+310h+var_2C0+8]
0x14000fb24  lea     rdx, [rsp+310h+var_2C0+8]
0x14000fb29  jmp     short loc_14000FB31
0x14000fb2b  mov     rsi, rcx
0x14000fb2e  mov     rdx, rcx
0x14000fb31  mov     rax, qword ptr [rsp+310h+var_2B0+8]
0x14000fb36  lea     r15, [rdx+rax*2]
0x14000fb3a  lea     rbx, [rsp+310h+var_2C0+8]
0x14000fb3f  cmova   rbx, rcx
0x14000fb43  jmp     short loc_14000FB59
0x14000fb45  movzx   ecx, word ptr [rbx]
0x14000fb48  call    cs:__imp__o_tolower
0x14000fb4e  mov     [rsi], ax
0x14000fb51  lea     rsi, [rsi+2]
0x14000fb55  add     rbx, 2
0x14000fb59  cmp     rbx, r15
0x14000fb5c  jnz     short loc_14000FB45
0x14000fb5e  xorps   xmm0, xmm0
0x14000fb61  movups  xmmword ptr [rbp+210h+S2], xmm0
0x14000fb65  mov     [rbp+210h+N], r13
0x14000fb69  mov     [rbp+210h+var_260], r13
0x14000fb6d  mov     r8d, 4
0x14000fb73  lea     rdx, aDll; ".dll"
0x14000fb7a  lea     rcx, [rbp+210h+S2]
0x14000fb7e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000fb83  nop
0x14000fb84  mov     r8, [rbp+210h+N]; N
0x14000fb88  mov     rax, qword ptr [rsp+310h+var_2B0+8]
0x14000fb8d  cmp     rax, r8
0x14000fb90  jbe     loc_14000FE01
0x14000fb96  mov     rcx, rax
0x14000fb99  sub     rcx, r8
0x14000fb9c  cmp     rax, rcx
0x14000fb9f  jb      loc_14000FE63
0x14000fba5  lea     rdx, [rbp+210h+S2]
0x14000fba9  cmp     [rbp+210h+var_260], 7
0x14000fbae  cmova   rdx, [rbp+210h+S2]; S2
0x14000fbb3  lea     rax, [rsp+310h+var_2C0+8]
0x14000fbb8  cmp     [rsp+310h+var_2A0], 7
0x14000fbbe  cmova   rax, qword ptr [rsp+310h+var_2C0+8]
0x14000fbc4  lea     rcx, [rax+rcx*2]; S1
0x14000fbc8  call    wmemcmp
0x14000fbcd  test    eax, eax
0x14000fbcf  jnz     loc_14000FE01
0x14000fbd5  lea     rcx, [rsp+310h+var_2C0+8]
0x14000fbda  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_last_of(ushort const * const,unsigned __int64)
0x14000fbdf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000fbe3  jz      short loc_14000FC49
0x14000fbe5  mov     r8, qword ptr [rsp+310h+var_2B0+8]
0x14000fbea  lea     rcx, [rax+1]
0x14000fbee  xorps   xmm0, xmm0
0x14000fbf1  movups  [rbp+210h+var_258], xmm0
0x14000fbf5  xorps   xmm1, xmm1
0x14000fbf8  movdqu  [rbp+210h+var_248], xmm1
0x14000fbfd  cmp     r8, rcx
0x14000fc00  jb      loc_14000FE63
0x14000fc06  lea     rax, [r8-1]
0x14000fc0a  sub     r8, rcx
0x14000fc0d  cmp     r8, rax
0x14000fc10  cmovnb  r8, rax
0x14000fc14  lea     rax, [rsp+310h+var_2C0+8]
0x14000fc19  cmp     [rsp+310h+var_2A0], 7
0x14000fc1f  cmova   rax, qword ptr [rsp+310h+var_2C0+8]
0x14000fc25  lea     rdx, [rax+rcx*2]
0x14000fc29  lea     rcx, [rbp+210h+var_258]
0x14000fc2d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000fc32  lea     rdx, [rbp+210h+var_258]
0x14000fc36  lea     rcx, [rsp+310h+var_298]
0x14000fc3b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14000fc40  lea     rcx, [rbp+210h+var_258]; void *
0x14000fc44  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000fc49  lea     r8, [rsp+310h+dwHandle]; lpdwHandle
0x14000fc4e  mov     rdx, r14; lpwstrFilename
0x14000fc51  xor     ecx, ecx; dwFlags
0x14000fc53  call    cs:__imp_GetFileVersionInfoSizeExW
0x14000fc59  mov     ebx, eax
0x14000fc5b  test    eax, eax
0x14000fc5d  jnz     short loc_14000FC8D
0x14000fc5f  call    cs:__imp_GetLastError
0x14000fc65  mov     ebx, eax
0x14000fc67  test    eax, eax
0x14000fc69  jle     short loc_14000FC74
0x14000fc6b  movzx   ebx, ax
0x14000fc6e  or      ebx, 80070000h
0x14000fc74  lea     rdx, aErrorTryingToG_0; "Error trying to get the file version in"...
0x14000fc7b  mov     r8d, ebx
0x14000fc7e  mov     ecx, 2; unsigned __int8
0x14000fc83  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x14000fc88  jmp     loc_14000FDDE
0x14000fc8d  mov     rcx, rbx; this
0x14000fc90  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x14000fc95  mov     rsi, rax
0x14000fc98  test    rax, rax
0x14000fc9b  jnz     short loc_14000FCAB
0x14000fc9d  mov     ebx, 8007000Eh
0x14000fca2  lea     rdx, aFailedToAlloca; "Failed to allocate memory for file vers"...
0x14000fca9  jmp     short loc_14000FC7B
0x14000fcab  mov     [rsp+310h+lpData], rsi; lpData
0x14000fcb0  mov     r9d, ebx; dwLen
0x14000fcb3  mov     r8d, [rsp+310h+dwHandle]; dwHandle
0x14000fcb8  mov     rdx, r14; lpwstrFilename
0x14000fcbb  xor     ecx, ecx; dwFlags
0x14000fcbd  call    cs:__imp_GetFileVersionInfoExW
0x14000fcc3  test    eax, eax
0x14000fcc5  jnz     short loc_14000FCF5
0x14000fcc7  call    cs:__imp_GetLastError
0x14000fccd  mov     ebx, eax
0x14000fccf  test    eax, eax
0x14000fcd1  jle     short loc_14000FCDC
0x14000fcd3  movzx   ebx, ax
0x14000fcd6  or      ebx, 80070000h
0x14000fcdc  mov     r8d, ebx
0x14000fcdf  lea     rdx, aErrorTryingToG; "Error trying to get the file version in"...
0x14000fce6  mov     ecx, 2; unsigned __int8
0x14000fceb  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x14000fcf0  jmp     loc_14000FDD5
0x14000fcf5  mov     ebx, r13d
0x14000fcf8  lea     r9, [rsp+310h+puLen]; puLen
0x14000fcfd  lea     r8, [rsp+310h+lpBuffer]; lplpBuffer
0x14000fd02  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x14000fd09  mov     rcx, rsi; pBlock
0x14000fd0c  call    cs:__imp_VerQueryValueW
0x14000fd12  test    eax, eax
0x14000fd14  jnz     short loc_14000FD22
0x14000fd16  lea     rcx, [rsp+310h+var_2D8]
0x14000fd1b  mov     [rsp+310h+lpBuffer], rcx
0x14000fd20  jmp     short loc_14000FD27
0x14000fd22  mov     rcx, [rsp+310h+lpBuffer]
0x14000fd27  test    rcx, rcx
0x14000fd2a  jz      loc_14000FDD5
0x14000fd30  movzx   eax, word ptr [rcx+2]
0x14000fd34  movzx   r9d, word ptr [rcx]
0x14000fd38  mov     dword ptr [rsp+310h+lpData], eax
0x14000fd3c  lea     r8, aStringfileinfo; "\\StringFileInfo\\%04x%04x\\OriginalFil"...
0x14000fd43  mov     edx, 0FEh; BufferCount
0x14000fd48  lea     rcx, [rbp+210h+Buffer]; Buffer
0x14000fd4c  call    swprintf_s
0x14000fd51  lea     r9, [rsp+310h+puLen]; puLen
0x14000fd56  lea     r8, [rsp+310h+var_2C8]; lplpBuffer
0x14000fd5b  lea     rdx, [rbp+210h+Buffer]; lpSubBlock
0x14000fd5f  mov     rcx, rsi; pBlock
0x14000fd62  call    cs:__imp_VerQueryValueW
0x14000fd68  test    eax, eax
0x14000fd6a  jnz     short loc_14000FD82
0x14000fd6c  lea     rdx, aTheOriginalFil; "The original file name could not be ret"...
0x14000fd73  lea     ecx, [rax+2]; unsigned __int8
0x14000fd76  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x14000fd7b  mov     ebx, 80004005h
0x14000fd80  jmp     short loc_14000FDD5
0x14000fd82  mov     rdx, [rsp+310h+var_2C8]
0x14000fd87  test    rdx, rdx
0x14000fd8a  jz      short loc_14000FDD5
0x14000fd8c  lea     rcx, [rsp+310h+var_298]
0x14000fd91  cmp     [rbp+210h+var_280], 7
0x14000fd96  cmova   rcx, [rsp+310h+var_298]
0x14000fd9c  call    cs:__imp__o__wcsicmp
0x14000fda2  test    eax, eax
0x14000fda4  setz    cl
0x14000fda7  mov     [r12], cl
0x14000fdab  test    eax, eax
0x14000fdad  jz      short loc_14000FDD5
0x14000fdaf  lea     r8, [rsp+310h+var_298]
0x14000fdb4  cmp     [rbp+210h+var_280], 7
0x14000fdb9  cmova   r8, [rsp+310h+var_298]
0x14000fdbf  mov     r9, [rsp+310h+var_2C8]
0x14000fdc4  lea     rdx, aExpectedWsFoun; "Expected: %ws Found: %ws"
0x14000fdcb  mov     ecx, 2; unsigned __int8
0x14000fdd0  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x14000fdd5  mov     rcx, rsi; this
0x14000fdd8  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x14000fddd  nop
0x14000fdde  lea     rcx, [rbp+210h+S2]; void *
0x14000fde2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000fde7  nop
0x14000fde8  lea     rcx, [rsp+310h+var_298]; void *
0x14000fded  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000fdf2  nop
0x14000fdf3  lea     rcx, [rsp+310h+var_2C0+8]; void *
0x14000fdf8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000fdfd  mov     eax, ebx
0x14000fdff  jmp     short loc_14000FE37
0x14000fe01  lea     rdx, aCallerPassedLi; "Caller passed library name that did not"...
0x14000fe08  mov     ecx, 2; unsigned __int8
0x14000fe0d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x14000fe12  nop
0x14000fe13  lea     rcx, [rbp+210h+S2]; void *
0x14000fe17  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000fe1c  nop
0x14000fe1d  lea     rcx, [rsp+310h+var_298]; void *
0x14000fe22  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000fe27  nop
0x14000fe28  lea     rcx, [rsp+310h+var_2C0+8]; void *
0x14000fe2d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000fe32  mov     eax, 80070057h
0x14000fe37  mov     rcx, [rbp+210h+var_30]
0x14000fe3e  xor     rcx, rsp; StackCookie
0x14000fe41  call    __security_check_cookie
0x14000fe46  lea     r11, [rsp+310h+var_20]
0x14000fe4e  mov     rbx, [r11+40h]
0x14000fe52  mov     rsi, [r11+48h]
0x14000fe56  mov     rsp, r11
0x14000fe59  pop     r15
0x14000fe5b  pop     r14
0x14000fe5d  pop     r13
0x14000fe5f  pop     r12
0x14000fe61  pop     rbp
0x14000fe62  retn
0x14000fe63  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```
