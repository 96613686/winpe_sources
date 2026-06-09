# `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateWatcher(winrt::param::hstring const &,winrt::param::iterable<winrt::hstring> const &,winrt::Windows::Devices::Enumeration::DeviceInformationKind const &)'::`2'::_lambda_1_::operator()(winrt::Windows::Devices::Enumeration::IDeviceInformationStatics2 const &)

- ea: `0x18000d70c`
- end: `0x18000d78a`
- name: `??R_lambda_1_@?1??CreateWatcher@DeviceInformation@Enumeration@Devices@Windows@winrt@@SA@AEBUhstring@param@6@AEBU?$iterable@Uhstring@winrt@@@86@AEBW4DeviceInformationKind@3456@@Z@QEBA@AEBUIDeviceInformationStatics2@3456@@Z`
- size: `126`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bafc`
- `0x18000e950`

## callees

- `0x18000d70c`
- `0x180011a4c`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall `winrt::Windows::Devices::Enumeration::DeviceInformation::CreateWatcher'::`2'::_lambda_1_::operator()(
        __int64 a1,
        _QWORD *a2,
        __int64 **a3)
{
  __int64 *v3; // r10
  unsigned int *v4; // r9
  __int64 *v6; // r8
  __int64 *v7; // rdx
  __int64 v8; // r9
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rax
  signed int v12; // eax
  __int64 v13; // r8
  unsigned int v15; // [rsp+38h] [rbp-20h] BYREF
  const char *v16; // [rsp+40h] [rbp-18h]
  __int64 v17; // [rsp+48h] [rbp-10h]
  __int64 v18; // [rsp+60h] [rbp+8h] BYREF

  v3 = *a3;
  v4 = *(unsigned int **)(a1 + 16);
  v6 = *(__int64 **)(a1 + 8);
  v7 = *(__int64 **)a1;
  v15 = 1008;
  v8 = *v4;
  v9 = *v6;
  v10 = *v7;
  v16 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Devices.Enumeration.h";
  v18 = 0;
  v11 = *v3;
  v17 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64, __int64 *))(v11 + 72))(v3, v10, v9, v8, &v18);
  if ( v12 < 0 )
    winrt::throw_hresult(v12, &v15, v13);
  *a2 = v18;
  return a2;
}

```

## disassembly

```asm
0x18000d70c  mov     r11, rsp
0x18000d70f  push    rbx
0x18000d710  sub     rsp, 50h
0x18000d714  mov     r10, [r8]
0x18000d717  lea     rax, aOnecoreuapInte_5; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18000d71e  mov     r9, [rcx+10h]
0x18000d722  mov     rbx, rdx
0x18000d725  mov     r8, [rcx+8]
0x18000d729  mov     rdx, [rcx]
0x18000d72c  lea     rcx, [r11+8]
0x18000d730  mov     [rsp+58h+var_20], 3F0h
0x18000d738  mov     r9d, [r9]
0x18000d73b  mov     r8, [r8]
0x18000d73e  mov     rdx, [rdx]
0x18000d741  mov     [r11-18h], rax
0x18000d745  mov     qword ptr [r11+8], 0
0x18000d74d  mov     rax, [r10]
0x18000d750  mov     [r11-38h], rcx
0x18000d754  mov     rcx, r10
0x18000d757  mov     qword ptr [r11-10h], 0
0x18000d75f  mov     rax, [rax+48h]
0x18000d763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d768  test    eax, eax
0x18000d76a  js      short loc_18000D77D
0x18000d76c  mov     rax, [rsp+58h+arg_0]
0x18000d771  mov     [rbx], rax
0x18000d774  mov     rax, rbx
0x18000d777  add     rsp, 50h
0x18000d77b  pop     rbx
0x18000d77c  retn
0x18000d77d  lea     rdx, [rsp+58h+var_20]
0x18000d782  mov     ecx, eax
0x18000d784  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
