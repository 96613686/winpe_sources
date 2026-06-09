# winrt::Microsoft::Windows::Workloads::implementation::Workload::InitManifestPackageItem(winrt::hstring const &)

- ea: `0x180015b30`
- end: `0x180015dee`
- name: `?InitManifestPackageItem@Workload@implementation@Workloads@Windows@Microsoft@winrt@@AEAAXAEBUhstring@6@@Z`
- size: `702`
- prototype: `void __fastcall(winrt::Microsoft::Windows::Workloads::implementation::Workload *__hidden this, const struct winrt::hstring *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015860`

## callees

- `0x1800027d0`
- `0x1800029f0`
- `0x1800040a0`
- `0x180004810`
- `0x180015b30`
- `0x180030ae5`
- `0x180030aeb`
- `0x180032dd0`
- `0x180034ef0`
- `0x18003bed0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180015d68`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180015d68`

## pseudocode

```c
void __fastcall winrt::Microsoft::Windows::Workloads::implementation::Workload::InitManifestPackageItem(
        winrt::Microsoft::Windows::Workloads::implementation::Workload *this,
        const struct winrt::hstring *a2)
{
  int v4; // eax
  int v5; // esi
  unsigned int v6; // r14d
  int v7; // eax
  int v8; // esi
  int v9; // eax
  unsigned int v10; // esi
  int v11; // eax
  LPVOID v12; // rbx
  const wchar_t *v13; // rdx
  volatile signed __int32 *v14; // rdi
  unsigned __int64 v15; // r8
  int v16; // eax
  HANDLE ProcessHeap; // rax
  const wchar_t *v18; // r8
  unsigned __int64 v19; // r9
  __int128 *v20; // rdi
  char *v21; // rbx
  __int64 v22; // rax
  _QWORD *v23; // rbx
  __int64 v24; // rcx
  LPVOID lpMem; // [rsp+20h] [rbp-50h] BYREF
  __int64 v26; // [rsp+28h] [rbp-48h] BYREF
  __int64 v27; // [rsp+30h] [rbp-40h] BYREF
  int v28; // [rsp+38h] [rbp-38h] BYREF
  __int128 v29; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int64 v30; // [rsp+50h] [rbp-20h]
  unsigned __int64 v31; // [rsp+58h] [rbp-18h]
  __int64 v32; // [rsp+60h] [rbp-10h] BYREF

  LODWORD(lpMem) = 0;
  if ( *(_QWORD *)a2 )
  {
    v26 = 0;
    v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 5) + 80LL))(*((_QWORD *)this + 5), &v26);
    if ( v4 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v4);
    }
    v32 = v26;
    v5 = 8;
    v6 = 0;
    v28 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v26 + 56LL))(v26, &v28);
    if ( v7 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v7);
    }
    if ( v28 )
    {
      while ( 1 )
      {
        v27 = 0;
        v8 = v5 | 2;
        LODWORD(lpMem) = v8;
        v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v26 + 48LL))(v26, v6, &v27);
        if ( v9 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v9);
        }
        v10 = v8 & 0xFFFFFFFC | 1;
        lpMem = 0;
        v11 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v27 + 64LL))(v27, &lpMem);
        if ( v11 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v11);
        }
        v12 = lpMem;
        v5 = v10 | 4;
        if ( lpMem )
        {
          v13 = (const wchar_t *)*((_QWORD *)lpMem + 2);
          v14 = (volatile signed __int32 *)lpMem;
        }
        else
        {
          v13 = &Src;
          v14 = 0;
        }
        v29 = 0;
        v30 = 0;
        v31 = 0;
        v15 = -1;
        do
          ++v15;
        while ( v13[v15] );
        std::wstring::_Construct<1,wchar_t const *>(&v29, v13, v15);
        if ( v12 )
        {
          v16 = _InterlockedDecrement(v14 + 6);
          if ( v16 )
          {
            if ( v16 < 0 )
              abort();
          }
          else
          {
            ProcessHeap = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v14);
          }
        }
        if ( *(_QWORD *)a2 )
          v18 = *(const wchar_t **)(*(_QWORD *)a2 + 16LL);
        else
          v18 = &Src;
        v19 = -1;
        do
          ++v19;
        while ( v18[v19] );
        v20 = &v29;
        if ( v31 > 7 )
          v20 = (__int128 *)v29;
        if ( v19 <= v30 )
        {
          _mm_lfence();
          if ( !v19 )
            break;
          v21 = (char *)v20 + 2 * v30;
          v22 = _std_search_2(v20, v21, v18, v19);
          if ( (char *)v22 != v21 && (unsigned __int64)(v22 - (_QWORD)v20) < 2 )
            break;
        }
        std::wstring::_Tidy_deallocate((__int64)&v29);
        if ( v27 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v27);
        if ( ++v6 == v28 )
          goto LABEL_30;
      }
      v23 = (_QWORD *)((char *)this + 48);
      if ( (__int64 *)((char *)this + 48) != &v27 )
      {
        if ( *v23 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((char *)this + 48);
        v24 = v27;
        *v23 = v27;
        if ( v24 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
      }
      std::wstring::_Tidy_deallocate((__int64)&v29);
      if ( v27 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v27);
    }
LABEL_30:
    if ( v26 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v32);
  }
}

```

## disassembly

```asm
0x180015b30  mov     [rsp-38h+arg_10], rbx
0x180015b35  push    rbp
0x180015b36  push    rsi
0x180015b37  push    rdi
0x180015b38  push    r12
0x180015b3a  push    r13
0x180015b3c  push    r14
0x180015b3e  push    r15
0x180015b40  mov     rbp, rsp
0x180015b43  sub     rsp, 70h
0x180015b47  mov     rax, cs:__security_cookie
0x180015b4e  xor     rax, rsp
0x180015b51  mov     [rbp+var_8], rax
0x180015b55  mov     r15, rdx
0x180015b58  mov     r13, rcx
0x180015b5b  xor     r12d, r12d
0x180015b5e  mov     dword ptr [rbp+lpMem], r12d
0x180015b62  cmp     [rdx], r12
0x180015b65  jz      loc_180015D44
0x180015b6b  mov     [rbp+var_48], r12
0x180015b6f  mov     rcx, [rcx+28h]
0x180015b73  mov     rax, [rcx]
0x180015b76  lea     rdx, [rbp+var_48]
0x180015b7a  mov     rax, [rax+50h]
0x180015b7e  call    cs:__guard_dispatch_icall_fptr
0x180015b84  test    eax, eax
0x180015b86  js      loc_180015DD8
0x180015b8c  mov     rcx, [rbp+var_48]
0x180015b90  mov     [rbp+var_10], rcx
0x180015b94  mov     esi, 8
0x180015b99  mov     r14d, r12d
0x180015b9c  mov     [rbp+var_38], r12d
0x180015ba0  mov     rax, [rcx]
0x180015ba3  lea     rdx, [rbp+var_38]
0x180015ba7  mov     rax, [rax+38h]
0x180015bab  call    cs:__guard_dispatch_icall_fptr
0x180015bb1  test    eax, eax
0x180015bb3  js      loc_180015DE3
0x180015bb9  cmp     [rbp+var_38], r12d
0x180015bbd  jz      loc_180015D34
0x180015bc3  nop     dword ptr [rax+00h]
0x180015bc7  nop     word ptr [rax+rax+00000000h]
0x180015bd0  mov     [rbp+var_40], r12
0x180015bd4  or      esi, 2
0x180015bd7  mov     dword ptr [rbp+lpMem], esi
0x180015bda  mov     rcx, [rbp+var_48]
0x180015bde  mov     rax, [rcx]
0x180015be1  lea     r8, [rbp+var_40]
0x180015be5  mov     edx, r14d
0x180015be8  mov     rax, [rax+30h]
0x180015bec  call    cs:__guard_dispatch_icall_fptr
0x180015bf2  test    eax, eax
0x180015bf4  js      loc_180015DCD
0x180015bfa  and     esi, 0FFFFFFFDh
0x180015bfd  or      esi, 1
0x180015c00  mov     [rbp+lpMem], r12
0x180015c04  mov     rcx, [rbp+var_40]
0x180015c08  mov     rax, [rcx]
0x180015c0b  lea     rdx, [rbp+lpMem]
0x180015c0f  mov     rax, [rax+40h]
0x180015c13  call    cs:__guard_dispatch_icall_fptr
0x180015c19  test    eax, eax
0x180015c1b  js      loc_180015DC2
0x180015c21  mov     rbx, [rbp+lpMem]
0x180015c25  mov     [rbp+lpMem], rbx
0x180015c29  or      esi, 4
0x180015c2c  test    rbx, rbx
0x180015c2f  jz      short loc_180015C3A
0x180015c31  mov     rdx, [rbx+10h]
0x180015c35  mov     rdi, rbx
0x180015c38  jmp     short loc_180015C44
0x180015c3a  lea     rdx, Src
0x180015c41  mov     rdi, r12
0x180015c44  xorps   xmm0, xmm0
0x180015c47  movups  [rbp+var_30], xmm0
0x180015c4b  mov     [rbp+var_20], r12
0x180015c4f  mov     [rbp+var_18], r12
0x180015c53  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180015c5a  nop     word ptr [rax+rax+00h]
0x180015c60  inc     r8
0x180015c63  cmp     word ptr [rdx+r8*2], 0
0x180015c69  jnz     short loc_180015C60
0x180015c6b  lea     rcx, [rbp+var_30]
0x180015c6f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180015c74  nop
0x180015c75  test    rbx, rbx
0x180015c78  jz      short loc_180015CA5
0x180015c7a  mov     eax, 0FFFFFFFFh
0x180015c7f  lock xadd [rdi+18h], eax
0x180015c84  sub     eax, 1
0x180015c87  jnz     short loc_180015C9D
0x180015c89  call    WINRT_IMPL_GetProcessHeap
0x180015c8e  mov     rcx, rax; hHeap
0x180015c91  mov     r8, rdi; lpMem
0x180015c94  xor     edx, edx; dwFlags
0x180015c96  call    WINRT_IMPL_HeapFree
0x180015c9b  jmp     short loc_180015CA5
0x180015c9d  test    eax, eax
0x180015c9f  js      loc_180015D68
0x180015ca5  mov     r8, [r15]
0x180015ca8  test    r8, r8
0x180015cab  jz      short loc_180015CB3
0x180015cad  mov     r8, [r8+10h]
0x180015cb1  jmp     short loc_180015CBA
0x180015cb3  lea     r8, Src
0x180015cba  mov     r9, 0FFFFFFFFFFFFFFFFh
0x180015cc1  inc     r9
0x180015cc4  cmp     word ptr [r8+r9*2], 0
0x180015cca  jnz     short loc_180015CC1
0x180015ccc  lea     rdi, [rbp+var_30]
0x180015cd0  cmp     [rbp+var_18], 7
0x180015cd5  cmova   rdi, qword ptr [rbp+var_30]
0x180015cda  cmp     r9, [rbp+var_20]
0x180015cde  ja      short loc_180015D0D
0x180015ce0  lfence
0x180015ce3  test    r9, r9
0x180015ce6  jz      loc_180015D6F
0x180015cec  mov     rax, [rbp+var_20]
0x180015cf0  lea     rbx, [rdi+rax*2]
0x180015cf4  mov     rdx, rbx
0x180015cf7  mov     rcx, rdi
0x180015cfa  call    __std_search_2
0x180015cff  cmp     rax, rbx
0x180015d02  jz      short loc_180015D0D
0x180015d04  sub     rax, rdi
0x180015d07  cmp     rax, 2
0x180015d0b  jb      short loc_180015D6F
0x180015d0d  lea     rcx, [rbp+var_30]
0x180015d11  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015d16  nop
0x180015d17  cmp     [rbp+var_40], 0
0x180015d1c  jz      short loc_180015D27
0x180015d1e  lea     rcx, [rbp+var_40]
0x180015d22  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180015d27  inc     r14d
0x180015d2a  cmp     r14d, [rbp+var_38]
0x180015d2e  jnz     loc_180015BD0
0x180015d34  cmp     [rbp+var_48], 0
0x180015d39  jz      short loc_180015D44
0x180015d3b  lea     rcx, [rbp+var_10]
0x180015d3f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180015d44  mov     rcx, [rbp+var_8]
0x180015d48  xor     rcx, rsp; StackCookie
0x180015d4b  call    __security_check_cookie
0x180015d50  mov     rbx, [rsp+70h+arg_10]
0x180015d58  add     rsp, 70h
0x180015d5c  pop     r15
0x180015d5e  pop     r14
0x180015d60  pop     r13
0x180015d62  pop     r12
0x180015d64  pop     rdi
0x180015d65  pop     rsi
0x180015d66  pop     rbp
0x180015d67  retn
0x180015d68  call    cs:__imp_abort
0x180015d6f  lea     rbx, [r13+30h]
0x180015d73  lea     rax, [rbp+var_40]
0x180015d77  cmp     rbx, rax
0x180015d7a  jz      short loc_180015DA3
0x180015d7c  cmp     qword ptr [rbx], 0
0x180015d80  jz      short loc_180015D8A
0x180015d82  mov     rcx, rbx
0x180015d85  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180015d8a  mov     rcx, [rbp+var_40]
0x180015d8e  mov     [rbx], rcx
0x180015d91  test    rcx, rcx
0x180015d94  jz      short loc_180015DA3
0x180015d96  mov     rax, [rcx]
0x180015d99  mov     rax, [rax+8]
0x180015d9d  call    cs:__guard_dispatch_icall_fptr
0x180015da3  lea     rcx, [rbp+var_30]
0x180015da7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015dac  nop
0x180015dad  cmp     [rbp+var_40], 0
0x180015db2  jz      short loc_180015D34
0x180015db4  lea     rcx, [rbp+var_40]
0x180015db8  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180015dbd  jmp     loc_180015D34
0x180015dc2  lfence
0x180015dc5  mov     ecx, eax
0x180015dc7  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x180015dcd  lfence
0x180015dd0  mov     ecx, eax
0x180015dd2  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x180015dd8  lfence
0x180015ddb  mov     ecx, eax
0x180015ddd  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x180015de3  lfence
0x180015de6  mov     ecx, eax
0x180015de8  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
