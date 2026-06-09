# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ToBgra8ImageView(int,int,winrt::Windows::Foundation::IMemoryBufferReference const &)

- ea: `0x1800678c0`
- end: `0x180067a90`
- name: `?ToBgra8ImageView@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AUBgra8ImageView@SemanticRegistry@asg@@HHAEBUIMemoryBufferReference@Foundation@Windows@7@@Z`
- size: `464`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001f550`
- `0x18006e600`
- `0x18006ed60`

## callees

- `0x180003df0`
- `0x180004140`
- `0x18000d230`
- `0x180010dd0`
- `0x1800678c0`
- `0x180067a90`
- `0x1801f97e0`
- `0x180242120`

## string_xrefs

- `0x180067910`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x1800679c8`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\Utilities.cpp`
- `0x180067a23`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\Utilities.cpp`

## pseudocode

```c
__int64 __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ToBgra8ImageView(
        __int64 a1,
        int a2,
        int a3,
        __int64 **a4)
{
  __int64 v4; // rdi
  __int64 *v8; // rcx
  __int64 v9; // r15
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rax
  int v14; // [rsp+20h] [rbp-50h] BYREF
  const char *v15; // [rsp+28h] [rbp-48h]
  __int64 v16; // [rsp+30h] [rbp-40h]
  _BYTE pExceptionObject[24]; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v18[32]; // [rsp+50h] [rbp-20h] BYREF
  unsigned int v19; // [rsp+98h] [rbp+28h] BYREF

  v4 = (unsigned int)a3;
  if ( a2 < 0 || a3 < 0 )
  {
    v14 = 19;
    v15 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\Utilities.cpp";
    v16 = 0;
    winrt::param::hstring::hstring((winrt::param::hstring *)v18, L"Image dimensions can not be negative");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)pExceptionObject,
      (const struct winrt::param::hstring *)v18,
      (const struct winrt::impl::slim_source_location *)&v14);
    throw (winrt::hresult_invalid_argument *)pExceptionObject;
  }
  v8 = *a4;
  v19 = 0;
  v9 = a3 * (__int64)a2;
  v14 = 543;
  v15 = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\winrt\\Windows.Foundation.h";
  v10 = *v8;
  v16 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v10 + 48))(v8, &v19);
  if ( v11 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v11, &v14);
  }
  if ( v19 < (unsigned __int64)(4 * v9) )
  {
    v14 = 27;
    v15 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\Utilities.cpp";
    v16 = 0;
    winrt::param::hstring::hstring((winrt::param::hstring *)v18, L"Image buffer too small");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)pExceptionObject,
      (const struct winrt::param::hstring *)v18,
      (const struct winrt::impl::slim_source_location *)&v14);
    throw (winrt::hresult_invalid_argument *)pExceptionObject;
  }
  v12 = winrt::impl::consume_Windows_Foundation_IMemoryBufferReference<winrt::Windows::Foundation::IMemoryBufferReference>::data(a4);
  *(_DWORD *)a1 = a2;
  *(_DWORD *)(a1 + 4) = v4;
  *(_QWORD *)(a1 + 8) = v12;
  *(_QWORD *)(a1 + 16) = v9;
  if ( (unsigned int)a2 > 0x4000 || (unsigned int)v4 > 0x4000 )
  {
    std::invalid_argument::invalid_argument((std::invalid_argument *)pExceptionObject, "Image dimensions is too large");
    throw (std::invalid_argument *)pExceptionObject;
  }
  if ( v9 != v4 * (unsigned int)a2 )
  {
    std::invalid_argument::invalid_argument((std::invalid_argument *)pExceptionObject, "Invalid pixel data size");
    throw (std::invalid_argument *)pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x1800678c0  mov     [rsp-18h+arg_10], rbx
0x1800678c5  mov     [rsp-18h+arg_18], rsi
0x1800678ca  push    rbp
0x1800678cb  push    rdi
0x1800678cc  push    r12
0x1800678ce  mov     rbp, rsp
0x1800678d1  sub     rsp, 70h
0x1800678d5  mov     edi, r8d
0x1800678d8  mov     r12, r9
0x1800678db  mov     esi, edx
0x1800678dd  mov     rbx, rcx
0x1800678e0  test    edx, edx
0x1800678e2  js      loc_1800679C8
0x1800678e8  test    edi, edi
0x1800678ea  js      loc_1800679C8
0x1800678f0  mov     rcx, [r9]
0x1800678f3  lea     rdx, [rbp+arg_8]
0x1800678f7  mov     [rsp+70h+arg_0], r15
0x1800678ff  movsxd  rax, edi
0x180067902  mov     [rbp+arg_8], 0
0x180067909  movsxd  r15, esi
0x18006790c  imul    r15, rax
0x180067910  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180067917  mov     [rbp+var_50], 21Fh
0x18006791e  mov     [rbp+var_48], rax
0x180067922  mov     rax, [rcx]
0x180067925  mov     [rbp+var_40], 0
0x18006792d  mov     rax, [rax+30h]
0x180067931  call    cs:__guard_dispatch_icall_fptr
0x180067937  test    eax, eax
0x180067939  js      loc_180067A14
0x18006793f  mov     eax, [rbp+arg_8]
0x180067942  lea     rcx, ds:0[r15*4]
0x18006794a  cmp     rax, rcx
0x18006794d  jb      loc_180067A23
0x180067953  mov     rcx, r12
0x180067956  call    ?data@?$consume_Windows_Foundation_IMemoryBufferReference@UIMemoryBufferReference@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IMemoryBufferReference<winrt::Windows::Foundation::IMemoryBufferReference>::data(void)
0x18006795b  mov     [rbx], esi
0x18006795d  mov     [rbx+4], edi
0x180067960  mov     [rbx+8], rax
0x180067964  mov     [rbx+10h], r15
0x180067968  cmp     esi, 4000h
0x18006796e  ja      short loc_1800679A7
0x180067970  cmp     edi, 4000h
0x180067976  ja      short loc_1800679A7
0x180067978  mov     ecx, esi
0x18006797a  imul    rcx, rdi
0x18006797e  cmp     r15, rcx
0x180067981  jnz     loc_180067A6F
0x180067987  mov     r15, [rsp+70h+arg_0]
0x18006798f  lea     r11, [rsp+70h+var_s0]
0x180067994  mov     rsi, [r11+38h]
0x180067998  mov     rax, rbx
0x18006799b  mov     rbx, [r11+30h]
0x18006799f  mov     rsp, r11
0x1800679a2  pop     r12
0x1800679a4  pop     rdi
0x1800679a5  pop     rbp
0x1800679a6  retn
0x1800679a7  lea     rdx, aImageDimension; "Image dimensions is too large"
0x1800679ae  lea     rcx, [rbp+pExceptionObject]; this
0x1800679b2  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x1800679b7  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x1800679be  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800679c2  call    _CxxThrowException
0x1800679c8  lea     rax, aCW1SSrcSemanti_36; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x1800679cf  mov     [rbp+var_50], 13h
0x1800679d6  lea     rdx, aImageDimension_0; "Image dimensions can not be negative"
0x1800679dd  mov     [rbp+var_48], rax
0x1800679e1  lea     rcx, [rbp+var_20]; this
0x1800679e5  mov     [rbp+var_40], 0
0x1800679ed  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x1800679f2  lea     r8, [rbp+var_50]; struct winrt::impl::slim_source_location *
0x1800679f6  lea     rdx, [rbp+var_20]; struct winrt::param::hstring *
0x1800679fa  lea     rcx, [rbp+pExceptionObject]; this
0x1800679fe  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180067a03  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180067a0a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180067a0e  call    _CxxThrowException
0x180067a14  lfence
0x180067a17  lea     rdx, [rbp+var_50]
0x180067a1b  mov     ecx, eax
0x180067a1d  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180067a23  lea     rax, aCW1SSrcSemanti_36; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180067a2a  mov     [rbp+var_50], 1Bh
0x180067a31  lea     rdx, aImageBufferToo; "Image buffer too small"
0x180067a38  mov     [rbp+var_48], rax
0x180067a3c  lea     rcx, [rbp+var_20]; this
0x180067a40  mov     [rbp+var_40], 0
0x180067a48  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180067a4d  lea     r8, [rbp+var_50]; struct winrt::impl::slim_source_location *
0x180067a51  lea     rdx, [rbp+var_20]; struct winrt::param::hstring *
0x180067a55  lea     rcx, [rbp+pExceptionObject]; this
0x180067a59  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180067a5e  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180067a65  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180067a69  call    _CxxThrowException
0x180067a6f  lea     rdx, aInvalidPixelDa; "Invalid pixel data size"
0x180067a76  lea     rcx, [rbp+pExceptionObject]; this
0x180067a7a  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x180067a7f  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x180067a86  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180067a8a  call    _CxxThrowException
```
