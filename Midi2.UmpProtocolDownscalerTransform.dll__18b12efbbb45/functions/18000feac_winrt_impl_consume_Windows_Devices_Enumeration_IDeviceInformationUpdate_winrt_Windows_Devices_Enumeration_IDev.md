# winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformationUpdate<winrt::Windows::Devices::Enumeration::IDeviceInformationUpdate>::Properties(void)

- ea: `0x18000feac`
- end: `0x18000ff0f`
- name: `?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformationUpdate@UIDeviceInformationUpdate@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000fac0`

## callees

- `0x18000feac`
- `0x180011a4c`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformationUpdate<winrt::Windows::Devices::Enumeration::IDeviceInformationUpdate>::Properties(
        __int64 **a1,
        _QWORD *a2)
{
  __int64 *v2; // rcx
  __int64 v4; // rax
  signed int v5; // eax
  __int64 v6; // r8
  unsigned int v8; // [rsp+28h] [rbp-20h] BYREF
  const char *v9; // [rsp+30h] [rbp-18h]
  __int64 v10; // [rsp+38h] [rbp-10h]
  __int64 v11; // [rsp+50h] [rbp+8h] BYREF

  v2 = *a1;
  v8 = 1098;
  v9 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Devices.Enumeration.h";
  v11 = 0;
  v4 = *v2;
  v10 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v4 + 56))(v2, &v11);
  if ( v5 < 0 )
    winrt::throw_hresult(v5, &v8, v6);
  *a2 = v11;
  return a2;
}

```

## disassembly

```asm
0x18000feac  mov     r11, rsp
0x18000feaf  push    rbx
0x18000feb0  sub     rsp, 40h
0x18000feb4  mov     rcx, [rcx]
0x18000feb7  lea     rax, aOnecoreuapInte_6; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18000febe  mov     [rsp+48h+var_20], 44Ah
0x18000fec6  mov     rbx, rdx
0x18000fec9  mov     [r11-18h], rax
0x18000fecd  lea     rdx, [r11+8]
0x18000fed1  mov     qword ptr [r11+8], 0
0x18000fed9  mov     rax, [rcx]
0x18000fedc  mov     qword ptr [r11-10h], 0
0x18000fee4  mov     rax, [rax+38h]
0x18000fee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000feed  test    eax, eax
0x18000feef  js      short loc_18000FF02
0x18000fef1  mov     rax, [rsp+48h+arg_0]
0x18000fef6  mov     [rbx], rax
0x18000fef9  mov     rax, rbx
0x18000fefc  add     rsp, 40h
0x18000ff00  pop     rbx
0x18000ff01  retn
0x18000ff02  lea     rdx, [rsp+48h+var_20]
0x18000ff07  mov     ecx, eax
0x18000ff09  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
