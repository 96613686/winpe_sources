# LogonSoundHelpers::LogonSoundPlayer::_PlayLogonSound(void)

- ea: `0x180043d7c`
- end: `0x1800440ad`
- name: `?_PlayLogonSound@LogonSoundPlayer@LogonSoundHelpers@@AEAAXXZ`
- size: `817`
- prototype: `void __fastcall(LogonSoundHelpers::LogonSoundPlayer *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180043d40`

## callees

- `0x180008094`
- `0x18000df10`
- `0x18002c268`
- `0x180043d7c`
- `0x1800440b4`
- `0x1800440d0`
- `0x180063cc8`
- `0x180066a54`
- `0x18006c000`
- `0x180082224`
- `0x180083824`
- `0x18008765c`
- `0x18009d010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180043f90`
- `KERNEL32!LoadLibraryExW` at `0x180043f90`
- `KERNEL32!CreateFileW` at `0x180043ecb`
- `KERNEL32!CreateFileW` at `0x180043ecb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180043e4d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180043e4d`
- `SHLWAPI!PathFileExistsW` at `0x180043e75`
- `SHLWAPI!PathFileExistsW` at `0x180043e75`

## string_xrefs

- `0x180043f89`: `imageres.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall LogonSoundHelpers::LogonSoundPlayer::_PlayLogonSound(
        LogonSoundHelpers::LogonSoundPlayer *this,
        __int64 a2)
{
  int v3; // eax
  char v4; // bl
  unsigned __int64 v5; // rdx
  HANDLE FileW; // rax
  int v7; // eax
  __int64 v8; // rsi
  __int64 (__fastcall *v9)(__int64, GUID *, __int64 *, __int64); // rdi
  __int64 v10; // rbx
  int v11; // eax
  __int64 *v12; // rbx
  HMODULE Library; // rax
  const char *v14; // r9
  __int64 v15; // rsi
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, GUID *, __int64 *, __int64); // rbx
  int v18; // eax
  int v19; // eax
  __int64 v20; // rcx
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[28]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszPath[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  if ( *((_BYTE *)this + 40) || (v3 = LogonSoundHelpers::LogonSoundPlayer::_InitializeAudioPlayer(this), v3 >= 0) )
  {
    v23 = 0;
    v4 = 1;
    LOBYTE(a2) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_HVSTest>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_HVSTest>::GetImpl'::`2'::impl,
      a2);
    *(_OWORD *)v26 = *(_OWORD *)L"\\Startup2.wav";
    *(_OWORD *)&v26[12] = *(_OWORD *)L"up2.wav";
    pcbData = 520;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\EditionOverrides",
            L"packagebase",
            2u,
            0,
            pszPath,
            &pcbData)
      && (int)StringCbCatW(pszPath, v5, (const unsigned __int16 *)v26) >= 0
      && PathFileExistsW(pszPath) )
    {
      v25 = 0;
      *(_QWORD *)v26 = &v25;
      *(_QWORD *)&v26[8] = 0;
      v26[16] = 1;
      FileW = CreateFileW(pszPath, 0x80000000, 1u, 0, 3u, 4u, 0);
      v7 = ResultFromWin32Handle(FileW, (void **)&v26[8]);
      if ( v7 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xFE,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\logonsoundhelpers.cpp",
          (const char *)(unsigned int)v7,
          pdwTypea);
        v4 = 0;
      }
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(v26);
      if ( v4 )
      {
        v8 = *((_QWORD *)this + 3);
        v9 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *, __int64))(*(_QWORD *)v8 + 32LL);
        v10 = v25;
        Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v23);
        v11 = v9(v8, &GUID_aa66e9d1_a5a6_435d_8677_155e8a01ee9f, &v23, v10);
        if ( v11 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x100,
            (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\logonsoundhelpers.cpp",
            (const char *)(unsigned int)v11,
            pdwTypea);
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v25);
    }
    if ( !v23 )
    {
      v12 = (__int64 *)((char *)this + 8);
      if ( !*((_QWORD *)this + 1) )
      {
        Library = LoadLibraryExW(L"imageres.dll", 0, 0x820u);
        wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
          (char *)this + 8,
          Library);
        if ( !*v12 )
          wil::details::in1diag3::_Log_GetLastError(
            retaddr,
            (void *)0x10B,
            (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\logonsoundhelpers.cpp",
            v14);
      }
      v15 = *v12;
      if ( *v12 )
      {
        v16 = *((_QWORD *)this + 3);
        v17 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *, __int64))(*(_QWORD *)v16 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v23);
        v18 = v17(v16, &GUID_aa66e9d1_a5a6_435d_8677_155e8a01ee9f, &v23, v15);
        if ( v18 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x110,
            (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\logonsoundhelpers.cpp",
            (const char *)(unsigned int)v18,
            5080);
      }
    }
    if ( v23 )
    {
      v19 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 4) + 40LL))(
              *((_QWORD *)this + 4),
              v23,
              0,
              0);
      if ( v19 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x116,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\logonsoundhelpers.cpp",
          (const char *)(unsigned int)v19,
          0);
    }
    v20 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xE4,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\logonsoundhelpers.cpp",
      (const char *)(unsigned int)v3,
      pdwType);
  }
}

```

## disassembly

```asm
0x180043d7c  mov     [rsp-8+arg_8], rbx
0x180043d81  mov     [rsp-8+arg_10], rsi
0x180043d86  push    rbp
0x180043d87  push    rdi
0x180043d88  push    r15
0x180043d8a  lea     rbp, [rsp-1A0h]
0x180043d92  sub     rsp, 2A0h
0x180043d99  mov     rax, cs:__security_cookie
0x180043da0  xor     rax, rsp
0x180043da3  mov     [rbp+1B0h+var_20], rax
0x180043daa  mov     r15, rcx
0x180043dad  cmp     byte ptr [rcx+28h], 0
0x180043db1  jnz     short loc_180043DDC
0x180043db3  call    ?_InitializeAudioPlayer@LogonSoundPlayer@LogonSoundHelpers@@AEAAJXZ; LogonSoundHelpers::LogonSoundPlayer::_InitializeAudioPlayer(void)
0x180043db8  mov     rcx, [rbp+1B8h]; this
0x180043dbf  test    eax, eax
0x180043dc1  jns     short loc_180043DDC
0x180043dc3  mov     r9d, eax; char *
0x180043dc6  lea     r8, aPcshellShellAu_18; "pcshell\\shell\\auth\\authux\\controlle"...
0x180043dcd  mov     edx, 0E4h; void *
0x180043dd2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180043dd7  jmp     loc_180044086
0x180043ddc  mov     [rsp+2B0h+var_270], 0
0x180043de5  mov     ebx, 1
0x180043dea  mov     dl, bl
0x180043dec  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HVSTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HVSTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HVSTest> `wil::Feature<__WilFeatureTraits_Feature_HVSTest>::GetImpl(void)'::`2'::impl
0x180043df3  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_HVSTest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HVSTest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180043df8  movups  xmm0, xmmword ptr cs:aStartup2Wav; "\\Startup2.wav"
0x180043dff  movups  xmmword ptr [rsp+2B0h+var_258], xmm0
0x180043e04  movups  xmm1, xmmword ptr cs:aStartup2Wav+0Ch; "up2.wav"
0x180043e0b  movups  xmmword ptr [rsp+2B0h+var_258+0Ch], xmm1
0x180043e10  mov     [rsp+2B0h+var_268], 208h
0x180043e18  lea     rax, [rsp+2B0h+var_268]
0x180043e1d  mov     [rsp+2B0h+pcbData], rax; pcbData
0x180043e22  lea     rax, [rbp+1B0h+pszPath]
0x180043e26  mov     [rsp+2B0h+pvData], rax; pvData
0x180043e2b  mov     [rsp+2B0h+pdwType], 0; pdwType
0x180043e34  lea     r9d, [rbx+1]; dwFlags
0x180043e38  lea     r8, aPackagebase; "packagebase"
0x180043e3f  lea     rdx, aSoftwareMicros_29; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180043e46  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180043e4d  call    cs:__imp_RegGetValueW
0x180043e53  test    eax, eax
0x180043e55  jnz     loc_180043F6B
0x180043e5b  lea     r8, [rsp+2B0h+var_258]; unsigned __int16 *
0x180043e60  lea     rcx, [rbp+1B0h+pszPath]; unsigned __int16 *
0x180043e64  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180043e69  test    eax, eax
0x180043e6b  js      loc_180043F6B
0x180043e71  lea     rcx, [rbp+1B0h+pszPath]; pszPath
0x180043e75  call    cs:__imp_PathFileExistsW
0x180043e7b  test    eax, eax
0x180043e7d  jz      loc_180043F6B
0x180043e83  mov     [rsp+2B0h+var_260], 0
0x180043e8c  lea     rax, [rsp+2B0h+var_260]
0x180043e91  mov     [rsp+2B0h+var_258], rax
0x180043e96  mov     [rsp+2B0h+var_258+8], 0
0x180043e9f  mov     [rsp+2B0h+var_248], bl
0x180043ea3  mov     [rsp+2B0h+pcbData], 0; hTemplateFile
0x180043eac  mov     dword ptr [rsp+2B0h+pvData], 4; dwFlagsAndAttributes
0x180043eb4  mov     dword ptr [rsp+2B0h+pdwType], 3; int
0x180043ebc  xor     r9d, r9d; lpSecurityAttributes
0x180043ebf  mov     r8d, ebx; dwShareMode
0x180043ec2  mov     edx, 80000000h; dwDesiredAccess
0x180043ec7  lea     rcx, [rbp+1B0h+pszPath]; lpFileName
0x180043ecb  call    cs:__imp_CreateFileW
0x180043ed1  lea     rdx, [rsp+2B0h+var_258+8]; void **
0x180043ed6  mov     rcx, rax; void *
0x180043ed9  call    ?ResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; ResultFromWin32Handle(void *,void * *)
0x180043ede  mov     rcx, [rbp+1B8h]; this
0x180043ee5  test    eax, eax
0x180043ee7  jns     short loc_180043EFF
0x180043ee9  mov     r9d, eax; char *
0x180043eec  lea     r8, aPcshellShellAu_18; "pcshell\\shell\\auth\\authux\\controlle"...
0x180043ef3  mov     edx, 0FEh; void *
0x180043ef8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180043efd  xor     bl, bl
0x180043eff  lea     rcx, [rsp+2B0h+var_258]
0x180043f04  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180043f09  test    bl, bl
0x180043f0b  jz      short loc_180043F61
0x180043f0d  mov     rsi, [r15+18h]
0x180043f11  mov     rax, [rsi]
0x180043f14  mov     rdi, [rax+20h]
0x180043f18  mov     rbx, [rsp+2B0h+var_260]
0x180043f1d  lea     rcx, [rsp+2B0h+var_270]
0x180043f22  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180043f27  mov     r9, rbx
0x180043f2a  lea     r8, [rsp+2B0h+var_270]
0x180043f2f  lea     rdx, _GUID_aa66e9d1_a5a6_435d_8677_155e8a01ee9f
0x180043f36  mov     rcx, rsi
0x180043f39  mov     rax, rdi
0x180043f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f41  mov     rcx, [rbp+1B8h]; this
0x180043f48  test    eax, eax
0x180043f4a  jns     short loc_180043F61
0x180043f4c  mov     r9d, eax; char *
0x180043f4f  lea     r8, aPcshellShellAu_18; "pcshell\\shell\\auth\\authux\\controlle"...
0x180043f56  mov     edx, 100h; void *
0x180043f5b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180043f60  nop
0x180043f61  lea     rcx, [rsp+2B0h+var_260]
0x180043f66  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180043f6b  cmp     [rsp+2B0h+var_270], 0
0x180043f71  jnz     loc_18004401D
0x180043f77  lea     rbx, [r15+8]
0x180043f7b  cmp     qword ptr [rbx], 0
0x180043f7f  jnz     short loc_180043FBF
0x180043f81  xor     edx, edx; hFile
0x180043f83  mov     r8d, 820h; dwFlags
0x180043f89  lea     rcx, aImageresDll; "imageres.dll"
0x180043f90  call    cs:__imp_LoadLibraryExW
0x180043f96  mov     rdx, rax
0x180043f99  mov     rcx, rbx
0x180043f9c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x180043fa1  mov     rcx, [rbp+1B8h]; this
0x180043fa8  cmp     qword ptr [rbx], 0
0x180043fac  jnz     short loc_180043FBF
0x180043fae  lea     r8, aPcshellShellAu_18; "pcshell\\shell\\auth\\authux\\controlle"...
0x180043fb5  mov     edx, 10Bh; void *
0x180043fba  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180043fbf  mov     rsi, [rbx]
0x180043fc2  test    rsi, rsi
0x180043fc5  jz      short loc_18004401D
0x180043fc7  mov     rdi, [r15+18h]
0x180043fcb  mov     rax, [rdi]
0x180043fce  mov     rbx, [rax+30h]
0x180043fd2  lea     rcx, [rsp+2B0h+var_270]
0x180043fd7  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180043fdc  mov     dword ptr [rsp+2B0h+pdwType], 13D8h; int
0x180043fe4  mov     r9, rsi
0x180043fe7  lea     r8, [rsp+2B0h+var_270]
0x180043fec  lea     rdx, _GUID_aa66e9d1_a5a6_435d_8677_155e8a01ee9f
0x180043ff3  mov     rcx, rdi
0x180043ff6  mov     rax, rbx
0x180043ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043ffe  mov     rcx, [rbp+1B8h]; this
0x180044005  test    eax, eax
0x180044007  jns     short loc_18004401D
0x180044009  mov     r9d, eax; char *
0x18004400c  lea     r8, aPcshellShellAu_18; "pcshell\\shell\\auth\\authux\\controlle"...
0x180044013  mov     edx, 110h; void *
0x180044018  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004401d  mov     rdx, [rsp+2B0h+var_270]
0x180044022  test    rdx, rdx
0x180044025  jz      short loc_180044066
0x180044027  mov     rcx, [r15+20h]
0x18004402b  mov     rax, [rcx]
0x18004402e  mov     [rsp+2B0h+pdwType], 0; int
0x180044037  xor     r9d, r9d
0x18004403a  xor     r8d, r8d
0x18004403d  mov     rax, [rax+28h]
0x180044041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044046  mov     rcx, [rbp+1B8h]; this
0x18004404d  test    eax, eax
0x18004404f  jns     short loc_180044066
0x180044051  mov     r9d, eax; char *
0x180044054  lea     r8, aPcshellShellAu_18; "pcshell\\shell\\auth\\authux\\controlle"...
0x18004405b  mov     edx, 116h; void *
0x180044060  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180044065  nop
0x180044066  mov     rcx, [rsp+2B0h+var_270]
0x18004406b  test    rcx, rcx
0x18004406e  jz      short loc_180044086
0x180044070  mov     [rsp+2B0h+var_270], 0
0x180044079  mov     rax, [rcx]
0x18004407c  mov     rax, [rax+10h]
0x180044080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044085  nop
0x180044086  mov     rcx, [rbp+1B0h+var_20]
0x18004408d  xor     rcx, rsp; StackCookie
0x180044090  call    __security_check_cookie
0x180044095  lea     r11, [rsp+2B0h+var_10]
0x18004409d  mov     rbx, [r11+28h]
0x1800440a1  mov     rsi, [r11+30h]
0x1800440a5  mov     rsp, r11
0x1800440a8  pop     r15
0x1800440aa  pop     rdi
0x1800440ab  pop     rbp
0x1800440ac  retn
```
