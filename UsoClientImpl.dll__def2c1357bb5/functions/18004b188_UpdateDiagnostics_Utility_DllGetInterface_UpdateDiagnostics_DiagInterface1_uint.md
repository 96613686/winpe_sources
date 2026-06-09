# UpdateDiagnostics::Utility::DllGetInterface<UpdateDiagnostics::DiagInterface1>(uint)

- ea: `0x18004b188`
- end: `0x18004b3e8`
- name: `??$DllGetInterface@UDiagInterface1@UpdateDiagnostics@@@Utility@UpdateDiagnostics@@SAPEAUDiagInterface1@1@I@Z`
- size: `608`
- prototype: `LPVOID __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180048978`

## callees

- `0x180009380`
- `0x18002e030`
- `0x18002e3dc`
- `0x18002e5c0`
- `0x18002ebe8`
- `0x18002ec24`
- `0x18002ed04`
- `0x18002ed7c`
- `0x18002ff90`
- `0x180034a30`
- `0x18004b188`
- `0x180056500`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004b305`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004b305`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004b391`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004b391`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004b35d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004b35d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b216`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b216`

## string_xrefs

- `0x18004b353`: `DllGetUpdateDiagnosticInterface`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID __fastcall UpdateDiagnostics::Utility::DllGetInterface<UpdateDiagnostics::DiagInterface1>(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbx
  __int64 v3; // rcx
  BOOL v4; // r8d
  LPCWSTR *v5; // rcx
  __int64 v6; // rdx
  const wchar_t *root_name_end; // rax
  const wchar_t *v8; // rcx
  DWORD v9; // r8d
  const WCHAR *v10; // rcx
  HMODULE Library; // rax
  HMODULE v12; // rbx
  LPCWSTR *v13; // rdx
  FARPROC ProcAddress; // rax
  const char *v15; // r9
  int v16; // eax
  LPVOID v17; // rdi
  int v19; // [rsp+28h] [rbp-19h]
  const wchar_t *v20; // [rsp+38h] [rbp-9h] BYREF
  __int64 v21; // [rsp+40h] [rbp-1h]
  LPVOID pv; // [rsp+48h] [rbp+7h] BYREF
  _QWORD v23[4]; // [rsp+50h] [rbp+Fh] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+70h] [rbp+2Fh] BYREF
  __m128i si128; // [rsp+80h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+A0h] [rbp+5Fh]

  *(_OWORD *)lpLibFileName = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpLibFileName[0]) = 0;
  pv = 0;
  wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(
    &pv,
    a2,
    0x180000000uLL);
  v2 = -1;
  v3 = -1;
  do
    ++v3;
  while ( *((_WORD *)pv + v3) );
  v20 = (const wchar_t *)pv;
  v21 = v3;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v23, &v20);
  if ( pv )
    CoTaskMemFree(pv);
  std::filesystem::path::remove_filename((std::filesystem::path *)v23);
  std::wstring::operator=(lpLibFileName);
  std::wstring::~wstring(v23);
  do
    ++v2;
  while ( UpdateDiagnostics::Constants::filenameUpdateDiagnosticsDll[v2] );
  v20 = UpdateDiagnostics::Constants::filenameUpdateDiagnosticsDll;
  v21 = v2;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v23, &v20);
  std::filesystem::path::operator/=(lpLibFileName);
  std::wstring::~wstring(v23);
  v23[0] = 24;
  v4 = 1;
  v23[1] = 1;
  v23[2] = 0x180000000uLL;
  v5 = lpLibFileName;
  if ( si128.m128i_i64[1] > 7uLL )
    v5 = (LPCWSTR *)lpLibFileName[0];
  v6 = (2 * si128.m128i_i64[0]) >> 1;
  if ( v6 < 2 || (*(_DWORD *)v5 & 0xFFFFFFDF) - 3801153 >= 0x1A )
  {
    root_name_end = std::filesystem::_Find_root_name_end(
                      (std::filesystem *)v5,
                      (const wchar_t *const)v5 + si128.m128i_i64[0],
                      (const wchar_t *const)1);
    v4 = v8 != root_name_end;
  }
  else if ( v6 < 3 || *((_WORD *)v5 + 2) != 92 && *((_WORD *)v5 + 2) != 47 )
  {
    v4 = 0;
  }
  v9 = (8 * v4) | 0x80;
  v10 = (const WCHAR *)lpLibFileName;
  if ( si128.m128i_i64[1] > 7uLL )
    v10 = lpLibFileName[0];
  Library = LoadLibraryExW(v10, 0, v9);
  v12 = Library;
  v20 = (const wchar_t *)Library;
  v13 = lpLibFileName;
  if ( si128.m128i_i64[1] > 7uLL )
    v13 = (LPCWSTR *)lpLibFileName[0];
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x6C,
    (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDiag.hpp",
    (const char *)(Library == 0),
    (void *)"Error loading library %s",
    (const char *)v13,
    v20);
  ProcAddress = GetProcAddress(v12, "DllGetUpdateDiagnosticInterface");
  if ( !ProcAddress )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x6F,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDiag.hpp",
      v15);
  pv = 0;
  v16 = ((__int64 (__fastcall *)(LPVOID *, _QWORD *))ProcAddress)(&pv, v23);
  if ( v16 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x73,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDiag.hpp",
      (const char *)(unsigned int)v16,
      v19);
  v17 = pv;
  if ( v12 )
    FreeLibrary(v12);
  std::wstring::~wstring(lpLibFileName);
  return v17;
}

```

## disassembly

```asm
0x18004b188  mov     rax, rsp
0x18004b18b  mov     [rax+8], rbx
0x18004b18f  mov     [rax+10h], rsi
0x18004b193  mov     [rax+18h], rdi
0x18004b197  push    rbp
0x18004b198  lea     rbp, [rax-5Fh]
0x18004b19c  sub     rsp, 90h
0x18004b1a3  mov     rax, cs:__security_cookie
0x18004b1aa  xor     rax, rsp
0x18004b1ad  mov     [rbp+57h+var_8], rax
0x18004b1b1  xor     esi, esi
0x18004b1b3  xorps   xmm0, xmm0
0x18004b1b6  movups  xmmword ptr [rbp+57h+lpLibFileName], xmm0
0x18004b1ba  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18004b1c2  movdqu  [rbp+57h+var_18], xmm1
0x18004b1c7  mov     word ptr [rbp+57h+lpLibFileName], si
0x18004b1cb  mov     [rbp+57h+pv], rsi
0x18004b1cf  lea     rdi, cs:180000000h
0x18004b1d6  mov     r8, rdi
0x18004b1d9  lea     rcx, [rbp+57h+pv]
0x18004b1dd  call    ??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEAXPEAUHINSTANCE__@@@Z; wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *)
0x18004b1e2  nop
0x18004b1e3  mov     rax, [rbp+57h+pv]
0x18004b1e7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004b1eb  mov     rcx, rbx
0x18004b1ee  inc     rcx
0x18004b1f1  cmp     [rax+rcx*2], si
0x18004b1f5  jnz     short loc_18004B1EE
0x18004b1f7  mov     [rbp+57h+var_60], rax
0x18004b1fb  mov     [rbp+57h+var_58], rcx
0x18004b1ff  lea     rdx, [rbp+57h+var_60]
0x18004b203  lea     rcx, [rbp+57h+var_48]
0x18004b207  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x18004b20c  nop
0x18004b20d  mov     rcx, [rbp+57h+pv]; pv
0x18004b211  test    rcx, rcx
0x18004b214  jz      short loc_18004B21D
0x18004b216  call    cs:__imp_CoTaskMemFree
0x18004b21c  nop
0x18004b21d  lea     rcx, [rbp+57h+var_48]; this
0x18004b221  call    ?remove_filename@path@filesystem@std@@QEAAAEAV123@XZ; std::filesystem::path::remove_filename(void)
0x18004b226  mov     rdx, rax
0x18004b229  lea     rcx, [rbp+57h+lpLibFileName]; void *
0x18004b22d  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004b232  nop
0x18004b233  lea     rcx, [rbp+57h+var_48]; void *
0x18004b237  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b23c  mov     rax, cs:?filenameUpdateDiagnosticsDll@Constants@UpdateDiagnostics@@2PEB_WEB; wchar_t const * const UpdateDiagnostics::Constants::filenameUpdateDiagnosticsDll
0x18004b243  inc     rbx
0x18004b246  cmp     [rax+rbx*2], si
0x18004b24a  jnz     short loc_18004B243
0x18004b24c  mov     [rbp+57h+var_60], rax
0x18004b250  mov     [rbp+57h+var_58], rbx
0x18004b254  lea     rdx, [rbp+57h+var_60]
0x18004b258  lea     rcx, [rbp+57h+var_48]
0x18004b25c  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x18004b261  nop
0x18004b262  lea     rdx, [rbp+57h+var_48]
0x18004b266  lea     rcx, [rbp+57h+lpLibFileName]; void *
0x18004b26a  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x18004b26f  nop
0x18004b270  lea     rcx, [rbp+57h+var_48]; void *
0x18004b274  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b279  mov     [rbp+57h+var_48], 18h
0x18004b281  mov     r8d, 1; wchar_t *
0x18004b287  mov     [rbp+57h+var_40], r8
0x18004b28b  mov     [rbp+57h+var_38], rdi
0x18004b28f  lea     rcx, [rbp+57h+lpLibFileName]
0x18004b293  cmp     qword ptr [rbp+57h+var_18+8], 7
0x18004b298  cmova   rcx, [rbp+57h+lpLibFileName]; this
0x18004b29d  mov     rax, qword ptr [rbp+57h+var_18]
0x18004b2a1  lea     r9, [rax+rax]
0x18004b2a5  mov     rdx, r9
0x18004b2a8  sar     rdx, 1
0x18004b2ab  cmp     rdx, 2
0x18004b2af  jl      short loc_18004B2D9
0x18004b2b1  mov     eax, [rcx]
0x18004b2b3  and     eax, 0FFFFFFDFh
0x18004b2b6  sub     eax, 3A0041h
0x18004b2bb  cmp     eax, 1Ah
0x18004b2be  jnb     short loc_18004B2D9
0x18004b2c0  cmp     rdx, 3
0x18004b2c4  jl      short loc_18004B2D4
0x18004b2c6  cmp     word ptr [rcx+4], 5Ch ; '\'
0x18004b2cb  jz      short loc_18004B2EC
0x18004b2cd  cmp     word ptr [rcx+4], 2Fh ; '/'
0x18004b2d2  jz      short loc_18004B2EC
0x18004b2d4  mov     r8d, esi
0x18004b2d7  jmp     short loc_18004B2EC
0x18004b2d9  lea     rdx, [r9+rcx]; wchar_t *
0x18004b2dd  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x18004b2e2  mov     r8d, esi
0x18004b2e5  cmp     rcx, rax
0x18004b2e8  setnz   r8b
0x18004b2ec  shl     r8d, 3
0x18004b2f0  bts     r8d, 7; dwFlags
0x18004b2f5  lea     rcx, [rbp+57h+lpLibFileName]
0x18004b2f9  cmp     qword ptr [rbp+57h+var_18+8], 7
0x18004b2fe  cmova   rcx, [rbp+57h+lpLibFileName]; lpLibFileName
0x18004b303  xor     edx, edx; hFile
0x18004b305  call    cs:__imp_LoadLibraryExW
0x18004b30b  mov     rbx, rax
0x18004b30e  mov     [rbp+57h+var_60], rax
0x18004b312  lea     rdx, [rbp+57h+lpLibFileName]
0x18004b316  cmp     qword ptr [rbp+57h+var_18+8], 7
0x18004b31b  cmova   rdx, [rbp+57h+lpLibFileName]
0x18004b320  test    rax, rax
0x18004b323  setz    al
0x18004b326  mov     rcx, [rbp+5Fh]; this
0x18004b32a  mov     [rsp+90h+var_68], rdx; char *
0x18004b32f  lea     rdx, aErrorLoadingLi; "Error loading library %s"
0x18004b336  mov     [rsp+90h+var_70], rdx; int
0x18004b33b  movzx   r9d, al; char *
0x18004b33f  lea     rdi, aCW1SSrcCalliop; "C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDi"...
0x18004b346  mov     r8, rdi; unsigned int
0x18004b349  mov     edx, 6Ch ; 'l'; void *
0x18004b34e  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18004b353  lea     rdx, aDllgetupdatedi; "DllGetUpdateDiagnosticInterface"
0x18004b35a  mov     rcx, rbx; hModule
0x18004b35d  call    cs:__imp_GetProcAddress
0x18004b363  mov     rcx, [rbp+5Fh]; this
0x18004b367  test    rax, rax
0x18004b36a  jz      short loc_18004B3DA
0x18004b36c  mov     [rbp+57h+pv], rsi
0x18004b370  lea     rdx, [rbp+57h+var_48]
0x18004b374  lea     rcx, [rbp+57h+pv]
0x18004b378  call    _guard_dispatch_icall
0x18004b37d  mov     rcx, [rbp+5Fh]; this
0x18004b381  test    eax, eax
0x18004b383  js      short loc_18004B3C9
0x18004b385  mov     rdi, [rbp+57h+pv]
0x18004b389  test    rbx, rbx
0x18004b38c  jz      short loc_18004B398
0x18004b38e  mov     rcx, rbx; hLibModule
0x18004b391  call    cs:__imp_FreeLibrary
0x18004b397  nop
0x18004b398  lea     rcx, [rbp+57h+lpLibFileName]; void *
0x18004b39c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b3a1  mov     rax, rdi
0x18004b3a4  mov     rcx, [rbp+57h+var_8]
0x18004b3a8  xor     rcx, rsp; StackCookie
0x18004b3ab  call    __security_check_cookie
0x18004b3b0  lea     r11, [rsp+90h+var_s0]
0x18004b3b8  mov     rbx, [r11+10h]
0x18004b3bc  mov     rsi, [r11+18h]
0x18004b3c0  mov     rdi, [r11+20h]
0x18004b3c4  mov     rsp, r11
0x18004b3c7  pop     rbp
0x18004b3c8  retn
0x18004b3c9  mov     r9d, eax; char *
0x18004b3cc  mov     r8, rdi; unsigned int
0x18004b3cf  mov     edx, 73h ; 's'; void *
0x18004b3d4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004b3da  mov     r8, rdi; unsigned int
0x18004b3dd  mov     edx, 6Fh ; 'o'; void *
0x18004b3e2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
