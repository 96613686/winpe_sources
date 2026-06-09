# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x1800251d0`
- end: `0x18002532b`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `347`
- prototype: `__int64 __fastcall(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), DWORD, int, _BYTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800256ac`

## callees

- `0x180009fc0`
- `0x18000c4cc`
- `0x180024fe0`
- `0x1800251d0`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18002527f`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18002527f`

## string_xrefs

- `0x180025243`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 __fastcall wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *>(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        DWORD a2,
        int a3,
        _BYTE *a4)
{
  int v6; // eax
  int v7; // ebx
  __int64 v8; // rdx
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rbx
  int lpdwindex; // [rsp+20h] [rbp-20h]
  __int64 v12; // [rsp+30h] [rbp-10h] BYREF
  HANDLE pHandles; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD dwindex; // [rsp+68h] [rbp+28h] BYREF
  int v16; // [rsp+70h] [rbp+30h] BYREF
  __int64 v17; // [rsp+78h] [rbp+38h] BYREF

  v16 = a3;
  dwindex = a2;
  if ( a4 )
    *a4 = 0;
  v17 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  v6 = ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVGeoposition_Geolocation_Devices_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVGeoposition_Geolocation_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAU__IAsyncOperation_PEAVGeoposition_Geolocation_Devices_Windows___Foundation_Windows___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVGeoposition_Geolocation_Devices_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVGeoposition_Geolocation_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(&v17);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 1608;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v6,
      lpdwindex);
    goto LABEL_12;
  }
  v6 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*a1)[6])(a1, v17);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 1609;
    goto LABEL_7;
  }
  pHandles = *(HANDLE *)(v17 + 56);
  dwindex = 0;
  v6 = CoWaitForMultipleHandles(8u, 0x2710u, 1u, &pHandles, &dwindex);
  v7 = v6;
  if ( a4 && v6 == -2147417835 )
  {
    *a4 = 1;
    goto LABEL_11;
  }
  if ( v6 < 0 )
  {
    v8 = 1621;
    goto LABEL_7;
  }
  if ( *(_DWORD *)(v17 + 48) == 1 )
  {
LABEL_11:
    v7 = 0;
    goto LABEL_12;
  }
  v12 = 0;
  v10 = **a1;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  v7 = v10(a1, &GUID_00000036_0000_0000_c000_000000000046, &v12);
  if ( v7 >= 0 )
  {
    v16 = -2147418113;
    v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 64LL))(v12, &v16);
    if ( v7 >= 0 )
      v7 = v16;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
LABEL_12:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800251d0  mov     [rsp-18h+arg_0], rbx
0x1800251d5  mov     [rsp-18h+arg_10], r8d
0x1800251da  mov     [rsp-18h+dwindex], edx
0x1800251de  push    rbp
0x1800251df  push    rsi
0x1800251e0  push    rdi
0x1800251e1  mov     rbp, rsp
0x1800251e4  sub     rsp, 40h
0x1800251e8  mov     rdi, r9
0x1800251eb  mov     rsi, rcx
0x1800251ee  test    r9, r9
0x1800251f1  jz      short loc_1800251F7
0x1800251f3  mov     byte ptr [r9], 0
0x1800251f7  mov     [rbp+arg_18], 0
0x1800251ff  lea     rcx, [rbp+arg_18]
0x180025203  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025208  lea     rcx, [rbp+arg_18]
0x18002520c  call    ??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)
0x180025211  mov     ebx, eax
0x180025213  test    eax, eax
0x180025215  jns     short loc_18002521E
0x180025217  mov     edx, 648h
0x18002521c  jmp     short loc_18002523C
0x18002521e  mov     rax, [rsi]
0x180025221  mov     rdx, [rbp+arg_18]
0x180025225  mov     rcx, rsi
0x180025228  mov     rax, [rax+30h]
0x18002522c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025231  mov     ebx, eax
0x180025233  test    eax, eax
0x180025235  jns     short loc_180025251
0x180025237  mov     edx, 649h; void *
0x18002523c  mov     rcx, [rbp+18h]; this
0x180025240  mov     r9d, eax; char *
0x180025243  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002524a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002524f  jmp     short loc_180025298
0x180025251  mov     rax, [rbp+arg_18]
0x180025255  mov     rcx, [rax+38h]
0x180025259  mov     [rbp+pHandles], rcx
0x18002525d  mov     [rbp+dwindex], 0
0x180025264  lea     rax, [rbp+dwindex]
0x180025268  mov     qword ptr [rsp+40h+lpdwindex], rax; lpdwindex
0x18002526d  lea     r9, [rbp+pHandles]; pHandles
0x180025271  mov     edx, 2710h; dwTimeout
0x180025276  mov     ecx, 8; dwFlags
0x18002527b  lea     r8d, [rcx-7]; cHandles
0x18002527f  call    cs:__imp_CoWaitForMultipleHandles
0x180025285  mov     ebx, eax
0x180025287  test    rdi, rdi
0x18002528a  jz      short loc_1800252B0
0x18002528c  cmp     eax, 80010115h
0x180025291  jnz     short loc_1800252B0
0x180025293  mov     byte ptr [rdi], 1
0x180025296  xor     ebx, ebx
0x180025298  lea     rcx, [rbp+arg_18]
0x18002529c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800252a1  mov     eax, ebx
0x1800252a3  mov     rbx, [rsp+40h+arg_0]
0x1800252a8  add     rsp, 40h
0x1800252ac  pop     rdi
0x1800252ad  pop     rsi
0x1800252ae  pop     rbp
0x1800252af  retn
0x1800252b0  test    eax, eax
0x1800252b2  jns     short loc_1800252BB
0x1800252b4  mov     edx, 655h
0x1800252b9  jmp     short loc_18002523C
0x1800252bb  mov     rax, [rbp+arg_18]
0x1800252bf  mov     ecx, [rax+30h]
0x1800252c2  cmp     ecx, 1
0x1800252c5  jz      short loc_180025296
0x1800252c7  mov     [rbp+var_10], 0
0x1800252cf  mov     rax, [rsi]
0x1800252d2  mov     rbx, [rax]
0x1800252d5  lea     rcx, [rbp+var_10]
0x1800252d9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800252de  lea     r8, [rbp+var_10]
0x1800252e2  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1800252e9  mov     rcx, rsi
0x1800252ec  mov     rax, rbx
0x1800252ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252f4  mov     ebx, eax
0x1800252f6  test    eax, eax
0x1800252f8  js      short loc_18002531D
0x1800252fa  mov     [rbp+arg_10], 8000FFFFh
0x180025301  mov     rcx, [rbp+var_10]
0x180025305  mov     rax, [rcx]
0x180025308  lea     rdx, [rbp+arg_10]
0x18002530c  mov     rax, [rax+40h]
0x180025310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025315  mov     ebx, eax
0x180025317  test    eax, eax
0x180025319  cmovns  ebx, [rbp+arg_10]
0x18002531d  lea     rcx, [rbp+var_10]
0x180025321  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025326  jmp     loc_180025298
```
