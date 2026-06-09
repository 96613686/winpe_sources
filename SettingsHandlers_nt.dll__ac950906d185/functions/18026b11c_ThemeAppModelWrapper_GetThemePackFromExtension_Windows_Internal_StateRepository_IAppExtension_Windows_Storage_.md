# ThemeAppModelWrapper::GetThemePackFromExtension(Windows::Internal::StateRepository::IAppExtension *,Windows::Storage::IStorageFile * *)

- ea: `0x18026b11c`
- end: `0x18026b524`
- name: `?GetThemePackFromExtension@ThemeAppModelWrapper@@SAJPEAUIAppExtension@StateRepository@Internal@Windows@@PEAPEAUIStorageFile@Storage@5@@Z`
- size: `1032`
- prototype: `__int64 __fastcall(struct Windows::Internal::StateRepository::IAppExtension *, struct Windows::Storage::IStorageFile **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18026ba2c`

## callees

- `0x180011bb0`
- `0x180019a20`
- `0x1800212b0`
- `0x180269088`
- `0x18026aba4`
- `0x18026b11c`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18026b39c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18026b3d5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18026b39c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18026b3d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026b34b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026b3ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026b41e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026b48d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026b34b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026b3ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026b41e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026b48d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18026b37a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18026b3b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18026b37a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18026b3b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ThemeAppModelWrapper::GetThemePackFromExtension(
        struct Windows::Internal::StateRepository::IAppExtension *a1,
        struct Windows::Storage::IStorageFile **a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  int PublicFolderForTheme; // eax
  struct Windows::Storage::IStorageFolder *v7; // rbx
  __int64 (__fastcall *v8)(struct Windows::Storage::IStorageFolder *, GUID *, __int64 *); // rdi
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, _QWORD, __int64 *); // rbx
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rdi
  int v17; // eax
  unsigned __int64 v18; // r9
  __int64 v19; // rdx
  unsigned int i; // esi
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, _QWORD, struct Windows::Storage::IStorageFile **); // rbx
  int v23; // eax
  struct Windows::Storage::IStorageFile *v24; // rdi
  __int64 (__fastcall *v25)(struct Windows::Storage::IStorageFile *, HSTRING *); // rbx
  int v26; // eax
  const WCHAR *StringRawBuffer; // rax
  const WCHAR *v28; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-40h]
  __int64 v31; // [rsp+30h] [rbp-30h] BYREF
  struct Windows::Storage::IStorageFile *v32; // [rsp+38h] [rbp-28h] BYREF
  __int64 v33; // [rsp+40h] [rbp-20h] BYREF
  __int64 v34; // [rsp+48h] [rbp-18h] BYREF
  struct Windows::Storage::IStorageFolder *v35[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  unsigned int v37; // [rsp+90h] [rbp+30h] BYREF
  __int64 v38; // [rsp+A0h] [rbp+40h] BYREF
  HSTRING string; // [rsp+A8h] [rbp+48h] BYREF

  if ( a1 )
  {
    if ( !a2 )
    {
      v4 = 363;
      goto LABEL_3;
    }
    *a2 = 0;
    v35[0] = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v35);
    PublicFolderForTheme = ThemeAppModelWrapper::GetPublicFolderForTheme(a1, v35);
    v5 = PublicFolderForTheme;
    if ( PublicFolderForTheme < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16E,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
        (const char *)(unsigned int)PublicFolderForTheme,
        bIgnoreCase);
LABEL_36:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v35);
      return (unsigned int)v5;
    }
    v38 = 0;
    v7 = v35[0];
    v8 = **(__int64 (__fastcall ***)(struct Windows::Storage::IStorageFolder *, GUID *, __int64 *))v35[0];
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
    v9 = v8(v7, &GUID_cb43ccc9_446b_4a4f_be97_757771be5203, &v38);
    v5 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x172,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
        (const char *)(unsigned int)v9,
        bIgnoreCase);
LABEL_35:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
      goto LABEL_36;
    }
    v31 = 0;
    v10 = v38;
    v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v38 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    v12 = v11(v10, 0, &v31);
    v5 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x174,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
        (const char *)(unsigned int)v12,
        bIgnoreCase);
LABEL_34:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
      goto LABEL_35;
    }
    v34 = 0;
    v13 = v31;
    v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    v15 = v14(v13, &v34);
    v5 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x177,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
        (const char *)(unsigned int)v15,
        bIgnoreCase);
LABEL_33:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
      goto LABEL_34;
    }
    v33 = 0;
    v16 = v34;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    v5 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Storage::StorageFile *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Storage::StorageFile *> *>>(v16);
    if ( v5 < 0 || (v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 64LL))(v16, &v33), v5 < 0) )
    {
      v18 = (unsigned int)v5;
      v19 = 377;
    }
    else
    {
      v37 = 0;
      v17 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v33 + 56LL))(v33, &v37);
      v5 = v17;
      if ( v17 >= 0 )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= v37 )
            goto LABEL_26;
          v32 = 0;
          v21 = v33;
          v22 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Storage::IStorageFile **))(*(_QWORD *)v33 + 48LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
          v23 = v22(v21, i, &v32);
          v5 = v23;
          if ( v23 < 0 )
            break;
          string = 0;
          v24 = v32;
          v25 = *(__int64 (__fastcall **)(struct Windows::Storage::IStorageFile *, HSTRING *))(*(_QWORD *)v32 + 48LL);
          WindowsDeleteString(0);
          string = 0;
          v26 = v25(v24, &string);
          v5 = v26;
          if ( v26 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x182,
              (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
              (const char *)(unsigned int)v26,
              bIgnoreCase);
            WindowsDeleteString(string);
            string = 0;
            goto LABEL_29;
          }
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          if ( CompareStringOrdinal(StringRawBuffer, -1, L".themepack", -1, 0) == 2
            || (v28 = WindowsGetStringRawBuffer(string, 0), CompareStringOrdinal(v28, -1, L".deskthemepack", -1, 0) == 2) )
          {
            Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v32);
            *a2 = v32;
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
LABEL_26:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v35);
            return 0;
          }
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x180,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
          (const char *)(unsigned int)v23,
          bIgnoreCase);
LABEL_29:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
        goto LABEL_32;
      }
      v18 = (unsigned int)v17;
      v19 = 380;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
      (const char *)v18,
      bIgnoreCase);
LABEL_32:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    goto LABEL_33;
  }
  v4 = 362;
LABEL_3:
  v5 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
    (const char *)0x80070057LL,
    bIgnoreCase);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18026b11c  mov     [rsp-28h+arg_8], rbx
0x18026b121  push    rbp
0x18026b122  push    rsi
0x18026b123  push    rdi
0x18026b124  push    r14
0x18026b126  push    r15
0x18026b128  mov     rbp, rsp
0x18026b12b  sub     rsp, 60h
0x18026b12f  mov     r14, rdx
0x18026b132  mov     rbx, rcx
0x18026b135  xor     r15d, r15d
0x18026b138  test    rcx, rcx
0x18026b13b  jnz     short loc_18026B15F
0x18026b13d  mov     edx, 16Ah; void *
0x18026b142  mov     ebx, 80070057h
0x18026b147  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026b14e  mov     r9d, ebx; char *
0x18026b151  mov     rcx, [rbp+28h]; this
0x18026b155  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026b15a  jmp     loc_18026B50D
0x18026b15f  test    r14, r14
0x18026b162  jnz     short loc_18026B16B
0x18026b164  mov     edx, 16Bh
0x18026b169  jmp     short loc_18026B142
0x18026b16b  mov     [rdx], r15
0x18026b16e  mov     [rbp+var_10], r15
0x18026b172  lea     rcx, [rbp+var_10]
0x18026b176  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026b17b  lea     rdx, [rbp+var_10]; struct Windows::Storage::IStorageFolder **
0x18026b17f  mov     rcx, rbx; struct Windows::Internal::StateRepository::IAppExtension *
0x18026b182  call    ?GetPublicFolderForTheme@ThemeAppModelWrapper@@CAJPEAUIAppExtension@StateRepository@Internal@Windows@@PEAPEAUIStorageFolder@Storage@5@@Z; ThemeAppModelWrapper::GetPublicFolderForTheme(Windows::Internal::StateRepository::IAppExtension *,Windows::Storage::IStorageFolder * *)
0x18026b187  mov     ebx, eax
0x18026b189  test    eax, eax
0x18026b18b  jns     short loc_18026B1AA
0x18026b18d  mov     rcx, [rbp+28h]; this
0x18026b191  mov     r9d, eax; char *
0x18026b194  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026b19b  mov     edx, 16Eh; void *
0x18026b1a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026b1a5  jmp     loc_18026B504
0x18026b1aa  mov     [rbp+arg_10], r15
0x18026b1ae  mov     rbx, [rbp+var_10]
0x18026b1b2  mov     rax, [rbx]
0x18026b1b5  mov     rdi, [rax]
0x18026b1b8  lea     rcx, [rbp+arg_10]
0x18026b1bc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026b1c1  lea     r8, [rbp+arg_10]
0x18026b1c5  lea     rdx, _GUID_cb43ccc9_446b_4a4f_be97_757771be5203
0x18026b1cc  mov     rcx, rbx
0x18026b1cf  mov     rax, rdi
0x18026b1d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026b1d7  mov     ebx, eax
0x18026b1d9  test    eax, eax
0x18026b1db  jns     short loc_18026B1FA
0x18026b1dd  mov     rcx, [rbp+28h]; this
0x18026b1e1  mov     r9d, eax; char *
0x18026b1e4  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026b1eb  mov     edx, 172h; void *
0x18026b1f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026b1f5  jmp     loc_18026B4FA
0x18026b1fa  mov     [rbp+var_30], r15
0x18026b1fe  mov     rdi, [rbp+arg_10]
0x18026b202  mov     rax, [rdi]
0x18026b205  mov     rbx, [rax+40h]
0x18026b209  lea     rcx, [rbp+var_30]
0x18026b20d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026b212  lea     r8, [rbp+var_30]
0x18026b216  xor     edx, edx
0x18026b218  mov     rcx, rdi
0x18026b21b  mov     rax, rbx
0x18026b21e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026b223  mov     ebx, eax
0x18026b225  test    eax, eax
0x18026b227  jns     short loc_18026B246
0x18026b229  mov     rcx, [rbp+28h]; this
0x18026b22d  mov     r9d, eax; char *
0x18026b230  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026b237  mov     edx, 174h; void *
0x18026b23c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026b241  jmp     loc_18026B4F0
0x18026b246  mov     [rbp+var_18], r15
0x18026b24a  mov     rdi, [rbp+var_30]
0x18026b24e  mov     rax, [rdi]
0x18026b251  mov     rbx, [rax+38h]
0x18026b255  lea     rcx, [rbp+var_18]
0x18026b259  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026b25e  lea     rdx, [rbp+var_18]
0x18026b262  mov     rcx, rdi
0x18026b265  mov     rax, rbx
0x18026b268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026b26d  mov     ebx, eax
0x18026b26f  test    eax, eax
0x18026b271  jns     short loc_18026B290
0x18026b273  mov     rcx, [rbp+28h]; this
0x18026b277  mov     r9d, eax; char *
0x18026b27a  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026b281  mov     edx, 177h; void *
0x18026b286  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026b28b  jmp     loc_18026B4E6
0x18026b290  mov     [rbp+var_20], r15
0x18026b294  mov     rdi, [rbp+var_18]
0x18026b298  lea     rcx, [rbp+var_20]
0x18026b29c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026b2a1  mov     rcx, rdi
0x18026b2a4  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVStorageFile@Storage@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVStorageFile@Storage@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVStorageFile@Storage@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Storage::StorageFile *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Storage::StorageFile *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Storage::StorageFile *> *> *,tagCOWAIT_FLAGS,void *)
0x18026b2a9  mov     ebx, eax
0x18026b2ab  test    eax, eax
0x18026b2ad  js      loc_18026B4C3
0x18026b2b3  mov     rax, [rdi]
0x18026b2b6  lea     rdx, [rbp+var_20]
0x18026b2ba  mov     rcx, rdi
0x18026b2bd  mov     rax, [rax+40h]
0x18026b2c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026b2c6  mov     ebx, eax
0x18026b2c8  test    eax, eax
0x18026b2ca  js      loc_18026B4C3
0x18026b2d0  mov     [rbp+arg_0], r15d
0x18026b2d4  mov     rcx, [rbp+var_20]
0x18026b2d8  mov     rax, [rcx]
0x18026b2db  lea     rdx, [rbp+arg_0]
0x18026b2df  mov     rax, [rax+38h]
0x18026b2e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026b2e8  mov     ebx, eax
0x18026b2ea  test    eax, eax
0x18026b2ec  jns     short loc_18026B2FB
0x18026b2ee  mov     r9d, eax
0x18026b2f1  mov     edx, 17Ch
0x18026b2f6  jmp     loc_18026B4CB
0x18026b2fb  mov     esi, r15d
0x18026b2fe  cmp     esi, [rbp+arg_0]
0x18026b301  jnb     loc_18026B438
0x18026b307  mov     [rbp+var_28], r15
0x18026b30b  mov     rdi, [rbp+var_20]
0x18026b30f  mov     rax, [rdi]
0x18026b312  mov     rbx, [rax+30h]
0x18026b316  lea     rcx, [rbp+var_28]
0x18026b31a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026b31f  lea     r8, [rbp+var_28]
0x18026b323  mov     edx, esi
0x18026b325  mov     rcx, rdi
0x18026b328  mov     rax, rbx
0x18026b32b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026b330  mov     ebx, eax
0x18026b332  test    eax, eax
0x18026b334  js      loc_18026B49F
0x18026b33a  mov     [rbp+string], r15
0x18026b33e  mov     rdi, [rbp+var_28]
0x18026b342  mov     rax, [rdi]
0x18026b345  mov     rbx, [rax+30h]
0x18026b349  xor     ecx, ecx; string
0x18026b34b  call    cs:__imp_WindowsDeleteString
0x18026b352  nop     dword ptr [rax+rax+00h]
0x18026b357  mov     [rbp+string], r15
0x18026b35b  lea     rdx, [rbp+string]
0x18026b35f  mov     rcx, rdi
0x18026b362  mov     rax, rbx
0x18026b365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026b36a  mov     ebx, eax
0x18026b36c  test    eax, eax
0x18026b36e  js      loc_18026B470
0x18026b374  xor     edx, edx; length
0x18026b376  mov     rcx, [rbp+string]; string
0x18026b37a  call    cs:__imp_WindowsGetStringRawBuffer
0x18026b381  nop     dword ptr [rax+rax+00h]
0x18026b386  mov     [rsp+60h+bIgnoreCase], r15d; bIgnoreCase
0x18026b38b  or      r9d, 0FFFFFFFFh; cchCount2
0x18026b38f  lea     r8, aThemepack; ".themepack"
0x18026b396  or      edx, r9d; cchCount1
0x18026b399  mov     rcx, rax; lpString1
0x18026b39c  call    cs:__imp_CompareStringOrdinal
0x18026b3a3  nop     dword ptr [rax+rax+00h]
0x18026b3a8  cmp     eax, 2
0x18026b3ab  jz      short loc_18026B40A
0x18026b3ad  xor     edx, edx; length
0x18026b3af  mov     rcx, [rbp+string]; string
0x18026b3b3  call    cs:__imp_WindowsGetStringRawBuffer
0x18026b3ba  nop     dword ptr [rax+rax+00h]
0x18026b3bf  mov     [rsp+60h+bIgnoreCase], r15d; bIgnoreCase
0x18026b3c4  or      r9d, 0FFFFFFFFh; cchCount2
0x18026b3c8  lea     r8, aDeskthemepack_0; ".deskthemepack"
0x18026b3cf  or      edx, r9d; cchCount1
0x18026b3d2  mov     rcx, rax; lpString1
0x18026b3d5  call    cs:__imp_CompareStringOrdinal
0x18026b3dc  nop     dword ptr [rax+rax+00h]
0x18026b3e1  cmp     eax, 2
0x18026b3e4  jz      short loc_18026B40A
0x18026b3e6  mov     rcx, [rbp+string]; string
0x18026b3ea  call    cs:__imp_WindowsDeleteString
0x18026b3f1  nop     dword ptr [rax+rax+00h]
0x18026b3f6  mov     [rbp+string], r15
0x18026b3fa  lea     rcx, [rbp+var_28]
0x18026b3fe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026b403  inc     esi
0x18026b405  jmp     loc_18026B2FE
0x18026b40a  lea     rcx, [rbp+var_28]
0x18026b40e  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18026b413  mov     rax, [rbp+var_28]
0x18026b417  mov     [r14], rax
0x18026b41a  mov     rcx, [rbp+string]; string
0x18026b41e  call    cs:__imp_WindowsDeleteString
0x18026b425  nop     dword ptr [rax+rax+00h]
0x18026b42a  mov     [rbp+string], r15
0x18026b42e  lea     rcx, [rbp+var_28]
0x18026b432  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026b437  nop
0x18026b438  lea     rcx, [rbp+var_20]
0x18026b43c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026b441  nop
0x18026b442  lea     rcx, [rbp+var_18]
0x18026b446  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026b44b  nop
0x18026b44c  lea     rcx, [rbp+var_30]
0x18026b450  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026b455  nop
0x18026b456  lea     rcx, [rbp+arg_10]
0x18026b45a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026b45f  nop
0x18026b460  lea     rcx, [rbp+var_10]
0x18026b464  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026b469  xor     eax, eax
0x18026b46b  jmp     loc_18026B50F
0x18026b470  mov     rcx, [rbp+28h]; this
0x18026b474  mov     r9d, eax; char *
0x18026b477  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026b47e  mov     edx, 182h; void *
0x18026b483  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026b488  nop
0x18026b489  mov     rcx, [rbp+string]; string
0x18026b48d  call    cs:__imp_WindowsDeleteString
0x18026b494  nop     dword ptr [rax+rax+00h]
0x18026b499  mov     [rbp+string], r15
0x18026b49d  jmp     short loc_18026B4B8
0x18026b49f  mov     rcx, [rbp+28h]; this
0x18026b4a3  mov     r9d, eax; char *
0x18026b4a6  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026b4ad  mov     edx, 180h; void *
0x18026b4b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026b4b7  nop
0x18026b4b8  lea     rcx, [rbp+var_28]
0x18026b4bc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026b4c1  jmp     short loc_18026B4DC
0x18026b4c3  mov     r9d, ebx; char *
0x18026b4c6  mov     edx, 179h; void *
0x18026b4cb  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026b4d2  mov     rcx, [rbp+28h]; this
0x18026b4d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026b4db  nop
0x18026b4dc  lea     rcx, [rbp+var_20]
0x18026b4e0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026b4e5  nop
0x18026b4e6  lea     rcx, [rbp+var_18]
0x18026b4ea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026b4ef  nop
0x18026b4f0  lea     rcx, [rbp+var_30]
0x18026b4f4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026b4f9  nop
0x18026b4fa  lea     rcx, [rbp+arg_10]
0x18026b4fe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026b503  nop
0x18026b504  lea     rcx, [rbp+var_10]
0x18026b508  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026b50d  mov     eax, ebx
0x18026b50f  mov     rbx, [rsp+60h+arg_8]
0x18026b517  add     rsp, 60h
0x18026b51b  pop     r15
0x18026b51d  pop     r14
0x18026b51f  pop     rdi
0x18026b520  pop     rsi
0x18026b521  pop     rbp
0x18026b522  retn
```
