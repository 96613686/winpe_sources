# winrt::Microsoft::Windows::SemanticSearch::implementation::QueryResult::Matches(void)

- ea: `0x18001f1c0`
- end: `0x18001f5bd`
- name: `?Matches@QueryResult@implementation@SemanticSearch@Windows@Microsoft@winrt@@QEBA?AU?$IVectorView@UItemQueryMatch@SemanticSearch@Windows@Microsoft@winrt@@@Collections@Foundation@46@XZ`
- size: `1021`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180026c70`

## callees

- `0x180002bb0`
- `0x180008840`
- `0x180009580`
- `0x18001f1c0`
- `0x18001f5c0`
- `0x18002c1f0`
- `0x18002e150`
- `0x18004c070`
- `0x18004c090`
- `0x18004c8cc`
- `0x18005e260`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001f548`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001f548`

## string_xrefs

- `0x18001f212`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
char **__fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::QueryResult::Matches(
        __int64 a1,
        char **a2)
{
  int v4; // eax
  unsigned __int64 v5; // rdi
  signed __int64 v6; // rbx
  _QWORD *v7; // r11
  __int64 *v8; // rcx
  __int64 *v9; // r10
  _QWORD *i; // rdx
  __int64 v11; // rax
  int v12; // eax
  int v13; // edi
  unsigned int v14; // esi
  int v15; // r14d
  char *v16; // rbx
  int v17; // edi
  int v18; // eax
  unsigned int v19; // edi
  _QWORD *v20; // rcx
  __int64 v21; // rax
  char *v22; // rax
  _QWORD *v23; // r8
  char *v24; // rbx
  _BYTE *v25; // rdx
  void *v26; // rcx
  void *v27; // rax
  int v28; // eax
  char *v29; // rbx
  char *v30; // rdi
  char *v31; // rax
  char *v33; // [rsp+30h] [rbp-39h] BYREF
  const char *v34; // [rsp+38h] [rbp-31h]
  unsigned int v35; // [rsp+40h] [rbp-29h]
  int v36; // [rsp+48h] [rbp-21h] BYREF
  const char *v37; // [rsp+50h] [rbp-19h]
  char *v38; // [rsp+58h] [rbp-11h] BYREF
  void *v39[2]; // [rsp+60h] [rbp-9h] BYREF
  _BYTE *v40; // [rsp+70h] [rbp+7h]
  __int64 v41; // [rsp+78h] [rbp+Fh] BYREF

  v35 = 0;
  *(_OWORD *)v39 = 0;
  v40 = 0;
  v38 = 0;
  LODWORD(v33) = 478;
  v34 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\Mi"
        "crosoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v4 = (*(__int64 (__fastcall **)(_QWORD, char **))(**(_QWORD **)(a1 + 24) + 72LL))(*(_QWORD *)(a1 + 24), &v38);
  if ( v4 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v4, &v33);
  }
  v33 = v38;
  v5 = (unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemQueryMatch>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemQueryMatch>::Size(&v33);
  if ( v5 > (v40 - (char *)v39[0]) >> 3 )
  {
    v6 = ((char *)v39[1] - (char *)v39[0]) >> 3;
    _mm_lfence();
    v7 = std::_Allocate<16,std::_Default_allocate_traits>(8 * v5);
    v8 = (__int64 *)v39[0];
    v9 = (__int64 *)v39[1];
    for ( i = v7; v8 != v9; ++v8 )
    {
      v11 = *v8;
      *v8 = 0;
      *i++ = v11;
    }
    std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>::_Change_array(v39, v7, v6, v5);
  }
  if ( v33 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v33);
  v38 = 0;
  LODWORD(v33) = 478;
  v34 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\Mi"
        "crosoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v12 = (*(__int64 (__fastcall **)(_QWORD, char **))(**(_QWORD **)(a1 + 24) + 72LL))(*(_QWORD *)(a1 + 24), &v38);
  if ( v12 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v12, &v33);
  }
  v13 = 384;
  v14 = 0;
  v15 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemQueryMatch>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemQueryMatch>::Size(&v38);
  v16 = v38;
  if ( v15 )
  {
    do
    {
      v41 = 0;
      v17 = v13 | 4;
      v35 = v17;
      v36 = 171;
      v37 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt"
            "\\Windows.Foundation.Collections.h";
      v18 = (*(__int64 (__fastcall **)(char *, _QWORD, __int64 *))(*(_QWORD *)v16 + 48LL))(v16, v14, &v41);
      if ( v18 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v18, &v36);
      }
      v19 = v17 & 0xFFFFFFF9 | 2;
      v35 = v19;
      v20 = operator new(0x20u);
      v20[2] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::ItemQueryMatch,winrt::Microsoft::Windows::SemanticSearch::IItemQueryMatch>::`vftable';
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      v20[1] = 1;
      *v20 = &winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::ItemQueryMatch>::`vftable';
      v21 = v41;
      v41 = 0;
      v20[3] = v21;
      *v20 = &winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::ItemQueryMatch>::`vftable';
      v33 = (char *)(v20 + 2);
      v13 = v19 | 8;
      if ( v39[1] == v40 )
      {
        std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>::_Emplace_reallocate<winrt::Microsoft::Windows::SemanticSearch::Embedding>(
          v39,
          v39[1],
          &v33);
        v22 = v33;
      }
      else
      {
        v22 = 0;
        v33 = 0;
        *(_QWORD *)v39[1] = v20 + 2;
        v39[1] = (char *)v39[1] + 8;
      }
      if ( v22 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v33);
      if ( v41 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v41);
      ++v14;
    }
    while ( v14 != v15 );
  }
  if ( v16 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v38);
  v23 = operator new(0x48u);
  v24 = (char *)(v23 + 2);
  v23[2] = &winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Microsoft::Windows::SemanticSearch::Embedding>>::`vftable';
  v23[3] = &winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Microsoft::Windows::SemanticSearch::Embedding>>::`vftable';
  v23[4] = &winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::ItemQueryMatch,std::vector<winrt::Microsoft::Windows::SemanticSearch::ItemQueryMatch>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::Microsoft::Windows::SemanticSearch::ItemQueryMatch>>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v23[1] = 1;
  *((_DWORD *)v23 + 10) = 0;
  *v23 = &winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::ItemQueryMatch,std::vector<winrt::Microsoft::Windows::SemanticSearch::ItemQueryMatch>,winrt::impl::single_threaded_collection_base>::`vftable';
  v25 = v40;
  v40 = 0;
  v26 = v39[1];
  v39[1] = 0;
  v27 = v39[0];
  v39[0] = 0;
  v23[6] = v27;
  v23[7] = v26;
  v23[8] = v25;
  *v23 = &winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::ItemQueryMatch,std::vector<winrt::Microsoft::Windows::SemanticSearch::ItemQueryMatch>,winrt::impl::single_threaded_collection_base>::`vftable';
  v33 = v24;
  v38 = 0;
  v36 = 207;
  v37 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\Wi"
        "ndows.Foundation.Collections.h";
  v28 = (*(__int64 (__fastcall **)(char *, char **))(*(_QWORD *)v24 + 64LL))(v24, &v38);
  if ( v28 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v28, &v36);
  }
  *a2 = v38;
  if ( v24 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v33);
  v29 = (char *)v39[0];
  if ( v39[0] )
  {
    v30 = (char *)v39[1];
    if ( v39[0] != v39[1] )
    {
      do
      {
        if ( *(_QWORD *)v29 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v29);
        v29 += 8;
      }
      while ( v29 != v30 );
      v29 = (char *)v39[0];
    }
    v31 = v29;
    if ( ((v40 - v29) & 0xFFFFFFFFFFFFFFF8uLL) >= 0x1000 )
    {
      v29 = (char *)*((_QWORD *)v29 - 1);
      if ( (unsigned __int64)(v31 - v29 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    operator delete(v29);
  }
  return a2;
}

```

## disassembly

```asm
0x18001f1c0  mov     [rsp-8+arg_10], rbx
0x18001f1c5  push    rbp
0x18001f1c6  push    rsi
0x18001f1c7  push    rdi
0x18001f1c8  push    r12
0x18001f1ca  push    r13
0x18001f1cc  push    r14
0x18001f1ce  push    r15
0x18001f1d0  lea     rbp, [rsp-27h]
0x18001f1d5  sub     rsp, 90h
0x18001f1dc  mov     rax, cs:__security_cookie
0x18001f1e3  xor     rax, rsp
0x18001f1e6  mov     [rbp+57h+var_40], rax
0x18001f1ea  mov     r15, rdx
0x18001f1ed  mov     rsi, rcx
0x18001f1f0  mov     [rbp+57h+var_68], rdx
0x18001f1f4  xor     r12d, r12d
0x18001f1f7  mov     [rbp+57h+var_80], r12d
0x18001f1fb  xorps   xmm1, xmm1
0x18001f1fe  movdqu  xmmword ptr [rbp+57h+var_60], xmm1
0x18001f203  mov     [rbp+57h+var_50], r12
0x18001f207  mov     [rbp+57h+var_68], r12
0x18001f20b  mov     dword ptr [rbp+57h+var_90], 1DEh
0x18001f212  lea     r14, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18001f219  mov     [rbp+57h+var_88], r14
0x18001f21d  mov     rcx, [rcx+18h]
0x18001f221  mov     rax, [rcx]
0x18001f224  lea     rdx, [rbp+57h+var_68]
0x18001f228  mov     rax, [rax+48h]
0x18001f22c  call    cs:__guard_dispatch_icall_fptr
0x18001f232  test    eax, eax
0x18001f234  js      loc_18001F590
0x18001f23a  mov     rax, [rbp+57h+var_68]
0x18001f23e  mov     [rbp+57h+var_90], rax
0x18001f242  lea     rcx, [rbp+57h+var_90]
0x18001f246  call    ?Size@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@UItemQueryMatch@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Collections@Foundation@Windows@winrt@@UItemQueryMatch@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@5@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemQueryMatch>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemQueryMatch>::Size(void)
0x18001f24b  mov     edi, eax
0x18001f24d  mov     rax, [rbp+57h+var_50]
0x18001f251  mov     rcx, [rbp+57h+var_60]
0x18001f255  sub     rax, rcx
0x18001f258  sar     rax, 3
0x18001f25c  cmp     rdi, rax
0x18001f25f  jbe     short loc_18001F2B9
0x18001f261  mov     rbx, [rbp+57h+var_60+8]
0x18001f265  sub     rbx, rcx
0x18001f268  sar     rbx, 3
0x18001f26c  lfence
0x18001f26f  lea     rcx, ds:0[rdi*8]
0x18001f277  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001f27c  mov     r11, rax
0x18001f27f  mov     rcx, [rbp+57h+var_60]
0x18001f283  mov     r10, [rbp+57h+var_60+8]
0x18001f287  mov     rdx, rax
0x18001f28a  cmp     rcx, r10
0x18001f28d  jz      short loc_18001F2A6
0x18001f28f  nop
0x18001f290  mov     rax, [rcx]
0x18001f293  mov     [rcx], r12
0x18001f296  mov     [rdx], rax
0x18001f299  lea     rdx, [rdx+8]
0x18001f29d  add     rcx, 8
0x18001f2a1  cmp     rcx, r10
0x18001f2a4  jnz     short loc_18001F290
0x18001f2a6  mov     r9, rdi
0x18001f2a9  mov     r8, rbx
0x18001f2ac  mov     rdx, r11
0x18001f2af  lea     rcx, [rbp+57h+var_60]
0x18001f2b3  call    ?_Change_array@?$vector@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@AEAAXQEAUEmbedding@SemanticSearch@Windows@Microsoft@winrt@@_K1@Z; std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>::_Change_array(winrt::Microsoft::Windows::SemanticSearch::Embedding * const,unsigned __int64,unsigned __int64)
0x18001f2b8  nop
0x18001f2b9  cmp     [rbp+57h+var_90], 0
0x18001f2be  jz      short loc_18001F2C9
0x18001f2c0  lea     rcx, [rbp+57h+var_90]
0x18001f2c4  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18001f2c9  mov     [rbp+57h+var_68], r12
0x18001f2cd  mov     dword ptr [rbp+57h+var_90], 1DEh
0x18001f2d4  mov     [rbp+57h+var_88], r14
0x18001f2d8  mov     rcx, [rsi+18h]
0x18001f2dc  mov     rax, [rcx]
0x18001f2df  lea     rdx, [rbp+57h+var_68]
0x18001f2e3  mov     rax, [rax+48h]
0x18001f2e7  call    cs:__guard_dispatch_icall_fptr
0x18001f2ed  test    eax, eax
0x18001f2ef  js      loc_18001F59F
0x18001f2f5  mov     rax, [rbp+57h+var_68]
0x18001f2f9  mov     [rbp+57h+var_68], rax
0x18001f2fd  mov     edi, 180h
0x18001f302  mov     esi, r12d
0x18001f305  lea     rcx, [rbp+57h+var_68]
0x18001f309  call    ?Size@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@UItemQueryMatch@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Collections@Foundation@Windows@winrt@@UItemQueryMatch@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@5@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemQueryMatch>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemQueryMatch>::Size(void)
0x18001f30e  mov     r14d, eax
0x18001f311  lea     r13, aCW1SProductApi_15; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18001f318  mov     rbx, [rbp+57h+var_68]
0x18001f31c  test    eax, eax
0x18001f31e  jz      loc_18001F40B
0x18001f324  mov     [rbp+57h+var_48], r12
0x18001f328  or      edi, 4
0x18001f32b  mov     [rbp+57h+var_80], edi
0x18001f32e  mov     [rbp+57h+var_78], 0ABh
0x18001f335  mov     [rbp+57h+var_70], r13
0x18001f339  mov     rax, [rbx]
0x18001f33c  lea     r8, [rbp+57h+var_48]
0x18001f340  mov     edx, esi
0x18001f342  mov     rcx, rbx
0x18001f345  mov     rax, [rax+30h]
0x18001f349  call    cs:__guard_dispatch_icall_fptr
0x18001f34f  test    eax, eax
0x18001f351  js      loc_18001F581
0x18001f357  and     edi, 0FFFFFFFBh
0x18001f35a  or      edi, 2
0x18001f35d  mov     [rbp+57h+var_80], edi
0x18001f360  mov     ecx, 20h ; ' '; Size
0x18001f365  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f36a  mov     rcx, rax
0x18001f36d  mov     [rbp+57h+var_90], rax
0x18001f371  lea     r8, [rax+10h]
0x18001f375  lea     rax, ??_7?$produce@UItemQueryMatch@implementation@SemanticSearch@Windows@Microsoft@winrt@@UIItemQueryMatch@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::ItemQueryMatch,winrt::Microsoft::Windows::SemanticSearch::IItemQueryMatch>::`vftable'
0x18001f37c  mov     [r8], rax
0x18001f37f  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001f386  mov     qword ptr [rcx+8], 1
0x18001f38e  lea     rax, ??_7?$heap_implements@UItemQueryMatch@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::ItemQueryMatch>::`vftable'
0x18001f395  mov     [rcx], rax
0x18001f398  mov     rax, [rbp+57h+var_48]
0x18001f39c  mov     [rbp+57h+var_48], r12
0x18001f3a0  mov     [rcx+18h], rax
0x18001f3a4  lea     rax, ??_7?$heap_implements@UItemQueryMatch@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::ItemQueryMatch>::`vftable'
0x18001f3ab  mov     [rcx], rax
0x18001f3ae  mov     [rbp+57h+var_90], r8
0x18001f3b2  or      edi, 8
0x18001f3b5  mov     rdx, [rbp+57h+var_60+8]
0x18001f3b9  cmp     rdx, [rbp+57h+var_50]
0x18001f3bd  jz      short loc_18001F3D0
0x18001f3bf  mov     rax, r12
0x18001f3c2  mov     [rbp+57h+var_90], rax
0x18001f3c6  mov     [rdx], r8
0x18001f3c9  add     [rbp+57h+var_60+8], 8
0x18001f3ce  jmp     short loc_18001F3E1
0x18001f3d0  lea     r8, [rbp+57h+var_90]
0x18001f3d4  lea     rcx, [rbp+57h+var_60]
0x18001f3d8  call    ??$_Emplace_reallocate@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@?$vector@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@AEAAPEAUEmbedding@SemanticSearch@Windows@Microsoft@winrt@@QEAU23456@$$QEAU23456@@Z; std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>::_Emplace_reallocate<winrt::Microsoft::Windows::SemanticSearch::Embedding>(winrt::Microsoft::Windows::SemanticSearch::Embedding * const,winrt::Microsoft::Windows::SemanticSearch::Embedding &&)
0x18001f3dd  mov     rax, [rbp+57h+var_90]
0x18001f3e1  test    rax, rax
0x18001f3e4  jz      short loc_18001F3F0
0x18001f3e6  lea     rcx, [rbp+57h+var_90]
0x18001f3ea  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18001f3ef  nop
0x18001f3f0  cmp     [rbp+57h+var_48], 0
0x18001f3f5  jz      short loc_18001F400
0x18001f3f7  lea     rcx, [rbp+57h+var_48]
0x18001f3fb  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18001f400  inc     esi
0x18001f402  cmp     esi, r14d
0x18001f405  jnz     loc_18001F324
0x18001f40b  test    rbx, rbx
0x18001f40e  jz      short loc_18001F419
0x18001f410  lea     rcx, [rbp+57h+var_68]
0x18001f414  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18001f419  mov     ecx, 48h ; 'H'; Size
0x18001f41e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f423  mov     r8, rax
0x18001f426  mov     [rbp+57h+var_68], rax
0x18001f42a  lea     rbx, [rax+10h]
0x18001f42e  lea     rax, ??_7?$produce@U?$vector_impl@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$vector@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Microsoft::Windows::SemanticSearch::Embedding>>::`vftable'
0x18001f435  mov     [rbx], rax
0x18001f438  lea     rax, ??_7?$produce@U?$vector_impl@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$vector@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVectorView@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Microsoft::Windows::SemanticSearch::Embedding>>::`vftable'
0x18001f43f  mov     [rbx+8], rax
0x18001f443  lea     rax, ??_7?$produce@U?$vector_impl@UItemQueryMatch@SemanticSearch@Windows@Microsoft@winrt@@V?$vector@UItemQueryMatch@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UItemQueryMatch@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IIterable@UItemQueryMatch@SemanticSearch@Windows@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::ItemQueryMatch,std::vector<winrt::Microsoft::Windows::SemanticSearch::ItemQueryMatch>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::Microsoft::Windows::SemanticSearch::ItemQueryMatch>>::`vftable'
0x18001f44a  mov     [rbx+10h], rax
0x18001f44e  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001f455  mov     qword ptr [r8+8], 1
0x18001f45d  xor     eax, eax
0x18001f45f  mov     [r8+28h], eax
0x18001f463  lea     rax, ??_7?$vector_impl@UItemQueryMatch@SemanticSearch@Windows@Microsoft@winrt@@V?$vector@UItemQueryMatch@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UItemQueryMatch@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@6B@; const winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::ItemQueryMatch,std::vector<winrt::Microsoft::Windows::SemanticSearch::ItemQueryMatch>,winrt::impl::single_threaded_collection_base>::`vftable'
0x18001f46a  mov     [r8], rax
0x18001f46d  mov     rdx, [rbp+57h+var_50]
0x18001f471  mov     [rbp+57h+var_50], r12
0x18001f475  mov     rcx, [rbp+57h+var_60+8]
0x18001f479  mov     [rbp+57h+var_60+8], r12
0x18001f47d  mov     rax, [rbp+57h+var_60]
0x18001f481  mov     [rbp+57h+var_60], r12
0x18001f485  mov     [r8+30h], rax
0x18001f489  mov     [r8+38h], rcx
0x18001f48d  mov     [r8+40h], rdx
0x18001f491  lea     rax, ??_7?$vector_impl@UItemQueryMatch@SemanticSearch@Windows@Microsoft@winrt@@V?$vector@UItemQueryMatch@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UItemQueryMatch@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@6B@; const winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::ItemQueryMatch,std::vector<winrt::Microsoft::Windows::SemanticSearch::ItemQueryMatch>,winrt::impl::single_threaded_collection_base>::`vftable'
0x18001f498  mov     [r8], rax
0x18001f49b  mov     [rbp+57h+var_90], rbx
0x18001f49f  mov     [rbp+57h+var_68], r12
0x18001f4a3  mov     [rbp+57h+var_78], 0CFh
0x18001f4aa  mov     [rbp+57h+var_70], r13
0x18001f4ae  mov     rax, [rbx]
0x18001f4b1  lea     rdx, [rbp+57h+var_68]
0x18001f4b5  mov     rcx, rbx
0x18001f4b8  mov     rax, [rax+40h]
0x18001f4bc  call    cs:__guard_dispatch_icall_fptr
0x18001f4c2  test    eax, eax
0x18001f4c4  js      loc_18001F5AE
0x18001f4ca  mov     rax, [rbp+57h+var_68]
0x18001f4ce  mov     [r15], rax
0x18001f4d1  test    rbx, rbx
0x18001f4d4  jz      short loc_18001F4E0
0x18001f4d6  lea     rcx, [rbp+57h+var_90]
0x18001f4da  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18001f4df  nop
0x18001f4e0  mov     rbx, [rbp+57h+var_60]
0x18001f4e4  test    rbx, rbx
0x18001f4e7  jz      short loc_18001F557
0x18001f4e9  mov     rdi, [rbp+57h+var_60+8]
0x18001f4ed  cmp     rbx, rdi
0x18001f4f0  jz      short loc_18001F50D
0x18001f4f2  cmp     qword ptr [rbx], 0
0x18001f4f6  jz      short loc_18001F500
0x18001f4f8  mov     rcx, rbx
0x18001f4fb  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18001f500  add     rbx, 8
0x18001f504  cmp     rbx, rdi
0x18001f507  jnz     short loc_18001F4F2
0x18001f509  mov     rbx, [rbp+57h+var_60]
0x18001f50d  mov     rdx, [rbp+57h+var_50]
0x18001f511  sub     rdx, rbx
0x18001f514  and     rdx, 0FFFFFFFFFFFFFFF8h; unsigned __int64
0x18001f518  mov     rax, rbx
0x18001f51b  cmp     rdx, 1000h
0x18001f522  jb      short loc_18001F54F
0x18001f524  add     rdx, 27h ; '''
0x18001f528  mov     rbx, [rbx-8]
0x18001f52c  sub     rax, rbx
0x18001f52f  sub     rax, 8
0x18001f533  cmp     rax, 1Fh
0x18001f537  jbe     short loc_18001F54F
0x18001f539  mov     [rsp+0C0h+Reserved], r12; Reserved
0x18001f53e  xor     r9d, r9d; LineNo
0x18001f541  xor     r8d, r8d; FileName
0x18001f544  xor     edx, edx; FunctionName
0x18001f546  xor     ecx, ecx; Expression
0x18001f548  call    cs:__imp__invoke_watson
0x18001f54f  mov     rcx, rbx; void *
0x18001f552  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f557  mov     rax, r15
0x18001f55a  mov     rcx, [rbp+57h+var_40]
0x18001f55e  xor     rcx, rsp; StackCookie
0x18001f561  call    __security_check_cookie
0x18001f566  mov     rbx, [rsp+0C0h+arg_10]
0x18001f56e  add     rsp, 90h
0x18001f575  pop     r15
0x18001f577  pop     r14
0x18001f579  pop     r13
0x18001f57b  pop     r12
0x18001f57d  pop     rdi
0x18001f57e  pop     rsi
0x18001f57f  pop     rbp
0x18001f580  retn
0x18001f581  lfence
0x18001f584  lea     rdx, [rbp+57h+var_78]
0x18001f588  mov     ecx, eax
0x18001f58a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001f590  lfence
0x18001f593  lea     rdx, [rbp+57h+var_90]
0x18001f597  mov     ecx, eax
0x18001f599  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001f59f  lfence
0x18001f5a2  lea     rdx, [rbp+57h+var_90]
0x18001f5a6  mov     ecx, eax
0x18001f5a8  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001f5ae  lfence
0x18001f5b1  lea     rdx, [rbp+57h+var_78]
0x18001f5b5  mov     ecx, eax
0x18001f5b7  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
