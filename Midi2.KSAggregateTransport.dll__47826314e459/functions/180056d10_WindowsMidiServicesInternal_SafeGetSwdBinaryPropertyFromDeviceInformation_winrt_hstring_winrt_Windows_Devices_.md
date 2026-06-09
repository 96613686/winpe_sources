# WindowsMidiServicesInternal::SafeGetSwdBinaryPropertyFromDeviceInformation(winrt::hstring,winrt::Windows::Devices::Enumeration::DeviceInformation)

- ea: `0x180056d10`
- end: `0x180056eb0`
- name: `?SafeGetSwdBinaryPropertyFromDeviceInformation@WindowsMidiServicesInternal@@YA?AU?$IReferenceArray@E@Foundation@Windows@winrt@@Uhstring@5@UDeviceInformation@Enumeration@Devices@45@@Z`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800553b4`

## callees

- `0x180005f2c`
- `0x180005fa4`
- `0x180010b94`
- `0x180014ff4`
- `0x1800161e0`
- `0x180017af8`
- `0x180017d30`
- `0x180056d10`
- `0x18005e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180056d92`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180056d92`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
volatile signed __int32 ***__fastcall WindowsMidiServicesInternal::SafeGetSwdBinaryPropertyFromDeviceInformation(
        volatile signed __int32 ***a1,
        volatile signed __int32 **a2,
        __int64 *a3)
{
  volatile signed __int32 *v6; // r14
  int v7; // eax
  HANDLE ProcessHeap; // rax
  char v10; // r14
  __int64 v11; // rax
  char v12; // r15
  __int64 v13; // rax
  void (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rcx
  bool v15; // zf
  __int64 v16; // [rsp+28h] [rbp-38h] BYREF
  __int64 v17; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v18[5]; // [rsp+38h] [rbp-28h] BYREF
  volatile signed __int32 **v19; // [rsp+A8h] [rbp+48h] BYREF
  __int64 *v20; // [rsp+B0h] [rbp+50h]
  void (__fastcall ***v21)(_QWORD, __int64 *, volatile signed __int32 ***); // [rsp+B8h] [rbp+58h] BYREF

  v20 = a3;
  v19 = a2;
  if ( *a2 )
  {
    v17 = 0;
    v10 = 2;
    if ( (unsigned __int8)winrt::Windows::Foundation::operator==(a3, &v17)
      || (v11 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
                  a3,
                  &v16),
          v10 = 6,
          v18[0] = *a2,
          v12 = 0,
          !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::HasKey(
                              v11,
                              v18)) )
    {
      v12 = 1;
    }
    if ( (v10 & 4) != 0 && v16 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v16);
    if ( v12 )
    {
      *a1 = 0;
    }
    else
    {
      v13 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
              a3,
              &v16);
      v18[0] = *a2;
      winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
        v13,
        &v21,
        v18);
      if ( v16 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v16);
      v19 = 0;
      if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v21, &v19) )
      {
        *a1 = 0;
        v15 = v21 == 0;
      }
      else
      {
        v14 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v21;
        if ( v21
          && (v19 = 0,
              (**v21)(v21, winrt::impl::guid_v<winrt::Windows::Foundation::IReferenceArray<unsigned char>>, &v19),
              v14 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v21,
              v19) )
        {
          *a1 = v19;
        }
        else
        {
          *a1 = 0;
        }
        v15 = v14 == 0;
      }
      if ( !v15 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v21);
    }
    v6 = *a2;
  }
  else
  {
    *a1 = 0;
    v6 = *a2;
  }
  if ( v6 )
  {
    v7 = _InterlockedDecrement(v6 + 6);
    if ( v7 )
    {
      if ( v7 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v6);
    }
    *a2 = 0;
  }
  if ( *a3 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a3);
  return a1;
}

```

## disassembly

```asm
0x180056d10  mov     [rsp-38h+arg_10], r8
0x180056d15  mov     [rsp-38h+arg_8], rdx
0x180056d1a  push    rbp
0x180056d1b  push    rbx
0x180056d1c  push    rsi
0x180056d1d  push    rdi
0x180056d1e  push    r12
0x180056d20  push    r14
0x180056d22  push    r15
0x180056d24  mov     rbp, rsp
0x180056d27  sub     rsp, 60h
0x180056d2b  mov     rbx, r8
0x180056d2e  mov     rdi, rdx
0x180056d31  mov     rsi, rcx
0x180056d34  xor     r12d, r12d
0x180056d37  mov     [rbp+var_40], r12d
0x180056d3b  cmp     [rdx], r12
0x180056d3e  jnz     short loc_180056D99
0x180056d40  mov     [rcx], r12
0x180056d43  mov     r14, [rdx]
0x180056d46  test    r14, r14
0x180056d49  jz      short loc_180056D6F
0x180056d4b  or      eax, 0FFFFFFFFh
0x180056d4e  lock xadd [r14+18h], eax
0x180056d54  sub     eax, 1
0x180056d57  jnz     short loc_180056D8E
0x180056d59  nop
0x180056d5a  call    WINRT_IMPL_GetProcessHeap
0x180056d5f  mov     rcx, rax; hHeap
0x180056d62  xor     edx, edx; dwFlags
0x180056d64  mov     r8, r14; lpMem
0x180056d67  call    WINRT_IMPL_HeapFree
0x180056d6c  mov     [rdi], r12
0x180056d6f  cmp     [rbx], r12
0x180056d72  jz      short loc_180056D7C
0x180056d74  mov     rcx, rbx
0x180056d77  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180056d7c  mov     rax, rsi
0x180056d7f  add     rsp, 60h
0x180056d83  pop     r15
0x180056d85  pop     r14
0x180056d87  pop     r12
0x180056d89  pop     rdi
0x180056d8a  pop     rsi
0x180056d8b  pop     rbx
0x180056d8c  pop     rbp
0x180056d8d  retn
0x180056d8e  test    eax, eax
0x180056d90  jns     short loc_180056D6C
0x180056d92  call    cs:__imp_abort
0x180056d99  mov     [rbp+var_30], r12
0x180056d9d  mov     r14d, 2
0x180056da3  mov     [rbp+var_40], r14d
0x180056da7  lea     rdx, [rbp+var_30]
0x180056dab  mov     rcx, rbx
0x180056dae  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180056db3  test    al, al
0x180056db5  jnz     short loc_180056DE8
0x180056db7  lea     rdx, [rbp+var_38]
0x180056dbb  mov     rcx, rbx
0x180056dbe  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
0x180056dc3  nop
0x180056dc4  mov     r14d, 6
0x180056dca  mov     [rbp+var_40], r14d
0x180056dce  mov     rcx, [rdi]
0x180056dd1  mov     [rbp+var_28], rcx
0x180056dd5  lea     rdx, [rbp+var_28]
0x180056dd9  mov     rcx, rax
0x180056ddc  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::HasKey(winrt::param::hstring const &)
0x180056de1  test    al, al
0x180056de3  mov     r15b, r12b
0x180056de6  jnz     short loc_180056DEB
0x180056de8  mov     r15b, 1
0x180056deb  test    r14b, 4
0x180056def  jz      short loc_180056E01
0x180056df1  cmp     [rbp+var_38], r12
0x180056df5  jz      short loc_180056E01
0x180056df7  lea     rcx, [rbp+var_38]
0x180056dfb  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180056e00  nop
0x180056e01  test    r15b, r15b
0x180056e04  jz      short loc_180056E0E
0x180056e06  mov     [rsi], r12
0x180056e09  jmp     loc_180056EA7
0x180056e0e  lea     rdx, [rbp+var_38]
0x180056e12  mov     rcx, rbx
0x180056e15  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
0x180056e1a  nop
0x180056e1b  mov     rcx, [rdi]
0x180056e1e  mov     [rbp+var_28], rcx
0x180056e22  lea     r8, [rbp+var_28]
0x180056e26  lea     rdx, [rbp+arg_18]
0x180056e2a  mov     rcx, rax
0x180056e2d  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x180056e32  nop
0x180056e33  cmp     [rbp+var_38], r12
0x180056e37  jz      short loc_180056E42
0x180056e39  lea     rcx, [rbp+var_38]
0x180056e3d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180056e42  mov     [rbp+arg_8], r12
0x180056e46  lea     rdx, [rbp+arg_8]
0x180056e4a  lea     rcx, [rbp+arg_18]
0x180056e4e  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180056e53  test    al, al
0x180056e55  jnz     short loc_180056E94
0x180056e57  mov     rcx, [rbp+arg_18]
0x180056e5b  test    rcx, rcx
0x180056e5e  jz      short loc_180056E8C
0x180056e60  mov     [rbp+arg_8], r12
0x180056e64  mov     rax, [rcx]
0x180056e67  lea     r8, [rbp+arg_8]
0x180056e6b  lea     rdx, ??$guid_v@U?$IReferenceArray@E@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IReferenceArray<uchar>>
0x180056e72  mov     rax, [rax]
0x180056e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056e7a  mov     rax, [rbp+arg_8]
0x180056e7e  mov     rcx, [rbp+arg_18]
0x180056e82  test    rax, rax
0x180056e85  jz      short loc_180056E8C
0x180056e87  mov     [rsi], rax
0x180056e8a  jmp     short loc_180056E8F
0x180056e8c  mov     [rsi], r12
0x180056e8f  test    rcx, rcx
0x180056e92  jmp     short loc_180056E9B
0x180056e94  mov     [rsi], r12
0x180056e97  cmp     [rbp+arg_18], r12
0x180056e9b  jz      short loc_180056EA7
0x180056e9d  lea     rcx, [rbp+arg_18]
0x180056ea1  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180056ea6  nop
0x180056ea7  mov     r14, [rdi]
0x180056eaa  jmp     loc_180056D46
```
