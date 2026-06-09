# SystemSettings::StorageSenseHandlers::CAppTileData::GetVersionNumber(HSTRING__ * *)

- ea: `0x1800a9a84`
- end: `0x1800a9db5`
- name: `?GetVersionNumber@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z`
- size: `817`
- prototype: `int(SystemSettings::StorageSenseHandlers::CAppTileData *__hidden this, HSTRING *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180041bc0`
- `0x1800bba54`

## callees

- `0x180006e50`
- `0x180007a00`
- `0x18000c964`
- `0x18000e6cc`
- `0x18000f07c`
- `0x180036c38`
- `0x180049f18`
- `0x1800a01b0`
- `0x1800a0338`
- `0x1800a0388`
- `0x1800a9a84`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9b97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9cad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9cd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9b97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9cad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9cd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a9c80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a9c80`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppTileData::GetVersionNumber(
        SystemSettings::StorageSenseHandlers::CAppTileData *this,
        HSTRING *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  const unsigned __int16 (*v8)[41]; // rdx
  _QWORD *v9; // rax
  HRESULT v10; // eax
  __int64 v11; // rdx
  __int64 (__fastcall *v12)(SystemSettings::StorageSenseHandlers::CAppTileData *, HSTRING *); // rbx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, HSTRING, __int64 *); // rbx
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rdx
  int v18; // [rsp+20h] [rbp-E0h]
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v22; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v23; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR sourceString[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  if ( *((_DWORD *)this + 12) == 2 )
  {
    v19 = 0;
    v4 = Microsoft::WRL::ComPtr<IInspectable>::As<SystemSettings::DataModel::StorageSense::IDesktopAppInfo>(
           (char *)this + 40,
           &v19);
    v5 = v4;
    if ( v4 < 0 )
    {
      v6 = 1193;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
        (const char *)(unsigned int)v4,
        v18);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v19);
      return v5;
    }
    v4 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 112LL))(v19, a2);
    v5 = v4;
    if ( v4 < 0 )
    {
      v6 = 1194;
      goto LABEL_6;
    }
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v19);
    return 0;
  }
  if ( !*((_DWORD *)this + 12) )
  {
    v20 = 0;
    v19 = 0;
    string = 0;
    v22 = 0;
    memset_0(sourceString, 0, 0x208u);
    v9 = (_QWORD *)Windows::Internal::StringReference::StringReference(&v23, v8);
    v10 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(
            *v9,
            &v20);
    v5 = v10;
    if ( v10 < 0 )
    {
      v11 = 1204;
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
        (const char *)(unsigned int)v10,
        v18);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v19);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v20);
      return v5;
    }
    v12 = *(__int64 (__fastcall **)(SystemSettings::StorageSenseHandlers::CAppTileData *, HSTRING *))(*(_QWORD *)this + 56LL);
    WindowsDeleteString(string);
    string = 0;
    v10 = v12(this, &string);
    v5 = v10;
    if ( v10 < 0 )
    {
      v11 = 1205;
      goto LABEL_24;
    }
    v13 = v20;
    v14 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, __int64 *))(*(_QWORD *)v20 + 368LL);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v19);
    v10 = v14(v13, 0, string, &v19);
    v5 = v10;
    if ( v10 < 0 )
    {
      v11 = 1206;
      goto LABEL_24;
    }
    v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 104LL))(v19, &v22);
    v5 = v10;
    if ( v10 < 0 )
    {
      v11 = 1208;
      goto LABEL_24;
    }
    v18 = WORD2(v22);
    v10 = StringCchPrintfW(sourceString, 0x104u, L"%d.%d.%d.%d", HIWORD(v22));
    v5 = v10;
    if ( v10 < 0 )
    {
      v11 = 1217;
      goto LABEL_24;
    }
    v15 = -1;
    do
      ++v15;
    while ( sourceString[v15] );
    v10 = WindowsCreateString(sourceString, v15, a2);
    v5 = v10;
    if ( v10 < 0 )
    {
      v11 = 1219;
      goto LABEL_24;
    }
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v19);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v20);
    return 0;
  }
  if ( *((_DWORD *)this + 12) == 3
    && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ID59787121>::GetImpl'::`2'::impl) )
  {
    v20 = 0;
    v16 = Microsoft::WRL::ComPtr<IInspectable>::As<SystemSettings::DataModel::StorageSense::IMcpServerInfo>(
            (char *)this + 40,
            &v20);
    v5 = v16;
    if ( v16 >= 0 )
    {
      v16 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v20 + 104LL))(v20, a2);
      v5 = v16;
      if ( v16 >= 0 )
      {
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v20);
        return 0;
      }
      v17 = 1227;
    }
    else
    {
      v17 = 1226;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
      (const char *)(unsigned int)v16,
      v18);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v20);
    return v5;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800a9a84  mov     [rsp-8+arg_10], rbx
0x1800a9a89  mov     [rsp-8+arg_18], rsi
0x1800a9a8e  push    rbp
0x1800a9a8f  push    rdi
0x1800a9a90  push    r14
0x1800a9a92  lea     rbp, [rsp-1A0h]
0x1800a9a9a  sub     rsp, 2A0h
0x1800a9aa1  mov     rax, cs:__security_cookie
0x1800a9aa8  xor     rax, rsp
0x1800a9aab  mov     [rbp+1B0h+var_20], rax
0x1800a9ab2  mov     r14, rdx
0x1800a9ab5  mov     rdi, rcx
0x1800a9ab8  xor     esi, esi
0x1800a9aba  cmp     dword ptr [rcx+30h], 2
0x1800a9abe  jnz     short loc_1800A9B36
0x1800a9ac0  mov     [rsp+2B0h+var_270], rsi
0x1800a9ac5  add     rcx, 28h ; '('
0x1800a9ac9  lea     rdx, [rsp+2B0h+var_270]
0x1800a9ace  call    ??$As@UIDesktopAppInfo@StorageSense@DataModel@SystemSettings@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDesktopAppInfo@StorageSense@DataModel@SystemSettings@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<SystemSettings::DataModel::StorageSense::IDesktopAppInfo>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SystemSettings::DataModel::StorageSense::IDesktopAppInfo>>)
0x1800a9ad3  mov     ebx, eax
0x1800a9ad5  test    eax, eax
0x1800a9ad7  jns     short loc_1800A9AE0
0x1800a9ad9  mov     edx, 4A9h
0x1800a9ade  jmp     short loc_1800A9AFF
0x1800a9ae0  mov     rcx, [rsp+2B0h+var_270]
0x1800a9ae5  mov     rax, [rcx]
0x1800a9ae8  mov     rdx, r14
0x1800a9aeb  mov     rax, [rax+70h]
0x1800a9aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9af4  mov     ebx, eax
0x1800a9af6  test    eax, eax
0x1800a9af8  jns     short loc_1800A9B27
0x1800a9afa  mov     edx, 4AAh; void *
0x1800a9aff  mov     r9d, eax; char *
0x1800a9b02  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a9b09  mov     rcx, [rbp+1B8h]; this
0x1800a9b10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a9b15  nop
0x1800a9b16  lea     rcx, [rsp+2B0h+var_270]
0x1800a9b1b  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a9b20  mov     eax, ebx
0x1800a9b22  jmp     loc_1800A9D8E
0x1800a9b27  lea     rcx, [rsp+2B0h+var_270]
0x1800a9b2c  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a9b31  jmp     loc_1800A9D85
0x1800a9b36  cmp     [rcx+30h], esi
0x1800a9b39  jnz     loc_1800A9CFC
0x1800a9b3f  mov     [rsp+2B0h+var_268], rsi
0x1800a9b44  mov     [rsp+2B0h+var_270], rsi
0x1800a9b49  mov     [rsp+2B0h+string], rsi
0x1800a9b4e  mov     [rsp+2B0h+var_258], rsi
0x1800a9b53  xor     edx, edx; Val
0x1800a9b55  mov     r8d, 208h; Size
0x1800a9b5b  lea     rcx, [rbp+1B0h+sourceString]; void *
0x1800a9b5f  call    memset_0
0x1800a9b64  lea     rcx, [rsp+2B0h+var_250]; string
0x1800a9b69  call    ??$?0$0CJ@@StringReference@Internal@Windows@@QEAA@AEAY0CJ@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[41])
0x1800a9b6e  lea     rdx, [rsp+2B0h+var_268]
0x1800a9b73  mov     rcx, [rax]
0x1800a9b76  call    ??$GetActivationFactory@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>)
0x1800a9b7b  mov     ebx, eax
0x1800a9b7d  test    eax, eax
0x1800a9b7f  jns     short loc_1800A9B8B
0x1800a9b81  mov     edx, 4B4h
0x1800a9b86  jmp     loc_1800A9C91
0x1800a9b8b  mov     rax, [rdi]
0x1800a9b8e  mov     rbx, [rax+38h]
0x1800a9b92  mov     rcx, [rsp+2B0h+string]; string
0x1800a9b97  call    cs:__imp_WindowsDeleteString
0x1800a9b9d  mov     [rsp+2B0h+string], rsi
0x1800a9ba2  lea     rdx, [rsp+2B0h+string]
0x1800a9ba7  mov     rcx, rdi
0x1800a9baa  mov     rax, rbx
0x1800a9bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9bb2  mov     ebx, eax
0x1800a9bb4  test    eax, eax
0x1800a9bb6  jns     short loc_1800A9BC2
0x1800a9bb8  mov     edx, 4B5h
0x1800a9bbd  jmp     loc_1800A9C91
0x1800a9bc2  mov     rdi, [rsp+2B0h+var_268]
0x1800a9bc7  mov     rax, [rdi]
0x1800a9bca  mov     rbx, [rax+170h]
0x1800a9bd1  lea     rcx, [rsp+2B0h+var_270]
0x1800a9bd6  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a9bdb  lea     r9, [rsp+2B0h+var_270]
0x1800a9be0  mov     r8, [rsp+2B0h+string]
0x1800a9be5  xor     edx, edx
0x1800a9be7  mov     rcx, rdi
0x1800a9bea  mov     rax, rbx
0x1800a9bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9bf2  mov     ebx, eax
0x1800a9bf4  test    eax, eax
0x1800a9bf6  jns     short loc_1800A9C02
0x1800a9bf8  mov     edx, 4B6h
0x1800a9bfd  jmp     loc_1800A9C91
0x1800a9c02  mov     rcx, [rsp+2B0h+var_270]
0x1800a9c07  mov     rax, [rcx]
0x1800a9c0a  lea     rdx, [rsp+2B0h+var_258]
0x1800a9c0f  mov     rax, [rax+68h]
0x1800a9c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9c18  mov     ebx, eax
0x1800a9c1a  test    eax, eax
0x1800a9c1c  jns     short loc_1800A9C25
0x1800a9c1e  mov     edx, 4B8h
0x1800a9c23  jmp     short loc_1800A9C91
0x1800a9c25  movzx   eax, word ptr [rsp+2B0h+var_258]
0x1800a9c2a  movzx   ecx, word ptr [rsp+2B0h+var_258+2]
0x1800a9c2f  movzx   edx, word ptr [rsp+2B0h+var_258+4]
0x1800a9c34  movzx   r9d, word ptr [rsp+2B0h+var_258+6]
0x1800a9c3a  mov     [rsp+2B0h+var_280], eax
0x1800a9c3e  mov     [rsp+2B0h+var_288], ecx
0x1800a9c42  mov     [rsp+2B0h+var_290], edx; int
0x1800a9c46  lea     r8, aDDDD; "%d.%d.%d.%d"
0x1800a9c4d  mov     edx, 104h; unsigned __int64
0x1800a9c52  lea     rcx, [rbp+1B0h+sourceString]; unsigned __int16 *
0x1800a9c56  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a9c5b  mov     ebx, eax
0x1800a9c5d  test    eax, eax
0x1800a9c5f  jns     short loc_1800A9C68
0x1800a9c61  mov     edx, 4C1h
0x1800a9c66  jmp     short loc_1800A9C91
0x1800a9c68  lea     rax, [rbp+1B0h+sourceString]
0x1800a9c6c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800a9c70  inc     rdx; length
0x1800a9c73  cmp     [rax+rdx*2], si
0x1800a9c77  jnz     short loc_1800A9C70
0x1800a9c79  mov     r8, r14; string
0x1800a9c7c  lea     rcx, [rbp+1B0h+sourceString]; sourceString
0x1800a9c80  call    cs:__imp_WindowsCreateString
0x1800a9c86  mov     ebx, eax
0x1800a9c88  test    eax, eax
0x1800a9c8a  jns     short loc_1800A9CD2
0x1800a9c8c  mov     edx, 4C3h; void *
0x1800a9c91  mov     r9d, eax; char *
0x1800a9c94  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a9c9b  mov     rcx, [rbp+1B8h]; this
0x1800a9ca2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a9ca7  nop
0x1800a9ca8  mov     rcx, [rsp+2B0h+string]; string
0x1800a9cad  call    cs:__imp_WindowsDeleteString
0x1800a9cb3  mov     [rsp+2B0h+string], rsi
0x1800a9cb8  lea     rcx, [rsp+2B0h+var_270]
0x1800a9cbd  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a9cc2  nop
0x1800a9cc3  lea     rcx, [rsp+2B0h+var_268]
0x1800a9cc8  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a9ccd  jmp     loc_1800A9B20
0x1800a9cd2  mov     rcx, [rsp+2B0h+string]; string
0x1800a9cd7  call    cs:__imp_WindowsDeleteString
0x1800a9cdd  mov     [rsp+2B0h+string], rsi
0x1800a9ce2  lea     rcx, [rsp+2B0h+var_270]
0x1800a9ce7  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a9cec  nop
0x1800a9ced  lea     rcx, [rsp+2B0h+var_268]
0x1800a9cf2  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a9cf7  jmp     loc_1800A9D85
0x1800a9cfc  cmp     dword ptr [rcx+30h], 3
0x1800a9d00  jnz     loc_1800A9D89
0x1800a9d06  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID59787121@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID59787121@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121> `wil::Feature<__WilFeatureTraits_Feature_ID59787121>::GetImpl(void)'::`2'::impl
0x1800a9d0d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59787121@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121>::__private_IsEnabled(void)
0x1800a9d12  test    al, al
0x1800a9d14  jz      short loc_1800A9D89
0x1800a9d16  mov     [rsp+2B0h+var_268], rsi
0x1800a9d1b  lea     rcx, [rdi+28h]
0x1800a9d1f  lea     rdx, [rsp+2B0h+var_268]
0x1800a9d24  call    ??$As@UIMcpServerInfo@StorageSense@DataModel@SystemSettings@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIMcpServerInfo@StorageSense@DataModel@SystemSettings@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<SystemSettings::DataModel::StorageSense::IMcpServerInfo>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SystemSettings::DataModel::StorageSense::IMcpServerInfo>>)
0x1800a9d29  mov     ebx, eax
0x1800a9d2b  test    eax, eax
0x1800a9d2d  jns     short loc_1800A9D36
0x1800a9d2f  mov     edx, 4CAh
0x1800a9d34  jmp     short loc_1800A9D55
0x1800a9d36  mov     rcx, [rsp+2B0h+var_268]
0x1800a9d3b  mov     rax, [rcx]
0x1800a9d3e  mov     rdx, r14
0x1800a9d41  mov     rax, [rax+68h]
0x1800a9d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9d4a  mov     ebx, eax
0x1800a9d4c  test    eax, eax
0x1800a9d4e  jns     short loc_1800A9D7B
0x1800a9d50  mov     edx, 4CBh; void *
0x1800a9d55  mov     r9d, eax; char *
0x1800a9d58  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a9d5f  mov     rcx, [rbp+1B8h]; this
0x1800a9d66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a9d6b  nop
0x1800a9d6c  lea     rcx, [rsp+2B0h+var_268]
0x1800a9d71  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a9d76  jmp     loc_1800A9B20
0x1800a9d7b  lea     rcx, [rsp+2B0h+var_268]
0x1800a9d80  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a9d85  xor     eax, eax
0x1800a9d87  jmp     short loc_1800A9D8E
0x1800a9d89  mov     eax, 80070057h
0x1800a9d8e  mov     rcx, [rbp+1B0h+var_20]
0x1800a9d95  xor     rcx, rsp; StackCookie
0x1800a9d98  call    __security_check_cookie
0x1800a9d9d  lea     r11, [rsp+2B0h+var_10]
0x1800a9da5  mov     rbx, [r11+30h]
0x1800a9da9  mov     rsi, [r11+38h]
0x1800a9dad  mov     rsp, r11
0x1800a9db0  pop     r14
0x1800a9db2  pop     rdi
0x1800a9db3  pop     rbp
0x1800a9db4  retn
```
