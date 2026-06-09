# ThemeAppModelWrapper::CreateThemeAppxMapping(Microsoft::WRL::ComPtr<ITheme>,Windows::Internal::StateRepository::IAppExtension *)

- ea: `0x18026a1e8`
- end: `0x18026a450`
- name: `?CreateThemeAppxMapping@ThemeAppModelWrapper@@CAJV?$ComPtr@UITheme@@@WRL@Microsoft@@PEAUIAppExtension@StateRepository@Internal@Windows@@@Z`
- size: `616`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18026ba2c`

## callees

- `0x180011bb0`
- `0x180019a20`
- `0x18002e1f4`
- `0x180041004`
- `0x180078f3c`
- `0x180228318`
- `0x18026a1e8`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18026a3b7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18026a3f0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18026a3b7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18026a3f0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18026a325`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18026a325`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026a245`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026a287`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026a425`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026a245`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026a287`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026a425`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18026a36e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18026a36e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ThemeAppModelWrapper::CreateThemeAppxMapping(__int64 **a1, __int64 a2)
{
  __int64 v4; // rdx
  unsigned int v5; // ebx
  __int64 (__fastcall *v6)(__int64, HSTRING *); // rbx
  int v7; // eax
  __int64 *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  unsigned int v11; // ebx
  const char *v12; // r9
  __int64 v13; // rdx
  const WCHAR *StringRawBuffer; // rax
  const BYTE *v15; // rsi
  BYTE *v16; // r14
  __int64 v17; // rbx
  __int64 v18; // rcx
  DWORD v19; // ecx
  unsigned int v20; // eax
  unsigned int v21; // eax
  int dwOptions; // [rsp+20h] [rbp-58h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-58h]
  HKEY *p_hKey; // [rsp+50h] [rbp-28h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-20h] BYREF
  char v27; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]
  HSTRING string; // [rsp+B8h] [rbp+40h] BYREF
  BYTE *lpData; // [rsp+C0h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+C8h] [rbp+50h] BYREF

  if ( a2 )
  {
    if ( !*a1 )
    {
      v4 = 662;
      goto LABEL_5;
    }
    string = 0;
    v6 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 104LL);
    WindowsDeleteString(0);
    string = 0;
    v7 = v6(a2, &string);
    v5 = v7;
    if ( v7 >= 0 )
    {
      lpData = 0;
      v8 = *a1;
      v9 = **a1;
      lpData = 0;
      v10 = (*(__int64 (__fastcall **)(__int64 *, BYTE **))(v9 + 24))(v8, &lpData);
      v5 = v10;
      if ( v10 >= 0 )
      {
        hKey = 0;
        p_hKey = &hKey;
        phkResult = 0;
        v27 = 1;
        v11 = RegCreateKeyExW(
                HKEY_CURRENT_USER,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes\\Personalize\\ThemeAppxMapping",
                0,
                0,
                0,
                0xF003Fu,
                0,
                &phkResult,
                0);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
        if ( v11 )
        {
          v12 = (const char *)v11;
          v13 = 671;
        }
        else
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v15 = (const BYTE *)StringRawBuffer;
          v16 = lpData;
          v17 = -1;
          v18 = -1;
          do
            ++v18;
          while ( *(_WORD *)&lpData[2 * v18] );
          v19 = 2 * v18;
          do
            ++v17;
          while ( StringRawBuffer[v17] );
          v20 = RegSetValueExW(hKey, StringRawBuffer, 0, 1u, lpData, v19);
          if ( v20 )
          {
            v12 = (const char *)v20;
            v13 = 679;
          }
          else
          {
            v21 = RegSetValueExW(hKey, (LPCWSTR)v16, 0, 1u, v15, 2 * v17);
            if ( !v21 )
            {
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpData);
              WindowsDeleteString(string);
              v5 = 0;
              goto LABEL_24;
            }
            v12 = (const char *)v21;
            v13 = 680;
          }
        }
        v5 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v13,
               (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
               v12,
               dwOptionsa);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x29C,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
          (const char *)(unsigned int)v10,
          dwOptions);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpData);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x299,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
        (const char *)(unsigned int)v7,
        dwOptions);
    }
    WindowsDeleteString(string);
LABEL_24:
    string = 0;
    goto LABEL_25;
  }
  v4 = 661;
LABEL_5:
  v5 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
    (const char *)0x80070057LL,
    dwOptions);
LABEL_25:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1);
  return v5;
}

```

## disassembly

```asm
0x18026a1e8  mov     [rsp-30h+arg_0], rcx
0x18026a1ed  push    rbp
0x18026a1ee  push    rbx
0x18026a1ef  push    rsi
0x18026a1f0  push    rdi
0x18026a1f1  push    r14
0x18026a1f3  push    r15
0x18026a1f5  mov     rbp, rsp
0x18026a1f8  sub     rsp, 78h
0x18026a1fc  mov     rsi, rdx
0x18026a1ff  mov     rdi, rcx
0x18026a202  xor     r15d, r15d
0x18026a205  test    rdx, rdx
0x18026a208  jnz     short loc_18026A211
0x18026a20a  mov     edx, 295h
0x18026a20f  jmp     short loc_18026A21B
0x18026a211  cmp     [rcx], r15
0x18026a214  jnz     short loc_18026A238
0x18026a216  mov     edx, 296h; void *
0x18026a21b  mov     ebx, 80070057h
0x18026a220  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026a227  mov     r9d, ebx; char *
0x18026a22a  mov     rcx, [rbp+30h]; this
0x18026a22e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026a233  jmp     loc_18026A438
0x18026a238  mov     [rbp+string], r15
0x18026a23c  mov     rax, [rdx]
0x18026a23f  mov     rbx, [rax+68h]
0x18026a243  xor     ecx, ecx; string
0x18026a245  call    cs:__imp_WindowsDeleteString
0x18026a24c  nop     dword ptr [rax+rax+00h]
0x18026a251  mov     [rbp+string], r15
0x18026a255  lea     rdx, [rbp+string]
0x18026a259  mov     rcx, rsi
0x18026a25c  mov     rax, rbx
0x18026a25f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026a264  mov     ebx, eax
0x18026a266  test    eax, eax
0x18026a268  jns     short loc_18026A298
0x18026a26a  mov     rcx, [rbp+30h]; this
0x18026a26e  mov     r9d, eax; char *
0x18026a271  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026a278  mov     edx, 299h; void *
0x18026a27d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026a282  nop
0x18026a283  mov     rcx, [rbp+string]; string
0x18026a287  call    cs:__imp_WindowsDeleteString
0x18026a28e  nop     dword ptr [rax+rax+00h]
0x18026a293  jmp     loc_18026A434
0x18026a298  mov     [rbp+lpData], r15
0x18026a29c  mov     rcx, [rdi]
0x18026a29f  mov     rax, [rcx]
0x18026a2a2  mov     [rbp+lpData], r15
0x18026a2a6  lea     rdx, [rbp+lpData]
0x18026a2aa  mov     rax, [rax+18h]
0x18026a2ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026a2b3  mov     ebx, eax
0x18026a2b5  test    eax, eax
0x18026a2b7  jns     short loc_18026A2DD
0x18026a2b9  mov     rcx, [rbp+30h]; this
0x18026a2bd  mov     r9d, eax; char *
0x18026a2c0  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026a2c7  mov     edx, 29Ch; void *
0x18026a2cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026a2d1  nop
0x18026a2d2  lea     rcx, [rbp+lpData]
0x18026a2d6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18026a2db  jmp     short loc_18026A283
0x18026a2dd  mov     [rbp+hKey], r15
0x18026a2e1  lea     rax, [rbp+hKey]
0x18026a2e5  mov     [rbp+var_28], rax
0x18026a2e9  mov     [rbp+var_20], r15
0x18026a2ed  mov     [rbp+var_18], 1
0x18026a2f1  mov     [rsp+78h+lpdwDisposition], r15; lpdwDisposition
0x18026a2f6  lea     rax, [rbp+var_20]
0x18026a2fa  mov     [rsp+78h+phkResult], rax; phkResult
0x18026a2ff  mov     [rsp+78h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18026a304  mov     [rsp+78h+samDesired], 0F003Fh; samDesired
0x18026a30c  mov     [rsp+78h+dwOptions], r15d; unsigned int
0x18026a311  xor     r9d, r9d; lpClass
0x18026a314  xor     r8d, r8d; Reserved
0x18026a317  lea     rdx, aSoftwareMicros_71; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18026a31e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18026a325  call    cs:__imp_RegCreateKeyExW
0x18026a32c  nop     dword ptr [rax+rax+00h]
0x18026a331  mov     ebx, eax
0x18026a333  lea     rcx, [rbp+var_28]
0x18026a337  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18026a33c  test    ebx, ebx
0x18026a33e  jz      short loc_18026A368
0x18026a340  mov     r9d, ebx; char *
0x18026a343  mov     edx, 29Fh; void *
0x18026a348  mov     rcx, [rbp+30h]; this
0x18026a34c  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026a353  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18026a358  mov     ebx, eax
0x18026a35a  lea     rcx, [rbp+hKey]
0x18026a35e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18026a363  jmp     loc_18026A2D2
0x18026a368  xor     edx, edx; length
0x18026a36a  mov     rcx, [rbp+string]; string
0x18026a36e  call    cs:__imp_WindowsGetStringRawBuffer
0x18026a375  nop     dword ptr [rax+rax+00h]
0x18026a37a  mov     rsi, rax
0x18026a37d  mov     r14, [rbp+lpData]
0x18026a381  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18026a385  mov     rcx, rbx
0x18026a388  inc     rcx
0x18026a38b  cmp     [r14+rcx*2], r15w
0x18026a390  jnz     short loc_18026A388
0x18026a392  add     ecx, ecx
0x18026a394  inc     rbx
0x18026a397  cmp     [rax+rbx*2], r15w
0x18026a39c  jnz     short loc_18026A394
0x18026a39e  mov     [rsp+78h+samDesired], ecx; cbData
0x18026a3a2  mov     qword ptr [rsp+78h+dwOptions], r14; lpData
0x18026a3a7  mov     r9d, 1; dwType
0x18026a3ad  xor     r8d, r8d; Reserved
0x18026a3b0  mov     rdx, rsi; lpValueName
0x18026a3b3  mov     rcx, [rbp+hKey]; hKey
0x18026a3b7  call    cs:__imp_RegSetValueExW
0x18026a3be  nop     dword ptr [rax+rax+00h]
0x18026a3c3  test    eax, eax
0x18026a3c5  jz      short loc_18026A3D4
0x18026a3c7  mov     r9d, eax
0x18026a3ca  mov     edx, 2A7h
0x18026a3cf  jmp     loc_18026A348
0x18026a3d4  lea     eax, [rbx+rbx]
0x18026a3d7  mov     [rsp+78h+samDesired], eax; cbData
0x18026a3db  mov     qword ptr [rsp+78h+dwOptions], rsi; lpData
0x18026a3e0  mov     r9d, 1; dwType
0x18026a3e6  xor     r8d, r8d; Reserved
0x18026a3e9  mov     rdx, r14; lpValueName
0x18026a3ec  mov     rcx, [rbp+hKey]; hKey
0x18026a3f0  call    cs:__imp_RegSetValueExW
0x18026a3f7  nop     dword ptr [rax+rax+00h]
0x18026a3fc  test    eax, eax
0x18026a3fe  jz      short loc_18026A40D
0x18026a400  mov     r9d, eax
0x18026a403  mov     edx, 2A8h
0x18026a408  jmp     loc_18026A348
0x18026a40d  lea     rcx, [rbp+hKey]
0x18026a411  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18026a416  nop
0x18026a417  lea     rcx, [rbp+lpData]
0x18026a41b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18026a420  nop
0x18026a421  mov     rcx, [rbp+string]; string
0x18026a425  call    cs:__imp_WindowsDeleteString
0x18026a42c  nop     dword ptr [rax+rax+00h]
0x18026a431  mov     ebx, r15d
0x18026a434  mov     [rbp+string], r15
0x18026a438  mov     rcx, rdi
0x18026a43b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026a440  mov     eax, ebx
0x18026a442  add     rsp, 78h
0x18026a446  pop     r15
0x18026a448  pop     r14
0x18026a44a  pop     rdi
0x18026a44b  pop     rsi
0x18026a44c  pop     rbx
0x18026a44d  pop     rbp
0x18026a44e  retn
```
