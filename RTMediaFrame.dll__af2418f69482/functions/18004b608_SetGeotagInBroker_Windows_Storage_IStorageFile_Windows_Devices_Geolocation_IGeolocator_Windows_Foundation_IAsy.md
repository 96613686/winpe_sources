# SetGeotagInBroker(Windows::Storage::IStorageFile *,Windows::Devices::Geolocation::IGeolocator *,Windows::Foundation::IAsyncAction * *)

- ea: `0x18004b608`
- end: `0x18004b754`
- name: `?SetGeotagInBroker@@YAJPEAUIStorageFile@Storage@Windows@@PEAUIGeolocator@Geolocation@Devices@3@PEAPEAUIAsyncAction@Foundation@3@@Z`
- size: `332`
- prototype: `int(struct Windows::Storage::IStorageFile *, struct Windows::Devices::Geolocation::IGeolocator *, struct Windows::Foundation::IAsyncAction **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180043c24`

## callees

- `0x1800019c0`
- `0x180018160`
- `0x1800204e8`
- `0x180020c48`
- `0x180026920`
- `0x18004663c`
- `0x18004b608`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18004b675`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18004b675`

## string_xrefs

- `0x18004b6c0`: `avcore\mf\photography\components\geotag\lib\geotag.cpp`
- `0x18004b659`: `Windows.Internal.GeotagBroker`

## pseudocode

```c
__int64 __fastcall SetGeotagInBroker(
        struct Windows::Storage::IStorageFile *a1,
        struct Windows::Devices::Geolocation::IGeolocator *a2,
        struct Windows::Foundation::IAsyncAction **a3)
{
  int v4; // r15d
  int DesiredLocationAccuracy; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rdi
  int v12; // [rsp+20h] [rbp-50h]
  unsigned int v13; // [rsp+30h] [rbp-40h] BYREF
  __int64 (__fastcall ***v14)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-38h] BYREF
  __int64 v15; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  __int64 v17; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v14 = 0;
  v15 = 0;
  v4 = (int)a3;
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v14);
  v17 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.GeotagBroker",
    0x1Eu,
    0x1Du);
  DesiredLocationAccuracy = RoActivateInstance(v17, &v14);
  v7 = DesiredLocationAccuracy;
  if ( DesiredLocationAccuracy >= 0 )
  {
    v9 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v14;
    v10 = **v14;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
    DesiredLocationAccuracy = v10(v9, &GUID_88b336bc_6f1b_482f_be30_25a9fb5566ed, &v15);
    v7 = DesiredLocationAccuracy;
    if ( DesiredLocationAccuracy >= 0 )
    {
      v13 = 0;
      DesiredLocationAccuracy = GetDesiredLocationAccuracy(a2, &v13);
      v7 = DesiredLocationAccuracy;
      if ( DesiredLocationAccuracy >= 0 )
      {
        v12 = v4;
        DesiredLocationAccuracy = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), struct Windows::Storage::IStorageFile *, _QWORD))(*(_QWORD *)v15 + 48LL))(
                                    v15,
                                    v14,
                                    a1,
                                    v13);
        v7 = DesiredLocationAccuracy;
        if ( DesiredLocationAccuracy >= 0 )
        {
          v7 = 0;
          goto LABEL_11;
        }
        v8 = 1024;
      }
      else
      {
        v8 = 1023;
      }
    }
    else
    {
      v8 = 1020;
    }
  }
  else
  {
    v8 = 1019;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"avcore\\mf\\photography\\components\\geotag\\lib\\geotag.cpp",
    (const char *)(unsigned int)DesiredLocationAccuracy,
    v12);
LABEL_11:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v14);
  return v7;
}

```

## disassembly

```asm
0x18004b608  mov     [rsp-28h+arg_18], rbx
0x18004b60d  push    rbp
0x18004b60e  push    rsi
0x18004b60f  push    rdi
0x18004b610  push    r14
0x18004b612  push    r15
0x18004b614  mov     rbp, rsp
0x18004b617  sub     rsp, 70h
0x18004b61b  mov     rax, cs:__security_cookie
0x18004b622  xor     rax, rsp
0x18004b625  mov     [rbp+var_8], rax
0x18004b629  mov     r14, rcx
0x18004b62c  mov     [rbp+var_38], 0
0x18004b634  lea     rcx, [rbp+var_38]
0x18004b638  mov     [rbp+var_30], 0
0x18004b640  mov     r15, r8
0x18004b643  mov     rsi, rdx
0x18004b646  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18004b64b  mov     r9d, 1Dh; unsigned int
0x18004b651  mov     [rbp+var_10], 0
0x18004b659  lea     rdx, ?RuntimeClass_Windows_Internal_GeotagBroker@@3QBGB; "Windows.Internal.GeotagBroker"
0x18004b660  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18004b664  lea     r8d, [r9+1]; unsigned int
0x18004b668  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004b66d  mov     rcx, [rbp+var_10]
0x18004b671  lea     rdx, [rbp+var_38]
0x18004b675  call    cs:__imp_RoActivateInstance
0x18004b67b  mov     ebx, eax
0x18004b67d  test    eax, eax
0x18004b67f  jns     short loc_18004B688
0x18004b681  mov     edx, 3FBh
0x18004b686  jmp     short loc_18004B6BC
0x18004b688  mov     rbx, [rbp+var_38]
0x18004b68c  lea     rcx, [rbp+var_30]
0x18004b690  mov     rax, [rbx]
0x18004b693  mov     rdi, [rax]
0x18004b696  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004b69b  lea     r8, [rbp+var_30]
0x18004b69f  mov     rcx, rbx
0x18004b6a2  lea     rdx, _GUID_88b336bc_6f1b_482f_be30_25a9fb5566ed
0x18004b6a9  mov     rax, rdi
0x18004b6ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b6b1  mov     ebx, eax
0x18004b6b3  test    eax, eax
0x18004b6b5  jns     short loc_18004B6D1
0x18004b6b7  mov     edx, 3FCh; void *
0x18004b6bc  mov     rcx, [rbp+28h]; this
0x18004b6c0  lea     r8, aAvcoreMfPhotog; "avcore\\mf\\photography\\components\\ge"...
0x18004b6c7  mov     r9d, eax; char *
0x18004b6ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b6cf  jmp     short loc_18004B720
0x18004b6d1  lea     rdx, [rbp+var_40]; unsigned int *
0x18004b6d5  mov     [rbp+var_40], 0
0x18004b6dc  mov     rcx, rsi; struct Windows::Devices::Geolocation::IGeolocator *
0x18004b6df  call    ?GetDesiredLocationAccuracy@@YAJPEAUIGeolocator@Geolocation@Devices@Windows@@PEAI@Z; GetDesiredLocationAccuracy(Windows::Devices::Geolocation::IGeolocator *,uint *)
0x18004b6e4  mov     ebx, eax
0x18004b6e6  test    eax, eax
0x18004b6e8  jns     short loc_18004B6F1
0x18004b6ea  mov     edx, 3FFh
0x18004b6ef  jmp     short loc_18004B6BC
0x18004b6f1  mov     rcx, [rbp+var_30]
0x18004b6f5  mov     r8, r14
0x18004b6f8  mov     r9d, [rbp+var_40]
0x18004b6fc  mov     rdx, [rbp+var_38]
0x18004b700  mov     qword ptr [rsp+70h+var_50], r15
0x18004b705  mov     rax, [rcx]
0x18004b708  mov     rax, [rax+30h]
0x18004b70c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b711  mov     ebx, eax
0x18004b713  test    eax, eax
0x18004b715  jns     short loc_18004B71E
0x18004b717  mov     edx, 400h
0x18004b71c  jmp     short loc_18004B6BC
0x18004b71e  xor     ebx, ebx
0x18004b720  lea     rcx, [rbp+var_30]
0x18004b724  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004b729  lea     rcx, [rbp+var_38]
0x18004b72d  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18004b732  mov     eax, ebx
0x18004b734  mov     rcx, [rbp+var_8]
0x18004b738  xor     rcx, rsp; StackCookie
0x18004b73b  call    __security_check_cookie
0x18004b740  mov     rbx, [rsp+70h+arg_18]
0x18004b748  add     rsp, 70h
0x18004b74c  pop     r15
0x18004b74e  pop     r14
0x18004b750  pop     rdi
0x18004b751  pop     rsi
0x18004b752  pop     rbp
0x18004b753  retn
```
