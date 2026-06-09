# WindowsMidiServicesInternal::SafeGetSwdPropertyFromDeviceInformation<uint>(winrt::hstring,winrt::Windows::Devices::Enumeration::DeviceInformation,uint)

- ea: `0x140026ce8`
- end: `0x140026eec`
- name: `??$SafeGetSwdPropertyFromDeviceInformation@I@WindowsMidiServicesInternal@@YAIUhstring@winrt@@UDeviceInformation@Enumeration@Devices@Windows@2@I@Z`
- size: `516`
- prototype: `__int64 __fastcall(volatile signed __int32 **, _QWORD *)`
- caller_count: `3`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002ce1c`
- `0x14002d640`
- `0x14002fcf0`

## callees

- `0x14000617c`
- `0x1400061e8`
- `0x14000cc2c`
- `0x1400145bc`
- `0x14001bd28`
- `0x14001c390`
- `0x14001ded0`
- `0x140026ce8`
- `0x140030a38`
- `0x14005a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140026dd4`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x140026dd4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WindowsMidiServicesInternal::SafeGetSwdPropertyFromDeviceInformation<unsigned int>(
        volatile signed __int32 **a1,
        _QWORD *a2)
{
  bool v4; // zf
  bool v5; // si
  char v6; // r14
  __int64 v7; // rax
  volatile signed __int32 *v8; // rsi
  int v9; // eax
  HANDLE ProcessHeap; // rax
  __int64 v12; // rax
  void (__fastcall ***v13)(_QWORD, __int64 *, _QWORD *); // rcx
  unsigned int v14; // r14d
  volatile signed __int32 *v15; // rsi
  int v16; // eax
  HANDLE v17; // rax
  __int64 v18; // [rsp+20h] [rbp-38h] BYREF
  __int64 v19; // [rsp+28h] [rbp-30h] BYREF
  _QWORD v20[5]; // [rsp+30h] [rbp-28h] BYREF
  void (__fastcall ***v21)(_QWORD, __int64 *, __int64 *); // [rsp+A8h] [rbp+50h] BYREF

  if ( !*a1 )
  {
    v4 = *a2 == 0;
LABEL_14:
    if ( !v4 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
    return 0;
  }
  v19 = 0;
  v5 = 1;
  v6 = 1;
  if ( !(unsigned __int8)winrt::Windows::Foundation::operator==(a2, &v19) )
  {
    v7 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
           a2,
           &v18);
    v6 = 3;
    v20[0] = *a1;
    v5 = (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::HasKey(
                            v7,
                            v20) == 0;
  }
  if ( (v6 & 2) != 0 && v18 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v18);
  if ( v5 )
    goto LABEL_9;
  v12 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
          a2,
          &v18);
  v20[0] = *a1;
  winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
    v12,
    &v21,
    v20);
  if ( v18 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v18);
  v19 = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v21, &v19) )
  {
    if ( v21 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v21);
LABEL_9:
    v8 = *a1;
    if ( !*a1 )
    {
LABEL_13:
      v4 = *a2 == 0;
      goto LABEL_14;
    }
    v9 = _InterlockedDecrement(v8 + 6);
    if ( !v9 )
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v8);
LABEL_12:
      *a1 = 0;
      goto LABEL_13;
    }
    if ( v9 >= 0 )
      goto LABEL_12;
LABEL_18:
    abort();
  }
  v13 = v21;
  if ( v21
    && (v18 = 0,
        (**v21)(v21, winrt::impl::guid_v<winrt::Windows::Foundation::IReference<unsigned int>>, &v18),
        v13 = v21,
        v18) )
  {
    v14 = winrt::impl::consume_Windows_Foundation_IReference<winrt::Windows::Foundation::IReference<unsigned int>,unsigned int>::Value(&v18);
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v18);
    v13 = v21;
  }
  else
  {
    v14 = 0;
  }
  if ( v13 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v21);
  v15 = *a1;
  if ( *a1 )
  {
    v16 = _InterlockedDecrement(v15 + 6);
    if ( v16 )
    {
      if ( v16 < 0 )
        goto LABEL_18;
    }
    else
    {
      v17 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v17, 0, (LPVOID)v15);
    }
    *a1 = 0;
  }
  if ( *a2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
  return v14;
}

```

## disassembly

```asm
0x140026ce8  mov     [rsp-30h+arg_10], r8d
0x140026ced  mov     [rsp-30h+arg_8], rdx
0x140026cf2  mov     [rsp-30h+arg_0], rcx
0x140026cf7  push    rbp
0x140026cf8  push    rbx
0x140026cf9  push    rsi
0x140026cfa  push    rdi
0x140026cfb  push    r14
0x140026cfd  push    r15
0x140026cff  mov     rbp, rsp
0x140026d02  sub     rsp, 58h
0x140026d06  mov     rbx, rdx
0x140026d09  mov     rdi, rcx
0x140026d0c  xor     r15d, r15d
0x140026d0f  mov     [rbp+arg_10], r15d
0x140026d13  cmp     [rcx], r15
0x140026d16  jnz     short loc_140026D20
0x140026d18  cmp     [rdx], r15
0x140026d1b  jmp     loc_140026DB7
0x140026d20  mov     [rbp+var_30], r15
0x140026d24  mov     esi, 1
0x140026d29  mov     r14d, esi
0x140026d2c  mov     [rbp+arg_10], esi
0x140026d2f  lea     rdx, [rbp+var_30]
0x140026d33  mov     rcx, rbx
0x140026d36  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x140026d3b  test    al, al
0x140026d3d  jnz     short loc_140026D6E
0x140026d3f  lea     rdx, [rbp+var_38]
0x140026d43  mov     rcx, rbx
0x140026d46  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
0x140026d4b  nop
0x140026d4c  lea     r14d, [rsi+2]
0x140026d50  mov     [rbp+arg_10], r14d
0x140026d54  mov     rcx, [rdi]
0x140026d57  mov     [rbp+var_28], rcx
0x140026d5b  lea     rdx, [rbp+var_28]
0x140026d5f  mov     rcx, rax
0x140026d62  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::HasKey(winrt::param::hstring const &)
0x140026d67  test    al, al
0x140026d69  jz      short loc_140026D6E
0x140026d6b  mov     sil, r15b
0x140026d6e  test    r14b, 2
0x140026d72  jz      short loc_140026D84
0x140026d74  cmp     [rbp+var_38], r15
0x140026d78  jz      short loc_140026D84
0x140026d7a  lea     rcx, [rbp+var_38]
0x140026d7e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140026d83  nop
0x140026d84  test    sil, sil
0x140026d87  jz      short loc_140026DDB
0x140026d89  mov     rsi, [rdi]
0x140026d8c  test    rsi, rsi
0x140026d8f  jz      short loc_140026DB4
0x140026d91  or      eax, 0FFFFFFFFh
0x140026d94  lock xadd [rsi+18h], eax
0x140026d99  sub     eax, 1
0x140026d9c  jnz     short loc_140026DD0
0x140026d9e  nop
0x140026d9f  call    WINRT_IMPL_GetProcessHeap
0x140026da4  mov     r8, rsi; lpMem
0x140026da7  xor     edx, edx; dwFlags
0x140026da9  mov     rcx, rax; hHeap
0x140026dac  call    WINRT_IMPL_HeapFree
0x140026db1  mov     [rdi], r15
0x140026db4  cmp     [rbx], r15
0x140026db7  jz      short loc_140026DC1
0x140026db9  mov     rcx, rbx
0x140026dbc  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140026dc1  xor     eax, eax
0x140026dc3  add     rsp, 58h
0x140026dc7  pop     r15
0x140026dc9  pop     r14
0x140026dcb  pop     rdi
0x140026dcc  pop     rsi
0x140026dcd  pop     rbx
0x140026dce  pop     rbp
0x140026dcf  retn
0x140026dd0  test    eax, eax
0x140026dd2  jns     short loc_140026DB1
0x140026dd4  call    cs:__imp_abort
0x140026ddb  lea     rdx, [rbp+var_38]
0x140026ddf  mov     rcx, rbx
0x140026de2  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
0x140026de7  nop
0x140026de8  mov     rcx, [rdi]
0x140026deb  mov     [rbp+var_28], rcx
0x140026def  lea     r8, [rbp+var_28]
0x140026df3  lea     rdx, [rbp+arg_18]
0x140026df7  mov     rcx, rax
0x140026dfa  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x140026dff  nop
0x140026e00  cmp     [rbp+var_38], r15
0x140026e04  jz      short loc_140026E0F
0x140026e06  lea     rcx, [rbp+var_38]
0x140026e0a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140026e0f  mov     [rbp+var_30], r15
0x140026e13  lea     rdx, [rbp+var_30]
0x140026e17  lea     rcx, [rbp+arg_18]
0x140026e1b  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x140026e20  test    al, al
0x140026e22  jnz     loc_140026ED3
0x140026e28  mov     rcx, [rbp+arg_18]
0x140026e2c  test    rcx, rcx
0x140026e2f  jz      short loc_140026E77
0x140026e31  mov     [rbp+var_38], r15
0x140026e35  mov     rax, [rcx]
0x140026e38  lea     r8, [rbp+var_38]
0x140026e3c  lea     rdx, ??$guid_v@U?$IReference@I@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IReference<uint>>
0x140026e43  mov     rax, [rax]
0x140026e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026e4b  mov     rax, [rbp+var_38]
0x140026e4f  mov     [rbp+var_38], rax
0x140026e53  mov     rcx, [rbp+arg_18]
0x140026e57  test    rax, rax
0x140026e5a  jz      short loc_140026E77
0x140026e5c  lea     rcx, [rbp+var_38]
0x140026e60  call    ?Value@?$consume_Windows_Foundation_IReference@U?$IReference@I@Foundation@Windows@winrt@@I@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IReference<winrt::Windows::Foundation::IReference<uint>,uint>::Value(void)
0x140026e65  mov     r14d, eax
0x140026e68  lea     rcx, [rbp+var_38]
0x140026e6c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140026e71  mov     rcx, [rbp+arg_18]
0x140026e75  jmp     short loc_140026E7A
0x140026e77  mov     r14d, r15d
0x140026e7a  test    rcx, rcx
0x140026e7d  jz      short loc_140026E89
0x140026e7f  lea     rcx, [rbp+arg_18]
0x140026e83  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140026e88  nop
0x140026e89  mov     rsi, [rdi]
0x140026e8c  test    rsi, rsi
0x140026e8f  jz      short loc_140026EBE
0x140026e91  or      eax, 0FFFFFFFFh
0x140026e94  lock xadd [rsi+18h], eax
0x140026e99  sub     eax, 1
0x140026e9c  jnz     short loc_140026EB3
0x140026e9e  nop
0x140026e9f  call    WINRT_IMPL_GetProcessHeap
0x140026ea4  mov     rcx, rax; hHeap
0x140026ea7  mov     r8, rsi; lpMem
0x140026eaa  xor     edx, edx; dwFlags
0x140026eac  call    WINRT_IMPL_HeapFree
0x140026eb1  jmp     short loc_140026EBB
0x140026eb3  test    eax, eax
0x140026eb5  js      loc_140026DD4
0x140026ebb  mov     [rdi], r15
0x140026ebe  cmp     [rbx], r15
0x140026ec1  jz      short loc_140026ECB
0x140026ec3  mov     rcx, rbx
0x140026ec6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140026ecb  mov     eax, r14d
0x140026ece  jmp     loc_140026DC3
0x140026ed3  cmp     [rbp+arg_18], r15
0x140026ed7  jz      loc_140026D89
0x140026edd  lea     rcx, [rbp+arg_18]
0x140026ee1  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140026ee6  jmp     loc_140026D89
```
