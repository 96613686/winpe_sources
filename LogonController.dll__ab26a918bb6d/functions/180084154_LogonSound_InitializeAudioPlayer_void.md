# LogonSound::_InitializeAudioPlayer(void)

- ea: `0x180084154`
- end: `0x1800842ac`
- name: `?_InitializeAudioPlayer@LogonSound@@AEAAJXZ`
- size: `344`
- prototype: `__int64 __fastcall(LogonSound *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800842b4`

## callees

- `0x18000df10`
- `0x1800440d0`
- `0x18004879c`
- `0x18004ae38`
- `0x18005d488`
- `0x180062a24`
- `0x18006532c`
- `0x180084154`
- `0x18009d010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18008417c`
- `KERNEL32!LoadLibraryExW` at `0x18008417c`
- `KERNEL32!FreeLibrary` at `0x180084243`
- `KERNEL32!FreeLibrary` at `0x180084299`
- `KERNEL32!FreeLibrary` at `0x180084243`
- `KERNEL32!FreeLibrary` at `0x180084299`

## string_xrefs

- `0x180084175`: `audioses.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall LogonSound::_InitializeAudioPlayer(LogonSound *this)
{
  HMODULE Library; // rax
  HMODULE v3; // rbx
  __int64 v4; // rdx
  int v5; // eax
  unsigned int v6; // edi
  __int64 v7; // rsi
  __int64 (__fastcall *v8)(__int64, GUID *, __int64 *, _QWORD); // rdi
  int v9; // eax
  int v11; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  __int64 v13; // [rsp+68h] [rbp+38h] BYREF
  __int64 v14; // [rsp+70h] [rbp+40h] BYREF
  HMODULE hLibModule; // [rsp+78h] [rbp+48h] BYREF

  hLibModule = 0;
  Library = LoadLibraryExW(L"audioses.dll", 0, 0x800u);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
    &hLibModule,
    Library);
  v3 = hLibModule;
  if ( hLibModule )
  {
    v13 = 0;
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v13);
    v5 = CreateAudioPlayerFacade(v3, v4, &v13);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF0,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\logonsound.cpp",
        (const char *)(unsigned int)v5,
        v11);
LABEL_6:
      Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v13);
      FreeLibrary(v3);
      return v6;
    }
    v14 = 0;
    v7 = v13;
    v8 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *, _QWORD))(*(_QWORD *)v13 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v14);
    v9 = v8(v7, &GUID_81ef556b_a13d_4f0c_b88e_5eded83750f7, &v14, 0);
    v6 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF3,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\logonsound.cpp",
        (const char *)(unsigned int)v9,
        v11);
      Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v14);
      goto LABEL_6;
    }
    *((_BYTE *)this + 120) = 1;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<HSTRING__ *>>::operator=((char *)this + 80, &v13);
    Microsoft::WRL::ComPtr<IAudioPlayer>::operator=((char *)this + 88, &v14);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::swap(
      (char *)this + 112,
      &hLibModule);
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v14);
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v13);
    v3 = hLibModule;
  }
  if ( v3 )
    FreeLibrary(v3);
  return 0;
}

```

## disassembly

```asm
0x180084154  push    rbp
0x180084156  push    rbx
0x180084157  push    rsi
0x180084158  push    rdi
0x180084159  push    r14
0x18008415b  mov     rbp, rsp
0x18008415e  sub     rsp, 30h
0x180084162  mov     r14, rcx
0x180084165  mov     [rbp+hLibModule], 0
0x18008416d  xor     edx, edx; hFile
0x18008416f  mov     r8d, 800h; dwFlags
0x180084175  lea     rcx, aAudiosesDll; "audioses.dll"
0x18008417c  call    cs:__imp_LoadLibraryExW
0x180084182  mov     rdx, rax
0x180084185  lea     rcx, [rbp+hLibModule]
0x180084189  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18008418e  mov     rbx, [rbp+hLibModule]
0x180084192  test    rbx, rbx
0x180084195  jz      loc_180084291
0x18008419b  mov     [rbp+arg_8], 0
0x1800841a3  lea     rcx, [rbp+arg_8]
0x1800841a7  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x1800841ac  lea     r8, [rbp+arg_8]
0x1800841b0  mov     rcx, rbx
0x1800841b3  call    CreateAudioPlayerFacade
0x1800841b8  mov     edi, eax
0x1800841ba  test    eax, eax
0x1800841bc  jns     short loc_1800841D8
0x1800841be  mov     rcx, [rbp+28h]; this
0x1800841c2  mov     r9d, eax; char *
0x1800841c5  lea     r8, aPcshellShellAu; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800841cc  mov     edx, 0F0h; void *
0x1800841d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800841d6  jmp     short loc_180084236
0x1800841d8  mov     [rbp+arg_10], 0
0x1800841e0  mov     rsi, [rbp+arg_8]
0x1800841e4  mov     rax, [rsi]
0x1800841e7  mov     rdi, [rax+18h]
0x1800841eb  lea     rcx, [rbp+arg_10]
0x1800841ef  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x1800841f4  xor     r9d, r9d
0x1800841f7  lea     r8, [rbp+arg_10]
0x1800841fb  lea     rdx, _GUID_81ef556b_a13d_4f0c_b88e_5eded83750f7
0x180084202  mov     rcx, rsi
0x180084205  mov     rax, rdi
0x180084208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008420d  mov     edi, eax
0x18008420f  test    eax, eax
0x180084211  jns     short loc_18008424D
0x180084213  mov     rcx, [rbp+28h]; this
0x180084217  mov     r9d, eax; char *
0x18008421a  lea     r8, aPcshellShellAu; "pcshell\\shell\\auth\\authux\\controlle"...
0x180084221  mov     edx, 0F3h; void *
0x180084226  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008422b  nop
0x18008422c  lea     rcx, [rbp+arg_10]
0x180084230  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180084235  nop
0x180084236  lea     rcx, [rbp+arg_8]
0x18008423a  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18008423f  nop
0x180084240  mov     rcx, rbx; hLibModule
0x180084243  call    cs:__imp_FreeLibrary
0x180084249  mov     eax, edi
0x18008424b  jmp     short loc_1800842A1
0x18008424d  mov     byte ptr [r14+78h], 1
0x180084252  lea     rcx, [r14+50h]
0x180084256  lea     rdx, [rbp+arg_8]
0x18008425a  call    ??4?$ComPtr@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<HSTRING__ *>>::operator=(Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<HSTRING__ *>> const &)
0x18008425f  lea     rcx, [r14+58h]
0x180084263  lea     rdx, [rbp+arg_10]
0x180084267  call    ??4?$ComPtr@UIAudioPlayer@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IAudioPlayer>::operator=(Microsoft::WRL::ComPtr<IAudioPlayer> const &)
0x18008426c  lea     rcx, [r14+70h]
0x180084270  lea     rdx, [rbp+hLibModule]
0x180084274  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &)
0x180084279  nop
0x18008427a  lea     rcx, [rbp+arg_10]
0x18008427e  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180084283  nop
0x180084284  lea     rcx, [rbp+arg_8]
0x180084288  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18008428d  mov     rbx, [rbp+hLibModule]
0x180084291  test    rbx, rbx
0x180084294  jz      short loc_18008429F
0x180084296  mov     rcx, rbx; hLibModule
0x180084299  call    cs:__imp_FreeLibrary
0x18008429f  xor     eax, eax
0x1800842a1  add     rsp, 30h
0x1800842a5  pop     r14
0x1800842a7  pop     rdi
0x1800842a8  pop     rsi
0x1800842a9  pop     rbx
0x1800842aa  pop     rbp
0x1800842ab  retn
```
