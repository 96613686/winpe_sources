# GeotagBrokerImpl::SetGeotagInBrokerWithPathAsync(IInspectable *,HSTRING__ *,uint,Windows::Foundation::IAsyncAction * *)

- ea: `0x180020560`
- end: `0x18002074b`
- name: `?SetGeotagInBrokerWithPathAsync@GeotagBrokerImpl@@UEAAJPEAUIInspectable@@PEAUHSTRING__@@IPEAPEAUIAsyncAction@Foundation@Windows@@@Z`
- size: `491`
- prototype: `__int64 __fastcall(GeotagBrokerImpl *this, struct IInspectable *, HSTRING, int, struct Windows::Foundation::IAsyncAction **)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180018160`
- `0x18001b710`
- `0x1800204e8`
- `0x180020560`
- `0x180020c48`
- `0x180020d50`
- `0x180020d98`
- `0x180020df8`
- `0x180020e34`
- `0x180026920`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180020640`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180020640`

## string_xrefs

- `0x1800205d5`: `avcore\mf\photography\components\geotag\lib\geotag.cpp`
- `0x180020650`: `avcore\mf\photography\components\geotag\lib\geotag.cpp`
- `0x1800206a1`: `avcore\mf\photography\components\geotag\lib\geotag.cpp`

## pseudocode

```c
__int64 __fastcall GeotagBrokerImpl::SetGeotagInBrokerWithPathAsync(
        GeotagBrokerImpl *this,
        struct IInspectable *a2,
        HSTRING a3,
        int a4,
        struct Windows::Foundation::IAsyncAction **a5)
{
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rbx
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rbx
  int ActivationFactory; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rax
  __int64 v17; // r8
  int v19; // [rsp+20h] [rbp-41h]
  __int64 v20; // [rsp+30h] [rbp-31h] BYREF
  __int64 v21; // [rsp+38h] [rbp-29h] BYREF
  __int64 v22; // [rsp+40h] [rbp-21h] BYREF
  _BYTE v23[12]; // [rsp+48h] [rbp-19h] BYREF
  int v24; // [rsp+58h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-1h] BYREF
  __int64 v26; // [rsp+78h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+57h]

  v24 = a4;
  v22 = 0;
  *a5 = 0;
  QueryInterface = a2->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  v9 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 *))QueryInterface)(
         a2,
         &GUID_88b336bc_6f1b_482f_be30_25a9fb5566ed,
         &v22);
  v10 = v9;
  if ( v9 >= 0 )
  {
    *(_QWORD *)v23 = this;
    Microsoft::WRL::ComPtr<GeotagBrokerImpl>::InternalAddRef(v23);
    v20 = 0;
    v26 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Storage.StorageFile",
      0x1Cu,
      0x1Bu);
    v11 = v26;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    ActivationFactory = RoGetActivationFactory(v11, &GUID_5984c710_daf2_43c8_8bb4_a4d3eacfd03f, &v20);
    v10 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v13 = v20;
      v21 = 0;
      v14 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v20 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
      v15 = v14(v13, a3, &v21);
      v10 = v15;
      if ( v15 >= 0 )
      {
        v16 = lambda_fe1a134061f42bfd75b30cefdece098e_::_lambda_fe1a134061f42bfd75b30cefdece098e_(
                (unsigned int)&hstringHeader,
                (unsigned int)&v22,
                (unsigned int)v23,
                (unsigned int)&v24,
                (__int64)&v21);
        *(_DWORD *)v23 = 3;
        *(_QWORD *)&v23[4] = 128;
        v10 = Windows::Internal::MakeAsyncAction_Microsoft::WRL::AsyncCausalityOptions__GeotagBroker_SetGeotagInBrokerWithPathAsync__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows::Internal::ComTaskPoolHandler__lambda_fe1a134061f42bfd75b30cefdece098e___(
                v23,
                a5,
                v17,
                v16);
        lambda_fe1a134061f42bfd75b30cefdece098e_::__lambda_fe1a134061f42bfd75b30cefdece098e_(&hstringHeader);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x337,
          (unsigned int)"avcore\\mf\\photography\\components\\geotag\\lib\\geotag.cpp",
          (const char *)(unsigned int)v15,
          v19);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x334,
        (unsigned int)"avcore\\mf\\photography\\components\\geotag\\lib\\geotag.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v19);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    if ( this )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::IGeotagBroker,Microsoft::WRL::FtmBase>::Release(this);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x330,
      (unsigned int)"avcore\\mf\\photography\\components\\geotag\\lib\\geotag.cpp",
      (const char *)(unsigned int)v9,
      v19);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  return v10;
}

```

## disassembly

```asm
0x180020560  mov     [rsp-8+arg_0], rbx
0x180020565  push    rbp
0x180020566  push    rsi
0x180020567  push    rdi
0x180020568  push    r14
0x18002056a  push    r15
0x18002056c  lea     rbp, [rsp-2Fh]
0x180020571  sub     rsp, 90h
0x180020578  mov     rax, cs:__security_cookie
0x18002057f  xor     rax, rsp
0x180020582  mov     [rbp+4Fh+var_30], rax
0x180020586  mov     r15, [rbp+4Fh+arg_20]
0x18002058a  mov     rsi, rcx
0x18002058d  lea     rcx, [rbp+4Fh+var_70]
0x180020591  mov     [rbp+4Fh+var_58], r9d
0x180020595  mov     r14, r8
0x180020598  mov     [rbp+4Fh+var_70], 0
0x1800205a0  mov     rdi, rdx
0x1800205a3  mov     qword ptr [r15], 0
0x1800205aa  mov     rax, [rdx]
0x1800205ad  mov     rbx, [rax]
0x1800205b0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800205b5  lea     r8, [rbp+4Fh+var_70]
0x1800205b9  mov     rcx, rdi
0x1800205bc  lea     rdx, _GUID_88b336bc_6f1b_482f_be30_25a9fb5566ed
0x1800205c3  mov     rax, rbx
0x1800205c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205cb  mov     ebx, eax
0x1800205cd  test    eax, eax
0x1800205cf  jns     short loc_1800205EE
0x1800205d1  mov     rcx, [rbp+57h]; this
0x1800205d5  lea     r8, aAvcoreMfPhotog; "avcore\\mf\\photography\\components\\ge"...
0x1800205dc  mov     r9d, eax; char *
0x1800205df  mov     edx, 330h; void *
0x1800205e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800205e9  jmp     loc_18002071D
0x1800205ee  lea     rcx, [rbp+4Fh+var_68]
0x1800205f2  mov     [rbp+4Fh+var_68], rsi
0x1800205f6  call    ?InternalAddRef@?$ComPtr@VGeotagBrokerImpl@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<GeotagBrokerImpl>::InternalAddRef(void)
0x1800205fb  mov     r9d, 1Bh; unsigned int
0x180020601  mov     [rbp+4Fh+var_80], 0
0x180020609  lea     rdx, ?RuntimeClass_Windows_Storage_StorageFile@@3QBGB; "Windows.Storage.StorageFile"
0x180020610  mov     [rbp+4Fh+var_38], 0
0x180020618  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x18002061c  lea     r8d, [r9+1]; unsigned int
0x180020620  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180020625  mov     rbx, [rbp+4Fh+var_38]
0x180020629  lea     rcx, [rbp+4Fh+var_80]
0x18002062d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020632  lea     r8, [rbp+4Fh+var_80]
0x180020636  mov     rcx, rbx
0x180020639  lea     rdx, _GUID_5984c710_daf2_43c8_8bb4_a4d3eacfd03f
0x180020640  call    cs:__imp_RoGetActivationFactory
0x180020646  mov     ebx, eax
0x180020648  test    eax, eax
0x18002064a  jns     short loc_180020669
0x18002064c  mov     rcx, [rbp+57h]; this
0x180020650  lea     r8, aAvcoreMfPhotog; "avcore\\mf\\photography\\components\\ge"...
0x180020657  mov     r9d, eax; char *
0x18002065a  mov     edx, 334h; void *
0x18002065f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020664  jmp     loc_180020707
0x180020669  mov     rdi, [rbp+4Fh+var_80]
0x18002066d  lea     rcx, [rbp+4Fh+var_78]
0x180020671  mov     [rbp+4Fh+var_78], 0
0x180020679  mov     rax, [rdi]
0x18002067c  mov     rbx, [rax+30h]
0x180020680  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020685  lea     r8, [rbp+4Fh+var_78]
0x180020689  mov     rdx, r14
0x18002068c  mov     rcx, rdi
0x18002068f  mov     rax, rbx
0x180020692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020697  mov     ebx, eax
0x180020699  test    eax, eax
0x18002069b  jns     short loc_1800206B7
0x18002069d  mov     rcx, [rbp+57h]; this
0x1800206a1  lea     r8, aAvcoreMfPhotog; "avcore\\mf\\photography\\components\\ge"...
0x1800206a8  mov     r9d, eax; char *
0x1800206ab  mov     edx, 337h; void *
0x1800206b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800206b5  jmp     short loc_1800206FE
0x1800206b7  lea     rax, [rbp+4Fh+var_78]
0x1800206bb  lea     r9, [rbp+4Fh+var_58]
0x1800206bf  mov     qword ptr [rsp+0B0h+var_90], rax
0x1800206c4  lea     r8, [rbp+4Fh+var_68]
0x1800206c8  lea     rdx, [rbp+4Fh+var_70]
0x1800206cc  lea     rcx, [rbp+4Fh+hstringHeader]
0x1800206d0  call    _lambda_fe1a134061f42bfd75b30cefdece098e____lambda_fe1a134061f42bfd75b30cefdece098e_
0x1800206d5  mov     r9, rax
0x1800206d8  mov     dword ptr [rbp+4Fh+var_68], 3
0x1800206df  mov     rdx, r15
0x1800206e2  mov     [rbp+4Fh+var_68+4], 80h
0x1800206ea  lea     rcx, [rbp+4Fh+var_68]
0x1800206ee  call    Windows__Internal__MakeAsyncAction_Microsoft__WRL__AsyncCausalityOptions__GeotagBroker_SetGeotagInBrokerWithPathAsync__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows__Internal__ComTaskPoolHandler__lambda_fe1a134061f42bfd75b30cefdece098e___
0x1800206f3  lea     rcx, [rbp+4Fh+hstringHeader]
0x1800206f7  mov     ebx, eax
0x1800206f9  call    _lambda_fe1a134061f42bfd75b30cefdece098e_____lambda_fe1a134061f42bfd75b30cefdece098e_
0x1800206fe  lea     rcx, [rbp+4Fh+var_78]
0x180020702  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020707  lea     rcx, [rbp+4Fh+var_80]
0x18002070b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020710  test    rsi, rsi
0x180020713  jz      short loc_18002071D
0x180020715  mov     rcx, rsi
0x180020718  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIGeotagBroker@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::IGeotagBroker,Microsoft::WRL::FtmBase>::Release(void)
0x18002071d  lea     rcx, [rbp+4Fh+var_70]
0x180020721  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020726  mov     eax, ebx
0x180020728  mov     rcx, [rbp+4Fh+var_30]
0x18002072c  xor     rcx, rsp; StackCookie
0x18002072f  call    __security_check_cookie
0x180020734  mov     rbx, [rsp+0B0h+arg_0]
0x18002073c  add     rsp, 90h
0x180020743  pop     r15
0x180020745  pop     r14
0x180020747  pop     rdi
0x180020748  pop     rsi
0x180020749  pop     rbp
0x18002074a  retn
```
