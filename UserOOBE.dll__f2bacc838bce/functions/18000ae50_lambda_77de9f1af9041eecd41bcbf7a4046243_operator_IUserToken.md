# _lambda_77de9f1af9041eecd41bcbf7a4046243_::operator()(IUserToken * *)

- ea: `0x18000ae50`
- end: `0x18000b05a`
- name: `??R_lambda_77de9f1af9041eecd41bcbf7a4046243_@@QEBA@PEAPEAUIUserToken@@@Z`
- size: `522`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800094b4`

## callees

- `0x1800067b0`
- `0x180009250`
- `0x1800098dc`
- `0x18000a5a4`
- `0x18000ae50`
- `0x18000b518`
- `0x18000be8c`
- `0x18000beb0`
- `0x18000e2bc`
- `0x18000e528`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000aed2`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000aed2`

## string_xrefs

- `0x18000b009`: `shell\oobe\user\dll\oobebrokermanager.cpp`
- `0x18000b01e`: `shell\oobe\user\dll\oobebrokermanager.cpp`
- `0x18000b033`: `shell\oobe\user\dll\oobebrokermanager.cpp`
- `0x18000b048`: `shell\oobe\user\dll\oobebrokermanager.cpp`
- `0x18000aff4`: `onecore\internal\sdk\inc\wil\opensource/wil/wrl.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall _lambda_77de9f1af9041eecd41bcbf7a4046243_::operator()(_QWORD *a1, _QWORD *a2)
{
  const struct _GUID *v3; // rdx
  const struct _GUID *v4; // rcx
  int ElevatedObject; // eax
  HRESULT v6; // eax
  int v7; // eax
  IUnknown *v8; // rdi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rbx
  DWORD dwAuthnLevel; // [rsp+20h] [rbp-50h]
  DWORD dwAuthnLevela; // [rsp+20h] [rbp-50h]
  __int64 v17; // [rsp+40h] [rbp-30h] BYREF
  IUnknown *pProxy; // [rsp+48h] [rbp-28h] BYREF
  __int64 v19; // [rsp+50h] [rbp-20h] BYREF
  __int64 v20; // [rsp+58h] [rbp-18h] BYREF
  __int64 v21; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  unsigned int v23; // [rsp+90h] [rbp+20h] BYREF
  __int64 v24; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v25; // [rsp+A8h] [rbp+38h] BYREF

  LODWORD(v24) = 0;
  InitializeAndReturnIfNecessary<IAuthBuffer,_lambda_5e8097f6559466f0c538964adbdb1f2d_>(&v20, *a1 + 40LL, *a1 + 16LL);
  pProxy = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy);
  ElevatedObject = CloudExperienceHostCreateElevatedObject(v4, v3, (void **)&pProxy);
  if ( ElevatedObject < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBC,
      (unsigned int)"shell\\oobe\\user\\dll\\oobebrokermanager.cpp",
      (const char *)(unsigned int)ElevatedObject,
      dwAuthnLevel);
  v6 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBF,
      (unsigned int)"shell\\oobe\\user\\dll\\oobebrokermanager.cpp",
      (const char *)(unsigned int)v6,
      dwAuthnLevela);
  v19 = 0;
  v23 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 *, unsigned int *))(*(_QWORD *)v20 + 24LL))(v20, &v19, &v23);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC2,
      (unsigned int)"shell\\oobe\\user\\dll\\oobebrokermanager.cpp",
      (const char *)(unsigned int)v7,
      dwAuthnLevela);
  v17 = 0;
  v8 = pProxy;
  QueryInterface = pProxy->lpVtbl[1].QueryInterface;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &v17,
    0);
  v10 = ((__int64 (__fastcall *)(IUnknown *, __int64, _QWORD, __int64 *))QueryInterface)(v8, v19, v23, &v17);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"shell\\oobe\\user\\dll\\oobebrokermanager.cpp",
      (const char *)(unsigned int)v10,
      dwAuthnLevela);
  v11 = v17;
  v17 = 0;
  v21 = v11;
  v25 = 0;
  LODWORD(v24) = 1;
  Microsoft::WRL::ComPtr<UserToken>::InternalRelease(&v25);
  v12 = Microsoft::WRL::Details::MakeAndInitialize<UserToken,UserToken,void *>(&v25, &v21);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/wrl.h",
      (const char *)(unsigned int)v12,
      dwAuthnLevela);
  v13 = v25;
  v24 = v25;
  v25 = 0;
  Microsoft::WRL::ComPtr<UserToken>::InternalRelease(&v25);
  Microsoft::WRL::ComPtr<IAuthBuffer>::InternalAddRef(&v24);
  *a2 = v13;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy);
  return Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
}

```

## disassembly

```asm
0x18000ae50  mov     [rsp-18h+arg_8], rbx
0x18000ae55  push    rbp
0x18000ae56  push    rsi
0x18000ae57  push    rdi
0x18000ae58  mov     rbp, rsp
0x18000ae5b  sub     rsp, 70h
0x18000ae5f  mov     rsi, rdx
0x18000ae62  mov     dword ptr [rbp+arg_10], 0
0x18000ae69  mov     rdx, [rcx]
0x18000ae6c  lea     r8, [rdx+10h]
0x18000ae70  add     rdx, 28h ; '('
0x18000ae74  lea     rcx, [rbp+var_18]
0x18000ae78  call    ??$InitializeAndReturnIfNecessary@UIAuthBuffer@@V_lambda_5e8097f6559466f0c538964adbdb1f2d_@@@@YA?AV?$ComPtr@UIAuthBuffer@@@WRL@Microsoft@@AEAV012@AEAVsrwlock@wil@@$$QEAV_lambda_5e8097f6559466f0c538964adbdb1f2d_@@@Z; InitializeAndReturnIfNecessary<IAuthBuffer,_lambda_5e8097f6559466f0c538964adbdb1f2d_>(Microsoft::WRL::ComPtr<IAuthBuffer> &,wil::srwlock &,_lambda_5e8097f6559466f0c538964adbdb1f2d_ &&)
0x18000ae7d  nop
0x18000ae7e  mov     [rbp+pProxy], 0
0x18000ae86  lea     rcx, [rbp+pProxy]
0x18000ae8a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000ae8f  lea     r8, [rbp+pProxy]; void **
0x18000ae93  call    ?CloudExperienceHostCreateElevatedObject@@YAJAEBU_GUID@@0PEAPEAX@Z; CloudExperienceHostCreateElevatedObject(_GUID const &,_GUID const &,void * *)
0x18000ae98  mov     rcx, [rbp+18h]; this
0x18000ae9c  test    eax, eax
0x18000ae9e  js      loc_18000B006
0x18000aea4  mov     [rsp+70h+dwCapabilities], 0; dwCapabilities
0x18000aeac  mov     [rsp+70h+pAuthInfo], 0; pAuthInfo
0x18000aeb5  mov     [rsp+70h+dwImpLevel], 3; dwImpLevel
0x18000aebd  mov     [rsp+70h+dwAuthnLevel], 0; int
0x18000aec5  xor     r9d, r9d; pServerPrincName
0x18000aec8  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18000aecb  mov     r8d, edx; dwAuthzSvc
0x18000aece  mov     rcx, [rbp+pProxy]; pProxy
0x18000aed2  call    cs:__imp_CoSetProxyBlanket
0x18000aed8  mov     rcx, [rbp+18h]; this
0x18000aedc  test    eax, eax
0x18000aede  js      loc_18000B01B
0x18000aee4  mov     [rbp+var_20], 0
0x18000aeec  mov     [rbp+arg_0], 0
0x18000aef3  mov     rcx, [rbp+var_18]
0x18000aef7  mov     rax, [rcx]
0x18000aefa  lea     r8, [rbp+arg_0]
0x18000aefe  lea     rdx, [rbp+var_20]
0x18000af02  mov     rax, [rax+18h]
0x18000af06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af0b  mov     rcx, [rbp+18h]; this
0x18000af0f  test    eax, eax
0x18000af11  js      loc_18000B030
0x18000af17  mov     [rbp+var_30], 0
0x18000af1f  mov     rdi, [rbp+pProxy]
0x18000af23  mov     rax, [rdi]
0x18000af26  mov     rbx, [rax+18h]
0x18000af2a  xor     edx, edx
0x18000af2c  lea     rcx, [rbp+var_30]
0x18000af30  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000af35  lea     r9, [rbp+var_30]
0x18000af39  mov     r8d, [rbp+arg_0]
0x18000af3d  mov     rdx, [rbp+var_20]
0x18000af41  mov     rcx, rdi
0x18000af44  mov     rax, rbx
0x18000af47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af4c  mov     rcx, [rbp+18h]; this
0x18000af50  test    eax, eax
0x18000af52  js      loc_18000B045
0x18000af58  mov     rax, [rbp+var_30]
0x18000af5c  mov     [rbp+var_30], 0
0x18000af64  mov     [rbp+var_10], rax
0x18000af68  mov     [rbp+arg_18], 0
0x18000af70  mov     dword ptr [rbp+arg_10], 1
0x18000af77  lea     rcx, [rbp+arg_18]
0x18000af7b  call    ?InternalRelease@?$ComPtr@VUserToken@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<UserToken>::InternalRelease(void)
0x18000af80  lea     rdx, [rbp+var_10]
0x18000af84  lea     rcx, [rbp+arg_18]
0x18000af88  call    ??$MakeAndInitialize@VUserToken@@V1@PEAX@Details@WRL@Microsoft@@YAJPEAPEAVUserToken@@$$QEAPEAX@Z; Microsoft::WRL::Details::MakeAndInitialize<UserToken,UserToken,void *>(UserToken * *,void * &&)
0x18000af8d  mov     rcx, [rbp+18h]; this
0x18000af91  test    eax, eax
0x18000af93  js      short loc_18000AFF1
0x18000af95  mov     rbx, [rbp+arg_18]
0x18000af99  mov     [rbp+arg_10], rbx
0x18000af9d  mov     [rbp+arg_18], 0
0x18000afa5  lea     rcx, [rbp+arg_18]
0x18000afa9  call    ?InternalRelease@?$ComPtr@VUserToken@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<UserToken>::InternalRelease(void)
0x18000afae  lea     rcx, [rbp+arg_10]
0x18000afb2  call    ?InternalAddRef@?$ComPtr@UIAuthBuffer@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IAuthBuffer>::InternalAddRef(void)
0x18000afb7  mov     [rsi], rbx
0x18000afba  lea     rcx, [rbp+arg_10]
0x18000afbe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000afc3  nop
0x18000afc4  lea     rcx, [rbp+var_30]
0x18000afc8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000afcd  nop
0x18000afce  lea     rcx, [rbp+pProxy]
0x18000afd2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000afd7  nop
0x18000afd8  lea     rcx, [rbp+var_18]
0x18000afdc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000afe1  mov     rbx, [rsp+70h+arg_8]
0x18000afe9  add     rsp, 70h
0x18000afed  pop     rdi
0x18000afee  pop     rsi
0x18000afef  pop     rbp
0x18000aff0  retn
0x18000aff1  mov     r9d, eax; char *
0x18000aff4  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000affb  mov     edx, 2Bh ; '+'; void *
0x18000b000  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000b006  mov     r9d, eax; char *
0x18000b009  lea     r8, aShellOobeUserD; "shell\\oobe\\user\\dll\\oobebrokermanag"...
0x18000b010  mov     edx, 0BCh; void *
0x18000b015  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000b01b  mov     r9d, eax; char *
0x18000b01e  lea     r8, aShellOobeUserD; "shell\\oobe\\user\\dll\\oobebrokermanag"...
0x18000b025  mov     edx, 0BFh; void *
0x18000b02a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000b030  mov     r9d, eax; char *
0x18000b033  lea     r8, aShellOobeUserD; "shell\\oobe\\user\\dll\\oobebrokermanag"...
0x18000b03a  mov     edx, 0C2h; void *
0x18000b03f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000b045  mov     r9d, eax; char *
0x18000b048  lea     r8, aShellOobeUserD; "shell\\oobe\\user\\dll\\oobebrokermanag"...
0x18000b04f  mov     edx, 0C4h; void *
0x18000b054  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
