# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextTokenizerWrapper::Tokenize(unsigned __int64,std::span<char16_t const,-1>,asg::SemanticRegistry::TokenizerBreakDirective,asg::SemanticRegistry::ExecutionPriorityHint)

- ea: `0x180059490`
- end: `0x18005999f`
- name: `?Tokenize@TextTokenizerWrapper@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UEBA?AV?$vector@UTokenText@SemanticRegistry@asg@@V?$allocator@UTokenText@SemanticRegistry@asg@@@std@@@std@@_KV?$span@$$CB_S$0?0@std@@W4TokenizerBreakDirective@SemanticRegistry@asg@@W4ExecutionPriorityHint@SemanticRegistry@asg@@@Z`
- size: `1295`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003bd0`
- `0x180003df0`
- `0x180006e30`
- `0x180007ba0`
- `0x18000d230`
- `0x180010dd0`
- `0x18001fc60`
- `0x180039160`
- `0x18003cd90`
- `0x180057f20`
- `0x180058670`
- `0x180059490`
- `0x1801f7190`
- `0x1801f97e0`
- `0x18022aeae`
- `0x180242120`
- `0x1802421a0`

## string_xrefs

- `0x180059682`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x1800595f9`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x1800598a3`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticVectorSpaceModelRegistry.cpp`
- `0x1800598ee`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticVectorSpaceModelRegistry.cpp`
- `0x180059949`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticVectorSpaceModelRegistry.cpp`
- `0x180059958`: `Invalid asg::SemanticRegistry::TokenizerBreakDirective`
- `0x1800598b2`: `Invalid winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::CharacterBreakType`
- `0x1800598ff`: `text has too many characters to tokenize`
- `0x180059859`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\Utilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextTokenizerWrapper::Tokenize(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        __int64 *a4,
        int a5,
        unsigned int a6)
{
  unsigned int v6; // r15d
  unsigned __int64 v8; // r12
  __int64 v9; // rdi
  _QWORD *v10; // rsi
  _DWORD *v11; // rdi
  int v12; // eax
  int v13; // r8d
  int v14; // edx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rbx
  char *v18; // r15
  __int64 v19; // rdi
  __int64 v20; // rsi
  _QWORD *v21; // rbx
  char *v22; // rbx
  int v23; // eax
  int v24; // eax
  int v25; // eax
  __int64 v26; // rdx
  __int128 pExceptionObject; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+70h] [rbp-90h]
  int v30; // [rsp+80h] [rbp-80h] BYREF
  const char *v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+90h] [rbp-70h]
  LPVOID pv[3]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD *v34; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v35[2]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v36[104]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v38; // [rsp+160h] [rbp+60h] BYREF
  __int64 v39; // [rsp+168h] [rbp+68h] BYREF

  v6 = a3;
  if ( a3 > 0xFFFFFFFF )
    v6 = -1;
  v8 = a4[1];
  if ( v8 > 0xFFFFFFFF )
  {
    LODWORD(pExceptionObject) = 270;
    *((_QWORD *)&pExceptionObject + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\Sem"
                                         "anticVectorSpaceModelRegistry.cpp";
    v29 = 0;
    winrt::param::hstring::hstring((winrt::param::hstring *)v35, L"text has too many characters to tokenize");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)&v30,
      (const struct winrt::param::hstring *)v35,
      (const struct winrt::impl::slim_source_location *)&pExceptionObject);
    throw (winrt::hresult_invalid_argument *)&v30;
  }
  v9 = *a4;
  v35[0] = 0u;
  v38 = 0;
  v10 = operator new(0x40u);
  v34 = v10;
  *(_QWORD *)&pExceptionObject = v9;
  DWORD2(pExceptionObject) = 2 * v8;
  v10[1] = &winrt::impl::produce<CustomMemoryBuffer,winrt::Windows::Foundation::IMemoryBuffer>::`vftable';
  v10[2] = &winrt::impl::produce<CustomMemoryBuffer,winrt::Windows::Foundation::IClosable>::`vftable';
  *v10 = &winrt::impl::producers_base<CustomMemoryBuffer,std::tuple<winrt::Windows::Foundation::IMemoryBuffer,Windows::Foundation::IMemoryBufferByteAccess,winrt::Windows::Foundation::IClosable>>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v10[4] = 1;
  *v10 = &CustomMemoryBuffer::`vftable'{for `winrt::impl::producers_base<CustomMemoryBuffer,std::tuple<winrt::Windows::Foundation::IMemoryBuffer,Windows::Foundation::IMemoryBufferByteAccess,winrt::Windows::Foundation::IClosable>>'};
  v10[3] = &CustomMemoryBuffer::`vftable'{for `winrt::impl::root_implements<CustomMemoryBuffer,winrt::Windows::Foundation::IMemoryBuffer,winrt::cloaked<Windows::Foundation::IMemoryBufferByteAccess>,winrt::Windows::Foundation::IClosable>'};
  v11 = operator new(0x38u);
  pv[0] = v11;
  *(_OWORD *)v11 = 0;
  v11[2] = 1;
  v11[3] = 1;
  *(_QWORD *)v11 = &std::_Ref_count_obj2<MemoryLifetime>::`vftable';
  MemoryLifetime::MemoryLifetime(v11 + 4, &pExceptionObject, &v38);
  v10[5] = 0;
  v10[6] = v11 + 4;
  v10[7] = v11;
  *v10 = &winrt::impl::heap_implements<CustomMemoryBuffer>::`vftable'{for `winrt::impl::producers_base<CustomMemoryBuffer,std::tuple<winrt::Windows::Foundation::IMemoryBuffer,Windows::Foundation::IMemoryBufferByteAccess,winrt::Windows::Foundation::IClosable>>'};
  v10[3] = &winrt::impl::heap_implements<CustomMemoryBuffer>::`vftable'{for `winrt::impl::root_implements<CustomMemoryBuffer,winrt::Windows::Foundation::IMemoryBuffer,winrt::cloaked<Windows::Foundation::IMemoryBufferByteAccess>,winrt::Windows::Foundation::IClosable>'};
  v34 = v10 + 1;
  if ( v38 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v38);
  v38 = 0;
  LODWORD(pExceptionObject) = 507;
  *((_QWORD *)&pExceptionObject + 1) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\"
                                       "Generated Files\\winrt\\Windows.Foundation.h";
  v29 = 0;
  v12 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(v10[1] + 48LL))(v10 + 1, &v38);
  if ( v12 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v12, &pExceptionObject);
  }
  v39 = v38;
  *(_QWORD *)&pExceptionObject = &v39;
  BYTE8(pExceptionObject) = 1;
  v13 = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::FromAsg(a6);
  v14 = a5;
  if ( a5 )
  {
    if ( a5 != 1 )
    {
      LODWORD(pv[0]) = 48;
      pv[1] = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticVectorSpaceModelRegistry.cpp";
      pv[2] = 0;
      winrt::param::hstring::hstring(
        (winrt::param::hstring *)v36,
        L"Invalid asg::SemanticRegistry::TokenizerBreakDirective");
      winrt::hresult_invalid_argument::hresult_invalid_argument(
        (winrt::hresult_invalid_argument *)&v30,
        (const struct winrt::param::hstring *)v36,
        (const struct winrt::impl::slim_source_location *)pv);
      throw (winrt::hresult_invalid_argument *)&v30;
    }
  }
  else
  {
    v14 = 0;
  }
  LODWORD(v38) = 0;
  pv[0] = 0;
  v15 = *(_QWORD *)(a1 + 8);
  v30 = 4194;
  v31 = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\winrt\\Microso"
        "ft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v32 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, int, int, __int64 *, LPVOID *))(*(_QWORD *)v15 + 48LL))(
          v15,
          v6,
          (unsigned int)v8,
          v39,
          v14,
          v13,
          &v38,
          pv);
  if ( v16 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v16, &v30);
  }
  v17 = (unsigned int)v38;
  v18 = (char *)pv[0];
  *(LPVOID *)&v35[0] = pv[0];
  DWORD2(v35[0]) = v38;
  winrt::impl::consume_Windows_Foundation_IClosable<winrt::Windows::Graphics::Imaging::IBitmapBuffer>::Close(&v39);
  if ( v39 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v39);
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v34);
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 16) = 0;
  v19 = v17;
  if ( (_DWORD)v17 )
  {
    _mm_lfence();
    v20 = 24 * v17;
    v21 = std::_Allocate<16,std::_Default_allocate_traits>(24 * v17);
    memmove(v21, *(const void **)a2, *(_QWORD *)(a2 + 8) - *(_QWORD *)a2);
    std::vector<asg::SemanticRegistry::TokenText>::_Change_array(a2, v21, 0, v19);
    v18 = (char *)pv[0];
  }
  else
  {
    v20 = 24 * v17;
  }
  if ( v18 != &v18[v20] )
  {
    v22 = v18 + 16;
    do
    {
      v23 = *(_DWORD *)v22;
      if ( *(_DWORD *)v22 && (unsigned int)(*(_DWORD *)v22 - 1) > 1 )
      {
        v30 = 107;
        v31 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\Utilities.cpp";
        v32 = 0;
        winrt::param::hstring::hstring((winrt::param::hstring *)v36, L"invalid CharacterBreakType");
        winrt::hresult_invalid_argument::hresult_invalid_argument(
          (winrt::hresult_invalid_argument *)&pExceptionObject,
          (const struct winrt::param::hstring *)v36,
          (const struct winrt::impl::slim_source_location *)&v30);
        throw (winrt::hresult_invalid_argument *)&pExceptionObject;
      }
      pExceptionObject = *((_OWORD *)v22 - 1);
      if ( v23 )
      {
        v24 = v23 - 1;
        if ( v24 )
        {
          if ( v24 != 1 )
          {
            v30 = 64;
            v31 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticVectorSpaceModelRegistry.cpp";
            v32 = 0;
            winrt::param::hstring::hstring(
              (winrt::param::hstring *)v36,
              L"Invalid winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::CharacterBreakType");
            winrt::hresult_invalid_argument::hresult_invalid_argument(
              (winrt::hresult_invalid_argument *)&pExceptionObject,
              (const struct winrt::param::hstring *)v36,
              (const struct winrt::impl::slim_source_location *)&v30);
            throw (winrt::hresult_invalid_argument *)&pExceptionObject;
          }
          v25 = 2;
        }
        else
        {
          v25 = 1;
        }
      }
      else
      {
        v25 = 0;
      }
      LODWORD(v29) = v25;
      BYTE4(v29) = v22[4];
      v26 = *(_QWORD *)(a2 + 8);
      if ( v26 == *(_QWORD *)(a2 + 16) )
      {
        std::vector<asg::SemanticRegistry::TokenText>::_Emplace_reallocate<asg::SemanticRegistry::TokenText>(
          (const void **)a2,
          (_BYTE *)v26,
          (__int64)&pExceptionObject);
      }
      else
      {
        *(_OWORD *)v26 = pExceptionObject;
        *(_QWORD *)(v26 + 16) = v29;
        *(_QWORD *)(a2 + 8) += 24LL;
      }
      v22 += 24;
    }
    while ( v22 - 16 != &v18[v20] );
  }
  if ( v18 )
    CoTaskMemFree_0(v18);
  return a2;
}

```

## disassembly

```asm
0x180059490  mov     [rsp-8+arg_8], rdx
0x180059495  mov     [rsp-8+arg_0], rcx
0x18005949a  push    rbp
0x18005949b  push    rbx
0x18005949c  push    rsi
0x18005949d  push    rdi
0x18005949e  push    r12
0x1800594a0  push    r13
0x1800594a2  push    r14
0x1800594a4  push    r15
0x1800594a6  lea     rbp, [rsp-8]
0x1800594ab  sub     rsp, 108h
0x1800594b2  mov     r15, r8
0x1800594b5  mov     r14, rdx
0x1800594b8  xor     ecx, ecx
0x1800594ba  mov     [rsp+140h+var_F0], ecx
0x1800594be  mov     eax, 0FFFFFFFFh
0x1800594c3  cmp     r8, rax
0x1800594c6  cmova   r15, rax
0x1800594ca  mov     r12, [r9+8]
0x1800594ce  cmp     r12, rax
0x1800594d1  ja      loc_1800598E6
0x1800594d7  mov     rdi, [r9]
0x1800594da  xorps   xmm0, xmm0
0x1800594dd  movups  [rbp+40h+var_88], xmm0
0x1800594e1  mov     qword ptr [rbp+40h+var_88], rcx
0x1800594e5  mov     dword ptr [rbp+40h+var_88+8], ecx
0x1800594e8  mov     [rbp+40h+arg_10], rcx
0x1800594ec  lea     ebx, [r12+r12]
0x1800594f0  mov     ecx, 40h ; '@'; Size
0x1800594f5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800594fa  mov     rsi, rax
0x1800594fd  mov     [rbp+40h+var_90], rax
0x180059501  mov     qword ptr [rsp+140h+pExceptionObject], rdi
0x180059506  mov     dword ptr [rsp+140h+pExceptionObject+8], ebx
0x18005950a  mov     ecx, dword ptr [rsp+140h+pExceptionObject+0Ch]
0x18005950e  mov     dword ptr [rsp+140h+pExceptionObject+0Ch], ecx
0x180059512  lea     r13, [rax+8]
0x180059516  lea     rax, ??_7?$produce@UCustomMemoryBuffer@@UIMemoryBuffer@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<CustomMemoryBuffer,winrt::Windows::Foundation::IMemoryBuffer>::`vftable'
0x18005951d  mov     [r13+0], rax
0x180059521  lea     rax, ??_7?$produce@UCustomMemoryBuffer@@UIClosable@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<CustomMemoryBuffer,winrt::Windows::Foundation::IClosable>::`vftable'
0x180059528  mov     [rsi+10h], rax
0x18005952c  lea     rax, ??_7?$producers_base@UCustomMemoryBuffer@@V?$tuple@UIMemoryBuffer@Foundation@Windows@winrt@@UIMemoryBufferByteAccess@23@UIClosable@234@@std@@@impl@winrt@@6B@; const winrt::impl::producers_base<CustomMemoryBuffer,std::tuple<winrt::Windows::Foundation::IMemoryBuffer,Windows::Foundation::IMemoryBufferByteAccess,winrt::Windows::Foundation::IClosable>>::`vftable'
0x180059533  mov     [rsi], rax
0x180059536  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18005953d  mov     qword ptr [rsi+20h], 1
0x180059545  lea     rax, ??_7CustomMemoryBuffer@@6B?$producers_base@UCustomMemoryBuffer@@V?$tuple@UIMemoryBuffer@Foundation@Windows@winrt@@UIMemoryBufferByteAccess@23@UIClosable@234@@std@@@impl@winrt@@@; const CustomMemoryBuffer::`vftable'{for `winrt::impl::producers_base<CustomMemoryBuffer,std::tuple<winrt::Windows::Foundation::IMemoryBuffer,Windows::Foundation::IMemoryBufferByteAccess,winrt::Windows::Foundation::IClosable>>'}
0x18005954c  mov     [rsi], rax
0x18005954f  lea     rax, ??_7CustomMemoryBuffer@@6B?$root_implements@UCustomMemoryBuffer@@UIMemoryBuffer@Foundation@Windows@winrt@@U?$cloaked@UIMemoryBufferByteAccess@Foundation@Windows@@@5@UIClosable@345@@impl@winrt@@@; const CustomMemoryBuffer::`vftable'{for `winrt::impl::root_implements<CustomMemoryBuffer,winrt::Windows::Foundation::IMemoryBuffer,winrt::cloaked<Windows::Foundation::IMemoryBufferByteAccess>,winrt::Windows::Foundation::IClosable>'}
0x180059556  mov     [rsi+18h], rax
0x18005955a  mov     ecx, 38h ; '8'; Size
0x18005955f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180059564  mov     rdi, rax
0x180059567  mov     [rbp+40h+pv], rax
0x18005956b  xorps   xmm0, xmm0
0x18005956e  movups  xmmword ptr [rax], xmm0
0x180059571  mov     dword ptr [rax+8], 1
0x180059578  mov     dword ptr [rax+0Ch], 1
0x18005957f  lea     rax, ??_7?$_Ref_count_obj2@UMemoryLifetime@@@std@@6B@; const std::_Ref_count_obj2<MemoryLifetime>::`vftable'
0x180059586  mov     [rdi], rax
0x180059589  lea     rbx, [rdi+10h]
0x18005958d  movaps  xmm0, [rsp+140h+pExceptionObject]
0x180059592  movdqa  [rsp+140h+pExceptionObject], xmm0
0x180059598  lea     r8, [rbp+40h+arg_10]
0x18005959c  lea     rdx, [rsp+140h+pExceptionObject]
0x1800595a1  mov     rcx, rbx
0x1800595a4  call    ??0MemoryLifetime@@QEAA@U?$array_view@E@winrt@@AEBUDeferralCompletedHandler@Foundation@Windows@2@@Z; MemoryLifetime::MemoryLifetime(winrt::array_view<uchar>,winrt::Windows::Foundation::DeferralCompletedHandler const &)
0x1800595a9  nop
0x1800595aa  mov     qword ptr [rsi+28h], 0
0x1800595b2  mov     [rsi+30h], rbx
0x1800595b6  mov     [rsi+38h], rdi
0x1800595ba  lea     rax, ??_7?$heap_implements@UCustomMemoryBuffer@@@impl@winrt@@6B?$producers_base@UCustomMemoryBuffer@@V?$tuple@UIMemoryBuffer@Foundation@Windows@winrt@@UIMemoryBufferByteAccess@23@UIClosable@234@@std@@@12@@; const winrt::impl::heap_implements<CustomMemoryBuffer>::`vftable'{for `winrt::impl::producers_base<CustomMemoryBuffer,std::tuple<winrt::Windows::Foundation::IMemoryBuffer,Windows::Foundation::IMemoryBufferByteAccess,winrt::Windows::Foundation::IClosable>>'}
0x1800595c1  mov     [rsi], rax
0x1800595c4  lea     rax, ??_7?$heap_implements@UCustomMemoryBuffer@@@impl@winrt@@6B?$root_implements@UCustomMemoryBuffer@@UIMemoryBuffer@Foundation@Windows@winrt@@U?$cloaked@UIMemoryBufferByteAccess@Foundation@Windows@@@5@UIClosable@345@@12@@; const winrt::impl::heap_implements<CustomMemoryBuffer>::`vftable'{for `winrt::impl::root_implements<CustomMemoryBuffer,winrt::Windows::Foundation::IMemoryBuffer,winrt::cloaked<Windows::Foundation::IMemoryBufferByteAccess>,winrt::Windows::Foundation::IClosable>'}
0x1800595cb  mov     [rsi+18h], rax
0x1800595cf  mov     [rbp+40h+var_90], r13
0x1800595d3  mov     [rsp+140h+var_F0], 1Eh
0x1800595db  cmp     [rbp+40h+arg_10], 0
0x1800595e0  jz      short loc_1800595EB
0x1800595e2  lea     rcx, [rbp+40h+arg_10]
0x1800595e6  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800595eb  xor     ebx, ebx
0x1800595ed  mov     [rbp+40h+arg_10], rbx
0x1800595f1  mov     dword ptr [rsp+140h+pExceptionObject], 1FBh
0x1800595f9  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180059600  mov     qword ptr [rsp+140h+pExceptionObject+8], rax
0x180059605  mov     [rsp+140h+var_D0], rbx
0x18005960a  mov     rax, [r13+0]
0x18005960e  lea     rdx, [rbp+40h+arg_10]
0x180059612  mov     rcx, r13
0x180059615  mov     rax, [rax+30h]
0x180059619  call    cs:__guard_dispatch_icall_fptr
0x18005961f  test    eax, eax
0x180059621  js      loc_180059932
0x180059627  mov     rax, [rbp+40h+arg_10]
0x18005962b  mov     [rbp+40h+arg_18], rax
0x18005962f  mov     [rsp+140h+var_F0], 3Eh ; '>'
0x180059637  lea     rax, [rbp+40h+arg_18]
0x18005963b  mov     qword ptr [rsp+140h+pExceptionObject], rax
0x180059640  mov     byte ptr [rsp+140h+pExceptionObject+8], 1
0x180059645  mov     ecx, [rbp+40h+arg_28]
0x180059648  call    winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__FromAsg
0x18005964d  mov     r8d, eax
0x180059650  mov     edx, [rbp+40h+arg_20]
0x180059653  test    edx, edx
0x180059655  jz      short loc_180059665
0x180059657  cmp     edx, 1
0x18005965a  jnz     loc_180059942
0x180059660  xor     r13d, r13d
0x180059663  jmp     short loc_18005966B
0x180059665  xor     r13d, r13d
0x180059668  mov     edx, r13d
0x18005966b  mov     dword ptr [rbp+40h+arg_10], r13d
0x18005966f  mov     [rbp+40h+pv], r13
0x180059673  mov     rcx, [rbp+40h+arg_0]
0x180059677  mov     rcx, [rcx+8]
0x18005967b  mov     [rbp+40h+var_C0], 1062h
0x180059682  lea     rax, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180059689  mov     [rbp+40h+var_B8], rax
0x18005968d  mov     [rbp+40h+var_B0], r13
0x180059691  mov     rax, [rcx]
0x180059694  lea     r9, [rbp+40h+pv]
0x180059698  mov     [rsp+140h+var_108], r9
0x18005969d  lea     r9, [rbp+40h+arg_10]
0x1800596a1  mov     [rsp+140h+var_110], r9
0x1800596a6  mov     [rsp+140h+var_118], r8d
0x1800596ab  mov     [rsp+140h+var_120], edx
0x1800596af  mov     r9, [rbp+40h+arg_18]
0x1800596b3  mov     r8d, r12d
0x1800596b6  mov     edx, r15d
0x1800596b9  mov     rax, [rax+30h]
0x1800596bd  call    cs:__guard_dispatch_icall_fptr
0x1800596c3  test    eax, eax
0x1800596c5  js      loc_18005998A
0x1800596cb  mov     ebx, dword ptr [rbp+40h+arg_10]
0x1800596ce  mov     [rsp+140h+var_F0], 7Eh ; '~'
0x1800596d6  mov     r15, [rbp+40h+pv]
0x1800596da  mov     qword ptr [rbp+40h+var_88], r15
0x1800596de  mov     dword ptr [rbp+40h+var_88+8], ebx
0x1800596e1  lea     rcx, [rbp+40h+arg_18]
0x1800596e5  call    ?Close@?$consume_Windows_Foundation_IClosable@UIBitmapBuffer@Imaging@Graphics@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IClosable<winrt::Windows::Graphics::Imaging::IBitmapBuffer>::Close(void)
0x1800596ea  nop
0x1800596eb  cmp     [rbp+40h+arg_18], 0
0x1800596f0  jz      short loc_1800596FC
0x1800596f2  lea     rcx, [rbp+40h+arg_18]
0x1800596f6  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800596fb  nop
0x1800596fc  lea     rcx, [rbp+40h+var_90]
0x180059700  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180059705  mov     [r14], r13
0x180059708  mov     [r14+8], r13
0x18005970c  mov     [r14+10h], r13
0x180059710  mov     [rsp+140h+var_F0], 7Fh
0x180059718  mov     rdi, rbx
0x18005971b  test    ebx, ebx
0x18005971d  jz      short loc_180059771
0x18005971f  mov     rax, 0AAAAAAAAAAAAAAAh
0x180059729  cmp     rbx, rax
0x18005972c  ja      loc_180059999
0x180059732  lfence
0x180059735  lea     rsi, [rbx+rbx*2]
0x180059739  shl     rsi, 3
0x18005973d  mov     rcx, rsi
0x180059740  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180059745  mov     rbx, rax
0x180059748  mov     rdx, [r14]; Src
0x18005974b  mov     r8, [r14+8]
0x18005974f  sub     r8, rdx; Size
0x180059752  mov     rcx, rax; void *
0x180059755  call    memmove
0x18005975a  mov     r9, rdi
0x18005975d  xor     r8d, r8d
0x180059760  mov     rdx, rbx
0x180059763  mov     rcx, r14
0x180059766  call    ?_Change_array@?$vector@UTokenText@SemanticRegistry@asg@@V?$allocator@UTokenText@SemanticRegistry@asg@@@std@@@std@@AEAAXQEAUTokenText@SemanticRegistry@asg@@_K1@Z; std::vector<asg::SemanticRegistry::TokenText>::_Change_array(asg::SemanticRegistry::TokenText * const,unsigned __int64,unsigned __int64)
0x18005976b  mov     r15, [rbp+40h+pv]
0x18005976f  jmp     short loc_180059779
0x180059771  lea     rsi, [rbx+rbx*2]
0x180059775  shl     rsi, 3
0x180059779  lea     rdi, [rsi+r15]
0x18005977d  cmp     r15, rdi
0x180059780  jz      loc_18005982E
0x180059786  lea     rbx, [r15+10h]
0x18005978a  nop     word ptr [rax+rax+00h]
0x180059790  mov     eax, [rbx]
0x180059792  mov     edx, eax
0x180059794  test    eax, eax
0x180059796  jz      short loc_1800597A6
0x180059798  sub     edx, 1
0x18005979b  jz      short loc_1800597A6
0x18005979d  cmp     edx, 1
0x1800597a0  jnz     loc_180059852
0x1800597a6  mov     ecx, [rbx-10h]
0x1800597a9  mov     dword ptr [rsp+140h+pExceptionObject], ecx
0x1800597ad  mov     ecx, [rbx-0Ch]
0x1800597b0  mov     dword ptr [rsp+140h+pExceptionObject+4], ecx
0x1800597b4  mov     rcx, [rbx-8]
0x1800597b8  mov     qword ptr [rsp+140h+pExceptionObject+8], rcx
0x1800597bd  test    eax, eax
0x1800597bf  jz      short loc_1800597DD
0x1800597c1  sub     eax, 1
0x1800597c4  jz      short loc_1800597D6
0x1800597c6  cmp     eax, 1
0x1800597c9  jnz     loc_18005989C
0x1800597cf  mov     eax, 2
0x1800597d4  jmp     short loc_1800597E0
0x1800597d6  mov     eax, 1
0x1800597db  jmp     short loc_1800597E0
0x1800597dd  mov     eax, r13d
0x1800597e0  mov     dword ptr [rsp+140h+var_D0], eax
0x1800597e4  movzx   eax, byte ptr [rbx+4]
0x1800597e8  mov     byte ptr [rsp+140h+var_D0+4], al
0x1800597ec  mov     rdx, [r14+8]
0x1800597f0  cmp     rdx, [r14+10h]
0x1800597f4  jz      short loc_180059810
0x1800597f6  movups  xmm0, [rsp+140h+pExceptionObject]
0x1800597fb  movups  xmmword ptr [rdx], xmm0
0x1800597fe  movsd   xmm1, [rsp+140h+var_D0]
0x180059804  movsd   qword ptr [rdx+10h], xmm1
0x180059809  add     qword ptr [r14+8], 18h
0x18005980e  jmp     short loc_18005981D
0x180059810  lea     r8, [rsp+140h+pExceptionObject]
0x180059815  mov     rcx, r14
0x180059818  call    ??$_Emplace_reallocate@UTokenText@SemanticRegistry@asg@@@?$vector@UTokenText@SemanticRegistry@asg@@V?$allocator@UTokenText@SemanticRegistry@asg@@@std@@@std@@AEAAPEAUTokenText@SemanticRegistry@asg@@QEAU234@$$QEAU234@@Z; std::vector<asg::SemanticRegistry::TokenText>::_Emplace_reallocate<asg::SemanticRegistry::TokenText>(asg::SemanticRegistry::TokenText * const,asg::SemanticRegistry::TokenText &&)
0x18005981d  add     rbx, 18h
0x180059821  lea     rax, [rbx-10h]
0x180059825  cmp     rax, rdi
0x180059828  jnz     loc_180059790
0x18005982e  test    r15, r15
0x180059831  jz      short loc_18005983B
0x180059833  mov     rcx, r15; pv
0x180059836  call    CoTaskMemFree_0
0x18005983b  mov     rax, r14
0x18005983e  add     rsp, 108h
0x180059845  pop     r15
0x180059847  pop     r14
0x180059849  pop     r13
0x18005984b  pop     r12
0x18005984d  pop     rdi
0x18005984e  pop     rsi
0x18005984f  pop     rbx
0x180059850  pop     rbp
0x180059851  retn
0x180059852  mov     [rbp+40h+var_C0], 6Bh ; 'k'
0x180059859  lea     rax, aCW1SSrcSemanti_36; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180059860  mov     [rbp+40h+var_B8], rax
0x180059864  mov     [rbp+40h+var_B0], r13
0x180059868  lea     rdx, aInvalidCharact; "invalid CharacterBreakType"
0x18005986f  lea     rcx, [rbp+40h+var_68]; this
0x180059873  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180059878  lea     r8, [rbp+40h+var_C0]; struct winrt::impl::slim_source_location *
0x18005987c  lea     rdx, [rbp+40h+var_68]; struct winrt::param::hstring *
0x180059880  lea     rcx, [rsp+140h+pExceptionObject]; this
0x180059885  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18005988a  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180059891  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x180059896  call    _CxxThrowException
0x18005989c  mov     [rbp+40h+var_C0], 40h ; '@'
0x1800598a3  lea     rax, aCW1SSrcSemanti_0; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x1800598aa  mov     [rbp+40h+var_B8], rax
0x1800598ae  mov     [rbp+40h+var_B0], r13
0x1800598b2  lea     rdx, aInvalidWinrtMi; "Invalid winrt::Microsoft::Asg::Semantic"...
0x1800598b9  lea     rcx, [rbp+40h+var_68]; this
0x1800598bd  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x1800598c2  lea     r8, [rbp+40h+var_C0]; struct winrt::impl::slim_source_location *
0x1800598c6  lea     rdx, [rbp+40h+var_68]; struct winrt::param::hstring *
0x1800598ca  lea     rcx, [rsp+140h+pExceptionObject]; this
0x1800598cf  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x1800598d4  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x1800598db  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x1800598e0  call    _CxxThrowException
0x1800598e6  mov     dword ptr [rsp+140h+pExceptionObject], 10Eh
0x1800598ee  lea     rax, aCW1SSrcSemanti_0; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x1800598f5  mov     qword ptr [rsp+140h+pExceptionObject+8], rax
0x1800598fa  mov     [rsp+140h+var_D0], rcx
0x1800598ff  lea     rdx, aTextHasTooMany; "text has too many characters to tokeniz"...
0x180059906  lea     rcx, [rbp+40h+var_88]; this
0x18005990a  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18005990f  lea     r8, [rsp+140h+pExceptionObject]; struct winrt::impl::slim_source_location *
0x180059914  lea     rdx, [rbp+40h+var_88]; struct winrt::param::hstring *
0x180059918  lea     rcx, [rbp+40h+var_C0]; this
0x18005991c  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180059921  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180059928  lea     rcx, [rbp+40h+var_C0]; pExceptionObject
0x18005992c  call    _CxxThrowException
0x180059932  lfence
0x180059935  lea     rdx, [rsp+140h+pExceptionObject]
0x18005993a  mov     ecx, eax
0x18005993c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180059942  mov     dword ptr [rbp+40h+pv], 30h ; '0'
0x180059949  lea     rax, aCW1SSrcSemanti_0; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180059950  mov     [rbp+40h+var_A0], rax
0x180059954  mov     [rbp+40h+var_98], rbx
0x180059958  lea     rdx, aInvalidAsgSema_0; "Invalid asg::SemanticRegistry::Tokenize"...
0x18005995f  lea     rcx, [rbp+40h+var_68]; this
0x180059963  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180059968  lea     r8, [rbp+40h+pv]; struct winrt::impl::slim_source_location *
0x18005996c  lea     rdx, [rbp+40h+var_68]; struct winrt::param::hstring *
0x180059970  lea     rcx, [rbp+40h+var_C0]; this
0x180059974  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
  ... truncated ...
```
