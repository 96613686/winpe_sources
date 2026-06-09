# winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::RemovePackageFromPackageSetByFamilyName(winrt::Microsoft::Windows::Management::Deployment::PackageSet &,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x180006940`
- end: `0x180006b66`
- name: `?RemovePackageFromPackageSetByFamilyName@ApiInfo@implementation@Workloads@Windows@Microsoft@winrt@@AEAAXAEAUPackageSet@Deployment@Management@456@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z`
- size: `550`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180006110`

## callees

- `0x1800040a0`
- `0x180004810`
- `0x180006940`
- `0x180015250`
- `0x180030ae5`
- `0x180030aeb`
- `0x180034ef0`
- `0x18003bed0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006afb`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006afb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::RemovePackageFromPackageSetByFamilyName(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  signed int v4; // eax
  __int64 v5; // rdi
  unsigned int v6; // esi
  unsigned int v7; // r14d
  signed int v8; // eax
  int v9; // esi
  signed int v10; // eax
  signed int v11; // eax
  int v12; // esi
  volatile signed __int32 *v13; // rbx
  size_t v14; // r8
  const wchar_t *v15; // rcx
  bool v16; // bp
  int v17; // eax
  HANDLE ProcessHeap; // rax
  signed int v19; // eax
  __int64 v21; // [rsp+20h] [rbp-58h] BYREF
  __int64 v22; // [rsp+28h] [rbp-50h] BYREF
  __int64 v23; // [rsp+30h] [rbp-48h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-40h] BYREF
  unsigned int v25; // [rsp+40h] [rbp-38h] BYREF

  v25 = 0;
  v23 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a2 + 80LL))(*a2, &v23);
  if ( v4 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult(v4);
  }
  v5 = v23;
  v22 = v23;
  v6 = 1;
  v7 = 0;
  v25 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v23 + 56LL))(v23, &v25);
  if ( v8 < 0 )
LABEL_31:
    winrt::throw_hresult(v8);
  while ( v7 < v25 )
  {
    v21 = 0;
    v9 = v6 | 2;
    v25 = v9;
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v5 + 48LL))(v5, v7, &v21);
    if ( v10 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult(v10);
    }
    lpMem = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v21 + 64LL))(v21, &lpMem);
    if ( v11 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult(v11);
    }
    v12 = v9 | 4;
    v13 = (volatile signed __int32 *)lpMem;
    if ( lpMem )
    {
      v14 = *((unsigned int *)lpMem + 1);
      v15 = (const wchar_t *)*((_QWORD *)lpMem + 2);
    }
    else
    {
      v14 = 0;
      v15 = &Src;
    }
    if ( v14 == *(_QWORD *)(a3 + 8) )
    {
      if ( v14 )
        v16 = wmemcmp(v15, *(const wchar_t **)a3, v14) == 0;
      else
        v16 = 1;
    }
    else
    {
      v16 = 0;
    }
    if ( v13 )
    {
      v17 = _InterlockedDecrement(v13 + 6);
      if ( v17 )
      {
        if ( v17 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, lpMem);
      }
      v5 = v23;
    }
    v6 = v12 & 0xFFFFFFFD;
    if ( v21 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v21);
    if ( v16 )
    {
      v19 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 96LL))(v5, v7);
      if ( v19 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult(v19);
      }
    }
    else
    {
      ++v7;
    }
    v25 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 56LL))(v5, &v25);
    if ( v8 < 0 )
      goto LABEL_31;
  }
  return winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v22);
}

```

## disassembly

```asm
0x180006940  mov     [rsp+arg_0], rbx
0x180006945  mov     [rsp+arg_18], rbp
0x18000694a  push    rsi
0x18000694b  push    rdi
0x18000694c  push    r12
0x18000694e  push    r14
0x180006950  push    r15
0x180006952  sub     rsp, 50h
0x180006956  mov     rax, cs:__security_cookie
0x18000695d  xor     rax, rsp
0x180006960  mov     [rsp+78h+var_30], rax
0x180006965  mov     r15, r8
0x180006968  xor     r12d, r12d
0x18000696b  mov     [rsp+78h+var_38], r12d
0x180006970  mov     [rsp+78h+var_48], r12
0x180006975  mov     rcx, [rdx]
0x180006978  mov     rax, [rcx]
0x18000697b  lea     rdx, [rsp+78h+var_48]
0x180006980  mov     rax, [rax+50h]
0x180006984  call    cs:__guard_dispatch_icall_fptr
0x18000698a  test    eax, eax
0x18000698c  js      loc_180006B50
0x180006992  mov     rdi, [rsp+78h+var_48]
0x180006997  mov     [rsp+78h+var_50], rdi
0x18000699c  mov     esi, 1
0x1800069a1  mov     r14d, r12d
0x1800069a4  mov     [rsp+78h+var_38], r12d
0x1800069a9  mov     rax, [rdi]
0x1800069ac  lea     rdx, [rsp+78h+var_38]
0x1800069b1  mov     rcx, rdi
0x1800069b4  mov     rax, [rax+38h]
0x1800069b8  call    cs:__guard_dispatch_icall_fptr
0x1800069be  test    eax, eax
0x1800069c0  js      loc_180006B48
0x1800069c6  nop     word ptr [rax+rax+00000000h]
0x1800069d0  cmp     r14d, [rsp+78h+var_38]
0x1800069d5  jnb     loc_180006B02
0x1800069db  mov     [rsp+78h+var_58], r12
0x1800069e0  or      esi, 2
0x1800069e3  mov     [rsp+78h+var_38], esi
0x1800069e7  mov     rax, [rdi]
0x1800069ea  lea     r8, [rsp+78h+var_58]
0x1800069ef  mov     edx, r14d
0x1800069f2  mov     rcx, rdi
0x1800069f5  mov     rax, [rax+30h]
0x1800069f9  call    cs:__guard_dispatch_icall_fptr
0x1800069ff  test    eax, eax
0x180006a01  js      loc_180006B32
0x180006a07  mov     [rsp+78h+lpMem], r12
0x180006a0c  mov     rcx, [rsp+78h+var_58]
0x180006a11  mov     rax, [rcx]
0x180006a14  lea     rdx, [rsp+78h+lpMem]
0x180006a19  mov     rax, [rax+40h]
0x180006a1d  call    cs:__guard_dispatch_icall_fptr
0x180006a23  test    eax, eax
0x180006a25  js      loc_180006B5B
0x180006a2b  or      esi, 4
0x180006a2e  mov     rbx, [rsp+78h+lpMem]
0x180006a33  test    rbx, rbx
0x180006a36  jz      short loc_180006A42
0x180006a38  mov     r8d, [rbx+4]
0x180006a3c  mov     rcx, [rbx+10h]
0x180006a40  jmp     short loc_180006A4C
0x180006a42  mov     r8, r12; N
0x180006a45  lea     rcx, Src; S1
0x180006a4c  cmp     r8, [r15+8]
0x180006a50  jz      short loc_180006A57
0x180006a52  xor     bpl, bpl
0x180006a55  jmp     short loc_180006A6F
0x180006a57  test    r8, r8
0x180006a5a  jnz     short loc_180006A61
0x180006a5c  mov     bpl, 1
0x180006a5f  jmp     short loc_180006A6F
0x180006a61  mov     rdx, [r15]; S2
0x180006a64  call    wmemcmp
0x180006a69  test    eax, eax
0x180006a6b  setz    bpl
0x180006a6f  test    rbx, rbx
0x180006a72  jz      short loc_180006AA2
0x180006a74  mov     eax, 0FFFFFFFFh
0x180006a79  lock xadd [rbx+18h], eax
0x180006a7e  sub     eax, 1
0x180006a81  jnz     short loc_180006A99
0x180006a83  call    WINRT_IMPL_GetProcessHeap
0x180006a88  mov     rcx, rax; hHeap
0x180006a8b  mov     r8, [rsp+78h+lpMem]; lpMem
0x180006a90  xor     edx, edx; dwFlags
0x180006a92  call    WINRT_IMPL_HeapFree
0x180006a97  jmp     short loc_180006A9D
0x180006a99  test    eax, eax
0x180006a9b  js      short loc_180006AFB
0x180006a9d  mov     rdi, [rsp+78h+var_48]
0x180006aa2  and     esi, 0FFFFFFFDh
0x180006aa5  cmp     [rsp+78h+var_58], 0
0x180006aab  jz      short loc_180006AB7
0x180006aad  lea     rcx, [rsp+78h+var_58]
0x180006ab2  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180006ab7  test    bpl, bpl
0x180006aba  jz      short loc_180006AD5
0x180006abc  mov     rax, [rdi]
0x180006abf  mov     edx, r14d
0x180006ac2  mov     rcx, rdi
0x180006ac5  mov     rax, [rax+60h]
0x180006ac9  call    cs:__guard_dispatch_icall_fptr
0x180006acf  test    eax, eax
0x180006ad1  js      short loc_180006B3D
0x180006ad3  jmp     short loc_180006AD8
0x180006ad5  inc     r14d
0x180006ad8  mov     [rsp+78h+var_38], r12d
0x180006add  mov     rax, [rdi]
0x180006ae0  lea     rdx, [rsp+78h+var_38]
0x180006ae5  mov     rcx, rdi
0x180006ae8  mov     rax, [rax+38h]
0x180006aec  call    cs:__guard_dispatch_icall_fptr
0x180006af2  test    eax, eax
0x180006af4  js      short loc_180006B48
0x180006af6  jmp     loc_1800069D0
0x180006afb  call    cs:__imp_abort
0x180006b02  lea     rcx, [rsp+78h+var_50]
0x180006b07  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180006b0c  mov     rcx, [rsp+78h+var_30]
0x180006b11  xor     rcx, rsp; StackCookie
0x180006b14  call    __security_check_cookie
0x180006b19  lea     r11, [rsp+78h+var_28]
0x180006b1e  mov     rbx, [r11+30h]
0x180006b22  mov     rbp, [r11+48h]
0x180006b26  mov     rsp, r11
0x180006b29  pop     r15
0x180006b2b  pop     r14
0x180006b2d  pop     r12
0x180006b2f  pop     rdi
0x180006b30  pop     rsi
0x180006b31  retn
0x180006b32  lfence
0x180006b35  mov     ecx, eax
0x180006b37  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x180006b3d  lfence
0x180006b40  mov     ecx, eax
0x180006b42  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x180006b48  mov     ecx, eax
0x180006b4a  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x180006b50  lfence
0x180006b53  mov     ecx, eax
0x180006b55  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x180006b5b  lfence
0x180006b5e  mov     ecx, eax
0x180006b60  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
