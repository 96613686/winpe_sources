# SystemSettings::Personalization::TouchKeyboardSingleton::GetCHSIMEBackgroundImagePathWithBrightness(SystemSettings::Personalization::TouchKeyboardThemeItemModel const &)

- ea: `0x1801a45ec`
- end: `0x1801a496d`
- name: `?GetCHSIMEBackgroundImagePathWithBrightness@TouchKeyboardSingleton@Personalization@SystemSettings@@QEAAPEAUHSTRING__@@AEBVTouchKeyboardThemeItemModel@23@@Z`
- size: `897`
- prototype: `HSTRING __fastcall(SystemSettings::Personalization::TouchKeyboardSingleton *__hidden this, const struct SystemSettings::Personalization::TouchKeyboardThemeItemModel *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18017cbb0`

## callees

- `0x18000c840`
- `0x18000d44c`
- `0x18001ecfc`
- `0x1800234f8`
- `0x18002373c`
- `0x180024428`
- `0x180024ad4`
- `0x180024b2c`
- `0x180024b60`
- `0x18002f220`
- `0x180045080`
- `0x1801a0da4`
- `0x1801a16c4`
- `0x1801a45ec`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1801a46ad`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1801a47cc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1801a48b3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1801a46ad`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1801a47cc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1801a48b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801a46eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801a4804`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801a48e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801a46eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801a4804`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801a48e7`

## string_xrefs

- `0x1801a4644`: `ChineseSimplifiedImeBackgroundImagePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
HSTRING __fastcall SystemSettings::Personalization::TouchKeyboardSingleton::GetCHSIMEBackgroundImagePathWithBrightness(
        SystemSettings::Personalization::TouchKeyboardSingleton *this,
        const struct SystemSettings::Personalization::TouchKeyboardThemeItemModel *a2)
{
  __int64 v3; // rbx
  __int64 RegistryKeyStringValue; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rax
  SystemSettings::Personalization *v9; // rcx
  const char *v10; // r9
  unsigned int CurrentCHSIMEBackgroundBrightnessUnvalidated; // edi
  HSTRING v12; // rbx
  __int64 v13; // r14
  _WORD *v14; // r9
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rax
  const char *v20; // r9
  __int64 v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rax
  const char *v29; // r9
  HSTRING string; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING v32; // [rsp+28h] [rbp-D8h] BYREF
  HSTRING v33; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v34[16]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h]
  _BYTE v36[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v37[32]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v38[32]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v39[74]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v40[14]; // [rsp+102h] [rbp+2h] BYREF
  WCHAR sourceString[264]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR v42[264]; // [rsp+320h] [rbp+220h] BYREF
  WCHAR v43[264]; // [rsp+530h] [rbp+430h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+768h] [rbp+668h]

  std::wstring::wstring(v34, &LocaleName);
  v3 = -1;
  if ( *((_BYTE *)a2 + 137) )
  {
    RegistryKeyStringValue = SystemSettings::Personalization::GetRegistryKeyStringValue(
                               v36,
                               L"Software\\Microsoft\\TabletTip\\1.7\\UserCustomTheme",
                               L"ChineseSimplifiedImeBackgroundImagePath");
    std::wstring::operator=(v34, RegistryKeyStringValue);
    std::wstring::_Tidy_deallocate(v36);
    if ( v35 )
    {
      memset_0(sourceString, 0, 0x208u);
      v8 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v34, v5, v6, v7);
      if ( !(unsigned int)SHExpandEnvironmentStringsW(v8, sourceString, 260) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x187,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardsingleton.cpp",
          v10);
      CurrentCHSIMEBackgroundBrightnessUnvalidated = SystemSettings::Personalization::GetCurrentCHSIMEBackgroundBrightnessUnvalidated(v9);
      if ( CurrentCHSIMEBackgroundBrightnessUnvalidated == 50 )
      {
        string = 0;
        do
          ++v3;
        while ( sourceString[v3] );
        WindowsCreateString(sourceString, v3, &string);
        v12 = string;
      }
      else
      {
        v13 = std::wstring::wstring(v38, sourceString);
        v14 = v40;
        do
        {
          *--v14 = CurrentCHSIMEBackgroundBrightnessUnvalidated % 0xA + 48;
          CurrentCHSIMEBackgroundBrightnessUnvalidated /= 0xAu;
        }
        while ( CurrentCHSIMEBackgroundBrightnessUnvalidated );
        std::wstring::wstring(v39, v14, v40);
        v15 = std::operator+<unsigned short>(v37, v39, L";");
        std::operator+<unsigned short>(v36, v15, v13);
        std::wstring::_Tidy_deallocate(v37);
        std::wstring::_Tidy_deallocate(v39);
        std::wstring::_Tidy_deallocate(v38);
        memset_0(v42, 0, 0x208u);
        v19 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v36, v16, v17, v18);
        if ( !(unsigned int)SHExpandEnvironmentStringsW(v19, v42, 260) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x194,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardsingleton.cpp",
            v20);
        v32 = 0;
        do
          ++v3;
        while ( v42[v3] );
        WindowsCreateString(v42, v3, &v32);
        v12 = v32;
        std::wstring::_Tidy_deallocate(v36);
      }
      goto LABEL_23;
    }
  }
  else
  {
    v21 = *((_QWORD *)a2 + 13);
    if ( v21 )
    {
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)(v21 + 2 * v22) );
      if ( v22 )
      {
        v23 = std::wstring::wstring(v37, v21);
        v24 = std::operator+<unsigned short>(v38, SystemSettings::Personalization::c_touchkeyboardImagePath, v23);
        std::wstring::operator=(v34, v24);
        std::wstring::_Tidy_deallocate(v38);
        std::wstring::_Tidy_deallocate(v37);
      }
    }
  }
  memset_0(v43, 0, 0x208u);
  v28 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v34, v25, v26, v27);
  if ( !(unsigned int)SHExpandEnvironmentStringsW(v28, v43, 260) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1A4,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardsingleton.cpp",
      v29);
  v33 = 0;
  do
    ++v3;
  while ( v43[v3] );
  WindowsCreateString(v43, v3, &v33);
  v12 = v33;
LABEL_23:
  std::wstring::_Tidy_deallocate(v34);
  return v12;
}

```

## disassembly

```asm
0x1801a45ec  mov     [rsp-8+arg_0], rbx
0x1801a45f1  mov     [rsp-8+arg_10], rdi
0x1801a45f6  push    rbp
0x1801a45f7  push    r14
0x1801a45f9  push    r15
0x1801a45fb  lea     rbp, [rsp-650h]
0x1801a4603  sub     rsp, 750h
0x1801a460a  mov     rax, cs:__security_cookie
0x1801a4611  xor     rax, rsp
0x1801a4614  mov     [rbp+660h+var_20], rax
0x1801a461b  mov     rdi, rdx
0x1801a461e  xor     r15d, r15d
0x1801a4621  lea     rdx, LocaleName
0x1801a4628  lea     rcx, [rsp+760h+var_728]
0x1801a462d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801a4632  nop
0x1801a4633  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801a4637  cmp     [rdi+89h], r15b
0x1801a463e  jz      loc_1801A4824
0x1801a4644  lea     r8, aChinesesimplif_3; "ChineseSimplifiedImeBackgroundImagePath"
0x1801a464b  lea     rdx, aSoftwareMicros_45; "Software\\Microsoft\\TabletTip\\1.7\\Us"...
0x1801a4652  lea     rcx, [rsp+760h+var_708]
0x1801a4657  call    ?GetRegistryKeyStringValue@Personalization@SystemSettings@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG00@Z; SystemSettings::Personalization::GetRegistryKeyStringValue(ushort const *,ushort const *,ushort const *)
0x1801a465c  mov     rdx, rax
0x1801a465f  lea     rcx, [rsp+760h+var_728]
0x1801a4664  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1801a4669  lea     rcx, [rsp+760h+var_708]
0x1801a466e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a4673  cmp     [rsp+760h+var_718], r15
0x1801a4678  jz      loc_1801A487E
0x1801a467e  xor     edx, edx; Val
0x1801a4680  mov     r8d, 208h; Size
0x1801a4686  lea     rcx, [rbp+660h+sourceString]; void *
0x1801a468a  call    memset_0
0x1801a468f  mov     rdi, [rbp+668h]
0x1801a4696  lea     rcx, [rsp+760h+var_728]
0x1801a469b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1801a46a0  mov     rcx, rax
0x1801a46a3  mov     r8d, 104h
0x1801a46a9  lea     rdx, [rbp+660h+sourceString]
0x1801a46ad  call    cs:__imp_SHExpandEnvironmentStringsW
0x1801a46b4  nop     dword ptr [rax+rax+00h]
0x1801a46b9  test    eax, eax
0x1801a46bb  jz      loc_1801A4943
0x1801a46c1  call    ?GetCurrentCHSIMEBackgroundBrightnessUnvalidated@Personalization@SystemSettings@@YAKXZ; SystemSettings::Personalization::GetCurrentCHSIMEBackgroundBrightnessUnvalidated(void)
0x1801a46c6  mov     edi, eax
0x1801a46c8  cmp     eax, 32h ; '2'
0x1801a46cb  jnz     short loc_1801A4701
0x1801a46cd  mov     [rsp+760h+string], r15
0x1801a46d2  lea     rax, [rbp+660h+sourceString]
0x1801a46d6  inc     rbx
0x1801a46d9  cmp     [rax+rbx*2], r15w
0x1801a46de  jnz     short loc_1801A46D6
0x1801a46e0  mov     edx, ebx; length
0x1801a46e2  lea     r8, [rsp+760h+string]; string
0x1801a46e7  lea     rcx, [rbp+660h+sourceString]; sourceString
0x1801a46eb  call    cs:__imp_WindowsCreateString
0x1801a46f2  nop     dword ptr [rax+rax+00h]
0x1801a46f7  mov     rbx, [rsp+760h+string]
0x1801a46fc  jmp     loc_1801A48F8
0x1801a4701  lea     rdx, [rbp+660h+sourceString]
0x1801a4705  lea     rcx, [rbp+660h+var_6C8]
0x1801a4709  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801a470e  mov     r14, rax
0x1801a4711  lea     r9, [rbp+660h+var_65E]
0x1801a4715  sub     r9, 2
0x1801a4719  mov     eax, 0CCCCCCCDh
0x1801a471e  mul     edi
0x1801a4720  shr     edx, 3
0x1801a4723  movzx   eax, dx
0x1801a4726  shl     ax, 2
0x1801a472a  lea     ecx, [rax+rdx]
0x1801a472d  add     cx, cx
0x1801a4730  sub     di, cx
0x1801a4733  add     di, 30h ; '0'
0x1801a4737  mov     [r9], di
0x1801a473b  mov     edi, edx
0x1801a473d  test    edx, edx
0x1801a473f  jnz     short loc_1801A4715
0x1801a4741  lea     r8, [rbp+660h+var_65E]
0x1801a4745  mov     rdx, r9
0x1801a4748  lea     rcx, [rbp+660h+var_6A8]
0x1801a474c  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x1801a4751  nop
0x1801a4752  lea     r8, asc_180319074; ";"
0x1801a4759  lea     rdx, [rbp+660h+var_6A8]
0x1801a475d  lea     rcx, [rsp+760h+var_6E8]
0x1801a4762  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1801a4767  nop
0x1801a4768  mov     r8, r14
0x1801a476b  mov     rdx, rax
0x1801a476e  lea     rcx, [rsp+760h+var_708]
0x1801a4773  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x1801a4778  nop
0x1801a4779  lea     rcx, [rsp+760h+var_6E8]
0x1801a477e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a4783  nop
0x1801a4784  lea     rcx, [rbp+660h+var_6A8]
0x1801a4788  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a478d  nop
0x1801a478e  lea     rcx, [rbp+660h+var_6C8]
0x1801a4792  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a4797  xor     edx, edx; Val
0x1801a4799  mov     r8d, 208h; Size
0x1801a479f  lea     rcx, [rbp+660h+var_440]; void *
0x1801a47a6  call    memset_0
0x1801a47ab  mov     rdi, [rbp+668h]
0x1801a47b2  lea     rcx, [rsp+760h+var_708]
0x1801a47b7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1801a47bc  mov     rcx, rax
0x1801a47bf  mov     r8d, 104h
0x1801a47c5  lea     rdx, [rbp+660h+var_440]
0x1801a47cc  call    cs:__imp_SHExpandEnvironmentStringsW
0x1801a47d3  nop     dword ptr [rax+rax+00h]
0x1801a47d8  test    eax, eax
0x1801a47da  jz      loc_1801A4958
0x1801a47e0  mov     [rsp+760h+var_738], r15
0x1801a47e5  lea     rax, [rbp+660h+var_440]
0x1801a47ec  inc     rbx
0x1801a47ef  cmp     [rax+rbx*2], r15w
0x1801a47f4  jnz     short loc_1801A47EC
0x1801a47f6  mov     edx, ebx; length
0x1801a47f8  lea     r8, [rsp+760h+var_738]; string
0x1801a47fd  lea     rcx, [rbp+660h+var_440]; sourceString
0x1801a4804  call    cs:__imp_WindowsCreateString
0x1801a480b  nop     dword ptr [rax+rax+00h]
0x1801a4810  mov     rbx, [rsp+760h+var_738]
0x1801a4815  lea     rcx, [rsp+760h+var_708]
0x1801a481a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a481f  jmp     loc_1801A48F8
0x1801a4824  mov     rdx, [rdi+68h]
0x1801a4828  test    rdx, rdx
0x1801a482b  jz      short loc_1801A487E
0x1801a482d  mov     rax, rbx
0x1801a4830  inc     rax
0x1801a4833  cmp     [rdx+rax*2], r15w
0x1801a4838  jnz     short loc_1801A4830
0x1801a483a  test    rax, rax
0x1801a483d  jz      short loc_1801A487E
0x1801a483f  lea     rcx, [rsp+760h+var_6E8]
0x1801a4844  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801a4849  nop
0x1801a484a  mov     r8, rax
0x1801a484d  lea     rdx, ?c_touchkeyboardImagePath@Personalization@SystemSettings@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SystemSettings::Personalization::c_touchkeyboardImagePath
0x1801a4854  lea     rcx, [rbp+660h+var_6C8]
0x1801a4858  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@$$QEAV10@@Z; std::operator+<ushort>(std::wstring const &,std::wstring &&)
0x1801a485d  mov     rdx, rax
0x1801a4860  lea     rcx, [rsp+760h+var_728]
0x1801a4865  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1801a486a  lea     rcx, [rbp+660h+var_6C8]
0x1801a486e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a4873  nop
0x1801a4874  lea     rcx, [rsp+760h+var_6E8]
0x1801a4879  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a487e  xor     edx, edx; Val
0x1801a4880  mov     r8d, 208h; Size
0x1801a4886  lea     rcx, [rbp+660h+var_230]; void *
0x1801a488d  call    memset_0
0x1801a4892  mov     rdi, [rbp+668h]
0x1801a4899  lea     rcx, [rsp+760h+var_728]
0x1801a489e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1801a48a3  mov     rcx, rax
0x1801a48a6  mov     r8d, 104h
0x1801a48ac  lea     rdx, [rbp+660h+var_230]
0x1801a48b3  call    cs:__imp_SHExpandEnvironmentStringsW
0x1801a48ba  nop     dword ptr [rax+rax+00h]
0x1801a48bf  test    eax, eax
0x1801a48c1  jz      short loc_1801A492E
0x1801a48c3  mov     [rsp+760h+var_730], r15
0x1801a48c8  lea     rax, [rbp+660h+var_230]
0x1801a48cf  inc     rbx
0x1801a48d2  cmp     [rax+rbx*2], r15w
0x1801a48d7  jnz     short loc_1801A48CF
0x1801a48d9  mov     edx, ebx; length
0x1801a48db  lea     r8, [rsp+760h+var_730]; string
0x1801a48e0  lea     rcx, [rbp+660h+var_230]; sourceString
0x1801a48e7  call    cs:__imp_WindowsCreateString
0x1801a48ee  nop     dword ptr [rax+rax+00h]
0x1801a48f3  mov     rbx, [rsp+760h+var_730]
0x1801a48f8  lea     rcx, [rsp+760h+var_728]
0x1801a48fd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a4902  mov     rax, rbx
0x1801a4905  mov     rcx, [rbp+660h+var_20]
0x1801a490c  xor     rcx, rsp; StackCookie
0x1801a490f  call    __security_check_cookie
0x1801a4914  lea     r11, [rsp+760h+var_10]
0x1801a491c  mov     rbx, [r11+20h]
0x1801a4920  mov     rdi, [r11+30h]
0x1801a4924  mov     rsp, r11
0x1801a4927  pop     r15
0x1801a4929  pop     r14
0x1801a492b  pop     rbp
0x1801a492c  retn
0x1801a492e  lea     r8, aShellSystemset_64; "shell\\systemsettingsthreshold\\handler"...
0x1801a4935  mov     edx, 1A4h; void *
0x1801a493a  mov     rcx, rdi; this
0x1801a493d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801a4943  lea     r8, aShellSystemset_64; "shell\\systemsettingsthreshold\\handler"...
0x1801a494a  mov     edx, 187h; void *
0x1801a494f  mov     rcx, rdi; this
0x1801a4952  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801a4958  lea     r8, aShellSystemset_64; "shell\\systemsettingsthreshold\\handler"...
0x1801a495f  mov     edx, 194h; void *
0x1801a4964  mov     rcx, rdi; this
0x1801a4967  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
