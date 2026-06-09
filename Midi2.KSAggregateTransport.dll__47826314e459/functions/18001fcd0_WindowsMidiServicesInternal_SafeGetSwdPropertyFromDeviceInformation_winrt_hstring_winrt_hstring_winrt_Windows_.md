# WindowsMidiServicesInternal::SafeGetSwdPropertyFromDeviceInformation<winrt::hstring>(winrt::hstring,winrt::Windows::Devices::Enumeration::DeviceInformation,winrt::hstring)

- ea: `0x18001fcd0`
- end: `0x18001feba`
- name: `??$SafeGetSwdPropertyFromDeviceInformation@Uhstring@winrt@@@WindowsMidiServicesInternal@@YA?AUhstring@winrt@@U12@UDeviceInformation@Enumeration@Devices@Windows@2@0@Z`
- size: `490`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180025ca0`
- `0x180039ef0`
- `0x18003c890`

## callees

- `0x180005f2c`
- `0x180005fa4`
- `0x180010b94`
- `0x180014ff4`
- `0x1800161e0`
- `0x180017af8`
- `0x180017d30`
- `0x18001fcd0`
- `0x180021974`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001fd7c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001fe31`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001fd7c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001fe31`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
volatile signed __int32 **__fastcall WindowsMidiServicesInternal::SafeGetSwdPropertyFromDeviceInformation<winrt::hstring>(
        volatile signed __int32 **a1,
        volatile signed __int32 **a2,
        __int64 *a3,
        volatile signed __int32 **a4)
{
  volatile signed __int32 *v8; // rax
  volatile signed __int32 *v9; // r15
  volatile signed __int32 *v10; // rsi
  int v11; // ebx
  HANDLE v12; // rax
  char v14; // bl
  __int64 v15; // rax
  char v16; // r15
  volatile signed __int32 *v17; // rax
  int v18; // eax
  HANDLE ProcessHeap; // rax
  __int64 v20; // rax
  bool v21; // zf
  volatile signed __int32 *v22; // rax
  __int64 v23; // [rsp+28h] [rbp-58h] BYREF
  __int64 v24; // [rsp+30h] [rbp-50h] BYREF
  __int64 v25; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v26[4]; // [rsp+40h] [rbp-40h] BYREF
  volatile signed __int32 *v27; // [rsp+60h] [rbp-20h] BYREF

  if ( *a2 )
  {
    v25 = 0;
    v14 = 2;
    if ( (unsigned __int8)winrt::Windows::Foundation::operator==(a3, &v25)
      || (v15 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
                  a3,
                  &v24),
          v14 = 6,
          v26[0] = *a2,
          v16 = 0,
          !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::HasKey(
                              v15,
                              v26)) )
    {
      v16 = 1;
    }
    if ( (v14 & 4) != 0 && v24 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v24);
    if ( v16 )
    {
      v17 = *a4;
      *a4 = 0;
      *a1 = v17;
    }
    else
    {
      v20 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(
              a3,
              &v24);
      v26[0] = *a2;
      winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
        v20,
        &v23,
        v26);
      if ( v24 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v24);
      v25 = 0;
      v21 = (unsigned __int8)winrt::Windows::Foundation::operator==(&v23, &v25) == 0;
      v22 = *a4;
      if ( v21 )
      {
        v27 = *a4;
        winrt::unbox_value_or<winrt::hstring,0>(a1, &v23, &v27);
      }
      else
      {
        *a4 = 0;
        *a1 = v22;
      }
      if ( v23 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
    }
    v9 = *a2;
  }
  else
  {
    v8 = *a4;
    *a4 = 0;
    *a1 = v8;
    v9 = *a2;
  }
  if ( v9 )
  {
    v18 = _InterlockedDecrement(v9 + 6);
    if ( v18 )
    {
      if ( v18 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v9);
    }
    *a2 = 0;
  }
  if ( *a3 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a3);
  v10 = *a4;
  if ( *a4 )
  {
    v11 = _InterlockedDecrement(v10 + 6);
    if ( v11 )
    {
      if ( v11 < 0 )
        abort();
    }
    else
    {
      v12 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v12, 0, (LPVOID)v10);
    }
    *a4 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18001fcd0  mov     rax, rsp
0x18001fcd3  mov     [rax+8], rbx
0x18001fcd7  mov     [rax+20h], r9
0x18001fcdb  mov     [rax+18h], r8
0x18001fcdf  mov     [rax+10h], rdx
0x18001fce3  push    rbp
0x18001fce4  push    rsi
0x18001fce5  push    rdi
0x18001fce6  push    r12
0x18001fce8  push    r13
0x18001fcea  push    r14
0x18001fcec  push    r15
0x18001fcee  mov     rbp, rsp
0x18001fcf1  sub     rsp, 80h
0x18001fcf8  mov     rdi, r9
0x18001fcfb  mov     rsi, r8
0x18001fcfe  mov     r14, rdx
0x18001fd01  mov     r12, rcx
0x18001fd04  xor     r13d, r13d
0x18001fd07  mov     [rbp+var_60], r13d
0x18001fd0b  cmp     [rdx], r13
0x18001fd0e  jnz     short loc_18001FD83
0x18001fd10  mov     rax, [r9]
0x18001fd13  mov     [r9], r13
0x18001fd16  mov     [rcx], rax
0x18001fd19  mov     r15, [rdx]
0x18001fd1c  jmp     loc_18001FDF8
0x18001fd21  mov     [r14], r13
0x18001fd24  cmp     [rsi], r13
0x18001fd27  jz      short loc_18001FD32
0x18001fd29  mov     rcx, rsi
0x18001fd2c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001fd31  nop
0x18001fd32  mov     rsi, [rdi]
0x18001fd35  test    rsi, rsi
0x18001fd38  jz      short loc_18001FD5A
0x18001fd3a  lock xadd [rsi+18h], ebx
0x18001fd3f  sub     ebx, 1
0x18001fd42  jnz     short loc_18001FD78
0x18001fd44  nop
0x18001fd45  call    WINRT_IMPL_GetProcessHeap
0x18001fd4a  mov     rcx, rax; hHeap
0x18001fd4d  xor     edx, edx; dwFlags
0x18001fd4f  mov     r8, rsi; lpMem
0x18001fd52  call    WINRT_IMPL_HeapFree
0x18001fd57  mov     [rdi], r13
0x18001fd5a  mov     rax, r12
0x18001fd5d  mov     rbx, [rsp+80h+arg_0]
0x18001fd65  add     rsp, 80h
0x18001fd6c  pop     r15
0x18001fd6e  pop     r14
0x18001fd70  pop     r13
0x18001fd72  pop     r12
0x18001fd74  pop     rdi
0x18001fd75  pop     rsi
0x18001fd76  pop     rbp
0x18001fd77  retn
0x18001fd78  test    ebx, ebx
0x18001fd7a  jns     short loc_18001FD57
0x18001fd7c  call    cs:__imp_abort
0x18001fd83  mov     [rbp+var_48], r13
0x18001fd87  mov     ebx, 2
0x18001fd8c  mov     [rbp+var_60], ebx
0x18001fd8f  lea     rdx, [rbp+var_48]
0x18001fd93  mov     rcx, rsi
0x18001fd96  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18001fd9b  test    al, al
0x18001fd9d  jnz     short loc_18001FDCE
0x18001fd9f  lea     rdx, [rbp+var_50]
0x18001fda3  mov     rcx, rsi
0x18001fda6  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
0x18001fdab  nop
0x18001fdac  mov     ebx, 6
0x18001fdb1  mov     [rbp+var_60], ebx
0x18001fdb4  mov     rcx, [r14]
0x18001fdb7  mov     [rbp+var_40], rcx
0x18001fdbb  lea     rdx, [rbp+var_40]
0x18001fdbf  mov     rcx, rax
0x18001fdc2  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::HasKey(winrt::param::hstring const &)
0x18001fdc7  test    al, al
0x18001fdc9  mov     r15b, r13b
0x18001fdcc  jnz     short loc_18001FDD1
0x18001fdce  mov     r15b, 1
0x18001fdd1  test    bl, 4
0x18001fdd4  jz      short loc_18001FDE6
0x18001fdd6  cmp     [rbp+var_50], r13
0x18001fdda  jz      short loc_18001FDE6
0x18001fddc  lea     rcx, [rbp+var_50]
0x18001fde0  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001fde5  nop
0x18001fde6  test    r15b, r15b
0x18001fde9  jz      short loc_18001FE38
0x18001fdeb  mov     rax, [rdi]
0x18001fdee  mov     [rdi], r13
0x18001fdf1  mov     [r12], rax
0x18001fdf5  mov     r15, [r14]
0x18001fdf8  or      ebx, 0FFFFFFFFh
0x18001fdfb  test    r15, r15
0x18001fdfe  jz      loc_18001FD24
0x18001fe04  mov     eax, ebx
0x18001fe06  lock xadd [r15+18h], eax
0x18001fe0c  sub     eax, 1
0x18001fe0f  jnz     short loc_18001FE29
0x18001fe11  nop
0x18001fe12  call    WINRT_IMPL_GetProcessHeap
0x18001fe17  mov     rcx, rax; hHeap
0x18001fe1a  xor     edx, edx; dwFlags
0x18001fe1c  mov     r8, r15; lpMem
0x18001fe1f  call    WINRT_IMPL_HeapFree
0x18001fe24  jmp     loc_18001FD21
0x18001fe29  test    eax, eax
0x18001fe2b  jns     loc_18001FD21
0x18001fe31  call    cs:__imp_abort
0x18001fe38  lea     rdx, [rbp+var_50]
0x18001fe3c  mov     rcx, rsi
0x18001fe3f  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Properties(void)
0x18001fe44  nop
0x18001fe45  mov     rcx, [r14]
0x18001fe48  mov     [rbp+var_40], rcx
0x18001fe4c  lea     r8, [rbp+var_40]
0x18001fe50  lea     rdx, [rbp+var_58]
0x18001fe54  mov     rcx, rax
0x18001fe57  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x18001fe5c  nop
0x18001fe5d  cmp     [rbp+var_50], r13
0x18001fe61  jz      short loc_18001FE6C
0x18001fe63  lea     rcx, [rbp+var_50]
0x18001fe67  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001fe6c  mov     [rbp+var_48], r13
0x18001fe70  lea     rdx, [rbp+var_48]
0x18001fe74  lea     rcx, [rbp+var_58]
0x18001fe78  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18001fe7d  test    al, al
0x18001fe7f  mov     rax, [rdi]
0x18001fe82  jnz     short loc_18001FE9A
0x18001fe84  mov     [rbp+var_20], rax
0x18001fe88  lea     r8, [rbp+var_20]
0x18001fe8c  lea     rdx, [rbp+var_58]
0x18001fe90  mov     rcx, r12
0x18001fe93  call    ??$unbox_value_or@Uhstring@winrt@@$0A@@winrt@@YA?AUhstring@0@AEBUIInspectable@Foundation@Windows@0@AEBU1param@0@@Z; winrt::unbox_value_or<winrt::hstring,0>(winrt::Windows::Foundation::IInspectable const &,winrt::param::hstring const &)
0x18001fe98  jmp     short loc_18001FEA1
0x18001fe9a  mov     [rdi], r13
0x18001fe9d  mov     [r12], rax
0x18001fea1  cmp     [rbp+var_58], r13
0x18001fea5  jz      loc_18001FDF5
0x18001feab  lea     rcx, [rbp+var_58]
0x18001feaf  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001feb4  jmp     loc_18001FDF5
```
