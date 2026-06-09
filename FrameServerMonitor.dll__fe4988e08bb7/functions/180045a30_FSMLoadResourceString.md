# FSMLoadResourceString

- ea: `0x180045a30`
- end: `0x180045dae`
- name: `FSMLoadResourceString`
- size: `894`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x180007a80`

## callees

- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x18000723c`
- `0x18000d060`
- `0x18000d1e0`
- `0x18000d3d8`
- `0x18000e25c`
- `0x18003222c`
- `0x18003224c`
- `0x180045a30`
- `0x180046028`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180045b9c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180045b9c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180045c74`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180045ce3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180045c74`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180045ce3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045ac0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045b66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045bb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045cf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045ac0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045b66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045bb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045cf1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180045aae`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180045b5c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180045aae`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180045b5c`

## string_xrefs

- `0x180045a7c`: `%SystemRoot%\System32\FrameServerMonitor.dll`
- `0x180045aa7`: `%SystemRoot%\System32\FrameServerMonitor.dll`
- `0x180045b52`: `%SystemRoot%\System32\FrameServerMonitor.dll`

## pseudocode

```c
__int64 __fastcall FSMLoadResourceString(__int64 a1, UINT a2, __int64 a3)
{
  int v5; // edx
  int v6; // r8d
  _WORD *v7; // rcx
  signed int v8; // esi
  DWORD v9; // eax
  unsigned __int64 v10; // rdi
  signed int LastError; // eax
  __int64 v12; // rdx
  unsigned __int8 Level; // al
  const struct std::nothrow_t *unique; // rax
  const WCHAR *v15; // rbx
  int v16; // ecx
  __int64 v17; // rdx
  signed int v18; // eax
  HMODULE Library; // rax
  HINSTANCE v20; // rdi
  signed int v21; // eax
  __int64 v22; // rdx
  const struct std::nothrow_t *v23; // rax
  LPWSTR v24; // rbx
  WCHAR *v25; // r8
  int StringW; // eax
  __int64 v27; // r15
  const struct std::nothrow_t *v28; // rax
  WCHAR *v29; // r8
  signed int v30; // eax
  HINSTANCE hInstance; // [rsp+30h] [rbp-10h] BYREF
  __int64 v33; // [rsp+38h] [rbp-8h] BYREF
  LPWSTR lpBuffer; // [rsp+70h] [rbp+30h] BYREF
  LPWSTR lpDst; // [rsp+88h] [rbp+48h] BYREF

  hInstance = 0;
  lpBuffer = 0;
  lpDst = 0;
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v5,
      v6,
      (unsigned int)L"%SystemRoot%\\System32\\FrameServerMonitor.dll",
      v5);
  v7 = *(_WORD **)a3;
  *(_QWORD *)(a3 + 8) = *(_QWORD *)a3;
  v8 = 0;
  *v7 = 0;
  v9 = ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\FrameServerMonitor.dll", 0, 0);
  v10 = v9;
  if ( !v9 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
LABEL_10:
        Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
        goto LABEL_27;
      }
      v12 = 52;
LABEL_9:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_6e0451f6c0fa38a47088d18d54723fd1_Traceguids, 0, v8);
      goto LABEL_10;
    }
  }
  unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned short [0]>(&v33, v10);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)&lpDst, unique);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v33);
  v15 = lpDst;
  if ( !lpDst )
  {
    v8 = -2147024882;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_10;
    v17 = 53;
LABEL_14:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_6e0451f6c0fa38a47088d18d54723fd1_Traceguids, 0, v16);
    goto LABEL_10;
  }
  if ( !ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\FrameServerMonitor.dll", lpDst, v10) )
  {
    v18 = GetLastError();
    v8 = v18;
    if ( v18 > 0 )
      v8 = (unsigned __int16)v18 | 0x80070000;
    if ( v8 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_10;
      v12 = 54;
      goto LABEL_9;
    }
  }
  Library = LoadLibraryExW(v15, 0, 0x60u);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
    &hInstance,
    Library);
  v20 = hInstance;
  if ( hInstance )
  {
    v23 = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned short [0]>(&v33, 0x104u);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)&lpBuffer, v23);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v33);
    v24 = lpBuffer;
    if ( !lpBuffer )
    {
      v8 = -2147024882;
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_10;
      v17 = 56;
      goto LABEL_14;
    }
    v25 = lpBuffer;
    lpBuffer[259] = 0;
    StringW = LoadStringW(v20, a2, v25, 259);
    v27 = StringW;
    if ( StringW > 259 )
    {
      v28 = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned short [0]>(&v33, StringW + 1);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(
        (void **)&lpBuffer,
        v28);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v33);
      v24 = lpBuffer;
      if ( !lpBuffer )
      {
        v8 = -2147024882;
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_10;
        v17 = 57;
        goto LABEL_14;
      }
      v29 = lpBuffer;
      lpBuffer[v27] = 0;
      LODWORD(v27) = LoadStringW(v20, a2, v29, v27);
    }
    if ( !(_DWORD)v27 )
    {
      v30 = GetLastError();
      v8 = v30;
      if ( v30 > 0 )
        v8 = (unsigned __int16)v30 | 0x80070000;
      if ( v8 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_10;
        v12 = 58;
        goto LABEL_9;
      }
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             a3,
                             v24) )
    {
      v8 = -2147024882;
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v17 = 59;
        goto LABEL_14;
      }
    }
  }
  else
  {
    v21 = GetLastError();
    v8 = v21;
    if ( v21 > 0 )
      v8 = (unsigned __int16)v21 | 0x80070000;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_6e0451f6c0fa38a47088d18d54723fd1_Traceguids, 0, v8);
  }
  Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
  if ( v8 < 0 )
  {
LABEL_27:
    if ( Level )
    {
      v22 = 60;
LABEL_48:
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        v22,
        &WPP_6e0451f6c0fa38a47088d18d54723fd1_Traceguids,
        (unsigned int)v8);
      goto LABEL_49;
    }
    goto LABEL_49;
  }
  if ( Level >= 8u )
  {
    v22 = 61;
    goto LABEL_48;
  }
LABEL_49:
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&lpDst);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&lpBuffer);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&hInstance);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180045a30  mov     [rsp-28h+arg_8], rbx
0x180045a35  mov     [rsp-28h+arg_10], rsi
0x180045a3a  mov     [rsp-28h+lpBuffer], rcx
0x180045a3f  push    rbp
0x180045a40  push    rdi
0x180045a41  push    r12
0x180045a43  push    r13
0x180045a45  push    r15
0x180045a47  mov     rbp, rsp
0x180045a4a  sub     rsp, 40h
0x180045a4e  mov     r13, r8
0x180045a51  mov     [rbp+hInstance], 0
0x180045a59  mov     r12d, edx
0x180045a5c  mov     [rbp+lpBuffer], 0
0x180045a64  mov     [rbp+lpDst], 0
0x180045a6c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180045a71  cmp     al, 8
0x180045a73  jb      short loc_180045A93
0x180045a75  mov     rcx, cs:WPP_GLOBAL_Control
0x180045a7c  lea     r9, Src; "%SystemRoot%\\System32\\FrameServerMoni"...
0x180045a83  mov     [rsp+40h+var_20], edx
0x180045a87  mov     rcx, [rcx+0D8h]
0x180045a8e  call    WPP_SF_SD
0x180045a93  mov     rcx, [r13+0]
0x180045a97  xor     eax, eax
0x180045a99  mov     [r13+8], rcx
0x180045a9d  xor     r8d, r8d; nSize
0x180045aa0  xor     edx, edx; lpDst
0x180045aa2  xor     esi, esi
0x180045aa4  mov     [rcx], ax
0x180045aa7  lea     rcx, Src; "%SystemRoot%\\System32\\FrameServerMoni"...
0x180045aae  call    cs:__imp_ExpandEnvironmentStringsW
0x180045ab4  mov     edi, eax
0x180045ab6  mov     r15d, 80070000h
0x180045abc  test    eax, eax
0x180045abe  jnz     short loc_180045B0C
0x180045ac0  call    cs:__imp_GetLastError
0x180045ac6  mov     esi, eax
0x180045ac8  test    eax, eax
0x180045aca  jle     short loc_180045AD2
0x180045acc  movzx   esi, ax
0x180045acf  or      esi, r15d
0x180045ad2  test    esi, esi
0x180045ad4  jns     short loc_180045B0C
0x180045ad6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180045adb  cmp     al, 1
0x180045add  jb      short loc_180045B02
0x180045adf  mov     edx, 34h ; '4'
0x180045ae4  mov     [rsp+40h+var_20], esi
0x180045ae8  mov     rcx, cs:WPP_GLOBAL_Control
0x180045aef  lea     r8, WPP_6e0451f6c0fa38a47088d18d54723fd1_Traceguids
0x180045af6  xor     r9d, r9d
0x180045af9  mov     rcx, [rcx+10h]
0x180045afd  call    WPP_SF_qD
0x180045b02  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180045b07  jmp     loc_180045C02
0x180045b0c  mov     rdx, rdi
0x180045b0f  lea     rcx, [rbp+var_8]
0x180045b13  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180045b18  mov     rdx, rax
0x180045b1b  lea     rcx, [rbp+lpDst]
0x180045b1f  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180045b24  lea     rcx, [rbp+var_8]
0x180045b28  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180045b2d  mov     rbx, [rbp+lpDst]
0x180045b31  test    rbx, rbx
0x180045b34  jnz     short loc_180045B4F
0x180045b36  mov     ecx, 8007000Eh
0x180045b3b  mov     esi, ecx
0x180045b3d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180045b42  cmp     al, 1
0x180045b44  jb      short loc_180045B02
0x180045b46  lea     edx, [rbx+35h]
0x180045b49  mov     [rsp+40h+var_20], ecx
0x180045b4d  jmp     short loc_180045AE8
0x180045b4f  mov     r8d, edi; nSize
0x180045b52  lea     rcx, Src; "%SystemRoot%\\System32\\FrameServerMoni"...
0x180045b59  mov     rdx, rbx; lpDst
0x180045b5c  call    cs:__imp_ExpandEnvironmentStringsW
0x180045b62  test    eax, eax
0x180045b64  jnz     short loc_180045B93
0x180045b66  call    cs:__imp_GetLastError
0x180045b6c  mov     esi, eax
0x180045b6e  test    eax, eax
0x180045b70  jle     short loc_180045B78
0x180045b72  movzx   esi, ax
0x180045b75  or      esi, r15d
0x180045b78  test    esi, esi
0x180045b7a  jns     short loc_180045B93
0x180045b7c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180045b81  cmp     al, 1
0x180045b83  jb      loc_180045B02
0x180045b89  mov     edx, 36h ; '6'
0x180045b8e  jmp     loc_180045AE4
0x180045b93  xor     edx, edx; hFile
0x180045b95  mov     rcx, rbx; lpLibFileName
0x180045b98  lea     r8d, [rdx+60h]; dwFlags
0x180045b9c  call    cs:__imp_LoadLibraryExW
0x180045ba2  mov     rdx, rax
0x180045ba5  lea     rcx, [rbp+hInstance]
0x180045ba9  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x180045bae  mov     rdi, [rbp+hInstance]
0x180045bb2  test    rdi, rdi
0x180045bb5  jnz     short loc_180045C14
0x180045bb7  call    cs:__imp_GetLastError
0x180045bbd  mov     esi, eax
0x180045bbf  test    eax, eax
0x180045bc1  jle     short loc_180045BC9
0x180045bc3  movzx   esi, ax
0x180045bc6  or      esi, r15d
0x180045bc9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180045bce  cmp     al, 1
0x180045bd0  jb      short loc_180045BF5
0x180045bd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180045bd9  lea     r8, WPP_6e0451f6c0fa38a47088d18d54723fd1_Traceguids
0x180045be0  mov     edx, 37h ; '7'
0x180045be5  mov     [rsp+40h+var_20], esi
0x180045be9  xor     r9d, r9d
0x180045bec  mov     rcx, [rcx+10h]
0x180045bf0  call    WPP_SF_qD
0x180045bf5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180045bfa  test    esi, esi
0x180045bfc  jns     loc_180045D52
0x180045c02  cmp     al, 1
0x180045c04  jb      loc_180045D78
0x180045c0a  mov     edx, 3Ch ; '<'
0x180045c0f  jmp     loc_180045D5B
0x180045c14  mov     edx, 104h
0x180045c19  lea     rcx, [rbp+var_8]
0x180045c1d  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180045c22  mov     rdx, rax
0x180045c25  lea     rcx, [rbp+lpBuffer]
0x180045c29  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180045c2e  lea     rcx, [rbp+var_8]
0x180045c32  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180045c37  mov     rbx, [rbp+lpBuffer]
0x180045c3b  test    rbx, rbx
0x180045c3e  jnz     short loc_180045C5C
0x180045c40  mov     ecx, 8007000Eh
0x180045c45  mov     esi, ecx
0x180045c47  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180045c4c  cmp     al, 1
0x180045c4e  jb      loc_180045B02
0x180045c54  lea     edx, [rbx+38h]
0x180045c57  jmp     loc_180045B49
0x180045c5c  xor     eax, eax
0x180045c5e  mov     r9d, 103h; cchBufferMax
0x180045c64  mov     r8, rbx; lpBuffer
0x180045c67  mov     [rbx+206h], ax
0x180045c6e  mov     edx, r12d; uID
0x180045c71  mov     rcx, rdi; hInstance
0x180045c74  call    cs:__imp_LoadStringW
0x180045c7a  movsxd  r15, eax
0x180045c7d  cmp     r15d, 103h
0x180045c84  jle     short loc_180045CEC
0x180045c86  lea     ecx, [r15+1]
0x180045c8a  movsxd  rdx, ecx
0x180045c8d  lea     rcx, [rbp+var_8]
0x180045c91  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180045c96  mov     rdx, rax
0x180045c99  lea     rcx, [rbp+lpBuffer]
0x180045c9d  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180045ca2  lea     rcx, [rbp+var_8]
0x180045ca6  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180045cab  mov     rbx, [rbp+lpBuffer]
0x180045caf  test    rbx, rbx
0x180045cb2  jnz     short loc_180045CD0
0x180045cb4  mov     ecx, 8007000Eh
0x180045cb9  mov     esi, ecx
0x180045cbb  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180045cc0  cmp     al, 1
0x180045cc2  jb      loc_180045B02
0x180045cc8  lea     edx, [rbx+39h]
0x180045ccb  jmp     loc_180045B49
0x180045cd0  xor     eax, eax
0x180045cd2  mov     r9d, r15d; cchBufferMax
0x180045cd5  mov     r8, rbx; lpBuffer
0x180045cd8  mov     [rbx+r15*2], ax
0x180045cdd  mov     edx, r12d; uID
0x180045ce0  mov     rcx, rdi; hInstance
0x180045ce3  call    cs:__imp_LoadStringW
0x180045ce9  mov     r15d, eax
0x180045cec  test    r15d, r15d
0x180045cef  jnz     short loc_180045D21
0x180045cf1  call    cs:__imp_GetLastError
0x180045cf7  mov     esi, eax
0x180045cf9  test    eax, eax
0x180045cfb  jle     short loc_180045D06
0x180045cfd  movzx   esi, ax
0x180045d00  or      esi, 80070000h
0x180045d06  test    esi, esi
0x180045d08  jns     short loc_180045D21
0x180045d0a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180045d0f  cmp     al, 1
0x180045d11  jb      loc_180045B02
0x180045d17  mov     edx, 3Ah ; ':'
0x180045d1c  jmp     loc_180045AE4
0x180045d21  mov     rdx, rbx
0x180045d24  mov     rcx, r13
0x180045d27  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180045d2c  test    al, al
0x180045d2e  jnz     loc_180045BF5
0x180045d34  mov     ecx, 8007000Eh
0x180045d39  mov     esi, ecx
0x180045d3b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180045d40  cmp     al, 1
0x180045d42  jb      loc_180045BF5
0x180045d48  mov     edx, 3Bh ; ';'
0x180045d4d  jmp     loc_180045B49
0x180045d52  cmp     al, 8
0x180045d54  jb      short loc_180045D78
0x180045d56  mov     edx, 3Dh ; '='
0x180045d5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180045d62  lea     r8, WPP_6e0451f6c0fa38a47088d18d54723fd1_Traceguids
0x180045d69  mov     r9d, esi
0x180045d6c  mov     rcx, [rcx+0D8h]
0x180045d73  call    WPP_SF_d
0x180045d78  lea     rcx, [rbp+lpDst]
0x180045d7c  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180045d81  lea     rcx, [rbp+lpBuffer]
0x180045d85  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180045d8a  lea     rcx, [rbp+hInstance]
0x180045d8e  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180045d93  lea     r11, [rsp+40h+var_s0]
0x180045d98  mov     eax, esi
0x180045d9a  mov     rbx, [r11+38h]
0x180045d9e  mov     rsi, [r11+40h]
0x180045da2  mov     rsp, r11
0x180045da5  pop     r15
0x180045da7  pop     r13
0x180045da9  pop     r12
0x180045dab  pop     rdi
0x180045dac  pop     rbp
0x180045dad  retn
```
