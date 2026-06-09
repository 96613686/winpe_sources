# _winrt::Microsoft::Windows::SemanticSearch::implementation::AiFabricModelFactories::RegisterAiFabricModels_::_2_::_lambda_1_::operator()_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::RegisterEmbeddingModelFactoryResult_

- ea: `0x1800487e0`
- end: `0x180048ac0`
- name: `_winrt::Microsoft::Windows::SemanticSearch::implementation::AiFabricModelFactories::RegisterAiFabricModels_::_2_::_lambda_1_::operator()_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::RegisterEmbeddingModelFactoryResult_`
- size: `736`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180045b00`

## callees

- `0x180001f60`
- `0x180007fe0`
- `0x180008520`
- `0x180009580`
- `0x1800487e0`
- `0x18004a3f0`
- `0x18004c070`
- `0x180051379`
- `0x18005137f`
- `0x18005e260`
- `0x18005e2c0`
- `0x18005e770`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180048962`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800489aa`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180048962`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800489aa`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004896e`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800489b6`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004896e`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800489b6`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180048a49`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180048a52`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180048a49`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180048a52`

## string_xrefs

- `0x180048823`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
wchar_t *__fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::AiFabricModelFactories::RegisterAiFabricModels_::_2_::_lambda_1_::operator()_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::RegisterEmbeddingModelFactoryResult_(
        __int64 a1,
        wchar_t *a2,
        _QWORD *a3)
{
  unsigned __int64 v5; // r15
  int v6; // eax
  int v7; // eax
  __int64 v8; // rax
  unsigned int v9; // edx
  volatile signed __int32 *v10; // rbx
  __int64 v11; // rsi
  const void *v12; // r13
  struct winrt::impl::shared_hstring_header *v13; // rdi
  bool v14; // zf
  size_t v15; // rsi
  void *v16; // rcx
  _WORD *v17; // rcx
  __int64 *v18; // rdx
  int v19; // eax
  HANDLE ProcessHeap; // rax
  signed __int32 v21; // r12d
  HANDLE v22; // rax
  __int128 v24; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *v25; // [rsp+80h] [rbp-80h] BYREF
  const char *v26; // [rsp+88h] [rbp-78h]
  LPVOID lpMem; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v28[16]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t Buffer[40]; // [rsp+B0h] [rbp-50h] BYREF

  v25 = a2;
  v5 = 0;
  v28[0] = 0;
  LODWORD(v24) = 514;
  *((_QWORD *)&v24 + 1) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generate"
                          "d Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v6 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*a3 + 64LL))(*a3, v28);
  if ( v6 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v6, &v24);
  }
  if ( v28[0] )
  {
    *(_OWORD *)a2 = 0;
    *((_QWORD *)a2 + 2) = 0;
    *((_QWORD *)a2 + 3) = 0;
    std::wstring::_Construct<1,wchar_t const *>(a2, &qword_18006D0D8, 0);
    return a2;
  }
  v24 = 0;
  LODWORD(v25) = 520;
  v26 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\Mi"
        "crosoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*a3 + 72LL))(*a3, &v24);
  if ( v7 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v7, &v25);
  }
  swprintf_s<40>(
    Buffer,
    (wchar_t *)L"{%08x-%04hx-%04hx-%02hhx%02hhx-%02hhx%02hhx%02hhx%02hhx%02hhx%02hhx}",
    (unsigned int)v24,
    WORD2(v24),
    WORD3(v24),
    BYTE8(v24),
    BYTE9(v24),
    BYTE10(v24),
    BYTE11(v24),
    BYTE12(v24),
    BYTE13(v24),
    BYTE14(v24),
    HIBYTE(v24));
  v25 = Buffer;
  v8 = -1;
  do
    ++v8;
  while ( Buffer[v8] );
  v26 = (const char *)v8;
  winrt::hstring::hstring((struct winrt::impl::shared_hstring_header **)&lpMem, (__int64)&v25);
  v10 = (volatile signed __int32 *)lpMem;
  if ( !lpMem )
  {
    v13 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)1, v9);
    v15 = 0;
    goto LABEL_16;
  }
  v11 = *((unsigned int *)lpMem + 1);
  v12 = (const void *)*((_QWORD *)lpMem + 2);
  if ( (_DWORD)v11 != -1 )
  {
    v13 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)(v11 + 1), v9);
    v14 = 2 * v11 == 0;
    v15 = 2 * v11;
    v16 = (void *)*((_QWORD *)v13 + 2);
    if ( !v14 )
    {
      if ( v16 )
      {
        if ( v12 )
        {
          memmove(v16, v12, v15);
          goto LABEL_16;
        }
        memset(v16, 0, v15);
      }
      *_errno() = 22;
      _invalid_parameter_noinfo();
    }
LABEL_16:
    v17 = (_WORD *)(v15 + *((_QWORD *)v13 + 2));
    if ( v17 )
    {
      *v17 = 10;
    }
    else
    {
      *_errno() = 22;
      _invalid_parameter_noinfo();
    }
    v25 = (wchar_t *)v13;
    goto LABEL_20;
  }
  v25 = 0;
  v13 = 0;
LABEL_20:
  *(_OWORD *)a2 = 0;
  *((_QWORD *)a2 + 2) = 0;
  *((_QWORD *)a2 + 3) = 0;
  if ( v13 )
  {
    v18 = (__int64 *)*((_QWORD *)v13 + 2);
    v5 = *((unsigned int *)v13 + 1);
  }
  else
  {
    v18 = &qword_18006D0D8;
  }
  std::wstring::_Construct<1,wchar_t const *>(a2, v18, v5);
  if ( v13 )
  {
    v19 = _InterlockedDecrement((volatile signed __int32 *)v13 + 6);
    if ( v19 )
    {
      if ( v19 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v13);
    }
  }
  if ( v10 )
  {
    v21 = _InterlockedExchangeAdd(v10 + 6, 0xFFFFFFFF);
    if ( v21 == 1 )
    {
      v22 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v22, 0, (LPVOID)v10);
    }
    else if ( v21 - 1 < 0 )
    {
      abort();
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1800487e0  mov     [rsp-8+arg_0], rbx
0x1800487e5  push    rbp
0x1800487e6  push    rsi
0x1800487e7  push    rdi
0x1800487e8  push    r12
0x1800487ea  push    r13
0x1800487ec  push    r14
0x1800487ee  push    r15
0x1800487f0  lea     rbp, [rsp-10h]
0x1800487f5  sub     rsp, 110h
0x1800487fc  mov     rax, cs:__security_cookie
0x180048803  xor     rax, rsp
0x180048806  mov     [rbp+40h+var_40], rax
0x18004880a  mov     rbx, r8
0x18004880d  mov     r14, rdx
0x180048810  mov     [rbp+40h+var_C0], rdx
0x180048814  xor     r15d, r15d
0x180048817  mov     [rbp+40h+var_A0], r15b
0x18004881b  mov     dword ptr [rsp+140h+var_D0], 202h
0x180048823  lea     rdi, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18004882a  mov     qword ptr [rsp+140h+var_D0+8], rdi
0x18004882f  mov     rcx, [r8]
0x180048832  mov     rax, [rcx]
0x180048835  lea     rdx, [rbp+40h+var_A0]
0x180048839  mov     rax, [rax+40h]
0x18004883d  call    cs:__guard_dispatch_icall_fptr
0x180048843  test    eax, eax
0x180048845  js      loc_180048AB0
0x18004884b  xorps   xmm0, xmm0
0x18004884e  cmp     [rbp+40h+var_A0], r15b
0x180048852  jnz     loc_180048A59
0x180048858  movups  [rsp+140h+var_D0], xmm0
0x18004885d  mov     dword ptr [rbp+40h+var_C0], 208h
0x180048864  mov     [rbp+40h+var_B8], rdi
0x180048868  mov     rcx, [rbx]
0x18004886b  mov     rax, [rcx]
0x18004886e  lea     rdx, [rsp+140h+var_D0]
0x180048873  mov     rax, [rax+48h]
0x180048877  call    cs:__guard_dispatch_icall_fptr
0x18004887d  test    eax, eax
0x18004887f  js      loc_180048AA1
0x180048885  movzx   eax, byte ptr [rsp+140h+var_D0+0Fh]
0x18004888a  movzx   ecx, byte ptr [rsp+140h+var_D0+0Eh]
0x18004888f  movzx   edx, byte ptr [rsp+140h+var_D0+0Dh]
0x180048894  movzx   r8d, byte ptr [rsp+140h+var_D0+0Ch]
0x18004889a  movzx   r10d, byte ptr [rsp+140h+var_D0+0Bh]
0x1800488a0  movzx   r11d, byte ptr [rsp+140h+var_D0+0Ah]
0x1800488a6  movzx   ebx, byte ptr [rsp+140h+var_D0+9]
0x1800488ab  movzx   edi, byte ptr [rsp+140h+var_D0+8]
0x1800488b0  movzx   esi, word ptr [rsp+140h+var_D0+6]
0x1800488b5  movzx   r9d, word ptr [rsp+140h+var_D0+4]
0x1800488bb  mov     [rsp+140h+var_E0], eax
0x1800488bf  mov     [rsp+140h+var_E8], ecx
0x1800488c3  mov     [rsp+140h+var_F0], edx
0x1800488c7  mov     [rsp+140h+var_F8], r8d
0x1800488cc  mov     [rsp+140h+var_100], r10d
0x1800488d1  mov     [rsp+140h+var_108], r11d
0x1800488d6  mov     [rsp+140h+var_110], ebx
0x1800488da  mov     [rsp+140h+var_118], edi
0x1800488de  mov     [rsp+140h+var_120], esi
0x1800488e2  mov     r8d, dword ptr [rsp+140h+var_D0]
0x1800488e7  lea     rdx, a08x04hx04hx02h; "{%08x-%04hx-%04hx-%02hhx%02hhx-%02hhx%0"...
0x1800488ee  lea     rcx, [rbp+40h+Buffer]; Buffer
0x1800488f2  call    ??$swprintf_s@$0CI@@@YAHAEAY0CI@_WPEB_WZZ; swprintf_s<40>(wchar_t (&)[40],wchar_t const *,...)
0x1800488f7  lea     rax, [rbp+40h+Buffer]
0x1800488fb  mov     [rbp+40h+var_C0], rax
0x1800488ff  lea     rcx, [rbp+40h+Buffer]
0x180048903  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18004890a  mov     rax, r12
0x18004890d  nop     dword ptr [rax]
0x180048910  inc     rax
0x180048913  cmp     [rcx+rax*2], r15w
0x180048918  jnz     short loc_180048910
0x18004891a  mov     [rbp+40h+var_B8], rax
0x18004891e  lea     rdx, [rbp+40h+var_C0]
0x180048922  lea     rcx, [rbp+40h+lpMem]
0x180048926  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x18004892b  nop
0x18004892c  mov     rbx, [rbp+40h+lpMem]
0x180048930  test    rbx, rbx
0x180048933  jz      short loc_180048991
0x180048935  mov     esi, [rbx+4]
0x180048938  mov     r13, [rbx+10h]
0x18004893c  lea     ecx, [rsi+1]; this
0x18004893f  test    ecx, ecx
0x180048941  jnz     short loc_18004894C
0x180048943  mov     [rbp+40h+var_C0], r15
0x180048947  mov     rdi, r15
0x18004894a  jmp     short loc_1800489C7
0x18004894c  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180048951  mov     rdi, rax
0x180048954  add     rsi, rsi
0x180048957  mov     rcx, [rax+10h]; void *
0x18004895b  jz      short loc_1800489A1
0x18004895d  test    rcx, rcx
0x180048960  jnz     short loc_180048976
0x180048962  call    cs:__imp__errno
0x180048968  mov     dword ptr [rax], 16h
0x18004896e  call    cs:__imp__invalid_parameter_noinfo
0x180048974  jmp     short loc_1800489A1
0x180048976  mov     r8, rsi; Size
0x180048979  test    r13, r13
0x18004897c  jz      short loc_180048988
0x18004897e  mov     rdx, r13; Src
0x180048981  call    memmove
0x180048986  jmp     short loc_1800489A1
0x180048988  xor     edx, edx; Val
0x18004898a  call    memset
0x18004898f  jmp     short loc_180048962
0x180048991  mov     ecx, 1; this
0x180048996  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18004899b  mov     rdi, rax
0x18004899e  mov     rsi, r15
0x1800489a1  mov     rcx, [rdi+10h]
0x1800489a5  add     rcx, rsi
0x1800489a8  jnz     short loc_1800489BE
0x1800489aa  call    cs:__imp__errno
0x1800489b0  mov     dword ptr [rax], 16h
0x1800489b6  call    cs:__imp__invalid_parameter_noinfo
0x1800489bc  jmp     short loc_1800489C3
0x1800489be  mov     word ptr [rcx], 0Ah
0x1800489c3  mov     [rbp+40h+var_C0], rdi
0x1800489c7  xorps   xmm0, xmm0
0x1800489ca  movups  xmmword ptr [r14], xmm0
0x1800489ce  mov     [r14+10h], r15
0x1800489d2  mov     [r14+18h], r15
0x1800489d6  test    rdi, rdi
0x1800489d9  jz      short loc_1800489E5
0x1800489db  mov     rdx, [rdi+10h]
0x1800489df  mov     r15d, [rdi+4]
0x1800489e3  jmp     short loc_1800489EC
0x1800489e5  lea     rdx, qword_18006D0D8
0x1800489ec  mov     r8, r15
0x1800489ef  mov     rcx, r14
0x1800489f2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800489f7  nop
0x1800489f8  test    rdi, rdi
0x1800489fb  jz      short loc_180048A1D
0x1800489fd  mov     eax, r12d
0x180048a00  lock xadd [rdi+18h], eax
0x180048a05  sub     eax, 1
0x180048a08  jnz     short loc_180048A45
0x180048a0a  call    WINRT_IMPL_GetProcessHeap
0x180048a0f  mov     rcx, rax; hHeap
0x180048a12  mov     r8, rdi; lpMem
0x180048a15  xor     edx, edx; dwFlags
0x180048a17  call    WINRT_IMPL_HeapFree
0x180048a1c  nop
0x180048a1d  test    rbx, rbx
0x180048a20  jz      short loc_180048A77
0x180048a22  lock xadd [rbx+18h], r12d
0x180048a28  lea     eax, [r12-1]
0x180048a2d  test    eax, eax
0x180048a2f  jnz     short loc_180048A50
0x180048a31  call    WINRT_IMPL_GetProcessHeap
0x180048a36  mov     rcx, rax; hHeap
0x180048a39  mov     r8, rbx; lpMem
0x180048a3c  xor     edx, edx; dwFlags
0x180048a3e  call    WINRT_IMPL_HeapFree
0x180048a43  jmp     short loc_180048A77
0x180048a45  test    eax, eax
0x180048a47  jns     short loc_180048A1D
0x180048a49  call    cs:__imp_abort
0x180048a50  jns     short loc_180048A77
0x180048a52  call    cs:__imp_abort
0x180048a59  movups  xmmword ptr [r14], xmm0
0x180048a5d  mov     [r14+10h], r15
0x180048a61  mov     [r14+18h], r15
0x180048a65  xor     r8d, r8d
0x180048a68  lea     rdx, qword_18006D0D8
0x180048a6f  mov     rcx, r14
0x180048a72  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180048a77  mov     rax, r14
0x180048a7a  mov     rcx, [rbp+40h+var_40]
0x180048a7e  xor     rcx, rsp; StackCookie
0x180048a81  call    __security_check_cookie
0x180048a86  mov     rbx, [rsp+140h+arg_0]
0x180048a8e  add     rsp, 110h
0x180048a95  pop     r15
0x180048a97  pop     r14
0x180048a99  pop     r13
0x180048a9b  pop     r12
0x180048a9d  pop     rdi
0x180048a9e  pop     rsi
0x180048a9f  pop     rbp
0x180048aa0  retn
0x180048aa1  lfence
0x180048aa4  lea     rdx, [rbp+40h+var_C0]
0x180048aa8  mov     ecx, eax
0x180048aaa  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180048ab0  lfence
0x180048ab3  lea     rdx, [rsp+140h+var_D0]
0x180048ab8  mov     ecx, eax
0x180048aba  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
