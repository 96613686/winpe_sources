# ??$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@1@I@Z

- ea: `0x18000efa8`
- end: `0x18000f09b`
- name: `??$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@1@I@Z`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013b14`

## callees

- `0x1800041d0`
- `0x1800050b4`
- `0x180005150`
- `0x18000efa8`
- `0x1800145d8`
- `0x180014804`
- `0x180014974`
- `0x180032010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Devices::Enumeration::DeviceInformation>>(
        __int64 *a1)
{
  const struct winrt::impl::slim_source_location *v2; // rdx
  HANDLE EventW; // rsi
  __int64 v4; // rcx
  signed int v5; // eax
  __int64 v6; // r8
  unsigned int v7; // ebx
  char *v9; // [rsp+20h] [rbp-30h] BYREF
  const char *v10; // [rsp+28h] [rbp-28h]
  __int64 v11; // [rsp+30h] [rbp-20h]
  unsigned int v12; // [rsp+38h] [rbp-18h] BYREF
  const char *v13; // [rsp+40h] [rbp-10h]
  __int64 v14; // [rsp+48h] [rbp-8h]
  char *v15; // [rsp+90h] [rbp+40h]

  LODWORD(v9) = 5095;
  v10 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Foundation.h";
  v11 = 0;
  EventW = WINRT_IMPL_CreateEventW(0, 1, 0, 0);
  if ( !EventW )
    winrt::throw_last_error((winrt *)&v9, v2);
  v15 = (char *)operator new(0x20u);
  *((_DWORD *)v15 + 2) = 1;
  *((_QWORD *)v15 + 2) = EventW;
  *((_DWORD *)v15 + 6) = 0;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v15 = ___7__delegate_U__AsyncOperationCompletedHandler_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___234_I_Z__impl_winrt__6B_;
  v9 = v15;
  v10 = v15 + 16;
  v4 = *a1;
  v12 = 332;
  v13 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Foundation.h";
  v14 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 48LL))(v4);
  if ( v5 < 0 )
    winrt::throw_hresult(v5, &v12, v6);
  WaitForSingleObject_0(*((HANDLE *)v15 + 2), 0xFFFFFFFF);
  v7 = *((_DWORD *)v15 + 6);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v9);
  return v7;
}

```

## disassembly

```asm
0x18000efa8  mov     [rsp-28h+arg_0], rbx
0x18000efad  push    rbp
0x18000efae  push    rsi
0x18000efaf  push    rdi
0x18000efb0  push    r12
0x18000efb2  push    r14
0x18000efb4  mov     rbp, rsp
0x18000efb7  sub     rsp, 50h
0x18000efbb  mov     r14, rcx
0x18000efbe  mov     dword ptr [rbp+var_30], 13E7h
0x18000efc5  lea     r12, aOnecoreuapInte_3; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18000efcc  mov     [rbp+var_28], r12
0x18000efd0  mov     [rbp+var_20], 0
0x18000efd8  xor     r9d, r9d; lpName
0x18000efdb  xor     r8d, r8d; bInitialState
0x18000efde  lea     edi, [r9+1]
0x18000efe2  mov     edx, edi; bManualReset
0x18000efe4  xor     ecx, ecx; lpEventAttributes
0x18000efe6  call    WINRT_IMPL_CreateEventW
0x18000efeb  mov     rsi, rax
0x18000efee  test    rax, rax
0x18000eff1  jz      loc_18000F091
0x18000eff7  mov     [rbp+var_30], rax
0x18000effb  xor     ebx, ebx
0x18000effd  mov     [rbp+var_28], rbx
0x18000f001  lea     ecx, [rdi+1Fh]; Size
0x18000f004  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f009  mov     rdx, rax
0x18000f00c  mov     [rbp+arg_10], rax
0x18000f010  mov     [rax+8], edi
0x18000f013  lea     rdi, [rax+10h]
0x18000f017  mov     [rdi], rsi
0x18000f01a  mov     [rdi+8], ebx
0x18000f01d  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000f024  lea     rax, ??_7?$delegate@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@winrt@@6B@
0x18000f02b  mov     [rdx], rax
0x18000f02e  mov     [rbp+var_30], rdx
0x18000f032  mov     [rbp+var_28], rdi
0x18000f036  mov     rcx, [r14]
0x18000f039  mov     [rbp+var_18], 14Ch
0x18000f040  mov     [rbp+var_10], r12
0x18000f044  mov     [rbp+var_8], rbx
0x18000f048  mov     rax, [rcx]
0x18000f04b  mov     rax, [rax+30h]
0x18000f04f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f054  test    eax, eax
0x18000f056  js      short loc_18000F085
0x18000f058  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000f05b  mov     rcx, [rdi]; hHandle
0x18000f05e  call    WaitForSingleObject_0
0x18000f063  mov     ebx, [rdi+8]
0x18000f066  lea     rcx, [rbp+var_30]
0x18000f06a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000f06f  mov     eax, ebx
0x18000f071  mov     rbx, [rsp+50h+arg_0]
0x18000f079  add     rsp, 50h
0x18000f07d  pop     r14
0x18000f07f  pop     r12
0x18000f081  pop     rdi
0x18000f082  pop     rsi
0x18000f083  pop     rbp
0x18000f084  retn
0x18000f085  lea     rdx, [rbp+var_18]
0x18000f089  mov     ecx, eax
0x18000f08b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000f091  lea     rcx, [rbp+var_30]; this
0x18000f095  call    ?throw_last_error@winrt@@YAXAEBUslim_source_location@impl@1@@Z; winrt::throw_last_error(winrt::impl::slim_source_location const &)
```
