# winrt::impl::create_and_initialize<winrt::Microsoft::Windows::Workloads::implementation::Workload,winrt::Microsoft::Windows::Workloads::WorkloadManager &,winrt::hstring &,winrt::Microsoft::Windows::Management::Deployment::PackageSet &,winrt::hstring &>(winrt::Microsoft::Windows::Workloads::WorkloadManager &,winrt::hstring &,winrt::Microsoft::Windows::Management::Deployment::PackageSet &,winrt::hstring &)

- ea: `0x180024840`
- end: `0x1800249f3`
- name: `??$create_and_initialize@UWorkload@implementation@Workloads@Windows@Microsoft@winrt@@AEAUWorkloadManager@3456@AEAUhstring@6@AEAUPackageSet@Deployment@Management@456@AEAU86@@impl@winrt@@YAPEAUWorkload@implementation@Workloads@Windows@Microsoft@1@AEAUWorkloadManager@4561@AEAUhstring@1@AEAUPackageSet@Deployment@Management@561@1@Z`
- size: `435`
- prototype: `_QWORD *__fastcall(LPVOID **, winrt::impl **, __int64 *, winrt::impl **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001eb00`

## callees

- `0x1800040a0`
- `0x1800157c0`
- `0x180015860`
- `0x180024840`
- `0x180030ae5`
- `0x180030aeb`
- `0x180035060`
- `0x18003bed0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800249e1`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800249ec`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800249e1`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800249ec`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::create_and_initialize<winrt::Microsoft::Windows::Workloads::implementation::Workload,winrt::Microsoft::Windows::Workloads::WorkloadManager &,winrt::hstring &,winrt::Microsoft::Windows::Management::Deployment::PackageSet &,winrt::hstring &>(
        LPVOID **a1,
        winrt::impl **a2,
        __int64 *a3,
        winrt::impl **a4)
{
  _QWORD *v8; // rsi
  struct winrt::impl::hstring_header *v9; // rdx
  struct winrt::impl::hstring_header *v10; // rdx
  __int64 v11; // rcx
  struct winrt::impl::hstring_header *v12; // rdx
  LPVOID *v13; // rcx
  LPVOID v14; // rax
  __int64 v15; // rax
  void *v16; // rbx
  int v17; // eax
  HANDLE ProcessHeap; // rax
  void *v19; // rbx
  int v20; // edi
  HANDLE v21; // rax
  LPVOID *v23; // [rsp+30h] [rbp-39h] BYREF
  LPVOID *v24; // [rsp+38h] [rbp-31h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-29h] BYREF
  __int64 v26; // [rsp+48h] [rbp-21h] BYREF
  LPVOID v27; // [rsp+50h] [rbp-19h] BYREF
  __int64 v28; // [rsp+58h] [rbp-11h] BYREF
  struct winrt::impl::hstring_header *v29; // [rsp+60h] [rbp-9h] BYREF
  _QWORD v30[11]; // [rsp+68h] [rbp-1h] BYREF

  v8 = operator new(0x38u);
  v30[1] = v8;
  v23 = &v27;
  v27 = winrt::impl::duplicate_hstring(*a4, v9);
  v30[2] = &v27;
  v29 = (struct winrt::impl::hstring_header *)&v26;
  v11 = *a3;
  v26 = v11;
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  v30[3] = &v26;
  v12 = winrt::impl::duplicate_hstring(*a2, v10);
  lpMem = v12;
  v30[4] = &lpMem;
  v13 = *a1;
  v24 = v13;
  if ( v13 )
  {
    (*((void (__fastcall **)(LPVOID *, struct winrt::impl::hstring_header *))*v13 + 1))(v13, v12);
    v12 = (struct winrt::impl::hstring_header *)lpMem;
    v13 = v24;
  }
  v30[5] = &v24;
  v14 = v27;
  v27 = 0;
  v30[0] = v14;
  v15 = v26;
  v26 = 0;
  v28 = v15;
  lpMem = 0;
  v29 = v12;
  v24 = 0;
  v23 = v13;
  winrt::Microsoft::Windows::Workloads::implementation::Workload::Workload(v8, &v23, &v29, &v28, v30);
  *v8 = &winrt::Microsoft::Windows::Workloads::implementation::Workload::`vftable';
  if ( v24 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v24);
  v16 = lpMem;
  if ( lpMem )
  {
    v17 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v17 )
    {
      if ( v17 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v16);
    }
    lpMem = 0;
  }
  if ( v26 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v26);
  v19 = v27;
  if ( v27 )
  {
    v20 = _InterlockedDecrement((volatile signed __int32 *)v27 + 6);
    if ( v20 )
    {
      if ( v20 < 0 )
        abort();
    }
    else
    {
      v21 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v21, 0, v19);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180024840  mov     [rsp-8+arg_0], rbx
0x180024845  push    rbp
0x180024846  push    rsi
0x180024847  push    rdi
0x180024848  push    r14
0x18002484a  push    r15
0x18002484c  lea     rbp, [rsp-37h]
0x180024851  sub     rsp, 0A0h
0x180024858  mov     rbx, r9
0x18002485b  mov     rdi, r8
0x18002485e  mov     r15, rdx
0x180024861  mov     r14, rcx
0x180024864  mov     ecx, 38h ; '8'; Size
0x180024869  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002486e  mov     rsi, rax
0x180024871  mov     [rbp+57h+var_50], rax
0x180024875  lea     rax, [rbp+57h+var_70]
0x180024879  mov     [rbp+57h+var_90], rax
0x18002487d  mov     rcx, [rbx]; this
0x180024880  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180024885  mov     [rbp+57h+var_70], rax
0x180024889  lea     rax, [rbp+57h+var_70]
0x18002488d  mov     [rbp+57h+var_48], rax
0x180024891  lea     rax, [rbp+57h+var_78]
0x180024895  mov     [rbp+57h+var_60], rax
0x180024899  mov     rcx, [rdi]
0x18002489c  mov     [rbp+57h+var_78], rcx
0x1800248a0  test    rcx, rcx
0x1800248a3  jz      short loc_1800248B2
0x1800248a5  mov     rax, [rcx]
0x1800248a8  mov     rax, [rax+8]
0x1800248ac  call    cs:__guard_dispatch_icall_fptr
0x1800248b2  lea     rax, [rbp+57h+var_78]
0x1800248b6  mov     [rbp+57h+var_40], rax
0x1800248ba  mov     rcx, [r15]; this
0x1800248bd  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x1800248c2  mov     rdx, rax
0x1800248c5  mov     [rbp+57h+lpMem], rax
0x1800248c9  lea     rax, [rbp+57h+lpMem]
0x1800248cd  mov     [rbp+57h+var_38], rax
0x1800248d1  mov     rcx, [r14]
0x1800248d4  mov     [rbp+57h+var_88], rcx
0x1800248d8  test    rcx, rcx
0x1800248db  jz      short loc_1800248F2
0x1800248dd  mov     rax, [rcx]
0x1800248e0  mov     rax, [rax+8]
0x1800248e4  call    cs:__guard_dispatch_icall_fptr
0x1800248ea  mov     rdx, [rbp+57h+lpMem]
0x1800248ee  mov     rcx, [rbp+57h+var_88]
0x1800248f2  lea     rax, [rbp+57h+var_88]
0x1800248f6  mov     [rbp+57h+var_30], rax
0x1800248fa  mov     rax, [rbp+57h+var_70]
0x1800248fe  xor     r14d, r14d
0x180024901  mov     [rbp+57h+var_70], r14
0x180024905  mov     [rbp+57h+var_58], rax
0x180024909  mov     rax, [rbp+57h+var_78]
0x18002490d  mov     [rbp+57h+var_78], r14
0x180024911  mov     [rbp+57h+var_68], rax
0x180024915  mov     [rbp+57h+lpMem], r14
0x180024919  mov     [rbp+57h+var_60], rdx
0x18002491d  mov     [rbp+57h+var_88], r14
0x180024921  mov     [rbp+57h+var_90], rcx
0x180024925  lea     rax, [rbp+57h+var_58]
0x180024929  mov     [rsp+0C0h+var_A0], rax
0x18002492e  lea     r9, [rbp+57h+var_68]
0x180024932  lea     r8, [rbp+57h+var_60]
0x180024936  lea     rdx, [rbp+57h+var_90]
0x18002493a  mov     rcx, rsi
0x18002493d  call    ??0Workload@implementation@Workloads@Windows@Microsoft@winrt@@QEAA@UWorkloadManager@2345@Uhstring@5@UPackageSet@Deployment@Management@345@1@Z; winrt::Microsoft::Windows::Workloads::implementation::Workload::Workload(winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::hstring,winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::hstring)
0x180024942  lea     rax, ??_7Workload@implementation@Workloads@Windows@Microsoft@winrt@@6B@; const winrt::Microsoft::Windows::Workloads::implementation::Workload::`vftable'
0x180024949  mov     [rsi], rax
0x18002494c  cmp     [rbp+57h+var_88], r14
0x180024950  jz      short loc_18002495C
0x180024952  lea     rcx, [rbp+57h+var_88]
0x180024956  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002495b  nop
0x18002495c  mov     edi, 0FFFFFFFFh
0x180024961  mov     rbx, [rbp+57h+lpMem]
0x180024965  test    rbx, rbx
0x180024968  jz      short loc_18002498C
0x18002496a  mov     eax, edi
0x18002496c  lock xadd [rbx+18h], eax
0x180024971  sub     eax, 1
0x180024974  jnz     short loc_1800249DD
0x180024976  call    WINRT_IMPL_GetProcessHeap
0x18002497b  mov     rcx, rax; hHeap
0x18002497e  mov     r8, rbx; lpMem
0x180024981  xor     edx, edx; dwFlags
0x180024983  call    WINRT_IMPL_HeapFree
0x180024988  mov     [rbp+57h+lpMem], r14
0x18002498c  cmp     [rbp+57h+var_78], 0
0x180024991  jz      short loc_18002499D
0x180024993  lea     rcx, [rbp+57h+var_78]
0x180024997  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002499c  nop
0x18002499d  mov     rbx, [rbp+57h+var_70]
0x1800249a1  test    rbx, rbx
0x1800249a4  jz      short loc_1800249C3
0x1800249a6  lock xadd [rbx+18h], edi
0x1800249ab  sub     edi, 1
0x1800249ae  jnz     short loc_1800249E8
0x1800249b0  call    WINRT_IMPL_GetProcessHeap
0x1800249b5  mov     rcx, rax; hHeap
0x1800249b8  mov     r8, rbx; lpMem
0x1800249bb  xor     edx, edx; dwFlags
0x1800249bd  call    WINRT_IMPL_HeapFree
0x1800249c2  nop
0x1800249c3  mov     rax, rsi
0x1800249c6  mov     rbx, [rsp+0C0h+arg_0]
0x1800249ce  add     rsp, 0A0h
0x1800249d5  pop     r15
0x1800249d7  pop     r14
0x1800249d9  pop     rdi
0x1800249da  pop     rsi
0x1800249db  pop     rbp
0x1800249dc  retn
0x1800249dd  test    eax, eax
0x1800249df  jns     short loc_180024988
0x1800249e1  call    cs:__imp_abort
0x1800249e8  test    edi, edi
0x1800249ea  jns     short loc_1800249C3
0x1800249ec  call    cs:__imp_abort
```
