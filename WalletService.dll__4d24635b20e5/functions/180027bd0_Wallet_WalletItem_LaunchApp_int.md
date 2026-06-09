# Wallet::WalletItem::LaunchApp(int *)

- ea: `0x180027bd0`
- end: `0x180027f24`
- name: `?LaunchApp@WalletItem@Wallet@@UEAAJPEAH@Z`
- size: `852`
- prototype: `__int64 __fastcall(Wallet::WalletItem *__hidden this, int *)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x18000d8d8`
- `0x180013f78`
- `0x18001d5a0`
- `0x180026120`
- `0x1800265a4`
- `0x180027bd0`
- `0x180037064`
- `0x180037494`
- `0x1800375ec`
- `0x180038800`
- `0x180038af4`
- `0x180038cc0`
- `0x1800396c8`
- `0x180043090`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180027e16`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180027e16`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180027d0e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180027dc5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180027d0e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180027dc5`
- `ext-ms-onecore-shellchromeapi-l1-1-0!Shell_LaunchSessionByUriEx` at `0x180027ede`
- `ext-ms-onecore-shellchromeapi-l1-1-0!Shell_LaunchSessionByUriEx` at `0x180027ede`

## string_xrefs

- `0x180027cdd`: `Windows.Foundation.Uri`

## pseudocode

```c
__int64 __fastcall Wallet::WalletItem::LaunchApp(Wallet::WalletItem *this, int *a2)
{
  __int64 v4; // rax
  int ActivationFactory; // ebx
  int *v6; // r8
  void *p_hstringHeader; // rcx
  __int64 v8; // rbx
  _QWORD *v9; // rbx
  __int64 v10; // rdi
  unsigned __int64 v11; // r9
  __int64 v12; // rbx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64, __int64 *); // rbx
  __int64 v15; // rdx
  struct Wallet::Utils::WalletActivationArguments *v16; // rdx
  __int64 v17; // rdx
  unsigned __int16 v19[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD *v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  int v23; // [rsp+40h] [rbp-C0h] BYREF
  PCWSTR sourceString[4]; // [rsp+48h] [rbp-B8h] BYREF
  Wallet::Utils *v25[5]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v26[8]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v27[40]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v28[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v29[32]; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+100h] [rbp+0h] BYREF
  __int64 v31; // [rsp+118h] [rbp+18h]

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v25);
  *a2 = 0;
  v4 = *(_QWORD *)this;
  v23 = 0;
  ActivationFactory = (*(__int64 (__fastcall **)(Wallet::WalletItem *, int *))(v4 + 168))(this, &v23);
  if ( ActivationFactory >= 0 )
  {
    Wallet::Utils::GetProductId(this, v25);
    if ( !v23 )
      goto LABEL_29;
    if ( v23 != 1 )
    {
      if ( v23 == 2 )
      {
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(sourceString);
        v21 = 0;
        v20 = 0;
        *(_QWORD *)v19 = 0;
        v22 = 0;
        if ( g_fUnitTestContext )
        {
          ActivationFactory = g_launchUriReturnValue;
        }
        else
        {
          ActivationFactory = Wallet::Utils::ConstructStoreLaunchUri(v25[0], sourceString);
          if ( ActivationFactory >= 0 )
          {
            v31 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(
              &hstringHeader,
              L"Windows.Foundation.Uri",
              0x17u,
              0x16u);
            v8 = v31;
            Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(&v21);
            ActivationFactory = RoGetActivationFactory(v8, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v21);
            if ( ActivationFactory >= 0 )
            {
              v9 = v21;
              v10 = *v21;
              Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(&v20);
              v11 = -1;
              v31 = 0;
              do
                ++v11;
              while ( sourceString[0][v11] );
              if ( v11 > 0xFFFFFFFF || (int)v11 + 1 < (unsigned int)v11 )
              {
                RaiseException(0x80070216, 1u, 0, 0);
                __debugbreak();
              }
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, sourceString[0], v11 + 1, v11);
              ActivationFactory = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64 *))(v10 + 48))(v9, v31, &v20);
              if ( ActivationFactory >= 0 )
              {
                v31 = 0;
                Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                  &hstringHeader,
                  L"Windows.System.Launcher",
                  0x18u,
                  0x17u);
                v12 = v31;
                Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(v19);
                ActivationFactory = RoGetActivationFactory(v12, &GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451, v19);
                if ( ActivationFactory >= 0 )
                {
                  v13 = *(_QWORD *)v19;
                  v14 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(**(_QWORD **)v19 + 64LL);
                  Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(&v22);
                  ActivationFactory = v14(v13, v20, &v22);
                }
              }
            }
          }
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(&v22);
        Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(v19);
        Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(&v20);
        Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(&v21);
        p_hstringHeader = sourceString;
LABEL_25:
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(p_hstringHeader);
        goto LABEL_30;
      }
LABEL_29:
      ActivationFactory = -2147418113;
      goto LABEL_30;
    }
    *(_DWORD *)v19 = 0;
    if ( !(unsigned int)Wallet::Utils::IsModernApp(v25[0], v19, v6) )
    {
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&hstringHeader);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(sourceString);
      if ( g_fUnitTestContext )
      {
        ActivationFactory = g_launchUriReturnValue;
      }
      else
      {
        ActivationFactory = Wallet::Utils::ConvertItemIdToString((char *)this + 80, &hstringHeader);
        if ( ActivationFactory >= 0 )
        {
          ActivationFactory = Wallet::Utils::GetLinkedAppUri(hstringHeader.Reserved.Reserved1, v17, sourceString);
          if ( ActivationFactory >= 0 )
            ActivationFactory = Shell_LaunchSessionByUriEx(sourceString[0]);
        }
      }
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(sourceString);
      p_hstringHeader = &hstringHeader;
      goto LABEL_25;
    }
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v27);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v28);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v29);
    ActivationFactory = Wallet::Utils::GetWalletActivationArguments(*((_QWORD *)this + 10), v15, v26);
    if ( ActivationFactory >= 0 )
      ActivationFactory = Wallet::Utils::ActivateApplication((Wallet::Utils *)v26, v16);
    Wallet::Utils::WalletActivationArguments::~WalletActivationArguments((Wallet::Utils::WalletActivationArguments *)v26);
  }
LABEL_30:
  *a2 = ActivationFactory >= 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v25);
  return 0;
}

```

## disassembly

```asm
0x180027bd0  mov     [rsp-8+arg_10], rbx
0x180027bd5  mov     [rsp-8+arg_18], rsi
0x180027bda  push    rbp
0x180027bdb  push    rdi
0x180027bdc  push    r14
0x180027bde  lea     rbp, [rsp-30h]
0x180027be3  sub     rsp, 130h
0x180027bea  mov     rax, cs:__security_cookie
0x180027bf1  xor     rax, rsp
0x180027bf4  mov     [rbp+40h+var_20], rax
0x180027bf8  mov     rdi, rcx
0x180027bfb  mov     rsi, rdx
0x180027bfe  lea     rcx, [rsp+140h+var_D8]
0x180027c03  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180027c08  xor     r14d, r14d
0x180027c0b  lea     rdx, [rsp+140h+var_100]
0x180027c10  mov     [rsi], r14d
0x180027c13  mov     rcx, rdi
0x180027c16  mov     rax, [rdi]
0x180027c19  mov     [rsp+140h+var_100], r14d
0x180027c1e  mov     rax, [rax+0A8h]
0x180027c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c2a  mov     ebx, eax
0x180027c2c  test    eax, eax
0x180027c2e  js      loc_180027EED
0x180027c34  lea     rdx, [rsp+140h+var_D8]
0x180027c39  mov     rcx, rdi
0x180027c3c  call    ?GetProductId@Utils@Wallet@@YAJPEAUIWalletItem@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Wallet::Utils::GetProductId(IWalletItem *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180027c41  mov     ecx, [rsp+140h+var_100]
0x180027c45  test    ecx, ecx
0x180027c47  jz      loc_180027EE8
0x180027c4d  sub     ecx, 1
0x180027c50  jz      loc_180027E1D
0x180027c56  cmp     ecx, 1
0x180027c59  jnz     loc_180027EE8
0x180027c5f  lea     rcx, [rsp+140h+sourceString]
0x180027c64  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180027c69  cmp     cs:?g_fUnitTestContext@@3HA, r14d; int g_fUnitTestContext
0x180027c70  mov     [rsp+140h+var_110], r14
0x180027c75  mov     [rsp+140h+var_118], r14
0x180027c7a  mov     qword ptr [rsp+140h+var_120], r14
0x180027c7f  mov     [rsp+140h+var_108], r14
0x180027c84  jz      short loc_180027CBE
0x180027c86  mov     ebx, cs:?g_launchUriReturnValue@@3JA; long g_launchUriReturnValue
0x180027c8c  lea     rcx, [rsp+140h+var_108]
0x180027c91  call    ?InternalRelease@?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(void)
0x180027c96  lea     rcx, [rsp+140h+var_120]
0x180027c9b  call    ?InternalRelease@?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(void)
0x180027ca0  lea     rcx, [rsp+140h+var_118]
0x180027ca5  call    ?InternalRelease@?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(void)
0x180027caa  lea     rcx, [rsp+140h+var_110]
0x180027caf  call    ?InternalRelease@?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(void)
0x180027cb4  lea     rcx, [rsp+140h+sourceString]
0x180027cb9  jmp     loc_180027EAB
0x180027cbe  mov     rcx, [rsp+140h+var_D8]
0x180027cc3  lea     rdx, [rsp+140h+sourceString]
0x180027cc8  call    ?ConstructStoreLaunchUri@Utils@Wallet@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Wallet::Utils::ConstructStoreLaunchUri(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180027ccd  mov     ebx, eax
0x180027ccf  test    eax, eax
0x180027cd1  js      short loc_180027C8C
0x180027cd3  mov     r9d, 16h; unsigned int
0x180027cd9  mov     [rbp+40h+var_28], r14
0x180027cdd  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x180027ce4  lea     rcx, [rbp+40h+hstringHeader]; hstringHeader
0x180027ce8  lea     r8d, [r9+1]; unsigned int
0x180027cec  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180027cf1  mov     rbx, [rbp+40h+var_28]
0x180027cf5  lea     rcx, [rsp+140h+var_110]
0x180027cfa  call    ?InternalRelease@?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(void)
0x180027cff  lea     r8, [rsp+140h+var_110]
0x180027d04  mov     rcx, rbx
0x180027d07  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x180027d0e  call    cs:__imp_RoGetActivationFactory
0x180027d14  mov     ebx, eax
0x180027d16  test    eax, eax
0x180027d18  js      loc_180027C8C
0x180027d1e  mov     rbx, [rsp+140h+var_110]
0x180027d23  lea     rcx, [rsp+140h+var_118]
0x180027d28  mov     rdi, [rbx]
0x180027d2b  call    ?InternalRelease@?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(void)
0x180027d30  mov     rdx, [rsp+140h+sourceString]; sourceString
0x180027d35  or      r9, 0FFFFFFFFFFFFFFFFh
0x180027d39  mov     [rbp+40h+var_28], r14
0x180027d3d  inc     r9; unsigned int
0x180027d40  cmp     [rdx+r9*2], r14w
0x180027d45  jnz     short loc_180027D3D
0x180027d47  mov     eax, 0FFFFFFFFh
0x180027d4c  cmp     r9, rax
0x180027d4f  ja      loc_180027E07
0x180027d55  lea     r8d, [r9+1]; unsigned int
0x180027d59  cmp     r8d, r9d
0x180027d5c  jb      loc_180027E07
0x180027d62  lea     rcx, [rbp+40h+hstringHeader]; hstringHeader
0x180027d66  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180027d6b  mov     rdx, [rbp+40h+var_28]
0x180027d6f  lea     r8, [rsp+140h+var_118]
0x180027d74  mov     rax, [rdi+30h]
0x180027d78  mov     rcx, rbx
0x180027d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d80  mov     ebx, eax
0x180027d82  test    eax, eax
0x180027d84  js      loc_180027C8C
0x180027d8a  mov     r9d, 17h; unsigned int
0x180027d90  mov     [rbp+40h+var_28], r14
0x180027d94  lea     rdx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x180027d9b  lea     rcx, [rbp+40h+hstringHeader]; hstringHeader
0x180027d9f  lea     r8d, [r9+1]; unsigned int
0x180027da3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180027da8  mov     rbx, [rbp+40h+var_28]
0x180027dac  lea     rcx, [rsp+140h+var_120]
0x180027db1  call    ?InternalRelease@?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(void)
0x180027db6  lea     r8, [rsp+140h+var_120]
0x180027dbb  mov     rcx, rbx
0x180027dbe  lea     rdx, _GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451
0x180027dc5  call    cs:__imp_RoGetActivationFactory
0x180027dcb  lea     rcx, [rsp+140h+var_108]
0x180027dd0  mov     ebx, eax
0x180027dd2  test    eax, eax
0x180027dd4  js      loc_180027C91
0x180027dda  mov     rdi, qword ptr [rsp+140h+var_120]
0x180027ddf  mov     rax, [rdi]
0x180027de2  mov     rbx, [rax+40h]
0x180027de6  call    ?InternalRelease@?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::InternalRelease(void)
0x180027deb  mov     rdx, [rsp+140h+var_118]
0x180027df0  lea     r8, [rsp+140h+var_108]
0x180027df5  mov     rcx, rdi
0x180027df8  mov     rax, rbx
0x180027dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e00  mov     ebx, eax
0x180027e02  jmp     loc_180027C8C
0x180027e07  xor     r9d, r9d; lpArguments
0x180027e0a  xor     r8d, r8d; nNumberOfArguments
0x180027e0d  mov     ecx, 80070216h; dwExceptionCode
0x180027e12  lea     edx, [r9+1]; dwExceptionFlags
0x180027e16  call    cs:__imp_RaiseException
0x180027e1c  int     3; Trap to Debugger
0x180027e1d  mov     rcx, [rsp+140h+var_D8]; this
0x180027e22  lea     rdx, [rsp+140h+var_120]; unsigned __int16 *
0x180027e27  mov     dword ptr [rsp+140h+var_120], r14d
0x180027e2c  call    ?IsModernApp@Utils@Wallet@@YAHPEBGAEAH@Z; Wallet::Utils::IsModernApp(ushort const *,int &)
0x180027e31  test    eax, eax
0x180027e33  jz      short loc_180027E7B
0x180027e35  lea     rcx, [rbp+40h+var_A8]
0x180027e39  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180027e3e  lea     rcx, [rbp+40h+var_80]
0x180027e42  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180027e47  lea     rcx, [rbp+40h+var_60]
0x180027e4b  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180027e50  mov     rcx, [rdi+50h]
0x180027e54  lea     r8, [rbp+40h+var_B0]
0x180027e58  call    ?GetWalletActivationArguments@Utils@Wallet@@YAJ_KW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@AEAUWalletActivationArguments@12@@Z; Wallet::Utils::GetWalletActivationArguments(unsigned __int64,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,Wallet::Utils::WalletActivationArguments &)
0x180027e5d  lea     rcx, [rbp+40h+var_B0]; this
0x180027e61  mov     ebx, eax
0x180027e63  test    eax, eax
0x180027e65  jns     short loc_180027E6E
0x180027e67  call    ??1WalletActivationArguments@Utils@Wallet@@QEAA@XZ; Wallet::Utils::WalletActivationArguments::~WalletActivationArguments(void)
0x180027e6c  jmp     short loc_180027EED
0x180027e6e  call    ?ActivateApplication@Utils@Wallet@@YAJAEAUWalletActivationArguments@12@@Z; Wallet::Utils::ActivateApplication(Wallet::Utils::WalletActivationArguments &)
0x180027e73  mov     ebx, eax
0x180027e75  lea     rcx, [rbp+40h+var_B0]
0x180027e79  jmp     short loc_180027E67
0x180027e7b  lea     rcx, [rbp+40h+hstringHeader]
0x180027e7f  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180027e84  lea     rcx, [rsp+140h+sourceString]
0x180027e89  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180027e8e  cmp     cs:?g_fUnitTestContext@@3HA, r14d; int g_fUnitTestContext
0x180027e95  jz      short loc_180027EB2
0x180027e97  mov     ebx, cs:?g_launchUriReturnValue@@3JA; long g_launchUriReturnValue
0x180027e9d  lea     rcx, [rsp+140h+sourceString]
0x180027ea2  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180027ea7  lea     rcx, [rbp+40h+hstringHeader]
0x180027eab  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180027eb0  jmp     short loc_180027EED
0x180027eb2  lea     rcx, [rdi+50h]
0x180027eb6  lea     rdx, [rbp+40h+hstringHeader]
0x180027eba  call    ?ConvertItemIdToString@Utils@Wallet@@YAJAEB_KAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Wallet::Utils::ConvertItemIdToString(unsigned __int64 const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180027ebf  mov     ebx, eax
0x180027ec1  test    eax, eax
0x180027ec3  js      short loc_180027E9D
0x180027ec5  mov     rcx, qword ptr [rbp+40h+hstringHeader.Reserved]
0x180027ec9  lea     r8, [rsp+140h+sourceString]
0x180027ece  call    ?GetLinkedAppUri@Utils@Wallet@@YAJPEBGW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Wallet::Utils::GetLinkedAppUri(ushort const *,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180027ed3  mov     ebx, eax
0x180027ed5  test    eax, eax
0x180027ed7  js      short loc_180027E9D
0x180027ed9  mov     rcx, [rsp+140h+sourceString]
0x180027ede  call    cs:__imp_Shell_LaunchSessionByUriEx
0x180027ee4  mov     ebx, eax
0x180027ee6  jmp     short loc_180027E9D
0x180027ee8  mov     ebx, 8000FFFFh
0x180027eed  not     ebx
0x180027eef  lea     rcx, [rsp+140h+var_D8]
0x180027ef4  shr     ebx, 1Fh
0x180027ef7  mov     [rsi], ebx
0x180027ef9  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180027efe  xor     eax, eax
0x180027f00  mov     rcx, [rbp+40h+var_20]
0x180027f04  xor     rcx, rsp; StackCookie
0x180027f07  call    __security_check_cookie
0x180027f0c  lea     r11, [rsp+140h+var_10]
0x180027f14  mov     rbx, [r11+30h]
0x180027f18  mov     rsi, [r11+38h]
0x180027f1c  mov     rsp, r11
0x180027f1f  pop     r14
0x180027f21  pop     rdi
0x180027f22  pop     rbp
0x180027f23  retn
```
