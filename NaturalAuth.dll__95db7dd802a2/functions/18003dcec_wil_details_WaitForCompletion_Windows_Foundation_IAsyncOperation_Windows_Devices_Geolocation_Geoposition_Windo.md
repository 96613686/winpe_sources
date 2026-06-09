# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x18003dcec`
- end: `0x18003de26`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `314`
- prototype: `__int64 __fastcall(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), DWORD, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003e49c`

## callees

- `0x180009114`
- `0x180014e7c`
- `0x18003d9f8`
- `0x18003dcec`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18003dd91`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18003dd91`

## string_xrefs

- `0x18003dd53`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *>(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        DWORD a2,
        int a3)
{
  int v4; // eax
  int v5; // ebx
  __int64 v6; // rdx
  __int64 (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rbx
  int lpdwindex; // [rsp+20h] [rbp-20h]
  __int64 v10; // [rsp+30h] [rbp-10h] BYREF
  HANDLE pHandles; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD dwindex; // [rsp+68h] [rbp+28h] BYREF
  int v14; // [rsp+70h] [rbp+30h] BYREF
  __int64 v15; // [rsp+78h] [rbp+38h] BYREF

  v14 = a3;
  dwindex = a2;
  v15 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  v4 = ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVGeoposition_Geolocation_Devices_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVGeoposition_Geolocation_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAU__IAsyncOperation_PEAVGeoposition_Geolocation_Devices_Windows___Foundation_Windows___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVGeoposition_Geolocation_Devices_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVGeoposition_Geolocation_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(&v15);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 1608;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v4,
      lpdwindex);
    goto LABEL_14;
  }
  v4 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*a1)[6])(a1, v15);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 1609;
    goto LABEL_5;
  }
  pHandles = *(HANDLE *)(v15 + 56);
  dwindex = 0;
  v4 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 1621;
    goto LABEL_5;
  }
  if ( *(_DWORD *)(v15 + 48) == 1 )
  {
    v5 = 0;
  }
  else
  {
    v10 = 0;
    v7 = **a1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
    v5 = v7(a1, &GUID_00000036_0000_0000_c000_000000000046, &v10);
    if ( v5 >= 0 )
    {
      v14 = -2147418113;
      v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 64LL))(v10, &v14);
      if ( v5 >= 0 )
        v5 = v14;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
  }
LABEL_14:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003dcec  mov     [rsp-18h+arg_18], r9
0x18003dcf1  mov     [rsp-18h+arg_10], r8d
0x18003dcf6  mov     [rsp-18h+dwindex], edx
0x18003dcfa  push    rbp
0x18003dcfb  push    rbx
0x18003dcfc  push    rdi
0x18003dcfd  mov     rbp, rsp
0x18003dd00  sub     rsp, 40h
0x18003dd04  mov     rdi, rcx
0x18003dd07  mov     [rbp+arg_18], 0
0x18003dd0f  lea     rcx, [rbp+arg_18]
0x18003dd13  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003dd18  lea     rcx, [rbp+arg_18]
0x18003dd1c  call    ??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)
0x18003dd21  mov     ebx, eax
0x18003dd23  test    eax, eax
0x18003dd25  jns     short loc_18003DD2E
0x18003dd27  mov     edx, 648h
0x18003dd2c  jmp     short loc_18003DD4C
0x18003dd2e  mov     rax, [rdi]
0x18003dd31  mov     rdx, [rbp+arg_18]
0x18003dd35  mov     rcx, rdi
0x18003dd38  mov     rax, [rax+30h]
0x18003dd3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd41  mov     ebx, eax
0x18003dd43  test    eax, eax
0x18003dd45  jns     short loc_18003DD64
0x18003dd47  mov     edx, 649h; void *
0x18003dd4c  mov     rcx, [rbp+18h]; this
0x18003dd50  mov     r9d, eax; char *
0x18003dd53  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003dd5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dd5f  jmp     loc_18003DE13
0x18003dd64  mov     rax, [rbp+arg_18]
0x18003dd68  mov     rcx, [rax+38h]
0x18003dd6c  mov     [rbp+pHandles], rcx
0x18003dd70  mov     [rbp+dwindex], 0
0x18003dd77  lea     rax, [rbp+dwindex]
0x18003dd7b  mov     qword ptr [rsp+40h+lpdwindex], rax; lpdwindex
0x18003dd80  lea     r9, [rbp+pHandles]; pHandles
0x18003dd84  mov     r8d, 1; cHandles
0x18003dd8a  or      edx, 0FFFFFFFFh; dwTimeout
0x18003dd8d  lea     ecx, [r8+7]; dwFlags
0x18003dd91  call    cs:__imp_CoWaitForMultipleHandles
0x18003dd97  mov     ebx, eax
0x18003dd99  test    eax, eax
0x18003dd9b  jns     short loc_18003DDA4
0x18003dd9d  mov     edx, 655h
0x18003dda2  jmp     short loc_18003DD4C
0x18003dda4  mov     rax, [rbp+arg_18]
0x18003dda8  mov     ecx, [rax+30h]
0x18003ddab  cmp     ecx, 1
0x18003ddae  jz      short loc_18003DE11
0x18003ddb0  mov     [rbp+var_10], 0
0x18003ddb8  mov     rax, [rdi]
0x18003ddbb  mov     rbx, [rax]
0x18003ddbe  lea     rcx, [rbp+var_10]
0x18003ddc2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ddc7  lea     r8, [rbp+var_10]
0x18003ddcb  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18003ddd2  mov     rcx, rdi
0x18003ddd5  mov     rax, rbx
0x18003ddd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dddd  mov     ebx, eax
0x18003dddf  test    eax, eax
0x18003dde1  js      short loc_18003DE06
0x18003dde3  mov     [rbp+arg_10], 8000FFFFh
0x18003ddea  mov     rcx, [rbp+var_10]
0x18003ddee  mov     rax, [rcx]
0x18003ddf1  lea     rdx, [rbp+arg_10]
0x18003ddf5  mov     rax, [rax+40h]
0x18003ddf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ddfe  mov     ebx, eax
0x18003de00  test    eax, eax
0x18003de02  cmovns  ebx, [rbp+arg_10]
0x18003de06  lea     rcx, [rbp+var_10]
0x18003de0a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003de0f  jmp     short loc_18003DE13
0x18003de11  xor     ebx, ebx
0x18003de13  lea     rcx, [rbp+arg_18]
0x18003de17  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003de1c  mov     eax, ebx
0x18003de1e  add     rsp, 40h
0x18003de22  pop     rdi
0x18003de23  pop     rbx
0x18003de24  pop     rbp
0x18003de25  retn
```
