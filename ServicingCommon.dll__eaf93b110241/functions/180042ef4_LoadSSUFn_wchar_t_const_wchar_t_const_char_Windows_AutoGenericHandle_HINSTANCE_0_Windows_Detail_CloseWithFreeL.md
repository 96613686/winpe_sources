# LoadSSUFn(wchar_t const *,wchar_t const *,char *,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> *,__int64 (**)(void),IServicingLoader * *)

- ea: `0x180042ef4`
- end: `0x18004323b`
- name: `?LoadSSUFn@@YAJPEB_W0PEADPEAV?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@PEAP6A_JXZPEAPEAVIServicingLoader@@@Z`
- size: `839`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800433f0`
- `0x180043860`

## callees

- `0x180002564`
- `0x18001e4fc`
- `0x18001e51c`
- `0x18001f660`
- `0x1800293a0`
- `0x18003e8f8`
- `0x18003ea38`
- `0x18003ea7c`
- `0x18003eb4c`
- `0x18003fcf0`
- `0x18004027c`
- `0x180041a00`
- `0x180042da0`
- `0x180042ef4`
- `0x180043380`
- `0x1800a0020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18004313a`
- `KERNEL32!GetProcAddress` at `0x180043166`
- `KERNEL32!GetProcAddress` at `0x1800431d3`
- `KERNEL32!GetProcAddress` at `0x18004313a`
- `KERNEL32!GetProcAddress` at `0x180043166`
- `KERNEL32!GetProcAddress` at `0x1800431d3`
- `KERNEL32!LoadLibraryExW` at `0x1800430e1`
- `KERNEL32!LoadLibraryExW` at `0x1800430e1`

## string_xrefs

- `0x180042f68`: `TurboStack.dll`
- `0x18004309f`: `TurboStack.dll`

## pseudocode

```c
__int64 __fastcall LoadSSUFn(__int64 a1, HMODULE a2, const CHAR *a3, HMODULE *a4, FARPROC *a5, _QWORD *a6)
{
  int v8; // eax
  unsigned int LastError; // ebx
  int v10; // eax
  const wchar_t *v11; // rax
  int FilePath; // eax
  __int64 v13; // rdx
  const wchar_t *v14; // rax
  bool v15; // dl
  const WCHAR *v16; // rax
  HMODULE Library; // rax
  const char *v18; // r9
  HMODULE v19; // rbx
  __int64 v20; // rdx
  FARPROC ProcAddress; // rax
  FARPROC v22; // rax
  int v23; // edi
  __int64 v24; // rdx
  FARPROC v25; // rax
  int v27; // [rsp+20h] [rbp-B9h]
  __int128 v28; // [rsp+30h] [rbp-A9h] BYREF
  const wchar_t *v29; // [rsp+40h] [rbp-99h]
  __int128 v30; // [rsp+48h] [rbp-91h] BYREF
  __int64 v31; // [rsp+58h] [rbp-81h]
  _QWORD v32[3]; // [rsp+60h] [rbp-79h] BYREF
  HMODULE hModule; // [rsp+78h] [rbp-61h] BYREF
  __int64 v34; // [rsp+80h] [rbp-59h] BYREF
  __int128 v35; // [rsp+90h] [rbp-49h] BYREF
  __int64 v36; // [rsp+A0h] [rbp-39h]
  __int64 v37; // [rsp+A8h] [rbp-31h]
  __int64 v38; // [rsp+B0h] [rbp-29h]
  __int64 v39; // [rsp+B8h] [rbp-21h]
  __int64 v40; // [rsp+C0h] [rbp-19h]
  __int64 v41; // [rsp+C8h] [rbp-11h]
  char v42; // [rsp+D0h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+4Fh]

  v34 = a1;
  hModule = a2;
  v31 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v30 = 0;
  if ( !a2 )
  {
    v29 = 0;
    v32[0] = 14;
    v32[1] = 14;
    v32[2] = L"Windows";
    v28 = 0;
    v10 = Windows::StringUtil::Rtl::CombineAndNullTerminateWin32Paths<wchar_t const *,_LUNICODE_STRING>(&v34, v32, &v28);
    if ( v10 >= 0 )
    {
      v11 = (const wchar_t *)Windows::StringUtil::c_str<Windows::Auto<_LUNICODE_STRING>>(&v28);
      FilePath = Windows::AutoSsShim::TryLoadFromWindowsPath((Windows::AutoSsShim *)&v35, v11, 0);
      LastError = FilePath;
      if ( FilePath >= 0 )
      {
        v14 = (const wchar_t *)Windows::StringUtil::c_str<Windows::Auto<_LUNICODE_STRING>>(&v28);
        FilePath = Windows::AutoSsShim::Bind((Windows::AutoSsShim *)&v35, v14, 0, 0, 0);
        LastError = FilePath;
        if ( FilePath >= 0 )
        {
          FilePath = Windows::AutoSsShim::Preload((Windows::AutoSsShim *)&v35, v15);
          LastError = FilePath;
          if ( FilePath >= 0 )
          {
            FilePath = Windows::AutoSsShim::GetFilePath(
                         (Windows::AutoSsShim *)&v35,
                         (wchar_t *)L"TurboStack.dll",
                         (struct _LUNICODE_STRING *)&v30);
            LastError = FilePath;
            if ( FilePath >= 0 )
            {
              Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v28);
LABEL_17:
              hModule = 0;
              v16 = (const WCHAR *)Windows::StringUtil::c_str<Windows::Auto<_LUNICODE_STRING>>(&v30);
              Library = LoadLibraryExW(v16, 0, 8u);
              Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(
                &hModule,
                Library);
              v19 = hModule;
              if ( hModule )
              {
                if ( g_TestMode )
                {
                  ProcAddress = GetProcAddress(hModule, "SetTestMode");
                  if ( !ProcAddress )
                  {
                    v20 = 135;
                    goto LABEL_19;
                  }
                  ((void (__fastcall *)(__int64))ProcAddress)(1);
                }
                v22 = GetProcAddress(v19, "GetIServicingLoader");
                if ( v22 )
                {
                  v23 = ((__int64 (__fastcall *)(_QWORD *))v22)(a6);
                  if ( v23 >= 0 )
                  {
                    v23 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a6 + 24LL))(*a6);
                    if ( v23 >= 0 )
                    {
                      v25 = GetProcAddress(v19, a3);
                      *a5 = v25;
                      if ( v25 )
                      {
                        hModule = *a4;
                        *a4 = v19;
                        Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&hModule);
                        LastError = 0;
                        goto LABEL_34;
                      }
                      v20 = 148;
                      goto LABEL_19;
                    }
                    v24 = 145;
                  }
                  else
                  {
                    v24 = 143;
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v24,
                    (unsigned int)"onecore\\base\\cbs\\pbr\\loader\\pbr_loader.cpp",
                    (const char *)(unsigned int)v23,
                    v27);
                  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&hModule);
                  LastError = v23;
                  goto LABEL_34;
                }
                v20 = 141;
              }
              else
              {
                v20 = 130;
              }
LABEL_19:
              LastError = wil::details::in1diag3::Return_GetLastError(
                            retaddr,
                            (void *)v20,
                            (unsigned int)"onecore\\base\\cbs\\pbr\\loader\\pbr_loader.cpp",
                            v18);
              Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&hModule);
              goto LABEL_34;
            }
            v13 = 121;
          }
          else
          {
            v13 = 120;
          }
        }
        else
        {
          v13 = 119;
        }
      }
      else
      {
        v13 = 118;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\base\\cbs\\pbr\\loader\\pbr_loader.cpp",
        (const char *)(unsigned int)FilePath,
        v27);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x74,
                    (unsigned int)"onecore\\base\\cbs\\pbr\\loader\\pbr_loader.cpp",
                    (const char *)(unsigned int)v10,
                    v27);
    }
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v28);
    goto LABEL_34;
  }
  v29 = L"TurboStack.dll";
  *(_QWORD *)&v28 = 28;
  *((_QWORD *)&v28 + 1) = 28;
  v8 = Windows::StringUtil::Rtl::CombineAndNullTerminateWin32Paths<wchar_t const *,_LUNICODE_STRING>(
         &hModule,
         &v28,
         &v30);
  if ( v8 >= 0 )
    goto LABEL_17;
  LastError = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x6B,
                (unsigned int)"onecore\\base\\cbs\\pbr\\loader\\pbr_loader.cpp",
                (const char *)(unsigned int)v8,
                v27);
LABEL_34:
  Windows::AutoSsShim::~AutoSsShim((Windows::AutoSsShim *)&v35);
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v30);
  return LastError;
}

```

## disassembly

```asm
0x180042ef4  push    rbp
0x180042ef6  push    rbx
0x180042ef7  push    rsi
0x180042ef8  push    rdi
0x180042ef9  push    r12
0x180042efb  push    r14
0x180042efd  push    r15
0x180042eff  lea     rbp, [rsp-17h]
0x180042f04  sub     rsp, 0F0h
0x180042f0b  mov     rax, cs:__security_cookie
0x180042f12  xor     rax, rsp
0x180042f15  mov     [rbp+47h+var_40], rax
0x180042f19  mov     r12, [rbp+47h+arg_20]
0x180042f1d  xor     eax, eax
0x180042f1f  mov     r14, [rbp+47h+arg_28]
0x180042f23  xorps   xmm0, xmm0
0x180042f26  mov     [rbp+47h+var_A0], rcx
0x180042f2a  mov     rsi, r9
0x180042f2d  mov     [rbp+47h+hModule], rdx
0x180042f31  mov     r15, r8
0x180042f34  mov     [rsp+120h+var_C8], rax
0x180042f39  movdqa  [rbp+47h+var_90], xmm0
0x180042f3e  mov     [rbp+47h+var_80], rax
0x180042f42  mov     [rbp+47h+var_78], rax
0x180042f46  mov     [rbp+47h+var_70], rax
0x180042f4a  mov     [rbp+47h+var_68], rax
0x180042f4e  mov     [rbp+47h+var_60], rax
0x180042f52  mov     [rbp+47h+var_58], rax
0x180042f56  mov     [rbp+47h+var_50], al
0x180042f59  movups  [rsp+120h+var_D8], xmm0
0x180042f5e  test    rdx, rdx
0x180042f61  jz      short loc_180042FB8
0x180042f63  mov     eax, 1Ch
0x180042f68  lea     rdx, aTurbostackDll; "TurboStack.dll"
0x180042f6f  mov     [rsp+120h+var_E0], rdx
0x180042f74  lea     r8, [rsp+120h+var_D8]
0x180042f79  lea     rdx, [rsp+120h+var_F0]
0x180042f7e  mov     qword ptr [rsp+120h+var_F0], rax
0x180042f83  lea     rcx, [rbp+47h+hModule]
0x180042f87  mov     qword ptr [rsp+120h+var_F0+8], rax
0x180042f8c  call    ??$CombineAndNullTerminateWin32Paths@PEB_WU_LUNICODE_STRING@@@Rtl@StringUtil@Windows@@YAJAEBQEB_WAEBU_LUNICODE_STRING@@PEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::StringUtil::Rtl::CombineAndNullTerminateWin32Paths<wchar_t const *,_LUNICODE_STRING>(wchar_t const * const &,_LUNICODE_STRING const &,Windows::Auto<_LUNICODE_STRING> *)
0x180042f91  test    eax, eax
0x180042f93  jns     loc_1800430C6
0x180042f99  mov     rcx, [rbp+4Fh]; this
0x180042f9d  lea     r8, aOnecoreBaseCbs_12; "onecore\\base\\cbs\\pbr\\loader\\pbr_lo"...
0x180042fa4  mov     r9d, eax; char *
0x180042fa7  mov     edx, 6Bh ; 'k'; void *
0x180042fac  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180042fb1  mov     ebx, eax
0x180042fb3  jmp     loc_180043207
0x180042fb8  mov     [rsp+120h+var_E0], rax
0x180042fbd  lea     r8, [rsp+120h+var_F0]
0x180042fc2  mov     eax, 0Eh
0x180042fc7  lea     rdx, [rbp+47h+var_C0]
0x180042fcb  mov     [rbp+47h+var_C0], rax
0x180042fcf  lea     rcx, [rbp+47h+var_A0]
0x180042fd3  mov     [rbp+47h+var_B8], rax
0x180042fd7  lea     rax, aWindows; "Windows"
0x180042fde  mov     [rbp+47h+var_B0], rax
0x180042fe2  movups  [rsp+120h+var_F0], xmm0
0x180042fe7  call    ??$CombineAndNullTerminateWin32Paths@PEB_WU_LUNICODE_STRING@@@Rtl@StringUtil@Windows@@YAJAEBQEB_WAEBU_LUNICODE_STRING@@PEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::StringUtil::Rtl::CombineAndNullTerminateWin32Paths<wchar_t const *,_LUNICODE_STRING>(wchar_t const * const &,_LUNICODE_STRING const &,Windows::Auto<_LUNICODE_STRING> *)
0x180042fec  test    eax, eax
0x180042fee  jns     short loc_180043019
0x180042ff0  mov     rcx, [rbp+4Fh]; this
0x180042ff4  lea     r8, aOnecoreBaseCbs_12; "onecore\\base\\cbs\\pbr\\loader\\pbr_lo"...
0x180042ffb  mov     r9d, eax; char *
0x180042ffe  mov     edx, 74h ; 't'; void *
0x180043003  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180043008  mov     ebx, eax
0x18004300a  lea     rcx, [rsp+120h+var_F0]
0x18004300f  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180043014  jmp     loc_180043207
0x180043019  lea     rcx, [rsp+120h+var_F0]
0x18004301e  call    ??$c_str@V?$Auto@U_LUNICODE_STRING@@@Windows@@@StringUtil@Windows@@YA?A_PAEBV?$Auto@U_LUNICODE_STRING@@@1@@Z
0x180043023  mov     rdx, rax; wchar_t *
0x180043026  lea     rcx, [rbp+47h+var_90]; this
0x18004302a  xor     r8d, r8d; wchar_t *
0x18004302d  call    ?TryLoadFromWindowsPath@AutoSsShim@Windows@@QEAAJQEB_W0@Z; Windows::AutoSsShim::TryLoadFromWindowsPath(wchar_t const * const,wchar_t const * const)
0x180043032  mov     ebx, eax
0x180043034  test    eax, eax
0x180043036  jns     short loc_180043052
0x180043038  mov     edx, 76h ; 'v'; void *
0x18004303d  mov     rcx, [rbp+4Fh]; this
0x180043041  lea     r8, aOnecoreBaseCbs_12; "onecore\\base\\cbs\\pbr\\loader\\pbr_lo"...
0x180043048  mov     r9d, eax; char *
0x18004304b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043050  jmp     short loc_18004300A
0x180043052  lea     rcx, [rsp+120h+var_F0]
0x180043057  call    ??$c_str@V?$Auto@U_LUNICODE_STRING@@@Windows@@@StringUtil@Windows@@YA?A_PAEBV?$Auto@U_LUNICODE_STRING@@@1@@Z
0x18004305c  mov     rdx, rax; wchar_t *
0x18004305f  mov     qword ptr [rsp+120h+var_100], 0; int
0x180043068  xor     r9d, r9d; wchar_t *
0x18004306b  lea     rcx, [rbp+47h+var_90]; this
0x18004306f  xor     r8d, r8d; bool
0x180043072  call    ?Bind@AutoSsShim@Windows@@QEAAJQEB_W_N0PEB_K@Z; Windows::AutoSsShim::Bind(wchar_t const * const,bool,wchar_t const * const,unsigned __int64 const *)
0x180043077  mov     ebx, eax
0x180043079  test    eax, eax
0x18004307b  jns     short loc_180043084
0x18004307d  mov     edx, 77h ; 'w'
0x180043082  jmp     short loc_18004303D
0x180043084  lea     rcx, [rbp+47h+var_90]; this
0x180043088  call    ?Preload@AutoSsShim@Windows@@QEAAJ_N@Z; Windows::AutoSsShim::Preload(bool)
0x18004308d  mov     ebx, eax
0x18004308f  test    eax, eax
0x180043091  jns     short loc_18004309A
0x180043093  mov     edx, 78h ; 'x'
0x180043098  jmp     short loc_18004303D
0x18004309a  lea     r8, [rsp+120h+var_D8]; struct _LUNICODE_STRING *
0x18004309f  lea     rdx, aTurbostackDll; "TurboStack.dll"
0x1800430a6  lea     rcx, [rbp+47h+var_90]; this
0x1800430aa  call    ?GetFilePath@AutoSsShim@Windows@@QEAAJQEB_WPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::AutoSsShim::GetFilePath(wchar_t const * const,Windows::Auto<_LUNICODE_STRING> *)
0x1800430af  mov     ebx, eax
0x1800430b1  test    eax, eax
0x1800430b3  jns     short loc_1800430BC
0x1800430b5  mov     edx, 79h ; 'y'
0x1800430ba  jmp     short loc_18004303D
0x1800430bc  lea     rcx, [rsp+120h+var_F0]
0x1800430c1  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1800430c6  lea     rcx, [rsp+120h+var_D8]
0x1800430cb  mov     [rbp+47h+hModule], 0
0x1800430d3  call    ??$c_str@V?$Auto@U_LUNICODE_STRING@@@Windows@@@StringUtil@Windows@@YA?A_PAEBV?$Auto@U_LUNICODE_STRING@@@1@@Z
0x1800430d8  xor     edx, edx; hFile
0x1800430da  mov     rcx, rax; lpLibFileName
0x1800430dd  lea     r8d, [rdx+8]; dwFlags
0x1800430e1  call    cs:__imp_LoadLibraryExW
0x1800430e8  nop     dword ptr [rax+rax+00h]
0x1800430ed  mov     rdx, rax
0x1800430f0  lea     rcx, [rbp+47h+hModule]
0x1800430f4  call    ?TakeOwnership@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXPEA_W@Z; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(wchar_t *)
0x1800430f9  mov     rbx, [rbp+47h+hModule]
0x1800430fd  test    rbx, rbx
0x180043100  jnz     short loc_180043127
0x180043102  mov     edx, 82h; void *
0x180043107  mov     rcx, [rbp+4Fh]; this
0x18004310b  lea     r8, aOnecoreBaseCbs_12; "onecore\\base\\cbs\\pbr\\loader\\pbr_lo"...
0x180043112  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180043117  lea     rcx, [rbp+47h+hModule]
0x18004311b  mov     ebx, eax
0x18004311d  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x180043122  jmp     loc_180043207
0x180043127  cmp     cs:?g_TestMode@@3_NA, 0; bool g_TestMode
0x18004312e  jz      short loc_18004315C
0x180043130  lea     rdx, aSettestmode; "SetTestMode"
0x180043137  mov     rcx, rbx; hModule
0x18004313a  call    cs:__imp_GetProcAddress
0x180043141  nop     dword ptr [rax+rax+00h]
0x180043146  test    rax, rax
0x180043149  jnz     short loc_180043152
0x18004314b  mov     edx, 87h
0x180043150  jmp     short loc_180043107
0x180043152  mov     ecx, 1
0x180043157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004315c  lea     rdx, aGetiservicingl; "GetIServicingLoader"
0x180043163  mov     rcx, rbx; hModule
0x180043166  call    cs:__imp_GetProcAddress
0x18004316d  nop     dword ptr [rax+rax+00h]
0x180043172  test    rax, rax
0x180043175  jnz     short loc_18004317E
0x180043177  mov     edx, 8Dh
0x18004317c  jmp     short loc_180043107
0x18004317e  mov     rcx, r14
0x180043181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043186  mov     edi, eax
0x180043188  test    eax, eax
0x18004318a  jns     short loc_1800431B1
0x18004318c  mov     edx, 8Fh; void *
0x180043191  mov     rcx, [rbp+4Fh]; this
0x180043195  lea     r8, aOnecoreBaseCbs_12; "onecore\\base\\cbs\\pbr\\loader\\pbr_lo"...
0x18004319c  mov     r9d, edi; char *
0x18004319f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800431a4  lea     rcx, [rbp+47h+hModule]
0x1800431a8  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x1800431ad  mov     ebx, edi
0x1800431af  jmp     short loc_180043207
0x1800431b1  mov     rcx, [r14]
0x1800431b4  mov     rax, [rcx]
0x1800431b7  mov     rax, [rax+18h]
0x1800431bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800431c0  mov     edi, eax
0x1800431c2  test    eax, eax
0x1800431c4  jns     short loc_1800431CD
0x1800431c6  mov     edx, 91h
0x1800431cb  jmp     short loc_180043191
0x1800431cd  mov     rdx, r15; lpProcName
0x1800431d0  mov     rcx, rbx; hModule
0x1800431d3  call    cs:__imp_GetProcAddress
0x1800431da  nop     dword ptr [rax+rax+00h]
0x1800431df  mov     [r12], rax
0x1800431e3  test    rax, rax
0x1800431e6  jnz     short loc_1800431F2
0x1800431e8  mov     edx, 94h
0x1800431ed  jmp     loc_180043107
0x1800431f2  mov     rax, [rsi]
0x1800431f5  lea     rcx, [rbp+47h+hModule]
0x1800431f9  mov     [rbp+47h+hModule], rax
0x1800431fd  mov     [rsi], rbx
0x180043200  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x180043205  xor     ebx, ebx
0x180043207  lea     rcx, [rbp+47h+var_90]; this
0x18004320b  call    ??1AutoSsShim@Windows@@QEAA@XZ; Windows::AutoSsShim::~AutoSsShim(void)
0x180043210  lea     rcx, [rsp+120h+var_D8]
0x180043215  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18004321a  mov     eax, ebx
0x18004321c  mov     rcx, [rbp+47h+var_40]
0x180043220  xor     rcx, rsp; StackCookie
0x180043223  call    __security_check_cookie
0x180043228  add     rsp, 0F0h
0x18004322f  pop     r15
0x180043231  pop     r14
0x180043233  pop     r12
0x180043235  pop     rdi
0x180043236  pop     rsi
0x180043237  pop     rbx
0x180043238  pop     rbp
0x180043239  retn
```
