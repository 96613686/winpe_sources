# SystemSettings::DataModel::CLangugeInputMethodSetting::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x1800f21f0`
- end: `0x1800f25df`
- name: `?GetProperty@CLangugeInputMethodSetting@DataModel@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `1007`
- prototype: `int(SystemSettings::DataModel::CLangugeInputMethodSetting *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000c840`
- `0x180010e41`
- `0x180011bb0`
- `0x180019a20`
- `0x18001a64c`
- `0x1800201c4`
- `0x1800212b0`
- `0x180032208`
- `0x18004d218`
- `0x1800f21f0`
- `0x1800f3e50`
- `0x1800fd4e8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f2267`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f2298`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f22c6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f234f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f2392`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f23d5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f2418`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f2461`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f248f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f24c5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f2517`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f254a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f2267`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f2298`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f22c6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f234f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f2392`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f23d5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f2418`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f2461`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f248f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f24c5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f2517`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f254a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f2223`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f223b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f2223`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f223b`

## string_xrefs

- `0x1800f24b8`: `IsConfigurableIME`
- `0x1800f2342`: `IsInstallable`
- `0x1800f23f4`: `SystemSettings_Language_RemoveInputMethod_ActionDescription`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CLangugeInputMethodSetting::GetProperty(
        SystemSettings::DataModel::CLangugeInputMethodSetting *this,
        HSTRING a2,
        struct IInspectable **a3)
{
  const WCHAR *StringRawBuffer; // rax
  char v7; // bl
  const WCHAR *v8; // rbp
  unsigned __int16 *v9; // rcx
  int v10; // eax
  unsigned int v11; // ebx
  unsigned __int8 v14; // cl
  struct IInspectable **v15; // r8
  wchar_t *v16; // rcx
  unsigned int Instance_LanguageIMESettingsDBDesktop; // esi
  unsigned __int64 i; // rsi
  struct IInspectable **v19; // rbx
  unsigned __int16 v20[976]; // [rsp+30h] [rbp-7D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+808h] [rbp+0h]

  WindowsGetStringRawBuffer(a2, 0);
  *a3 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v7 = 1;
  v8 = StringRawBuffer;
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"Name", -1, 1) != 2 )
  {
    if ( CompareStringOrdinal(v8, -1, L"TileText", -1, 1) == 2 )
    {
      v9 = (unsigned __int16 *)((char *)this + 256);
      return (unsigned int)SystemSettings::DataModel::PropValueHelper::CreateString(v9, a3);
    }
    if ( CompareStringOrdinal(v8, -1, L"NarratorText", -1, 1) == 2 )
    {
      v10 = StringCchPrintfW(v20, 0x165u, L"%ws %ws", (char *)this + 632);
      v11 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3F7,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\language\\lib\\languageoptionhandlers.cpp",
          (const char *)(unsigned int)v10,
          (_DWORD)this + 256);
        return v11;
      }
      v9 = v20;
      return (unsigned int)SystemSettings::DataModel::PropValueHelper::CreateString(v9, a3);
    }
    if ( CompareStringOrdinal(v8, -1, L"IsInstallable", -1, 1) == 2 )
    {
      if ( !*((_BYTE *)this + 1665) )
      {
        if ( *((_DWORD *)this + 414) != 1 )
          goto LABEL_26;
        goto LABEL_24;
      }
      goto LABEL_25;
    }
    if ( CompareStringOrdinal(v8, -1, L"IsRemovable", -1, 1) == 2 )
    {
      if ( !*((_DWORD *)this + 63) )
        SystemSettings::DataModel::CLangugeInputMethodSetting::_UpdateRemovableState(this, 0);
      v14 = *((_DWORD *)this + 63) == 1;
      return (unsigned int)SystemSettings::DataModel::PropValueHelper::CreateBoolean(v14, a3);
    }
    if ( CompareStringOrdinal(v8, -1, L"ActionDescription", -1, 1) == 2 )
    {
      v16 = L"SystemSettings_Language_RemoveInputMethod_ActionDescription";
      if ( !*((_BYTE *)this + 1665) )
        v16 = L"SystemSettings_Language_AddInputMethod_ActionDescription";
    }
    else
    {
      if ( CompareStringOrdinal(v8, -1, L"IsImmersiveIME", -1, 1) == 2 )
      {
        if ( *((_DWORD *)this + 414) == 1 )
        {
LABEL_24:
          if ( !*((_BYTE *)this + 1661) )
            goto LABEL_25;
LABEL_26:
          v14 = v7;
          return (unsigned int)SystemSettings::DataModel::PropValueHelper::CreateBoolean(v14, a3);
        }
LABEL_25:
        v7 = 0;
        goto LABEL_26;
      }
      if ( CompareStringOrdinal(v8, -1, L"IMEOptionsDescription", -1, 1) == 2 )
      {
        v16 = L"SystemSettings_Language_IMEOptionsDescription";
      }
      else
      {
        if ( CompareStringOrdinal(v8, -1, L"FlyoutIMEOptionsDescription", -1, 1) != 2 )
        {
          if ( CompareStringOrdinal(v8, -1, L"IsConfigurableIME", -1, 1) != 2 )
          {
            Instance_LanguageIMESettingsDBDesktop = -2147024809;
            if ( CompareStringOrdinal(v8, -1, L"DynamicSettingsDatabaseValue", -1, 1) == 2 && !*((_BYTE *)this + 248) )
            {
              v19 = (struct IInspectable **)((char *)this + 2200);
              if ( *((_QWORD *)this + 275)
                || (Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 2200),
                    memcpy_0(v20, (char *)this + 256, 0x794u),
                    Instance_LanguageIMESettingsDBDesktop = SystemSettings::DataModel::CreateInstance_LanguageIMESettingsDBDesktop(
                                                              v20,
                                                              (char *)this + 2200),
                    *v19) )
              {
                Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef((char *)this + 2200);
                Instance_LanguageIMESettingsDBDesktop = 0;
                *a3 = *v19;
              }
            }
            return Instance_LanguageIMESettingsDBDesktop;
          }
          if ( *((_DWORD *)this + 414) == 1 && *((_BYTE *)this + 1661) )
          {
            for ( i = 0; i < 9; ++i )
            {
              if ( CompareStringOrdinal((LPCWCH)this + 572, -1, off_1802BF9A0[i], -1, 1) == 2 )
                goto LABEL_26;
            }
          }
          goto LABEL_25;
        }
        v16 = L"SystemSettings_Language_FlyoutIMEOptionsDescription";
      }
    }
    return (unsigned int)SystemSettings::DataModel::GetResourceStringValue((SystemSettings::DataModel *)v16, a3, v15);
  }
  v9 = (unsigned __int16 *)((char *)this + 632);
  return (unsigned int)SystemSettings::DataModel::PropValueHelper::CreateString(v9, a3);
}

```

## disassembly

```asm
0x1800f21f0  mov     [rsp+arg_18], rbx
0x1800f21f5  push    rbp
0x1800f21f6  push    rsi
0x1800f21f7  push    rdi
0x1800f21f8  push    r14
0x1800f21fa  push    r15
0x1800f21fc  sub     rsp, 7E0h
0x1800f2203  mov     rax, cs:__security_cookie
0x1800f220a  xor     rax, rsp
0x1800f220d  mov     [rsp+808h+var_38], rax
0x1800f2215  mov     rbx, rdx
0x1800f2218  mov     rdi, rcx
0x1800f221b  mov     rcx, rbx; string
0x1800f221e  xor     edx, edx; length
0x1800f2220  mov     r14, r8
0x1800f2223  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f222a  nop     dword ptr [rax+rax+00h]
0x1800f222f  xor     edx, edx; length
0x1800f2231  mov     qword ptr [r14], 0
0x1800f2238  mov     rcx, rbx; string
0x1800f223b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f2242  nop     dword ptr [rax+rax+00h]
0x1800f2247  or      r15d, 0FFFFFFFFh
0x1800f224b  lea     r8, aName; "Name"
0x1800f2252  mov     ebx, 1
0x1800f2257  mov     r9d, r15d; cchCount2
0x1800f225a  mov     edx, r15d; cchCount1
0x1800f225d  mov     [rsp+808h+bIgnoreCase], ebx; bIgnoreCase
0x1800f2261  mov     rcx, rax; lpString1
0x1800f2264  mov     rbp, rax
0x1800f2267  call    cs:__imp_CompareStringOrdinal
0x1800f226e  nop     dword ptr [rax+rax+00h]
0x1800f2273  cmp     eax, 2
0x1800f2276  jnz     short loc_1800F2284
0x1800f2278  lea     rcx, [rdi+278h]
0x1800f227f  jmp     loc_1800F232E
0x1800f2284  mov     r9d, r15d; cchCount2
0x1800f2287  mov     [rsp+808h+bIgnoreCase], ebx; bIgnoreCase
0x1800f228b  lea     r8, aTiletext; "TileText"
0x1800f2292  mov     edx, r15d; cchCount1
0x1800f2295  mov     rcx, rbp; lpString1
0x1800f2298  call    cs:__imp_CompareStringOrdinal
0x1800f229f  nop     dword ptr [rax+rax+00h]
0x1800f22a4  cmp     eax, 2
0x1800f22a7  jnz     short loc_1800F22B2
0x1800f22a9  lea     rcx, [rdi+100h]
0x1800f22b0  jmp     short loc_1800F232E
0x1800f22b2  mov     r9d, r15d; cchCount2
0x1800f22b5  mov     [rsp+808h+bIgnoreCase], ebx; bIgnoreCase
0x1800f22b9  lea     r8, aNarratortext; "NarratorText"
0x1800f22c0  mov     edx, r15d; cchCount1
0x1800f22c3  mov     rcx, rbp; lpString1
0x1800f22c6  call    cs:__imp_CompareStringOrdinal
0x1800f22cd  nop     dword ptr [rax+rax+00h]
0x1800f22d2  cmp     eax, 2
0x1800f22d5  jnz     short loc_1800F233B
0x1800f22d7  lea     rax, [rdi+100h]
0x1800f22de  mov     edx, 165h; unsigned __int64
0x1800f22e3  lea     r9, [rdi+278h]
0x1800f22ea  mov     qword ptr [rsp+808h+bIgnoreCase], rax; int
0x1800f22ef  lea     r8, aWsWs_2; "%ws %ws"
0x1800f22f6  lea     rcx, [rsp+808h+var_7D8]; unsigned __int16 *
0x1800f22fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800f2300  mov     ebx, eax
0x1800f2302  test    eax, eax
0x1800f2304  jns     short loc_1800F2329
0x1800f2306  mov     rcx, [rsp+808h]; this
0x1800f230e  lea     r8, aShellSystemset_111; "shell\\systemsettingsthreshold\\handler"...
0x1800f2315  mov     r9d, eax; char *
0x1800f2318  mov     edx, 3F7h; void *
0x1800f231d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f2322  mov     eax, ebx
0x1800f2324  jmp     loc_1800F25B7
0x1800f2329  lea     rcx, [rsp+808h+var_7D8]; unsigned __int16 *
0x1800f232e  mov     rdx, r14; struct IInspectable **
0x1800f2331  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1800f2336  jmp     loc_1800F2446
0x1800f233b  mov     r9d, r15d; cchCount2
0x1800f233e  mov     [rsp+808h+bIgnoreCase], ebx; bIgnoreCase
0x1800f2342  lea     r8, aIsinstallable; "IsInstallable"
0x1800f2349  mov     edx, r15d; cchCount1
0x1800f234c  mov     rcx, rbp; lpString1
0x1800f234f  call    cs:__imp_CompareStringOrdinal
0x1800f2356  nop     dword ptr [rax+rax+00h]
0x1800f235b  cmp     eax, 2
0x1800f235e  jnz     short loc_1800F237E
0x1800f2360  cmp     byte ptr [rdi+681h], 0
0x1800f2367  jnz     loc_1800F243A
0x1800f236d  cmp     [rdi+678h], ebx
0x1800f2373  jnz     loc_1800F243C
0x1800f2379  jmp     loc_1800F2431
0x1800f237e  mov     r9d, r15d; cchCount2
0x1800f2381  mov     [rsp+808h+bIgnoreCase], ebx; bIgnoreCase
0x1800f2385  lea     r8, aIsremovable; "IsRemovable"
0x1800f238c  mov     edx, r15d; cchCount1
0x1800f238f  mov     rcx, rbp; lpString1
0x1800f2392  call    cs:__imp_CompareStringOrdinal
0x1800f2399  nop     dword ptr [rax+rax+00h]
0x1800f239e  cmp     eax, 2
0x1800f23a1  jnz     short loc_1800F23C1
0x1800f23a3  cmp     dword ptr [rdi+0FCh], 0
0x1800f23aa  jnz     short loc_1800F23B6
0x1800f23ac  xor     edx, edx; bool
0x1800f23ae  mov     rcx, rdi; this
0x1800f23b1  call    ?_UpdateRemovableState@CLangugeInputMethodSetting@DataModel@SystemSettings@@AEAAX_N@Z; SystemSettings::DataModel::CLangugeInputMethodSetting::_UpdateRemovableState(bool)
0x1800f23b6  cmp     [rdi+0FCh], ebx
0x1800f23bc  setz    cl
0x1800f23bf  jmp     short loc_1800F243E
0x1800f23c1  mov     r9d, r15d; cchCount2
0x1800f23c4  mov     [rsp+808h+bIgnoreCase], ebx; bIgnoreCase
0x1800f23c8  lea     r8, aActiondescript_0; "ActionDescription"
0x1800f23cf  mov     edx, r15d; cchCount1
0x1800f23d2  mov     rcx, rbp; lpString1
0x1800f23d5  call    cs:__imp_CompareStringOrdinal
0x1800f23dc  nop     dword ptr [rax+rax+00h]
0x1800f23e1  cmp     eax, 2
0x1800f23e4  jnz     short loc_1800F2404
0x1800f23e6  cmp     byte ptr [rdi+681h], 0
0x1800f23ed  lea     rax, aSystemsettings_377; "SystemSettings_Language_AddInputMethod_"...
0x1800f23f4  lea     rcx, aSystemsettings_200; "SystemSettings_Language_RemoveInputMeth"...
0x1800f23fb  cmovz   rcx, rax
0x1800f23ff  jmp     loc_1800F24A7
0x1800f2404  mov     r9d, r15d; cchCount2
0x1800f2407  mov     [rsp+808h+bIgnoreCase], ebx; bIgnoreCase
0x1800f240b  lea     r8, aIsimmersiveime; "IsImmersiveIME"
0x1800f2412  mov     edx, r15d; cchCount1
0x1800f2415  mov     rcx, rbp; lpString1
0x1800f2418  call    cs:__imp_CompareStringOrdinal
0x1800f241f  nop     dword ptr [rax+rax+00h]
0x1800f2424  cmp     eax, 2
0x1800f2427  jnz     short loc_1800F244D
0x1800f2429  cmp     [rdi+678h], ebx
0x1800f242f  jnz     short loc_1800F243A
0x1800f2431  cmp     byte ptr [rdi+67Dh], 0
0x1800f2438  jnz     short loc_1800F243C
0x1800f243a  xor     bl, bl
0x1800f243c  mov     cl, bl; unsigned __int8
0x1800f243e  mov     rdx, r14; struct IInspectable **
0x1800f2441  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x1800f2446  mov     esi, eax
0x1800f2448  jmp     loc_1800F25B5
0x1800f244d  mov     r9d, r15d; cchCount2
0x1800f2450  mov     [rsp+808h+bIgnoreCase], ebx; bIgnoreCase
0x1800f2454  lea     r8, aImeoptionsdesc; "IMEOptionsDescription"
0x1800f245b  mov     edx, r15d; cchCount1
0x1800f245e  mov     rcx, rbp; lpString1
0x1800f2461  call    cs:__imp_CompareStringOrdinal
0x1800f2468  nop     dword ptr [rax+rax+00h]
0x1800f246d  cmp     eax, 2
0x1800f2470  jnz     short loc_1800F247B
0x1800f2472  lea     rcx, aSystemsettings_1624; "SystemSettings_Language_IMEOptionsDescr"...
0x1800f2479  jmp     short loc_1800F24A7
0x1800f247b  mov     r9d, r15d; cchCount2
0x1800f247e  mov     [rsp+808h+bIgnoreCase], ebx; bIgnoreCase
0x1800f2482  lea     r8, aFlyoutimeoptio; "FlyoutIMEOptionsDescription"
0x1800f2489  mov     edx, r15d; cchCount1
0x1800f248c  mov     rcx, rbp; lpString1
0x1800f248f  call    cs:__imp_CompareStringOrdinal
0x1800f2496  nop     dword ptr [rax+rax+00h]
0x1800f249b  cmp     eax, 2
0x1800f249e  jnz     short loc_1800F24B1
0x1800f24a0  lea     rcx, aSystemsettings_871; "SystemSettings_Language_FlyoutIMEOption"...
0x1800f24a7  mov     rdx, r14; struct IInspectable **
0x1800f24aa  call    ?GetResourceStringValue@DataModel@SystemSettings@@YAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::GetResourceStringValue(ushort const *,IInspectable * *)
0x1800f24af  jmp     short loc_1800F2446
0x1800f24b1  mov     r9d, r15d; cchCount2
0x1800f24b4  mov     [rsp+808h+bIgnoreCase], ebx; bIgnoreCase
0x1800f24b8  lea     r8, aIsconfigurable; "IsConfigurableIME"
0x1800f24bf  mov     edx, r15d; cchCount1
0x1800f24c2  mov     rcx, rbp; lpString1
0x1800f24c5  call    cs:__imp_CompareStringOrdinal
0x1800f24cc  nop     dword ptr [rax+rax+00h]
0x1800f24d1  cmp     eax, 2
0x1800f24d4  jnz     short loc_1800F2531
0x1800f24d6  cmp     [rdi+678h], ebx
0x1800f24dc  jnz     loc_1800F243A
0x1800f24e2  cmp     byte ptr [rdi+67Dh], 0
0x1800f24e9  jz      loc_1800F243A
0x1800f24ef  xor     esi, esi
0x1800f24f1  cmp     rsi, 9
0x1800f24f5  jnb     loc_1800F243A
0x1800f24fb  lea     r8, off_1802BF9A0; "0411:{03B5835F-F03C-411B-9CE2-AA23E1171"...
0x1800f2502  mov     [rsp+808h+bIgnoreCase], ebx; bIgnoreCase
0x1800f2506  mov     r8, [r8+rsi*8]; lpString2
0x1800f250a  lea     rcx, [rdi+478h]; lpString1
0x1800f2511  mov     r9d, r15d; cchCount2
0x1800f2514  mov     edx, r15d; cchCount1
0x1800f2517  call    cs:__imp_CompareStringOrdinal
0x1800f251e  nop     dword ptr [rax+rax+00h]
0x1800f2523  cmp     eax, 2
0x1800f2526  jz      loc_1800F243C
0x1800f252c  add     rsi, rbx
0x1800f252f  jmp     short loc_1800F24F1
0x1800f2531  mov     r9d, r15d; cchCount2
0x1800f2534  mov     [rsp+808h+bIgnoreCase], ebx; bIgnoreCase
0x1800f2538  lea     r8, aDynamicsetting; "DynamicSettingsDatabaseValue"
0x1800f253f  mov     edx, r15d; cchCount1
0x1800f2542  mov     rcx, rbp; lpString1
0x1800f2545  mov     esi, 80070057h
0x1800f254a  call    cs:__imp_CompareStringOrdinal
0x1800f2551  nop     dword ptr [rax+rax+00h]
0x1800f2556  cmp     eax, 2
0x1800f2559  jnz     short loc_1800F25B5
0x1800f255b  cmp     byte ptr [rdi+0F8h], 0
0x1800f2562  jnz     short loc_1800F25B5
0x1800f2564  lea     rbx, [rdi+898h]
0x1800f256b  cmp     qword ptr [rbx], 0
0x1800f256f  jnz     short loc_1800F25A5
0x1800f2571  mov     rcx, rbx
0x1800f2574  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f2579  lea     rcx, [rsp+808h+var_7D8]; void *
0x1800f257e  mov     r8d, 794h; Size
0x1800f2584  lea     rdx, [rdi+100h]; Src
0x1800f258b  call    memcpy_0
0x1800f2590  mov     rdx, rbx
0x1800f2593  lea     rcx, [rsp+808h+var_7D8]
0x1800f2598  call    ?CreateInstance_LanguageIMESettingsDBDesktop@DataModel@SystemSettings@@YAJUEXTENDED_INPUTMETHODDATATYPE@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::CreateInstance_LanguageIMESettingsDBDesktop(EXTENDED_INPUTMETHODDATATYPE,IInspectable * *)
0x1800f259d  cmp     qword ptr [rbx], 0
0x1800f25a1  mov     esi, eax
0x1800f25a3  jz      short loc_1800F25B5
0x1800f25a5  mov     rcx, rbx
0x1800f25a8  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800f25ad  mov     rax, [rbx]
0x1800f25b0  xor     esi, esi
0x1800f25b2  mov     [r14], rax
0x1800f25b5  mov     eax, esi
0x1800f25b7  mov     rcx, [rsp+808h+var_38]
0x1800f25bf  xor     rcx, rsp; StackCookie
0x1800f25c2  call    __security_check_cookie
0x1800f25c7  mov     rbx, [rsp+808h+arg_18]
0x1800f25cf  add     rsp, 7E0h
0x1800f25d6  pop     r15
0x1800f25d8  pop     r14
0x1800f25da  pop     rdi
0x1800f25db  pop     rsi
0x1800f25dc  pop     rbp
0x1800f25dd  retn
```
