# GetWebAcount(ushort const *,Windows::Security::Credentials::IWebAccount * *)

- ea: `0x18007759c`
- end: `0x180077c1a`
- name: `?GetWebAcount@@YAJPEBGPEAPEAUIWebAccount@Credentials@Security@Windows@@@Z`
- size: `1662`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct Windows::Security::Credentials::IWebAccount **)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180074f10`

## callees

- `0x180007270`
- `0x180057c6c`
- `0x18005d690`
- `0x180064a44`
- `0x180072920`
- `0x1800729d0`
- `0x180072f7c`
- `0x180072fc4`
- `0x180073004`
- `0x18007759c`
- `0x180078358`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007761e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007761e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007776b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077821`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800778eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077996`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077a62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077b0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077b7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007776b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077821`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800778eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077996`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077a62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077b0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077b7d`

## string_xrefs

- `0x180077688`: `onecoreuap\admin\dm\dmcmnutils\tokenutils\tokenutils.cpp`
- `0x180077754`: `onecoreuap\admin\dm\dmcmnutils\tokenutils\tokenutils.cpp`
- `0x18007780a`: `onecoreuap\admin\dm\dmcmnutils\tokenutils\tokenutils.cpp`
- `0x1800778d4`: `onecoreuap\admin\dm\dmcmnutils\tokenutils\tokenutils.cpp`
- `0x18007797f`: `onecoreuap\admin\dm\dmcmnutils\tokenutils\tokenutils.cpp`
- `0x180077a4b`: `onecoreuap\admin\dm\dmcmnutils\tokenutils\tokenutils.cpp`
- `0x180077af4`: `onecoreuap\admin\dm\dmcmnutils\tokenutils\tokenutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall GetWebAcount(const unsigned __int16 *a1, struct Windows::Security::Credentials::IWebAccount **a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  unsigned __int64 v8; // rcx
  int v9; // ebx
  unsigned int v10; // r8d
  const unsigned __int16 *v11; // rdx
  const unsigned __int16 *v12; // rdx
  _QWORD *v13; // rax
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING, __int64 *); // rbx
  int v18; // eax
  unsigned int v19; // ebx
  int v20; // eax
  unsigned int v21; // ebx
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, __int64, HSTRING, __int64 *); // rbx
  int v24; // eax
  unsigned int v25; // ebx
  int v26; // eax
  unsigned int v27; // ebx
  int ppv; // [rsp+20h] [rbp-D8h]
  LPVOID v29; // [rsp+30h] [rbp-C8h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+40h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+48h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v34; // [rsp+58h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+60h] [rbp-98h] BYREF
  unsigned int v36; // [rsp+68h] [rbp-90h] BYREF
  LPVOID *v37; // [rsp+70h] [rbp-88h]
  __int64 *v38; // [rsp+78h] [rbp-80h]
  char v39; // [rsp+80h] [rbp-78h]
  HSTRING v40; // [rsp+88h] [rbp-70h] BYREF
  HSTRING v41; // [rsp+A8h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v33 = 0;
  v32 = 0;
  v34 = 0;
  v29 = 0;
  v35 = 0;
  v31 = 0;
  Windows::Internal::StringReference::StringReference(&v40, (const unsigned __int16 (*)[26])a2);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  v4 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &v29);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 715;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\tokenutils\\tokenutils.cpp",
      (const char *)(unsigned int)v4,
      ppv);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
    return v5;
  }
  v4 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v29 + 32LL))(v29, 5, &v35);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 717;
    goto LABEL_7;
  }
  v4 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v29 + 24LL))(v29, 5, 1);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 719;
    goto LABEL_7;
  }
  v37 = &v29;
  v38 = &v35;
  v39 = 1;
  string = 0;
  if ( a1 )
  {
    v36 = 0;
    v8 = -1;
    do
      ++v8;
    while ( a1[v8] );
    v9 = ULongLongToULong(v8, &v36);
    if ( v9 < 0 )
      goto LABEL_15;
    v10 = v36;
    v11 = a1;
  }
  else
  {
    v10 = 0;
    v11 = &pszSrc;
  }
  v9 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, v11, v10);
  if ( v9 < 0 )
  {
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D9,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\tokenutils\\tokenutils.cpp",
      (const char *)(unsigned int)v9,
      ppv);
    WindowsDeleteString(string);
    string = 0;
    v39 = 0;
    (*(void (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v29 + 24LL))(v29, 5, v35);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
    return (unsigned int)v9;
  }
  v13 = (_QWORD *)Windows::Internal::StringReference::StringReference(&v41, (const unsigned __int16 (*)[70])v12);
  v14 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(
          *v13,
          &v32);
  v15 = v14;
  if ( v14 >= 0 )
  {
    v16 = v32;
    v17 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v32 + 88LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    v18 = v17(v16, v40, &v31);
    v19 = v18;
    if ( v18 >= 0 )
    {
      v20 = BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider>(
              v31,
              &v34);
      v21 = v20;
      if ( v20 >= 0 )
      {
        v22 = v32;
        v23 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, __int64 *))(*(_QWORD *)v32 + 80LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
        v24 = v23(v22, v34, string, &v33);
        v25 = v24;
        if ( v24 >= 0 )
        {
          v26 = BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>,Windows::Security::Credentials::IWebAccount *>(
                  v33,
                  a2);
          v27 = v26;
          if ( v26 >= 0 )
          {
            WindowsDeleteString(string);
            (*(void (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v29 + 24LL))(v29, 5, v35);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2DE,
              (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\tokenutils\\tokenutils.cpp",
              (const char *)(unsigned int)v26,
              ppv);
            WindowsDeleteString(string);
            string = 0;
            v39 = 0;
            (*(void (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v29 + 24LL))(v29, 5, v35);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
            return v27;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2DD,
            (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\tokenutils\\tokenutils.cpp",
            (const char *)(unsigned int)v24,
            ppv);
          WindowsDeleteString(string);
          string = 0;
          v39 = 0;
          (*(void (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v29 + 24LL))(v29, 5, v35);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
          return v25;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2DC,
          (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\tokenutils\\tokenutils.cpp",
          (const char *)(unsigned int)v20,
          ppv);
        WindowsDeleteString(string);
        string = 0;
        v39 = 0;
        (*(void (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v29 + 24LL))(v29, 5, v35);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
        return v21;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2DB,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\tokenutils\\tokenutils.cpp",
        (const char *)(unsigned int)v18,
        ppv);
      WindowsDeleteString(string);
      string = 0;
      v39 = 0;
      (*(void (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v29 + 24LL))(v29, 5, v35);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
      return v19;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DA,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\tokenutils\\tokenutils.cpp",
      (const char *)(unsigned int)v14,
      ppv);
    WindowsDeleteString(string);
    string = 0;
    v39 = 0;
    (*(void (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v29 + 24LL))(v29, 5, v35);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
    return v15;
  }
}

```

## disassembly

```asm
0x18007759c  mov     r11, rsp
0x18007759f  mov     [r11+18h], rbx
0x1800775a3  push    rsi
0x1800775a4  push    rdi
0x1800775a5  push    r12
0x1800775a7  push    r14
0x1800775a9  push    r15
0x1800775ab  sub     rsp, 0D0h
0x1800775b2  mov     rax, cs:__security_cookie
0x1800775b9  xor     rax, rsp
0x1800775bc  mov     [rsp+0F8h+var_30], rax
0x1800775c4  mov     r12, rdx
0x1800775c7  mov     rdi, rcx
0x1800775ca  xor     esi, esi
0x1800775cc  mov     [rsp+0F8h+var_A8], rsi
0x1800775d1  mov     [rsp+0F8h+var_B0], rsi
0x1800775d6  mov     [rsp+0F8h+var_A0], rsi
0x1800775db  mov     [rsp+0F8h+var_C8], rsi
0x1800775e0  mov     [rsp+0F8h+var_98], rsi
0x1800775e5  mov     [rsp+0F8h+var_B8], rsi
0x1800775ea  lea     rcx, [r11-70h]; string
0x1800775ee  call    ??$?0$0BK@@StringReference@Internal@Windows@@QEAA@AEAY0BK@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[26])
0x1800775f3  lea     rcx, [rsp+0F8h+var_C8]
0x1800775f8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800775fd  lea     rax, [rsp+0F8h+var_C8]
0x180077602  mov     qword ptr [rsp+0F8h+ppv], rax; int
0x180077607  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18007760e  lea     r15d, [rsi+1]
0x180077612  mov     r8d, r15d; dwClsContext
0x180077615  xor     edx, edx; pUnkOuter
0x180077617  lea     rcx, CLSID_GlobalOptions; rclsid
0x18007761e  call    cs:__imp_CoCreateInstance
0x180077625  nop     dword ptr [rax+rax+00h]
0x18007762a  mov     ebx, eax
0x18007762c  test    eax, eax
0x18007762e  jns     short loc_180077637
0x180077630  mov     edx, 2CBh
0x180077635  jmp     short loc_180077685
0x180077637  mov     rcx, [rsp+0F8h+var_C8]
0x18007763c  mov     rax, [rcx]
0x18007763f  lea     r8, [rsp+0F8h+var_98]
0x180077644  mov     r14d, 5
0x18007764a  mov     edx, r14d
0x18007764d  mov     rax, [rax+20h]
0x180077651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077656  mov     ebx, eax
0x180077658  test    eax, eax
0x18007765a  jns     short loc_180077663
0x18007765c  mov     edx, 2CDh
0x180077661  jmp     short loc_180077685
0x180077663  mov     rcx, [rsp+0F8h+var_C8]
0x180077668  mov     rax, [rcx]
0x18007766b  mov     r8, r15
0x18007766e  mov     edx, r14d
0x180077671  mov     rax, [rax+18h]
0x180077675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007767a  mov     ebx, eax
0x18007767c  test    eax, eax
0x18007767e  jns     short loc_1800776DA
0x180077680  mov     edx, 2CFh; void *
0x180077685  mov     r9d, eax; char *
0x180077688  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmcmnutils\\toke"...
0x18007768f  mov     rcx, [rsp+0F8h]; this
0x180077697  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007769c  nop
0x18007769d  lea     rcx, [rsp+0F8h+var_B8]
0x1800776a2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800776a7  nop
0x1800776a8  lea     rcx, [rsp+0F8h+var_C8]
0x1800776ad  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800776b2  nop
0x1800776b3  lea     rcx, [rsp+0F8h+var_A0]
0x1800776b8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800776bd  nop
0x1800776be  lea     rcx, [rsp+0F8h+var_B0]
0x1800776c3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800776c8  nop
0x1800776c9  lea     rcx, [rsp+0F8h+var_A8]
0x1800776ce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800776d3  mov     eax, ebx
0x1800776d5  jmp     loc_180077BF1
0x1800776da  lea     rax, [rsp+0F8h+var_C8]
0x1800776df  mov     [rsp+0F8h+var_88], rax
0x1800776e4  lea     rax, [rsp+0F8h+var_98]
0x1800776e9  mov     [rsp+0F8h+var_80], rax
0x1800776ee  mov     [rsp+0F8h+var_78], r15b
0x1800776f6  mov     [rsp+0F8h+string], rsi
0x1800776fb  test    rdi, rdi
0x1800776fe  jz      short loc_18007772B
0x180077700  mov     [rsp+0F8h+var_90], esi
0x180077704  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180077708  inc     rcx; unsigned __int64
0x18007770b  cmp     [rdi+rcx*2], si
0x18007770f  jnz     short loc_180077708
0x180077711  lea     rdx, [rsp+0F8h+var_90]; unsigned int *
0x180077716  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18007771b  mov     ebx, eax
0x18007771d  test    eax, eax
0x18007771f  js      short loc_180077749
0x180077721  mov     r8d, [rsp+0F8h+var_90]
0x180077726  mov     rdx, rdi
0x180077729  jmp     short loc_180077735
0x18007772b  xor     r8d, r8d; unsigned int
0x18007772e  lea     rdx, pszSrc; unsigned __int16 *
0x180077735  lea     rcx, [rsp+0F8h+string]; this
0x18007773a  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18007773f  mov     ebx, eax
0x180077741  test    eax, eax
0x180077743  jns     loc_1800777DB
0x180077749  mov     rcx, [rsp+0F8h]; this
0x180077751  mov     r9d, ebx; char *
0x180077754  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmcmnutils\\toke"...
0x18007775b  mov     edx, 2D9h; void *
0x180077760  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077765  nop
0x180077766  mov     rcx, [rsp+0F8h+string]; string
0x18007776b  call    cs:__imp_WindowsDeleteString
0x180077772  nop     dword ptr [rax+rax+00h]
0x180077777  mov     [rsp+0F8h+string], rsi
0x18007777c  mov     [rsp+0F8h+var_78], sil
0x180077784  mov     rcx, [rsp+0F8h+var_C8]
0x180077789  mov     rax, [rcx]
0x18007778c  mov     r8, [rsp+0F8h+var_98]
0x180077791  mov     edx, r14d
0x180077794  mov     rax, [rax+18h]
0x180077798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007779d  nop
0x18007779e  lea     rcx, [rsp+0F8h+var_B8]
0x1800777a3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800777a8  nop
0x1800777a9  lea     rcx, [rsp+0F8h+var_C8]
0x1800777ae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800777b3  nop
0x1800777b4  lea     rcx, [rsp+0F8h+var_A0]
0x1800777b9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800777be  nop
0x1800777bf  lea     rcx, [rsp+0F8h+var_B0]
0x1800777c4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800777c9  nop
0x1800777ca  lea     rcx, [rsp+0F8h+var_A8]
0x1800777cf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800777d4  mov     eax, ebx
0x1800777d6  jmp     loc_180077BF1
0x1800777db  lea     rcx, [rsp+0F8h+var_50]; string
0x1800777e3  call    ??$?0$0EG@@StringReference@Internal@Windows@@QEAA@AEAY0EG@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[70])
0x1800777e8  lea     rdx, [rsp+0F8h+var_B0]
0x1800777ed  mov     rcx, [rax]
0x1800777f0  call    ??$GetActivationFactory@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>)
0x1800777f5  mov     ebx, eax
0x1800777f7  test    eax, eax
0x1800777f9  jns     loc_180077891
0x1800777ff  mov     rcx, [rsp+0F8h]; this
0x180077807  mov     r9d, eax; char *
0x18007780a  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmcmnutils\\toke"...
0x180077811  mov     edx, 2DAh; void *
0x180077816  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007781b  nop
0x18007781c  mov     rcx, [rsp+0F8h+string]; string
0x180077821  call    cs:__imp_WindowsDeleteString
0x180077828  nop     dword ptr [rax+rax+00h]
0x18007782d  mov     [rsp+0F8h+string], rsi
0x180077832  mov     [rsp+0F8h+var_78], sil
0x18007783a  mov     rcx, [rsp+0F8h+var_C8]
0x18007783f  mov     rax, [rcx]
0x180077842  mov     r8, [rsp+0F8h+var_98]
0x180077847  mov     edx, r14d
0x18007784a  mov     rax, [rax+18h]
0x18007784e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077853  nop
0x180077854  lea     rcx, [rsp+0F8h+var_B8]
0x180077859  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007785e  nop
0x18007785f  lea     rcx, [rsp+0F8h+var_C8]
0x180077864  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180077869  nop
0x18007786a  lea     rcx, [rsp+0F8h+var_A0]
0x18007786f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180077874  nop
0x180077875  lea     rcx, [rsp+0F8h+var_B0]
0x18007787a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007787f  nop
0x180077880  lea     rcx, [rsp+0F8h+var_A8]
0x180077885  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007788a  mov     eax, ebx
0x18007788c  jmp     loc_180077BF1
0x180077891  mov     rdi, [rsp+0F8h+var_B0]
0x180077896  mov     rax, [rdi]
0x180077899  mov     rbx, [rax+58h]
0x18007789d  lea     rcx, [rsp+0F8h+var_B8]
0x1800778a2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800778a7  lea     r8, [rsp+0F8h+var_B8]
0x1800778ac  mov     rdx, [rsp+0F8h+var_70]
0x1800778b4  mov     rcx, rdi
0x1800778b7  mov     rax, rbx
0x1800778ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800778bf  mov     ebx, eax
0x1800778c1  test    eax, eax
0x1800778c3  jns     loc_18007795B
0x1800778c9  mov     rcx, [rsp+0F8h]; this
0x1800778d1  mov     r9d, eax; char *
0x1800778d4  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmcmnutils\\toke"...
0x1800778db  mov     edx, 2DBh; void *
0x1800778e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800778e5  nop
0x1800778e6  mov     rcx, [rsp+0F8h+string]; string
0x1800778eb  call    cs:__imp_WindowsDeleteString
0x1800778f2  nop     dword ptr [rax+rax+00h]
0x1800778f7  mov     [rsp+0F8h+string], rsi
0x1800778fc  mov     [rsp+0F8h+var_78], sil
0x180077904  mov     rcx, [rsp+0F8h+var_C8]
0x180077909  mov     rax, [rcx]
0x18007790c  mov     r8, [rsp+0F8h+var_98]
0x180077911  mov     edx, r14d
0x180077914  mov     rax, [rax+18h]
0x180077918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007791d  nop
0x18007791e  lea     rcx, [rsp+0F8h+var_B8]
0x180077923  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180077928  nop
0x180077929  lea     rcx, [rsp+0F8h+var_C8]
0x18007792e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180077933  nop
0x180077934  lea     rcx, [rsp+0F8h+var_A0]
0x180077939  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007793e  nop
0x18007793f  lea     rcx, [rsp+0F8h+var_B0]
0x180077944  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180077949  nop
0x18007794a  lea     rcx, [rsp+0F8h+var_A8]
0x18007794f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180077954  mov     eax, ebx
0x180077956  jmp     loc_180077BF1
0x18007795b  lea     rdx, [rsp+0F8h+var_A0]
0x180077960  mov     rcx, [rsp+0F8h+var_B8]
0x180077965  call    ??$BlockOnCompletionAndGetResults@PEAVWebAccountProvider@Credentials@Security@Windows@@UIWebAccountProvider@234@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>>,tagCOWAIT_FLAGS,void *)
0x18007796a  mov     ebx, eax
0x18007796c  test    eax, eax
0x18007796e  jns     loc_180077A06
0x180077974  mov     rcx, [rsp+0F8h]; this
0x18007797c  mov     r9d, eax; char *
0x18007797f  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmcmnutils\\toke"...
0x180077986  mov     edx, 2DCh; void *
0x18007798b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077990  nop
0x180077991  mov     rcx, [rsp+0F8h+string]; string
0x180077996  call    cs:__imp_WindowsDeleteString
0x18007799d  nop     dword ptr [rax+rax+00h]
0x1800779a2  mov     [rsp+0F8h+string], rsi
0x1800779a7  mov     [rsp+0F8h+var_78], sil
0x1800779af  mov     rcx, [rsp+0F8h+var_C8]
0x1800779b4  mov     rax, [rcx]
0x1800779b7  mov     r8, [rsp+0F8h+var_98]
0x1800779bc  mov     edx, r14d
0x1800779bf  mov     rax, [rax+18h]
0x1800779c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800779c8  nop
0x1800779c9  lea     rcx, [rsp+0F8h+var_B8]
0x1800779ce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800779d3  nop
0x1800779d4  lea     rcx, [rsp+0F8h+var_C8]
0x1800779d9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800779de  nop
0x1800779df  lea     rcx, [rsp+0F8h+var_A0]
0x1800779e4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800779e9  nop
0x1800779ea  lea     rcx, [rsp+0F8h+var_B0]
0x1800779ef  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800779f4  nop
0x1800779f5  lea     rcx, [rsp+0F8h+var_A8]
0x1800779fa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800779ff  mov     eax, ebx
0x180077a01  jmp     loc_180077BF1
0x180077a06  mov     rdi, [rsp+0F8h+var_B0]
0x180077a0b  mov     rax, [rdi]
0x180077a0e  mov     rbx, [rax+50h]
0x180077a12  lea     rcx, [rsp+0F8h+var_A8]
0x180077a17  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180077a1c  lea     r9, [rsp+0F8h+var_A8]
0x180077a21  mov     r8, [rsp+0F8h+string]
0x180077a26  mov     rdx, [rsp+0F8h+var_A0]
0x180077a2b  mov     rcx, rdi
0x180077a2e  mov     rax, rbx
0x180077a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077a36  mov     ebx, eax
0x180077a38  test    eax, eax
0x180077a3a  jns     loc_180077AD2
0x180077a40  mov     rcx, [rsp+0F8h]; this
0x180077a48  mov     r9d, eax; char *
0x180077a4b  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmcmnutils\\toke"...
0x180077a52  mov     edx, 2DDh; void *
0x180077a57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077a5c  nop
0x180077a5d  mov     rcx, [rsp+0F8h+string]; string
0x180077a62  call    cs:__imp_WindowsDeleteString
0x180077a69  nop     dword ptr [rax+rax+00h]
0x180077a6e  mov     [rsp+0F8h+string], rsi
0x180077a73  mov     [rsp+0F8h+var_78], sil
0x180077a7b  mov     rcx, [rsp+0F8h+var_C8]
0x180077a80  mov     rax, [rcx]
0x180077a83  mov     r8, [rsp+0F8h+var_98]
  ... truncated ...
```
