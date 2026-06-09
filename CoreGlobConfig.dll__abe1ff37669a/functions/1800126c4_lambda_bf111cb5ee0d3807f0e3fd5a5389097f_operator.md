# _lambda_bf111cb5ee0d3807f0e3fd5a5389097f_::operator()

- ea: `0x1800126c4`
- end: `0x180012794`
- name: `_lambda_bf111cb5ee0d3807f0e3fd5a5389097f_::operator()`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x18001cf90`

## callees

- `0x180002380`
- `0x18000e794`
- `0x1800105ac`
- `0x180011044`
- `0x180011ffc`
- `0x1800126c4`
- `0x18001b4e4`
- `0x18001b6e0`
- `0x18001d3ac`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180012776`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180012776`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800126e2`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800126e2`

## string_xrefs

- `0x1800126f7`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 lambda_bf111cb5ee0d3807f0e3fd5a5389097f_::operator()()
{
  int v0; // eax
  int v1; // eax
  __int64 v2; // r8
  __int64 v3; // rcx
  int v5; // [rsp+20h] [rbp-E8h]
  _BYTE v6[40]; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v7[128]; // [rsp+70h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v0 = RoInitialize(1);
  if ( v0 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4F7,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)(unsigned int)v0,
      v5);
  wil::cloud_store::cloud_store(v6);
  wil::cloud_store::load<Windows::Data::Globalization::Culture::CultureSettings>(v6, v7, 2);
  v1 = UpdateAndSaveCultureSettings((__int64)v6, (__int64)v7);
  if ( v1 < 0 )
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x4FF, v2, (const char *)(unsigned int)v1);
  wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>::~cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>((wil::cloud_store::validated_data_reference *)v7);
  wil::cloud_store::~cloud_store((wil::cloud_store *)v6);
  return RoUninitialize(v3);
}

```

## disassembly

```asm
0x1800126c4  sub     rsp, 108h
0x1800126cb  mov     rax, cs:__security_cookie
0x1800126d2  xor     rax, rsp
0x1800126d5  mov     [rsp+108h+var_18], rax
0x1800126dd  mov     ecx, 1
0x1800126e2  call    cs:__imp_RoInitialize
0x1800126e8  mov     rcx, [rsp+108h]; this
0x1800126f0  test    eax, eax
0x1800126f2  jns     short loc_180012709
0x1800126f4  mov     r9d, eax; char *
0x1800126f7  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x1800126fe  mov     edx, 4F7h; void *
0x180012703  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012709  mov     [rsp+108h+var_C8], 1
0x18001270e  mov     [rsp+108h+var_E8], 0; int
0x180012716  lea     rcx, [rsp+108h+var_C0]
0x18001271b  call    ??0cloud_store@wil@@QEAA@W4PartitionKind@Cloud@Storage@Internal@Windows@@PEBG1W4CloudStoreOptions@3456@II@Z; wil::cloud_store::cloud_store(Windows::Internal::Storage::Cloud::PartitionKind,ushort const *,ushort const *,Windows::Internal::Storage::Cloud::CloudStoreOptions,uint,uint)
0x180012720  nop
0x180012721  mov     r8d, 2
0x180012727  lea     rdx, [rsp+108h+var_98]
0x18001272c  lea     rcx, [rsp+108h+var_C0]
0x180012731  call    ??$load@UCultureSettings@Culture@Globalization@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@1@W4cloud_store_load_options@1@PEBD@Z; wil::cloud_store::load<Windows::Data::Globalization::Culture::CultureSettings>(wil::cloud_store_load_options,char const *)
0x180012736  nop
0x180012737  lea     rdx, [rsp+108h+var_98]
0x18001273c  lea     rcx, [rsp+108h+var_C0]
0x180012741  call    ?UpdateAndSaveCultureSettings@@YAJAEAVcloud_store@wil@@AEAV?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@2@@Z; UpdateAndSaveCultureSettings(wil::cloud_store &,wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings> &)
0x180012746  mov     rcx, [rsp+108h]; this
0x18001274e  test    eax, eax
0x180012750  jns     short loc_180012760
0x180012752  mov     r9d, eax; char *
0x180012755  mov     edx, 4FFh; void *
0x18001275a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001275f  nop
0x180012760  lea     rcx, [rsp+108h+var_98]; this
0x180012765  call    ??1?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@QEAA@XZ; wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>::~cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>(void)
0x18001276a  nop
0x18001276b  lea     rcx, [rsp+108h+var_C0]; this
0x180012770  call    ??1cloud_store@wil@@QEAA@XZ; wil::cloud_store::~cloud_store(void)
0x180012775  nop
0x180012776  call    cs:__imp_RoUninitialize
0x18001277c  mov     rcx, [rsp+108h+var_18]
0x180012784  xor     rcx, rsp; StackCookie
0x180012787  call    __security_check_cookie
0x18001278c  add     rsp, 108h
0x180012793  retn
```
