# BackgroundColorRestoreHandler::SetSolidColor(wil::cloud_store_data<Windows::Data::Background::DesktopWallpaper> const &)

- ea: `0x1800a10c0`
- end: `0x1800a1249`
- name: `?SetSolidColor@BackgroundColorRestoreHandler@@AEAAXAEBV?$cloud_store_data@UDesktopWallpaper@Background@Data@Windows@@@wil@@@Z`
- size: `393`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a0b00`
- `0x1800a0fac`

## callees

- `0x18001649c`
- `0x18001a96c`
- `0x18001cfa4`
- `0x1800284d0`
- `0x180095d1c`
- `0x18009eb70`
- `0x1800a10c0`
- `0x1800a1e48`
- `0x18012d010`

## import_xrefs

- `OLE32!CoCreateInstance` at `0x1800a10fb`
- `OLE32!CoCreateInstance` at `0x1800a10fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall BackgroundColorRestoreHandler::SetSolidColor(__int64 a1, __int64 a2)
{
  HRESULT v3; // eax
  int v4; // ebx
  int v5; // eax
  int v6; // eax
  __int64 v7; // rdx
  HKEY v8; // rcx
  int v9; // eax
  int v10; // edx
  int v11; // r9d
  wil::details::in1diag3 *v12; // rcx
  int v14; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID v16; // [rsp+50h] [rbp+18h] BYREF

  v16 = 0;
  v3 = CoCreateInstance(&CLSID_DesktopWallpaper, 0, 4u, &GUID_b92b56a9_8b55_4e14_9a89_0199bbb6f93b, &v16);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundcolorrestorehandler.cpp",
      (const char *)(unsigned int)v3,
      v14);
  v4 = *(_DWORD *)(a2 + 8);
  v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v16 + 96LL))(v16, 0);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundcolorrestorehandler.cpp",
      (const char *)(unsigned int)v5,
      v14);
  v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v16 + 64LL))(
         v16,
         (unsigned __int8)v4 | (BYTE2(v4) << 16) | (BYTE1(v4) << 8));
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundcolorrestorehandler.cpp",
      (const char *)(unsigned int)v6,
      v14);
  LOBYTE(v7) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightV2RestoreHandler>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightV2RestoreHandler>::GetImpl'::`2'::impl,
    v7);
  v9 = SHRegSetBOOL(v8, L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Wallpapers", L"WallpaperRestored", 1);
  v12 = retaddr;
  if ( v9 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundcolorrestorehandler.cpp",
      (const char *)(unsigned int)v9,
      v14);
  if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
  {
    LOBYTE(v11) = *(_BYTE *)(a2 + 8);
    McTemplateU0zuuu_EventWriteTransfer(
      (_DWORD)v12,
      v10,
      (unsigned int)L"Restore",
      v11,
      *(_BYTE *)(a2 + 9),
      *(_BYTE *)(a2 + 10));
  }
  CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ColorActivity<unsigned short const (&)[13],unsigned char const &,unsigned char const &,unsigned char const &>(
    v12,
    a2 + 8,
    a2 + 9,
    a2 + 10);
  return wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(&v16);
}

```

## disassembly

```asm
0x1800a10c0  mov     r11, rsp
0x1800a10c3  mov     [r11+10h], rbx
0x1800a10c7  mov     [r11+20h], rsi
0x1800a10cb  mov     [r11+8], rcx
0x1800a10cf  push    rdi
0x1800a10d0  sub     rsp, 30h
0x1800a10d4  mov     rsi, rdx
0x1800a10d7  mov     qword ptr [r11+18h], 0
0x1800a10df  lea     rax, [r11+18h]
0x1800a10e3  mov     [r11-18h], rax
0x1800a10e7  lea     r9, _GUID_b92b56a9_8b55_4e14_9a89_0199bbb6f93b; riid
0x1800a10ee  xor     edx, edx; pUnkOuter
0x1800a10f0  lea     r8d, [rdx+4]; dwClsContext
0x1800a10f4  lea     rcx, CLSID_DesktopWallpaper; rclsid
0x1800a10fb  call    cs:__imp_CoCreateInstance
0x1800a1101  mov     rcx, [rsp+38h]; this
0x1800a1106  test    eax, eax
0x1800a1108  js      loc_1800A121F
0x1800a110e  lea     rdi, [rsi+8]
0x1800a1112  mov     ebx, [rdi]
0x1800a1114  mov     [rsp+38h+arg_0], ebx
0x1800a1118  mov     rcx, [rsp+38h+arg_10]
0x1800a111d  mov     rax, [rcx]
0x1800a1120  xor     edx, edx
0x1800a1122  mov     rax, [rax+60h]
0x1800a1126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a112b  mov     rcx, [rsp+38h]; this
0x1800a1130  test    eax, eax
0x1800a1132  js      loc_1800A1234
0x1800a1138  mov     rcx, [rsp+38h+arg_10]
0x1800a113d  mov     r8, [rcx]
0x1800a1140  movzx   edx, byte ptr [rsp+38h+arg_0+1]
0x1800a1145  shl     edx, 8
0x1800a1148  movzx   eax, byte ptr [rsp+38h+arg_0+2]
0x1800a114d  shl     eax, 10h
0x1800a1150  or      edx, eax
0x1800a1152  movzx   eax, bl
0x1800a1155  or      edx, eax
0x1800a1157  mov     rax, [r8+40h]
0x1800a115b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1160  mov     rcx, [rsp+38h]; this
0x1800a1165  test    eax, eax
0x1800a1167  js      loc_1800A120A
0x1800a116d  mov     dl, 1
0x1800a116f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightV2RestoreHandler@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightV2RestoreHandler@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightV2RestoreHandler> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightV2RestoreHandler>::GetImpl(void)'::`2'::impl
0x1800a1176  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightV2RestoreHandler@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightV2RestoreHandler>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800a117b  mov     r9d, 1; int
0x1800a1181  lea     r8, aWallpaperresto; "WallpaperRestored"
0x1800a1188  lea     rdx, aSoftwareMicros_24; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800a118f  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x1800a1194  mov     rcx, [rsp+38h]; this
0x1800a1199  test    eax, eax
0x1800a119b  jns     short loc_1800A11B1
0x1800a119d  mov     r9d, eax; char *
0x1800a11a0  lea     r8, aPcshellShellCl_19; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800a11a7  mov     edx, 3Bh ; ';'; void *
0x1800a11ac  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a11b1  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800a11b8  jz      short loc_1800A11DC
0x1800a11ba  lea     rbx, [rsi+9]
0x1800a11be  mov     al, [rsi+0Ah]
0x1800a11c1  mov     [rsp+38h+var_10], al
0x1800a11c5  mov     al, [rbx]
0x1800a11c7  mov     [rsp+38h+var_18], al
0x1800a11cb  mov     r9b, [rdi]
0x1800a11ce  lea     r8, aRestore; "Restore"
0x1800a11d5  call    McTemplateU0zuuu_EventWriteTransfer
0x1800a11da  jmp     short loc_1800A11E0
0x1800a11dc  lea     rbx, [rdi+1]
0x1800a11e0  lea     r9, [rdi+2]
0x1800a11e4  mov     r8, rbx
0x1800a11e7  mov     rdx, rdi
0x1800a11ea  call    ??$Background_ColorActivity@AEAY0N@$$CBGAEBEAEBEAEBE@BackgroundActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0N@$$CBGAEBE11@Z; CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ColorActivity<ushort const (&)[13],uchar const &,uchar const &,uchar const &>(ushort const (&)[13],uchar const &,uchar const &,uchar const &)
0x1800a11ef  nop
0x1800a11f0  lea     rcx, [rsp+38h+arg_10]
0x1800a11f5  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x1800a11fa  mov     rbx, [rsp+38h+arg_8]
0x1800a11ff  mov     rsi, [rsp+38h+arg_18]
0x1800a1204  add     rsp, 30h
0x1800a1208  pop     rdi
0x1800a1209  retn
0x1800a120a  mov     r9d, eax; char *
0x1800a120d  lea     r8, aPcshellShellCl_19; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800a1214  mov     edx, 38h ; '8'; void *
0x1800a1219  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a121f  mov     r9d, eax; char *
0x1800a1222  lea     r8, aPcshellShellCl_19; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800a1229  mov     edx, 34h ; '4'; void *
0x1800a122e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a1234  mov     r9d, eax; char *
0x1800a1237  lea     r8, aPcshellShellCl_19; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800a123e  mov     edx, 37h ; '7'; void *
0x1800a1243  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
