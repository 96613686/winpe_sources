# SystemSettings::StorageSenseHandlers::CAppNotificationSink::Init(SystemSettings::StorageSenseHandlers::CAppListHelper *)

- ea: `0x1800aa230`
- end: `0x1800aa562`
- name: `?Init@CAppNotificationSink@StorageSenseHandlers@SystemSettings@@QEAAJPEAVCAppListHelper@23@@Z`
- size: `818`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppNotificationSink *__hidden this, struct SystemSettings::StorageSenseHandlers::CAppListHelper *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800a3204`

## callees

- `0x180006e50`
- `0x180008a80`
- `0x18000aa20`
- `0x18000c964`
- `0x18000e6cc`
- `0x180019fa8`
- `0x18001f468`
- `0x180043f48`
- `0x1800a0e4c`
- `0x1800a0eec`
- `0x1800a12f4`
- `0x1800aa230`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800aa2a5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800aa2a5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800aa2dd`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800aa2dd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800aa344`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800aa344`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800aa2e9`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800aa2e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppNotificationSink::Init(
        SystemSettings::StorageSenseHandlers::CAppNotificationSink *this,
        struct SystemSettings::StorageSenseHandlers::CAppListHelper *a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rdx
  HANDLE EventW; // rax
  __int64 v7; // rbx
  int ActivationFactory; // eax
  __int64 v9; // rdx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, char *); // rbx
  _QWORD *v12; // r14
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  DWORD dwCreationFlags; // [rsp+20h] [rbp-60h]
  __int64 v24; // [rsp+30h] [rbp-50h] BYREF
  __int64 v25; // [rsp+38h] [rbp-48h] BYREF
  SystemSettings::StorageSenseHandlers::CAppNotificationSink *v26; // [rsp+40h] [rbp-40h] BYREF
  __int64 v27; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v28[8]; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  __int64 v30; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  if ( a2 )
  {
    *((_QWORD *)this + 4) = a2;
    if ( IsDesktopSKU() || (unsigned __int8)IsCpmcGetContainerIdForUserPresent() )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      *((_QWORD *)this + 9) = EventW;
      if ( !EventW )
        return 2147942414LL;
      *((_QWORD *)this + 8) = CreateThread(
                                0,
                                0,
                                lambda_5d8abe126ccde22c1560365abf811aa4_::_lambda_invoker_cdecl_,
                                this,
                                0,
                                0);
    }
    v3 = RoInitialize(1);
    if ( (v3 & 0x80000000) != 0 )
    {
      v4 = 3019;
      goto LABEL_3;
    }
    v27 = 0;
    v30 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.ApplicationModel.PackageCatalog",
      0x28u,
      0x27u);
    v7 = v30;
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v27);
    ActivationFactory = RoGetActivationFactory(v7, &GUID_a18c9696_e65b_4634_ba21_5e63eb7244a7, &v27);
    v3 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v10 = v27;
      v11 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v27 + 56LL);
      v12 = (_QWORD *)((char *)this + 40);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease((char *)this + 40);
      ActivationFactory = v11(v10, (char *)this + 40);
      v3 = ActivationFactory;
      if ( ActivationFactory >= 0 )
      {
        v26 = this;
        Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v26);
        v13 = lambda_7d85c6fafbd7d5d8be22d9bc65ba599d_::_lambda_7d85c6fafbd7d5d8be22d9bc65ba599d_(v28, &v26);
        wil::MakeAgileCallback_Windows::Foundation::ITypedEventHandler_Windows::ApplicationModel::PackageCatalog___Windows::ApplicationModel::PackageInstallingEventArgs_____lambda_7d85c6fafbd7d5d8be22d9bc65ba599d___(
          &v25,
          v13);
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(v28);
        v14 = lambda_7d85c6fafbd7d5d8be22d9bc65ba599d_::_lambda_7d85c6fafbd7d5d8be22d9bc65ba599d_(v28, &v26);
        wil::MakeAgileCallback_Windows::Foundation::ITypedEventHandler_Windows::ApplicationModel::PackageCatalog___Windows::ApplicationModel::PackageUninstallingEventArgs_____lambda_272c37809e2571d6dda7ecd38f07dcfe___(
          &v24,
          v14);
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(v28);
        v15 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v12 + 64LL))(
                *v12,
                v25,
                (char *)this + 48);
        v3 = v15;
        if ( v15 >= 0 )
        {
          v18 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v12 + 96LL))(
                  *v12,
                  v24,
                  (char *)this + 56);
          v3 = v18;
          if ( v18 >= 0 )
          {
            v21 = v24;
            if ( v24 )
            {
              v24 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
            }
            v22 = v25;
            if ( v25 )
            {
              v25 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
            }
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v26);
            v3 = 0;
            goto LABEL_33;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC12,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
            (const char *)(unsigned int)v18,
            dwCreationFlags);
          v19 = v24;
          if ( v24 )
          {
            v24 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          }
          v20 = v25;
          if ( v25 )
          {
            v25 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC0E,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
            (const char *)(unsigned int)v15,
            dwCreationFlags);
          v16 = v24;
          if ( v24 )
          {
            v24 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          }
          v17 = v25;
          if ( v25 )
          {
            v25 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          }
        }
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v26);
LABEL_33:
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v27);
        return v3;
      }
      v9 = 3026;
    }
    else
    {
      v9 = 3024;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
      (const char *)(unsigned int)ActivationFactory,
      dwCreationFlags);
    goto LABEL_33;
  }
  v3 = -2147024809;
  v4 = 2927;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
    (const char *)v3,
    dwCreationFlags);
  return v3;
}

```

## disassembly

```asm
0x1800aa230  mov     [rsp-18h+arg_8], rbx
0x1800aa235  mov     [rsp-18h+arg_10], rsi
0x1800aa23a  push    rbp
0x1800aa23b  push    rdi
0x1800aa23c  push    r14
0x1800aa23e  mov     rbp, rsp
0x1800aa241  sub     rsp, 80h
0x1800aa248  mov     rax, cs:__security_cookie
0x1800aa24f  xor     rax, rsp
0x1800aa252  mov     [rbp+var_8], rax
0x1800aa256  mov     rsi, rcx
0x1800aa259  test    rdx, rdx
0x1800aa25c  jnz     short loc_1800AA280
0x1800aa25e  mov     ebx, 80070057h
0x1800aa263  mov     edx, 0B6Fh; void *
0x1800aa268  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800aa26f  mov     r9d, ebx; char *
0x1800aa272  mov     rcx, [rbp+18h]; this
0x1800aa276  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aa27b  jmp     loc_1800AA53C
0x1800aa280  mov     [rcx+20h], rdx
0x1800aa284  call    ?IsDesktopSKU@@YA_NXZ; IsDesktopSKU(void)
0x1800aa289  mov     ebx, 1
0x1800aa28e  cmp     al, bl
0x1800aa290  jz      short loc_1800AA29B
0x1800aa292  call    IsCpmcGetContainerIdForUserPresent
0x1800aa297  test    al, al
0x1800aa299  jz      short loc_1800AA2E7
0x1800aa29b  xor     r9d, r9d; lpName
0x1800aa29e  xor     r8d, r8d; bInitialState
0x1800aa2a1  mov     edx, ebx; bManualReset
0x1800aa2a3  xor     ecx, ecx; lpEventAttributes
0x1800aa2a5  call    cs:__imp_CreateEventW
0x1800aa2ab  mov     [rsi+48h], rax
0x1800aa2af  test    rax, rax
0x1800aa2b2  jnz     short loc_1800AA2BE
0x1800aa2b4  mov     eax, 8007000Eh
0x1800aa2b9  jmp     loc_1800AA53E
0x1800aa2be  mov     [rsp+80h+lpThreadId], 0; lpThreadId
0x1800aa2c7  mov     [rsp+80h+dwCreationFlags], 0; int
0x1800aa2cf  mov     r9, rsi; lpParameter
0x1800aa2d2  lea     r8, _lambda_5d8abe126ccde22c1560365abf811aa4____lambda_invoker_cdecl_; lpStartAddress
0x1800aa2d9  xor     edx, edx; dwStackSize
0x1800aa2db  xor     ecx, ecx; lpThreadAttributes
0x1800aa2dd  call    cs:__imp_CreateThread
0x1800aa2e3  mov     [rsi+40h], rax
0x1800aa2e7  mov     ecx, ebx
0x1800aa2e9  call    cs:__imp_RoInitialize
0x1800aa2ef  mov     ebx, eax
0x1800aa2f1  test    eax, eax
0x1800aa2f3  jns     short loc_1800AA2FF
0x1800aa2f5  mov     edx, 0BCBh
0x1800aa2fa  jmp     loc_1800AA268
0x1800aa2ff  mov     [rbp+var_38], 0
0x1800aa307  mov     [rbp+var_10], 0
0x1800aa30f  mov     r9d, 27h ; '''; unsigned int
0x1800aa315  lea     r8d, [r9+1]; unsigned int
0x1800aa319  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_PackageCatalog@@3QBGB; "Windows.ApplicationModel.PackageCatalog"
0x1800aa320  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800aa324  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800aa329  mov     rbx, [rbp+var_10]
0x1800aa32d  lea     rcx, [rbp+var_38]
0x1800aa331  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800aa336  lea     r8, [rbp+var_38]
0x1800aa33a  lea     rdx, _GUID_a18c9696_e65b_4634_ba21_5e63eb7244a7
0x1800aa341  mov     rcx, rbx
0x1800aa344  call    cs:__imp_RoGetActivationFactory
0x1800aa34a  mov     ebx, eax
0x1800aa34c  test    eax, eax
0x1800aa34e  jns     short loc_1800AA357
0x1800aa350  mov     edx, 0BD0h
0x1800aa355  jmp     short loc_1800AA387
0x1800aa357  mov     rdi, [rbp+var_38]
0x1800aa35b  mov     rax, [rdi]
0x1800aa35e  mov     rbx, [rax+38h]
0x1800aa362  lea     r14, [rsi+28h]
0x1800aa366  mov     rcx, r14
0x1800aa369  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800aa36e  mov     rdx, r14
0x1800aa371  mov     rcx, rdi
0x1800aa374  mov     rax, rbx
0x1800aa377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa37c  mov     ebx, eax
0x1800aa37e  test    eax, eax
0x1800aa380  jns     short loc_1800AA39F
0x1800aa382  mov     edx, 0BD2h; void *
0x1800aa387  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800aa38e  mov     r9d, eax; char *
0x1800aa391  mov     rcx, [rbp+18h]; this
0x1800aa395  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aa39a  jmp     loc_1800AA533
0x1800aa39f  mov     [rbp+var_40], rsi
0x1800aa3a3  lea     rcx, [rbp+var_40]
0x1800aa3a7  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800aa3ac  nop
0x1800aa3ad  lea     rdx, [rbp+var_40]
0x1800aa3b1  lea     rcx, [rbp+var_30]
0x1800aa3b5  call    _lambda_7d85c6fafbd7d5d8be22d9bc65ba599d____lambda_7d85c6fafbd7d5d8be22d9bc65ba599d_
0x1800aa3ba  nop
0x1800aa3bb  mov     rdx, rax
0x1800aa3be  lea     rcx, [rbp+var_48]
0x1800aa3c2  call    wil__MakeAgileCallback_Windows__Foundation__ITypedEventHandler_Windows__ApplicationModel__PackageCatalog___Windows__ApplicationModel__PackageInstallingEventArgs_____lambda_7d85c6fafbd7d5d8be22d9bc65ba599d___
0x1800aa3c7  nop
0x1800aa3c8  lea     rcx, [rbp+var_30]; void *
0x1800aa3cc  call    ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
0x1800aa3d1  lea     rdx, [rbp+var_40]
0x1800aa3d5  lea     rcx, [rbp+var_30]
0x1800aa3d9  call    _lambda_7d85c6fafbd7d5d8be22d9bc65ba599d____lambda_7d85c6fafbd7d5d8be22d9bc65ba599d_
0x1800aa3de  nop
0x1800aa3df  mov     rdx, rax
0x1800aa3e2  lea     rcx, [rbp+var_50]
0x1800aa3e6  call    wil__MakeAgileCallback_Windows__Foundation__ITypedEventHandler_Windows__ApplicationModel__PackageCatalog___Windows__ApplicationModel__PackageUninstallingEventArgs_____lambda_272c37809e2571d6dda7ecd38f07dcfe___
0x1800aa3eb  nop
0x1800aa3ec  lea     rcx, [rbp+var_30]; void *
0x1800aa3f0  call    ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
0x1800aa3f5  mov     rcx, [r14]
0x1800aa3f8  mov     rax, [rcx]
0x1800aa3fb  lea     r8, [rsi+30h]
0x1800aa3ff  mov     rdx, [rbp+var_48]
0x1800aa403  mov     rax, [rax+40h]
0x1800aa407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa40c  mov     ebx, eax
0x1800aa40e  test    eax, eax
0x1800aa410  jns     short loc_1800AA475
0x1800aa412  mov     rcx, [rbp+18h]; this
0x1800aa416  mov     r9d, eax; char *
0x1800aa419  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800aa420  mov     edx, 0C0Eh; void *
0x1800aa425  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aa42a  nop
0x1800aa42b  mov     rcx, [rbp+var_50]
0x1800aa42f  test    rcx, rcx
0x1800aa432  jz      short loc_1800AA449
0x1800aa434  mov     [rbp+var_50], 0
0x1800aa43c  mov     rax, [rcx]
0x1800aa43f  mov     rax, [rax+10h]
0x1800aa443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa448  nop
0x1800aa449  mov     rcx, [rbp+var_48]
0x1800aa44d  test    rcx, rcx
0x1800aa450  jz      short loc_1800AA467
0x1800aa452  mov     [rbp+var_48], 0
0x1800aa45a  mov     rax, [rcx]
0x1800aa45d  mov     rax, [rax+10h]
0x1800aa461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa466  nop
0x1800aa467  lea     rcx, [rbp+var_40]
0x1800aa46b  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800aa470  jmp     loc_1800AA533
0x1800aa475  mov     rcx, [r14]
0x1800aa478  mov     rax, [rcx]
0x1800aa47b  lea     r8, [rsi+38h]
0x1800aa47f  mov     rdx, [rbp+var_50]
0x1800aa483  mov     rax, [rax+60h]
0x1800aa487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa48c  mov     ebx, eax
0x1800aa48e  test    eax, eax
0x1800aa490  jns     short loc_1800AA4EC
0x1800aa492  mov     rcx, [rbp+18h]; this
0x1800aa496  mov     r9d, eax; char *
0x1800aa499  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800aa4a0  mov     edx, 0C12h; void *
0x1800aa4a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aa4aa  nop
0x1800aa4ab  mov     rcx, [rbp+var_50]
0x1800aa4af  test    rcx, rcx
0x1800aa4b2  jz      short loc_1800AA4C9
0x1800aa4b4  mov     [rbp+var_50], 0
0x1800aa4bc  mov     rax, [rcx]
0x1800aa4bf  mov     rax, [rax+10h]
0x1800aa4c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa4c8  nop
0x1800aa4c9  mov     rcx, [rbp+var_48]
0x1800aa4cd  test    rcx, rcx
0x1800aa4d0  jz      short loc_1800AA4E7
0x1800aa4d2  mov     [rbp+var_48], 0
0x1800aa4da  mov     rax, [rcx]
0x1800aa4dd  mov     rax, [rax+10h]
0x1800aa4e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa4e6  nop
0x1800aa4e7  jmp     loc_1800AA467
0x1800aa4ec  mov     rcx, [rbp+var_50]
0x1800aa4f0  test    rcx, rcx
0x1800aa4f3  jz      short loc_1800AA50A
0x1800aa4f5  mov     [rbp+var_50], 0
0x1800aa4fd  mov     rax, [rcx]
0x1800aa500  mov     rax, [rax+10h]
0x1800aa504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa509  nop
0x1800aa50a  mov     rcx, [rbp+var_48]
0x1800aa50e  test    rcx, rcx
0x1800aa511  jz      short loc_1800AA528
0x1800aa513  mov     [rbp+var_48], 0
0x1800aa51b  mov     rax, [rcx]
0x1800aa51e  mov     rax, [rax+10h]
0x1800aa522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa527  nop
0x1800aa528  lea     rcx, [rbp+var_40]
0x1800aa52c  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800aa531  xor     ebx, ebx
0x1800aa533  lea     rcx, [rbp+var_38]
0x1800aa537  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800aa53c  mov     eax, ebx
0x1800aa53e  mov     rcx, [rbp+var_8]
0x1800aa542  xor     rcx, rsp; StackCookie
0x1800aa545  call    __security_check_cookie
0x1800aa54a  lea     r11, [rsp+80h+var_s0]
0x1800aa552  mov     rbx, [r11+28h]
0x1800aa556  mov     rsi, [r11+30h]
0x1800aa55a  mov     rsp, r11
0x1800aa55d  pop     r14
0x1800aa55f  pop     rdi
0x1800aa560  pop     rbp
0x1800aa561  retn
```
