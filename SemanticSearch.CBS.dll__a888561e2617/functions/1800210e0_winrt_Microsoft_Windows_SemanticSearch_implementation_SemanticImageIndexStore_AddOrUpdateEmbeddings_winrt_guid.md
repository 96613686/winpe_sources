# winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore::AddOrUpdateEmbeddings(winrt::guid const &,winrt::array_view<winrt::Microsoft::Windows::SemanticSearch::Embedding const>)

- ea: `0x1800210e0`
- end: `0x180021315`
- name: `?AddOrUpdateEmbeddings@SemanticImageIndexStore@implementation@SemanticSearch@Windows@Microsoft@winrt@@QEAA?AUAddOrUpdateEmbeddingsResult@3456@AEBUguid@6@U?$array_view@$$CBUEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@6@@Z`
- size: `565`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int128 *, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800258b0`

## callees

- `0x180002bb0`
- `0x180002ec0`
- `0x180009580`
- `0x1800210e0`
- `0x1800228e0`
- `0x18002bfe0`
- `0x18004c070`
- `0x18004c090`
- `0x18004c8cc`
- `0x18005e260`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800212d6`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800212d6`

## string_xrefs

- `0x1800211a3`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore::AddOrUpdateEmbeddings(
        __int64 a1,
        _QWORD *a2,
        __int128 *a3,
        __int64 *a4)
{
  __int64 v4; // rdi
  __int64 v8; // rbx
  __int64 i; // rbx
  __int64 *v10; // rax
  __int64 v11; // rax
  void *v12; // rdi
  signed __int64 v13; // rbx
  void (__fastcall ***v14)(_QWORD, __int64 *, _QWORD **); // rcx
  _QWORD *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // r9
  int v18; // eax
  _QWORD *v19; // rax
  char *v20; // rbx
  char *v21; // rdi
  char *v22; // rax
  int v24; // [rsp+38h] [rbp-31h] BYREF
  const char *v25; // [rsp+40h] [rbp-29h]
  __int128 v26; // [rsp+50h] [rbp-19h] BYREF
  _QWORD *v27; // [rsp+60h] [rbp-9h] BYREF
  _QWORD *v28; // [rsp+68h] [rbp-1h] BYREF
  void *v29[2]; // [rsp+70h] [rbp+7h] BYREF
  _BYTE *v30; // [rsp+80h] [rbp+17h]

  v4 = *a4;
  v27 = a2;
  *(_OWORD *)v29 = 0;
  v30 = 0;
  v8 = *((unsigned int *)a4 + 2);
  std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>::reserve(v29, v8);
  for ( i = v4 + 8 * v8; v4 != i; v4 += 8 )
  {
    v10 = (__int64 *)winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl<winrt::Microsoft::Windows::SemanticSearch::implementation::Embedding,winrt::Microsoft::Windows::SemanticSearch::Embedding>(v4);
    if ( v29[1] == v30 )
    {
      std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>::_Emplace_reallocate<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding const &>(
        (__int64 **)v29,
        (__int64 *)v29[1],
        v10);
    }
    else
    {
      v11 = *v10;
      *(_QWORD *)v29[1] = v11;
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
      v29[1] = (char *)v29[1] + 8;
    }
  }
  v12 = v29[0];
  v13 = ((char *)v29[1] - (char *)v29[0]) >> 3;
  v28 = 0;
  v24 = 860;
  v25 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\Mi"
        "crosoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v14 = *(void (__fastcall ****)(_QWORD, __int64 *, _QWORD **))(a1 + 104);
  if ( v14 )
  {
    v27 = 0;
    (**v14)(
      v14,
      winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex>,
      &v27);
    v15 = v27;
  }
  else
  {
    v15 = 0;
  }
  v27 = v15;
  v16 = *v15;
  v17 = 8;
  if ( (_DWORD)v13 )
    v17 = (__int64)v12;
  v26 = *a3;
  v18 = (*(__int64 (__fastcall **)(_QWORD *, __int128 *, _QWORD, __int64, _QWORD **))(v16 + 120))(
          v15,
          &v26,
          (unsigned int)v13,
          v17,
          &v28);
  if ( v18 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v18, &v24);
  }
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v27);
  v27 = v28;
  v19 = operator new(0x20u);
  v27 = v19;
  v19[2] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::AddOrUpdateEmbeddingsResult,winrt::Microsoft::Windows::SemanticSearch::IAddOrUpdateEmbeddingsResult>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v19[1] = 1;
  v19[3] = v28;
  *v19 = &winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::AddOrUpdateEmbeddingsResult>::`vftable';
  *a2 = v19 + 2;
  v20 = (char *)v29[0];
  if ( v29[0] )
  {
    v21 = (char *)v29[1];
    if ( v29[0] != v29[1] )
    {
      do
      {
        if ( *(_QWORD *)v20 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v20);
        v20 += 8;
      }
      while ( v20 != v21 );
      v20 = (char *)v29[0];
    }
    v22 = v20;
    if ( ((v30 - v20) & 0xFFFFFFFFFFFFFFF8uLL) >= 0x1000 )
    {
      v20 = (char *)*((_QWORD *)v20 - 1);
      if ( (unsigned __int64)(v22 - v20 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    operator delete(v20);
  }
  return a2;
}

```

## disassembly

```asm
0x1800210e0  push    rbp
0x1800210e2  push    rbx
0x1800210e3  push    rsi
0x1800210e4  push    rdi
0x1800210e5  push    r12
0x1800210e7  push    r14
0x1800210e9  push    r15
0x1800210eb  lea     rbp, [rsp-27h]
0x1800210f0  sub     rsp, 90h
0x1800210f7  mov     rax, cs:__security_cookie
0x1800210fe  xor     rax, rsp
0x180021101  mov     [rbp+57h+var_38], rax
0x180021105  mov     rdi, [r9]
0x180021108  mov     r15, r8
0x18002110b  mov     rsi, rdx
0x18002110e  mov     r14, rcx
0x180021111  mov     [rbp+57h+var_60], rdx
0x180021115  xor     r12d, r12d
0x180021118  xorps   xmm1, xmm1
0x18002111b  movdqu  xmmword ptr [rbp+57h+var_50], xmm1
0x180021120  mov     [rbp+57h+var_40], r12
0x180021124  mov     ebx, [r9+8]
0x180021128  mov     edx, ebx
0x18002112a  lea     rcx, [rbp+57h+var_50]
0x18002112e  call    ?reserve@?$vector@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@QEAAX_K@Z; std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>::reserve(unsigned __int64)
0x180021133  lea     rbx, [rdi+rbx*8]
0x180021137  cmp     rdi, rbx
0x18002113a  jz      short loc_180021189
0x18002113c  nop     dword ptr [rax+00h]
0x180021140  mov     rcx, rdi
0x180021143  call    ??$GetAsgImpl@UEmbedding@implementation@SemanticSearch@Windows@Microsoft@winrt@@U13456@@implementation@SemanticSearch@Windows@Microsoft@winrt@@YAAEB_PAEBUEmbedding@1234@@Z
0x180021148  mov     rdx, [rbp+57h+var_50+8]
0x18002114c  cmp     rdx, [rbp+57h+var_40]
0x180021150  jz      short loc_180021174
0x180021152  mov     rax, [rax]
0x180021155  mov     [rdx], rax
0x180021158  mov     rcx, rax
0x18002115b  test    rax, rax
0x18002115e  jz      short loc_18002116D
0x180021160  mov     rax, [rax]
0x180021163  mov     rax, [rax+8]
0x180021167  call    cs:__guard_dispatch_icall_fptr
0x18002116d  add     [rbp+57h+var_50+8], 8
0x180021172  jmp     short loc_180021180
0x180021174  mov     r8, rax
0x180021177  lea     rcx, [rbp+57h+var_50]
0x18002117b  call    ??$_Emplace_reallocate@AEBUEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@?$vector@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@AEAAPEAUEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAU2345678@AEBU2345678@@Z; std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>::_Emplace_reallocate<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding const &>(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding * const,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding const &)
0x180021180  add     rdi, 8
0x180021184  cmp     rdi, rbx
0x180021187  jnz     short loc_180021140
0x180021189  mov     rbx, [rbp+57h+var_50+8]
0x18002118d  mov     rdi, [rbp+57h+var_50]
0x180021191  sub     rbx, rdi
0x180021194  sar     rbx, 3
0x180021198  mov     [rbp+57h+var_58], r12
0x18002119c  mov     [rbp+57h+var_88], 35Ch
0x1800211a3  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x1800211aa  mov     [rbp+57h+var_80], rax
0x1800211ae  mov     rcx, [r14+68h]
0x1800211b2  test    rcx, rcx
0x1800211b5  jnz     short loc_1800211BC
0x1800211b7  mov     rcx, r12
0x1800211ba  jmp     short loc_1800211DB
0x1800211bc  mov     [rbp+57h+var_60], r12
0x1800211c0  mov     rax, [rcx]
0x1800211c3  lea     r8, [rbp+57h+var_60]
0x1800211c7  lea     rdx, ??$guid_v@UISemanticIndex@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex>
0x1800211ce  mov     rax, [rax]
0x1800211d1  call    cs:__guard_dispatch_icall_fptr
0x1800211d7  mov     rcx, [rbp+57h+var_60]
0x1800211db  mov     [rbp+57h+var_60], rcx
0x1800211df  mov     rax, [rcx]
0x1800211e2  mov     r9d, 8
0x1800211e8  test    ebx, ebx
0x1800211ea  cmovnz  r9, rdi
0x1800211ee  movups  xmm0, xmmword ptr [r15]
0x1800211f2  movaps  [rbp+57h+var_70], xmm0
0x1800211f6  lea     rdx, [rbp+57h+var_58]
0x1800211fa  mov     [rsp+0C0h+Reserved], rdx
0x1800211ff  mov     r8d, ebx
0x180021202  lea     rdx, [rbp+57h+var_70]
0x180021206  mov     rax, [rax+78h]
0x18002120a  call    cs:__guard_dispatch_icall_fptr
0x180021210  test    eax, eax
0x180021212  js      loc_180021306
0x180021218  lea     rcx, [rbp+57h+var_60]
0x18002121c  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180021221  mov     rax, [rbp+57h+var_58]
0x180021225  mov     [rbp+57h+var_60], rax
0x180021229  mov     ecx, 20h ; ' '; Size
0x18002122e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021233  mov     rdx, rax
0x180021236  mov     [rbp+57h+var_60], rax
0x18002123a  lea     rcx, [rax+10h]
0x18002123e  lea     rax, ??_7?$produce@UAddOrUpdateEmbeddingsResult@implementation@SemanticSearch@Windows@Microsoft@winrt@@UIAddOrUpdateEmbeddingsResult@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::AddOrUpdateEmbeddingsResult,winrt::Microsoft::Windows::SemanticSearch::IAddOrUpdateEmbeddingsResult>::`vftable'
0x180021245  mov     [rcx], rax
0x180021248  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18002124f  mov     qword ptr [rdx+8], 1
0x180021257  mov     rax, [rbp+57h+var_58]
0x18002125b  mov     [rdx+18h], rax
0x18002125f  lea     rax, ??_7?$heap_implements@UAddOrUpdateEmbeddingsResult@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::AddOrUpdateEmbeddingsResult>::`vftable'
0x180021266  mov     [rdx], rax
0x180021269  mov     [rsi], rcx
0x18002126c  mov     rbx, [rbp+57h+var_50]
0x180021270  test    rbx, rbx
0x180021273  jz      short loc_1800212E5
0x180021275  mov     rdi, [rbp+57h+var_50+8]
0x180021279  cmp     rbx, rdi
0x18002127c  jz      short loc_18002129B
0x18002127e  xchg    ax, ax
0x180021280  cmp     qword ptr [rbx], 0
0x180021284  jz      short loc_18002128E
0x180021286  mov     rcx, rbx
0x180021289  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18002128e  add     rbx, 8
0x180021292  cmp     rbx, rdi
0x180021295  jnz     short loc_180021280
0x180021297  mov     rbx, [rbp+57h+var_50]
0x18002129b  mov     rdx, [rbp+57h+var_40]
0x18002129f  sub     rdx, rbx
0x1800212a2  and     rdx, 0FFFFFFFFFFFFFFF8h; unsigned __int64
0x1800212a6  mov     rax, rbx
0x1800212a9  cmp     rdx, 1000h
0x1800212b0  jb      short loc_1800212DD
0x1800212b2  add     rdx, 27h ; '''
0x1800212b6  mov     rbx, [rbx-8]
0x1800212ba  sub     rax, rbx
0x1800212bd  sub     rax, 8
0x1800212c1  cmp     rax, 1Fh
0x1800212c5  jbe     short loc_1800212DD
0x1800212c7  mov     [rsp+0C0h+Reserved], r12; Reserved
0x1800212cc  xor     r9d, r9d; LineNo
0x1800212cf  xor     r8d, r8d; FileName
0x1800212d2  xor     edx, edx; FunctionName
0x1800212d4  xor     ecx, ecx; Expression
0x1800212d6  call    cs:__imp__invoke_watson
0x1800212dd  mov     rcx, rbx; void *
0x1800212e0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800212e5  mov     rax, rsi
0x1800212e8  mov     rcx, [rbp+57h+var_38]
0x1800212ec  xor     rcx, rsp; StackCookie
0x1800212ef  call    __security_check_cookie
0x1800212f4  add     rsp, 90h
0x1800212fb  pop     r15
0x1800212fd  pop     r14
0x1800212ff  pop     r12
0x180021301  pop     rdi
0x180021302  pop     rsi
0x180021303  pop     rbx
0x180021304  pop     rbp
0x180021305  retn
0x180021306  lfence
0x180021309  lea     rdx, [rbp+57h+var_88]
0x18002130d  mov     ecx, eax
0x18002130f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
