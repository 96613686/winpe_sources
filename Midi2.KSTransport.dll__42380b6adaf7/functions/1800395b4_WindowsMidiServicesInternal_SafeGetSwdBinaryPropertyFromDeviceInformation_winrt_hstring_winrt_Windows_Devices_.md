# WindowsMidiServicesInternal::SafeGetSwdBinaryPropertyFromDeviceInformation(winrt::hstring,winrt::Windows::Devices::Enumeration::DeviceInformation)

- ea: `0x1800395b4`
- end: `0x180039786`
- name: `?SafeGetSwdBinaryPropertyFromDeviceInformation@WindowsMidiServicesInternal@@YA?AU?$IReferenceArray@E@Foundation@Windows@winrt@@Uhstring@5@UDeviceInformation@Enumeration@Devices@45@@Z`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800376c0`

## callees

- `0x1800052fc`
- `0x180005374`
- `0x18000d1c0`
- `0x1800112b0`
- `0x1800136e8`
- `0x180013920`
- `0x180015348`
- `0x1800395b4`
- `0x180041010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180039636`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180039636`

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
  __int64 *v11; // rax
  __int64 v12; // rcx
  signed int v13; // eax
  __int64 v14; // r8
  char v15; // r15
  __int64 v16; // rax
  void (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // rcx
  bool v18; // zf
  void (__fastcall ***v19)(_QWORD, __int64 *, volatile signed __int32 ***); // [rsp+28h] [rbp-38h] BYREF
  __int64 v20; // [rsp+30h] [rbp-30h] BYREF
  __int64 v21; // [rsp+38h] [rbp-28h] BYREF
  _QWORD v22[4]; // [rsp+40h] [rbp-20h] BYREF
  volatile signed __int32 **v23; // [rsp+A8h] [rbp+48h] BYREF
  __int64 *v24; // [rsp+B0h] [rbp+50h]
  __int64 v25; // [rsp+B8h] [rbp+58h] BYREF

  v24 = a3;
  v23 = a2;
  if ( *a2 )
  {
    v21 = 0;
    v10 = 2;
    if ( (unsigned __int8)winrt::Windows::Foundation::operator==(a3, &v21) )
      goto LABEL_15;
    v11 = (__int64 *)winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
                       a3,
                       &v20);
    v10 = 6;
    LOBYTE(v25) = 0;
    v12 = *v11;
    LODWORD(v22[0]) = 226;
    v22[1] = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.foundation.collections.h";
    v22[2] = 0;
    v13 = (*(__int64 (__fastcall **)(__int64, volatile signed __int32 *, __int64 *))(*(_QWORD *)v12 + 64LL))(
            v12,
            *a2,
            &v25);
    if ( v13 < 0 )
      winrt::throw_hresult(v13, (unsigned int *)v22, v14);
    v15 = 0;
    if ( !(_BYTE)v25 )
LABEL_15:
      v15 = 1;
    if ( (v10 & 4) != 0 && v20 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v20);
    if ( v15 )
    {
      *a1 = 0;
    }
    else
    {
      v16 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
              a3,
              &v25);
      v22[0] = *a2;
      winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
        v16,
        &v19,
        v22);
      if ( v25 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v25);
      v23 = 0;
      if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v19, &v23) )
      {
        *a1 = 0;
        v18 = v19 == 0;
      }
      else
      {
        v17 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v19;
        if ( v19
          && (v23 = 0,
              (**v19)(v19, winrt::impl::guid_v<winrt::Windows::Foundation::IReferenceArray<unsigned char>>, &v23),
              v17 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v19,
              v23) )
        {
          *a1 = v23;
        }
        else
        {
          *a1 = 0;
        }
        v18 = v17 == 0;
      }
      if ( !v18 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v19);
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
0x1800395b4  mov     [rsp-38h+arg_10], r8
0x1800395b9  mov     [rsp-38h+arg_8], rdx
0x1800395be  push    rbp
0x1800395bf  push    rbx
0x1800395c0  push    rsi
0x1800395c1  push    rdi
0x1800395c2  push    r12
0x1800395c4  push    r14
0x1800395c6  push    r15
0x1800395c8  mov     rbp, rsp
0x1800395cb  sub     rsp, 60h
0x1800395cf  mov     rbx, r8
0x1800395d2  mov     rdi, rdx
0x1800395d5  mov     rsi, rcx
0x1800395d8  xor     r12d, r12d
0x1800395db  mov     [rbp+var_40], r12d
0x1800395df  cmp     [rdx], r12
0x1800395e2  jnz     short loc_18003963D
0x1800395e4  mov     [rcx], r12
0x1800395e7  mov     r14, [rdx]
0x1800395ea  test    r14, r14
0x1800395ed  jz      short loc_180039613
0x1800395ef  or      eax, 0FFFFFFFFh
0x1800395f2  lock xadd [r14+18h], eax
0x1800395f8  sub     eax, 1
0x1800395fb  jnz     short loc_180039632
0x1800395fd  nop
0x1800395fe  call    WINRT_IMPL_GetProcessHeap
0x180039603  mov     rcx, rax; hHeap
0x180039606  xor     edx, edx; dwFlags
0x180039608  mov     r8, r14; lpMem
0x18003960b  call    WINRT_IMPL_HeapFree
0x180039610  mov     [rdi], r12
0x180039613  cmp     [rbx], r12
0x180039616  jz      short loc_180039620
0x180039618  mov     rcx, rbx
0x18003961b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180039620  mov     rax, rsi
0x180039623  add     rsp, 60h
0x180039627  pop     r15
0x180039629  pop     r14
0x18003962b  pop     r12
0x18003962d  pop     rdi
0x18003962e  pop     rsi
0x18003962f  pop     rbx
0x180039630  pop     rbp
0x180039631  retn
0x180039632  test    eax, eax
0x180039634  jns     short loc_180039610
0x180039636  call    cs:__imp_abort
0x18003963d  mov     [rbp+var_28], r12
0x180039641  mov     r14d, 2
0x180039647  mov     [rbp+var_40], r14d
0x18003964b  lea     rdx, [rbp+var_28]
0x18003964f  mov     rcx, rbx
0x180039652  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180039657  test    al, al
0x180039659  jnz     short loc_1800396B3
0x18003965b  lea     rdx, [rbp+var_30]
0x18003965f  mov     rcx, rbx
0x180039662  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
0x180039667  nop
0x180039668  mov     r14d, 6
0x18003966e  mov     [rbp+var_40], r14d
0x180039672  mov     byte ptr [rbp+arg_18], r12b
0x180039676  mov     rcx, [rax]
0x180039679  mov     dword ptr [rbp+var_20], 0E2h
0x180039680  lea     rax, aOnecoreuapInte_7; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180039687  mov     [rbp+var_18], rax
0x18003968b  mov     [rbp+var_10], r12
0x18003968f  mov     rax, [rcx]
0x180039692  lea     r8, [rbp+arg_18]
0x180039696  mov     rdx, [rdi]
0x180039699  mov     rax, [rax+40h]
0x18003969d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800396a2  test    eax, eax
0x1800396a4  js      loc_18003977A
0x1800396aa  cmp     byte ptr [rbp+arg_18], r12b
0x1800396ae  mov     r15b, r12b
0x1800396b1  jnz     short loc_1800396B6
0x1800396b3  mov     r15b, 1
0x1800396b6  test    r14b, 4
0x1800396ba  jz      short loc_1800396CC
0x1800396bc  cmp     [rbp+var_30], r12
0x1800396c0  jz      short loc_1800396CC
0x1800396c2  lea     rcx, [rbp+var_30]
0x1800396c6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800396cb  nop
0x1800396cc  test    r15b, r15b
0x1800396cf  jz      short loc_1800396D9
0x1800396d1  mov     [rsi], r12
0x1800396d4  jmp     loc_180039772
0x1800396d9  lea     rdx, [rbp+arg_18]
0x1800396dd  mov     rcx, rbx
0x1800396e0  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
0x1800396e5  nop
0x1800396e6  mov     rcx, [rdi]
0x1800396e9  mov     [rbp+var_20], rcx
0x1800396ed  lea     r8, [rbp+var_20]
0x1800396f1  lea     rdx, [rbp+var_38]
0x1800396f5  mov     rcx, rax
0x1800396f8  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x1800396fd  nop
0x1800396fe  cmp     [rbp+arg_18], r12
0x180039702  jz      short loc_18003970D
0x180039704  lea     rcx, [rbp+arg_18]
0x180039708  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003970d  mov     [rbp+arg_8], r12
0x180039711  lea     rdx, [rbp+arg_8]
0x180039715  lea     rcx, [rbp+var_38]
0x180039719  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18003971e  test    al, al
0x180039720  jnz     short loc_18003975F
0x180039722  mov     rcx, [rbp+var_38]
0x180039726  test    rcx, rcx
0x180039729  jz      short loc_180039757
0x18003972b  mov     [rbp+arg_8], r12
0x18003972f  mov     rax, [rcx]
0x180039732  lea     r8, [rbp+arg_8]
0x180039736  lea     rdx, ??$guid_v@U?$IReferenceArray@E@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IReferenceArray<uchar>>
0x18003973d  mov     rax, [rax]
0x180039740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039745  mov     rax, [rbp+arg_8]
0x180039749  mov     rcx, [rbp+var_38]
0x18003974d  test    rax, rax
0x180039750  jz      short loc_180039757
0x180039752  mov     [rsi], rax
0x180039755  jmp     short loc_18003975A
0x180039757  mov     [rsi], r12
0x18003975a  test    rcx, rcx
0x18003975d  jmp     short loc_180039766
0x18003975f  mov     [rsi], r12
0x180039762  cmp     [rbp+var_38], r12
0x180039766  jz      short loc_180039772
0x180039768  lea     rcx, [rbp+var_38]
0x18003976c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180039771  nop
0x180039772  mov     r14, [rdi]
0x180039775  jmp     loc_1800395EA
0x18003977a  lea     rdx, [rbp+var_20]
0x18003977e  mov     ecx, eax
0x180039780  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
