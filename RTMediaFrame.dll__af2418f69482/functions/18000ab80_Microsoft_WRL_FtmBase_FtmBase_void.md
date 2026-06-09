# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18000ab80`
- end: `0x18000ac2a`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `170`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `23`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800025b4`
- `0x180009760`
- `0x18000a8ac`
- `0x18000aa70`
- `0x18000aae0`
- `0x18000ac60`
- `0x180016120`
- `0x18001867c`
- `0x180019538`
- `0x18001a5dc`
- `0x180021a30`
- `0x180028aa0`
- `0x180028b3c`
- `0x180028c04`
- `0x180028e1c`
- `0x180031bc8`
- `0x180039d8c`
- `0x18003dea0`
- `0x180040494`
- `0x18004055c`
- `0x180040624`
- `0x1800406ec`
- `0x1800407b4`

## callees

- `0x18000ab80`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000abb2`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000abb2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  LPUNKNOWN v2; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v4; // rcx
  LPUNKNOWN v5; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = &Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 3) = 0;
  ppunkMarshal = 0;
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v2 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    v4 = *((_QWORD *)this + 3);
    if ( v4 )
    {
      *((_QWORD *)this + 3) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))QueryInterface)(
      v2,
      &GUID_00000003_0000_0000_c000_000000000046,
      (char *)this + 24);
  }
  v5 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v5->lpVtbl->Release)(v5);
  }
  return this;
}

```

## disassembly

```asm
0x18000ab80  mov     [rsp+arg_8], rbx
0x18000ab85  mov     [rsp+arg_10], rbp
0x18000ab8a  push    rsi
0x18000ab8b  push    rdi
0x18000ab8c  push    r14
0x18000ab8e  sub     rsp, 20h
0x18000ab92  mov     rsi, rcx
0x18000ab95  lea     rax, ??_7?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x18000ab9c  mov     [rcx], rax
0x18000ab9f  xor     r14d, r14d
0x18000aba2  mov     [rcx+18h], r14
0x18000aba6  mov     [rsp+38h+ppunkMarshal], r14
0x18000abab  lea     rdx, [rsp+38h+ppunkMarshal]; ppunkMarshal
0x18000abb0  xor     ecx, ecx; punkOuter
0x18000abb2  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000abb8  test    eax, eax
0x18000abba  js      short loc_18000ABF8
0x18000abbc  mov     rbx, [rsp+38h+ppunkMarshal]
0x18000abc1  mov     rax, [rbx]
0x18000abc4  mov     rbp, [rax]
0x18000abc7  mov     rcx, [rsi+18h]
0x18000abcb  test    rcx, rcx
0x18000abce  jz      short loc_18000ABE1
0x18000abd0  mov     [rsi+18h], r14
0x18000abd4  mov     rdx, [rcx]
0x18000abd7  mov     rax, [rdx+10h]
0x18000abdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abe0  nop
0x18000abe1  lea     r8, [rsi+18h]
0x18000abe5  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000abec  mov     rcx, rbx
0x18000abef  mov     rax, rbp
0x18000abf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abf7  nop
0x18000abf8  mov     rcx, [rsp+38h+ppunkMarshal]
0x18000abfd  test    rcx, rcx
0x18000ac00  jz      short loc_18000AC14
0x18000ac02  mov     [rsp+38h+ppunkMarshal], r14
0x18000ac07  mov     rax, [rcx]
0x18000ac0a  mov     rax, [rax+10h]
0x18000ac0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac13  nop
0x18000ac14  mov     rax, rsi
0x18000ac17  mov     rbx, [rsp+38h+arg_8]
0x18000ac1c  mov     rbp, [rsp+38h+arg_10]
0x18000ac21  add     rsp, 20h
0x18000ac25  pop     r14
0x18000ac27  pop     rdi
0x18000ac28  pop     rsi
0x18000ac29  retn
```
