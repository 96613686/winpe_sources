# LoadDll

- ea: `0x18001df8c`
- end: `0x18001e254`
- name: `LoadDll`
- size: `712`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18001e25c`

## callees

- `0x180004170`
- `0x180005140`
- `0x18000a7f8`
- `0x18001df8c`
- `0x18001f738`
- `0x18001f7b8`
- `0x180046010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001e05f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001e073`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001e05f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001e073`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e125`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e16d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e125`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e16d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001e1f0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001e1f0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001e0cc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001e0cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e00d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e0da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e133`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e17c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e00d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e0da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e133`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e17c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001e003`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001e003`
- `WINTRUST!WTGetPluginSignatureInfo` at `0x18001e0a1`
- `WINTRUST!WTGetPluginSignatureInfo` at `0x18001e0a1`

## string_xrefs

- `0x18001e11b`: `PluginInitialize`
- `0x18001e163`: `PluginUninitialize`

## pseudocode

```c
__int64 __fastcall LoadDll(__int64 a1)
{
  DWORD LastError; // ebx
  int v3; // r8d
  HMODULE Library; // rax
  HMODULE v5; // rsi
  int v6; // r8d
  FARPROC ProcAddress; // rax
  int v8; // r8d
  _QWORD *v9; // rcx
  int v10; // edx
  FARPROC v11; // rax
  __int64 v13; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v14; // [rsp+38h] [rbp-C8h]
  __int128 v15; // [rsp+48h] [rbp-B8h]
  int v16; // [rsp+60h] [rbp-A0h] BYREF
  int v17; // [rsp+64h] [rbp-9Ch]
  WCHAR Buffer[264]; // [rsp+C0h] [rbp-40h] BYREF

  v13 = 1;
  v14 = 0;
  v15 = 0;
  memset_0(Buffer, 0, 0x208u);
  memset_0(&v16, 0, 0x58u);
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_fb4b6c20289c37c1f24720aba8866156_Traceguids, LastError);
    return LastError;
  }
  _o_wcscat_s(Buffer, 260, L"\\");
  _o_wcscat_s(Buffer, 260, a1 + 100);
  v16 = 88;
  LastError = WTGetPluginSignatureInfo(
                a1 + 100,
                -1,
                4099,
                &v16,
                0,
                0,
                v13,
                v14,
                *((_QWORD *)&v14 + 1),
                v15,
                *((_QWORD *)&v15 + 1));
  if ( (LastError & 0x80000000) == 0 && (unsigned int)(v17 - 5) <= 1 )
  {
    Library = LoadLibraryExW((LPCWSTR)(a1 + 100), 0, 0x800u);
    v5 = Library;
    if ( !Library )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sl(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v6, a1 + 100, LastError);
      return LastError;
    }
    ProcAddress = GetProcAddress(Library, "PluginInitialize");
    *(_QWORD *)a1 = ProcAddress;
    if ( ProcAddress )
    {
      v11 = GetProcAddress(v5, "PluginUninitialize");
      *(_QWORD *)(a1 + 8) = v11;
      if ( v11 )
      {
        LastError = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64))a1)(&v13, a1 + 80, a1 + 16);
        if ( !LastError )
        {
          *(_QWORD *)(a1 + 88) = v5;
          return LastError;
        }
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_24;
        v10 = 19;
      }
      else
      {
        LastError = GetLastError();
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_24;
        v10 = 18;
      }
    }
    else
    {
      LastError = GetLastError();
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_24;
      v10 = 17;
    }
    WPP_SF_Sl(v9[2], v10, v8, a1 + 100, LastError);
LABEL_24:
    FreeLibrary(v5);
    return LastError;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_SlD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v3, a1 + 100, LastError, v17);
  return LastError;
}

```

## disassembly

```asm
0x18001df8c  mov     [rsp-8+arg_8], rbx
0x18001df91  mov     [rsp-8+arg_10], rsi
0x18001df96  push    rbp
0x18001df97  push    rdi
0x18001df98  push    r14
0x18001df9a  lea     rbp, [rsp-1E0h]
0x18001dfa2  sub     rsp, 2E0h
0x18001dfa9  mov     rax, cs:__security_cookie
0x18001dfb0  xor     rax, rsp
0x18001dfb3  mov     [rbp+1F0h+var_20], rax
0x18001dfba  xorps   xmm0, xmm0
0x18001dfbd  mov     [rsp+2F0h+var_2C0], 1
0x18001dfc6  mov     r14, rcx
0x18001dfc9  xor     edx, edx; Val
0x18001dfcb  lea     rcx, [rbp+1F0h+Buffer]; void *
0x18001dfcf  mov     r8d, 208h; Size
0x18001dfd5  movups  [rsp+2F0h+var_2B8], xmm0
0x18001dfda  movups  [rsp+2F0h+var_2A8], xmm0
0x18001dfdf  call    memset_0
0x18001dfe4  mov     esi, 58h ; 'X'
0x18001dfe9  lea     rcx, [rsp+2F0h+var_290]; void *
0x18001dfee  mov     r8d, esi; Size
0x18001dff1  xor     edx, edx; Val
0x18001dff3  call    memset_0
0x18001dff8  mov     ebx, 104h
0x18001dffd  lea     rcx, [rbp+1F0h+Buffer]; lpBuffer
0x18001e001  mov     edx, ebx; uSize
0x18001e003  call    cs:__imp_GetSystemDirectoryW
0x18001e009  test    eax, eax
0x18001e00b  jnz     short loc_18001E051
0x18001e00d  call    cs:__imp_GetLastError
0x18001e013  mov     ebx, eax
0x18001e015  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e01c  lea     rax, WPP_GLOBAL_Control
0x18001e023  cmp     rcx, rax
0x18001e026  jz      loc_18001E22B
0x18001e02c  test    byte ptr [rcx+1Ch], 1
0x18001e030  jz      loc_18001E22B
0x18001e036  mov     rcx, [rcx+10h]
0x18001e03a  lea     edx, [rsi-4Ah]
0x18001e03d  mov     r9d, ebx
0x18001e040  lea     r8, WPP_fb4b6c20289c37c1f24720aba8866156_Traceguids
0x18001e047  call    WPP_SF_d
0x18001e04c  jmp     loc_18001E22B
0x18001e051  lea     r8, asc_18004AA98; "\\"
0x18001e058  mov     rdx, rbx
0x18001e05b  lea     rcx, [rbp+1F0h+Buffer]
0x18001e05f  call    cs:__imp__o_wcscat_s
0x18001e065  lea     rdi, [r14+64h]
0x18001e069  mov     rdx, rbx
0x18001e06c  mov     r8, rdi
0x18001e06f  lea     rcx, [rbp+1F0h+Buffer]
0x18001e073  call    cs:__imp__o_wcscat_s
0x18001e079  lea     r9, [rsp+2F0h+var_290]
0x18001e07e  mov     [rsp+2F0h+var_2C8], 0
0x18001e087  mov     r8d, 1003h
0x18001e08d  mov     [rsp+2F0h+var_290], esi
0x18001e091  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001e095  mov     [rsp+2F0h+var_2D0], 0
0x18001e09e  mov     rcx, rdi
0x18001e0a1  call    cs:__imp_WTGetPluginSignatureInfo
0x18001e0a7  mov     edx, [rsp+2F0h+var_28C]
0x18001e0ab  mov     ebx, eax
0x18001e0ad  test    eax, eax
0x18001e0af  js      loc_18001E1FE
0x18001e0b5  lea     eax, [rdx-5]
0x18001e0b8  cmp     eax, 1
0x18001e0bb  ja      loc_18001E1FE
0x18001e0c1  xor     edx, edx; hFile
0x18001e0c3  mov     r8d, 800h; dwFlags
0x18001e0c9  mov     rcx, rdi; lpLibFileName
0x18001e0cc  call    cs:__imp_LoadLibraryExW
0x18001e0d2  mov     rsi, rax
0x18001e0d5  test    rax, rax
0x18001e0d8  jnz     short loc_18001E11B
0x18001e0da  call    cs:__imp_GetLastError
0x18001e0e0  mov     ebx, eax
0x18001e0e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e0e9  lea     rax, WPP_GLOBAL_Control
0x18001e0f0  cmp     rcx, rax
0x18001e0f3  jz      loc_18001E22B
0x18001e0f9  test    byte ptr [rcx+1Ch], 1
0x18001e0fd  jz      loc_18001E22B
0x18001e103  mov     rcx, [rcx+10h]
0x18001e107  lea     edx, [rsi+10h]
0x18001e10a  mov     r9, rdi
0x18001e10d  mov     dword ptr [rsp+2F0h+var_2D0], ebx
0x18001e111  call    WPP_SF_Sl
0x18001e116  jmp     loc_18001E22B
0x18001e11b  lea     rdx, aPlugininitiali; "PluginInitialize"
0x18001e122  mov     rcx, rsi; hModule
0x18001e125  call    cs:__imp_GetProcAddress
0x18001e12b  mov     [r14], rax
0x18001e12e  test    rax, rax
0x18001e131  jnz     short loc_18001E163
0x18001e133  call    cs:__imp_GetLastError
0x18001e139  mov     ebx, eax
0x18001e13b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e142  lea     rax, WPP_GLOBAL_Control
0x18001e149  cmp     rcx, rax
0x18001e14c  jz      loc_18001E1ED
0x18001e152  test    byte ptr [rcx+1Ch], 1
0x18001e156  jz      loc_18001E1ED
0x18001e15c  mov     edx, 11h
0x18001e161  jmp     short loc_18001E1DD
0x18001e163  lea     rdx, aPluginuninitia; "PluginUninitialize"
0x18001e16a  mov     rcx, rsi; hModule
0x18001e16d  call    cs:__imp_GetProcAddress
0x18001e173  mov     [r14+8], rax
0x18001e177  test    rax, rax
0x18001e17a  jnz     short loc_18001E1A4
0x18001e17c  call    cs:__imp_GetLastError
0x18001e182  mov     ebx, eax
0x18001e184  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e18b  lea     rax, WPP_GLOBAL_Control
0x18001e192  cmp     rcx, rax
0x18001e195  jz      short loc_18001E1ED
0x18001e197  test    byte ptr [rcx+1Ch], 1
0x18001e19b  jz      short loc_18001E1ED
0x18001e19d  mov     edx, 12h
0x18001e1a2  jmp     short loc_18001E1DD
0x18001e1a4  mov     rax, [r14]
0x18001e1a7  lea     r8, [r14+10h]
0x18001e1ab  lea     rdx, [r14+50h]
0x18001e1af  lea     rcx, [rsp+2F0h+var_2C0]
0x18001e1b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1b9  mov     ebx, eax
0x18001e1bb  test    eax, eax
0x18001e1bd  jz      short loc_18001E1F8
0x18001e1bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e1c6  lea     rax, WPP_GLOBAL_Control
0x18001e1cd  cmp     rcx, rax
0x18001e1d0  jz      short loc_18001E1ED
0x18001e1d2  test    byte ptr [rcx+1Ch], 1
0x18001e1d6  jz      short loc_18001E1ED
0x18001e1d8  mov     edx, 13h
0x18001e1dd  mov     rcx, [rcx+10h]
0x18001e1e1  mov     r9, rdi
0x18001e1e4  mov     dword ptr [rsp+2F0h+var_2D0], ebx
0x18001e1e8  call    WPP_SF_Sl
0x18001e1ed  mov     rcx, rsi; hLibModule
0x18001e1f0  call    cs:__imp_FreeLibrary
0x18001e1f6  jmp     short loc_18001E22B
0x18001e1f8  mov     [r14+58h], rsi
0x18001e1fc  jmp     short loc_18001E22B
0x18001e1fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e205  lea     rax, WPP_GLOBAL_Control
0x18001e20c  cmp     rcx, rax
0x18001e20f  jz      short loc_18001E22B
0x18001e211  test    byte ptr [rcx+1Ch], 1
0x18001e215  jz      short loc_18001E22B
0x18001e217  mov     rcx, [rcx+10h]
0x18001e21b  mov     r9, rdi
0x18001e21e  mov     dword ptr [rsp+2F0h+var_2C8], edx
0x18001e222  mov     dword ptr [rsp+2F0h+var_2D0], ebx
0x18001e226  call    WPP_SF_SlD
0x18001e22b  mov     eax, ebx
0x18001e22d  mov     rcx, [rbp+1F0h+var_20]
0x18001e234  xor     rcx, rsp; StackCookie
0x18001e237  call    __security_check_cookie
0x18001e23c  lea     r11, [rsp+2F0h+var_10]
0x18001e244  mov     rbx, [r11+28h]
0x18001e248  mov     rsi, [r11+30h]
0x18001e24c  mov     rsp, r11
0x18001e24f  pop     r14
0x18001e251  pop     rdi
0x18001e252  pop     rbp
0x18001e253  retn
```
