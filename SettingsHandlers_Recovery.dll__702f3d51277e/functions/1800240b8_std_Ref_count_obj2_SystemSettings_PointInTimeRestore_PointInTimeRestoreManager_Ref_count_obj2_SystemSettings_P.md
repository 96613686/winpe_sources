# std::_Ref_count_obj2<SystemSettings::PointInTimeRestore::PointInTimeRestoreManager>::_Ref_count_obj2<SystemSettings::PointInTimeRestore::PointInTimeRestoreManager>(void)

- ea: `0x1800240b8`
- end: `0x1800241fc`
- name: `??$?0$$V@?$_Ref_count_obj2@VPointInTimeRestoreManager@PointInTimeRestore@SystemSettings@@@std@@QEAA@XZ`
- size: `324`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180025c88`

## callees

- `0x180002350`
- `0x180009718`
- `0x1800240b8`
- `0x1800266dc`

## import_xrefs

- `ole32!CoGetObject` at `0x1800241b0`
- `ole32!CoGetObject` at `0x1800241b0`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180024147`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180024147`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x180024113`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x180024113`

## string_xrefs

- `0x1800241bd`: `Failed to create RecoveryAdminHelper instance as admin`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_obj2<SystemSettings::PointInTimeRestore::PointInTimeRestoreManager>::_Ref_count_obj2<SystemSettings::PointInTimeRestore::PointInTimeRestoreManager>(
        __int64 a1)
{
  void **v2; // rdi
  HWND ForegroundWindow; // rsi
  HRESULT Object; // eax
  const char *v6; // [rsp+28h] [rbp-D8h]
  BIND_OPTS pBindOptions[3]; // [rsp+38h] [rbp-C8h] BYREF
  OLECHAR sz[56]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszName[304]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+278h]

  *(_DWORD *)(a1 + 8) = 1;
  *(_DWORD *)(a1 + 12) = 1;
  *(_QWORD *)a1 = &std::_Ref_count_obj2<SystemSettings::PointInTimeRestore::PointInTimeRestoreManager>::`vftable';
  *(_QWORD *)(a1 + 16) = &SystemSettings::PointInTimeRestore::PointInTimeRestoreManager::`vftable';
  v2 = (void **)(a1 + 24);
  *(_QWORD *)(a1 + 24) = 0;
  ForegroundWindow = GetForegroundWindow();
  memset(pBindOptions, 0, sizeof(pBindOptions));
  *v2 = 0;
  if ( StringFromGUID2(&GUID_d93439d5_e434_441c_b701_8cd826ea6fb2, sz, 50) )
  {
    Object = StringCchPrintfW(pszName, 0x12Cu, L"Elevation:Administrator!new:%s", sz);
    if ( Object >= 0 )
    {
      *(_OWORD *)&pBindOptions[0].grfFlags = 0;
      *(_OWORD *)&pBindOptions[1].grfMode = 0;
      pBindOptions[0].cbStruct = 48;
      *(_QWORD *)&pBindOptions[2].grfMode = ForegroundWindow;
      pBindOptions[1].grfFlags = 4;
      Object = CoGetObject(pszName, pBindOptions, &GUID_57fc7410_6d82_46fb_bd12_2e858e77169a, v2);
    }
  }
  else
  {
    Object = -2147024882;
  }
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x14,
    (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\pointintimerestoremanager.cpp",
    (const char *)(unsigned int)Object,
    (int)"Failed to create RecoveryAdminHelper instance as admin",
    v6);
  return a1;
}

```

## disassembly

```asm
0x1800240b8  push    rbp
0x1800240ba  push    rbx
0x1800240bb  push    rsi
0x1800240bc  push    rdi
0x1800240bd  lea     rbp, [rsp-258h]
0x1800240c5  sub     rsp, 358h
0x1800240cc  mov     rax, cs:__security_cookie
0x1800240d3  xor     rax, rsp
0x1800240d6  mov     [rbp+270h+var_30], rax
0x1800240dd  mov     rbx, rcx
0x1800240e0  mov     eax, 1
0x1800240e5  mov     [rcx+8], eax
0x1800240e8  mov     [rcx+0Ch], eax
0x1800240eb  lea     rax, ??_7?$_Ref_count_obj2@VPointInTimeRestoreManager@PointInTimeRestore@SystemSettings@@@std@@6B@; const std::_Ref_count_obj2<SystemSettings::PointInTimeRestore::PointInTimeRestoreManager>::`vftable'
0x1800240f2  mov     [rcx], rax
0x1800240f5  lea     rax, [rcx+10h]
0x1800240f9  mov     [rsp+370h+var_340], rax
0x1800240fe  lea     rcx, ??_7PointInTimeRestoreManager@PointInTimeRestore@SystemSettings@@6B@; const SystemSettings::PointInTimeRestore::PointInTimeRestoreManager::`vftable'
0x180024105  mov     [rax], rcx
0x180024108  lea     rdi, [rax+8]
0x18002410c  mov     qword ptr [rdi], 0
0x180024113  call    cs:__imp_GetForegroundWindow
0x180024119  mov     rsi, rax
0x18002411c  xorps   xmm0, xmm0
0x18002411f  movups  xmmword ptr [rsp+370h+pBindOptions.cbStruct], xmm0
0x180024124  movups  [rsp+370h+var_328], xmm0
0x180024129  movups  [rsp+370h+var_318], xmm0
0x18002412e  mov     qword ptr [rdi], 0
0x180024135  mov     r8d, 32h ; '2'; cchMax
0x18002413b  lea     rdx, [rsp+370h+sz]; lpsz
0x180024140  lea     rcx, _GUID_d93439d5_e434_441c_b701_8cd826ea6fb2; rguid
0x180024147  call    cs:__imp_StringFromGUID2
0x18002414d  test    eax, eax
0x18002414f  jnz     short loc_180024158
0x180024151  mov     eax, 8007000Eh
0x180024156  jmp     short loc_1800241B6
0x180024158  lea     r9, [rsp+370h+sz]
0x18002415d  lea     r8, aElevationAdmin; "Elevation:Administrator!new:%s"
0x180024164  mov     edx, 12Ch; unsigned __int64
0x180024169  lea     rcx, [rbp+270h+pszName]; unsigned __int16 *
0x18002416d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180024172  test    eax, eax
0x180024174  js      short loc_1800241B6
0x180024176  xorps   xmm0, xmm0
0x180024179  movdqu  xmmword ptr [rsp+370h+pBindOptions.grfFlags], xmm0
0x18002417f  xorps   xmm1, xmm1
0x180024182  movdqu  [rsp+370h+var_328+8], xmm1
0x180024188  mov     [rsp+370h+pBindOptions.cbStruct], 30h ; '0'
0x180024190  mov     qword ptr [rsp+370h+var_318+8], rsi
0x180024195  mov     dword ptr [rsp+370h+var_328+4], 4
0x18002419d  mov     r9, rdi; ppv
0x1800241a0  lea     r8, _GUID_57fc7410_6d82_46fb_bd12_2e858e77169a; riid
0x1800241a7  lea     rdx, [rsp+370h+pBindOptions]; pBindOptions
0x1800241ac  lea     rcx, [rbp+270h+pszName]; pszName
0x1800241b0  call    cs:__imp_CoGetObject
0x1800241b6  mov     rcx, [rbp+278h]; this
0x1800241bd  lea     rdx, aFailedToCreate_14; "Failed to create RecoveryAdminHelper in"...
0x1800241c4  mov     qword ptr [rsp+370h+var_350], rdx; int
0x1800241c9  mov     r9d, eax; char *
0x1800241cc  lea     r8, aPcshellShellSy; "pcshell\\shell\\systemsettings\\recover"...
0x1800241d3  mov     edx, 14h; void *
0x1800241d8  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800241dd  nop
0x1800241de  mov     rax, rbx
0x1800241e1  mov     rcx, [rbp+270h+var_30]
0x1800241e8  xor     rcx, rsp; StackCookie
0x1800241eb  call    __security_check_cookie
0x1800241f0  add     rsp, 358h
0x1800241f7  pop     rdi
0x1800241f8  pop     rsi
0x1800241f9  pop     rbx
0x1800241fa  pop     rbp
0x1800241fb  retn
```
