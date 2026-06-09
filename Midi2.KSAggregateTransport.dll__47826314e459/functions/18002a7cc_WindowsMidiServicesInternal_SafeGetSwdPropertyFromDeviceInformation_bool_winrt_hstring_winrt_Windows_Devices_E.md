# WindowsMidiServicesInternal::SafeGetSwdPropertyFromDeviceInformation<bool>(winrt::hstring,winrt::Windows::Devices::Enumeration::DeviceInformation,bool)

- ea: `0x18002a7cc`
- end: `0x18002aa08`
- name: `??$SafeGetSwdPropertyFromDeviceInformation@_N@WindowsMidiServicesInternal@@YA_NUhstring@winrt@@UDeviceInformation@Enumeration@Devices@Windows@2@_N@Z`
- size: `572`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003dcf0`

## callees

- `0x180005f2c`
- `0x180005fa4`
- `0x180010b94`
- `0x180014ff4`
- `0x1800161e0`
- `0x180017af8`
- `0x180017d30`
- `0x18001a4a8`
- `0x18002a7cc`
- `0x18005e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002a8b8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002a8b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
char __fastcall WindowsMidiServicesInternal::SafeGetSwdPropertyFromDeviceInformation<bool>(
        volatile signed __int32 **a1,
        __int64 *a2)
{
  bool v4; // zf
  bool v5; // si
  char v6; // r14
  __int64 v7; // rax
  volatile signed __int32 *v8; // rsi
  int v9; // eax
  HANDLE ProcessHeap; // rax
  __int64 v12; // rax
  void (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rcx
  signed int v14; // eax
  __int64 v15; // r8
  char v16; // r14
  volatile signed __int32 *v17; // rsi
  int v18; // eax
  HANDLE v19; // rax
  __int64 v20; // [rsp+20h] [rbp-38h] BYREF
  __int64 v21; // [rsp+28h] [rbp-30h] BYREF
  _QWORD v22[5]; // [rsp+30h] [rbp-28h] BYREF
  int v23; // [rsp+A0h] [rbp+48h] BYREF
  void (__fastcall ***v24)(_QWORD, __int64 *, __int64 *); // [rsp+A8h] [rbp+50h] BYREF

  v23 = 0;
  if ( !*a1 )
  {
    v4 = *a2 == 0;
LABEL_14:
    if ( !v4 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
    return 0;
  }
  v21 = 0;
  v5 = 1;
  v6 = 1;
  v23 = 1;
  if ( !(unsigned __int8)winrt::Windows::Foundation::operator==(a2, &v21) )
  {
    v7 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
           a2,
           &v20);
    v6 = 3;
    v23 = 3;
    v22[0] = *a1;
    v5 = (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::HasKey(
                            v7,
                            v22) == 0;
  }
  if ( (v6 & 2) != 0 && v20 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v20);
  if ( v5 )
    goto LABEL_9;
  v12 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
          a2,
          &v20);
  v22[0] = *a1;
  winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
    v12,
    &v24,
    v22);
  if ( v20 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v20);
  v21 = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v24, &v21) )
  {
    if ( v24 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v24);
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
  v13 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v24;
  if ( v24
    && (v20 = 0,
        (**v24)(v24, winrt::impl::guid_v<winrt::Windows::Foundation::IReference<bool>>, &v20),
        v13 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v24,
        v20) )
  {
    LOBYTE(v23) = 0;
    LODWORD(v22[0]) = 1984;
    v22[1] = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.h";
    v22[2] = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 48LL))(v20, &v23);
    if ( v14 < 0 )
      winrt::throw_hresult(v14, (unsigned int *)v22, v15);
    v16 = v23;
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v20);
    v13 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v24;
  }
  else
  {
    v16 = 0;
  }
  if ( v13 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v24);
  v17 = *a1;
  if ( *a1 )
  {
    v18 = _InterlockedDecrement(v17 + 6);
    if ( v18 )
    {
      if ( v18 < 0 )
        goto LABEL_18;
    }
    else
    {
      v19 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v19, 0, (LPVOID)v17);
    }
    *a1 = 0;
  }
  if ( *a2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
  return v16;
}

```

## disassembly

```asm
0x18002a7cc  mov     byte ptr [rsp-30h+arg_10], r8b
0x18002a7d1  mov     [rsp-30h+arg_8], rdx
0x18002a7d6  mov     [rsp-30h+arg_0], rcx
0x18002a7db  push    rbp
0x18002a7dc  push    rbx
0x18002a7dd  push    rsi
0x18002a7de  push    rdi
0x18002a7df  push    r14
0x18002a7e1  push    r15
0x18002a7e3  mov     rbp, rsp
0x18002a7e6  sub     rsp, 58h
0x18002a7ea  mov     rbx, rdx
0x18002a7ed  mov     rdi, rcx
0x18002a7f0  xor     r15d, r15d
0x18002a7f3  mov     [rbp+arg_10], r15d
0x18002a7f7  cmp     [rcx], r15
0x18002a7fa  jnz     short loc_18002A804
0x18002a7fc  cmp     [rdx], r15
0x18002a7ff  jmp     loc_18002A89B
0x18002a804  mov     [rbp+var_30], r15
0x18002a808  mov     esi, 1
0x18002a80d  mov     r14d, esi
0x18002a810  mov     [rbp+arg_10], esi
0x18002a813  lea     rdx, [rbp+var_30]
0x18002a817  mov     rcx, rbx
0x18002a81a  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18002a81f  test    al, al
0x18002a821  jnz     short loc_18002A852
0x18002a823  lea     rdx, [rbp+var_38]
0x18002a827  mov     rcx, rbx
0x18002a82a  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
0x18002a82f  nop
0x18002a830  lea     r14d, [rsi+2]
0x18002a834  mov     [rbp+arg_10], r14d
0x18002a838  mov     rcx, [rdi]
0x18002a83b  mov     [rbp+var_28], rcx
0x18002a83f  lea     rdx, [rbp+var_28]
0x18002a843  mov     rcx, rax
0x18002a846  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::HasKey(winrt::param::hstring const &)
0x18002a84b  test    al, al
0x18002a84d  jz      short loc_18002A852
0x18002a84f  mov     sil, r15b
0x18002a852  test    r14b, 2
0x18002a856  jz      short loc_18002A868
0x18002a858  cmp     [rbp+var_38], r15
0x18002a85c  jz      short loc_18002A868
0x18002a85e  lea     rcx, [rbp+var_38]
0x18002a862  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002a867  nop
0x18002a868  test    sil, sil
0x18002a86b  jz      short loc_18002A8BF
0x18002a86d  mov     rsi, [rdi]
0x18002a870  test    rsi, rsi
0x18002a873  jz      short loc_18002A898
0x18002a875  or      eax, 0FFFFFFFFh
0x18002a878  lock xadd [rsi+18h], eax
0x18002a87d  sub     eax, 1
0x18002a880  jnz     short loc_18002A8B4
0x18002a882  nop
0x18002a883  call    WINRT_IMPL_GetProcessHeap
0x18002a888  mov     r8, rsi; lpMem
0x18002a88b  xor     edx, edx; dwFlags
0x18002a88d  mov     rcx, rax; hHeap
0x18002a890  call    WINRT_IMPL_HeapFree
0x18002a895  mov     [rdi], r15
0x18002a898  cmp     [rbx], r15
0x18002a89b  jz      short loc_18002A8A5
0x18002a89d  mov     rcx, rbx
0x18002a8a0  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002a8a5  xor     al, al
0x18002a8a7  add     rsp, 58h
0x18002a8ab  pop     r15
0x18002a8ad  pop     r14
0x18002a8af  pop     rdi
0x18002a8b0  pop     rsi
0x18002a8b1  pop     rbx
0x18002a8b2  pop     rbp
0x18002a8b3  retn
0x18002a8b4  test    eax, eax
0x18002a8b6  jns     short loc_18002A895
0x18002a8b8  call    cs:__imp_abort
0x18002a8bf  lea     rdx, [rbp+var_38]
0x18002a8c3  mov     rcx, rbx
0x18002a8c6  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
0x18002a8cb  nop
0x18002a8cc  mov     rcx, [rdi]
0x18002a8cf  mov     [rbp+var_28], rcx
0x18002a8d3  lea     r8, [rbp+var_28]
0x18002a8d7  lea     rdx, [rbp+arg_18]
0x18002a8db  mov     rcx, rax
0x18002a8de  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x18002a8e3  nop
0x18002a8e4  cmp     [rbp+var_38], r15
0x18002a8e8  jz      short loc_18002A8F3
0x18002a8ea  lea     rcx, [rbp+var_38]
0x18002a8ee  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002a8f3  mov     [rbp+var_30], r15
0x18002a8f7  lea     rdx, [rbp+var_30]
0x18002a8fb  lea     rcx, [rbp+arg_18]
0x18002a8ff  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18002a904  test    al, al
0x18002a906  jnz     loc_18002A9E4
0x18002a90c  mov     rcx, [rbp+arg_18]
0x18002a910  test    rcx, rcx
0x18002a913  jz      short loc_18002A988
0x18002a915  mov     [rbp+var_38], r15
0x18002a919  mov     rax, [rcx]
0x18002a91c  lea     r8, [rbp+var_38]
0x18002a920  lea     rdx, ??$guid_v@U?$IReference@_N@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IReference<bool>>
0x18002a927  mov     rax, [rax]
0x18002a92a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a92f  mov     r8, [rbp+var_38]
0x18002a933  mov     [rbp+var_38], r8
0x18002a937  mov     rcx, [rbp+arg_18]
0x18002a93b  test    r8, r8
0x18002a93e  jz      short loc_18002A988
0x18002a940  mov     byte ptr [rbp+arg_10], r15b
0x18002a944  mov     dword ptr [rbp+var_28], 7C0h
0x18002a94b  lea     rax, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18002a952  mov     [rbp+var_20], rax
0x18002a956  mov     [rbp+var_18], r15
0x18002a95a  mov     rax, [r8]
0x18002a95d  lea     rdx, [rbp+arg_10]
0x18002a961  mov     rcx, r8
0x18002a964  mov     rax, [rax+30h]
0x18002a968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a96d  test    eax, eax
0x18002a96f  js      loc_18002A9FC
0x18002a975  mov     r14b, byte ptr [rbp+arg_10]
0x18002a979  lea     rcx, [rbp+var_38]
0x18002a97d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002a982  mov     rcx, [rbp+arg_18]
0x18002a986  jmp     short loc_18002A98B
0x18002a988  mov     r14b, r15b
0x18002a98b  test    rcx, rcx
0x18002a98e  jz      short loc_18002A99A
0x18002a990  lea     rcx, [rbp+arg_18]
0x18002a994  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002a999  nop
0x18002a99a  mov     rsi, [rdi]
0x18002a99d  test    rsi, rsi
0x18002a9a0  jz      short loc_18002A9CF
0x18002a9a2  or      eax, 0FFFFFFFFh
0x18002a9a5  lock xadd [rsi+18h], eax
0x18002a9aa  sub     eax, 1
0x18002a9ad  jnz     short loc_18002A9C4
0x18002a9af  nop
0x18002a9b0  call    WINRT_IMPL_GetProcessHeap
0x18002a9b5  mov     rcx, rax; hHeap
0x18002a9b8  mov     r8, rsi; lpMem
0x18002a9bb  xor     edx, edx; dwFlags
0x18002a9bd  call    WINRT_IMPL_HeapFree
0x18002a9c2  jmp     short loc_18002A9CC
0x18002a9c4  test    eax, eax
0x18002a9c6  js      loc_18002A8B8
0x18002a9cc  mov     [rdi], r15
0x18002a9cf  cmp     [rbx], r15
0x18002a9d2  jz      short loc_18002A9DC
0x18002a9d4  mov     rcx, rbx
0x18002a9d7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002a9dc  mov     al, r14b
0x18002a9df  jmp     loc_18002A8A7
0x18002a9e4  cmp     [rbp+arg_18], r15
0x18002a9e8  jz      loc_18002A86D
0x18002a9ee  lea     rcx, [rbp+arg_18]
0x18002a9f2  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002a9f7  jmp     loc_18002A86D
0x18002a9fc  lea     rdx, [rbp+var_28]
0x18002aa00  mov     ecx, eax
0x18002aa02  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
