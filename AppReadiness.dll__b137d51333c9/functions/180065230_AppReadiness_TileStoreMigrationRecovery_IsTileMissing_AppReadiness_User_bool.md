# AppReadiness::TileStoreMigrationRecovery::IsTileMissing(AppReadiness::User *,bool &)

- ea: `0x180065230`
- end: `0x180065584`
- name: `?IsTileMissing@TileStoreMigrationRecovery@AppReadiness@@YAJPEAVUser@2@AEA_N@Z`
- size: `852`
- prototype: `__int64 __fastcall(AppReadiness::TileStoreMigrationRecovery *__hidden this, struct AppReadiness::User *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18006558c`

## callees

- `0x180002958`
- `0x18001d548`
- `0x1800203d8`
- `0x18002084c`
- `0x180030914`
- `0x18003e210`
- `0x180065230`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800652f0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006535d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800652f0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006535d`

## string_xrefs

- `0x18006529c`: `onecoreuap\shell\appreadiness\src\groups\tilestoremigrationrecovery.cpp`
- `0x180065303`: `onecoreuap\shell\appreadiness\src\groups\tilestoremigrationrecovery.cpp`
- `0x180065370`: `onecoreuap\shell\appreadiness\src\groups\tilestoremigrationrecovery.cpp`
- `0x1800653e5`: `onecoreuap\shell\appreadiness\src\groups\tilestoremigrationrecovery.cpp`
- `0x18006543b`: `onecoreuap\shell\appreadiness\src\groups\tilestoremigrationrecovery.cpp`
- `0x180065561`: `onecoreuap\shell\appreadiness\src\groups\tilestoremigrationrecovery.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall AppReadiness::TileStoreMigrationRecovery::IsTileMissing(
        AppReadiness::TileStoreMigrationRecovery *this,
        struct AppReadiness::User *a2,
        bool *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rbx
  int ActivationFactory; // eax
  __int64 v9; // rbx
  int v10; // eax
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int64, PVOID, __int64 *); // rdi
  const WCHAR *v13; // rax
  HSTRING_HEADER *v14; // rax
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64, __int64 *); // rbx
  int v18; // eax
  __int64 v19; // rdx
  unsigned int i; // esi
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, _QWORD, const WCHAR **); // rbx
  int v23; // eax
  __int64 v25; // rdx
  int v26; // [rsp+20h] [rbp-39h] BYREF
  __int64 v27; // [rsp+28h] [rbp-31h] BYREF
  __int64 v28; // [rsp+30h] [rbp-29h] BYREF
  __int64 v29; // [rsp+38h] [rbp-21h] BYREF
  __int64 v30; // [rsp+40h] [rbp-19h] BYREF
  const WCHAR *v31; // [rsp+48h] [rbp-11h] BYREF
  unsigned int v32; // [rsp+50h] [rbp-9h] BYREF
  __int64 v33; // [rsp+58h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp+7h] BYREF
  __int64 v35; // [rsp+78h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  *(_BYTE *)a2 = 0;
  v33 = 0;
  v35 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.User",
    0x26u,
    0x25u);
  v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics>>(
         v35,
         (__int64)&v33);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v27 = 0;
    v35 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.StateRepository.Application",
      0x2Du,
      0x2Cu);
    v7 = v35;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    ActivationFactory = RoGetActivationFactory(v7, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v27);
    v6 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7F,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\tilestoremigrationrecovery.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v26);
LABEL_5:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
      goto LABEL_28;
    }
    v28 = 0;
    v35 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.StateRepository.PrimaryTile",
      0x2Du,
      0x2Cu);
    v9 = v35;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    v10 = RoGetActivationFactory(v9, &GUID_d4df57cc_8228_4f18_8f78_a705d8416b07, &v28);
    v6 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x83,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\tilestoremigrationrecovery.cpp",
        (const char *)(unsigned int)v10,
        v26);
LABEL_8:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
      goto LABEL_5;
    }
    v30 = 0;
    v11 = v33;
    v12 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v33 + 80LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    v13 = (const WCHAR *)((char *)this + 64);
    if ( *((_QWORD *)this + 11) > 7u )
      v13 = *(const WCHAR **)v13;
    v31 = v13;
    v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v31);
    v15 = v12(v11, v14[1].Reserved.Reserved1, &v30);
    v6 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x86,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\tilestoremigrationrecovery.cpp",
        (const char *)(unsigned int)v15,
        v26);
LABEL_13:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
      goto LABEL_8;
    }
    v29 = 0;
    v16 = v27;
    v17 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v27 + 320LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    v18 = v17(v16, v30, &v29);
    v6 = v18;
    if ( v18 >= 0 )
    {
      v32 = 0;
      v18 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v29 + 56LL))(v29, &v32);
      v6 = v18;
      if ( v18 >= 0 )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= v32 )
            goto LABEL_27;
          v31 = 0;
          v21 = v29;
          v22 = *(__int64 (__fastcall **)(__int64, _QWORD, const WCHAR **))(*(_QWORD *)v29 + 48LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
          v23 = v22(v21, i, &v31);
          v6 = v23;
          if ( v23 < 0 )
            break;
          LOBYTE(v26) = 0;
          v23 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, int *))(*(_QWORD *)v28 + 56LL))(v28, v31, &v26);
          v6 = v23;
          if ( v23 < 0 )
          {
            v25 = 146;
            goto LABEL_31;
          }
          if ( !(_BYTE)v26 )
          {
            *(_BYTE *)a2 = 1;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
LABEL_27:
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
            v6 = 0;
            goto LABEL_28;
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
        }
        v25 = 144;
LABEL_31:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v25,
          (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\tilestoremigrationrecovery.cpp",
          (const char *)(unsigned int)v23,
          v26);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
        goto LABEL_17;
      }
      v19 = 140;
    }
    else
    {
      v19 = 137;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\tilestoremigrationrecovery.cpp",
      (const char *)(unsigned int)v18,
      v26);
LABEL_17:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    goto LABEL_13;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x7B,
    (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\tilestoremigrationrecovery.cpp",
    (const char *)(unsigned int)v5,
    v26);
LABEL_28:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  return v6;
}

```

## disassembly

```asm
0x180065230  mov     [rsp-8+arg_10], rbx
0x180065235  push    rbp
0x180065236  push    rsi
0x180065237  push    rdi
0x180065238  push    r14
0x18006523a  push    r15
0x18006523c  lea     rbp, [rsp-37h]
0x180065241  sub     rsp, 90h
0x180065248  mov     rax, cs:__security_cookie
0x18006524f  xor     rax, rsp
0x180065252  mov     [rbp+57h+var_30], rax
0x180065256  mov     r14, rdx
0x180065259  mov     rsi, rcx
0x18006525c  xor     r15d, r15d
0x18006525f  mov     [rdx], r15b
0x180065262  mov     [rbp+57h+var_58], r15
0x180065266  mov     [rbp+57h+var_38], r15
0x18006526a  lea     r9d, [r15+25h]; unsigned int
0x18006526e  lea     r8d, [r15+26h]; unsigned int
0x180065272  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_User@@3QBGB; "Windows.Internal.StateRepository.User"
0x180065279  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18006527d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180065282  lea     rdx, [rbp+57h+var_58]
0x180065286  mov     rcx, [rbp+57h+var_38]
0x18006528a  call    ??$GetActivationFactory@V?$ComPtr@UIUserStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUserStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics>>)
0x18006528f  mov     ebx, eax
0x180065291  test    eax, eax
0x180065293  jns     short loc_1800652B1
0x180065295  mov     rcx, [rbp+5Fh]; this
0x180065299  mov     r9d, eax; char *
0x18006529c  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x1800652a3  lea     edx, [r15+7Bh]; void *
0x1800652a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800652ac  jmp     loc_180065527
0x1800652b1  mov     [rbp+57h+var_88], r15
0x1800652b5  mov     [rbp+57h+var_38], r15
0x1800652b9  mov     edi, 2Ch ; ','
0x1800652be  mov     r9d, edi; unsigned int
0x1800652c1  lea     r8d, [rdi+1]; unsigned int
0x1800652c5  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x1800652cc  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800652d0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800652d5  mov     rbx, [rbp+57h+var_38]
0x1800652d9  lea     rcx, [rbp+57h+var_88]
0x1800652dd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800652e2  lea     r8, [rbp+57h+var_88]
0x1800652e6  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x1800652ed  mov     rcx, rbx
0x1800652f0  call    cs:__imp_RoGetActivationFactory
0x1800652f6  mov     ebx, eax
0x1800652f8  test    eax, eax
0x1800652fa  jns     short loc_180065321
0x1800652fc  mov     rcx, [rbp+5Fh]; this
0x180065300  mov     r9d, eax; char *
0x180065303  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x18006530a  lea     edx, [rdi+53h]; void *
0x18006530d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065312  nop
0x180065313  lea     rcx, [rbp+57h+var_88]
0x180065317  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006531c  jmp     loc_180065527
0x180065321  mov     [rbp+57h+var_80], r15
0x180065325  mov     [rbp+57h+var_38], r15
0x180065329  mov     r9d, edi; unsigned int
0x18006532c  mov     r8d, 2Dh ; '-'; unsigned int
0x180065332  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_PrimaryTile@@3QBGB; "Windows.Internal.StateRepository.Primar"...
0x180065339  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18006533d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180065342  mov     rbx, [rbp+57h+var_38]
0x180065346  lea     rcx, [rbp+57h+var_80]
0x18006534a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006534f  lea     r8, [rbp+57h+var_80]
0x180065353  lea     rdx, _GUID_d4df57cc_8228_4f18_8f78_a705d8416b07
0x18006535a  mov     rcx, rbx
0x18006535d  call    cs:__imp_RoGetActivationFactory
0x180065363  mov     ebx, eax
0x180065365  test    eax, eax
0x180065367  jns     short loc_18006538D
0x180065369  mov     rcx, [rbp+5Fh]; this
0x18006536d  mov     r9d, eax; char *
0x180065370  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x180065377  mov     edx, 83h; void *
0x18006537c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065381  nop
0x180065382  lea     rcx, [rbp+57h+var_80]
0x180065386  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006538b  jmp     short loc_180065313
0x18006538d  mov     [rbp+57h+var_70], r15
0x180065391  mov     rbx, [rbp+57h+var_58]
0x180065395  mov     rax, [rbx]
0x180065398  mov     rdi, [rax+50h]
0x18006539c  lea     rcx, [rbp+57h+var_70]
0x1800653a0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800653a5  lea     rax, [rsi+40h]
0x1800653a9  cmp     qword ptr [rax+18h], 7
0x1800653ae  jbe     short loc_1800653B3
0x1800653b0  mov     rax, [rax]
0x1800653b3  mov     [rbp+57h+var_68], rax
0x1800653b7  lea     rdx, [rbp+57h+var_68]
0x1800653bb  lea     rcx, [rbp+57h+hstringHeader]
0x1800653bf  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800653c4  nop
0x1800653c5  lea     r8, [rbp+57h+var_70]
0x1800653c9  mov     rdx, [rax+18h]
0x1800653cd  mov     rcx, rbx
0x1800653d0  mov     rax, rdi
0x1800653d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800653d8  mov     ebx, eax
0x1800653da  test    eax, eax
0x1800653dc  jns     short loc_180065402
0x1800653de  mov     rcx, [rbp+5Fh]; this
0x1800653e2  mov     r9d, eax; char *
0x1800653e5  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x1800653ec  mov     edx, 86h; void *
0x1800653f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800653f6  nop
0x1800653f7  lea     rcx, [rbp+57h+var_70]
0x1800653fb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180065400  jmp     short loc_180065382
0x180065402  mov     [rbp+57h+var_78], r15
0x180065406  mov     rdi, [rbp+57h+var_88]
0x18006540a  mov     rax, [rdi]
0x18006540d  mov     rbx, [rax+140h]
0x180065414  lea     rcx, [rbp+57h+var_78]
0x180065418  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006541d  lea     r8, [rbp+57h+var_78]
0x180065421  mov     rdx, [rbp+57h+var_70]
0x180065425  mov     rcx, rdi
0x180065428  mov     rax, rbx
0x18006542b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065430  mov     ebx, eax
0x180065432  test    eax, eax
0x180065434  jns     short loc_18006545A
0x180065436  mov     edx, 89h; void *
0x18006543b  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x180065442  mov     r9d, eax; char *
0x180065445  mov     rcx, [rbp+5Fh]; this
0x180065449  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006544e  nop
0x18006544f  lea     rcx, [rbp+57h+var_78]
0x180065453  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180065458  jmp     short loc_1800653F7
0x18006545a  mov     [rbp+57h+var_60], r15d
0x18006545e  mov     rcx, [rbp+57h+var_78]
0x180065462  mov     rax, [rcx]
0x180065465  lea     rdx, [rbp+57h+var_60]
0x180065469  mov     rax, [rax+38h]
0x18006546d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065472  mov     ebx, eax
0x180065474  test    eax, eax
0x180065476  jns     short loc_18006547F
0x180065478  mov     edx, 8Ch
0x18006547d  jmp     short loc_18006543B
0x18006547f  mov     esi, r15d
0x180065482  cmp     esi, [rbp+57h+var_60]
0x180065485  jnb     short loc_1800654FD
0x180065487  mov     [rbp+57h+var_68], r15
0x18006548b  mov     rdi, [rbp+57h+var_78]
0x18006548f  mov     rax, [rdi]
0x180065492  mov     rbx, [rax+30h]
0x180065496  lea     rcx, [rbp+57h+var_68]
0x18006549a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006549f  lea     r8, [rbp+57h+var_68]
0x1800654a3  mov     edx, esi
0x1800654a5  mov     rcx, rdi
0x1800654a8  mov     rax, rbx
0x1800654ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800654b0  mov     ebx, eax
0x1800654b2  test    eax, eax
0x1800654b4  js      loc_18006555C
0x1800654ba  mov     byte ptr [rbp+57h+var_90], r15b
0x1800654be  mov     rcx, [rbp+57h+var_80]
0x1800654c2  mov     rax, [rcx]
0x1800654c5  lea     r8, [rbp+57h+var_90]
0x1800654c9  mov     rdx, [rbp+57h+var_68]
0x1800654cd  mov     rax, [rax+38h]
0x1800654d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800654d6  mov     ebx, eax
0x1800654d8  test    eax, eax
0x1800654da  js      short loc_180065555
0x1800654dc  cmp     byte ptr [rbp+57h+var_90], r15b
0x1800654e0  jz      short loc_1800654EF
0x1800654e2  lea     rcx, [rbp+57h+var_68]
0x1800654e6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800654eb  inc     esi
0x1800654ed  jmp     short loc_180065482
0x1800654ef  mov     byte ptr [r14], 1
0x1800654f3  lea     rcx, [rbp+57h+var_68]
0x1800654f7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800654fc  nop
0x1800654fd  lea     rcx, [rbp+57h+var_78]
0x180065501  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180065506  nop
0x180065507  lea     rcx, [rbp+57h+var_70]
0x18006550b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180065510  nop
0x180065511  lea     rcx, [rbp+57h+var_80]
0x180065515  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006551a  nop
0x18006551b  lea     rcx, [rbp+57h+var_88]
0x18006551f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180065524  mov     ebx, r15d
0x180065527  lea     rcx, [rbp+57h+var_58]
0x18006552b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180065530  mov     eax, ebx
0x180065532  mov     rcx, [rbp+57h+var_30]
0x180065536  xor     rcx, rsp; StackCookie
0x180065539  call    __security_check_cookie
0x18006553e  mov     rbx, [rsp+0B0h+arg_10]
0x180065546  add     rsp, 90h
0x18006554d  pop     r15
0x18006554f  pop     r14
0x180065551  pop     rdi
0x180065552  pop     rsi
0x180065553  pop     rbp
0x180065554  retn
0x180065555  mov     edx, 92h
0x18006555a  jmp     short loc_180065561
0x18006555c  mov     edx, 90h; void *
0x180065561  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x180065568  mov     r9d, eax; char *
0x18006556b  mov     rcx, [rbp+5Fh]; this
0x18006556f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065574  nop
0x180065575  lea     rcx, [rbp+57h+var_68]
0x180065579  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006557e  jmp     loc_18006544F
```
