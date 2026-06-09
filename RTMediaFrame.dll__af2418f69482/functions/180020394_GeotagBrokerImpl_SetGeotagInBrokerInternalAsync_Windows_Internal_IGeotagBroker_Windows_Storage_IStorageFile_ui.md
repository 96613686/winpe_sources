# GeotagBrokerImpl::SetGeotagInBrokerInternalAsync(Windows::Internal::IGeotagBroker *,Windows::Storage::IStorageFile *,uint,Windows::Foundation::IAsyncAction * *)

- ea: `0x180020394`
- end: `0x1800204bb`
- name: `?SetGeotagInBrokerInternalAsync@GeotagBrokerImpl@@AEAAJPEAUIGeotagBroker@Internal@Windows@@PEAUIStorageFile@Storage@4@IPEAPEAUIAsyncAction@Foundation@4@@Z`
- size: `295`
- prototype: `__int64 __fastcall(GeotagBrokerImpl *__hidden this, struct Windows::Internal::IGeotagBroker *, struct Windows::Storage::IStorageFile *, unsigned int, struct Windows::Foundation::IAsyncAction **)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180043914`
- `0x18004b760`

## callees

- `0x18001b710`
- `0x180020394`
- `0x1800204c4`
- `0x1800204e8`
- `0x180020514`
- `0x180020c48`
- `0x180020c6c`
- `0x180020ccc`
- `0x180020d50`
- `0x1800468a0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180020427`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180020427`

## string_xrefs

- `0x1800203e7`: `avcore\mf\photography\components\geotag\lib\geotag.cpp`

## pseudocode

```c
__int64 __fastcall GeotagBrokerImpl::SetGeotagInBrokerInternalAsync(
        GeotagBrokerImpl *this,
        struct Windows::Internal::IGeotagBroker *a2,
        struct Windows::Storage::IStorageFile *a3,
        unsigned int a4,
        struct Windows::Foundation::IAsyncAction **a5)
{
  struct Windows::Foundation::IAsyncAction **v5; // rsi
  __int64 v10; // rdx
  __int64 v11; // rcx
  int GeopositionAsync; // eax
  unsigned int v13; // ebx
  __int64 v14; // rax
  __int64 v15; // r8
  int v17; // [rsp+20h] [rbp-41h]
  struct Windows::Storage::IStorageFile *v18; // [rsp+30h] [rbp-31h] BYREF
  struct Windows::Internal::IGeotagBroker *v19; // [rsp+38h] [rbp-29h] BYREF
  GeotagBrokerImpl *v20; // [rsp+40h] [rbp-21h] BYREF
  _BYTE v21[12]; // [rsp+48h] [rbp-19h] BYREF
  _BYTE v22[88]; // [rsp+58h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+57h]

  v5 = a5;
  a5 = 0;
  *v5 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&a5);
  GeopositionAsync = GetGeopositionAsync(v11, v10, a4, &a5);
  v13 = GeopositionAsync;
  if ( GeopositionAsync >= 0 )
  {
    v19 = a2;
    Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(&v19);
    v20 = this;
    Microsoft::WRL::ComPtr<GeotagBrokerImpl>::InternalAddRef(&v20);
    v18 = a3;
    Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(&v18);
    *(_QWORD *)v21 = GetTickCount64();
    v14 = lambda_93ffa0af85459f36f72a0c0ec15e7481_::_lambda_93ffa0af85459f36f72a0c0ec15e7481_(
            (unsigned int)v22,
            (unsigned int)&v19,
            (unsigned int)&v20,
            (unsigned int)&v18,
            (__int64)&a5,
            (__int64)v21);
    *(_DWORD *)v21 = 3;
    *(_QWORD *)&v21[4] = 128;
    v13 = Windows::Internal::MakeAsyncAction_Microsoft::WRL::AsyncCausalityOptions__GeotagBroker_SetGeotagInBrokerInternalAsync__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows::Internal::ComTaskPoolHandler__lambda_93ffa0af85459f36f72a0c0ec15e7481___(
            v21,
            v5,
            v15,
            v14);
    lambda_93ffa0af85459f36f72a0c0ec15e7481_::__lambda_93ffa0af85459f36f72a0c0ec15e7481_(v22);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
    if ( this )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::IGeotagBroker,Microsoft::WRL::FtmBase>::Release(this);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DB,
      (unsigned int)"avcore\\mf\\photography\\components\\geotag\\lib\\geotag.cpp",
      (const char *)(unsigned int)GeopositionAsync,
      v17);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&a5);
  return v13;
}

```

## disassembly

```asm
0x180020394  push    rbp
0x180020396  push    rbx
0x180020397  push    rsi
0x180020398  push    rdi
0x180020399  push    r14
0x18002039b  push    r15
0x18002039d  lea     rbp, [rsp-27h]
0x1800203a2  sub     rsp, 88h
0x1800203a9  mov     rsi, [rbp+4Fh+arg_20]
0x1800203ad  mov     rdi, rcx
0x1800203b0  lea     rcx, [rbp+4Fh+arg_20]
0x1800203b4  mov     [rbp+4Fh+arg_20], 0
0x1800203bc  mov     ebx, r9d
0x1800203bf  mov     r14, r8
0x1800203c2  mov     r15, rdx
0x1800203c5  mov     qword ptr [rsi], 0
0x1800203cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800203d1  lea     r9, [rbp+4Fh+arg_20]
0x1800203d5  mov     r8d, ebx
0x1800203d8  call    ?GetGeopositionAsync@@YAJHHHPEAPEAU?$IAsyncOperation@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@Z; GetGeopositionAsync(int,int,int,Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> * *)
0x1800203dd  mov     ebx, eax
0x1800203df  test    eax, eax
0x1800203e1  jns     short loc_180020400
0x1800203e3  mov     rcx, [rbp+57h]; this
0x1800203e7  lea     r8, aAvcoreMfPhotog; "avcore\\mf\\photography\\components\\ge"...
0x1800203ee  mov     r9d, eax; char *
0x1800203f1  mov     edx, 2DBh; void *
0x1800203f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800203fb  jmp     loc_1800204A0
0x180020400  lea     rcx, [rbp+4Fh+var_78]
0x180020404  mov     [rbp+4Fh+var_78], r15
0x180020408  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x18002040d  lea     rcx, [rbp+4Fh+var_70]
0x180020411  mov     [rbp+4Fh+var_70], rdi
0x180020415  call    ?InternalAddRef@?$ComPtr@VGeotagBrokerImpl@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<GeotagBrokerImpl>::InternalAddRef(void)
0x18002041a  lea     rcx, [rbp+4Fh+var_80]
0x18002041e  mov     [rbp+4Fh+var_80], r14
0x180020422  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x180020427  call    cs:__imp_GetTickCount64
0x18002042d  mov     [rbp+4Fh+var_68], rax
0x180020431  lea     r9, [rbp+4Fh+var_80]
0x180020435  lea     rax, [rbp+4Fh+var_68]
0x180020439  mov     [rsp+0B0h+var_88], rax
0x18002043e  lea     r8, [rbp+4Fh+var_70]
0x180020442  lea     rax, [rbp+4Fh+arg_20]
0x180020446  lea     rdx, [rbp+4Fh+var_78]
0x18002044a  mov     [rsp+0B0h+var_90], rax
0x18002044f  lea     rcx, [rbp+4Fh+var_58]
0x180020453  call    _lambda_93ffa0af85459f36f72a0c0ec15e7481____lambda_93ffa0af85459f36f72a0c0ec15e7481_
0x180020458  mov     r9, rax
0x18002045b  mov     dword ptr [rbp+4Fh+var_68], 3
0x180020462  mov     rdx, rsi
0x180020465  mov     [rbp+4Fh+var_68+4], 80h
0x18002046d  lea     rcx, [rbp+4Fh+var_68]
0x180020471  call    Windows__Internal__MakeAsyncAction_Microsoft__WRL__AsyncCausalityOptions__GeotagBroker_SetGeotagInBrokerInternalAsync__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows__Internal__ComTaskPoolHandler__lambda_93ffa0af85459f36f72a0c0ec15e7481___
0x180020476  lea     rcx, [rbp+4Fh+var_58]
0x18002047a  mov     ebx, eax
0x18002047c  call    _lambda_93ffa0af85459f36f72a0c0ec15e7481_____lambda_93ffa0af85459f36f72a0c0ec15e7481_
0x180020481  lea     rcx, [rbp+4Fh+var_80]
0x180020485  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002048a  test    rdi, rdi
0x18002048d  jz      short loc_180020497
0x18002048f  mov     rcx, rdi
0x180020492  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIGeotagBroker@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::IGeotagBroker,Microsoft::WRL::FtmBase>::Release(void)
0x180020497  lea     rcx, [rbp+4Fh+var_78]
0x18002049b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800204a0  lea     rcx, [rbp+4Fh+arg_20]
0x1800204a4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800204a9  mov     eax, ebx
0x1800204ab  add     rsp, 88h
0x1800204b2  pop     r15
0x1800204b4  pop     r14
0x1800204b6  pop     rdi
0x1800204b7  pop     rsi
0x1800204b8  pop     rbx
0x1800204b9  pop     rbp
0x1800204ba  retn
```
