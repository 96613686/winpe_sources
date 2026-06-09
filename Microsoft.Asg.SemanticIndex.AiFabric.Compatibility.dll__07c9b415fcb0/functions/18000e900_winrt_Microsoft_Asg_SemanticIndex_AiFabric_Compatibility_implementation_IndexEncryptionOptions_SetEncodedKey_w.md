# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexEncryptionOptions::SetEncodedKey(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IndexEncryptionFlags,winrt::Windows::Foundation::Collections::IVectorView<uchar> const &)

- ea: `0x18000e900`
- end: `0x18000ebcb`
- name: `?SetEncodedKey@IndexEncryptionOptions@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAAXW4IndexEncryptionFlags@345678@AEBU?$IVectorView@E@Collections@Foundation@Windows@8@@Z`
- size: `715`
- prototype: `__int64 __fastcall(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexEncryptionOptions *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000f950`

## callees

- `0x180003df0`
- `0x18000d230`
- `0x18000e900`
- `0x18000f240`
- `0x18000f4d0`
- `0x18000fe80`
- `0x180010400`
- `0x180010490`
- `0x180010dd0`
- `0x1801d2ae0`
- `0x1801d2b20`
- `0x1801d2dc0`
- `0x1801f97e0`
- `0x180242120`

## string_xrefs

- `0x18000eb06`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexEncryptionOptions.cpp`
- `0x18000eb6c`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexEncryptionOptions.cpp`
- `0x18000e9ee`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.Collections.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
int __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexEncryptionOptions::SetEncodedKey(
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexEncryptionOptions *this,
        int a2,
        _QWORD *a3)
{
  char *v6; // rbx
  __int64 v8; // rcx
  int v9; // eax
  char v10; // al
  __int64 v11; // rcx
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned int *v16; // rax
  __int64 v17; // [rsp+20h] [rbp-138h] BYREF
  const char *v18; // [rsp+28h] [rbp-130h]
  const char *v19; // [rsp+30h] [rbp-128h]
  _OWORD v20[2]; // [rsp+40h] [rbp-118h] BYREF
  int v21; // [rsp+60h] [rbp-F8h]
  _QWORD *v22; // [rsp+70h] [rbp-E8h] BYREF
  int v23; // [rsp+78h] [rbp-E0h]
  char *v24; // [rsp+80h] [rbp-D8h]
  _BYTE pExceptionObject[24]; // [rsp+88h] [rbp-D0h] BYREF
  _BYTE v26[24]; // [rsp+A0h] [rbp-B8h] BYREF
  _BYTE v27[24]; // [rsp+B8h] [rbp-A0h] BYREF
  _BYTE v28[32]; // [rsp+D0h] [rbp-88h] BYREF
  _BYTE v29[104]; // [rsp+F0h] [rbp-68h] BYREF
  winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexEncryptionOptions *v30; // [rsp+160h] [rbp+8h] BYREF
  int v31; // [rsp+178h] [rbp+20h] BYREF

  v30 = this;
  v21 = 0;
  v6 = (char *)this + 40;
  v24 = (char *)this + 40;
  if ( Mtx_lock((winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexEncryptionOptions *)((char *)this + 40)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)v6 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v6 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  *((_BYTE *)this + 168) = 0;
  memset(v20, 0, sizeof(v20));
  std::vector<unsigned char,asg::secure_allocator<unsigned char>>::operator=((char *)this + 176, v20);
  std::vector<unsigned char,asg::secure_allocator<unsigned char>>::_Tidy(v20);
  *((_DWORD *)this + 43) = 0;
  if ( a2 )
  {
    if ( a2 != 65538 )
    {
      LODWORD(v17) = 41;
      v18 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexEncryptionOptions.cpp";
      v19 = 0;
      winrt::param::hstring::hstring((winrt::param::hstring *)v20, L"invalid IndexEncryptionFlags");
      winrt::hresult_invalid_argument::hresult_invalid_argument(
        (winrt::hresult_invalid_argument *)pExceptionObject,
        (const struct winrt::param::hstring *)v20,
        (const struct winrt::impl::slim_source_location *)&v17);
      throw (winrt::hresult_invalid_argument *)pExceptionObject;
    }
    v22 = 0;
    v21 = 1;
    v8 = *a3;
    if ( !*a3 )
      goto LABEL_11;
    v31 = 0;
    LODWORD(v17) = 512;
    v18 = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\winrt\\Windo"
          "ws.Foundation.Collections.h";
    v19 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v8 + 56LL))(v8, &v31);
    if ( v9 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v9, &v17);
    }
    if ( v31 == 32 )
      v10 = 0;
    else
LABEL_11:
      v10 = 1;
    if ( v10 )
    {
      LODWORD(v17) = 46;
      v18 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexEncryptionOptions.cpp";
      v19 = 0;
      winrt::param::hstring::hstring((winrt::param::hstring *)v20, L"Invalid or missing AES256 key; expected 32 bytes.");
      winrt::hresult_invalid_argument::hresult_invalid_argument(
        (winrt::hresult_invalid_argument *)v26,
        (const struct winrt::param::hstring *)v20,
        (const struct winrt::impl::slim_source_location *)&v17);
      throw (winrt::hresult_invalid_argument *)v26;
    }
    *((_DWORD *)this + 43) = 65538;
    v31 = 0;
    v11 = *a3;
    LODWORD(v17) = 512;
    v18 = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\winrt\\Windo"
          "ws.Foundation.Collections.h";
    v19 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v11 + 56LL))(v11, &v31);
    try
    {
      if ( v12 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v12, &v17);
      }
      v22 = a3;
      v23 = v31;
      v17 = (__int64)a3;
      LODWORD(v18) = 0;
      asg::Sqlite::DbAesKeyStore::Load<winrt::impl::fast_iterator<winrt::Windows::Foundation::Collections::IVectorView<unsigned char>>>(
        (char *)this + 176,
        &v17,
        &v22);
    }
    catch ( ... )
    {
      memset(v20, 0, sizeof(v20));
      asg::Sqlite::DbAesKeyStore::DbAesKeyStore((asg::Sqlite::DbAesKeyStore *)v20);
      asg::Sqlite::DbAesKeyStore::operator=((char *)v30 + 176, v20);
      std::vector<unsigned char,asg::secure_allocator<unsigned char>>::~vector<unsigned char,asg::secure_allocator<unsigned char>>(v20);
      v13 = asg::SemanticIndex::ResultFromCaughtSemanticIndexException();
      v17 = 0x300000003CLL;
      v18 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexEncryptionOptions.cpp";
      v19 = "void __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexEncryptionO"
            "ptions::SetEncodedKey(enum winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IndexEncryptionFla"
            "gs,const struct winrt::Windows::Foundation::Collections::IVectorView<unsigned char> &)";
      asg::SemanticIndex::LogCaughtSemanticIndexException(v29, v13, &v17);
      LODWORD(v20[0]) = 61;
      *((_QWORD *)&v20[0] + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexEncryptionOptions.cpp";
      *(_QWORD *)&v20[1] = 0;
      v14 = asg::LogStringView::View(v29, &v17);
      v15 = asg::as_u16string_view(&v22, v14);
      winrt::param::hstring::hstring(v28, v15);
      v16 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v30, v13);
      winrt::hresult_error::hresult_error(v27, *v16, v28, v20);
      throw (winrt::hresult_error *)v27;
    }
    winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexEncryptionOptions::UpdateDeprecatedFromActual(this);
  }
  else
  {
    std::basic_string<wchar_t,std::char_traits<wchar_t>,asg::secure_allocator<wchar_t>>::assign(
      (char *)this + 128,
      0,
      0);
    *((_DWORD *)this + 30) = 0;
  }
  return Mtx_unlock((_Mtx_t)v6);
}

```

## disassembly

```asm
0x18000e900  mov     [rsp+arg_8], rbx
0x18000e905  mov     [rsp+arg_0], rcx
0x18000e90a  push    rsi
0x18000e90b  push    rdi
0x18000e90c  push    r12
0x18000e90e  push    r14
0x18000e910  push    r15
0x18000e912  sub     rsp, 130h
0x18000e919  mov     rsi, r8
0x18000e91c  mov     r14d, edx
0x18000e91f  mov     rdi, rcx
0x18000e922  xor     r12d, r12d
0x18000e925  mov     [rsp+158h+var_F8], r12d
0x18000e92a  lea     rbx, [rcx+28h]
0x18000e92e  mov     [rsp+158h+var_D8], rbx
0x18000e936  mov     rcx, rbx; _Mtx_t
0x18000e939  call    _Mtx_lock
0x18000e93e  test    eax, eax
0x18000e940  jnz     loc_18000EAE1
0x18000e946  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18000e94d  jz      loc_18000EAEC
0x18000e953  mov     byte ptr [rdi+0A8h], 0
0x18000e95a  xorps   xmm0, xmm0
0x18000e95d  movups  [rsp+158h+var_118], xmm0
0x18000e962  movups  [rsp+158h+var_108], xmm0
0x18000e967  xorps   xmm1, xmm1
0x18000e96a  movdqu  [rsp+158h+var_118+8], xmm1
0x18000e970  mov     qword ptr [rsp+158h+var_108+8], r12
0x18000e975  lea     rdx, [rsp+158h+var_118]
0x18000e97a  lea     rcx, [rdi+0B0h]
0x18000e981  call    ??4?$vector@EU?$secure_allocator@E@asg@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar,asg::secure_allocator<uchar>>::operator=(std::vector<uchar,asg::secure_allocator<uchar>> &&)
0x18000e986  nop
0x18000e987  lea     rcx, [rsp+158h+var_118]
0x18000e98c  call    ?_Tidy@?$vector@EU?$secure_allocator@E@asg@@@std@@AEAAXXZ; std::vector<uchar,asg::secure_allocator<uchar>>::_Tidy(void)
0x18000e991  mov     [rdi+0ACh], r12d
0x18000e998  test    r14d, r14d
0x18000e99b  jnz     short loc_18000E9D1
0x18000e99d  lea     rcx, [rdi+80h]
0x18000e9a4  xor     r8d, r8d
0x18000e9a7  xor     edx, edx
0x18000e9a9  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@U?$secure_allocator@_W@asg@@@std@@QEAAAEAV12@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,asg::secure_allocator<wchar_t>>::assign(wchar_t const * const,unsigned __int64)
0x18000e9ae  mov     [rdi+78h], r12d
0x18000e9b2  mov     rcx, rbx
0x18000e9b5  mov     rbx, [rsp+158h+arg_8]
0x18000e9bd  add     rsp, 130h
0x18000e9c4  pop     r15
0x18000e9c6  pop     r14
0x18000e9c8  pop     r12
0x18000e9ca  pop     rdi
0x18000e9cb  pop     rsi
0x18000e9cc  jmp     _Mtx_unlock
0x18000e9d1  cmp     r14d, 10002h
0x18000e9d8  jnz     loc_18000EAFE
0x18000e9de  mov     qword ptr [rsp+158h+var_E8], r12
0x18000e9e3  mov     [rsp+158h+var_F8], 1
0x18000e9eb  mov     rcx, [rsi]
0x18000e9ee  lea     r14, aCW1SX64Release; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18000e9f5  test    rcx, rcx
0x18000e9f8  jz      short loc_18000EA3F
0x18000e9fa  mov     [rsp+158h+arg_18], r12d
0x18000ea02  mov     dword ptr [rsp+158h+var_138], 200h
0x18000ea0a  mov     qword ptr [rsp+158h+var_138+8], r14
0x18000ea0f  mov     [rsp+158h+var_128], r12
0x18000ea14  mov     rax, [rcx]
0x18000ea17  lea     rdx, [rsp+158h+arg_18]
0x18000ea1f  mov     rax, [rax+38h]
0x18000ea23  call    cs:__guard_dispatch_icall_fptr
0x18000ea29  test    eax, eax
0x18000ea2b  js      loc_18000EB54
0x18000ea31  cmp     [rsp+158h+arg_18], 20h ; ' '
0x18000ea39  jnz     short loc_18000EA3F
0x18000ea3b  xor     al, al
0x18000ea3d  jmp     short loc_18000EA41
0x18000ea3f  mov     al, 1
0x18000ea41  test    al, al
0x18000ea43  jnz     loc_18000EB64
0x18000ea49  mov     dword ptr [rdi+0ACh], 10002h
0x18000ea53  mov     [rsp+158h+arg_18], r12d
0x18000ea5b  mov     rcx, [rsi]
0x18000ea5e  mov     dword ptr [rsp+158h+var_138], 200h
0x18000ea66  mov     qword ptr [rsp+158h+var_138+8], r14
0x18000ea6b  mov     [rsp+158h+var_128], r12
0x18000ea70  mov     rax, [rcx]
0x18000ea73  lea     rdx, [rsp+158h+arg_18]
0x18000ea7b  mov     rax, [rax+38h]
0x18000ea7f  call    cs:__guard_dispatch_icall_fptr
0x18000ea85  test    eax, eax
0x18000ea87  js      loc_18000EBBA
0x18000ea8d  mov     qword ptr [rsp+158h+var_E8], rsi
0x18000ea92  mov     eax, [rsp+158h+arg_18]
0x18000ea99  mov     dword ptr [rsp+158h+var_E8+8], eax
0x18000ea9d  mov     qword ptr [rsp+158h+var_138], rsi
0x18000eaa2  mov     dword ptr [rsp+158h+var_138+8], r12d
0x18000eaa7  movaps  xmm0, [rsp+158h+var_E8]
0x18000eaac  movdqa  [rsp+158h+var_E8], xmm0
0x18000eab2  movaps  xmm1, [rsp+158h+var_138]
0x18000eab7  movdqa  [rsp+158h+var_138], xmm1
0x18000eabd  lea     r8, [rsp+158h+var_E8]
0x18000eac2  lea     rdx, [rsp+158h+var_138]
0x18000eac7  lea     rcx, [rdi+0B0h]
0x18000eace  call    ??$Load@U?$fast_iterator@U?$IVectorView@E@Collections@Foundation@Windows@winrt@@@impl@winrt@@@DbAesKeyStore@Sqlite@asg@@QEAAXU?$fast_iterator@U?$IVectorView@E@Collections@Foundation@Windows@winrt@@@impl@winrt@@0@Z; asg::Sqlite::DbAesKeyStore::Load<winrt::impl::fast_iterator<winrt::Windows::Foundation::Collections::IVectorView<uchar>>>(winrt::impl::fast_iterator<winrt::Windows::Foundation::Collections::IVectorView<uchar>>,winrt::impl::fast_iterator<winrt::Windows::Foundation::Collections::IVectorView<uchar>>)
0x18000ead3  nop
0x18000ead4  mov     rcx, rdi; this
0x18000ead7  call    ?UpdateDeprecatedFromActual@IndexEncryptionOptions@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAAXXZ; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexEncryptionOptions::UpdateDeprecatedFromActual(void)
0x18000eadc  jmp     loc_18000E9B2
0x18000eae1  mov     ecx, 5; int
0x18000eae6  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000eaec  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x18000eaf3  mov     ecx, 6; int
0x18000eaf8  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000eafe  mov     dword ptr [rsp+158h+var_138], 29h ; ')'
0x18000eb06  lea     rax, aCW1SSrcSemanti_25; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18000eb0d  mov     qword ptr [rsp+158h+var_138+8], rax
0x18000eb12  mov     [rsp+158h+var_128], r12
0x18000eb17  lea     rdx, aInvalidIndexen; "invalid IndexEncryptionFlags"
0x18000eb1e  lea     rcx, [rsp+158h+var_118]; this
0x18000eb23  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18000eb28  lea     r8, [rsp+158h+var_138]; struct winrt::impl::slim_source_location *
0x18000eb2d  lea     rdx, [rsp+158h+var_118]; struct winrt::param::hstring *
0x18000eb32  lea     rcx, [rsp+158h+pExceptionObject]; this
0x18000eb3a  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18000eb3f  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18000eb46  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x18000eb4e  call    _CxxThrowException
0x18000eb54  lfence
0x18000eb57  lea     rdx, [rsp+158h+var_138]
0x18000eb5c  mov     ecx, eax
0x18000eb5e  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000eb64  mov     dword ptr [rsp+158h+var_138], 2Eh ; '.'
0x18000eb6c  lea     rax, aCW1SSrcSemanti_25; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18000eb73  mov     qword ptr [rsp+158h+var_138+8], rax
0x18000eb78  mov     [rsp+158h+var_128], r12
0x18000eb7d  lea     rdx, aInvalidOrMissi; "Invalid or missing AES256 key; expected"...
0x18000eb84  lea     rcx, [rsp+158h+var_118]; this
0x18000eb89  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18000eb8e  lea     r8, [rsp+158h+var_138]; struct winrt::impl::slim_source_location *
0x18000eb93  lea     rdx, [rsp+158h+var_118]; struct winrt::param::hstring *
0x18000eb98  lea     rcx, [rsp+158h+var_B8]; this
0x18000eba0  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18000eba5  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18000ebac  lea     rcx, [rsp+158h+var_B8]; pExceptionObject
0x18000ebb4  call    _CxxThrowException
0x18000ebba  lfence
0x18000ebbd  lea     rdx, [rsp+158h+var_138]
0x18000ebc2  mov     ecx, eax
0x18000ebc4  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
