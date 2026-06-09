# FSD3DProxy::FSD3DProxy(void)

- ea: `0x1800668b8`
- end: `0x180066ce9`
- name: `??0FSD3DProxy@@IEAA@XZ`
- size: `1073`
- prototype: `FSD3DProxy *__fastcall(FSD3DProxy *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180066f68`

## callees

- `0x180003e20`
- `0x18000478c`
- `0x180007c10`
- `0x1800095c8`
- `0x180009608`
- `0x1800096f4`
- `0x1800668b8`
- `0x180067168`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180066ab4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180066b03`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180066b3b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180066ab4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180066b03`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180066b3b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180066b88`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180066bd2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180066c00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180066c3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180066b88`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180066bd2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180066c00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180066c3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800669cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066acb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066b1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066b52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066b97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066be1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066c0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066c4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800669cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066acb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066b1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066b52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066b97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066be1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066c0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066c4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800669bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800669bd`

## string_xrefs

- `0x180066a06`: `%s\d3d11.dll`
- `0x180066a7b`: `%s\dxgi.dll`
- `0x180066a44`: `%s\d3d12.dll`
- `0x180066bcb`: `D3D12CreateDevice`
- `0x180066b81`: `D3D11CreateDevice`
- `0x180066c37`: `CreateDXGIFactory2`
- `0x180066bf9`: `CreateDXGIFactory1`

## pseudocode

```c
FSD3DProxy *__fastcall FSD3DProxy::FSD3DProxy(FSD3DProxy *this)
{
  HMODULE *v1; // rsi
  HMODULE *v2; // r15
  HMODULE *v3; // r14
  signed int LastError; // eax
  signed int v6; // ebx
  __int64 v7; // rdx
  int v8; // eax
  __int64 v9; // rdx
  HMODULE Library; // rax
  signed int v11; // eax
  HMODULE v12; // rax
  signed int v13; // eax
  HMODULE v14; // rax
  signed int v15; // eax
  FARPROC ProcAddress; // rax
  signed int v17; // eax
  FARPROC v18; // rax
  signed int v19; // eax
  FARPROC v20; // rax
  signed int v21; // eax
  FARPROC v22; // rax
  signed int v23; // eax
  __int64 v25; // [rsp+20h] [rbp-E0h]
  WCHAR Buffer[264]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR LibFileName[264]; // [rsp+240h] [rbp+140h] BYREF
  WCHAR v28[264]; // [rsp+450h] [rbp+350h] BYREF
  WCHAR v29[264]; // [rsp+660h] [rbp+560h] BYREF

  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &FSD3DProxy::`vftable';
  v1 = (HMODULE *)((char *)this + 24);
  v2 = (HMODULE *)((char *)this + 32);
  *((_DWORD *)this + 3) = -2147418113;
  v3 = (HMODULE *)((char *)this + 40);
  *((_DWORD *)this + 4) = -2147418113;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 10, WPP_730173a282b93357ac7e2da417db9a6b_Traceguids, this);
  memset_0(Buffer, 0, 0x208u);
  memset_0(LibFileName, 0, 0x208u);
  memset_0(v29, 0, 0x208u);
  memset_0(v28, 0, 0x208u);
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x103 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_54;
      v7 = 11;
      goto LABEL_53;
    }
  }
  v8 = StringCchPrintfW(LibFileName, 0x104u, L"%s\\d3d11.dll", Buffer);
  v6 = v8;
  if ( v8 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_54;
    v9 = 12;
    goto LABEL_12;
  }
  v8 = StringCchPrintfW(v28, 0x104u, L"%s\\d3d12.dll", Buffer);
  v6 = v8;
  if ( v8 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_54;
    v9 = 13;
    goto LABEL_12;
  }
  v8 = StringCchPrintfW(v29, 0x104u, L"%s\\dxgi.dll", Buffer);
  v6 = v8;
  if ( v8 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_54;
    v9 = 14;
LABEL_12:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_730173a282b93357ac7e2da417db9a6b_Traceguids, this, v8);
    goto LABEL_54;
  }
  Library = LoadLibraryExW(LibFileName, 0, 0);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
    v2,
    Library);
  if ( *v2 )
  {
    v12 = LoadLibraryExW(v28, 0, 0);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      v3,
      v12);
    if ( !*v3 )
    {
      v13 = GetLastError();
      if ( v13 > 0 )
        v13 = (unsigned __int16)v13 | 0x80070000;
      *((_DWORD *)this + 4) = v13;
    }
    v14 = LoadLibraryExW(v29, 0, 0);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      v1,
      v14);
    if ( *v1 )
    {
      ProcAddress = GetProcAddress(*v2, "D3D11CreateDevice");
      *((_QWORD *)this + 8) = ProcAddress;
      if ( ProcAddress )
      {
        if ( *v3 )
        {
          v18 = GetProcAddress(*v3, "D3D12CreateDevice");
          *((_QWORD *)this + 9) = v18;
          if ( !v18 )
          {
            v19 = GetLastError();
            if ( v19 > 0 )
              v19 = (unsigned __int16)v19 | 0x80070000;
            *((_DWORD *)this + 4) = v19;
          }
        }
        v20 = GetProcAddress(*v1, "CreateDXGIFactory1");
        *((_QWORD *)this + 6) = v20;
        if ( v20 )
        {
          v22 = GetProcAddress(*v1, "CreateDXGIFactory2");
          *((_QWORD *)this + 7) = v22;
          if ( !v22 )
          {
            v23 = GetLastError();
            v6 = v23;
            if ( v23 > 0 )
              v6 = (unsigned __int16)v23 | 0x80070000;
            if ( g_wppLevels )
            {
              v7 = 19;
              goto LABEL_53;
            }
          }
        }
        else
        {
          v21 = GetLastError();
          v6 = v21;
          if ( v21 > 0 )
            v6 = (unsigned __int16)v21 | 0x80070000;
          if ( g_wppLevels )
          {
            v7 = 18;
            goto LABEL_53;
          }
        }
      }
      else
      {
        v17 = GetLastError();
        v6 = v17;
        if ( v17 > 0 )
          v6 = (unsigned __int16)v17 | 0x80070000;
        if ( g_wppLevels )
        {
          v7 = 17;
          goto LABEL_53;
        }
      }
    }
    else
    {
      v15 = GetLastError();
      v6 = v15;
      if ( v15 > 0 )
        v6 = (unsigned __int16)v15 | 0x80070000;
      if ( g_wppLevels )
      {
        v7 = 16;
        goto LABEL_53;
      }
    }
  }
  else
  {
    v11 = GetLastError();
    v6 = v11;
    if ( v11 > 0 )
      v6 = (unsigned __int16)v11 | 0x80070000;
    if ( g_wppLevels )
    {
      v7 = 15;
LABEL_53:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_730173a282b93357ac7e2da417db9a6b_Traceguids, this, v6);
    }
  }
LABEL_54:
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    LODWORD(v25) = v6;
    WPP_SF_qDD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      20,
      WPP_730173a282b93357ac7e2da417db9a6b_Traceguids,
      this,
      v25,
      *((_DWORD *)this + 4));
  }
  *((_DWORD *)this + 3) = v6;
  return this;
}

```

## disassembly

```asm
0x1800668b8  push    rbp
0x1800668ba  push    rbx
0x1800668bb  push    rsi
0x1800668bc  push    rdi
0x1800668bd  push    r14
0x1800668bf  push    r15
0x1800668c1  lea     rbp, [rsp-788h]
0x1800668c9  sub     rsp, 888h
0x1800668d0  mov     rax, cs:__security_cookie
0x1800668d7  xor     rax, rsp
0x1800668da  mov     [rbp+7B0h+var_40], rax
0x1800668e1  lea     rax, ??_7FSD3DProxy@@6B@; const FSD3DProxy::`vftable'
0x1800668e8  mov     dword ptr [rcx+8], 1
0x1800668ef  mov     [rcx], rax
0x1800668f2  lea     rsi, [rcx+18h]
0x1800668f6  mov     eax, 8000FFFFh
0x1800668fb  lea     r15, [rcx+20h]
0x1800668ff  mov     [rcx+0Ch], eax
0x180066902  lea     r14, [rcx+28h]
0x180066906  mov     [rcx+10h], eax
0x180066909  mov     rdi, rcx
0x18006690c  mov     qword ptr [rsi], 0
0x180066913  mov     qword ptr [r15], 0
0x18006691a  mov     qword ptr [r14], 0
0x180066921  mov     qword ptr [rcx+30h], 0
0x180066929  mov     qword ptr [rcx+38h], 0
0x180066931  mov     qword ptr [rcx+40h], 0
0x180066939  mov     qword ptr [rcx+48h], 0
0x180066941  cmp     cs:byte_18010EC4D, 10h
0x180066948  jb      short loc_18006696C
0x18006694a  mov     r9, rcx
0x18006694d  lea     r8, WPP_730173a282b93357ac7e2da417db9a6b_Traceguids
0x180066954  mov     rcx, cs:WPP_GLOBAL_Control
0x18006695b  mov     edx, 0Ah
0x180066960  mov     rcx, [rcx+0D8h]
0x180066967  call    WPP_SF_q
0x18006696c  mov     ebx, 208h
0x180066971  lea     rcx, [rsp+8B0h+Buffer]; void *
0x180066976  mov     r8d, ebx; Size
0x180066979  xor     edx, edx; Val
0x18006697b  call    memset_0
0x180066980  mov     r8d, ebx; Size
0x180066983  lea     rcx, [rbp+7B0h+LibFileName]; void *
0x18006698a  xor     edx, edx; Val
0x18006698c  call    memset_0
0x180066991  mov     r8d, ebx; Size
0x180066994  lea     rcx, [rbp+7B0h+var_250]; void *
0x18006699b  xor     edx, edx; Val
0x18006699d  call    memset_0
0x1800669a2  mov     r8d, ebx; Size
0x1800669a5  lea     rcx, [rbp+7B0h+var_460]; void *
0x1800669ac  xor     edx, edx; Val
0x1800669ae  call    memset_0
0x1800669b3  mov     edx, 104h; uSize
0x1800669b8  lea     rcx, [rsp+8B0h+Buffer]; lpBuffer
0x1800669bd  call    cs:__imp_GetSystemDirectoryW
0x1800669c3  dec     eax
0x1800669c5  cmp     eax, 103h
0x1800669ca  jbe     short loc_1800669FC
0x1800669cc  call    cs:__imp_GetLastError
0x1800669d2  mov     ebx, eax
0x1800669d4  test    eax, eax
0x1800669d6  jle     short loc_1800669E1
0x1800669d8  movzx   ebx, ax
0x1800669db  or      ebx, 80070000h
0x1800669e1  test    ebx, ebx
0x1800669e3  jns     short loc_1800669FC
0x1800669e5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800669ec  jb      loc_180066C8E
0x1800669f2  mov     edx, 0Bh
0x1800669f7  jmp     loc_180066C70
0x1800669fc  lea     r9, [rsp+8B0h+Buffer]
0x180066a01  mov     edx, 104h; unsigned __int64
0x180066a06  lea     r8, aSD3d11Dll; "%s\\d3d11.dll"
0x180066a0d  lea     rcx, [rbp+7B0h+LibFileName]; unsigned __int16 *
0x180066a14  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180066a19  mov     ebx, eax
0x180066a1b  test    eax, eax
0x180066a1d  jns     short loc_180066A3A
0x180066a1f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066a26  jb      loc_180066C8E
0x180066a2c  mov     edx, 0Ch
0x180066a31  mov     dword ptr [rsp+8B0h+var_890], eax
0x180066a35  jmp     loc_180066C74
0x180066a3a  lea     r9, [rsp+8B0h+Buffer]
0x180066a3f  mov     edx, 104h; unsigned __int64
0x180066a44  lea     r8, aSD3d12Dll; "%s\\d3d12.dll"
0x180066a4b  lea     rcx, [rbp+7B0h+var_460]; unsigned __int16 *
0x180066a52  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180066a57  mov     ebx, eax
0x180066a59  test    eax, eax
0x180066a5b  jns     short loc_180066A71
0x180066a5d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066a64  jb      loc_180066C8E
0x180066a6a  mov     edx, 0Dh
0x180066a6f  jmp     short loc_180066A31
0x180066a71  lea     r9, [rsp+8B0h+Buffer]
0x180066a76  mov     edx, 104h; unsigned __int64
0x180066a7b  lea     r8, aSDxgiDll; "%s\\dxgi.dll"
0x180066a82  lea     rcx, [rbp+7B0h+var_250]; unsigned __int16 *
0x180066a89  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180066a8e  mov     ebx, eax
0x180066a90  test    eax, eax
0x180066a92  jns     short loc_180066AA8
0x180066a94  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066a9b  jb      loc_180066C8E
0x180066aa1  mov     edx, 0Eh
0x180066aa6  jmp     short loc_180066A31
0x180066aa8  xor     r8d, r8d; dwFlags
0x180066aab  lea     rcx, [rbp+7B0h+LibFileName]; lpLibFileName
0x180066ab2  xor     edx, edx; hFile
0x180066ab4  call    cs:__imp_LoadLibraryExW
0x180066aba  mov     rdx, rax
0x180066abd  mov     rcx, r15
0x180066ac0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x180066ac5  cmp     qword ptr [r15], 0
0x180066ac9  jnz     short loc_180066AF7
0x180066acb  call    cs:__imp_GetLastError
0x180066ad1  mov     ebx, eax
0x180066ad3  test    eax, eax
0x180066ad5  jle     short loc_180066AE0
0x180066ad7  movzx   ebx, ax
0x180066ada  or      ebx, 80070000h
0x180066ae0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066ae7  jb      loc_180066C8E
0x180066aed  mov     edx, 0Fh
0x180066af2  jmp     loc_180066C70
0x180066af7  xor     r8d, r8d; dwFlags
0x180066afa  lea     rcx, [rbp+7B0h+var_460]; lpLibFileName
0x180066b01  xor     edx, edx; hFile
0x180066b03  call    cs:__imp_LoadLibraryExW
0x180066b09  mov     rdx, rax
0x180066b0c  mov     rcx, r14
0x180066b0f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x180066b14  cmp     qword ptr [r14], 0
0x180066b18  jnz     short loc_180066B2F
0x180066b1a  call    cs:__imp_GetLastError
0x180066b20  test    eax, eax
0x180066b22  jle     short loc_180066B2C
0x180066b24  movzx   eax, ax
0x180066b27  or      eax, 80070000h
0x180066b2c  mov     [rdi+10h], eax
0x180066b2f  xor     r8d, r8d; dwFlags
0x180066b32  lea     rcx, [rbp+7B0h+var_250]; lpLibFileName
0x180066b39  xor     edx, edx; hFile
0x180066b3b  call    cs:__imp_LoadLibraryExW
0x180066b41  mov     rdx, rax
0x180066b44  mov     rcx, rsi
0x180066b47  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x180066b4c  cmp     qword ptr [rsi], 0
0x180066b50  jnz     short loc_180066B7E
0x180066b52  call    cs:__imp_GetLastError
0x180066b58  mov     ebx, eax
0x180066b5a  test    eax, eax
0x180066b5c  jle     short loc_180066B67
0x180066b5e  movzx   ebx, ax
0x180066b61  or      ebx, 80070000h
0x180066b67  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066b6e  jb      loc_180066C8E
0x180066b74  mov     edx, 10h
0x180066b79  jmp     loc_180066C70
0x180066b7e  mov     rcx, [r15]; hModule
0x180066b81  lea     rdx, aD3d11createdev; "D3D11CreateDevice"
0x180066b88  call    cs:__imp_GetProcAddress
0x180066b8e  mov     [rdi+40h], rax
0x180066b92  test    rax, rax
0x180066b95  jnz     short loc_180066BC3
0x180066b97  call    cs:__imp_GetLastError
0x180066b9d  mov     ebx, eax
0x180066b9f  test    eax, eax
0x180066ba1  jle     short loc_180066BAC
0x180066ba3  movzx   ebx, ax
0x180066ba6  or      ebx, 80070000h
0x180066bac  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066bb3  jb      loc_180066C8E
0x180066bb9  mov     edx, 11h
0x180066bbe  jmp     loc_180066C70
0x180066bc3  mov     rcx, [r14]; hModule
0x180066bc6  test    rcx, rcx
0x180066bc9  jz      short loc_180066BF6
0x180066bcb  lea     rdx, aD3d12createdev; "D3D12CreateDevice"
0x180066bd2  call    cs:__imp_GetProcAddress
0x180066bd8  mov     [rdi+48h], rax
0x180066bdc  test    rax, rax
0x180066bdf  jnz     short loc_180066BF6
0x180066be1  call    cs:__imp_GetLastError
0x180066be7  test    eax, eax
0x180066be9  jle     short loc_180066BF3
0x180066beb  movzx   eax, ax
0x180066bee  or      eax, 80070000h
0x180066bf3  mov     [rdi+10h], eax
0x180066bf6  mov     rcx, [rsi]; hModule
0x180066bf9  lea     rdx, aCreatedxgifact; "CreateDXGIFactory1"
0x180066c00  call    cs:__imp_GetProcAddress
0x180066c06  mov     [rdi+30h], rax
0x180066c0a  test    rax, rax
0x180066c0d  jnz     short loc_180066C34
0x180066c0f  call    cs:__imp_GetLastError
0x180066c15  mov     ebx, eax
0x180066c17  test    eax, eax
0x180066c19  jle     short loc_180066C24
0x180066c1b  movzx   ebx, ax
0x180066c1e  or      ebx, 80070000h
0x180066c24  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066c2b  jb      short loc_180066C8E
0x180066c2d  mov     edx, 12h
0x180066c32  jmp     short loc_180066C70
0x180066c34  mov     rcx, [rsi]; hModule
0x180066c37  lea     rdx, aCreatedxgifact_0; "CreateDXGIFactory2"
0x180066c3e  call    cs:__imp_GetProcAddress
0x180066c44  mov     [rdi+38h], rax
0x180066c48  test    rax, rax
0x180066c4b  jnz     short loc_180066C8E
0x180066c4d  call    cs:__imp_GetLastError
0x180066c53  mov     ebx, eax
0x180066c55  test    eax, eax
0x180066c57  jle     short loc_180066C62
0x180066c59  movzx   ebx, ax
0x180066c5c  or      ebx, 80070000h
0x180066c62  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066c69  jb      short loc_180066C8E
0x180066c6b  mov     edx, 13h
0x180066c70  mov     dword ptr [rsp+8B0h+var_890], ebx
0x180066c74  mov     rcx, cs:WPP_GLOBAL_Control
0x180066c7b  lea     r8, WPP_730173a282b93357ac7e2da417db9a6b_Traceguids
0x180066c82  mov     r9, rdi
0x180066c85  mov     rcx, [rcx+10h]
0x180066c89  call    WPP_SF_qD
0x180066c8e  cmp     cs:byte_18010EC4D, 8
0x180066c95  jb      short loc_180066CC4
0x180066c97  mov     ecx, [rdi+10h]
0x180066c9a  lea     r8, WPP_730173a282b93357ac7e2da417db9a6b_Traceguids
0x180066ca1  mov     [rsp+8B0h+var_888], ecx
0x180066ca5  mov     edx, 14h
0x180066caa  mov     rcx, cs:WPP_GLOBAL_Control
0x180066cb1  mov     r9, rdi
0x180066cb4  mov     dword ptr [rsp+8B0h+var_890], ebx
0x180066cb8  mov     rcx, [rcx+0D8h]
0x180066cbf  call    WPP_SF_qDD
0x180066cc4  mov     [rdi+0Ch], ebx
0x180066cc7  mov     rax, rdi
0x180066cca  mov     rcx, [rbp+7B0h+var_40]
0x180066cd1  xor     rcx, rsp; StackCookie
0x180066cd4  call    __security_check_cookie
0x180066cd9  add     rsp, 888h
0x180066ce0  pop     r15
0x180066ce2  pop     r14
0x180066ce4  pop     rdi
0x180066ce5  pop     rsi
0x180066ce6  pop     rbx
0x180066ce7  pop     rbp
0x180066ce8  retn
```
