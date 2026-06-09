# ??$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@1@I@Z

- ea: `0x18000c354`
- end: `0x18000c447`
- name: `??$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@1@I@Z`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011044`

## callees

- `0x180002ec0`
- `0x180003ac8`
- `0x180003b6d`
- `0x18000c354`
- `0x180011a4c`
- `0x180011c78`
- `0x180011e0c`
- `0x180013010`

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
0x18000c354  mov     [rsp-28h+arg_0], rbx
0x18000c359  push    rbp
0x18000c35a  push    rsi
0x18000c35b  push    rdi
0x18000c35c  push    r12
0x18000c35e  push    r14
0x18000c360  mov     rbp, rsp
0x18000c363  sub     rsp, 50h
0x18000c367  mov     r14, rcx
0x18000c36a  mov     dword ptr [rbp+var_30], 13E7h
0x18000c371  lea     r12, aOnecoreuapInte_4; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18000c378  mov     [rbp+var_28], r12
0x18000c37c  mov     [rbp+var_20], 0
0x18000c384  xor     r9d, r9d; lpName
0x18000c387  xor     r8d, r8d; bInitialState
0x18000c38a  lea     edi, [r9+1]
0x18000c38e  mov     edx, edi; bManualReset
0x18000c390  xor     ecx, ecx; lpEventAttributes
0x18000c392  call    WINRT_IMPL_CreateEventW
0x18000c397  mov     rsi, rax
0x18000c39a  test    rax, rax
0x18000c39d  jz      loc_18000C43D
0x18000c3a3  mov     [rbp+var_30], rax
0x18000c3a7  xor     ebx, ebx
0x18000c3a9  mov     [rbp+var_28], rbx
0x18000c3ad  lea     ecx, [rdi+1Fh]; Size
0x18000c3b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c3b5  mov     rdx, rax
0x18000c3b8  mov     [rbp+arg_10], rax
0x18000c3bc  mov     [rax+8], edi
0x18000c3bf  lea     rdi, [rax+10h]
0x18000c3c3  mov     [rdi], rsi
0x18000c3c6  mov     [rdi+8], ebx
0x18000c3c9  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000c3d0  lea     rax, ??_7?$delegate@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@winrt@@6B@
0x18000c3d7  mov     [rdx], rax
0x18000c3da  mov     [rbp+var_30], rdx
0x18000c3de  mov     [rbp+var_28], rdi
0x18000c3e2  mov     rcx, [r14]
0x18000c3e5  mov     [rbp+var_18], 14Ch
0x18000c3ec  mov     [rbp+var_10], r12
0x18000c3f0  mov     [rbp+var_8], rbx
0x18000c3f4  mov     rax, [rcx]
0x18000c3f7  mov     rax, [rax+30h]
0x18000c3fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c400  test    eax, eax
0x18000c402  js      short loc_18000C431
0x18000c404  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000c407  mov     rcx, [rdi]; hHandle
0x18000c40a  call    WaitForSingleObject_0
0x18000c40f  mov     ebx, [rdi+8]
0x18000c412  lea     rcx, [rbp+var_30]
0x18000c416  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000c41b  mov     eax, ebx
0x18000c41d  mov     rbx, [rsp+50h+arg_0]
0x18000c425  add     rsp, 50h
0x18000c429  pop     r14
0x18000c42b  pop     r12
0x18000c42d  pop     rdi
0x18000c42e  pop     rsi
0x18000c42f  pop     rbp
0x18000c430  retn
0x18000c431  lea     rdx, [rbp+var_18]
0x18000c435  mov     ecx, eax
0x18000c437  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000c43d  lea     rcx, [rbp+var_30]; this
0x18000c441  call    ?throw_last_error@winrt@@YAXAEBUslim_source_location@impl@1@@Z; winrt::throw_last_error(winrt::impl::slim_source_location const &)
```
