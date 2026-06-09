# wil::details::svchost_module<winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::populate_winrt_runtime_classes_helper<2>(std::array<winrt::hstring,5> &,std::array<HSTRING__ *,5> &,std::array<long (*)(HSTRING__ *,IActivationFactory * *),5> &)

- ea: `0x18000e180`
- end: `0x18000e39e`
- name: `??$populate_winrt_runtime_classes_helper@$01@?$svchost_module@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@23456@UUQIMaintenanceTaskRun@Private@23456@UTestAPI@923456@UTestConfigurationRegistration@923456@@details@wil@@AEAAXAEAV?$array@Uhstring@winrt@@$04@std@@AEAV?$array@PEAUHSTRING__@@$04@4@AEAV?$array@P6AJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z$04@4@@Z`
- size: `542`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180010b24`

## callees

- `0x1800040a0`
- `0x180004140`
- `0x18000c6b4`
- `0x18000cc44`
- `0x18000e180`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000e397`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000e397`

## string_xrefs

- `0x18000e1a7`: `Windows.Internal.Data.UsageAndQualityInsights.Private.UQIMaintenanceTaskRun`
- `0x18000e2fc`: `Windows.Internal.Data.UsageAndQualityInsights.Private.TestConfigurationRegistration`

## pseudocode

```c
__int64 (*__fastcall wil::details::svchost_module<winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::populate_winrt_runtime_classes_helper<2>(
        __int64 a1,
        volatile signed __int32 **a2,
        _QWORD *a3,
        _QWORD *a4))()
{
  volatile signed __int32 *v7; // rdi
  unsigned int v8; // edx
  volatile signed __int32 **v9; // r14
  volatile signed __int32 *v10; // rsi
  int v11; // eax
  HANDLE v12; // rax
  int v13; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v15; // rdi
  unsigned int v16; // edx
  volatile signed __int32 **v17; // r14
  volatile signed __int32 *v18; // rsi
  int v19; // eax
  HANDLE v20; // rax
  int v21; // eax
  HANDLE v22; // rax
  volatile signed __int32 *v23; // rdi
  volatile signed __int32 **v24; // r14
  volatile signed __int32 *v25; // rsi
  int v26; // ebx
  HANDLE v27; // rax
  __int64 (*result)(); // rax
  int v29; // ebx
  HANDLE v30; // rax
  char v31; // [rsp+20h] [rbp-58h] BYREF
  char v32; // [rsp+28h] [rbp-50h] BYREF
  char v33; // [rsp+30h] [rbp-48h] BYREF

  v7 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x4B, (unsigned int)a2);
  memcpy_s(
    (void *const)(v7 + 7),
    0x96u,
    L"Windows.Internal.Data.UsageAndQualityInsights.Private.UQIMaintenanceTaskRun",
    0x96u);
  v9 = a2 + 2;
  if ( a2 + 2 == (volatile signed __int32 **)&v31 )
  {
    if ( v7 )
    {
      v13 = _InterlockedDecrement(v7 + 6);
      if ( v13 )
      {
        if ( v13 < 0 )
          goto LABEL_32;
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v7);
      }
    }
  }
  else
  {
    v10 = *v9;
    if ( *v9 )
    {
      v11 = _InterlockedDecrement(v10 + 6);
      if ( v11 )
      {
        if ( v11 < 0 )
          goto LABEL_32;
      }
      else
      {
        v12 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v12, 0, (LPVOID)v10);
      }
    }
    *v9 = v7;
  }
  a3[2] = *v9;
  a4[2] = DllGetActivationFactory;
  v15 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x3D, v8);
  memcpy_s((void *const)(v15 + 7), 0x7Au, L"Windows.Internal.Data.UsageAndQualityInsights.Private.TestAPI", 0x7Au);
  v17 = a2 + 3;
  if ( a2 + 3 == (volatile signed __int32 **)&v32 )
  {
    if ( v15 )
    {
      v21 = _InterlockedDecrement(v15 + 6);
      if ( v21 )
      {
        if ( v21 < 0 )
          goto LABEL_32;
      }
      else
      {
        v22 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v22, 0, (LPVOID)v15);
      }
    }
  }
  else
  {
    v18 = *v17;
    if ( *v17 )
    {
      v19 = _InterlockedDecrement(v18 + 6);
      if ( v19 )
      {
        if ( v19 < 0 )
          goto LABEL_32;
      }
      else
      {
        v20 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v20, 0, (LPVOID)v18);
      }
    }
    *v17 = v15;
  }
  a3[3] = *v17;
  a4[3] = DllGetActivationFactory;
  v23 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x53, v16);
  memcpy_s(
    (void *const)(v23 + 7),
    0xA6u,
    L"Windows.Internal.Data.UsageAndQualityInsights.Private.TestConfigurationRegistration",
    0xA6u);
  v24 = a2 + 4;
  if ( a2 + 4 == (volatile signed __int32 **)&v33 )
  {
    if ( !v23 )
      goto LABEL_27;
    v29 = _InterlockedDecrement(v23 + 6);
    if ( !v29 )
    {
      v30 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v30, 0, (LPVOID)v23);
      goto LABEL_27;
    }
    if ( v29 >= 0 )
      goto LABEL_27;
    goto LABEL_32;
  }
  v25 = *v24;
  if ( *v24 )
  {
    v26 = _InterlockedDecrement(v25 + 6);
    if ( !v26 )
    {
      v27 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v27, 0, (LPVOID)v25);
      goto LABEL_26;
    }
    if ( v26 >= 0 )
      goto LABEL_26;
LABEL_32:
    abort();
  }
LABEL_26:
  *v24 = v23;
LABEL_27:
  a3[4] = *v24;
  result = DllGetActivationFactory;
  a4[4] = DllGetActivationFactory;
  return result;
}

```

## disassembly

```asm
0x18000e180  push    rbx
0x18000e182  push    rbp
0x18000e183  push    rsi
0x18000e184  push    rdi
0x18000e185  push    r13
0x18000e187  push    r14
0x18000e189  push    r15
0x18000e18b  sub     rsp, 40h
0x18000e18f  mov     ecx, 4Bh ; 'K'; this
0x18000e194  mov     rbp, r9
0x18000e197  mov     r15, r8
0x18000e19a  mov     r13, rdx
0x18000e19d  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18000e1a2  mov     edx, 96h; DestinationSize
0x18000e1a7  lea     r8, aWindowsInterna_0; "Windows.Internal.Data.UsageAndQualityIn"...
0x18000e1ae  mov     r9d, edx; SourceSize
0x18000e1b1  mov     rdi, rax
0x18000e1b4  lea     rcx, [rax+1Ch]; Destination
0x18000e1b8  call    memcpy_s
0x18000e1bd  lea     rax, [rsp+78h+var_58]
0x18000e1c2  or      ebx, 0FFFFFFFFh
0x18000e1c5  lea     r14, [r13+10h]
0x18000e1c9  cmp     r14, rax
0x18000e1cc  jz      short loc_18000E204
0x18000e1ce  mov     rsi, [r14]
0x18000e1d1  test    rsi, rsi
0x18000e1d4  jz      short loc_18000E1FF
0x18000e1d6  mov     eax, ebx
0x18000e1d8  lock xadd [rsi+18h], eax
0x18000e1dd  sub     eax, 1
0x18000e1e0  jnz     short loc_18000E1F7
0x18000e1e2  nop
0x18000e1e3  call    WINRT_IMPL_GetProcessHeap
0x18000e1e8  mov     rcx, rax; hHeap
0x18000e1eb  mov     r8, rsi; lpMem
0x18000e1ee  xor     edx, edx; dwFlags
0x18000e1f0  call    WINRT_IMPL_HeapFree
0x18000e1f5  jmp     short loc_18000E1FF
0x18000e1f7  test    eax, eax
0x18000e1f9  js      loc_18000E397
0x18000e1ff  mov     [r14], rdi
0x18000e202  jmp     short loc_18000E232
0x18000e204  test    rdi, rdi
0x18000e207  jz      short loc_18000E232
0x18000e209  mov     eax, ebx
0x18000e20b  lock xadd [rdi+18h], eax
0x18000e210  sub     eax, 1
0x18000e213  jnz     short loc_18000E22A
0x18000e215  nop
0x18000e216  call    WINRT_IMPL_GetProcessHeap
0x18000e21b  mov     rcx, rax; hHeap
0x18000e21e  mov     r8, rdi; lpMem
0x18000e221  xor     edx, edx; dwFlags
0x18000e223  call    WINRT_IMPL_HeapFree
0x18000e228  jmp     short loc_18000E232
0x18000e22a  test    eax, eax
0x18000e22c  js      loc_18000E397
0x18000e232  mov     rax, [r14]
0x18000e235  mov     ecx, 3Dh ; '='; this
0x18000e23a  mov     [r15+10h], rax
0x18000e23e  lea     rax, DllGetActivationFactory
0x18000e245  mov     [rbp+10h], rax
0x18000e249  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18000e24e  mov     edx, 7Ah ; 'z'; DestinationSize
0x18000e253  lea     r8, aWindowsInterna_2; "Windows.Internal.Data.UsageAndQualityIn"...
0x18000e25a  mov     r9d, edx; SourceSize
0x18000e25d  mov     rdi, rax
0x18000e260  lea     rcx, [rax+1Ch]; Destination
0x18000e264  call    memcpy_s
0x18000e269  lea     rax, [rsp+78h+var_50]
0x18000e26e  lea     r14, [r13+18h]
0x18000e272  cmp     r14, rax
0x18000e275  jz      short loc_18000E2AD
0x18000e277  mov     rsi, [r14]
0x18000e27a  test    rsi, rsi
0x18000e27d  jz      short loc_18000E2A8
0x18000e27f  mov     eax, ebx
0x18000e281  lock xadd [rsi+18h], eax
0x18000e286  sub     eax, 1
0x18000e289  jnz     short loc_18000E2A0
0x18000e28b  nop
0x18000e28c  call    WINRT_IMPL_GetProcessHeap
0x18000e291  mov     rcx, rax; hHeap
0x18000e294  mov     r8, rsi; lpMem
0x18000e297  xor     edx, edx; dwFlags
0x18000e299  call    WINRT_IMPL_HeapFree
0x18000e29e  jmp     short loc_18000E2A8
0x18000e2a0  test    eax, eax
0x18000e2a2  js      loc_18000E397
0x18000e2a8  mov     [r14], rdi
0x18000e2ab  jmp     short loc_18000E2DB
0x18000e2ad  test    rdi, rdi
0x18000e2b0  jz      short loc_18000E2DB
0x18000e2b2  mov     eax, ebx
0x18000e2b4  lock xadd [rdi+18h], eax
0x18000e2b9  sub     eax, 1
0x18000e2bc  jnz     short loc_18000E2D3
0x18000e2be  nop
0x18000e2bf  call    WINRT_IMPL_GetProcessHeap
0x18000e2c4  mov     rcx, rax; hHeap
0x18000e2c7  mov     r8, rdi; lpMem
0x18000e2ca  xor     edx, edx; dwFlags
0x18000e2cc  call    WINRT_IMPL_HeapFree
0x18000e2d1  jmp     short loc_18000E2DB
0x18000e2d3  test    eax, eax
0x18000e2d5  js      loc_18000E397
0x18000e2db  mov     rax, [r14]
0x18000e2de  mov     ecx, 53h ; 'S'; this
0x18000e2e3  mov     [r15+18h], rax
0x18000e2e7  lea     rax, DllGetActivationFactory
0x18000e2ee  mov     [rbp+18h], rax
0x18000e2f2  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18000e2f7  mov     edx, 0A6h; DestinationSize
0x18000e2fc  lea     r8, aWindowsInterna_4; "Windows.Internal.Data.UsageAndQualityIn"...
0x18000e303  mov     r9d, edx; SourceSize
0x18000e306  mov     rdi, rax
0x18000e309  lea     rcx, [rax+1Ch]; Destination
0x18000e30d  call    memcpy_s
0x18000e312  lea     rax, [rsp+78h+var_48]
0x18000e317  lea     r14, [r13+20h]
0x18000e31b  cmp     r14, rax
0x18000e31e  jz      short loc_18000E36F
0x18000e320  mov     rsi, [r14]
0x18000e323  test    rsi, rsi
0x18000e326  jz      short loc_18000E34B
0x18000e328  lock xadd [rsi+18h], ebx
0x18000e32d  sub     ebx, 1
0x18000e330  jnz     short loc_18000E347
0x18000e332  nop
0x18000e333  call    WINRT_IMPL_GetProcessHeap
0x18000e338  mov     rcx, rax; hHeap
0x18000e33b  mov     r8, rsi; lpMem
0x18000e33e  xor     edx, edx; dwFlags
0x18000e340  call    WINRT_IMPL_HeapFree
0x18000e345  jmp     short loc_18000E34B
0x18000e347  test    ebx, ebx
0x18000e349  js      short loc_18000E397
0x18000e34b  mov     [r14], rdi
0x18000e34e  mov     rax, [r14]
0x18000e351  mov     [r15+20h], rax
0x18000e355  lea     rax, DllGetActivationFactory
0x18000e35c  mov     [rbp+20h], rax
0x18000e360  add     rsp, 40h
0x18000e364  pop     r15
0x18000e366  pop     r14
0x18000e368  pop     r13
0x18000e36a  pop     rdi
0x18000e36b  pop     rsi
0x18000e36c  pop     rbp
0x18000e36d  pop     rbx
0x18000e36e  retn
0x18000e36f  test    rdi, rdi
0x18000e372  jz      short loc_18000E34E
0x18000e374  lock xadd [rdi+18h], ebx
0x18000e379  sub     ebx, 1
0x18000e37c  jnz     short loc_18000E393
0x18000e37e  nop
0x18000e37f  call    WINRT_IMPL_GetProcessHeap
0x18000e384  mov     rcx, rax; hHeap
0x18000e387  mov     r8, rdi; lpMem
0x18000e38a  xor     edx, edx; dwFlags
0x18000e38c  call    WINRT_IMPL_HeapFree
0x18000e391  jmp     short loc_18000E34E
0x18000e393  test    ebx, ebx
0x18000e395  jns     short loc_18000E34E
0x18000e397  call    cs:__imp_abort
```
