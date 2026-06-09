# SystemSettings::StorageSenseHandlers::CAppTileData::GetIsUninstallableAndToolTipMsg(bool *,HSTRING__ * *)

- ea: `0x1800a7cd4`
- end: `0x1800a7f76`
- name: `?GetIsUninstallableAndToolTipMsg@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEA_NPEAPEAUHSTRING__@@@Z`
- size: `674`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppTileData *__hidden this, bool *, HSTRING *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800402fc`

## callees

- `0x18000c964`
- `0x18000e6cc`
- `0x1800a03d8`
- `0x1800a4aec`
- `0x1800a7cd4`
- `0x1800a8ee4`
- `0x1800aabcc`
- `0x1800ad354`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7d39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7e58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7ed0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7f55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7d39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7e58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7ed0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7f55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a7e85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a7e85`

## string_xrefs

- `0x1800a7d68`: `SystemSettings_Apps_Uninstall_OrgPolicy_ToolTipMsg`
- `0x1800a7ede`: `SystemSettings_Apps_Uninstall_WindowsPolicy_ToolTipMsg`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppTileData::GetIsUninstallableAndToolTipMsg(
        SystemSettings::StorageSenseHandlers::CAppTileData *this,
        bool *a2,
        HSTRING *a3)
{
  unsigned int v6; // ebx
  int PackageType; // edi
  SystemSettings::StorageSenseHandlers::CAppTileData *v9; // rcx
  int IsAUMIDUninstallable; // eax
  __int64 v11; // rdx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64 *); // rbx
  unsigned int v14; // r14d
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, __int64 *); // rbx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  const WCHAR *StringRawBuffer; // rax
  bool *v20; // r8
  SystemSettings::StorageSenseHandlers::CAppTileData *v21; // rcx
  __int64 v22; // [rsp+20h] [rbp-20h] BYREF
  __int64 v23; // [rsp+28h] [rbp-18h] BYREF
  HSTRING string[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  unsigned int v26; // [rsp+78h] [rbp+38h] BYREF
  __int64 v27; // [rsp+88h] [rbp+48h] BYREF

  if ( !a2 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x551,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
      (const char *)0x80070057LL,
      v22);
    return v6;
  }
  if ( *((_DWORD *)this + 12) )
  {
    *a2 = 1;
  }
  else
  {
    string[0] = 0;
    PackageType = SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageType(this);
    *a2 = 0;
    WindowsDeleteString(string[0]);
    string[0] = 0;
    if ( SystemSettings::StorageSenseHandlers::CAppTileData::GetAppId(this, string) < 0 )
    {
      *a2 = PackageType == 32;
      if ( PackageType != 32 )
      {
        LOBYTE(v9) = 0;
        SystemSettings::StorageSenseHandlers::CAppTileData::SetToolTipValue(
          v9,
          L"SystemSettings_Apps_Uninstall_OrgPolicy_ToolTipMsg",
          a3);
      }
LABEL_22:
      v6 = 0;
      goto LABEL_27;
    }
    v23 = 0;
    v27 = 0;
    v22 = 0;
    v26 = 0;
    IsAUMIDUninstallable = Microsoft::WRL::ComPtr<IInspectable>::As<SystemSettings::DataModel::StorageSense::IPackageInfo>(
                             (char *)this + 40,
                             &v23);
    v6 = IsAUMIDUninstallable;
    if ( IsAUMIDUninstallable < 0 )
    {
      v11 = 1392;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
        (const char *)(unsigned int)IsAUMIDUninstallable,
        v22);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v22);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v27);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v23);
LABEL_27:
      WindowsDeleteString(string[0]);
      return v6;
    }
    v12 = v23;
    v13 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 88LL);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v27);
    IsAUMIDUninstallable = v13(v12, &v27);
    v6 = IsAUMIDUninstallable;
    if ( IsAUMIDUninstallable < 0 )
    {
      v11 = 1393;
      goto LABEL_26;
    }
    IsAUMIDUninstallable = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v27 + 56LL))(v27, &v26);
    v6 = IsAUMIDUninstallable;
    if ( IsAUMIDUninstallable < 0 )
    {
      v11 = 1394;
      goto LABEL_26;
    }
    v14 = 0;
    if ( v26 )
    {
      while ( 1 )
      {
        v15 = v27;
        v16 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v27 + 48LL);
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v22);
        IsAUMIDUninstallable = v16(v15, v14, &v22);
        v6 = IsAUMIDUninstallable;
        if ( IsAUMIDUninstallable < 0 )
          break;
        v17 = v22;
        v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v22 + 72LL);
        WindowsDeleteString(string[0]);
        string[0] = 0;
        IsAUMIDUninstallable = v18(v17, string);
        v6 = IsAUMIDUninstallable;
        if ( IsAUMIDUninstallable < 0 )
        {
          v11 = 1399;
          goto LABEL_26;
        }
        StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
        IsAUMIDUninstallable = ShellBlockLists::IsAUMIDUninstallable(StringRawBuffer, (unsigned __int16 *)a2, v20);
        v6 = IsAUMIDUninstallable;
        if ( IsAUMIDUninstallable < 0 )
        {
          v11 = 1401;
          goto LABEL_26;
        }
        if ( !*a2 )
        {
          SystemSettings::StorageSenseHandlers::CAppTileData::SetToolTipValue(
            v21,
            L"SystemSettings_Apps_Uninstall_WindowsPolicy_ToolTipMsg",
            a3);
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v22);
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v27);
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v23);
          goto LABEL_22;
        }
        if ( ++v14 >= v26 )
          goto LABEL_20;
      }
      v11 = 1398;
      goto LABEL_26;
    }
LABEL_20:
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v22);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v27);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v23);
    WindowsDeleteString(string[0]);
  }
  return 0;
}

```

## disassembly

```asm
0x1800a7cd4  mov     [rsp-28h+arg_0], rbx
0x1800a7cd9  push    rbp
0x1800a7cda  push    rsi
0x1800a7cdb  push    rdi
0x1800a7cdc  push    r14
0x1800a7cde  push    r15
0x1800a7ce0  mov     rbp, rsp
0x1800a7ce3  sub     rsp, 40h
0x1800a7ce7  mov     r15, r8
0x1800a7cea  mov     rsi, rdx
0x1800a7ced  mov     rbx, rcx
0x1800a7cf0  test    rdx, rdx
0x1800a7cf3  jnz     short loc_1800A7D19
0x1800a7cf5  mov     rcx, [rbp+28h]; this
0x1800a7cf9  mov     ebx, 80070057h
0x1800a7cfe  mov     r9d, ebx; char *
0x1800a7d01  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a7d08  mov     edx, 551h; void *
0x1800a7d0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7d12  mov     eax, ebx
0x1800a7d14  jmp     loc_1800A7F65
0x1800a7d19  cmp     dword ptr [rcx+30h], 0
0x1800a7d1d  jnz     loc_1800A7F60
0x1800a7d23  mov     [rbp+string], 0
0x1800a7d2b  call    ?GetPackageType@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAA?AW4PackageType@StateRepository@Internal@Windows@@XZ; SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageType(void)
0x1800a7d30  mov     edi, eax
0x1800a7d32  mov     byte ptr [rsi], 0
0x1800a7d35  mov     rcx, [rbp+string]; string
0x1800a7d39  call    cs:__imp_WindowsDeleteString
0x1800a7d3f  mov     [rbp+string], 0
0x1800a7d47  lea     rdx, [rbp+string]; HSTRING *
0x1800a7d4b  mov     rcx, rbx; this
0x1800a7d4e  call    ?GetAppId@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetAppId(HSTRING__ * *)
0x1800a7d53  test    eax, eax
0x1800a7d55  jns     short loc_1800A7D79
0x1800a7d57  cmp     edi, 20h ; ' '
0x1800a7d5a  setz    cl; this
0x1800a7d5d  mov     [rsi], cl
0x1800a7d5f  jz      loc_1800A7F08
0x1800a7d65  mov     r8, r15; HSTRING *
0x1800a7d68  lea     rdx, aSystemsettings_178; "SystemSettings_Apps_Uninstall_OrgPolicy"...
0x1800a7d6f  call    ?SetToolTipValue@CAppTileData@StorageSenseHandlers@SystemSettings@@AEAAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::SetToolTipValue(ushort const *,HSTRING__ * *)
0x1800a7d74  jmp     loc_1800A7F08
0x1800a7d79  mov     [rbp+var_18], 0
0x1800a7d81  mov     [rbp+arg_18], 0
0x1800a7d89  mov     [rbp+var_20], 0
0x1800a7d91  mov     [rbp+arg_8], 0
0x1800a7d98  lea     rcx, [rbx+28h]
0x1800a7d9c  lea     rdx, [rbp+var_18]
0x1800a7da0  call    ??$As@UIPackageInfo@StorageSense@DataModel@SystemSettings@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPackageInfo@StorageSense@DataModel@SystemSettings@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<SystemSettings::DataModel::StorageSense::IPackageInfo>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SystemSettings::DataModel::StorageSense::IPackageInfo>>)
0x1800a7da5  mov     ebx, eax
0x1800a7da7  test    eax, eax
0x1800a7da9  jns     short loc_1800A7DB5
0x1800a7dab  mov     edx, 570h
0x1800a7db0  jmp     loc_1800A7F1F
0x1800a7db5  mov     rdi, [rbp+var_18]
0x1800a7db9  mov     rax, [rdi]
0x1800a7dbc  mov     rbx, [rax+58h]
0x1800a7dc0  lea     rcx, [rbp+arg_18]
0x1800a7dc4  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a7dc9  lea     rdx, [rbp+arg_18]
0x1800a7dcd  mov     rcx, rdi
0x1800a7dd0  mov     rax, rbx
0x1800a7dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7dd8  mov     ebx, eax
0x1800a7dda  test    eax, eax
0x1800a7ddc  jns     short loc_1800A7DE8
0x1800a7dde  mov     edx, 571h
0x1800a7de3  jmp     loc_1800A7F1F
0x1800a7de8  mov     rcx, [rbp+arg_18]
0x1800a7dec  mov     rax, [rcx]
0x1800a7def  lea     rdx, [rbp+arg_8]
0x1800a7df3  mov     rax, [rax+38h]
0x1800a7df7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7dfc  mov     ebx, eax
0x1800a7dfe  test    eax, eax
0x1800a7e00  jns     short loc_1800A7E0C
0x1800a7e02  mov     edx, 572h
0x1800a7e07  jmp     loc_1800A7F1F
0x1800a7e0c  xor     r14d, r14d
0x1800a7e0f  cmp     [rbp+arg_8], r14d
0x1800a7e13  jbe     loc_1800A7EAE
0x1800a7e19  mov     rdi, [rbp+arg_18]
0x1800a7e1d  mov     rax, [rdi]
0x1800a7e20  mov     rbx, [rax+30h]
0x1800a7e24  lea     rcx, [rbp+var_20]
0x1800a7e28  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a7e2d  lea     r8, [rbp+var_20]
0x1800a7e31  mov     edx, r14d
0x1800a7e34  mov     rcx, rdi
0x1800a7e37  mov     rax, rbx
0x1800a7e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7e3f  mov     ebx, eax
0x1800a7e41  test    eax, eax
0x1800a7e43  js      loc_1800A7F1A
0x1800a7e49  mov     rdi, [rbp+var_20]
0x1800a7e4d  mov     rax, [rdi]
0x1800a7e50  mov     rbx, [rax+48h]
0x1800a7e54  mov     rcx, [rbp+string]; string
0x1800a7e58  call    cs:__imp_WindowsDeleteString
0x1800a7e5e  mov     [rbp+string], 0
0x1800a7e66  lea     rdx, [rbp+string]
0x1800a7e6a  mov     rcx, rdi
0x1800a7e6d  mov     rax, rbx
0x1800a7e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7e75  mov     ebx, eax
0x1800a7e77  test    eax, eax
0x1800a7e79  js      loc_1800A7F13
0x1800a7e7f  xor     edx, edx; length
0x1800a7e81  mov     rcx, [rbp+string]; string
0x1800a7e85  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a7e8b  mov     rdx, rsi; unsigned __int16 *
0x1800a7e8e  mov     rcx, rax; lpString2
0x1800a7e91  call    ?IsAUMIDUninstallable@ShellBlockLists@@YAJPEBGPEA_N@Z; ShellBlockLists::IsAUMIDUninstallable(ushort const *,bool *)
0x1800a7e96  mov     ebx, eax
0x1800a7e98  test    eax, eax
0x1800a7e9a  js      short loc_1800A7F0C
0x1800a7e9c  cmp     byte ptr [rsi], 0
0x1800a7e9f  jz      short loc_1800A7EDB
0x1800a7ea1  inc     r14d
0x1800a7ea4  cmp     r14d, [rbp+arg_8]
0x1800a7ea8  jb      loc_1800A7E19
0x1800a7eae  lea     rcx, [rbp+var_20]
0x1800a7eb2  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a7eb7  nop
0x1800a7eb8  lea     rcx, [rbp+arg_18]
0x1800a7ebc  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a7ec1  nop
0x1800a7ec2  lea     rcx, [rbp+var_18]
0x1800a7ec6  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a7ecb  nop
0x1800a7ecc  mov     rcx, [rbp+string]; string
0x1800a7ed0  call    cs:__imp_WindowsDeleteString
0x1800a7ed6  jmp     loc_1800A7F63
0x1800a7edb  mov     r8, r15; HSTRING *
0x1800a7ede  lea     rdx, aSystemsettings_377; "SystemSettings_Apps_Uninstall_WindowsPo"...
0x1800a7ee5  call    ?SetToolTipValue@CAppTileData@StorageSenseHandlers@SystemSettings@@AEAAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::SetToolTipValue(ushort const *,HSTRING__ * *)
0x1800a7eea  nop
0x1800a7eeb  lea     rcx, [rbp+var_20]
0x1800a7eef  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a7ef4  nop
0x1800a7ef5  lea     rcx, [rbp+arg_18]
0x1800a7ef9  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a7efe  nop
0x1800a7eff  lea     rcx, [rbp+var_18]
0x1800a7f03  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a7f08  xor     ebx, ebx
0x1800a7f0a  jmp     short loc_1800A7F51
0x1800a7f0c  mov     edx, 579h
0x1800a7f11  jmp     short loc_1800A7F1F
0x1800a7f13  mov     edx, 577h
0x1800a7f18  jmp     short loc_1800A7F1F
0x1800a7f1a  mov     edx, 576h; void *
0x1800a7f1f  mov     r9d, eax; char *
0x1800a7f22  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a7f29  mov     rcx, [rbp+28h]; this
0x1800a7f2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7f32  nop
0x1800a7f33  lea     rcx, [rbp+var_20]
0x1800a7f37  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a7f3c  nop
0x1800a7f3d  lea     rcx, [rbp+arg_18]
0x1800a7f41  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a7f46  nop
0x1800a7f47  lea     rcx, [rbp+var_18]
0x1800a7f4b  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a7f50  nop
0x1800a7f51  mov     rcx, [rbp+string]; string
0x1800a7f55  call    cs:__imp_WindowsDeleteString
0x1800a7f5b  jmp     loc_1800A7D12
0x1800a7f60  mov     byte ptr [rdx], 1
0x1800a7f63  xor     eax, eax
0x1800a7f65  mov     rbx, [rsp+40h+arg_0]
0x1800a7f6a  add     rsp, 40h
0x1800a7f6e  pop     r15
0x1800a7f70  pop     r14
0x1800a7f72  pop     rdi
0x1800a7f73  pop     rsi
0x1800a7f74  pop     rbp
0x1800a7f75  retn
```
