# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::Embedding::CopyTo(winrt::Windows::Foundation::IMemoryBuffer const &)

- ea: `0x180068bc0`
- end: `0x180068ed4`
- name: `?CopyTo@Embedding@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEBAIAEBUIMemoryBuffer@Foundation@Windows@8@@Z`
- size: `788`
- prototype: `unsigned int __fastcall(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::Embedding *__hidden this, const struct winrt::Windows::Foundation::IMemoryBuffer *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800691b0`

## callees

- `0x180003bd0`
- `0x180003df0`
- `0x18000d230`
- `0x180010dd0`
- `0x180068bc0`
- `0x1801f97e0`
- `0x180206ea0`
- `0x180207050`
- `0x180242120`
- `0x1802421a0`
- `0x180242860`

## string_xrefs

- `0x180068d23`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\base.h`
- `0x180068be9`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x180068cf8`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\impl\Windows.Foundation.0.h`
- `0x180068e66`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\Embedding.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::Embedding::CopyTo(
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::Embedding *this,
        const struct winrt::Windows::Foundation::IMemoryBuffer *a2)
{
  __int64 v3; // rcx
  int v4; // eax
  __int64 v5; // rbx
  int v6; // eax
  __int64 v7; // rax
  size_t v8; // rdi
  __int64 v9; // rbx
  const void *v10; // r14
  __int64 v11; // rbx
  int v12; // eax
  size_t v13; // rsi
  __int64 v14; // rcx
  int v15; // eax
  int v16; // eax
  int v17; // eax
  void *v19; // [rsp+20h] [rbp-60h] BYREF
  __int64 v20; // [rsp+28h] [rbp-58h] BYREF
  int v21; // [rsp+30h] [rbp-50h] BYREF
  const char *v22; // [rsp+38h] [rbp-48h]
  __int64 v23; // [rsp+40h] [rbp-40h]
  int pExceptionObject; // [rsp+48h] [rbp-38h] BYREF
  const char *v25; // [rsp+50h] [rbp-30h]
  __int64 v26; // [rsp+58h] [rbp-28h]
  _BYTE v27[32]; // [rsp+60h] [rbp-20h] BYREF
  size_t Size; // [rsp+C8h] [rbp+48h] BYREF
  __int64 v29; // [rsp+D0h] [rbp+50h] BYREF
  __int64 v30; // [rsp+D8h] [rbp+58h] BYREF

  v29 = 0;
  v3 = *(_QWORD *)a2;
  v21 = 507;
  v22 = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\winrt\\Windows.Foundation.h";
  v23 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 48LL))(v3, &v29);
  if ( v4 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v4, &v21);
  }
  v20 = v29;
  v5 = *((_QWORD *)this + 8);
  LODWORD(Size) = 0;
  v21 = 543;
  v22 = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\winrt\\Windows.Foundation.h";
  v23 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, size_t *))(*(_QWORD *)v29 + 48LL))(v29, &Size);
  if ( v6 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v6, &v21);
  }
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  if ( (unsigned int)Size != v7 )
  {
    v21 = 24;
    v22 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\Embedding.cpp";
    v23 = 0;
    winrt::param::hstring::hstring((winrt::param::hstring *)v27, L"buffer is not the correct size");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)&pExceptionObject,
      (const struct winrt::param::hstring *)v27,
      (const struct winrt::impl::slim_source_location *)&v21);
    throw (winrt::hresult_invalid_argument *)&pExceptionObject;
  }
  _mm_lfence();
  v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 8LL))(*((_QWORD *)this + 8));
  v9 = *((_QWORD *)this + 8);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
  v10 = (const void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 24LL))(v9);
  LODWORD(Size) = 0;
  v21 = 543;
  v22 = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\winrt\\Windows.Foundation.h";
  v23 = 0;
  v11 = v29;
  v12 = (*(__int64 (__fastcall **)(__int64, size_t *))(*(_QWORD *)v29 + 48LL))(v29, &Size);
  if ( v12 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v12, &v21);
  }
  v13 = (unsigned int)Size;
  v19 = 0;
  LODWORD(Size) = 0;
  pExceptionObject = 745;
  v25 = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\winrt\\impl\\W"
        "indows.Foundation.0.h";
  v26 = 0;
  if ( v11 )
  {
    _mm_lfence();
    v30 = 0;
    v21 = 2135;
    v22 = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\winrt\\base.h";
    v23 = 0;
    v11 = v29;
    v15 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v29)(
            v29,
            winrt::impl::guid_v<winrt::impl::IMemoryBufferByteAccess>,
            &v30);
    if ( v15 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v15, &v21);
    }
    v14 = v30;
    v29 = v30;
  }
  else
  {
    v29 = 0;
    v14 = 0;
  }
  v16 = (*(__int64 (__fastcall **)(__int64, void **, size_t *))(*(_QWORD *)v14 + 24LL))(v14, &v19, &Size);
  if ( v16 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v16, &pExceptionObject);
  }
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v29);
  if ( v8 )
  {
    if ( !v19 )
      goto LABEL_12;
    if ( v10 && v13 >= v8 )
    {
      memmove(v19, v10, v8);
      goto LABEL_20;
    }
    memset(v19, 0, v13);
    if ( v10 )
    {
      if ( v13 >= v8 )
        goto LABEL_20;
      *errno() = 34;
    }
    else
    {
LABEL_12:
      *errno() = 22;
    }
    invalid_parameter_noinfo();
  }
LABEL_20:
  LODWORD(Size) = 0;
  pExceptionObject = 543;
  v25 = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\winrt\\Windows.Foundation.h";
  v26 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, size_t *))(*(_QWORD *)v11 + 48LL))(v11, &Size);
  if ( v17 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v17, &pExceptionObject);
  }
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v20);
  return (unsigned int)Size;
}

```

## disassembly

```asm
0x180068bc0  push    rbp
0x180068bc2  push    rbx
0x180068bc3  push    rsi
0x180068bc4  push    rdi
0x180068bc5  push    r12
0x180068bc7  push    r14
0x180068bc9  push    r15
0x180068bcb  mov     rbp, rsp
0x180068bce  sub     rsp, 80h
0x180068bd5  mov     rsi, rcx
0x180068bd8  xor     r15d, r15d
0x180068bdb  mov     [rbp+arg_10], r15
0x180068bdf  mov     rcx, [rdx]
0x180068be2  mov     [rbp+var_50], 1FBh
0x180068be9  lea     r12, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180068bf0  mov     [rbp+var_48], r12
0x180068bf4  mov     [rbp+var_40], r15
0x180068bf8  mov     rax, [rcx]
0x180068bfb  lea     rdx, [rbp+arg_10]
0x180068bff  mov     rax, [rax+30h]
0x180068c03  call    cs:__guard_dispatch_icall_fptr
0x180068c09  test    eax, eax
0x180068c0b  js      loc_180068E41
0x180068c11  mov     rcx, [rbp+arg_10]
0x180068c15  mov     [rbp+var_58], rcx
0x180068c19  mov     rbx, [rsi+40h]
0x180068c1d  mov     dword ptr [rbp+Size], r15d
0x180068c21  mov     [rbp+var_50], 21Fh
0x180068c28  mov     [rbp+var_48], r12
0x180068c2c  mov     [rbp+var_40], r15
0x180068c30  mov     rax, [rcx]
0x180068c33  lea     rdx, [rbp+Size]
0x180068c37  mov     rax, [rax+30h]
0x180068c3b  call    cs:__guard_dispatch_icall_fptr
0x180068c41  test    eax, eax
0x180068c43  js      loc_180068E50
0x180068c49  mov     rax, [rbx]
0x180068c4c  mov     rcx, rbx
0x180068c4f  mov     rax, [rax+8]
0x180068c53  call    cs:__guard_dispatch_icall_fptr
0x180068c59  mov     ecx, dword ptr [rbp+Size]
0x180068c5c  cmp     rcx, rax
0x180068c5f  jnz     loc_180068E5F
0x180068c65  lfence
0x180068c68  mov     rcx, [rsi+40h]
0x180068c6c  mov     rax, [rcx]
0x180068c6f  mov     rax, [rax+8]
0x180068c73  call    cs:__guard_dispatch_icall_fptr
0x180068c79  mov     rdi, rax
0x180068c7c  mov     rbx, [rsi+40h]
0x180068c80  mov     rdx, [rbx]
0x180068c83  mov     rcx, rbx
0x180068c86  mov     rax, [rdx+10h]
0x180068c8a  call    cs:__guard_dispatch_icall_fptr
0x180068c90  mov     rdx, [rbx]
0x180068c93  mov     rcx, rbx
0x180068c96  mov     rax, [rdx+8]
0x180068c9a  call    cs:__guard_dispatch_icall_fptr
0x180068ca0  mov     rdx, [rbx]
0x180068ca3  mov     rcx, rbx
0x180068ca6  mov     rax, [rdx+18h]
0x180068caa  call    cs:__guard_dispatch_icall_fptr
0x180068cb0  mov     r14, rax
0x180068cb3  mov     dword ptr [rbp+Size], r15d
0x180068cb7  mov     [rbp+var_50], 21Fh
0x180068cbe  mov     [rbp+var_48], r12
0x180068cc2  mov     [rbp+var_40], r15
0x180068cc6  mov     rbx, [rbp+arg_10]
0x180068cca  mov     rcx, [rbx]
0x180068ccd  mov     rax, [rcx+30h]
0x180068cd1  lea     rdx, [rbp+Size]
0x180068cd5  mov     rcx, rbx
0x180068cd8  call    cs:__guard_dispatch_icall_fptr
0x180068cde  test    eax, eax
0x180068ce0  js      loc_180068EA7
0x180068ce6  mov     esi, dword ptr [rbp+Size]
0x180068ce9  mov     [rbp+var_60], r15
0x180068ced  mov     dword ptr [rbp+Size], r15d
0x180068cf1  mov     [rbp+pExceptionObject], 2E9h
0x180068cf8  lea     rax, aCW1SX64Release_5; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180068cff  mov     [rbp+var_30], rax
0x180068d03  mov     [rbp+var_28], r15
0x180068d07  test    rbx, rbx
0x180068d0a  jnz     short loc_180068D15
0x180068d0c  mov     [rbp+arg_10], r15
0x180068d10  mov     ecx, r15d
0x180068d13  jmp     short loc_180068D60
0x180068d15  lfence
0x180068d18  mov     [rbp+arg_18], r15
0x180068d1c  mov     [rbp+var_50], 857h
0x180068d23  lea     rax, aCW1SX64Release_13; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180068d2a  mov     [rbp+var_48], rax
0x180068d2e  mov     [rbp+var_40], r15
0x180068d32  mov     rbx, [rbp+arg_10]
0x180068d36  mov     rax, [rbx]
0x180068d39  lea     r8, [rbp+arg_18]
0x180068d3d  lea     rdx, ??$guid_v@UIMemoryBufferByteAccess@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IMemoryBufferByteAccess>
0x180068d44  mov     rcx, rbx
0x180068d47  mov     rax, [rax]
0x180068d4a  call    cs:__guard_dispatch_icall_fptr
0x180068d50  test    eax, eax
0x180068d52  js      loc_180068EB6
0x180068d58  mov     rcx, [rbp+arg_18]
0x180068d5c  mov     [rbp+arg_10], rcx
0x180068d60  mov     rax, [rcx]
0x180068d63  lea     r8, [rbp+Size]
0x180068d67  lea     rdx, [rbp+var_60]
0x180068d6b  mov     rax, [rax+18h]
0x180068d6f  call    cs:__guard_dispatch_icall_fptr
0x180068d75  test    eax, eax
0x180068d77  js      loc_180068EC5
0x180068d7d  lea     rcx, [rbp+arg_10]
0x180068d81  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180068d86  test    rdi, rdi
0x180068d89  jz      short loc_180068DE9
0x180068d8b  mov     rcx, [rbp+var_60]; void *
0x180068d8f  test    rcx, rcx
0x180068d92  jnz     short loc_180068DA1
0x180068d94  call    _errno
0x180068d99  mov     dword ptr [rax], 16h
0x180068d9f  jmp     short loc_180068DE4
0x180068da1  test    r14, r14
0x180068da4  jz      short loc_180068DB8
0x180068da6  cmp     rsi, rdi
0x180068da9  jb      short loc_180068DB8
0x180068dab  mov     r8, rdi; Size
0x180068dae  mov     rdx, r14; Src
0x180068db1  call    memmove
0x180068db6  jmp     short loc_180068DE9
0x180068db8  mov     r8, rsi; Size
0x180068dbb  xor     edx, edx; Val
0x180068dbd  call    memset
0x180068dc2  test    r14, r14
0x180068dc5  jnz     short loc_180068DD4
0x180068dc7  call    _errno
0x180068dcc  mov     dword ptr [rax], 16h
0x180068dd2  jmp     short loc_180068DE4
0x180068dd4  cmp     rsi, rdi
0x180068dd7  jnb     short loc_180068DE9
0x180068dd9  call    _errno
0x180068dde  mov     dword ptr [rax], 22h ; '"'
0x180068de4  call    _invalid_parameter_noinfo
0x180068de9  mov     dword ptr [rbp+Size], r15d
0x180068ded  mov     [rbp+pExceptionObject], 21Fh
0x180068df4  mov     [rbp+var_30], r12
0x180068df8  mov     [rbp+var_28], r15
0x180068dfc  mov     rax, [rbx]
0x180068dff  lea     rdx, [rbp+Size]
0x180068e03  mov     rcx, rbx
0x180068e06  mov     rax, [rax+30h]
0x180068e0a  call    cs:__guard_dispatch_icall_fptr
0x180068e10  test    eax, eax
0x180068e12  js      short loc_180068E32
0x180068e14  lea     rcx, [rbp+var_58]
0x180068e18  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180068e1d  mov     eax, dword ptr [rbp+Size]
0x180068e20  add     rsp, 80h
0x180068e27  pop     r15
0x180068e29  pop     r14
0x180068e2b  pop     r12
0x180068e2d  pop     rdi
0x180068e2e  pop     rsi
0x180068e2f  pop     rbx
0x180068e30  pop     rbp
0x180068e31  retn
0x180068e32  lfence
0x180068e35  lea     rdx, [rbp+pExceptionObject]
0x180068e39  mov     ecx, eax
0x180068e3b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180068e41  lfence
0x180068e44  lea     rdx, [rbp+var_50]
0x180068e48  mov     ecx, eax
0x180068e4a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180068e50  lfence
0x180068e53  lea     rdx, [rbp+var_50]
0x180068e57  mov     ecx, eax
0x180068e59  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180068e5f  mov     [rbp+var_50], 18h
0x180068e66  lea     rax, aCW1SSrcSemanti_27; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180068e6d  mov     [rbp+var_48], rax
0x180068e71  mov     [rbp+var_40], r15
0x180068e75  lea     rdx, aBufferIsNotThe; "buffer is not the correct size"
0x180068e7c  lea     rcx, [rbp+var_20]; this
0x180068e80  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180068e85  lea     r8, [rbp+var_50]; struct winrt::impl::slim_source_location *
0x180068e89  lea     rdx, [rbp+var_20]; struct winrt::param::hstring *
0x180068e8d  lea     rcx, [rbp+pExceptionObject]; this
0x180068e91  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180068e96  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180068e9d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180068ea1  call    _CxxThrowException
0x180068ea7  lfence
0x180068eaa  lea     rdx, [rbp+var_50]
0x180068eae  mov     ecx, eax
0x180068eb0  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180068eb6  lfence
0x180068eb9  lea     rdx, [rbp+var_50]
0x180068ebd  mov     ecx, eax
0x180068ebf  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180068ec5  lfence
0x180068ec8  lea     rdx, [rbp+pExceptionObject]
0x180068ecc  mov     ecx, eax
0x180068ece  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
