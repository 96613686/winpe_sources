# SystemSettings::Personalization::CSlideshowFolderHelper::IsFolderSupported(IShellItem *,bool)

- ea: `0x18019b160`
- end: `0x18019b42e`
- name: `?IsFolderSupported@CSlideshowFolderHelper@Personalization@SystemSettings@@QEAA_NPEAUIShellItem@@_N@Z`
- size: `718`
- prototype: `bool(SystemSettings::Personalization::CSlideshowFolderHelper *__hidden this, struct IShellItem *, bool)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180144fc0`
- `0x180196ce0`

## callees

- `0x18000c840`
- `0x180010e35`
- `0x180011bb0`
- `0x180021470`
- `0x1800236e0`
- `0x18019ad80`
- `0x18019b098`
- `0x18019b160`
- `0x18019b434`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019b212`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019b2d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019b2fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019b3c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019b212`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019b2d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019b2fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019b3c5`
- `SHELL32!SHCreateItemFromParsingName` at `0x18019b25c`
- `SHELL32!SHCreateItemFromParsingName` at `0x18019b25c`

## string_xrefs

- `0x18019b39d`: `Unhandled Folder Picker namespace.  This code needs to be updated to explicitly allow or disallow it.`
- `0x18019b3af`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\slideshowcommon.cpp`
- `0x18019b407`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\slideshowcommon.cpp`
- `0x18019b41c`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\slideshowcommon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
bool __fastcall SystemSettings::Personalization::CSlideshowFolderHelper::IsFolderSupported(
        SystemSettings::Personalization::CSlideshowFolderHelper *this,
        struct IShellItem *a2,
        char a3)
{
  int TopLevelNamespaceItem; // esi
  HRESULT (__stdcall *GetDisplayName)(IShellItem *, SIGDN, LPWSTR *); // rbx
  HRESULT v7; // eax
  int v8; // eax
  bool v9; // di
  HRESULT (__stdcall *v10)(IShellItem *, SIGDN, LPWSTR *); // rbx
  int v11; // ebx
  const unsigned __int16 *v12; // rdx
  int v14; // [rsp+20h] [rbp-50h]
  const char *v15; // [rsp+28h] [rbp-48h]
  PCWSTR pszPath; // [rsp+30h] [rbp-40h] BYREF
  struct IShellItem2 *v17; // [rsp+38h] [rbp-38h] BYREF
  void *ppv; // [rsp+40h] [rbp-30h] BYREF
  struct IShellItem2 *v19; // [rsp+48h] [rbp-28h] BYREF
  __int128 Buf1; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  Buf1 = 0;
  v19 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  TopLevelNamespaceItem = GetTopLevelNamespaceItem(a2, &v19);
  if ( TopLevelNamespaceItem >= 0 )
  {
    TopLevelNamespaceItem = ((__int64 (__fastcall *)(struct IShellItem2 *, const PROPERTYKEY *, __int128 *))v19->lpVtbl->GetCLSID)(
                              v19,
                              &PKEY_NamespaceCLSID,
                              &Buf1);
    pszPath = 0;
    if ( TopLevelNamespaceItem < 0 && !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    {
      GetDisplayName = a2->lpVtbl->GetDisplayName;
      CoTaskMemFree(0);
      if ( ((int (__fastcall *)(struct IShellItem *, __int64, PCWSTR *))GetDisplayName)(a2, 2147844096LL, &pszPath) >= 0 )
      {
        ppv = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
        v7 = SHCreateItemFromParsingName(pszPath, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
        if ( v7 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x3E8,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\slideshowcommon.cpp",
            (const char *)(unsigned int)v7,
            v14);
        v17 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
        v8 = GetTopLevelNamespaceItem((struct IShellItem *)ppv, &v17);
        if ( v8 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x3EB,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\slideshowcommon.cpp",
            (const char *)(unsigned int)v8,
            v14);
        TopLevelNamespaceItem = ((__int64 (__fastcall *)(struct IShellItem2 *, const PROPERTYKEY *, __int128 *))v17->lpVtbl->GetCLSID)(
                                  v17,
                                  &PKEY_NamespaceCLSID,
                                  &Buf1);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      }
    }
    CoTaskMemFree((LPVOID)pszPath);
  }
  v9 = 0;
  if ( TopLevelNamespaceItem >= 0 )
  {
    pszPath = 0;
    v10 = a2->lpVtbl->GetDisplayName;
    CoTaskMemFree(0);
    v11 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, PCWSTR *))v10)(a2, 2147844096LL, &pszPath);
    if ( a3 || !memcmp_0(&Buf1, &CLSID_UsersLibrariesFolder, 0x10u) )
    {
      v9 = 1;
    }
    else if ( !memcmp_0(&Buf1, &CLSID_NetworkExplorerFolder, 0x10u) )
    {
      v9 = 0;
    }
    else if ( v11 >= 0
           && (!memcmp_0(&Buf1, &CLSID_MyComputer, 0x10u)
            || SystemSettings::Personalization::IsCloudBrandNameFolder(pszPath, v12)) )
    {
      v9 = (unsigned int)IsNetworkItem(a2) == 0;
    }
    else
    {
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x423,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\slideshowcommon.cpp",
        (const char *)0x80004001LL,
        (int)"Unhandled Folder Picker namespace.  This code needs to be updated to explicitly allow or disallow it.",
        v15);
    }
    CoTaskMemFree((LPVOID)pszPath);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  return v9;
}

```

## disassembly

```asm
0x18019b160  mov     [rsp-28h+arg_0], rbx
0x18019b165  mov     [rsp-28h+arg_10], rsi
0x18019b16a  push    rbp
0x18019b16b  push    rdi
0x18019b16c  push    r13
0x18019b16e  push    r14
0x18019b170  push    r15
0x18019b172  mov     rbp, rsp
0x18019b175  sub     rsp, 70h
0x18019b179  mov     rax, cs:__security_cookie
0x18019b180  xor     rax, rsp
0x18019b183  mov     [rbp+var_10], rax
0x18019b187  mov     r15b, r8b
0x18019b18a  mov     r14, rdx
0x18019b18d  xorps   xmm0, xmm0
0x18019b190  movups  [rbp+Buf1], xmm0
0x18019b194  mov     [rbp+var_28], 0
0x18019b19c  lea     rcx, [rbp+var_28]
0x18019b1a0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b1a5  lea     rdx, [rbp+var_28]; struct IShellItem2 **
0x18019b1a9  mov     rcx, r14; struct IShellItem *
0x18019b1ac  call    ?GetTopLevelNamespaceItem@@YAJPEAUIShellItem@@PEAPEAUIShellItem2@@@Z; GetTopLevelNamespaceItem(IShellItem *,IShellItem2 * *)
0x18019b1b1  mov     esi, eax
0x18019b1b3  mov     r13d, 10h
0x18019b1b9  test    eax, eax
0x18019b1bb  js      loc_18019B2DF
0x18019b1c1  mov     rcx, [rbp+var_28]
0x18019b1c5  mov     rax, [rcx]
0x18019b1c8  lea     r8, [rbp+Buf1]
0x18019b1cc  lea     rdx, PKEY_NamespaceCLSID
0x18019b1d3  mov     rax, [rax+70h]
0x18019b1d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b1dc  mov     esi, eax
0x18019b1de  mov     [rbp+pszPath], 0
0x18019b1e6  test    eax, eax
0x18019b1e8  jns     loc_18019B2CF
0x18019b1ee  mov     r8d, r13d; Size
0x18019b1f1  lea     rdx, GUID_NULL; Buf2
0x18019b1f8  lea     rcx, [rbp+Buf1]; Buf1
0x18019b1fc  call    memcmp_0
0x18019b201  test    eax, eax
0x18019b203  jnz     loc_18019B2CF
0x18019b209  mov     rax, [r14]
0x18019b20c  mov     rbx, [rax+28h]
0x18019b210  xor     ecx, ecx; pv
0x18019b212  call    cs:__imp_CoTaskMemFree
0x18019b219  nop     dword ptr [rax+rax+00h]
0x18019b21e  lea     r8, [rbp+pszPath]
0x18019b222  mov     edx, 80058000h
0x18019b227  mov     rcx, r14
0x18019b22a  mov     rax, rbx
0x18019b22d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b232  test    eax, eax
0x18019b234  js      loc_18019B2CF
0x18019b23a  mov     [rbp+ppv], 0
0x18019b242  lea     rcx, [rbp+ppv]
0x18019b246  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b24b  lea     r9, [rbp+ppv]; ppv
0x18019b24f  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x18019b256  xor     edx, edx; pbc
0x18019b258  mov     rcx, [rbp+pszPath]; pszPath
0x18019b25c  call    cs:__imp_SHCreateItemFromParsingName
0x18019b263  nop     dword ptr [rax+rax+00h]
0x18019b268  mov     rcx, [rbp+28h]; this
0x18019b26c  test    eax, eax
0x18019b26e  js      loc_18019B419
0x18019b274  mov     [rbp+var_38], 0
0x18019b27c  lea     rcx, [rbp+var_38]
0x18019b280  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b285  lea     rdx, [rbp+var_38]; struct IShellItem2 **
0x18019b289  mov     rcx, [rbp+ppv]; struct IShellItem *
0x18019b28d  call    ?GetTopLevelNamespaceItem@@YAJPEAUIShellItem@@PEAPEAUIShellItem2@@@Z; GetTopLevelNamespaceItem(IShellItem *,IShellItem2 * *)
0x18019b292  mov     rcx, [rbp+28h]; this
0x18019b296  test    eax, eax
0x18019b298  js      loc_18019B404
0x18019b29e  mov     rcx, [rbp+var_38]
0x18019b2a2  mov     rax, [rcx]
0x18019b2a5  lea     r8, [rbp+Buf1]
0x18019b2a9  lea     rdx, PKEY_NamespaceCLSID
0x18019b2b0  mov     rax, [rax+70h]
0x18019b2b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b2b9  mov     esi, eax
0x18019b2bb  lea     rcx, [rbp+var_38]
0x18019b2bf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b2c4  nop
0x18019b2c5  lea     rcx, [rbp+ppv]
0x18019b2c9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b2ce  nop
0x18019b2cf  mov     rcx, [rbp+pszPath]; pv
0x18019b2d3  call    cs:__imp_CoTaskMemFree
0x18019b2da  nop     dword ptr [rax+rax+00h]
0x18019b2df  xor     dil, dil
0x18019b2e2  test    esi, esi
0x18019b2e4  js      loc_18019B3D2
0x18019b2ea  mov     [rbp+pszPath], 0
0x18019b2f2  mov     rax, [r14]
0x18019b2f5  mov     rbx, [rax+28h]
0x18019b2f9  xor     ecx, ecx; pv
0x18019b2fb  call    cs:__imp_CoTaskMemFree
0x18019b302  nop     dword ptr [rax+rax+00h]
0x18019b307  lea     r8, [rbp+pszPath]
0x18019b30b  mov     edx, 80058000h
0x18019b310  mov     rcx, r14
0x18019b313  mov     rax, rbx
0x18019b316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b31b  mov     ebx, eax
0x18019b31d  test    r15b, r15b
0x18019b320  jnz     short loc_18019B339
0x18019b322  mov     r8, r13; Size
0x18019b325  lea     rdx, CLSID_UsersLibrariesFolder; Buf2
0x18019b32c  lea     rcx, [rbp+Buf1]; Buf1
0x18019b330  call    memcmp_0
0x18019b335  test    eax, eax
0x18019b337  jnz     short loc_18019B341
0x18019b339  mov     dil, 1
0x18019b33c  jmp     loc_18019B3C1
0x18019b341  mov     r8, r13; Size
0x18019b344  lea     rdx, CLSID_NetworkExplorerFolder; Buf2
0x18019b34b  lea     rcx, [rbp+Buf1]; Buf1
0x18019b34f  call    memcmp_0
0x18019b354  test    eax, eax
0x18019b356  jnz     short loc_18019B35D
0x18019b358  xor     dil, dil
0x18019b35b  jmp     short loc_18019B3C1
0x18019b35d  shr     ebx, 1Fh
0x18019b360  xor     bl, 1
0x18019b363  jz      short loc_18019B399
0x18019b365  mov     r8, r13; Size
0x18019b368  lea     rdx, CLSID_MyComputer; Buf2
0x18019b36f  lea     rcx, [rbp+Buf1]; Buf1
0x18019b373  call    memcmp_0
0x18019b378  test    eax, eax
0x18019b37a  jz      short loc_18019B389
0x18019b37c  mov     rcx, [rbp+pszPath]; pszFile1
0x18019b380  call    ?IsCloudBrandNameFolder@Personalization@SystemSettings@@YA_NPEBG@Z; SystemSettings::Personalization::IsCloudBrandNameFolder(ushort const *)
0x18019b385  test    al, al
0x18019b387  jz      short loc_18019B399
0x18019b389  mov     rcx, r14; struct IShellItem *
0x18019b38c  call    ?IsNetworkItem@@YAHPEAUIShellItem@@@Z; IsNetworkItem(IShellItem *)
0x18019b391  test    eax, eax
0x18019b393  setz    dil
0x18019b397  jmp     short loc_18019B3C1
0x18019b399  mov     rcx, [rbp+28h]; this
0x18019b39d  lea     rax, aUnhandledFolde; "Unhandled Folder Picker namespace.  Thi"...
0x18019b3a4  mov     qword ptr [rsp+70h+var_50], rax; int
0x18019b3a9  mov     r9d, 80004001h; char *
0x18019b3af  lea     r8, aShellSystemset_5; "shell\\systemsettingsthreshold\\handler"...
0x18019b3b6  mov     edx, 423h; void *
0x18019b3bb  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18019b3c0  nop
0x18019b3c1  mov     rcx, [rbp+pszPath]; pv
0x18019b3c5  call    cs:__imp_CoTaskMemFree
0x18019b3cc  nop     dword ptr [rax+rax+00h]
0x18019b3d1  nop
0x18019b3d2  lea     rcx, [rbp+var_28]
0x18019b3d6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b3db  mov     al, dil
0x18019b3de  mov     rcx, [rbp+var_10]
0x18019b3e2  xor     rcx, rsp; StackCookie
0x18019b3e5  call    __security_check_cookie
0x18019b3ea  lea     r11, [rsp+70h+var_s0]
0x18019b3ef  mov     rbx, [r11+30h]
0x18019b3f3  mov     rsi, [r11+40h]
0x18019b3f7  mov     rsp, r11
0x18019b3fa  pop     r15
0x18019b3fc  pop     r14
0x18019b3fe  pop     r13
0x18019b400  pop     rdi
0x18019b401  pop     rbp
0x18019b402  retn
0x18019b404  mov     r9d, eax; char *
0x18019b407  lea     r8, aShellSystemset_5; "shell\\systemsettingsthreshold\\handler"...
0x18019b40e  mov     edx, 3EBh; void *
0x18019b413  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18019b419  mov     r9d, eax; char *
0x18019b41c  lea     r8, aShellSystemset_5; "shell\\systemsettingsthreshold\\handler"...
0x18019b423  mov     edx, 3E8h; void *
0x18019b428  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
