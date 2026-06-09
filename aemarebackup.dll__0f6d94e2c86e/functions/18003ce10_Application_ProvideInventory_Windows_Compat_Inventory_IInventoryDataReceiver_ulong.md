# Application::ProvideInventory(Windows::Compat::Inventory::IInventoryDataReceiver *,ulong)

- ea: `0x18003ce10`
- end: `0x18003d5a9`
- name: `?ProvideInventory@Application@@UEAAJPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@K@Z`
- size: `1945`
- prototype: `__int64 __fastcall(Application *__hidden this, struct Windows::Compat::Inventory::IInventoryDataReceiver *, unsigned int)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x180006cec`
- `0x180011fcc`
- `0x1800134b8`
- `0x18001459c`
- `0x18001efb4`
- `0x180035b98`
- `0x1800374b0`
- `0x180037f08`
- `0x180039164`
- `0x18003ce10`
- `0x18004275c`
- `0x180042878`
- `0x1800443a8`
- `0x180044734`
- `0x18004c020`
- `0x1800ec010`

## string_xrefs

- `0x18003d25e`: `RootDirPath`
- `0x18003d0a2`: `MsiProductCode`
- `0x18003d0ec`: `MsiPackageCode`
- `0x18003d214`: `InstallDate`
- `0x18003d136`: `UninstallString`
- `0x18003d180`: `ArpRegistryKeyPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Application::ProvideInventory(
        Application *this,
        struct Windows::Compat::Inventory::IInventoryDataReceiver *a2,
        int a3)
{
  char *v6; // rdi
  void (__fastcall *v7)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const WCHAR *, _QWORD *); // rbx
  _QWORD *v8; // rax
  void (__fastcall *v9)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *); // rbx
  _QWORD *v10; // rax
  void (__fastcall *v11)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *); // rbx
  _QWORD *v12; // rax
  void (__fastcall *v13)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *); // rbx
  _QWORD *v14; // rax
  void (__fastcall *v15)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *); // rbx
  _QWORD *v16; // rax
  void (__fastcall *v17)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *); // rbx
  _QWORD *v18; // rax
  void (__fastcall *v19)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *); // rbx
  _QWORD *v20; // rax
  void (__fastcall *v21)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *); // rbx
  _QWORD *v22; // rax
  void (__fastcall *v23)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *); // rbx
  _QWORD *v24; // rax
  void (__fastcall *v25)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *); // rbx
  _QWORD *v26; // rax
  void (__fastcall *v27)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *); // rbx
  _QWORD *v28; // rax
  void (__fastcall *v29)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *); // rbx
  _QWORD *v30; // rax
  void (__fastcall *v31)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *); // rbx
  _QWORD *v32; // rax
  void (__fastcall *v33)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *); // rbx
  _QWORD *v34; // rax
  const wchar_t *v35; // r8
  File *v36; // rax
  unsigned __int16 *v37; // rdx
  bool v38; // zf
  __int64 (__fastcall *v39)(char *); // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 FilesFromCache; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  struct AppInfo2Impl *AppInfo2; // rbx
  __int64 v48; // rax
  const wchar_t *v49; // rbx
  __int64 v50; // rax
  File *v51; // [rsp+40h] [rbp-C0h]
  _BYTE v52[32]; // [rsp+48h] [rbp-B8h] BYREF
  char *Src[5]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v54; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v55[80]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v56; // [rsp+E8h] [rbp-18h]
  __int16 v57; // [rsp+F0h] [rbp-10h]
  __int64 v58; // [rsp+F8h] [rbp-8h]
  __int128 v59; // [rsp+100h] [rbp+0h]
  __int64 v60; // [rsp+110h] [rbp+10h]
  int v61; // [rsp+118h] [rbp+18h]
  char v62; // [rsp+11Ch] [rbp+1Ch]

  v6 = (char *)this + 8;
  if ( *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 1) + 16LL))((char *)this + 8) + 16)
    && *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6) + 16) )
  {
    if ( (a3 & 1) != 0 )
    {
      (**(void (__fastcall ***)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *))a2)(
        a2,
        L"InventoryApplication");
      v7 = *(void (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const WCHAR *, _QWORD *))(*(_QWORD *)a2 + 8LL);
      v8 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
      if ( v8[3] > 7u )
        v8 = (_QWORD *)*v8;
      v7(a2, L"ProgramId", v8);
      v9 = *(void (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *))(*(_QWORD *)a2 + 8LL);
      v10 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
      if ( v10[3] > 7u )
        v10 = (_QWORD *)*v10;
      v9(a2, L"Name", v10);
      v11 = *(void (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *))(*(_QWORD *)a2 + 8LL);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 120LL))(v6);
      v12 = (_QWORD *)Utility::FormatWstring(Src, (wchar_t *)L"%d");
      if ( v12[3] > 7u )
        v12 = (_QWORD *)*v12;
      v11(a2, L"Language", v12);
      std::wstring::~wstring(Src);
      if ( *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 80LL))(v6) + 16) )
      {
        v13 = *(void (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *))(*(_QWORD *)a2 + 8LL);
        v14 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 80LL))(v6);
        if ( v14[3] > 7u )
          v14 = (_QWORD *)*v14;
        v13(a2, L"ProgramInstanceId", v14);
      }
      if ( *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 24LL))(v6) + 16) )
      {
        v15 = *(void (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *))(*(_QWORD *)a2 + 8LL);
        v16 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 24LL))(v6);
        if ( v16[3] > 7u )
          v16 = (_QWORD *)*v16;
        v15(a2, L"Publisher", v16);
      }
      if ( *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 32LL))(v6) + 16) )
      {
        v17 = *(void (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *))(*(_QWORD *)a2 + 8LL);
        v18 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 32LL))(v6);
        if ( v18[3] > 7u )
          v18 = (_QWORD *)*v18;
        v17(a2, L"Version", v18);
      }
      if ( *((_QWORD *)this + 94) )
        (*(void (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *))(*(_QWORD *)a2 + 8LL))(
          a2,
          L"PackageFullName");
      if ( *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 96LL))(v6) + 16) )
      {
        v19 = *(void (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *))(*(_QWORD *)a2 + 8LL);
        v20 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 96LL))(v6);
        if ( v20[3] > 7u )
          v20 = (_QWORD *)*v20;
        v19(a2, L"MsiProductCode", v20);
      }
      if ( *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 104LL))(v6) + 16) )
      {
        v21 = *(void (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *))(*(_QWORD *)a2 + 8LL);
        v22 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 104LL))(v6);
        if ( v22[3] > 7u )
          v22 = (_QWORD *)*v22;
        v21(a2, L"MsiPackageCode", v22);
      }
      if ( *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 48LL))(v6) + 16) )
      {
        v23 = *(void (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *))(*(_QWORD *)a2 + 8LL);
        v24 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 48LL))(v6);
        if ( v24[3] > 7u )
          v24 = (_QWORD *)*v24;
        v23(a2, L"UninstallString", v24);
      }
      if ( *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 88LL))(v6) + 16) )
      {
        v25 = *(void (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *))(*(_QWORD *)a2 + 8LL);
        v26 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 88LL))(v6);
        if ( v26[3] > 7u )
          v26 = (_QWORD *)*v26;
        v25(a2, L"ArpRegistryKeyPath", v26);
      }
      if ( *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 64LL))(v6) + 16) )
      {
        v27 = *(void (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *))(*(_QWORD *)a2 + 8LL);
        v28 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 64LL))(v6);
        if ( v28[3] > 7u )
          v28 = (_QWORD *)*v28;
        v27(a2, L"Source", v28);
      }
      if ( *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 56LL))(v6) + 16) )
      {
        v29 = *(void (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *))(*(_QWORD *)a2 + 8LL);
        v30 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 56LL))(v6);
        if ( v30[3] > 7u )
          v30 = (_QWORD *)*v30;
        v29(a2, L"InstallDate", v30);
      }
      if ( *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 40LL))(v6) + 16) )
      {
        v31 = *(void (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *))(*(_QWORD *)a2 + 8LL);
        v32 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 40LL))(v6);
        if ( v32[3] > 7u )
          v32 = (_QWORD *)*v32;
        v31(a2, L"RootDirPath", v32);
      }
      if ( *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 72LL))(v6) + 16) )
      {
        v33 = *(void (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *))(*(_QWORD *)a2 + 8LL);
        v34 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 72LL))(v6);
        if ( v34[3] > 7u )
          v34 = (_QWORD *)*v34;
        v33(a2, L"AppType", v34);
      }
      v35 = L"true";
      if ( !*((_BYTE *)this + 692) )
        v35 = L"false";
      (*(void (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 8LL))(
        a2,
        L"HiddenArp",
        v35);
    }
    if ( (a3 & 0x10) != 0 )
    {
      (**(void (__fastcall ***)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *))a2)(
        a2,
        L"AppInfo");
      (*(void (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, unsigned __int64))(*(_QWORD *)a2 + 8LL))(
        a2,
        L"AppInfo",
        (unsigned __int64)v6 & -(__int64)(this != (Application *)8));
    }
    if ( (a3 & 0x41000000) != 0 )
    {
      if ( !*((_BYTE *)this + 993) && (a3 & 0x20000000) == 0 )
      {
        memset_0(v55, 0, 0x4Eu);
        v57 = 0;
        v58 = 0;
        v59 = 0;
        v60 = 0;
        v61 = 0;
        v62 = 0;
        v56 = 0;
        v54 = 0;
        v51 = (File *)operator new(0x330u);
        v36 = File::File(v51);
        v37 = (unsigned __int16 *)&File::FileCacheProviderName;
        if ( (unsigned __int64)qword_18011B968 > 7 )
          v37 = (unsigned __int16 *)File::FileCacheProviderName;
        if ( (int)TelCacheProvider::Initialize(
                    &v54,
                    v37,
                    ((unsigned __int64)v36 + 8) & -(__int64)(v36 != 0),
                    0,
                    1,
                    3u,
                    0x64u) >= 0 )
        {
          v38 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_Performance>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_Performance>::GetImpl'::`2'::impl) == 0;
          v39 = *(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL);
          if ( v38 )
          {
            v40 = v39(v6);
            v41 = std::wstring::wstring((__int64)v52, v40);
            FilesFromCache = File::GetFilesFromCache(Src, &v54, v41);
            Application::SetFiles((char *)this - 8, FilesFromCache);
          }
          else
          {
            v43 = v39(v6);
            v44 = std::wstring::wstring((__int64)v52, v43);
            v45 = File::GetFilesFromCache(Src, &v54, v44);
            Application::SetFiles2((char *)this - 8, v45);
            std::vector<File>::_Tidy(Src);
          }
        }
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v54);
      }
      AppInfo2 = Application::CreateAppInfo2((Application *)((char *)this - 8));
      if ( AppInfo2 )
      {
        if ( (a3 & 0x40000000) != 0 )
        {
          (**(void (__fastcall ***)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *))a2)(
            a2,
            L"AppInfo2");
          (*(void (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, __int64))(*(_QWORD *)a2 + 8LL))(
            a2,
            L"AppInfo2",
            (__int64)AppInfo2 + 8);
        }
        if ( (a3 & 0x1000000) != 0 )
        {
          (**(void (__fastcall ***)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *))a2)(
            a2,
            L"AppInfoEx");
          (*(void (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, __int64))(*(_QWORD *)a2 + 8LL))(
            a2,
            L"AppInfoEx",
            (__int64)AppInfo2 + 8);
        }
      }
      if ( AppInfo2 )
        (**(void (__fastcall ***)(struct AppInfo2Impl *, __int64))AppInfo2)(AppInfo2, 1);
    }
    return 0;
  }
  else
  {
    v48 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
    v49 = (const wchar_t *)v48;
    if ( *(_QWORD *)(v48 + 24) > 7u )
      v49 = *(const wchar_t **)v48;
    v50 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( *(_QWORD *)(v50 + 24) > 7u )
      v50 = *(_QWORD *)v50;
    AslLogCallPrintf(
      1,
      "Application::ProvideInventory",
      212,
      "Application missing required attribute! ProgramId:%ls Name:%ls [%#x]",
      (const wchar_t *)v50,
      v49,
      -2147467259);
    return 1;
  }
}

```

## disassembly

```asm
0x18003ce10  mov     [rsp-8+arg_10], rbx
0x18003ce15  mov     [rsp-8+arg_18], rsi
0x18003ce1a  push    rbp
0x18003ce1b  push    rdi
0x18003ce1c  push    r13
0x18003ce1e  push    r14
0x18003ce20  push    r15
0x18003ce22  lea     rbp, [rsp-30h]
0x18003ce27  sub     rsp, 130h
0x18003ce2e  mov     rax, cs:__security_cookie
0x18003ce35  xor     rax, rsp
0x18003ce38  mov     [rbp+50h+var_30], rax
0x18003ce3c  mov     r15d, r8d
0x18003ce3f  mov     rsi, rdx
0x18003ce42  mov     r14, rcx
0x18003ce45  lea     rdi, [rcx+8]
0x18003ce49  mov     rax, [rdi]
0x18003ce4c  mov     rcx, rdi
0x18003ce4f  mov     rax, [rax+10h]
0x18003ce53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce58  xor     r13d, r13d
0x18003ce5b  cmp     [rax+10h], r13
0x18003ce5f  jz      loc_18003D517
0x18003ce65  mov     rax, [rdi]
0x18003ce68  mov     rcx, rdi
0x18003ce6b  mov     rax, [rax+8]
0x18003ce6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce74  cmp     [rax+10h], r13
0x18003ce78  jz      loc_18003D517
0x18003ce7e  test    r15b, 1
0x18003ce82  jz      loc_18003D2E9
0x18003ce88  mov     rax, [rsi]
0x18003ce8b  lea     rdx, aInventoryappli; "InventoryApplication"
0x18003ce92  mov     rcx, rsi
0x18003ce95  mov     rax, [rax]
0x18003ce98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce9d  mov     rax, [rsi]
0x18003cea0  mov     rbx, [rax+8]
0x18003cea4  mov     rax, [rdi]
0x18003cea7  mov     rcx, rdi
0x18003ceaa  mov     rax, [rax+10h]
0x18003ceae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ceb3  cmp     qword ptr [rax+18h], 7
0x18003ceb8  jbe     short loc_18003CEBD
0x18003ceba  mov     rax, [rax]
0x18003cebd  mov     r8, rax
0x18003cec0  lea     rdx, aProgramid_0; "ProgramId"
0x18003cec7  mov     rcx, rsi
0x18003ceca  mov     rax, rbx
0x18003cecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ced2  mov     rax, [rsi]
0x18003ced5  mov     rbx, [rax+8]
0x18003ced9  mov     rax, [rdi]
0x18003cedc  mov     rcx, rdi
0x18003cedf  mov     rax, [rax+8]
0x18003cee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cee8  cmp     qword ptr [rax+18h], 7
0x18003ceed  jbe     short loc_18003CEF2
0x18003ceef  mov     rax, [rax]
0x18003cef2  mov     r8, rax
0x18003cef5  lea     rdx, aName; "Name"
0x18003cefc  mov     rcx, rsi
0x18003ceff  mov     rax, rbx
0x18003cf02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf07  mov     rax, [rsi]
0x18003cf0a  mov     rbx, [rax+8]
0x18003cf0e  mov     rax, [rdi]
0x18003cf11  mov     rcx, rdi
0x18003cf14  mov     rax, [rax+78h]
0x18003cf18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf1d  mov     r8d, eax
0x18003cf20  lea     rdx, aD; "%d"
0x18003cf27  lea     rcx, [rsp+150h+Src]; Src
0x18003cf2c  call    ?FormatWstring@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Utility::FormatWstring(ushort const *,...)
0x18003cf31  nop
0x18003cf32  cmp     qword ptr [rax+18h], 7
0x18003cf37  jbe     short loc_18003CF3C
0x18003cf39  mov     rax, [rax]
0x18003cf3c  mov     r8, rax
0x18003cf3f  lea     rdx, aLanguage; "Language"
0x18003cf46  mov     rcx, rsi
0x18003cf49  mov     rax, rbx
0x18003cf4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf51  nop
0x18003cf52  lea     rcx, [rsp+150h+Src]
0x18003cf57  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003cf5c  mov     rax, [rdi]
0x18003cf5f  mov     rcx, rdi
0x18003cf62  mov     rax, [rax+50h]
0x18003cf66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf6b  cmp     [rax+10h], r13
0x18003cf6f  jbe     short loc_18003CFA6
0x18003cf71  mov     rax, [rsi]
0x18003cf74  mov     rbx, [rax+8]
0x18003cf78  mov     rax, [rdi]
0x18003cf7b  mov     rcx, rdi
0x18003cf7e  mov     rax, [rax+50h]
0x18003cf82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf87  cmp     qword ptr [rax+18h], 7
0x18003cf8c  jbe     short loc_18003CF91
0x18003cf8e  mov     rax, [rax]
0x18003cf91  mov     r8, rax
0x18003cf94  lea     rdx, aPrograminstanc; "ProgramInstanceId"
0x18003cf9b  mov     rcx, rsi
0x18003cf9e  mov     rax, rbx
0x18003cfa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfa6  mov     rax, [rdi]
0x18003cfa9  mov     rcx, rdi
0x18003cfac  mov     rax, [rax+18h]
0x18003cfb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfb5  cmp     [rax+10h], r13
0x18003cfb9  jbe     short loc_18003CFF0
0x18003cfbb  mov     rax, [rsi]
0x18003cfbe  mov     rbx, [rax+8]
0x18003cfc2  mov     rax, [rdi]
0x18003cfc5  mov     rcx, rdi
0x18003cfc8  mov     rax, [rax+18h]
0x18003cfcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfd1  cmp     qword ptr [rax+18h], 7
0x18003cfd6  jbe     short loc_18003CFDB
0x18003cfd8  mov     rax, [rax]
0x18003cfdb  mov     r8, rax
0x18003cfde  lea     rdx, aPublisher; "Publisher"
0x18003cfe5  mov     rcx, rsi
0x18003cfe8  mov     rax, rbx
0x18003cfeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cff0  mov     rax, [rdi]
0x18003cff3  mov     rcx, rdi
0x18003cff6  mov     rax, [rax+20h]
0x18003cffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfff  cmp     [rax+10h], r13
0x18003d003  jbe     short loc_18003D03A
0x18003d005  mov     rax, [rsi]
0x18003d008  mov     rbx, [rax+8]
0x18003d00c  mov     rax, [rdi]
0x18003d00f  mov     rcx, rdi
0x18003d012  mov     rax, [rax+20h]
0x18003d016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d01b  cmp     qword ptr [rax+18h], 7
0x18003d020  jbe     short loc_18003D025
0x18003d022  mov     rax, [rax]
0x18003d025  mov     r8, rax
0x18003d028  lea     rdx, aVersion; "Version"
0x18003d02f  mov     rcx, rsi
0x18003d032  mov     rax, rbx
0x18003d035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d03a  cmp     [r14+2F0h], r13
0x18003d041  jbe     short loc_18003D06A
0x18003d043  mov     rax, [rsi]
0x18003d046  lea     r8, [r14+2E0h]
0x18003d04d  cmp     qword ptr [r8+18h], 7
0x18003d052  jbe     short loc_18003D057
0x18003d054  mov     r8, [r8]
0x18003d057  lea     rdx, aPackagefullnam; "PackageFullName"
0x18003d05e  mov     rcx, rsi
0x18003d061  mov     rax, [rax+8]
0x18003d065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d06a  mov     rax, [rdi]
0x18003d06d  mov     rcx, rdi
0x18003d070  mov     rax, [rax+60h]
0x18003d074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d079  cmp     [rax+10h], r13
0x18003d07d  jbe     short loc_18003D0B4
0x18003d07f  mov     rax, [rsi]
0x18003d082  mov     rbx, [rax+8]
0x18003d086  mov     rax, [rdi]
0x18003d089  mov     rcx, rdi
0x18003d08c  mov     rax, [rax+60h]
0x18003d090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d095  cmp     qword ptr [rax+18h], 7
0x18003d09a  jbe     short loc_18003D09F
0x18003d09c  mov     rax, [rax]
0x18003d09f  mov     r8, rax
0x18003d0a2  lea     rdx, aMsiproductcode; "MsiProductCode"
0x18003d0a9  mov     rcx, rsi
0x18003d0ac  mov     rax, rbx
0x18003d0af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0b4  mov     rax, [rdi]
0x18003d0b7  mov     rcx, rdi
0x18003d0ba  mov     rax, [rax+68h]
0x18003d0be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0c3  cmp     [rax+10h], r13
0x18003d0c7  jbe     short loc_18003D0FE
0x18003d0c9  mov     rax, [rsi]
0x18003d0cc  mov     rbx, [rax+8]
0x18003d0d0  mov     rax, [rdi]
0x18003d0d3  mov     rcx, rdi
0x18003d0d6  mov     rax, [rax+68h]
0x18003d0da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0df  cmp     qword ptr [rax+18h], 7
0x18003d0e4  jbe     short loc_18003D0E9
0x18003d0e6  mov     rax, [rax]
0x18003d0e9  mov     r8, rax
0x18003d0ec  lea     rdx, aMsipackagecode; "MsiPackageCode"
0x18003d0f3  mov     rcx, rsi
0x18003d0f6  mov     rax, rbx
0x18003d0f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0fe  mov     rax, [rdi]
0x18003d101  mov     rcx, rdi
0x18003d104  mov     rax, [rax+30h]
0x18003d108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d10d  cmp     [rax+10h], r13
0x18003d111  jbe     short loc_18003D148
0x18003d113  mov     rax, [rsi]
0x18003d116  mov     rbx, [rax+8]
0x18003d11a  mov     rax, [rdi]
0x18003d11d  mov     rcx, rdi
0x18003d120  mov     rax, [rax+30h]
0x18003d124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d129  cmp     qword ptr [rax+18h], 7
0x18003d12e  jbe     short loc_18003D133
0x18003d130  mov     rax, [rax]
0x18003d133  mov     r8, rax
0x18003d136  lea     rdx, aUninstallstrin; "UninstallString"
0x18003d13d  mov     rcx, rsi
0x18003d140  mov     rax, rbx
0x18003d143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d148  mov     rax, [rdi]
0x18003d14b  mov     rcx, rdi
0x18003d14e  mov     rax, [rax+58h]
0x18003d152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d157  cmp     [rax+10h], r13
0x18003d15b  jbe     short loc_18003D192
0x18003d15d  mov     rax, [rsi]
0x18003d160  mov     rbx, [rax+8]
0x18003d164  mov     rax, [rdi]
0x18003d167  mov     rcx, rdi
0x18003d16a  mov     rax, [rax+58h]
0x18003d16e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d173  cmp     qword ptr [rax+18h], 7
0x18003d178  jbe     short loc_18003D17D
0x18003d17a  mov     rax, [rax]
0x18003d17d  mov     r8, rax
0x18003d180  lea     rdx, aArpregistrykey; "ArpRegistryKeyPath"
0x18003d187  mov     rcx, rsi
0x18003d18a  mov     rax, rbx
0x18003d18d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d192  mov     rax, [rdi]
0x18003d195  mov     rcx, rdi
0x18003d198  mov     rax, [rax+40h]
0x18003d19c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1a1  cmp     [rax+10h], r13
0x18003d1a5  jbe     short loc_18003D1DC
0x18003d1a7  mov     rax, [rsi]
0x18003d1aa  mov     rbx, [rax+8]
0x18003d1ae  mov     rax, [rdi]
0x18003d1b1  mov     rcx, rdi
0x18003d1b4  mov     rax, [rax+40h]
0x18003d1b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1bd  cmp     qword ptr [rax+18h], 7
0x18003d1c2  jbe     short loc_18003D1C7
0x18003d1c4  mov     rax, [rax]
0x18003d1c7  mov     r8, rax
0x18003d1ca  lea     rdx, aSource; "Source"
0x18003d1d1  mov     rcx, rsi
0x18003d1d4  mov     rax, rbx
0x18003d1d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1dc  mov     rax, [rdi]
0x18003d1df  mov     rcx, rdi
0x18003d1e2  mov     rax, [rax+38h]
0x18003d1e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1eb  cmp     [rax+10h], r13
0x18003d1ef  jbe     short loc_18003D226
0x18003d1f1  mov     rax, [rsi]
0x18003d1f4  mov     rbx, [rax+8]
0x18003d1f8  mov     rax, [rdi]
0x18003d1fb  mov     rcx, rdi
0x18003d1fe  mov     rax, [rax+38h]
0x18003d202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d207  cmp     qword ptr [rax+18h], 7
0x18003d20c  jbe     short loc_18003D211
0x18003d20e  mov     rax, [rax]
0x18003d211  mov     r8, rax
0x18003d214  lea     rdx, aInstalldate; "InstallDate"
0x18003d21b  mov     rcx, rsi
0x18003d21e  mov     rax, rbx
0x18003d221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d226  mov     rax, [rdi]
0x18003d229  mov     rcx, rdi
0x18003d22c  mov     rax, [rax+28h]
0x18003d230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d235  cmp     [rax+10h], r13
0x18003d239  jbe     short loc_18003D270
0x18003d23b  mov     rax, [rsi]
0x18003d23e  mov     rbx, [rax+8]
0x18003d242  mov     rax, [rdi]
0x18003d245  mov     rcx, rdi
0x18003d248  mov     rax, [rax+28h]
0x18003d24c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d251  cmp     qword ptr [rax+18h], 7
0x18003d256  jbe     short loc_18003D25B
0x18003d258  mov     rax, [rax]
0x18003d25b  mov     r8, rax
0x18003d25e  lea     rdx, aRootdirpath; "RootDirPath"
0x18003d265  mov     rcx, rsi
0x18003d268  mov     rax, rbx
0x18003d26b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d270  mov     rax, [rdi]
0x18003d273  mov     rcx, rdi
0x18003d276  mov     rax, [rax+48h]
  ... truncated ...
```
