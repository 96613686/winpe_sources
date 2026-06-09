# GeolocSignal::GeolocSignal(__int64,float,float,long)

- ea: `0x18003e118`
- end: `0x18003e274`
- name: `??0GeolocSignal@@QEAA@_JMMJ@Z`
- size: `348`
- prototype: `GeolocSignal *__fastcall(GeolocSignal *__hidden this, __int64, float, float, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003f2b0`

## callees

- `0x180004170`
- `0x18000a7f8`
- `0x180029568`
- `0x180033134`
- `0x18003d7d8`
- `0x18003d978`
- `0x18003e118`
- `0x18003eb08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003e1fd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003e1fd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003e1da`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003e1da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e1c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e1c4`

## pseudocode

```c
GeolocSignal *__fastcall GeolocSignal::GeolocSignal(GeolocSignal *this, __int64 a2, float a3, float a4, int a5)
{
  HRESULT v6; // eax
  int v7; // edi
  struct GeolocSignal *v9[2]; // [rsp+20h] [rbp-68h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-58h] BYREF
  HSTRING string; // [rsp+48h] [rbp-40h] BYREF

  v9[1] = this;
  GenericPlugin::DefaultSignal::DefaultSignal(this, a2);
  *(_QWORD *)this = &GeolocSignal::`vftable';
  *((_QWORD *)this + 6) = 0;
  *((float *)this + 14) = a3;
  *((float *)this + 15) = a4;
  *((_DWORD *)this + 16) = a5;
  *((_QWORD *)this + 9) = 0;
  std::atomic<bool>::atomic<bool>((char *)this + 80);
  *((_QWORD *)this + 11) = 0;
  v9[0] = this;
  Microsoft::WRL::Details::Make<GeolocSignal::GeopositionHandler,GeolocSignal *>((__int64 *)this + 12, v9);
  string = 0;
  v6 = WindowsCreateStringReference(L"Windows.Devices.Geolocation.Geolocator", 0x26u, &hstringHeader, &string);
  if ( v6 < 0 )
  {
    RaiseException(v6, 1u, 0, 0);
    __debugbreak();
  }
  v7 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeolocator>>(
         (__int64)string,
         (_QWORD *)this + 9);
  *((_QWORD *)this + 6) = CreateEventW(0, 1, 0, 0);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        &WPP_d7a34c12d6d033c41d405f6d74c18c9b_Traceguids,
        (unsigned int)v7);
  }
  else
  {
    GeolocSignal::ForceEvaluation(this, 0);
  }
  return this;
}

```

## disassembly

```asm
0x18003e118  mov     [rsp+arg_8], rbx
0x18003e11d  push    rdi
0x18003e11e  sub     rsp, 80h
0x18003e125  movaps  [rsp+88h+var_18], xmm6
0x18003e12a  movaps  [rsp+88h+var_28], xmm7
0x18003e12f  mov     rax, cs:__security_cookie
0x18003e136  xor     rax, rsp
0x18003e139  mov     [rsp+88h+var_38], rax
0x18003e13e  movaps  xmm7, xmm3
0x18003e141  movaps  xmm6, xmm2
0x18003e144  mov     rbx, rcx
0x18003e147  mov     [rsp+88h+var_60], rcx
0x18003e14c  call    ??0DefaultSignal@GenericPlugin@@QEAA@_J@Z; GenericPlugin::DefaultSignal::DefaultSignal(__int64)
0x18003e151  nop
0x18003e152  lea     rax, ??_7GeolocSignal@@6B@; const GeolocSignal::`vftable'
0x18003e159  mov     [rbx], rax
0x18003e15c  mov     qword ptr [rbx+30h], 0
0x18003e164  movss   dword ptr [rbx+38h], xmm6
0x18003e169  movss   dword ptr [rbx+3Ch], xmm7
0x18003e16e  mov     eax, [rsp+88h+arg_20]
0x18003e175  mov     [rbx+40h], eax
0x18003e178  mov     qword ptr [rbx+48h], 0
0x18003e180  lea     rcx, [rbx+50h]
0x18003e184  call    ??0?$atomic@_N@std@@QEAA@_N@Z; std::atomic<bool>::atomic<bool>(bool)
0x18003e189  mov     qword ptr [rbx+58h], 0
0x18003e191  mov     [rsp+88h+var_68], rbx
0x18003e196  lea     rcx, [rbx+60h]
0x18003e19a  lea     rdx, [rsp+88h+var_68]
0x18003e19f  call    ??$Make@VGeopositionHandler@GeolocSignal@@PEAV2@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VGeopositionHandler@GeolocSignal@@@12@$$QEAPEAVGeolocSignal@@@Z; Microsoft::WRL::Details::Make<GeolocSignal::GeopositionHandler,GeolocSignal *>(GeolocSignal * &&)
0x18003e1a4  nop
0x18003e1a5  mov     [rsp+88h+string], 0
0x18003e1ae  lea     r9, [rsp+88h+string]; string
0x18003e1b3  lea     r8, [rsp+88h+hstringHeader]; hstringHeader
0x18003e1b8  mov     edx, 26h ; '&'; length
0x18003e1bd  lea     rcx, ?RuntimeClass_Windows_Devices_Geolocation_Geolocator@@3QBGB; "Windows.Devices.Geolocation.Geolocator"
0x18003e1c4  call    cs:__imp_WindowsCreateStringReference
0x18003e1ca  test    eax, eax
0x18003e1cc  jns     short loc_18003E1E1
0x18003e1ce  xor     r9d, r9d; lpArguments
0x18003e1d1  xor     r8d, r8d; nNumberOfArguments
0x18003e1d4  lea     edx, [r9+1]; dwExceptionFlags
0x18003e1d8  mov     ecx, eax; dwExceptionCode
0x18003e1da  call    cs:__imp_RaiseException
0x18003e1e0  int     3; Trap to Debugger
0x18003e1e1  lea     rdx, [rbx+48h]
0x18003e1e5  mov     rcx, [rsp+88h+string]
0x18003e1ea  call    ??$ActivateInstance@V?$ComPtr@UIGeolocator@Geolocation@Devices@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIGeolocator@Geolocation@Devices@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeolocator>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeolocator>>)
0x18003e1ef  mov     edi, eax
0x18003e1f1  xor     r9d, r9d; lpName
0x18003e1f4  xor     r8d, r8d; bInitialState
0x18003e1f7  lea     edx, [r9+1]; bManualReset
0x18003e1fb  xor     ecx, ecx; lpEventAttributes
0x18003e1fd  call    cs:__imp_CreateEventW
0x18003e203  mov     [rbx+30h], rax
0x18003e207  test    edi, edi
0x18003e209  js      short loc_18003E217
0x18003e20b  xor     edx, edx
0x18003e20d  mov     rcx, rbx
0x18003e210  call    ?ForceEvaluation@GeolocSignal@@QEAAXW4_GEOLOC_EVALUATE_SOURCE@@@Z; GeolocSignal::ForceEvaluation(_GEOLOC_EVALUATE_SOURCE)
0x18003e215  jmp     short loc_18003E249
0x18003e217  lea     rax, WPP_GLOBAL_Control
0x18003e21e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e225  cmp     rcx, rax
0x18003e228  jz      short loc_18003E249
0x18003e22a  test    byte ptr [rcx+1Ch], 1
0x18003e22e  jz      short loc_18003E249
0x18003e230  mov     edx, 0Bh
0x18003e235  mov     r9d, edi
0x18003e238  lea     r8, WPP_d7a34c12d6d033c41d405f6d74c18c9b_Traceguids
0x18003e23f  mov     rcx, [rcx+10h]
0x18003e243  call    WPP_SF_d
0x18003e248  nop
0x18003e249  mov     rax, rbx
0x18003e24c  mov     rcx, [rsp+88h+var_38]
0x18003e251  xor     rcx, rsp; StackCookie
0x18003e254  call    __security_check_cookie
0x18003e259  mov     rbx, [rsp+88h+arg_8]
0x18003e261  movaps  xmm6, [rsp+88h+var_18]
0x18003e266  movaps  xmm7, [rsp+88h+var_28]
0x18003e26b  add     rsp, 80h
0x18003e272  pop     rdi
0x18003e273  retn
```
