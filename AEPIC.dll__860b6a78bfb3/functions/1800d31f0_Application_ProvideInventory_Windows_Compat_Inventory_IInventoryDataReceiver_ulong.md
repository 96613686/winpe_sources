# Application::ProvideInventory(Windows::Compat::Inventory::IInventoryDataReceiver *,ulong)

- ea: `0x1800d31f0`
- end: `0x1800d397b`
- name: `?ProvideInventory@Application@@UEAAJPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@K@Z`
- size: `1931`
- prototype: `__int64 __fastcall(Application *__hidden this, struct Windows::Compat::Inventory::IInventoryDataReceiver *, unsigned int)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001f378`

## callees

- `0x180005890`
- `0x180006040`
- `0x180006938`
- `0x18000faac`
- `0x18001084c`
- `0x180015cf0`
- `0x18001c5f0`
- `0x1800224dc`
- `0x180022544`
- `0x1800295dc`
- `0x1800c2d74`
- `0x1800c312c`
- `0x1800c48b4`
- `0x1800ca928`
- `0x1800d1424`
- `0x1800d31f0`
- `0x1800d52f0`
- `0x1800d5338`
- `0x1800eb010`

## string_xrefs

- `0x1800d34cc`: `MsiPackageCode`
- `0x1800d3482`: `MsiProductCode`
- `0x1800d35f4`: `InstallDate`
- `0x1800d363e`: `RootDirPath`
- `0x1800d3516`: `UninstallString`
- `0x1800d3560`: `ArpRegistryKeyPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Application::ProvideInventory(
        Application *this,
        struct Windows::Compat::Inventory::IInventoryDataReceiver *a2,
        int a3)
{
  char *v6; // rdi
  void (__fastcall *v7)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *); // rbx
  _QWORD *v8; // rax
  void (__fastcall *v9)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *); // rbx
  _QWORD *v10; // rax
  void (__fastcall *v11)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const WCHAR *, _QWORD *); // rbx
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
  const unsigned __int16 *v37; // rdx
  bool v38; // zf
  __int64 (__fastcall *v39)(char *); // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 FilesFromCache; // rax
  File *AppInfo2; // rbx
  __int64 v47; // rax
  const wchar_t *v48; // rbx
  __int64 v49; // rax
  File *v50; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v51[32]; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t Buffer[20]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v53; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v54[80]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v55; // [rsp+E8h] [rbp-18h]
  __int16 v56; // [rsp+F0h] [rbp-10h]
  __int64 v57; // [rsp+F8h] [rbp-8h]
  __int128 v58; // [rsp+100h] [rbp+0h]
  __int64 v59; // [rsp+110h] [rbp+10h]
  int v60; // [rsp+118h] [rbp+18h]
  char v61; // [rsp+11Ch] [rbp+1Ch]

  v6 = (char *)this + 8;
  if ( *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 1) + 16LL))((char *)this + 8) + 16)
    && *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6) + 16) )
  {
    if ( (a3 & 1) != 0 )
    {
      (**(void (__fastcall ***)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *))a2)(
        a2,
        L"InventoryApplication");
      v7 = *(void (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *))(*(_QWORD *)a2 + 8LL);
      v8 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
      if ( v8[3] > 7u )
        v8 = (_QWORD *)*v8;
      v7(a2, L"ProgramId", v8);
      v9 = *(void (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *, _QWORD *))(*(_QWORD *)a2 + 8LL);
      v10 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
      if ( v10[3] > 7u )
        v10 = (_QWORD *)*v10;
      v9(a2, L"Name", v10);
      v11 = *(void (__fastcall **)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const WCHAR *, _QWORD *))(*(_QWORD *)a2 + 8LL);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 120LL))(v6);
      v12 = (_QWORD *)Utility::FormatWstring(Buffer, (wchar_t *)L"%d");
      if ( v12[3] > 7u )
        v12 = (_QWORD *)*v12;
      v11(a2, L"Language", v12);
      std::wstring::_Tidy_deallocate(Buffer);
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
        memset_0(v54, 0, 0x4Eu);
        v56 = 0;
        v57 = 0;
        v58 = 0;
        v59 = 0;
        v60 = 0;
        v61 = 0;
        v55 = 0;
        v53 = 0;
        v50 = (File *)operator new(0x330u);
        v36 = File::File(v50);
        v37 = (const unsigned __int16 *)&File::FileCacheProviderName;
        if ( (unsigned __int64)qword_180121AA8 > 7 )
          v37 = (const unsigned __int16 *)File::FileCacheProviderName;
        if ( (int)TelCacheProvider::Initialize(
                    &v53,
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
            v41 = std::wstring::wstring(v51, v40);
            File::GetFilesFromCache(Buffer, &v53, v41);
            Application::SetFiles((Application *)((char *)this - 8));
          }
          else
          {
            v42 = v39(v6);
            v43 = std::wstring::wstring(v51, v42);
            FilesFromCache = File::GetFilesFromCache(Buffer, &v53, v43);
            Application::SetFiles2((char *)this - 8, FilesFromCache);
            std::vector<File>::_Tidy(Buffer);
          }
        }
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v53);
      }
      AppInfo2 = Application::CreateAppInfo2((Application *)((char *)this - 8));
      v50 = AppInfo2;
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
      std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(&v50);
    }
    return 0;
  }
  else
  {
    v47 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
    v48 = (const wchar_t *)v47;
    if ( *(_QWORD *)(v47 + 24) > 7u )
      v48 = *(const wchar_t **)v47;
    v49 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( *(_QWORD *)(v49 + 24) > 7u )
      v49 = *(_QWORD *)v49;
    AslLogCallPrintf(
      1,
      "Application::ProvideInventory",
      212,
      "Application missing required attribute! ProgramId:%ls Name:%ls [%#x]",
      (const wchar_t *)v49,
      v48,
      -2147467259);
    return 1;
  }
}

```

## disassembly

```asm
0x1800d31f0  mov     [rsp-8+arg_10], rbx
0x1800d31f5  mov     [rsp-8+arg_18], rsi
0x1800d31fa  push    rbp
0x1800d31fb  push    rdi
0x1800d31fc  push    r12
0x1800d31fe  push    r14
0x1800d3200  push    r15
0x1800d3202  lea     rbp, [rsp-30h]
0x1800d3207  sub     rsp, 130h
0x1800d320e  mov     rax, cs:__security_cookie
0x1800d3215  xor     rax, rsp
0x1800d3218  mov     [rbp+50h+var_30], rax
0x1800d321c  mov     r15d, r8d
0x1800d321f  mov     rsi, rdx
0x1800d3222  mov     r14, rcx
0x1800d3225  lea     rdi, [rcx+8]
0x1800d3229  mov     rax, [rdi]
0x1800d322c  mov     rcx, rdi
0x1800d322f  mov     rax, [rax+10h]
0x1800d3233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3238  xor     r12d, r12d
0x1800d323b  cmp     [rax+10h], r12
0x1800d323f  jz      loc_1800D38E9
0x1800d3245  mov     rax, [rdi]
0x1800d3248  mov     rcx, rdi
0x1800d324b  mov     rax, [rax+8]
0x1800d324f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3254  cmp     [rax+10h], r12
0x1800d3258  jz      loc_1800D38E9
0x1800d325e  test    r15b, 1
0x1800d3262  jz      loc_1800D36C9
0x1800d3268  mov     rax, [rsi]
0x1800d326b  lea     rdx, aInventoryappli; "InventoryApplication"
0x1800d3272  mov     rcx, rsi
0x1800d3275  mov     rax, [rax]
0x1800d3278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d327d  mov     rax, [rsi]
0x1800d3280  mov     rbx, [rax+8]
0x1800d3284  mov     rax, [rdi]
0x1800d3287  mov     rcx, rdi
0x1800d328a  mov     rax, [rax+10h]
0x1800d328e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3293  cmp     qword ptr [rax+18h], 7
0x1800d3298  jbe     short loc_1800D329D
0x1800d329a  mov     rax, [rax]
0x1800d329d  mov     r8, rax
0x1800d32a0  lea     rdx, aProgramid; "ProgramId"
0x1800d32a7  mov     rcx, rsi
0x1800d32aa  mov     rax, rbx
0x1800d32ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d32b2  mov     rax, [rsi]
0x1800d32b5  mov     rbx, [rax+8]
0x1800d32b9  mov     rax, [rdi]
0x1800d32bc  mov     rcx, rdi
0x1800d32bf  mov     rax, [rax+8]
0x1800d32c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d32c8  cmp     qword ptr [rax+18h], 7
0x1800d32cd  jbe     short loc_1800D32D2
0x1800d32cf  mov     rax, [rax]
0x1800d32d2  mov     r8, rax
0x1800d32d5  lea     rdx, aName; "Name"
0x1800d32dc  mov     rcx, rsi
0x1800d32df  mov     rax, rbx
0x1800d32e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d32e7  mov     rax, [rsi]
0x1800d32ea  mov     rbx, [rax+8]
0x1800d32ee  mov     rax, [rdi]
0x1800d32f1  mov     rcx, rdi
0x1800d32f4  mov     rax, [rax+78h]
0x1800d32f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d32fd  mov     r8d, eax
0x1800d3300  lea     rdx, aD; "%d"
0x1800d3307  lea     rcx, [rsp+150h+Buffer]; Buffer
0x1800d330c  call    ?FormatWstring@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Utility::FormatWstring(ushort const *,...)
0x1800d3311  nop
0x1800d3312  cmp     qword ptr [rax+18h], 7
0x1800d3317  jbe     short loc_1800D331C
0x1800d3319  mov     rax, [rax]
0x1800d331c  mov     r8, rax
0x1800d331f  lea     rdx, aLanguage; "Language"
0x1800d3326  mov     rcx, rsi
0x1800d3329  mov     rax, rbx
0x1800d332c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3331  nop
0x1800d3332  lea     rcx, [rsp+150h+Buffer]
0x1800d3337  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d333c  mov     rax, [rdi]
0x1800d333f  mov     rcx, rdi
0x1800d3342  mov     rax, [rax+50h]
0x1800d3346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d334b  cmp     [rax+10h], r12
0x1800d334f  jbe     short loc_1800D3386
0x1800d3351  mov     rax, [rsi]
0x1800d3354  mov     rbx, [rax+8]
0x1800d3358  mov     rax, [rdi]
0x1800d335b  mov     rcx, rdi
0x1800d335e  mov     rax, [rax+50h]
0x1800d3362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3367  cmp     qword ptr [rax+18h], 7
0x1800d336c  jbe     short loc_1800D3371
0x1800d336e  mov     rax, [rax]
0x1800d3371  mov     r8, rax
0x1800d3374  lea     rdx, aPrograminstanc; "ProgramInstanceId"
0x1800d337b  mov     rcx, rsi
0x1800d337e  mov     rax, rbx
0x1800d3381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3386  mov     rax, [rdi]
0x1800d3389  mov     rcx, rdi
0x1800d338c  mov     rax, [rax+18h]
0x1800d3390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3395  cmp     [rax+10h], r12
0x1800d3399  jbe     short loc_1800D33D0
0x1800d339b  mov     rax, [rsi]
0x1800d339e  mov     rbx, [rax+8]
0x1800d33a2  mov     rax, [rdi]
0x1800d33a5  mov     rcx, rdi
0x1800d33a8  mov     rax, [rax+18h]
0x1800d33ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d33b1  cmp     qword ptr [rax+18h], 7
0x1800d33b6  jbe     short loc_1800D33BB
0x1800d33b8  mov     rax, [rax]
0x1800d33bb  mov     r8, rax
0x1800d33be  lea     rdx, aPublisher; "Publisher"
0x1800d33c5  mov     rcx, rsi
0x1800d33c8  mov     rax, rbx
0x1800d33cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d33d0  mov     rax, [rdi]
0x1800d33d3  mov     rcx, rdi
0x1800d33d6  mov     rax, [rax+20h]
0x1800d33da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d33df  cmp     [rax+10h], r12
0x1800d33e3  jbe     short loc_1800D341A
0x1800d33e5  mov     rax, [rsi]
0x1800d33e8  mov     rbx, [rax+8]
0x1800d33ec  mov     rax, [rdi]
0x1800d33ef  mov     rcx, rdi
0x1800d33f2  mov     rax, [rax+20h]
0x1800d33f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d33fb  cmp     qword ptr [rax+18h], 7
0x1800d3400  jbe     short loc_1800D3405
0x1800d3402  mov     rax, [rax]
0x1800d3405  mov     r8, rax
0x1800d3408  lea     rdx, aVersion; "Version"
0x1800d340f  mov     rcx, rsi
0x1800d3412  mov     rax, rbx
0x1800d3415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d341a  cmp     [r14+2F0h], r12
0x1800d3421  jbe     short loc_1800D344A
0x1800d3423  mov     rax, [rsi]
0x1800d3426  lea     r8, [r14+2E0h]
0x1800d342d  cmp     qword ptr [r8+18h], 7
0x1800d3432  jbe     short loc_1800D3437
0x1800d3434  mov     r8, [r8]
0x1800d3437  lea     rdx, aPackagefullnam; "PackageFullName"
0x1800d343e  mov     rcx, rsi
0x1800d3441  mov     rax, [rax+8]
0x1800d3445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d344a  mov     rax, [rdi]
0x1800d344d  mov     rcx, rdi
0x1800d3450  mov     rax, [rax+60h]
0x1800d3454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3459  cmp     [rax+10h], r12
0x1800d345d  jbe     short loc_1800D3494
0x1800d345f  mov     rax, [rsi]
0x1800d3462  mov     rbx, [rax+8]
0x1800d3466  mov     rax, [rdi]
0x1800d3469  mov     rcx, rdi
0x1800d346c  mov     rax, [rax+60h]
0x1800d3470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3475  cmp     qword ptr [rax+18h], 7
0x1800d347a  jbe     short loc_1800D347F
0x1800d347c  mov     rax, [rax]
0x1800d347f  mov     r8, rax
0x1800d3482  lea     rdx, aMsiproductcode; "MsiProductCode"
0x1800d3489  mov     rcx, rsi
0x1800d348c  mov     rax, rbx
0x1800d348f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3494  mov     rax, [rdi]
0x1800d3497  mov     rcx, rdi
0x1800d349a  mov     rax, [rax+68h]
0x1800d349e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d34a3  cmp     [rax+10h], r12
0x1800d34a7  jbe     short loc_1800D34DE
0x1800d34a9  mov     rax, [rsi]
0x1800d34ac  mov     rbx, [rax+8]
0x1800d34b0  mov     rax, [rdi]
0x1800d34b3  mov     rcx, rdi
0x1800d34b6  mov     rax, [rax+68h]
0x1800d34ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d34bf  cmp     qword ptr [rax+18h], 7
0x1800d34c4  jbe     short loc_1800D34C9
0x1800d34c6  mov     rax, [rax]
0x1800d34c9  mov     r8, rax
0x1800d34cc  lea     rdx, aMsipackagecode; "MsiPackageCode"
0x1800d34d3  mov     rcx, rsi
0x1800d34d6  mov     rax, rbx
0x1800d34d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d34de  mov     rax, [rdi]
0x1800d34e1  mov     rcx, rdi
0x1800d34e4  mov     rax, [rax+30h]
0x1800d34e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d34ed  cmp     [rax+10h], r12
0x1800d34f1  jbe     short loc_1800D3528
0x1800d34f3  mov     rax, [rsi]
0x1800d34f6  mov     rbx, [rax+8]
0x1800d34fa  mov     rax, [rdi]
0x1800d34fd  mov     rcx, rdi
0x1800d3500  mov     rax, [rax+30h]
0x1800d3504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3509  cmp     qword ptr [rax+18h], 7
0x1800d350e  jbe     short loc_1800D3513
0x1800d3510  mov     rax, [rax]
0x1800d3513  mov     r8, rax
0x1800d3516  lea     rdx, aUninstallstrin; "UninstallString"
0x1800d351d  mov     rcx, rsi
0x1800d3520  mov     rax, rbx
0x1800d3523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3528  mov     rax, [rdi]
0x1800d352b  mov     rcx, rdi
0x1800d352e  mov     rax, [rax+58h]
0x1800d3532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3537  cmp     [rax+10h], r12
0x1800d353b  jbe     short loc_1800D3572
0x1800d353d  mov     rax, [rsi]
0x1800d3540  mov     rbx, [rax+8]
0x1800d3544  mov     rax, [rdi]
0x1800d3547  mov     rcx, rdi
0x1800d354a  mov     rax, [rax+58h]
0x1800d354e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3553  cmp     qword ptr [rax+18h], 7
0x1800d3558  jbe     short loc_1800D355D
0x1800d355a  mov     rax, [rax]
0x1800d355d  mov     r8, rax
0x1800d3560  lea     rdx, aArpregistrykey; "ArpRegistryKeyPath"
0x1800d3567  mov     rcx, rsi
0x1800d356a  mov     rax, rbx
0x1800d356d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3572  mov     rax, [rdi]
0x1800d3575  mov     rcx, rdi
0x1800d3578  mov     rax, [rax+40h]
0x1800d357c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3581  cmp     [rax+10h], r12
0x1800d3585  jbe     short loc_1800D35BC
0x1800d3587  mov     rax, [rsi]
0x1800d358a  mov     rbx, [rax+8]
0x1800d358e  mov     rax, [rdi]
0x1800d3591  mov     rcx, rdi
0x1800d3594  mov     rax, [rax+40h]
0x1800d3598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d359d  cmp     qword ptr [rax+18h], 7
0x1800d35a2  jbe     short loc_1800D35A7
0x1800d35a4  mov     rax, [rax]
0x1800d35a7  mov     r8, rax
0x1800d35aa  lea     rdx, aSource; "Source"
0x1800d35b1  mov     rcx, rsi
0x1800d35b4  mov     rax, rbx
0x1800d35b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d35bc  mov     rax, [rdi]
0x1800d35bf  mov     rcx, rdi
0x1800d35c2  mov     rax, [rax+38h]
0x1800d35c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d35cb  cmp     [rax+10h], r12
0x1800d35cf  jbe     short loc_1800D3606
0x1800d35d1  mov     rax, [rsi]
0x1800d35d4  mov     rbx, [rax+8]
0x1800d35d8  mov     rax, [rdi]
0x1800d35db  mov     rcx, rdi
0x1800d35de  mov     rax, [rax+38h]
0x1800d35e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d35e7  cmp     qword ptr [rax+18h], 7
0x1800d35ec  jbe     short loc_1800D35F1
0x1800d35ee  mov     rax, [rax]
0x1800d35f1  mov     r8, rax
0x1800d35f4  lea     rdx, aInstalldate; "InstallDate"
0x1800d35fb  mov     rcx, rsi
0x1800d35fe  mov     rax, rbx
0x1800d3601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3606  mov     rax, [rdi]
0x1800d3609  mov     rcx, rdi
0x1800d360c  mov     rax, [rax+28h]
0x1800d3610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3615  cmp     [rax+10h], r12
0x1800d3619  jbe     short loc_1800D3650
0x1800d361b  mov     rax, [rsi]
0x1800d361e  mov     rbx, [rax+8]
0x1800d3622  mov     rax, [rdi]
0x1800d3625  mov     rcx, rdi
0x1800d3628  mov     rax, [rax+28h]
0x1800d362c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3631  cmp     qword ptr [rax+18h], 7
0x1800d3636  jbe     short loc_1800D363B
0x1800d3638  mov     rax, [rax]
0x1800d363b  mov     r8, rax
0x1800d363e  lea     rdx, aRootdirpath; "RootDirPath"
0x1800d3645  mov     rcx, rsi
0x1800d3648  mov     rax, rbx
0x1800d364b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3650  mov     rax, [rdi]
0x1800d3653  mov     rcx, rdi
0x1800d3656  mov     rax, [rax+48h]
  ... truncated ...
```
