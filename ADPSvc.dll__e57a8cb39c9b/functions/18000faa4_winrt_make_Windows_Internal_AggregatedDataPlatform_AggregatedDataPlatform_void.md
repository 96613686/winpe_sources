# winrt_make_Windows_Internal_AggregatedDataPlatform_AggregatedDataPlatform(void)

- ea: `0x18000faa4`
- end: `0x18000fb47`
- name: `?winrt_make_Windows_Internal_AggregatedDataPlatform_AggregatedDataPlatform@@YAPEAXXZ`
- size: `163`
- prototype: `char *(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x1800080e0`

## callees

- `0x1800033bc`
- `0x18000c1f0`
- `0x18000e284`
- `0x18000f1b8`
- `0x18000faa4`

## string_xrefs

- `0x18000fb32`: `onecoreuap\base\appmodel\aggregateddataplatform\service\servicehelper\lib\aggregateddataplatform.cpp`

## pseudocode

```c
char *winrt_make_Windows_Internal_AggregatedDataPlatform_AggregatedDataPlatform(void)
{
  _OWORD *v0; // rdi
  int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v0 = operator new(0x20u);
  *v0 = 0;
  v0[1] = 0;
  *((_QWORD *)v0 + 2) = &winrt::impl::produce<winrt::Windows::Internal::AggregatedDataPlatform::factory_implementation::AggregatedDataPlatform,winrt::Windows::Foundation::IActivationFactory>::`vftable';
  *((_QWORD *)v0 + 3) = &winrt::impl::produce<winrt::Windows::Internal::AggregatedDataPlatform::factory_implementation::AggregatedDataPlatform,winrt::Windows::Internal::AggregatedDataPlatform::IAggregatedDataPlatformStatics>::`vftable';
  winrt::impl::module_lock_updater<1>::module_lock_updater<1>((char *)v0 + 8);
  *((_QWORD *)v0 + 1) = 1;
  *(_QWORD *)v0 = &winrt::Windows::Internal::AggregatedDataPlatform::factory_implementation::AggregatedDataPlatform::`vftable';
  if ( !IsClientAllowed() )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\servicehelper\\lib\\aggregateddataplatform.cpp",
      (const char *)0x80070005LL,
      v2);
  *(_QWORD *)v0 = &winrt::Windows::Internal::AggregatedDataPlatform::factory_implementation::AggregatedDataPlatform::`vftable';
  return (char *)(v0 + 1);
}

```

## disassembly

```asm
0x18000faa4  mov     [rsp+arg_8], rbx
0x18000faa9  mov     [rsp+arg_10], rsi
0x18000faae  push    rdi; int
0x18000faaf  sub     rsp, 20h
0x18000fab3  mov     ecx, 20h ; ' '; Size
0x18000fab8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fabd  mov     rdi, rax
0x18000fac0  mov     [rsp+28h+arg_0], rax
0x18000fac5  xorps   xmm0, xmm0
0x18000fac8  movups  xmmword ptr [rax], xmm0
0x18000facb  movups  xmmword ptr [rax+10h], xmm0
0x18000facf  lea     rax, ??_7?$produce@UAggregatedDataPlatform@factory_implementation@1Internal@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Internal::AggregatedDataPlatform::factory_implementation::AggregatedDataPlatform,winrt::Windows::Foundation::IActivationFactory>::`vftable'
0x18000fad6  mov     [rdi+10h], rax
0x18000fada  lea     rax, ??_7?$produce@UAggregatedDataPlatform@factory_implementation@1Internal@Windows@winrt@@UIAggregatedDataPlatformStatics@1345@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Internal::AggregatedDataPlatform::factory_implementation::AggregatedDataPlatform,winrt::Windows::Internal::AggregatedDataPlatform::IAggregatedDataPlatformStatics>::`vftable'
0x18000fae1  mov     [rdi+18h], rax
0x18000fae5  lea     rcx, [rdi+8]
0x18000fae9  call    ??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ; winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)
0x18000faee  mov     qword ptr [rdi+8], 1
0x18000faf6  lea     rax, ??_7AggregatedDataPlatform@factory_implementation@0Internal@Windows@winrt@@6B@; const winrt::Windows::Internal::AggregatedDataPlatform::factory_implementation::AggregatedDataPlatform::`vftable'
0x18000fafd  mov     [rdi], rax
0x18000fb00  mov     rbx, [rsp+28h]
0x18000fb05  call    ?IsClientAllowed@@YA_NXZ; IsClientAllowed(void)
0x18000fb0a  test    al, al
0x18000fb0c  jz      short loc_18000FB2C
0x18000fb0e  lea     rax, ??_7AggregatedDataPlatform@factory_implementation@0Internal@Windows@winrt@@6B@; const winrt::Windows::Internal::AggregatedDataPlatform::factory_implementation::AggregatedDataPlatform::`vftable'
0x18000fb15  mov     [rdi], rax
0x18000fb18  lea     rax, [rdi+10h]
0x18000fb1c  mov     rbx, [rsp+28h+arg_8]
0x18000fb21  mov     rsi, [rsp+28h+arg_10]
0x18000fb26  add     rsp, 20h
0x18000fb2a  pop     rdi
0x18000fb2b  retn
0x18000fb2c  mov     r9d, 80070005h; char *
0x18000fb32  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x18000fb39  mov     edx, 6Dh ; 'm'; void *
0x18000fb3e  mov     rcx, rbx; this
0x18000fb41  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
