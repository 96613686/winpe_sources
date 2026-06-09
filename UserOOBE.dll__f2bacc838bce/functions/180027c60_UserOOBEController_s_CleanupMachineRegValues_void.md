# UserOOBEController::s_CleanupMachineRegValues(void)

- ea: `0x180027c60`
- end: `0x180027ef4`
- name: `?s_CleanupMachineRegValues@UserOOBEController@@CAXXZ`
- size: `660`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180024320`

## callees

- `0x1800039c0`
- `0x180003a28`
- `0x1800067b0`
- `0x18000e270`
- `0x18002668c`
- `0x1800279b8`
- `0x180027c60`
- `0x180047bd0`
- `0x18004e010`

## import_xrefs

- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180027ceb`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180027d1b`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180027ceb`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180027d1b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027de5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027de5`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryDWORD` at `0x180027d5e`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryDWORD` at `0x180027d5e`
- `api-ms-win-stateseparation-helpers-l1-1-1!DeletePersistedRegistryValue` at `0x180027c85`
- `api-ms-win-stateseparation-helpers-l1-1-1!DeletePersistedRegistryValue` at `0x180027c85`

## string_xrefs

- `0x180027caa`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180027cd3`: `OOBEUpdateStarted`
- `0x180027d0a`: `OOBEInProgressDriverUpdatesPostponed`
- `0x180027cda`: `SOFTWARE\Microsoft\Windows\CurrentVersion\OOBE\Updates`
- `0x180027e7b`: `OOBESystemProtected`
- `0x180027e89`: `SOFTWARE\Microsoft\Windows\CurrentVersion\OOBE\SystemProtected`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void UserOOBEController::s_CleanupMachineRegValues(void)
{
  unsigned int v0; // eax
  __int64 v1; // rdx
  unsigned int v2; // ebx
  unsigned int v3; // eax
  __int64 *v4; // rdi
  int v5; // eax
  unsigned int v6; // ebx
  HRESULT v7; // eax
  wil::details::in1diag3 *v8; // rcx
  __int64 v9; // rdx
  unsigned int ppv; // [rsp+20h] [rbp-38h]
  int ppva; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPVOID v13; // [rsp+60h] [rbp+8h] BYREF

  v0 = DeletePersistedRegistryValue(L"OOBE", L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE", L"LaunchUserOOBE");
  v2 = v0;
  if ( v0 )
    UnattendLogW(1, L"Deleting LaunchUserOOBE reg value failed [%d]", v0);
  if ( v2 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)v2,
      ppv);
  LOBYTE(v1) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NDUPOobeSeekerLifeSpan>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_Servicing_NDUPOobeSeekerLifeSpan>::GetImpl'::`2'::impl,
    v1);
  v3 = SHDeleteValueW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Updates",
         L"OOBEUpdateStarted");
  if ( v3 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x1AA,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)v3,
      ppv);
  SHDeleteValueW(HKEY_LOCAL_MACHINE, L"System\\Setup", L"OOBEInProgressDriverUpdatesPostponed");
  if ( dword_18006EA68 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18006EA68);
    if ( dword_18006EA68 == -1 )
    {
      qword_18006E420 = (__int64)L"OOBE";
      qword_18006E428 = (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE";
      qword_18006E430 = (__int64)L"DefaultAccountAction";
      dword_18006E438 = 2;
      qword_18006E440 = (__int64)L"OOBESystemProtected";
      qword_18006E448 = (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\SystemProtected";
      qword_18006E450 = (__int64)L"DisableCAD";
      dword_18006E458 = 0;
      qword_18006E460 = (__int64)L"Winlogon";
      qword_18006E468 = (__int64)L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon";
      qword_18006E470 = (__int64)L"DisableLockWorkstation";
      dword_18006E478 = 0;
      Init_thread_footer(&dword_18006EA68);
    }
  }
  v4 = &qword_18006E420;
  do
  {
    v5 = SetPersistedRegistryDWORD(*v4, v4[1], v4[2], *((unsigned int *)v4 + 6));
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( (v6 & 0x80000000) != 0 )
    {
      UnattendLogW(1, L"Setting machine reg value failed [hr=0x%08X]", v6);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1C1,
        (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
        (const char *)v6,
        ppv);
    }
    v4 += 4;
  }
  while ( v4 != (__int64 *)&__objectFactory__UserOOBEController_COM );
  v13 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
  v7 = CoCreateInstance(&CLSID_AuthUILastLoggedOnUsername, 0, 1u, &GUID_ae449c7f_1eba_4deb_9a62_1be3cb45010e, &v13);
  v8 = retaddr;
  if ( v7 < 0 )
  {
    v9 = 454;
LABEL_18:
    wil::details::in1diag3::_Log_Hr(
      v8,
      (void *)v9,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v7,
      ppva);
    goto LABEL_19;
  }
  v7 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v13 + 24LL))(v13, 0);
  v8 = retaddr;
  if ( v7 < 0 )
  {
    v9 = 456;
    goto LABEL_18;
  }
LABEL_19:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
}

```

## disassembly

```asm
0x180027c60  push    rbx
0x180027c62  push    rbp
0x180027c63  push    rdi
0x180027c64  push    r15
0x180027c66  sub     rsp, 38h
0x180027c6a  lea     r8, aLaunchuseroobe; "LaunchUserOOBE"
0x180027c71  lea     rdi, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180027c78  mov     rdx, rdi
0x180027c7b  lea     r15, aOobe_0; "OOBE"
0x180027c82  mov     rcx, r15
0x180027c85  call    cs:__imp_DeletePersistedRegistryValue
0x180027c8b  mov     ebx, eax
0x180027c8d  test    eax, eax
0x180027c8f  jz      short loc_180027CA5
0x180027c91  mov     r8d, eax
0x180027c94  lea     rdx, aDeletingLaunch; "Deleting LaunchUserOOBE reg value faile"...
0x180027c9b  mov     ecx, 1
0x180027ca0  call    UnattendLogW
0x180027ca5  mov     rcx, [rsp+58h]; this
0x180027caa  lea     rbp, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180027cb1  test    ebx, ebx
0x180027cb3  jz      short loc_180027CC5
0x180027cb5  mov     r9d, ebx; char *
0x180027cb8  mov     r8, rbp; unsigned int
0x180027cbb  mov     edx, 1A6h; void *
0x180027cc0  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180027cc5  mov     dl, 1
0x180027cc7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NDUPOobeSeekerLifeSpan@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NDUPOobeSeekerLifeSpan@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NDUPOobeSeekerLifeSpan> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NDUPOobeSeekerLifeSpan>::GetImpl(void)'::`2'::impl
0x180027cce  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NDUPOobeSeekerLifeSpan@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NDUPOobeSeekerLifeSpan>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180027cd3  lea     r8, aOobeupdatestar; "OOBEUpdateStarted"
0x180027cda  lea     rdx, aSoftwareMicros_27; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180027ce1  mov     rbx, 0FFFFFFFF80000002h
0x180027ce8  mov     rcx, rbx; hkey
0x180027ceb  call    cs:__imp_SHDeleteValueW
0x180027cf1  mov     rcx, [rsp+58h]; this
0x180027cf6  test    eax, eax
0x180027cf8  jz      short loc_180027D0A
0x180027cfa  mov     r9d, eax; char *
0x180027cfd  mov     r8, rbp; unsigned int
0x180027d00  mov     edx, 1AAh; void *
0x180027d05  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180027d0a  lea     r8, aOobeinprogress_0; "OOBEInProgressDriverUpdatesPostponed"
0x180027d11  lea     rdx, aSystemSetup; "System\\Setup"
0x180027d18  mov     rcx, rbx; hkey
0x180027d1b  call    cs:__imp_SHDeleteValueW
0x180027d21  mov     ecx, cs:_tls_index
0x180027d27  mov     rax, gs:58h
0x180027d30  mov     edx, 4
0x180027d35  mov     rax, [rax+rcx*8]
0x180027d39  mov     eax, [rdx+rax]
0x180027d3c  cmp     cs:dword_18006EA68, eax
0x180027d42  jg      loc_180027E3C
0x180027d48  lea     rdi, qword_18006E420
0x180027d4f  mov     r9d, [rdi+18h]
0x180027d53  mov     r8, [rdi+10h]
0x180027d57  mov     rdx, [rdi+8]
0x180027d5b  mov     rcx, [rdi]
0x180027d5e  call    cs:__imp_SetPersistedRegistryDWORD
0x180027d64  mov     ebx, eax
0x180027d66  test    eax, eax
0x180027d68  jle     short loc_180027D73
0x180027d6a  movzx   ebx, ax
0x180027d6d  or      ebx, 80070000h
0x180027d73  test    ebx, ebx
0x180027d75  jns     short loc_180027D8B
0x180027d77  mov     r8d, ebx
0x180027d7a  lea     rdx, aSettingMachine; "Setting machine reg value failed [hr=0x"...
0x180027d81  mov     ecx, 1
0x180027d86  call    UnattendLogW
0x180027d8b  mov     rcx, [rsp+58h]; this
0x180027d90  test    ebx, ebx
0x180027d92  jns     short loc_180027DA4
0x180027d94  mov     r9d, ebx; char *
0x180027d97  mov     r8, rbp; unsigned int
0x180027d9a  mov     edx, 1C1h; void *
0x180027d9f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027da4  add     rdi, 20h ; ' '
0x180027da8  lea     rax, ?__objectFactory__UserOOBEController_COM@@3UFactoryCache@Details@WRL@Microsoft@@A; Microsoft::WRL::Details::FactoryCache __objectFactory__UserOOBEController_COM
0x180027daf  cmp     rdi, rax
0x180027db2  jnz     short loc_180027D4F
0x180027db4  mov     [rsp+58h+arg_0], 0
0x180027dbd  lea     rcx, [rsp+58h+arg_0]
0x180027dc2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180027dc7  lea     rax, [rsp+58h+arg_0]
0x180027dcc  mov     qword ptr [rsp+58h+ppv], rax; int
0x180027dd1  lea     r9, _GUID_ae449c7f_1eba_4deb_9a62_1be3cb45010e; riid
0x180027dd8  xor     edx, edx; pUnkOuter
0x180027dda  lea     r8d, [rdx+1]; dwClsContext
0x180027dde  lea     rcx, CLSID_AuthUILastLoggedOnUsername; rclsid
0x180027de5  call    cs:__imp_CoCreateInstance
0x180027deb  mov     rcx, [rsp+58h]
0x180027df0  test    eax, eax
0x180027df2  jns     short loc_180027DFB
0x180027df4  mov     edx, 1C6h
0x180027df9  jmp     short loc_180027E1C
0x180027dfb  mov     rcx, [rsp+58h+arg_0]
0x180027e00  mov     rax, [rcx]
0x180027e03  xor     edx, edx
0x180027e05  mov     rax, [rax+18h]
0x180027e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e0e  mov     rcx, [rsp+58h]; this
0x180027e13  test    eax, eax
0x180027e15  jns     short loc_180027E28
0x180027e17  mov     edx, 1C8h; void *
0x180027e1c  mov     r9d, eax; char *
0x180027e1f  mov     r8, rbp; unsigned int
0x180027e22  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027e27  nop
0x180027e28  lea     rcx, [rsp+58h+arg_0]
0x180027e2d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180027e32  add     rsp, 38h
0x180027e36  pop     r15
0x180027e38  pop     rdi
0x180027e39  pop     rbp
0x180027e3a  pop     rbx
0x180027e3b  retn
0x180027e3c  lea     rcx, dword_18006EA68
0x180027e43  call    _Init_thread_header
0x180027e48  cmp     cs:dword_18006EA68, 0FFFFFFFFh
0x180027e4f  jnz     loc_180027D48
0x180027e55  mov     cs:qword_18006E420, r15
0x180027e5c  mov     cs:qword_18006E428, rdi
0x180027e63  lea     rax, aDefaultaccount; "DefaultAccountAction"
0x180027e6a  mov     cs:qword_18006E430, rax
0x180027e71  mov     cs:dword_18006E438, 2
0x180027e7b  lea     rax, aOobesystemprot; "OOBESystemProtected"
0x180027e82  mov     cs:qword_18006E440, rax
0x180027e89  lea     rax, aSoftwareMicros_33; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180027e90  mov     cs:qword_18006E448, rax
0x180027e97  lea     rax, aDisablecad; "DisableCAD"
0x180027e9e  mov     cs:qword_18006E450, rax
0x180027ea5  mov     cs:dword_18006E458, 0
0x180027eaf  lea     rax, aWinlogon; "Winlogon"
0x180027eb6  mov     cs:qword_18006E460, rax
0x180027ebd  lea     rax, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180027ec4  mov     cs:qword_18006E468, rax
0x180027ecb  lea     rax, aDisablelockwor; "DisableLockWorkstation"
0x180027ed2  mov     cs:qword_18006E470, rax
0x180027ed9  mov     cs:dword_18006E478, 0
0x180027ee3  lea     rcx, dword_18006EA68
0x180027eea  call    _Init_thread_footer
0x180027eef  jmp     loc_180027D48
```
