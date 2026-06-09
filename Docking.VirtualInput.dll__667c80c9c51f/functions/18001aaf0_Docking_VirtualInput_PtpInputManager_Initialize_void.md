# Docking::VirtualInput::PtpInputManager::_Initialize(void)

- ea: `0x18001aaf0`
- end: `0x18001abed`
- name: `?_Initialize@PtpInputManager@VirtualInput@Docking@@MEAAJXZ`
- size: `253`
- prototype: `__int64 __fastcall(Docking::VirtualInput::PtpInputManager *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x180004bac`
- `0x180006784`
- `0x180014528`
- `0x18001a07c`
- `0x18001aaf0`
- `0x18001af34`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001abd7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001abd7`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001ab8e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001ab8e`
- `ext-ms-win-ntuser-rim-l1-1-0!InitializeInputDeviceInjection` at `0x18001ab32`
- `ext-ms-win-ntuser-rim-l1-1-0!InitializeInputDeviceInjection` at `0x18001ab32`

## string_xrefs

- `0x18001ab87`: `ShellChromeApi.dll`

## pseudocode

```c
__int64 __fastcall Docking::VirtualInput::PtpInputManager::_Initialize(
        Docking::VirtualInput::PtpInputManager *this,
        __int64 a2)
{
  __int64 v2; // rcx
  const char *v3; // r9
  HMODULE LibraryW; // rax
  HMODULE v6; // rax
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  Docking::VirtualInput::PtpInputManager *v8; // [rsp+60h] [rbp+8h]

  v8 = this;
  LOWORD(a2) = 5;
  LOWORD(this) = 13;
  LOBYTE(v2) = (unsigned int)InitializeInputDeviceInjection(
                               this,
                               a2,
                               &Docking::VirtualInput::g_PtpUsages,
                               11,
                               *((_QWORD *)v8 + 11),
                               1,
                               (char *)v8 + 96) == 0;
  if ( (unsigned __int8)wil::verify_bool<bool,0>(v2) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x8F,
             (unsigned int)"onecoreuap\\shell\\docking\\virtualinput\\lib\\ptpinputmanager.cpp",
             v3);
  LibraryW = LoadLibraryW(L"ShellChromeApi.dll");
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
    (char *)v8 + 104,
    LibraryW);
  if ( (unsigned __int8)wil::operator!=<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>(
                          (char *)v8 + 104,
                          0) )
  {
    v6 = (HMODULE)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::get((char *)v8 + 104);
    *((_QWORD *)v8 + 14) = GetProcAddress(v6, "Shell_TurnOnDockScreens");
  }
  return 0;
}

```

## disassembly

```asm
0x18001aaf0  mov     [rsp+arg_0], rcx
0x18001aaf5  sub     rsp, 58h
0x18001aaf9  mov     rax, [rsp+58h+arg_0]
0x18001aafe  add     rax, 60h ; '`'
0x18001ab02  mov     [rsp+58h+var_28], rax
0x18001ab07  mov     [rsp+58h+var_30], 1
0x18001ab0f  mov     rax, [rsp+58h+arg_0]
0x18001ab14  mov     rax, [rax+58h]
0x18001ab18  mov     [rsp+58h+var_38], rax
0x18001ab1d  mov     r9d, 0Bh
0x18001ab23  lea     r8, ?g_PtpUsages@VirtualInput@Docking@@3PAUtagUSAGE_PROPERTIES@@A; tagUSAGE_PROPERTIES near * Docking::VirtualInput::g_PtpUsages
0x18001ab2a  mov     dx, 5
0x18001ab2e  mov     cx, 0Dh
0x18001ab32  call    cs:__imp_InitializeInputDeviceInjection
0x18001ab38  test    eax, eax
0x18001ab3a  jnz     short loc_18001AB43
0x18001ab3c  mov     [rsp+58h+var_18], 1
0x18001ab41  jmp     short loc_18001AB48
0x18001ab43  mov     [rsp+58h+var_18], 0
0x18001ab48  mov     cl, [rsp+58h+var_18]
0x18001ab4c  call    ??$verify_bool@_N$0A@@wil@@YA_N_N@Z; wil::verify_bool<bool,0>(bool)
0x18001ab51  movzx   eax, al
0x18001ab54  test    eax, eax
0x18001ab56  jz      short loc_18001AB73
0x18001ab58  mov     rax, [rsp+58h]
0x18001ab5d  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\docking\\virtualinpu"...
0x18001ab64  mov     edx, 8Fh; void *
0x18001ab69  mov     rcx, rax; this
0x18001ab6c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ab71  jmp     short loc_18001ABE8
0x18001ab73  xor     eax, eax
0x18001ab75  test    eax, eax
0x18001ab77  jnz     short loc_18001AAF9
0x18001ab79  mov     rax, [rsp+58h+arg_0]
0x18001ab7e  add     rax, 68h ; 'h'
0x18001ab82  mov     [rsp+58h+var_10], rax
0x18001ab87  lea     rcx, LibFileName; "ShellChromeApi.dll"
0x18001ab8e  call    cs:__imp_LoadLibraryW
0x18001ab94  mov     rdx, rax
0x18001ab97  mov     rcx, [rsp+58h+var_10]
0x18001ab9c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18001aba1  nop
0x18001aba2  mov     rax, [rsp+58h+arg_0]
0x18001aba7  add     rax, 68h ; 'h'
0x18001abab  xor     edx, edx
0x18001abad  mov     rcx, rax
0x18001abb0  call    ??$?9V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@$$T@Z; wil::operator!=<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> const &,std::nullptr_t)
0x18001abb5  movzx   eax, al
0x18001abb8  test    eax, eax
0x18001abba  jz      short loc_18001ABE6
0x18001abbc  mov     rax, [rsp+58h+arg_0]
0x18001abc1  add     rax, 68h ; 'h'
0x18001abc5  mov     rcx, rax
0x18001abc8  call    ?get@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEBAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::get(void)
0x18001abcd  lea     rdx, aShellTurnondoc; "Shell_TurnOnDockScreens"
0x18001abd4  mov     rcx, rax; hModule
0x18001abd7  call    cs:__imp_GetProcAddress
0x18001abdd  mov     rcx, [rsp+58h+arg_0]
0x18001abe2  mov     [rcx+70h], rax
0x18001abe6  xor     eax, eax
0x18001abe8  add     rsp, 58h
0x18001abec  retn
```
