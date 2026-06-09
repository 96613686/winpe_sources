# _lambda_3d286022ee928f8cb6ff2c371b0c4c3f_::operator()

- ea: `0x18036de84`
- end: `0x18036e2e2`
- name: `_lambda_3d286022ee928f8cb6ff2c371b0c4c3f_::operator()`
- size: `1118`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800328c0`

## callees

- `0x18000ce94`
- `0x1800240ac`
- `0x18002edec`
- `0x18004a468`
- `0x1800dd908`
- `0x180161204`
- `0x180219b4c`
- `0x180263540`
- `0x18036de84`
- `0x18037113c`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18036e1f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18036e1f0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18036dfa6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18036dfa6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18036df14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18036dfba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18036e172`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18036e2a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18036df14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18036dfba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18036e172`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18036e2a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18036df54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18036df88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18036df54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18036df88`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18036e0f1`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18036e0f1`
- `api-ms-win-appmodel-runtime-l1-1-3!GetPackagePathByFullName2` at `0x18036e0a5`
- `api-ms-win-appmodel-runtime-l1-1-3!GetPackagePathByFullName2` at `0x18036e0a5`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18036deaf`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18036deaf`

## string_xrefs

- `0x18036deea`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\tilestoretransformer.cpp`
- `0x18036df38`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\tilestoretransformer.cpp`
- `0x18036df71`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\tilestoretransformer.cpp`
- `0x18036e258`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\tilestoretransformer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_3d286022ee928f8cb6ff2c371b0c4c3f_::operator()(__int64 a1)
{
  char v2; // r14
  int v3; // eax
  bool v4; // bl
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, HSTRING *); // rbx
  int v7; // eax
  const WCHAR *StringRawBuffer; // rax
  bool *v9; // r8
  int IsAUMIDUninstallable; // eax
  const WCHAR *v11; // rax
  __int64 v12; // rcx
  __int16 v13; // ax
  __int64 v14; // rdi
  unsigned __int8 (__fastcall *v15)(__int64, void *, HSTRING *); // rbx
  const unsigned __int16 *v16; // rax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rdi
  unsigned __int8 (__fastcall *v20)(__int64, void *, HSTRING *); // rbx
  __int64 v21; // rbx
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, HSTRING, __int64 *); // rbx
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rcx
  _BYTE *v27; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-38h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-38h]
  HSTRING v31; // [rsp+30h] [rbp-28h] BYREF
  __int64 v32; // [rsp+38h] [rbp-20h] BYREF
  PSRWLOCK SRWLock[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  __int64 v35; // [rsp+90h] [rbp+38h] BYREF
  HSTRING string; // [rsp+98h] [rbp+40h] BYREF
  __int64 v37; // [rsp+A0h] [rbp+48h] BYREF
  __int64 v38; // [rsp+A8h] [rbp+50h] BYREF

  if ( !*(_BYTE *)(*(_QWORD *)(a1 + 8) + 4LL) )
  {
    if ( (unsigned int)SHWindowsPolicy(POLID_NoUninstallFromStart) || *(_DWORD *)(a1 + 16) != 1 )
      goto LABEL_46;
    v2 = 1;
    LOBYTE(v35) = 1;
    v37 = 0;
    v3 = Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier>::As<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifier>(
           *(_QWORD *)(a1 + 24),
           &v37);
    if ( v3 >= 0 )
    {
      string = 0;
      v5 = v37;
      v6 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 48LL);
      WindowsDeleteString(0);
      string = 0;
      v7 = v6(v5, &string);
      if ( v7 >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        IsAUMIDUninstallable = ShellBlockLists::IsAUMIDUninstallable(StringRawBuffer, (unsigned __int16 *)&v35, v9);
        if ( IsAUMIDUninstallable < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x3BA,
            (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
            (const char *)(unsigned int)IsAUMIDUninstallable,
            bIgnoreCase);
        v11 = WindowsGetStringRawBuffer(string, 0);
        v4 = CompareStringOrdinal(ShellBlockLists::PackagedAppsThatAreInstalledByFOD, -1, v11, -1, 1) == 2;
        v2 = v35;
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x3B8,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
          (const char *)(unsigned int)v7,
          bIgnoreCase);
        v4 = 0;
      }
      WindowsDeleteString(string);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3B6,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
        (const char *)(unsigned int)v3,
        bIgnoreCase);
      v4 = 0;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    if ( !v2 )
      goto LABEL_46;
    LODWORD(v37) = 0;
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD, _GUID **, __int64, __int64 *))(***(_QWORD ***)(a1 + 32) + 24LL))(
           **(_QWORD **)(a1 + 32),
           &DataStoreCache::TileStoreProperties::PackageExecutionContext,
           4,
           &v37)
      && (_DWORD)v37 == 3 )
    {
      v12 = *(_QWORD *)(a1 + 8);
      *(_DWORD *)v12 = 2;
LABEL_47:
      v13 = *(_WORD *)((char *)&v35 + 5);
      goto LABEL_48;
    }
    v12 = *(_QWORD *)(a1 + 8);
    v13 = *(_WORD *)((char *)&v35 + 5);
    if ( v4 )
    {
      *(_DWORD *)v12 = 3;
LABEL_48:
      *(_BYTE *)(v12 + 4) = 1;
      *(_WORD *)(v12 + 5) = v13;
      *(_BYTE *)(v12 + 7) = HIBYTE(v35);
      goto LABEL_49;
    }
    *(_DWORD *)v12 = 1;
    *(_BYTE *)(v12 + 4) = 1;
    *(_WORD *)(v12 + 5) = v13;
    *(_BYTE *)(v12 + 7) = HIBYTE(v35);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShowSettingsUninstallForSparsePackages>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShowSettingsUninstallForSparsePackages>::GetImpl'::`2'::impl) )
    {
      string = 0;
      v14 = **(_QWORD **)(a1 + 32);
      v15 = *(unsigned __int8 (__fastcall **)(__int64, void *, HSTRING *))(*(_QWORD *)v14 + 32LL);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&string);
      if ( v15(v14, &DataStoreCache::TileStoreProperties::PackageFullName, &string) )
      {
        LODWORD(v35) = 0;
        v16 = winrt::hstring::c_str((winrt::hstring *)&string);
        if ( (unsigned int)GetPackagePathByFullName2(v16, 5, &v35) == 122 )
        {
          if ( (_DWORD)v35 )
          {
            v17 = *(_QWORD *)(a1 + 8);
            *(_DWORD *)v17 = 2;
            *(_BYTE *)(v17 + 4) = 1;
            *(_WORD *)(v17 + 5) = *(_WORD *)((char *)&v35 + 5);
            *(_BYTE *)(v17 + 7) = HIBYTE(v35);
          }
        }
      }
      winrt::handle_type<winrt::impl::hstring_traits>::close(&string);
    }
    if ( `Details::GetDeviceFamily'::`2'::s_hasChecked )
    {
      v18 = `Details::GetDeviceFamily'::`2'::s_platform;
    }
    else
    {
      LODWORD(v35) = 0;
      RtlGetDeviceFamilyInfoEnum(0, &v35, 0);
      v18 = v35;
      `Details::GetDeviceFamily'::`2'::s_platform = v35;
      `Details::GetDeviceFamily'::`2'::s_hasChecked = 1;
    }
    if ( ((v18 - 14) & 0xFFFFFFFD) == 0 )
    {
      LODWORD(string) = 0;
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD, void **, __int64, HSTRING *))(***(_QWORD ***)(a1 + 32) + 24LL))(
             **(_QWORD **)(a1 + 32),
             &DataStoreCache::TileStoreProperties::PackageOrigin,
             4,
             &string) )
      {
        if ( (_DWORD)string != 2 )
        {
          if ( (_DWORD)string != 3 )
            goto LABEL_49;
          v31 = 0;
          v19 = **(_QWORD **)(a1 + 32);
          v20 = *(unsigned __int8 (__fastcall **)(__int64, void *, HSTRING *))(*(_QWORD *)v19 + 32LL);
          WindowsDeleteString(0);
          v31 = 0;
          if ( !v20(v19, &DataStoreCache::TileStoreProperties::PackageFullName, &v31) )
            goto LABEL_45;
          v32 = 0;
          Microsoft::WRL::Wrappers::SRWLock::LockShared(SRWLock, *(_QWORD *)a1 + 152LL);
          v21 = *(_QWORD *)(*(_QWORD *)a1 + 304LL);
          v22 = 0;
          if ( v21 )
          {
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v21 + 8LL))(*(_QWORD *)(*(_QWORD *)a1 + 304LL));
            v35 = 0;
            v32 = v21;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
            v22 = v21;
          }
          if ( SRWLock[0] )
            ReleaseSRWLockShared(SRWLock[0]);
          v38 = 0;
          if ( v22 )
          {
            v23 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v22 + 176LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
            v24 = v23(v22, v31, &v38);
            if ( v24 >= 0 )
            {
              LOBYTE(v35) = 0;
              v24 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 224LL))(v38, &v35);
              if ( v24 >= 0 )
              {
                if ( (_BYTE)v35 )
                {
                  v26 = *(_QWORD *)(a1 + 8);
                  *(_DWORD *)v26 = 0;
                  *(_BYTE *)(v26 + 4) = 1;
                  *(_WORD *)(v26 + 5) = *(_WORD *)((char *)&v35 + 5);
                  *(_BYTE *)(v26 + 7) = HIBYTE(v35);
                }
                goto LABEL_44;
              }
              v25 = 1039;
            }
            else
            {
              v25 = 1036;
            }
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)v25,
              (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
              (const char *)(unsigned int)v24,
              bIgnoreCasea);
          }
LABEL_44:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
LABEL_45:
          WindowsDeleteString(v31);
          goto LABEL_49;
        }
LABEL_46:
        v12 = *(_QWORD *)(a1 + 8);
        *(_DWORD *)v12 = 0;
        goto LABEL_47;
      }
    }
  }
LABEL_49:
  v27 = *(_BYTE **)(a1 + 8);
  if ( !v27[4] )
    std::_Throw_bad_optional_access();
  return *(unsigned int *)v27;
}

```

## disassembly

```asm
0x18036de84  push    rbp
0x18036de86  push    rbx
0x18036de87  push    rsi
0x18036de88  push    rdi
0x18036de89  push    r14
0x18036de8b  push    r15
0x18036de8d  mov     rbp, rsp
0x18036de90  sub     rsp, 58h
0x18036de94  mov     rsi, rcx
0x18036de97  mov     rax, [rcx+8]
0x18036de9b  xor     r15d, r15d
0x18036de9e  cmp     [rax+4], r15b
0x18036dea2  jnz     loc_18036E2C3
0x18036dea8  lea     rcx, POLID_NoUninstallFromStart
0x18036deaf  call    cs:__imp_SHWindowsPolicy
0x18036deb5  test    eax, eax
0x18036deb7  jnz     loc_18036E2AA
0x18036debd  cmp     dword ptr [rsi+10h], 1
0x18036dec1  jnz     loc_18036E2AA
0x18036dec7  mov     r14b, 1
0x18036deca  mov     byte ptr [rbp+arg_0], r14b
0x18036dece  mov     [rbp+arg_10], r15
0x18036ded2  lea     rdx, [rbp+arg_10]
0x18036ded6  mov     rcx, [rsi+18h]
0x18036deda  call    ??$As@UIPackagedUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@?$ComPtr@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPackagedUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier>::As<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifier>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifier>>)
0x18036dedf  mov     rcx, [rbp+30h]; this
0x18036dee3  test    eax, eax
0x18036dee5  jns     short loc_18036DF03
0x18036dee7  mov     r9d, eax; char *
0x18036deea  lea     r8, aShellcommonShe_151; "shellcommon\\shell\\datastorecache\\tra"...
0x18036def1  mov     edx, 3B6h; void *
0x18036def6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18036defb  mov     bl, r15b
0x18036defe  jmp     loc_18036DFC0
0x18036df03  mov     [rbp+string], r15
0x18036df07  mov     rdi, [rbp+arg_10]
0x18036df0b  mov     rax, [rdi]
0x18036df0e  mov     rbx, [rax+30h]
0x18036df12  xor     ecx, ecx; string
0x18036df14  call    cs:__imp_WindowsDeleteString
0x18036df1a  mov     [rbp+string], r15
0x18036df1e  lea     rdx, [rbp+string]
0x18036df22  mov     rcx, rdi
0x18036df25  mov     rax, rbx
0x18036df28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18036df2d  mov     rcx, [rbp+30h]; this
0x18036df31  test    eax, eax
0x18036df33  jns     short loc_18036DF4E
0x18036df35  mov     r9d, eax; char *
0x18036df38  lea     r8, aShellcommonShe_151; "shellcommon\\shell\\datastorecache\\tra"...
0x18036df3f  mov     edx, 3B8h; void *
0x18036df44  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18036df49  mov     bl, r15b
0x18036df4c  jmp     short loc_18036DFB6
0x18036df4e  xor     edx, edx; length
0x18036df50  mov     rcx, [rbp+string]; string
0x18036df54  call    cs:__imp_WindowsGetStringRawBuffer
0x18036df5a  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x18036df5e  mov     rcx, rax; lpString2
0x18036df61  call    ?IsAUMIDUninstallable@ShellBlockLists@@YAJPEBGPEA_N@Z; ShellBlockLists::IsAUMIDUninstallable(ushort const *,bool *)
0x18036df66  mov     rcx, [rbp+30h]; this
0x18036df6a  test    eax, eax
0x18036df6c  jns     short loc_18036DF82
0x18036df6e  mov     r9d, eax; char *
0x18036df71  lea     r8, aShellcommonShe_151; "shellcommon\\shell\\datastorecache\\tra"...
0x18036df78  mov     edx, 3BAh; void *
0x18036df7d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18036df82  xor     edx, edx; length
0x18036df84  mov     rcx, [rbp+string]; string
0x18036df88  call    cs:__imp_WindowsGetStringRawBuffer
0x18036df8e  mov     [rsp+58h+bIgnoreCase], 1; int
0x18036df96  or      edx, 0FFFFFFFFh; cchCount1
0x18036df99  mov     r9d, edx; cchCount2
0x18036df9c  mov     r8, rax; lpString2
0x18036df9f  mov     rcx, cs:?PackagedAppsThatAreInstalledByFOD@ShellBlockLists@@3QBQEBGB; lpString1
0x18036dfa6  call    cs:__imp_CompareStringOrdinal
0x18036dfac  cmp     eax, 2
0x18036dfaf  setz    bl
0x18036dfb2  mov     r14b, byte ptr [rbp+arg_0]
0x18036dfb6  mov     rcx, [rbp+string]; string
0x18036dfba  call    cs:__imp_WindowsDeleteString
0x18036dfc0  lea     rcx, [rbp+arg_10]
0x18036dfc4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18036dfc9  test    r14b, r14b
0x18036dfcc  jz      loc_18036E2AA
0x18036dfd2  mov     dword ptr [rbp+arg_10], r15d
0x18036dfd6  mov     rax, [rsi+20h]
0x18036dfda  mov     rcx, [rax]
0x18036dfdd  mov     rax, [rcx]
0x18036dfe0  lea     r9, [rbp+arg_10]
0x18036dfe4  mov     r14d, 4
0x18036dfea  mov     r8d, r14d
0x18036dfed  lea     rdx, ?PackageExecutionContext@TileStoreProperties@DataStoreCache@@3U?$DataStoreProperty@I@2@B; DataStoreCache::DataStoreProperty<uint> const DataStoreCache::TileStoreProperties::PackageExecutionContext
0x18036dff4  mov     rax, [rax+18h]
0x18036dff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18036dffd  test    al, al
0x18036dfff  jz      short loc_18036E016
0x18036e001  cmp     dword ptr [rbp+arg_10], 3
0x18036e005  jnz     short loc_18036E016
0x18036e007  mov     rcx, [rsi+8]
0x18036e00b  mov     dword ptr [rcx], 2
0x18036e011  jmp     loc_18036E2B1
0x18036e016  mov     rcx, [rsi+8]
0x18036e01a  movzx   eax, word ptr [rbp+arg_0+5]
0x18036e01e  test    bl, bl
0x18036e020  jz      short loc_18036E02D
0x18036e022  mov     dword ptr [rcx], 3
0x18036e028  jmp     loc_18036E2B5
0x18036e02d  mov     dword ptr [rcx], 1
0x18036e033  mov     byte ptr [rcx+4], 1
0x18036e037  mov     [rcx+5], ax
0x18036e03b  mov     al, byte ptr [rbp+arg_0+7]
0x18036e03e  mov     [rcx+7], al
0x18036e041  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShowSettingsUninstallForSparsePackages@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShowSettingsUninstallForSparsePackages@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShowSettingsUninstallForSparsePackages> `wil::Feature<__WilFeatureTraits_Feature_ShowSettingsUninstallForSparsePackages>::GetImpl(void)'::`2'::impl
0x18036e048  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShowSettingsUninstallForSparsePackages@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShowSettingsUninstallForSparsePackages>::__private_IsEnabled(void)
0x18036e04d  test    al, al
0x18036e04f  jz      loc_18036E0DB
0x18036e055  mov     [rbp+string], r15
0x18036e059  mov     rax, [rsi+20h]
0x18036e05d  mov     rdi, [rax]
0x18036e060  mov     rax, [rdi]
0x18036e063  mov     rbx, [rax+20h]
0x18036e067  lea     rcx, [rbp+string]
0x18036e06b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18036e070  lea     r8, [rbp+string]
0x18036e074  lea     rdx, ?PackageFullName@TileStoreProperties@DataStoreCache@@3U?$DataStoreProperty@PEAUHSTRING__@@@2@B; DataStoreCache::DataStoreProperty<HSTRING__ *> const DataStoreCache::TileStoreProperties::PackageFullName
0x18036e07b  mov     rcx, rdi
0x18036e07e  mov     rax, rbx
0x18036e081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18036e086  test    al, al
0x18036e088  jz      short loc_18036E0D2
0x18036e08a  mov     dword ptr [rbp+arg_0], r15d
0x18036e08e  lea     rcx, [rbp+string]; this
0x18036e092  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18036e097  mov     rcx, rax
0x18036e09a  xor     r9d, r9d
0x18036e09d  lea     r8, [rbp+arg_0]
0x18036e0a1  lea     edx, [r9+5]
0x18036e0a5  call    cs:__imp_GetPackagePathByFullName2
0x18036e0ab  cmp     eax, 7Ah ; 'z'
0x18036e0ae  jnz     short loc_18036E0D2
0x18036e0b0  cmp     dword ptr [rbp+arg_0], r15d
0x18036e0b4  jbe     short loc_18036E0D2
0x18036e0b6  mov     rcx, [rsi+8]
0x18036e0ba  mov     dword ptr [rcx], 2
0x18036e0c0  mov     byte ptr [rcx+4], 1
0x18036e0c4  movzx   eax, word ptr [rbp+arg_0+5]
0x18036e0c8  mov     [rcx+5], ax
0x18036e0cc  mov     al, byte ptr [rbp+arg_0+7]
0x18036e0cf  mov     [rcx+7], al
0x18036e0d2  lea     rcx, [rbp+string]
0x18036e0d6  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18036e0db  cmp     cs:?s_hasChecked@?1??GetDeviceFamily@Details@@YAKXZ@4_NA, r15b; bool `Details::GetDeviceFamily(void)'::`2'::s_hasChecked
0x18036e0e2  jnz     short loc_18036E109
0x18036e0e4  mov     dword ptr [rbp+arg_0], r15d
0x18036e0e8  xor     r8d, r8d
0x18036e0eb  lea     rdx, [rbp+arg_0]
0x18036e0ef  xor     ecx, ecx
0x18036e0f1  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18036e0f7  mov     eax, dword ptr [rbp+arg_0]
0x18036e0fa  mov     cs:?s_platform@?1??GetDeviceFamily@Details@@YAKXZ@4KA, eax; ulong `Details::GetDeviceFamily(void)'::`2'::s_platform
0x18036e100  mov     cs:?s_hasChecked@?1??GetDeviceFamily@Details@@YAKXZ@4_NA, 1; bool `Details::GetDeviceFamily(void)'::`2'::s_hasChecked
0x18036e107  jmp     short loc_18036E10F
0x18036e109  mov     eax, cs:?s_platform@?1??GetDeviceFamily@Details@@YAKXZ@4KA; ulong `Details::GetDeviceFamily(void)'::`2'::s_platform
0x18036e10f  add     eax, 0FFFFFFF2h
0x18036e112  test    eax, 0FFFFFFFDh
0x18036e117  jnz     loc_18036E2C3
0x18036e11d  mov     dword ptr [rbp+string], r15d
0x18036e121  mov     rax, [rsi+20h]
0x18036e125  mov     rcx, [rax]
0x18036e128  mov     rax, [rcx]
0x18036e12b  lea     r9, [rbp+string]
0x18036e12f  mov     r8d, r14d
0x18036e132  lea     rdx, ?PackageOrigin@TileStoreProperties@DataStoreCache@@3U?$DataStoreProperty@I@2@B; DataStoreCache::DataStoreProperty<uint> const DataStoreCache::TileStoreProperties::PackageOrigin
0x18036e139  mov     rax, [rax+18h]
0x18036e13d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18036e142  test    al, al
0x18036e144  jz      loc_18036E2C3
0x18036e14a  cmp     dword ptr [rbp+string], 2
0x18036e14e  jz      loc_18036E2AA
0x18036e154  cmp     dword ptr [rbp+string], 3
0x18036e158  jnz     loc_18036E2C3
0x18036e15e  mov     [rbp+var_28], r15
0x18036e162  mov     rax, [rsi+20h]
0x18036e166  mov     rdi, [rax]
0x18036e169  mov     rax, [rdi]
0x18036e16c  mov     rbx, [rax+20h]
0x18036e170  xor     ecx, ecx; string
0x18036e172  call    cs:__imp_WindowsDeleteString
0x18036e178  mov     [rbp+var_28], r15
0x18036e17c  lea     r8, [rbp+var_28]
0x18036e180  lea     rdx, ?PackageFullName@TileStoreProperties@DataStoreCache@@3U?$DataStoreProperty@PEAUHSTRING__@@@2@B; DataStoreCache::DataStoreProperty<HSTRING__ *> const DataStoreCache::TileStoreProperties::PackageFullName
0x18036e187  mov     rcx, rdi
0x18036e18a  mov     rax, rbx
0x18036e18d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18036e192  test    al, al
0x18036e194  jz      loc_18036E29E
0x18036e19a  mov     [rbp+var_20], r15
0x18036e19e  mov     rdx, [rsi]
0x18036e1a1  add     rdx, 98h
0x18036e1a8  lea     rcx, [rbp+SRWLock]
0x18036e1ac  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x18036e1b1  mov     rax, [rsi]
0x18036e1b4  mov     rbx, [rax+130h]
0x18036e1bb  mov     rdi, r15
0x18036e1be  test    rbx, rbx
0x18036e1c1  jz      short loc_18036E1E7
0x18036e1c3  mov     rax, [rbx]
0x18036e1c6  mov     rcx, rbx
0x18036e1c9  mov     rax, [rax+8]
0x18036e1cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18036e1d2  nop
0x18036e1d3  mov     [rbp+arg_0], r15
0x18036e1d7  mov     [rbp+var_20], rbx
0x18036e1db  lea     rcx, [rbp+arg_0]
0x18036e1df  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18036e1e4  mov     rdi, rbx
0x18036e1e7  mov     rcx, [rbp+SRWLock]; SRWLock
0x18036e1eb  test    rcx, rcx
0x18036e1ee  jz      short loc_18036E1F6
0x18036e1f0  call    cs:__imp_ReleaseSRWLockShared
0x18036e1f6  mov     [rbp+arg_18], r15
0x18036e1fa  test    rdi, rdi
0x18036e1fd  jz      loc_18036E28C
0x18036e203  mov     rax, [rdi]
0x18036e206  mov     rbx, [rax+0B0h]
0x18036e20d  lea     rcx, [rbp+arg_18]
0x18036e211  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18036e216  lea     r8, [rbp+arg_18]
0x18036e21a  mov     rdx, [rbp+var_28]
0x18036e21e  mov     rcx, rdi
0x18036e221  mov     rax, rbx
0x18036e224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18036e229  test    eax, eax
0x18036e22b  jns     short loc_18036E234
0x18036e22d  mov     edx, 40Ch
0x18036e232  jmp     short loc_18036E258
0x18036e234  mov     byte ptr [rbp+arg_0], r15b
0x18036e238  mov     rcx, [rbp+arg_18]
0x18036e23c  mov     rax, [rcx]
0x18036e23f  lea     rdx, [rbp+arg_0]
0x18036e243  mov     rax, [rax+0E0h]
0x18036e24a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18036e24f  test    eax, eax
0x18036e251  jns     short loc_18036E26D
0x18036e253  mov     edx, 40Fh; void *
0x18036e258  lea     r8, aShellcommonShe_151; "shellcommon\\shell\\datastorecache\\tra"...
0x18036e25f  mov     r9d, eax; char *
0x18036e262  mov     rcx, [rbp+30h]; this
0x18036e266  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18036e26b  jmp     short loc_18036E28C
0x18036e26d  cmp     byte ptr [rbp+arg_0], r15b
0x18036e271  jz      short loc_18036E28C
0x18036e273  mov     rcx, [rsi+8]
0x18036e277  mov     [rcx], r15d
0x18036e27a  mov     byte ptr [rcx+4], 1
0x18036e27e  movzx   eax, word ptr [rbp+arg_0+5]
0x18036e282  mov     [rcx+5], ax
0x18036e286  mov     al, byte ptr [rbp+arg_0+7]
0x18036e289  mov     [rcx+7], al
0x18036e28c  lea     rcx, [rbp+arg_18]
0x18036e290  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18036e295  lea     rcx, [rbp+var_20]
0x18036e299  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18036e29e  mov     rcx, [rbp+var_28]; string
0x18036e2a2  call    cs:__imp_WindowsDeleteString
0x18036e2a8  jmp     short loc_18036E2C3
0x18036e2aa  mov     rcx, [rsi+8]
0x18036e2ae  mov     [rcx], r15d
0x18036e2b1  movzx   eax, word ptr [rbp+arg_0+5]
0x18036e2b5  mov     byte ptr [rcx+4], 1
0x18036e2b9  mov     [rcx+5], ax
0x18036e2bd  mov     al, byte ptr [rbp+arg_0+7]
0x18036e2c0  mov     [rcx+7], al
0x18036e2c3  mov     rax, [rsi+8]
0x18036e2c7  cmp     [rax+4], r15b
0x18036e2cb  jz      short loc_18036E2DC
0x18036e2cd  mov     eax, [rax]
0x18036e2cf  add     rsp, 58h
0x18036e2d3  pop     r15
0x18036e2d5  pop     r14
0x18036e2d7  pop     rdi
0x18036e2d8  pop     rsi
0x18036e2d9  pop     rbx
0x18036e2da  pop     rbp
0x18036e2db  retn
0x18036e2dc  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
```
